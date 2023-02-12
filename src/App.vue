<template>
  <header>
    <img src="./assets/pfp.jpg" class="pfp" />
    <div class="expanded-menu">
      <img src="./assets/menu.svg" class="menu" @click="handleMenu" />
      <div class="menu-content" :style="{ display: menuConDisplay }">
        <img
          src="./assets/menu-close.svg"
          @click="handleMenu"
          class="menu close"
        />
        <li>
          <p class="green">01</p>

          <p class="menu-p" @click="scrollToAbout">About Me</p>
        </li>
        <li>
          <p class="green">02</p>

          <p class="menu-p" @click="scrollToWork">Work</p>
        </li>
        <li>
          <p class="green">03</p>

          <p class="menu-p" @click="scrollToPortfolio">Portfolio</p>
        </li>
        <li>
          <p class="green">04</p>

          <p class="menu-p" @click="scrollToContact">Contact</p>
        </li>
      </div>
    </div>
  </header>
  <main>
    <div class="container">
      <div class="text">
        <h2>Hi, my name is</h2>
        <h1>Jakub "JustKooba".</h1>
        <h2 class="websites">I build websites.</h2>
        <p>
          I'm a frontend developer who is good in building responsive websites.
          Currently I'm working on improving my frontend skills and learning new
          things.
        </p>
      </div>
      <a href="https://github.com/JustKooba?tab=repositories">
        <button class="check">Check Out My Projects!</button></a
      >
    </div>
    <div class="bottom-section">
      <div class="about" ref="about">
        <div class="about-header">
          <p class="green">01.</p>
          <h3>About Me</h3>
        </div>
        <div class="about-desc">
          <p class="desc">
            Hello! My name is Jakub and I'm Learning Front-end development. i
            first started in 2021 When i decided to build a website using Html.
            I got really interested as i got further so i started learning more
            and more.
          </p>
          <p class="desc">
            Fast forwarding to this day - I'm currently working on improving my
            skills, by building projects for example from FronetndMentor My Main
            focus is getting started with backend, I want to be a Full-stack
            developer someday!
          </p>
          <p class="desc">
            If you're curious, Here are things that I work with:
          </p>
          <ul class="tech">
            <li>HTML</li>
            <li>CSS</li>
            <li>JavaScript</li>
            <li>Vue.js</li>
          </ul>
        </div>
      </div>
      <div class="work" ref="work">
        <div class="work-header">
          <p class="green">02.</p>
          <h3>Work</h3>
        </div>
        <div class="work-desc">
          <p class="desc">Currently Unemployed, this page will be updated!</p>
        </div>
      </div>
      <div class="portfolio" ref="portfolio">
        <div class="portfolio-header">
          <p class="green">03.</p>
          <h3>portfolio</h3>
        </div>
        <div class="portfolio-desc">
          <p class="desc">
            most of my projects are from
            <a href="https://www.frontendmentor.io/challenges">FronetndMentor</a
            >, Here are some things I've build:
          </p>
          <div class="project-one">
            <a href="https://charming-snickerdoodle-41f457.netlify.app/">
              <h4>Tip Calculator App</h4>
            </a>
            <img src="./assets/image.png" />
          </div>
          <div class="project-two">
            <a href="https://celebrated-malasada-d91691.netlify.app/"
              ><h4>Advice Generator App</h4></a
            >
            <img src="./assets/image2.png" />
          </div>
          <div class="project-three">
            <a href="https://monumental-melba-18241f.netlify.app/"
              ><h4>Time tracker dashboard</h4></a
            >
            <img src="./assets/image3.png" />
          </div>
        </div>
      </div>
      <div class="contact" ref="contact">
        <div class="contact-header">
          <p class="green">04.</p>
          <h3>Contact</h3>
        </div>
        <p class="desc">
          Want to get in touch? Just message me on one of those platforms:
        </p>
        <ul class="contact-ul">
          <li>Discord: JustKooba#2707</li>
          <li>GMail: justkooba@gmail.com</li>
        </ul>
      </div>
    </div>
    <div class="footer">
      Built by justkooba, inspired by
      <a href="https://brittanychiang.com/#contact"> Brittany Chiang</a>
    </div>
  </main>
</template>

<script>
export default {
  data() {
    return {
      menuConDisplay: "none",
    };
  },
  methods: {
    handleMenu() {
      if (this.menuConDisplay == "none") {
        this.menuConDisplay = "block";
      } else if (this.menuConDisplay == "block") {
        this.menuConDisplay = "none";
      }
    },
    scrollToAbout() {
      const about = this.$refs.about;
      this.menuConDisplay = "none";
      window.scrollTo({
        top: about.offsetTop,
        behavior: "smooth",
      });
    },

    closeMenuOnScroll() {
      if (window.scrollY > 0) {
        this.menuConDisplay = "none";
      }
    },
    scrollToWork() {
      const work = this.$refs.work;
      this.menuConDisplay = "none";
      window.scrollTo({
        top: work.offsetTop,
        behavior: "smooth",
      });
    },
    scrollToPortfolio() {
      const portfolio = this.$refs.portfolio;
      this.menuConDisplay = "none";
      window.scrollTo({
        top: portfolio.offsetTop,
        behavior: "smooth",
      });
    },
    scrollToContact() {
      const contact = this.$refs.contact;
      this.menuConDisplay = "none";
      window.scrollTo({
        top: contact.offsetTop,
        behavior: "smooth",
      });
    },
  },
  mounted() {
    window.addEventListener("scroll", this.closeMenuOnScroll);
  },
  beforeUnmount() {
    window.removeEventListener("scroll", this.closeMenuOnScroll);
  },
};
</script>

