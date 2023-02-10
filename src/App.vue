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
          <p class="green">01.</p>

          <p class="menu-p">About Me</p>
        </li>
        <li>
          <p class="green">02.</p>

          <p class="menu-p">Work</p>
        </li>
        <li>
          <p class="green">03.</p>

          <p class="menu-p">Portfolio</p>
        </li>
        <li>
          <p class="green">04.</p>

          <p class="menu-p">Contact</p>
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
      <button class="check">Check Out My Projects!</button>

      <div class="about">
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
          <p class="desc">If you're curious, Here are things that I work with:</p>
          <ul class="tech">
            <li>HTML</li>
            <li>CSS</li>
            <li>JavaScript</li>
            <li>Vue.js</li>
          </ul>
        </div>
      </div>
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
  padding: 20px 25px;
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
  margin-bottom: 150px;
}

.pfp {
  border-radius: 50%;
  height: 55px;
}

.menu {
  height: 55px;
  cursor: pointer;
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
  display: flex;
  flex-direction: row;
  align-items: center;
  border-bottom: 1px solid #ccd6f6;
  position: relative;
  top: 300px;
}

.about-header .green {
  margin-bottom: 0;
}

.about-header .green,
h3 {
  margin-bottom: 15px;
}

.about-desc {
  position: relative;
  top: 300px;
}
</style>



