<template>
  <div>
    <NavBar :vectorLetters="vectorLetters" :siteLinks="siteLinks"/>
    <Work />
    <Clients />
    <QuestionsForm />
    <Footer :vectorLetters="vectorLetters" :siteLinks="siteLinks"/>
    <ToTopArrow />
  </div>
</template>

<script>
import NavBar from "./views/NavBar.vue"
import Work from "./views/Work.vue"
import Clients from "./components/Clients.vue"
import QuestionsForm from "./components/QuestionsForm.vue"
import Footer from "./components/Footer.vue"
import ToTopArrow from "./components/ToTopArrow.vue"

export default {
  name: 'App',
  components: {
    NavBar,
    Work,
    Clients,
    QuestionsForm,
    Footer,
    ToTopArrow,
  },
  data() {
    return {
      vectorLetters: ["1", "2", "3", "4", "5"],
      siteLinks: [
        {
            title: "WORK",
            link: null,
            isActive: true,
        },
        {
            title: "CULTURE",
            link: null,
        },
        {
            title: "SERVICE",
            link: null,
        },
        {
            title: "INSIGHTS",
            link: null,
        },
        {
            title: "CAREERS",
            link: null,
        },
        {
            title: "CONTACT",
            link: null,
        }
        ]
    }
  }
}
</script>

<style>
  @font-face {
    font-family: "maisonNeue";
    src: url("./assets/fonts/maisonNeue.woff2") format('woff2');
  }

  html,body {
    padding:0;
    margin:0;
    overflow-x:hidden;
    font-family:maisonNeue;
  }

  a {
        text-decoration:none;
        color:white;
  }
</style>
