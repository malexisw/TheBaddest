<template>
  <div class="home">
    <Header v-if="!isPlayed" />

    <section :class="container">
      <div class="player">
        <div :class="video">
          <!-- Play Button -->
          <div
            class="btn btn-play abs index3"
            @click="onPlay()"
            v-show="!isPlayed"
          >
            <div class="play-logo"></div>
          </div>

          <!-- Content  -->
          <Intro v-if="intro" />
          <Refrain v-if="refrain" />
          <FirstRap v-if="firstRap" />
          <Transition v-if="transition" />

          <div class="logoBlack abs d-flex" v-if="logoB">
            <img src="../assets/black/logo1.png" alt="logo1" v-if="l1" />
            <img src="../assets/black/logo2.png" alt="logo1" v-if="l2" />
            <img src="../assets/black/logo3.png" alt="logo1" v-if="l3" />
            <img src="../assets/black/logo4.png" alt="logo1" v-if="l4" />
          </div>

          <SecondRap v-if="secondRap" />
          <End v-if="end" />

          <!-- Stop Button -->
          <div
            class="btn btn-stop abs index3"
            @click="onPlay()"
            v-show="isPlayed"
          >
            <div class="stop-logo"></div>
          </div>

          <!-- Volume Slider -->
          <div id="container-volume" class="index3">
            <i class="fas fa-volume-up"></i>
            <input type="range" id="volume" name="volume" min="0" max="100" />
          </div>
        </div>
        <h2 class="title">
          K/DA - THE BADDEST ft. (G)I-DLE, Bea Miller, Wolftyla - Version
          HTML/CSS | League of Legends
        </h2>
      </div>

      <div class="explain" v-if="!isPlayed">
        <h2>Context</h2>
        <hr />
        <h3>
          Après avoir regardé une lyric video faite par Riot Games, je me suis
          demandé si je pouvais la reproduire en HTML/CSS et malgré le manque
          d'assets voici le résultat. <br /><br />
          Vous pouvez trouver la vidéo originale ici pour faire une comparaison
          :
          <a href="https://www.youtube.com/watch?v=RkID8_gnTxw" target="_blank"  class="link"
            >THE BADDEST - ORIGINAL VIDEO</a
          >
        </h3>
      </div>
    </section>

    <audio id="myAudio">
      <source src="../assets/audio/music.ogg" type="audio/ogg" />
      <source src="../assets/audio/music.mp3" type="audio/mpeg" />
      Your browser does not support the audio element.
    </audio>
  </div>
</template>

<script>
import Header from "../components/Header.vue";
import Intro from "./Intro.vue";
import Refrain from "./Refrain.vue";
import FirstRap from "./FirstRap.vue";
import Transition from "./Transition.vue";
import SecondRap from "./SecondRap.vue";
import End from "./End.vue";

export default {
  name: "Home",
  components: {
    Header,
    Intro,
    Refrain,
    FirstRap,
    Transition,
    SecondRap,
    End,
  },
  data: () => ({
    audio: null,
    volume: null,
    isPlayed: false,

    intro: false,
    refrain: false,
    firstRap: false,
    transition: false,
    logoB: false,
    l1: false,
    l2: false,
    l3: false,
    l4: false,
    secondRap: false,
    end: false,
  }),
  computed: {
    video() {
      if (!this.isPlayed) {
        return "video pause";
      } else {
        return "video play";
      }
    },
    container() {
      if (!this.isPlayed) {
        return "container paused";
      } else {
        return "container played";
      }
    },
  },
  mounted() {
    this.audio = document.getElementById("myAudio");
    this.volume = document.getElementById("volume");

    this.volume.addEventListener("mousemove", this.setVolume);
  },
  methods: {
    onPlay() {
      this.isPlayed = !this.isPlayed;

      if (this.isPlayed) {
        this.startVideo();
        this.startAudio();
      } else {
        this.stopVideo();
        this.stopAudio();
      }
    },
    startVideo() {
      this.intro = true;

      setTimeout(() => (this.intro = false), 13000);

      setTimeout(() => (this.refrain = true), 12800);
      setTimeout(() => (this.refrain = false), 38000);

      setTimeout(() => (this.firstRap = true), 38500);
      setTimeout(() => (this.firstRap = false), 77200);

      setTimeout(() => (this.transition = true), 77200);
      setTimeout(() => (this.transition = false), 89350);

      setTimeout(() => (this.refrain = true), 89350);
      setTimeout(() => (this.refrain = false), 115050);

      setTimeout(() => (this.logoB = true), 115100);
      setTimeout(() => (this.l1 = true), 115050);
      setTimeout(() => (this.l1 = false), 115210);
      setTimeout(() => (this.l2 = true), 115210);
      setTimeout(() => (this.l2 = false), 115280);
      setTimeout(() => (this.l3 = true), 115280);
      setTimeout(() => (this.l3 = false), 115350);
      setTimeout(() => (this.l4 = true), 115350);
      setTimeout(() => (this.l4 = false), 115380);
      setTimeout(() => (this.logoB = false), 115380);

      setTimeout(() => (this.secondRap = true), 115650);
      setTimeout(() => (this.secondRap = false), 141440);

      setTimeout(() => (this.transition = true), 141470);
      setTimeout(() => (this.transition = false), 152750);

      setTimeout(() => (this.end = true), 152750);
      setTimeout(() => {
        this.isPlayed = false;
        this.end = false;
        this.stopAudio();
      }, 162000);
    },
    stopVideo() {
      var highestTimeoutId = setTimeout(";");
      for (var i = 0; i < highestTimeoutId; i++) {
        clearTimeout(i);
      }

      this.intro = false;
      this.refrain = false;
      this.firstRap = false;
      this.transition = false;
      this.logoB = false;
      this.l1 = false;
      this.l2 = false;
      this.l3 = false;
      this.l4 = false;
      this.secondRap = false;
      this.end = false;
    },
    startAudio() {
      this.audio.play();
    },
    stopAudio() {
      this.audio.pause();
      this.audio.currentTime = 0;
    },
    setVolume() {
      this.audio.volume = this.volume.value / 100;
    }
  },
};
</script>

