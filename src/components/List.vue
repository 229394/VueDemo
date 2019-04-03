<template>
  <div class="col-md-8">
    <h3 class="reply">评论回复:</h3>
    <h3 v-show="comments.length===0">暂无评论,点击左侧添加评论!</h3>
    <ul class="list-group">
      <Item v-for="(comment,index) in comments" :key="index" :comment="comment" :deleteComment="deleteComment" :index="index"/>
    </ul>
  </div>
</template>

<script>
    import Item from './Item.vue'
    export default {
      //声明接收属性,这个属性就会成为组件对象的属性
      //此处只指定了属性名
      props: ['comments', 'deleteComment'],
      components: {
        Item
      }

    }
</script>

<style>
  .reply {
    margin-top: 0px;
  }
</style>
