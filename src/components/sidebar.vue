<template>
  <div
      class="lg:w-1/4 border-r border-gray-200 px-2 lg:px-8 py-2 flex flex-col justify-between"
  >
    <div>
      <button
          class="h-12 w-12 text-blue-600 focus:outline-none rounded-full hover:bg-blue-200 text-3xl"
      >
        <i class="fab fa-twitter"></i>
      </button>
      <div>
        <button
            :class="
						`flex items-center py-2 px-4 focus:outline-none hover:bg-blue-200 hover:text-blue-600 rounded-full mr-auto
                        ${id === tab.id ? 'text-blue-600' : ' '}`
					"
            @click="id = tab.id"
            v-for="tab in tabs"
            :key="tab.id"
        >
          <i :class="`${tab.icon} text-2xl mr-4 text-left`"></i>
          <p class="text-lg font-semibold text-left lg:block hidden">
            {{ tab.title }}
          </p>
        </button>
      </div>
      <button
          class="bg-blue-600 focus:outline-none mt-5 p-3 w-12 h-12 lg:h-auto lg:w-full text-white rounded-full font-semibold hover:bg-blue-600"
      >
        <p class="hidden lg:block">Tweet</p>
        <i class="fas fa-plus block lg:hidden"></i>
      </button>
    </div>
    <div class="lg:w-full relative">
      <div
          class="flex items-center hover:bg-blue-200 rounded-full p-2 cursor-pointer lg:w-full focus:outline-none"
          @click="droptoggle"
      >
        <img
            src="@/assets/img.jpg"
            alt="profile picture"
            class="h-10 w-10 rounded-full flex-shrink-0"
        />
        <div class="ml-4 hidden lg:block">
          <p class=" text-sm font-bold leading-tight">Mikael</p>
          <p class="text-sm leading-tight">@nicole_mikael</p>
        </div>
        <i
            class="fas fa-angle-down ml-auto text-lg px-2 hidden lg:block"
        ></i>
      </div>
      <div
          class="absolute bottom-16 left-0 w-64 rounded-lg bg-white shadow-md"
          v-if="dropdown === true"
      >
        <div class="flex items-center p-2 w-full ">
          <img
              src="@/assets/img.jpg"
              alt="profile picture"
              class="h-10 w-10 rounded-full flex-shrink-0"
          />
          <div class="ml-4 ">
            <p class=" text-sm font-bold leading-tight">
              Mikael
            </p>
            <p class="text-sm leading-tight">
              @nicole_mikael
            </p>
          </div>
          <i class="fas fa-check ml-auto text-blue-600 px-2"></i>
        </div>
        <div
            class="border-t border-gray-200 hover:bg-gray-100 cursor-pointer"
            @click="dropdown = false"
        >
          <p class="p-3">Add an existing account</p>
        </div>
        <div
            class="border-t border-gray-200 hover:bg-gray-100 cursor-pointer"
            @click="dropdown = false"
        >
          <p class="p-3">Logout @nicole_mikael</p>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "sidebar",
  data() {
    return {
      id: "home",
      dropdown: false,
    };
  },
  props: {
    tabs: Object,
  },
  methods: {
    droptoggle() {
      this.dropdown = !this.dropdown;
    },
  },
};
</script>

<style></style>