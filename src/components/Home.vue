<template>
  <div class="wrapper">
    <header>Azure workshops built and contributed to with 😍 by the Cloud Advocacy Team</header>

    <h1 class="headline">How Do I Even Dev?</h1>

    <img src="../assets/bit.png" width="300px" />

    <div class="container">
      <div
        @click="goToWorkshop(workshop.link)"
        v-for="workshop in workshops"
        :key="workshop.text"
        class="card"
      >
        <p style="text-align:left" v-if="!workshop.ready">🚧</p>
        <h2>{{workshop.title}}</h2>
        <p>{{workshop.language}}</p>
        <h3 v-if="workshop.authors">by {{workshop.authors}}</h3>
        <p>{{workshop.blurb}}</p>
      </div>
    </div>
    <footer>
      🚧 = Not yet tested in a live venue. Testers welcome! Have a workshop to add? PR the
      <a
        href="https://github.com/jlooper/howdoievendev"
      >repo</a>
    </footer>
  </div>
</template>

<script>
export default {
  name: "Home",
  data() {
    return {
      workshops: [
        {
          title: "Step by Step Express Workshop",
          authors: "Tierney Cyren",
          blurb: "Step-by-step, learn the process of building an Express app",
          link: "https://github.com/bnb/step-by-step-express-workshop",
          ready: true,
          language: "🇺🇸"
        },
        {
          title: "Vue.js Workshops",
          authors: "Glaucia Lemos",
          blurb:
            "Series of three workshops teaching beginning, intermediate, and advanced Vue.js concepts",
          link: "https://github.com/glaucia86/vuejs-workshop",
          ready: true,
          language: "🇧🇷"
        },
        {
          title: "Not A Dog Cognitive Services Workshop",
          authors: "Frank Boucher",
          blurb:
            "Detect when an image is or is not a dog, using Cognitive Services.",
          link: "https://github.com/FBoucher/Not-a-Dog-Workshop",
          ready: true,
          language: "🇬🇧"
        },
        {
          title: "Fake Call Workshop with Azure and Twilio",
          authors: "Chloe Condon",
          blurb:
            "A workshop to build your own fake boyfriend/boss/sibling/co-worker call with Azure & Twilio ",
          link: "https://github.com/ChloeCodesThings/FakeCallWorkshop",
          ready: true,
          language: "🇺🇸"
        },
        {
          title: "MxChip IoT Workshop",
          authors: "Several authors",
          blurb: "Code your first IoT project on Azure",
          link: "https://github.com/manekinekko/MXChip-Workshop",
          ready: true,
          language: "🇫🇷"
        },
        {
          title: "Apollo GraphQL Mini Workshop",
          authors: "Brandon Minnick",
          blurb:
            "Convert an e-commerce application to GraphQL in this workshop",
          link: "https://www.codetraveler.io/apollographqlworkshop/",
          ready: true,
          language: "🇺🇸"
        },
        {
          title: "Web Apps with Visual Studio Code and Azure",
          authors: "Nina Zakharenko",
          blurb:
            "Introduction to Building Scalable Web Apps with Visual Studio Code and Azure",
          link: "https://pycon2019.azurefd.net/",
          ready: true,
          language: "🇺🇸"
        },
        {
          title: "Learn Python",
          authors: "Nina Zakharenko",
          blurb:
            "Introductory and Intermediate Python, recorded for Frontend Masters.",
          link: "https://www.learnpython.dev/",
          ready: true,
          language: "🇺🇸"
        },
        {
          title: "Azure Kubernetes Workshop",
          authors: "Several authors",
          blurb:
            "Master the basic and more advanced topics required to deploy a multi-container application to Kubernetes on Azure Kubernetes Service (AKS)",
          link: "https://aksworkshop.io/",
          ready: true,
          language: "🇺🇸"
        },
        {
          title: "Kubernetes 201 Production tooling",
          authors: "Several authors",
          blurb: "Master Kubernetes with this in-depth workshop",
          link: "https://oscon2019.container.training/",
          ready: true,
          language: "🇺🇸"
        },
        {
          title: "MXChip Workshop",
          authors: "Jim Bennett",
          blurb: "A hands-on workshop to get started with an MXChip board",
          link: "https://github.com/jimbobbennett/MXChip-Workshop",
          ready: true,
          language: "🇺🇸"
        },
        {
          title: "Attendee Detector Workshop",
          authors: "Jim Bennett",
          blurb: "A Python and Azure workshop to look for faces in photos",
          link: "https://github.com/jimbobbennett/AttendeeDetectorWorkshop",
          ready: true,
          language: "🇺🇸"
        },
        {
          title: "Xamarin Workshop",
          authors: "Jim Bennett",
          blurb: "Workshop for building an Azure powered Xamarin mobile app",
          link: "https://github.com/jimbobbennett/MobileAppsOfTomorrow-Lab",
          ready: true,
          language: "🇺🇸"
        },
        {
          title: "Kubernetes Workshop",
          authors: "Scott Coulton",
          blurb: "Workshop for learning about Kubernetes Containers",
          link: "https://github.com/scotty-c/kubernetes-on-azure-workshop",
          ready: true,
          language: "🇺🇸"
        },
        {
          title: "VS Code Can Do That Workshop",
          authors: "Burke Holland",
          blurb: "Exercises linked to a Frontend Masters workshop on VS Code",
          link: "https://burkeholland.gitbook.io/vs-code-can-do-that/",
          ready: true,
          language: "🇺🇸"
        },
        {
          title: "GraphQL + Serverless Workshop",
          authors: "Chris Noring",
          blurb:
            "Explore the GraphQL API, Learn about Dockerized Microservices, and Build a Serverless Function",
          link: "http://aka.ms/graphql-workshop",
          ready: true,
          language: "🇺🇸"
        }
      ]
    };
  },
  methods: {
    goToWorkshop(link) {
      window.open(link);
    }
  }
};
</script>

<style scoped>
header,
footer {
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

p {
  margin: 0;
}

.card {
  background-color: #3e92cc;
  border-radius: 5px;
  padding: 10px;
  margin: 5px;
  cursor: pointer;
}
</style>

