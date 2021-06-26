<template>
  <div class="wrapper">
    <div class="header">
      <div>
        <button class="rounded-lg opacity-60 hover:opacity-100 dark:bg-gray-100 hover:shadow-md p-2 ease-transition">
            <img src="../assets/images/more.svg"  class="menu" alt="">
        </button>
      </div>
    </div>
    <div class="content">
      <img
        class="avatar"
        :alt="content.trainer"
        :src="content.image"
      />
      <div class="centered-row pt-2">
          <h2 class="instructor">{{content.trainer}}</h2> 
          <span v-if="content.isPro" class="tag">PRO</span>
      </div>
      <div class="centered-row pt-2">
          <h2 class="rating">{{content.rating}}</h2> 
          <img src="../assets/images/etoile.png"  class="star" alt="">
      </div>
      <ul class="centered-row my-8 flex-wrap">
          <li v-for="(keyword,index) in content.keywords" :key="keyword" class="keyword">{{keyword}}<span v-if="index < content.keywords.length -1" class="dot">·</span> </li>
      </ul>
      <div class="details">
          <div class="detail">
              <h3 class="details__title">Students</h3>
              <p class="details__value">{{content.students}}</p>
          </div>
          <div class="detail">
              <h3 class="details__title">Sessions</h3>
              <p class="details__value">{{content.sessions}}</p>
          </div>
          <div class="detail">
              <h3 class="details__title">Docs</h3>
              <p class="details__value">{{content.docs}}</p>
          </div>
      </div>
      <button class="action-btn ease-transition">Schedule session</button>
    </div>
  </div>
</template>

<style scoped>
.wrapper {
  @apply  rounded-lg shadow-lg overflow-hidden max-w-xl dark:bg-gray-700;
 width: fit-content;
}
.header {
  @apply bg-gray-50 dark:bg-gray-800 flex justify-end p-10;
}
.menu {
    @apply opacity-50;
    width : 2em;
}
.avatar {
  width: 8em;
  height: 8em;
  object-fit: cover;
  @apply rounded-full -mt-12;
}
.content {
    @apply px-10 md:px-14;
}
.centered-row {
    @apply flex text-center justify-start items-center;
}
.instructor {
@apply font-bold text-gray-800 dark:text-green-50 text-xl md:text-2xl mr-4;
}
.tag{
    @apply py-1 px-2 font-bold bg-yellow-200 text-gray-400 text-opacity-70 rounded-md;
}
.star {
    @apply flex justify-start items-center mx-4;
    max-width : 1.5em;
    max-height: 1.5em
}
.rating {
    @apply text-blue-400 text-xl font-bold;
}
.dot{
    @apply m-2 text-2xl font-bold text-opacity-50;
}
.keyword{
    @apply text-base md:text-xl text-gray-400 font-semibold;
}
.details {
    @apply flex justify-between  w-full;
}
.detail {
    @apply flex flex-col justify-start items-start;
}
.details__title {
    @apply text-base md:text-xl font-semibold text-gray-400 dark:text-gray-50;
}
.details__value {
 @apply text-lg md:text-2xl py-4 font-bold text-gray-800 dark:text-gray-300;
}
.action-btn {
    @apply py-4 px-6 bg-gray-800 text-xl text-white font-bold  w-full rounded-md shadow-lg my-10
     hover:bg-gray-50 hover:text-black
     dark:bg-gray-50 dark:text-gray-900 dark:hover:bg-gray-800 dark:hover:text-white
     ;

}
.ease-transition {
    @apply transition transition-all duration-150 ease-linear ;
}
</style>

<script>
export default {
    props : ["content"]
};
</script>