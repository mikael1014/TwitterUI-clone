<template>
  <div
      class="w-1/4 h-full border-l border-gray-200 py-2 px-6 relative overflow-y-scroll hidden lg:block "
  >
    <div>
      <input
          type="text"
          class="bg-gray-200 rounded-full w-full px-10 py-2 text-gray-500"
          placeholder="Search Twitter"
      />
      <i
          class="fas fa-search absolute left-0 ml-10 mt-3 text-gray-500 text-sm text-light"
      ></i>
    </div>
    <div class="bg-gray-100 rounded-lg w-full mt-5">
      <div class="flex items-center justify-between">
        <h2 class="font-bold text-2xl p-3">France trends</h2>
        <i
            class="fas fa-cog hover:bg-blue-200 rounded-full cursor-pointer py-2 px-2 mr-2"
        ></i>
      </div>
      <div
          class="p-2 border-t border-gray-200 hover:bg-gray-200"
          v-for="trend in trending"
          :key="trend.id"
      >
        <div class="flex items center justify-between">
          <div class="flex items center text-sm text-gray-500">
            <p class="px-1">{{ trend.top }}.</p>
            <p class="px-1">Trending</p>
          </div>
          <i
              class="fas fa-angle-down hover:bg-blue-200 rounded-full cursor-pointer py-1 px-1.5 hover:text-blue-600"
          ></i>
        </div>
        <p class="px-1 font-bold ">#{{ trend.title }}</p>
        <p class="text-sm text-gray-500 px-1">
          {{ trend.tweetno }} Tweets
        </p>
      </div>
      <div class="p-2 border-t border-gray-200 hover:bg-gray-200">
        <p class="text-blue-600">Show more</p>
      </div>
    </div>

    <div class="bg-gray-100 rounded-lg w-full mt-5">
      <div class="flex items-center justify-between">
        <h2 class="font-bold text-2xl p-3">Who to follow</h2>
        <i
            class="fas fa-cog hover:bg-blue-200 rounded-full cursor-pointer py-2 px-2 mr-2"
        ></i>
      </div>
      <div
          class="p-2 border-t border-gray-200 hover:bg-gray-200"
          v-for="friend in friends"
          :key="friend.id"
      >
        <div class="flex items-center p-2 cursor-pointer w-full">
          <img
              src="@/assets/img.jpg"
              alt="profile picture"
              class="h-10 w-10 rounded-full flex-shrink-0"
          />
          <div class="ml-4 hidden lg:block">
            <p class=" text-sm font-bold leading-tight">
              Mikael
            </p>
            <p class="text-sm leading-tight">
              @nicole_mikael
            </p>
          </div>
          <button
              class="text-sm text-blue-600 border border-blue-600 rounded-full px-3 py-1.5 hover:bg-blue-100 font-semibold ml-3.5"
          >
            Follow
          </button>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "trendarea",
  props: {
    trending: Object,
    friends: Object,
  },
};
</script>

<style></style>