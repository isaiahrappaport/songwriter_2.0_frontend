
<template>
  <div class="home">
    <h1>{{ message }}</h1>
    <br>
    <div v-for="song in songs">
      <h3 class="title">Title: {{song.name}}</h3>
      <h5 class="artist">By: {{song.artist}}</h5>
    </div>
  </div>
</template>

<style>
.artist {
  font-weight: 200;
}

.by {
  font-weight: 400;
}
</style>

<script>
import axios from "axios";

export default {
  data: function () {
    return {
      message: "Songwriter 2.0",
      songs: [],
    };
    x;
  },
  created: function () {
    this.indexSongs();
  },
  methods: {
    indexSongs: function () {
      axios.get("/api/songs").then((response) => {
        console.log("songs", response.data);
        this.songs = response.data;
      });
    },
  },
};
</script>

