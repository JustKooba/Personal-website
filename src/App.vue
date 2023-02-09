<template>
  <header>
    <img src="./assets/pfp.jpg" class="pfp" />
    <div class="expanded-menu">
      <img src="./assets/menu.svg" class="menu" @click="handleMenu" />
      <div class="menu-content" :style="{ display: menuConDisplay }">
        <li><p class="menu-p">Home</p></li>
        <li><p class="menu-p">About Me</p></li>
        <li><p class="menu-p">Portfolio</p></li>
        <li><p class="menu-p">Skills</p></li>
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
  overflow: hidden;
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
  height: 55px;
  cursor: pointer;
}
</style>

