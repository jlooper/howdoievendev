<template>
  <div class="wrapper">
    <header>Azure workshops built with 😍 by the Cloud Advocacy Team</header>

    <h1 class="headline">How Do I Even Dev?</h1>

    <img src="../assets/bit.png" width="300px">

    <div class="container">
      <div v-for="workshop in workshops" :key="workshop.text" class="card">
        <h2>{{workshop.title}}</h2>
        <h3 v-if="workshop.authors">by {{workshop.authors}}</h3>
        <p>{{workshop.blurb}}</p>
        <div class="button" v-if="workshop.blurb">Let's Go!</div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Home",
  data() {
    return {
      workshops: [
        {
          title: "GraphQL + Serverless Workshop",
          authors: "Chris Noring and Jen Looper",
          blurb:
            "Explore the GraphQL API, Learn about Dockerized Microservices, and Build a Serverless Function"
        },
        { title: "More coming soon!" }
      ]
    };
  }
};
</script>

<style scoped>
header {
  background-color: #d8315b;
  padding: 10px;
}

.container {
  padding-top: 10px;
  display: grid;
  /* Display as a Grid */
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  /* repeat = as many times as you can fit */
  /* auto-fit = fit as many items on the line as possible, go bigger if you need to */
  /*minmax = (min size, max size) = the minimum size the column should be is 200px, but if there's space then give them all 1fr of that width. */
  grid-gap: 10px;
}
.button {
  border-radius: 5px;
  color: #fffaff;
  background-color: #d8315b;
  margin: 10px;
  padding: 15px;
  width: 100px;
  margin: auto;
}
.card {
  background-color: #3e92cc;
  border-radius: 5px;
  padding: 10px;
  margin: 5px;
}
</style>

