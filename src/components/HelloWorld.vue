<template>
  <div class="box">
    <ul class="box_head clearfix">
      <li class="head_item fl">商品ID</li>
      <li class="head_item fl">商品名称</li>
      <li class="head_item fl">描述</li>
    </ul>
    <ul class="box_list">
      <li class="list_box" v-for="(item,index) in list">
        <div class="list_head">
          <ul class="head_box clearfix">
            <li class="head_item flag fl" :class="{active:isFlag ===index}" @click="OnOff(index)"></li>
            <li class="head_item fl">{{item.ID}}</li>
            <li class="head_item fl">{{item.name}}</li>
            <li class="head_item fl">{{item.directory}}</li>
          </ul>
        </div>
        <div class="list_inner" v-if="isFlag === index">
          <ul class="list_box clearfix">
            <li class="list_item fl clearfix">
              <span class="item_title fl">商品名称</span>
              <span class="item_inner fl">{{item.name}}</span>
            </li>
            <li class="list_item fl clearfix">
              <span class="item_title fl">所属店铺</span>
              <span class="item_inner fl">{{item.ssdp}}</span>
            </li>
            <li class="list_item fl clearfix">
              <span class="item_title fl">商品ID</span>
              <span class="item_inner fl">{{item.ID}}</span>
            </li>
            <li class="list_item fl clearfix">
              <span class="item_title fl">店铺ID</span>
              <span class="item_inner fl">{{item.dpid}}</span>
            </li>
            <li class="list_item fl clearfix">
              <span class="item_title fl">商品分类</span>
              <span class="item_inner fl">{{item.spfl}}</span>
            </li>
            <li class="list_item fl clearfix">
              <span class="item_title fl">店铺地址</span>
              <span class="item_inner fl">{{item.dpdz}}</span>
            </li>
            <li class="list_item fl clearfix">
              <span class="item_title fl">商品描述</span>
              <span class="item_inner fl">{{item.directory}}</span>
            </li>
          </ul>
        </div>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  data () {
    return {
      list:[
        {ID:'12345',name:'好滋味鸡蛋仔',describe:'荷兰优质蛋奶，奶香浓而不腻',spfl:'江浙小吃',ssdp:'王小虎夫妻店', dpid:'11100',dpdz:'上海'},
        {ID:'12345',name:'好滋味鸡蛋仔',describe:'荷兰优质蛋奶，奶香浓而不腻',spfl:'江浙小吃',ssdp:'王小虎夫妻店', dpid:'11100',dpdz:'上海'},
        {ID:'12345',name:'好滋味鸡蛋仔',describe:'荷兰优质蛋奶，奶香浓而不腻',spfl:'江浙小吃',ssdp:'王小虎夫妻店', dpid:'11100',dpdz:'上海'},
        {ID:'12345',name:'好滋味鸡蛋仔',describe:'荷兰优质蛋奶，奶香浓而不腻',spfl:'江浙小吃',ssdp:'王小虎夫妻店', dpid:'11100',dpdz:'上海'},
        {ID:'12345',name:'好滋味鸡蛋仔',describe:'荷兰优质蛋奶，奶香浓而不腻',spfl:'江浙小吃',ssdp:'王小虎夫妻店', dpid:'11100',dpdz:'上海'}
      ],
      isFlag:0,//显示第一个
    }
  },
  methods: {
    OnOff:function(flag){
      this.isFlag = flag;
    },
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="stylus">
rectangle(a,b)
  width a
  height b
.clearfix:after {
    content: ".";
    display: block;
    clear: both;
    visibility: hidden;
    line-height: 0;
    height: 0;
    font-size: 0;
}
.clearfix {
    *zoom: 1;
}
.fl {
    float: left;
}
.fr {
    float: right;
}
*
  padding:0;
  margin:0;
  list-style: none;
  font-style: normal;
.box
  rectangle(1024px,auto)
  margin 0 auto
  border 1px solid #dddddd
  border-bottom 0
  .box_head
    rectangle(100%,40px)
    background #cdc7c7
    font-size 24px
    color #333333
    line-height 40px
    border-bottom 1px solid #dddddd
    .head_item
      rectangle(30%,100%)
      &:first-child
        rectangle(40%,100%)
  .box_list
    rectangle(100%,auto)
    .list_box
      rectangle(100%,auto)
      border-bottom 1px solid #dddddd
      .list_head
        rectangle(100%,40px)
        line-height 40px
        .head_box
          rectangle(100%,100%)
          background #cdc7c7
          font-size 24px
          color #666666
          line-height 40px
          .head_item
            rectangle(30%,100%)
            &:first-child
              rectangle(10%,100%)
              cursor pointer
            &.flag
              background red
      .list_inner
        padding 5px 10px
        rectangle( calc(100% - 20px),calc(100% - 10px))
        background #d7d7d7
        .list_box
          rectangle(100%,100%)
          border none
          .list_item
            rectangle(50%,34px)
            font-size 22px
            .item_title
              display block
              rectangle(30%,100%)
              color red
            .item_inner
              display block
              rectangle(70%,100%)
              color #666666


</style>
