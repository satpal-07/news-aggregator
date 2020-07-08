<template>
  <div id="app">
    <Header/>
    <div class="logo"><img src="logo.png"/> </div>
    <Weather v-bind:weather="weather"/>
    <div class="location">Your location is {{location.city}}, {{location.country}}, {{location.zip}}</div>
    <Articles v-bind:articles="articles" />
    <PortalTarget name="popup"/>
  </div>
</template>

<script>
import Articles from "./components/articles";
import Weather from "./components/weather";
import Header from "./components/layout/header";

export default {
  name: "App",
  components: {
    Articles,
    Header,
    Weather
  },
  data() {
    return {
      articles: [],
      location:{},
      weather:'This is weather holder'
    };
  },
  methods: {
    async getArticles() {
    var url = 'http://newsapi.org/v2/everything?' +
          'q=covid&'+
          'apiKey=6d8caf72f6874900abedc74bb34001e1';
     const request = await fetch(url).catch(err => console.log(err));
    const data = await request.json().catch(err => console.log(err));
      console.log("data received", data);
      return data.articles;
    },

    async getCoronaArticles() {
    var url = 'http://newsapi.org/v2/everything?' +
          'q=corona&'+
          'apiKey=6d8caf72f6874900abedc74bb34001e1';
     const request = await fetch(url).catch(err => console.log(err));
    const data = await request.json().catch(err => console.log(err));
      console.log("data received", data);
      return data.articles;
    },

    async getUserLocation() {
      const request = await fetch(
        "http://ip-api.com/json/"
      ).catch(err => console.log(err));
      const locationData = await request.json().catch(err => console.log(err));
      console.log("Location recieved", locationData);
      return locationData;
    }
  },
  async created() {
    // method that executes at start up
    this.articles = await this.getArticles();
    this.articles.push(...await this.getCoronaArticles())
    this.location = await this.getUserLocation();
  }
};
</script>

<style>
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

body {
  font-family: Arial, Helvetica, sans-serif;
  line-height: 1.4;
  background-color: rgb(221, 213, 213);
}

.location {
  text-align: right;
  padding: 10px 0;
}
</style>
