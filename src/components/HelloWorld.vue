<template>
  <div class="app-container">
    <button @click="start">Start</button>
    <div>
      <img
        @click="onSelectImg(item)"
        style="
          width: 300px;
          height: 300px;
          object-fit: cover;
          margin-right: 20px;
        "
        v-for="item in imgListAll"
        :key="item"
        :src="item"
        alt=""
      />
    </div>
    <div id="lightgallery">
    </div>
  </div>
</template>

<script>
import lightGallery from "lightgallery";
// Plugins
import lgThumbnail from "lightgallery/plugins/thumbnail";
import lgZoom from "lightgallery/plugins/zoom";
export default {
  name: "HelloWorld",
  data() {
    return {
      showGlary: false,
      imgListAll: [
        "https://phongvu.vn/cong-nghe/wp-content/uploads/sites/2/2018/07/hinh-nen-full-hd-cho-laptop-1.jpg",
        "https://img.freepik.com/premium-photo/closeup-nature-view-colorful-leaves_860528-2622.jpg",
        "https://images.unsplash.com/photo-1418065460487-3e41a6c84dc5?ixid=MXwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHw%3D&ixlib=rb-1.2.1&auto=format&fit=crop&w=1600&q=80",
      ],
      imgListSelect: [],
    };
  },

  mounted() {
    // this.start()
  },

  methods: {
    onSelectImg(img) {
      console.log("img", img);
      this.imgListSelect.push(img);
    },

    start() {
      this.showGlary = true;
      let dynamicElements = [];
      this.imgListSelect.forEach((value) => {
        dynamicElements.push({
          src: value,
          thumb: value,
        });
      });

      const lg = document.getElementById("lightgallery");
      window.lightGallery(lg, {
        mode: "lg-slide",
        download: false,
        thumbnail: true,
        dynamic: true,
        dynamicEl: dynamicElements,
        autoplayFirstVideo: true,
        loadVimeoThumbnail: false,
      });

      window.lightGallery(lg);
    },
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1,
h2 {
  font-weight: normal;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
