<template>
  <div>
    <nuxt-child :video="video" />
  </div>
</template>

<script>
import { mapState } from "vuex";
export default {
  head() {
    return { title: `${this.video.name}` };
  },
  async fetch({ $axios, params, store }) {
    let response = await $axios.get(`/videos/${params.id}`);
    let video = response.data.data.attributes;
    store.commit("SET_CURRENT_VIDEO", video);
  },
  computed: {
    ...mapState({
      video: "currentVideo",
    }),
  },
};
</script>

<style lang="scss" scoped>
</style> 