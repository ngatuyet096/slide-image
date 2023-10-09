<template>
  <div class="app-container">
    <div id="lightgallery">
      <a
        data-lg-size="1600-1067"
        data-src="https://phongvu.vn/cong-nghe/wp-content/uploads/sites/2/2018/07/hinh-nen-full-hd-cho-laptop-1.jpg"
      >
        <img
          style="width: 300px; height: 300px; object-fit: cover;"
          src="https://phongvu.vn/cong-nghe/wp-content/uploads/sites/2/2018/07/hinh-nen-full-hd-cho-laptop-1.jpg"
        />
      </a>

      <a
        data-lg-size="1600-1067"
        data-src="https://img.freepik.com/premium-photo/closeup-nature-view-colorful-leaves_860528-2622.jpg"
      >
        <img
          style="width: 300px; height: 300px; object-fit: cover;"
          src="https://img.freepik.com/premium-photo/closeup-nature-view-colorful-leaves_860528-2622.jpg"
        />
      </a>

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
      msg: "Welcome to Your Vue.js App",
    };
  },

  mounted() {
    const el = document.getElementById('lightgallery')
    window.lightGallery(el, {
        mode: 'lg-slide',
        speed: 500,
        autoplayFirstVideo: false,
        pager: false,
        galleryId: "nature",
        autoplayFirstVideo: true,
        plugins: [lgZoom, lgThumbnail],
        enableSwipe: true, // required
        showMaximizeIcon: true, // required
        mobileSettings: {
          controls: false,
          showCloseIcon: false,
          download: false,
          rotate: false
        }
      })
  }
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
