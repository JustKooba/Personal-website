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
    <div class="pc-menu">
      <li>
        <p class="menu-p" @click="scrollToAbout">About Me</p>
      </li>
      <li>
        <p class="menu-p" @click="scrollToWork">Work</p>
      </li>
      <li>
        <p class="menu-p" @click="scrollToPortfolio">Portfolio</p>
      </li>
      <li>
        <p class="menu-p" @click="scrollToContact">Contact</p>
      </li>
    </div>
  </header>
  <main>
    <div class="rotated-email">
      <p class="email" @click="scrollToContact">justkooba@gmail.com</p>
    </div>
    <div class="container">
      <div class="text">
        <h2>Hi, my name is</h2>
        <h1>Jakub "JustKooba".</h1>
        <h2 class="websites">I build websites.</h2>
        <p>
          I'm a frontend developer who is interested in building responsive
          websites. Currently I'm working on improving my frontend skills and
          learning new things.
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
            Hello! My name is Jakub and I'm learning front-end development. I
            first started in 2021 when I decided to build a website using HTML.
            I got really interested as I progressed, so I started learning more
            and more.
          </p>
          <p class="desc">
            Fast forwarding to today - I'm currently working on improving my
            skills by building projects, for example from Frontend Mentor. My
            main focus is getting started with backend development because I
            want to become a full-stack developer someday!
          </p>
          <p class="desc">
            If you're curious, here are the things I work with:
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
            Most of my projects are from
            <a href="https://www.frontendmentor.io/challenges">FrontendMentor</a
            >, Here are some things I've build:
          </p>
          <div class="project-one">
            <a href="https://charming-snickerdoodle-41f457.netlify.app/">
              <h4>Tip Calculator App</h4>
            </a>
            <p>
              This project was build entirely using Vanilla JavaScript, As the
              name suggests - it calculates the tip based of the ammount of
              money and people you've put in.
            </p>
            <img src="./assets/image.png" />
          </div>
          <div class="project-two">
            <a href="https://celebrated-malasada-d91691.netlify.app/"
              ><h4>Advice Generator App</h4></a
            >
            <p>
              API - based project made with vanilla JavaScript. It generates a
              piece of advice each time you press the button.
            </p>
            <img src="./assets/image2.png" />
          </div>
          <div class="project-three">
            <a href="https://monumental-melba-18241f.netlify.app/"
              ><h4>Time tracker dashboard</h4></a
            >
            <p>
              Project which was also made in vanilla JavaScript. I've used a
              JSON file to store all the data for this project.
            </p>
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
      if (this.menuConDisplay === "none") {
        this.menuConDisplay = "block";
      } else if (this.menuConDisplay === "block") {
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
  text-align: center;
}

.pc-menu {
  display: none;
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
  margin-top: 150px;
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
  margin-bottom: 50px;
}

.project-one,
.project-two,
.project-three {
  background-color: #112240;
  padding: 25px;
  text-align: center;
}

.project-one:hover,
.project-two:hover,
.project-three:hover {
  transform: scale(1.05);
  transition: all 0.3s ease-in-out;
}

.project-three img,
.project-two img,
.project-one img {
  position: relative;
  left: 50%;
  right: 50%;
  transform: translateX(-50%);
}

.contact li {
  color: #ccd6f6;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}

.contact ul {
  margin-top: -30px;
  margin-bottom: 50px;
}

.contact {
  margin-bottom: -20px;
}

.footer {
  display: flex;
  justify-content: center;
  align-content: center;
  text-align: center;
  color: #ccd6f6;
  padding-bottom: 30px;
}

.rotated-email {
  display: none;
}

.footer a {
  margin-left: 5px;
}

@media (min-width: 767px) {
  .bottom-section {
    padding: 5vw;
  }

  .rotated-email {
    display: block;
    position: fixed;
    bottom: 0;
    right: 100px;
    width: 100vh;
    height: 100px;
    transform: rotate(90deg);
    transform-origin: bottom right;
    overflow-y: hidden;
  }

  .email {
    display: block;
    transform: rotate(-90deg);
    transform-origin: bottom right;
    position: absolute;
    bottom: 1%;
    right: 50px;
    writing-mode: vertical-rl;
    text-align: center;
    padding: 20px;
    cursor: pointer;
  }

  .email::before {
    content: "";
    display: block;
    width: 2px;
    height: 45px;
    background-color: #5c647a;
    position: absolute;
    bottom: -45px;
    right: 33px;
    cursor: pointer;
  }

  .email:hover {
    color: #08d698;
  }

  .email:hover::before {
    background-color: #08d698;
  }

  header {
    margin-bottom: -100px;
  }

  .container {
    padding: 5vw;
  }

  .bottom-section {
    text-align: center;
    padding: 20vw;
    font-size: 25px;
  }

  .bottom-section .green {
    font-size: 25px;
  }

  .bottom-section img {
    display: flex;
    justify-content: center;
    align-content: center;
  }
  .about-header,
  .work-header,
  .portfolio-header,
  .contact-header {
    display: flex;
    justify-content: center;
    align-content: center;
    text-align: center;
  }
  .about-header {
    margin-top: -100px;
  }
  .menu-content {
    min-width: 25vw;
  }

  .container h2 {
    font-size: 30px;
  }

  .container h1 {
    font-size: 70px;
  }

  .menu-content {
    display: flex;
  }

  .close {
    display: none;
  }

  .menu {
    display: none;
  }

  .pc-menu {
    display: flex;
  }
  .pc-menu li {
    padding: 10px;
    flex-direction: row;
  }
}

@media (min-width: 1400px) {
  .bottom-section {
    padding: 30vw;
  }

  header {
    margin-bottom: -150px;
  }

  .container {
    padding: 15vw;
  }

  .container h2 {
    font-size: 30px;
  }

  .container h1 {
    font-size: 70px;
  }

  .about-header {
    margin-top: -300px;
  }
}

@media (max-height: 700px) {
  header {
    margin-bottom: 50px;
  }
}
</style>
