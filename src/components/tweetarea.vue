<template>
  <div class="lg:w-2/4 h-full w-full">
    <div
        class="flex items-center justify-between border-b border-gray-200 px-5 py-3"
    >
      <h1 class="font-bold text-xl">Home</h1>
      <i
          class="far fa-star text-xl text-blue-600 hover:bg-blue-100 rounded-full cursor pointer  px-1.5 py-1"
      ></i>
    </div>
    <div class="flex px-5 py-3 border-b border-gray-200">
      <div class="flex-none">
        <img
            src="@/assets/img.jpg"
            class="w-12 h-12 rounded-full flex-none"
            alt=""
        />
      </div>
      <form class="w-full px-4 relative" @submit.prevent="addTweet">
				<textarea
            placeholder="What's up?"
            v-model="tweet.content"
            class="w-full "
        ></textarea>
        <div class="flex items-center justify-between">
          <div class="flex items-center">
            <i class="text-lg text-blue-600 mr-4 far fa-image"></i>
            <i class="text-lg text-blue-600 mr-4 fas fa-film"></i>
            <i
                class="text-lg text-blue-600 mr-4 far fa-chart-bar"
            ></i>
            <i class="text-lg text-blue-600 mr-4 far fa-smile"></i>
          </div>
          <button
              class="bg-blue-600 rounded-full py-2 px-3 font-semibold text-white focus:outline-none"
              type="submit"
          >
            Tweet
          </button>
        </div>
      </form>
    </div>
    <div
        class="w-full border-b border-gray-200 flex px-5 py-3 cursor-pointer hover:bg-gray-100"
        v-for="tweet in tweets"
        :key="tweet.id"
    >
      <img
          src="@/assets/img.jpg"
          class="w-12 h-12 rounded-full flex-none"
      />
      <div class="ml-3 w-full">
        <div class="flex items-center">
          <p class="font-bold">Mikael</p>
          <p class="text-sm ml-2 text-gray-500">
            @nicole_mikael.
          </p>
          <p class="text-sm ml-2 text-gray-500">
            1 sec
          </p>
          <i class="fas fa-angle-down text-gray-500 ml-auto"></i>
        </div>
        <div id="tweet" class="py-1">
          <p>{{ tweet.content }}</p>
        </div>
        <div class="flex justify-between items-center">
          <div class="flex items-center text-sm text-dark">
            <i class="far fa-comment mr-3"></i>
            <p>0</p>
          </div>
          <div class="flex items-center text-sm text-dark">
            <i class="fas fa-retweet mr-3"></i>
            <p>0</p>
          </div>
          <div class="flex items-center text-sm text-dark">
            <i class="fas fa-heart mr-3 text-pink-600"></i>
            <p>1</p>
          </div>
          <div class="flex items-center text-sm text-dark">
            <i class="fas fa-share-square mr-3"></i>
          </div>
        </div>
      </div>
    </div>
    <div
        class="w-full border-b border-gray-200 flex px-5 py-3 cursor-pointer hover:bg-gray-100"
        v-for="follow in following"
        :key="follow.id"
    >
      <img
          src="@/assets/img.jpg"
          class="w-12 h-12 rounded-full flex-none"
      />
      <div class="ml-3 w-full">
        <div class="flex items-center">
          <p class="font-bold">{{ follow.name }}</p>
          <p class="text-sm ml-2 text-gray-500">
            {{ follow.handle }}.
          </p>
          <p class="text-sm ml-2 text-gray-500">
            {{ follow.time }}
          </p>
          <i class="fas fa-angle-down text-gray-500 ml-auto"></i>
        </div>
        <div id="tweet" class="py-1">
          <p>{{ follow.tweet }}</p>
        </div>
        <div class="flex justify-between items-center">
          <div class="flex items-center text-sm text-dark">
            <i class="far fa-comment mr-3"></i>
            <p>{{ follow.comments }}</p>
          </div>
          <div class="flex items-center text-sm text-dark">
            <i class="fas fa-retweet mr-3"></i>
            <p>{{ follow.retweets }}</p>
          </div>
          <div class="flex items-center text-sm text-dark">
            <i class="fas fa-heart mr-3"></i>
            <p>{{ follow.like }}</p>
          </div>
          <div class="flex items-center text-sm text-dark">
            <i class="fas fa-share-square mr-3"></i>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "tweetarea",
  data() {
    return {
      tweets: [{ content: "This is actually going to be a test..." }],

      tweet: {
        content: "",
      },
    };
  },
  props: {
    following: Object,
  },
  methods: {
    addTweet() {
      let newtweet = {
        content: this.tweet.content,
      };
      this.tweets.unshift(newtweet);

      this.tweet.content = "";
    },
  },
};
</script>

<style></style>