<style>
@import url("https://fonts.googleapis.com/css2?family=Roboto+Mono:wght@300&family=Roboto:wght@700&display=swap");

@import url("https://fonts.googleapis.com/css2?family=Roboto+Mono:wght@100;200&family=Roboto:wght@700&display=swap");

* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body {
  font-family: "Roboto", sans-serif;
  background-color: #0a192f;
  height: 100vh;
}
.container {
  height: 100vh;
  padding: 30px;
  display: flex;
  flex-direction: column;
  justify-content: center;
}

.bottom-section {
  padding: 30px;
}

h2 {
  font-family: "Roboto Mono", sans-serif;
  color: #08d698;
  margin-bottom: 25px;
}

h3 {
  color: #ccd6f6;
}

.websites {
  color: #8892b0;
  font-family: "Roboto", sans-serif;
  font-size: 55px;
  margin-bottom: 20px;
}

.check {
  border: #08d698 2px solid;
  padding: 20px 55px;
  background-color: transparent;
  color: #08d698;
  margin-top: 30px;
  font-size: 17px;
  max-width: 350px;
  border-radius: 10px;
  font-family: "Roboto Mono", sans-serif;
  font-weight: 300;
  cursor: pointer;
  transition: ease-in-out 0.3s;
}

.check:hover {
  opacity: 0.5;
}

li {
  list-style: none;
}

h1 {
  color: #ccd6f6;
  font-size: 46px;
}

p {
  color: #5c647a;
  line-height: 26px;
  font-size: 18px;
  margin-bottom: 60px;
}

img {
  max-width: 100%;
}

header {
  display: flex;
  justify-content: space-between;
  padding: 15px 30px;
}

.pfp {
  border-radius: 50%;
  height: 55px;
}

.menu {
  height: 45px;
  cursor: pointer;
}

a {
  color: #08d698;
  text-decoration: none;
}

.expanded-menu {
  position: relative;
  display: inline-block;
}

.menu-content {
  display: none;
  position: absolute;
  background-color: #112240;
  min-width: 65vw;
  min-height: 100vh;
  left: 153%;
  transform: translateX(-100%);
  top: -15px;
  z-index: 1;
}

.menu-content li {
  display: flex;
  align-items: center;
  justify-content: center;
  flex-direction: column;
}

.green {
  color: #08d698;
  font-family: "Roboto Mono", sans-serif;
  margin-bottom: 5px;
}

.close {
  position: relative;
  left: 77%;
  top: 10px;
}

.menu-p {
  color: #ccd6f6;
  cursor: pointer;
}

.menu-p:hover {
  color: #08d698;
  transition: ease-in-out 0.3s;
}

.about-header {
  margin-top: 500px;
}

.about-header,
.work-header,
.portfolio-header,
.contact-header {
  display: flex;
  flex-direction: row;
  align-items: center;
  border-bottom: 1px solid #ccd6f6;
  margin-bottom: 20px;
}

.about-header .green,
.work-header,
.contact-header .green {
  margin-bottom: 0;
}

.about-header .green,
.work-header .green,
.portfolio-header .green,
.contact-header .green h3 {
  margin-bottom: 5px;
}

.work-desc {
  margin-top: 20px;
}

h4 {
  color: #ccd6f6;
  text-align: center;
  margin-bottom: 20px;
}

h4:hover {
  color: #08d698;
}

.tech {
  display: flex;
  flex-wrap: wrap;
  justify-content: space-between;
  text-align: center;
  color: #ccd6f6;
  margin-top: -30px;
  margin-bottom: 30px;
}

.tech li {
  width: calc(50% - 10px);
  margin-bottom: 10px;
}

.tech li::before {
  content: "";
  border-color: transparent #08d698;
  border-style: solid;
  border-width: 0.35em 0 0.35em 0.45em;
  display: block;
  height: 0;
  width: 0;
  top: 0.9em;
  position: relative;
}

.work-header {
  display: flex;
}

.portfolio-header {
  display: flex;
}

.project-two {
  margin-top: 30px;
}

.project-three {
  margin-top: 30px;
}

.contact li {
  color: #ccd6f6;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}

.footer {
  display: flex;
  justify-content: center;
  align-content: center;
  text-align: center;
  color: #ccd6f6;
}

.footer a {
  margin-left: 5px;
}
</style>

