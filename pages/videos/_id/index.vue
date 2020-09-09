<template>
  <div>
    We are in a video {{ video.name}}
    <nuxt-link :to="`/videos/${video.id}/edit`">
      <button>Edit</button>
    </nuxt-link>
    <nuxt-link :to="`/videos`">
      <button>Go Back</button>
    </nuxt-link>
  </div>
</template>

<script>
export default {
  props: ["video"],
};
</script>

<style>
</style>