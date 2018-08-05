<template>
    <div class="nasa-apod"> 
        <h2>Nasa Apod </h2>
        <hr>
        <nasa-apod-render :apodimg='apod_image'/>

    </div>  
</template>

<script>
import NasaApodRender from "@/components/NasaApodRender.vue";

export default {
  name: "nasa-apod",
  components: {
    NasaApodRender
  },

  data() {
    return {
      apod_image: {}
    };
  },

  mounted() {
    this.getNasaApod();
  },

  methods: {
    getNasaApod() {
      fetch(
        `https://api.nasa.gov/planetary/apod?api_key=9eNKqZJSuom8cMIKlWJGrZrDrdxYNPfcvK7Js8yU`
      ).then(res =>
        res.json().then(data => {
          this.apod_image = data;
        })
      );
    }
  }
};
</script>

<style>
</style>
