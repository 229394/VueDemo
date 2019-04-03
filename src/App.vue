<template>
  <div>
    <header class="site-header jumbotron">
      <div class="container">
        <div class="row">
          <div class="col-xs-12">
            <h2>请对即将上映的复联4发表评论</h2>
          </div>
        </div>
      </div>
    </header>
    <div class="container">
      <Add :addComment="addComment"/>
      <List :comments="comments" :deleteComment="deleteComment"/>
    </div>
  </div>
</template>

<script>
  import Add from './components/Add.vue'
  import List from './components/List.vue'
  export default {

    data () {
      return {
        //数据在哪个组件,更新数据的方法就应该定义在哪个组件
        comments: [
          {
            name: 'lsq',
            content: '复联是啥?(手动滑稽)'
          },
          {
            name: 'autumn_leaf',
            content: '这部电影值得一看!'
          },
          {
            name: 'taotao',
            content: '复联大结局必去!'
          }
        ]
      }
    },
    methods: {
      //添加评论
      addComment (comment) {
        this.comments.unshift(comment)
      },
      //删除指定下标的评论
      deleteComment (index) {
        this.comments.splice(index, 1)
      }
    },
    components: {
      Add,
      List
    }

}
</script>

<style>

</style>
