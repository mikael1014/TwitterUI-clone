<template>
  <div id="app" class="flex w-full h-screen ">
    <!-- Side nav bar -->
    <sidebar :tabs="tabs" />
    <!-- Main area -->
    <tweetarea :following="following" />
    <!-- Trends area -->
    <trendarea :trending="trending" :friends="friends" />
  </div>
</template>

<script>
import sidebar from "./components/sidebar.vue";
import tweetarea from "./components/tweetarea.vue";
import trendarea from "./components/trendarea.vue";
export default {
  name: "App",
  components: {
    sidebar,
    tweetarea,
    trendarea,
  },
  data() {
    return {
      tabs: [
        { icon: "fas fa-home", title: "Home", id: "home" },
        { icon: "fas fa-hashtag", title: "Explore", id: "explore" },
        {
          icon: "far fa-bell",
          title: "Notifications",
          id: "notifications",
        },
        { icon: "far fa-envelope", title: "Messages", id: "messages" },
        {
          icon: "far fa-bookmark",
          title: "Bookmarks",
          id: "bookmarks",
        },
        { icon: "fas fa-clipboard-list", title: "Lists", id: "lists" },
        { icon: "far fa-user", title: "Profile", id: "profile" },
        { icon: "fas fa-ellipsis-h", title: "More", id: "more" },
      ],

      trending: [
        {
          top: "Trending in TX",
          title: "Gigi",
          tweetno: "120k",
        },
        { top: "Music", title: "WeWon", tweetno: "135K" },
        { top: "Pop", title: "BlueIvy", tweetno: "40k" },
        {
          top: "Trending in US",
          title: "DenimDay",
          tweetno: "40k",
        },
      ],
      friends: [
        {
          src: "@/assets/img.jpg",
          name: "Elon Musk",
          handle: "@teslaBoy",
        },
        {
          src: "@/assets/img.jpg",
          name: "Adrian Monk",
          handle: "@detective:)",
        },
        {
          src: "@/assets/img.jpg",
          name: "Kevin Hart",
          handle: "@miniRock",
        },
      ],
      following: [
        {
          src: "img.jpg",
          name: "Elon Musk",
          handle: "@teslaBoy",
          time: "20 min",
          tweet: "Should I just quarantine on mars??",
          comments: "1,000",
          retweets: "550",
          like: "3,000",
        },
        {
          src: "img.jpg",
          name: "Kevin Hart",
          handle: "@miniRock",
          time: "55 min",
          tweet:
              "Should me and the rock do another sub-par movie together????",
          comments: "2,030",
          retweets: "50",
          like: "203",
        },
        {
          src: "img.jpg",
          name: "Elon Musk",
          handle: "@teslaBoy",
          time: "1.4 hr",
          tweet: "Haha just made a flame thrower. Shld I sell them?",
          comments: "107",
          retweets: "1,030",
          like: "5,001",
        },
        {
          src: "img.jpg",
          name: "Elon Musk",
          handle: "@teslaBoy",
          time: "1.4 hr",
          tweet: "Just did something crazyyyyyyy",
          comments: "100",
          retweets: "1,000",
          like: "5,000",
        },
      ],
    };
  },
};
</script>