<template>
    <div class="nasa-apod-image"> 
        <div class="card card-primary text-center">
            <div class="card-header">
                Nasa APOD - (Astronomy Picture of the Day)
            </div>
            <div class="card-body">
                <img class="card-img" v-bind:src="apodimg.hdurl" >
                <h5 class="card-title">{{apodimg.title}}</h5>
                <p class="card-text">{{apodimg.explanation}}.</p>
                <!-- <a href="#" class="btn btn-primary">Go somewhere</a> -->
            </div>
            <div class="card-footer text-muted">
                Post Date: {{apodimg.date}}
            </div>
        </div>
    </div>
</template>

<script>
export default {
  name: "nasa-apod-image",

  props: {
    apodimg: {
      date: Date,
      explanation: String,
      hdurl: String,
      media_type: String,
      service_version: String,
      title: String,
      url: String
    }
  }
};
</script>

<style>
</style>
