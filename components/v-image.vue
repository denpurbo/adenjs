<template>
  <div>
    <skeleton :class="class" v-if="loading || !imageLoaded" />
    <img
      v-show="imageLoaded && !loading"
      class="xyz-in"
      xyz="fade"
      :key="src"
      :class="{ invisible: imageLoaded == false, [props.class]: true }"
      @load="imageLoaded = true"
      :src="src"
      :draggable="draggable"
    />
  </div>
</template>

<script setup lang="ts">
defineOptions({ inheritAttrs: false });
const props = defineProps(["src", "loading", "draggable", "class"]);
const imageLoaded = ref(false);
</script>
