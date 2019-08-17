<template>
  <div class="container">
    <div>
      <logo />
      <h1 class="title">
        Rabbit-game
      </h1>
      <div class="links">
        <a
          href="https://nuxtjs.org/"
          target="_blank"
          class="button--green"
        >
          Documentation
        </a>
        <a
          href="https://github.com/nuxt/nuxt.js"
          target="_blank"
          class="button--grey"
        >
          GitHub
        </a>
      </div>
    </div>
  </div>
</template>

<script>
import Logo from '~/components/Logo.vue'

export default {
  components: {
    Logo
  }
}
</script>

<style>
 body {
        display: flex;
      }
      p {
      text-align: center;
      }
      .game {
        left: 0px;
        margin: auto;
      }
      .box {
        width: 100px;
        height: 100px;
        background: skyblue;
        cursor: pointer;
        transition: 0.8s;
        margin: 0 8px 8px 0;
        text-align: center;
        line-height: 100px;
      }
      .win {
        background-image: url("./img/usagi.png");
        background-size: 100px;
        border-radius: 50%;
        transform: rotate(360deg);
      }
      .lose {
        background-image: url("./img/yagi.png");
        background-size: 100px;
        border-radius: 50%;
        transform: scale(0.9);
      }
      </style>
