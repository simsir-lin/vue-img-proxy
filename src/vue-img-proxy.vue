<template>
<img :src="url" :title="title" :alt="title">
</template>
<script>
import notfound from './assets/image-not-found.svg';
import placeholder from './assets/image-placeholder.svg';
export default {
  props: {
    src: null,
    title: null
  },
  data() {
    return {
      url: ''
    }
  },
  created() {
    this.url = placeholder;
    if (this.src) {
      this.loadImg(this.src);
    }
  },
  methods: {
    loadImg(src) {
      var newImg = new Image();
      newImg.src = src;
      newImg.onerror = () => {
        newImg.src = notfound;
      };
      newImg.onload = () => {
        this.url = newImg.src;
        setTimeout(() => {
          this.$emit('loaded')
        }, 200);
      };
    }
  },
   watch: {
    src: function (val) {
      this.loadImg(val);
    }
  },
}
</script>
