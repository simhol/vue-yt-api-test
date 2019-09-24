<template>
  <li class="list-group-item media" @click="onVideoSelect">
    <img class="mr-3" :src="thumbnailurl" />
    <div class="media-body">{{ snippetTitle }}</div>
  </li>
</template>

<script>
export default {
  name: "VideoItem",
  props: ["video"],
  computed: {
    thumbnailurl() {
      return this.video.snippet.thumbnails.default.url;
    },
    snippetTitle() {
      return this.video.snippet.title;
    }
  },
  methods: {
    onVideoSelect() {
      this.$emit("videoSelect", this.video);
    }
  }
};
</script>

<style scoped>
li {
  display: flex;
  cursor: pointer;
}
li:hover {
  background-color: #eee;
}
</style>