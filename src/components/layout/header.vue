<template>
  <div class="nav-bar">
      <ul>
          <li>Home</li>
          <li>Contact Us</li>
          <li>About</li>
      </ul>
  </div>
</template>

<script>
export default {
  name: 'Header'
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.nav-bar ul {
    list-style-type: none;
    margin: 0;
    padding: 0;
    overflow: hidden;
    background-color: #333;
    position: fixed;
    top: 0;
    width: 100%;
}
.nav-bar ul li {
    float: left;
    display: block;
    color: white;
    text-align: center;
    padding: 14px 16px;
    text-decoration: none;
}
.nav-bar ul li:last-child {
    float: right;
}
li:hover {
  background-color: #111;
}

@media (max-width: 600px) {
    .nav-bar ul li:last-child,
    .nav-bar ul li {
        float: none;
    }
}
</style>
