<template>
  <ul class="list-group col-md-4">
    <VideoItem
      v-for="video in videos"
      :key="video.etag"
      :video="video"
      @videoSelect="onVideoSelect"
    ></VideoItem>
  </ul>
</template>

<script>
import VideoItem from "./VideoItem";

export default {
  name: "VideoList",
  components: {
    VideoItem
  },
  props: {
    videos: Array
  },
  methods: {
    onVideoSelect(video) {
      this.$emit("videoSelect", video);
    }
  }
};
</script>

<style scoped>
</style>