<template>
  <div>
      <div class="bookInfo" @click="handleBookList">
        <img class="bookImg" :src="book.image" alt="">
        <p>{{book.title}}</p>
        <p>作者：{{book.author}}</p>
        <p>出版社: {{book.publisher}}</p>
        <p class="bookPrice">{{book.price}}</p>
        <button>收藏该文章</button>
        <div>
          <h5>作者简介</h5>
          <span>{{book.summary}}</span>
        </div>
        <div>
          <h5></h5>
          <span></span>
        </div>
      </div>
  </div>
</template>

<script>
  export default {
    data () {
      return {
        book: {}
      }
    },
    mounted(){
      console.log(this)
      let booksList = JSON.parse(this.$mp.query.booksList)
      let index = JSON.parse(this.$mp.query.index)
      console.log('booksList',booksList)
      console.log('index',index)
      this.book=booksList[index]
      console.log(this.book,'this.book')
    }
  }

//    onLoad(options){
//      // 演示
//      console.log(options);
//    },

</script>

<style lang="stylus" rel="stylesheet/stylus">
  #bookListContainer
    display flex
    padding 10rpx
    border-bottom 1rpx solid #eee
    img
      width 140rpx
      height 140rpx
      margin-right 20rpx
    .bookInfo
      p
        font-size 28rpx
        line-height 50rpx
    .bookPrice
      position absolute
      right 30rpx
      font-size 36rpx
      font-weight bold
      color red
</style>
