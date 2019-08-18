<template>
  <div>
    <p>POINT: <span>{{ point }}</span></p>
    <button v-on:click="pointUp">UP</button>
    <button v-on:click="pointDown">DOWN</button>
    <button onclick="location.reload()">CONTINUE</button>

    <div class="game">

      <div class="box"
       v-on:click="answer(index)"
       v-bind:class="{win: (answered && isWinner(index)), lose: (answered && !isWinner(index))}"
       v-for="(answered, index) in answeredStatuses">
      </div>


    </div>
    <button onclick="localStorage.removeItem('point'); point=0;pointTag.textContent = point;">Reset</button>

  </div>



</template>

<script>
import Logo from '~/components/Logo.vue'

export default {
  components: {
    Logo
  },
  data () {
    return {
        point: 0,
        winner: Math.floor(Math.random() * 5),
        answeredStatuses: [false, false, false, false, false],
    }
  },
  methods: {
   isWinner (index) {
       return this.winner == index;
   },
   answer (index) {
       if (this.answeredStatuses[index]) {
         return
       }
       this.answeredStatuses[index] = true;
       if (this.isWinner(index)) {
       this.pointUp();
       } else {
       this.pointDown();
       }
       this.answeredStatuses = Array.from(this.answeredStatuses);
   },
    pointUp () {
       this.point += 5;
    },
     pointDown () {
       this.point -= 1;
    },
  },
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
    background-image: url("../assets/usagi.png");
    background-size: 100px;
    border-radius: 50%;
    transform: rotate(360deg);
  }

  .win::after {
    content: "うさぎ";
  }

  .lose {
    background-image: url("../assets/yagi.png");
    background-size: 100px;
    border-radius: 50%;
    transform: scale(0.9);
  }

  .lose::after {
    content: "やぎ";
  }
</style>