<style scoped>
.home {
  background: #e9e7ec;
  height: 100vh;

  font-family: Arial, Helvetica, sans-serif;
}

.video {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;

  transition: all 0.2s ease-out;
}

.video * {
  font-family: "Anton", sans-serif;
}

.container {
  display: flex;

  margin-top: 50px;
  gap: 20px;
  z-index: 99;
}

.player {
  width: 80%;
}

.pause {
  position: relative;
  width: 100%;
  height: 60vh;
  background: url(../assets/presentation.jpg) center center/cover;
}

.play {
  width: 100vw;
  height: 100vh;
  background: var(--first-bg);
}

.logoBlack {
  flex-direction: column;
  justify-content: center;
  align-items: center;

  width: 0%;
  height: 0%;

  background: url(../assets/bg/bg-second.jpg) center center/cover;

  animation: bgSet 0.3s forwards;
}

@keyframes bgSet {
  35% {
    width: 100%;
    height: 100%;
  }
  60% {
    width: 100%;
    height: 100%;
  }
  100% {
    width: 0%;
    height: 0%;
  }
}

.logoBlack img {
  width: 400px;
}

.container.played {
  position: absolute;

  padding: 0;
  margin: 0;
  width: 100vw;
  height: 100vh;
}

.container.paused {
  padding-right: 15px;
  padding-left: 15px;
  margin-right: auto;
  margin-left: auto;
}
@media (min-width: 768px) {
  .container.paused {
    width: 750px;
  }
}
@media (min-width: 992px) {
  .container.paused {
    width: 970px;
  }
}
@media (min-width: 1200px) {
  .container.paused {
    width: 1170px;
  }
}

h2 {
  max-width: 100%;
  word-wrap: normal;
  font-weight: normal;

  padding: 10px 0;
}

.explain {
  max-width: 20%;
}

.explain h3 {
  margin-top: 10px;
  font-weight: normal;
}

.btn {
  display: flex;
  align-items: center;
  justify-content: center;

  background: #c9c8d0;
  border-radius: 50%;

  cursor: pointer;

  transition: transform 0.1s linear;
}

.btn-play {
  height: 150px;
  width: 150px;
}

.btn-stop {
  position: absolute;

  width: 40px;
  height: 40px;
  left: 0;
  bottom: 0;

  margin: 15px;
}

.stop-logo {
  width: 15px;
  height: 15px;
  background: var(--first-bg);
}

.play-logo {
  width: 70px;
  height: 70px;

  border-style: solid;
  border-color: transparent transparent transparent var(--first-bg);
  border-width: 35px 0px 35px 70px;

  transform: translateX(15%);
}

.btn:hover {
  transform: scale(1.05);
}

#container-volume {
  width: 150px;
  height: 25px;
  position: absolute;
  margin: 10px auto;
  bottom: 0;
  left: 5%;
  display: flex;
  align-items: center;
}

#container-volume .fa-volume-up {
  margin-top: -6px;
  color: #fff;
  margin-right: -8px;
}

#volume {
  position: absolute;
  left: 24px;
  margin: 0 auto;
  height: 5px;
  width: 90%;
  background: #555;
  border-radius: 15px;
  cursor: pointer;
}

@media (max-width: 1100px) {
  .btn-play {
    height: 50px;
    width: 50px;
  }
  .play-logo {
    width: 24px;
    height: 24px;

    border-width: 12px 0px 12px 24px;
  }
  .btn-stop {
    position: absolute;

    width: 40px;
    height: 40px;
    left: 5%;
    bottom: 0;

    margin: 15px;
  }
  #container-volume {
    left: 50%;
    transform: translateX(-50%);
  }
}

@media (max-width: 800px) {
  .container {
    flex-direction: column;
    margin-top: 0;
  }
  .container .explain {
    order: 1;
  }
  .container .player {
    order: 2;
  }
  .explain {
    max-width: 100%;
  }
  .player {
    width: 100%;
  }
}

@media (max-width: 400px) {
  .btn-play {
    height: 50px;
    width: 50px;
  }
  .play-logo {
    width: 24px;
    height: 24px;

    border-width: 12px 0px 12px 24px;
  }
  .btn-stop {
    position: absolute;

    width: 40px;
    height: 40px;
    left: 5%;
    bottom: 0;

    margin: 15px;
  }
  #container-volume {
    left: 50%;
    transform: translateX(-50%);
  }
}
</style>
