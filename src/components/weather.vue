<template>
  <div class="weather">
    <div id="openweathermap-widget-12" align="right"></div>
  </div>
</template>

<script>
export default {
  name: "Weather",
  props: ["weather"]
};
</script>

<script>
window.myWidgetParam ? window.myWidgetParam : (window.myWidgetParam = []);
window.myWidgetParam.push({
  id: 12,
  cityid: "2655603",
  appid: "7b519064124bc75c3fd1a43c968fe50f",
  units: "metric",
  containerid: "openweathermap-widget-12"
});
(function() {
  var script = document.createElement("script");
  script.async = true;
  script.charset = "utf-8";
  script.src =
    "//openweathermap.org/themes/openweathermap/assets/vendor/owm/js/weather-widget-generator.js";
  var s = document.getElementsByTagName("script")[0];
  s.parentNode.insertBefore(script, s);
})();
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.weather {
  align: right;
  text-align: right;
  padding: 10px 0;
}
</style>
