<template>
  <div class="bg-dark h-screen">
    <div class="flex" style="height: 88vh">
      <!-- side nav -->
      <div class="w-56 bg-black h-full flex-none">
        <div class="p-6">
          <img src="./assets/img/Spotify_Logo_RGB_White.png" class="h-10" />
        </div>
        <div class="mx-2 mb-5">
          <button
            v-for="page in pages"
            @click="setID = page.id"
            :key="page.id"
            :class="`w-full text-sm font-semibold rounded px-3 py-2 flex items-center justify-start  ${
              setID === page.id ? 'bg-light text-white' : 'text-lightest'
            }`"
          >
            <i class="material-icons mr-3">{{ page.icon }}</i>
            <p>{{ page.name }}</p>
          </button>
        </div>
        <div class="mx-5">
          <h1 class="mb-3 text-xs text-lightest tracking-widest uppercase">
            Playlists
          </h1>
          <button class="flex items-center justify-start">
            <img src="./assets/img/add-new.png" class="h-8 w-8 mr-3" />
            <p class="text-sm text-white font-semibold">Create Playlist</p>
          </button>
        </div>
      </div>
      <!-- main content -->
      <div class="w-full h-full relative">
        <!-- header -->
        <div class="w-full sticky top-0 p-2"></div>
      </div>
    </div>
    <!-- play bar -->
    <div class="w-full bg-light" style="height: 12vh"></div>
  </div>
</template>

<script>
export default {
  name: "App",
  data: function () {
    return {
      pages: [
        { id: "home", name: "Home", icon: "home" },
        { id: "search", name: "Search", icon: "search" },
        { id: "library", name: "Your Library", icon: "bar_chart" },
      ],
      setID: "home",
    };
  },
  methods: {},
};
</script>

<style>
button:focus {
  outline: 0;
}
</style>