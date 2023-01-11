<template>
  <div class="main">
    <aside>
      <a href="#">LOGO</a>
      <a href="#">About</a>
      <a href="#"></a>
    </aside>
    <main>
      <!-- <nav>
        <ul>
          <li class="liOne"></li>
          <li class="liTwo"></li>
          <li class="liThree"></li>
        </ul>
      </nav> -->

      <NuxtLink to="/cart" class="title" style="cursor: pointer" @click="change()">
        <h1>X</h1>
        <div class="title-wrapper">
          <span>U</span>
          <span>M</span>
          <span>G</span>
        </div>
      </NuxtLink>
      <NuxtLink to="/cart" class="view">
          <div class="circle">
            <div class="arrow"></div>
          </div>
          <a>View Project</a>
       
      </NuxtLink>
    </main>
    <div class="contacts">
      <a class="contacts-text">Contacts</a>
     
    </div>
  </div>
</template>

<script>
import "../assets/styles/sidebar.scss";
import "../assets/styles/contacts.scss";

export default {
  name: "Index",
  // mounted() {
  //   this.boxRotation();
  // },

  methods: {
    boxRotation() {
      let tl = this.$gsap.timeline();
      tl.fromTo(
        "span",
        { opacity: 0, y: -350, x: -100 },
        { opacity: 1, y: 0, x: 0, duration: 1, rotation: "360" }
      )
        .fromTo(
          "h1",
          { opacity: 0, y: 350, x: 100 },
          { opacity: 1, y: 0, x: 0, duration: 1 }
        )
        .fromTo(
          "li",
          { opacity: 0, scale: 0 },
          { opacity: 1, scale: 1, duration: 1 }
        )
        .fromTo("a", { opacity: 0, y: -100 }, { opacity: 1, y: 0, duration: 1 })
        .fromTo(
          ".liOne",
          { opacity: 0 },
          { opacity: 1, scaleX: 2, backgroundColor: "#FFFFFF", duration: 1 }
        );
    },
    change() {
      let tl = this.$gsap.timeline();
      tl.fromTo(
        ".title-wrapper",
        { opacity: 1, x: 0 },
        { opacity: 0, duration: 1, x: -50 }
      ).fromTo(
        ".title-wrapper",
        { x: -50, opacity: 0 },
        { opacity: 1, duration: 1, x: 0 }
      );
    }
  }
};
</script>

<style  lang="scss" scoped >
@import '../assets/styles/index.scss';
</style>
