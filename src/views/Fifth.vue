<template>
  <div
    ref="indicatorFifth"
    style="transition: all 0.5s ease-in-out;"
    id="indicatorFifth"
  >
    <div
      style="position: absolute; height: 0.75%; width: 2.5%; top: 94.5vh; left: 45%; z-index: 9; background: white; border-radius: 10%; transition: all 0.5s ease-in-out;"
    ></div>
    <div
      style="position: absolute; height: 4%; width: 2.5%; top: 90.5vh; left: 45%; z-index: 9; background: linear-gradient(to top, rgba(255,255,255, 0.25), transparent); transition: all 0.5s ease-in-out;"
    ></div>
  </div>
  <div id="back-box">
    <div id="white-border"></div>
    <keep-alive>
      <component :is="currentComponent"></component>
    </keep-alive>
    <div id="buttons">
      <button
        @click="changeComponent(`audio`)"
        style="left: 44.5%"
        type="submit"
      >
        <svg
          xmlns="http://www.w3.org/2000/svg"
          width="16"
          height="16"
          fill="currentColor"
          class="bi bi-volume-up-fill"
          viewBox="0 0 16 16"
        >
          <path
            d="M11.536 14.01A8.473 8.473 0 0 0 14.026 8a8.473 8.473 0 0 0-2.49-6.01l-.708.707A7.476 7.476 0 0 1 13.025 8c0 2.071-.84 3.946-2.197 5.303l.708.707z"
          />
          <path
            d="M10.121 12.596A6.48 6.48 0 0 0 12.025 8a6.48 6.48 0 0 0-1.904-4.596l-.707.707A5.483 5.483 0 0 1 11.025 8a5.483 5.483 0 0 1-1.61 3.89l.706.706z"
          />
          <path
            d="M8.707 11.182A4.486 4.486 0 0 0 10.025 8a4.486 4.486 0 0 0-1.318-3.182L8 5.525A3.489 3.489 0 0 1 9.025 8 3.49 3.49 0 0 1 8 10.475l.707.707zM6.717 3.55A.5.5 0 0 1 7 4v8a.5.5 0 0 1-.812.39L3.825 10.5H1.5A.5.5 0 0 1 1 10V6a.5.5 0 0 1 .5-.5h2.325l2.363-1.89a.5.5 0 0 1 .529-.06z"
          />
        </svg>
        <p>Audio</p>
      </button>
      <button
        @click="changeComponent(`cabin`)"
        style="left: 48.25%"
        type="submit"
      >
        <svg
          xmlns="http://www.w3.org/2000/svg"
          width="16"
          height="16"
          fill="currentColor"
          class="bi bi-egg-fill"
          viewBox="0 0 16 16"
        >
          <path
            d="M 14 15 q -6 3 -12 0 C 0.5 7.5 6.5 0 8 0 s 7.5 7.5 6 15 z M 8 1.5 C 5 4.5 3.5 7.5 3.5 10.5 Q 6.5 12 6.5 15 L 9.5 15 Q 9.5 12 12.5 10.5 C 12.5 7.5 11 4.5 8 1.5 M 6.5 6 Q 5.75 7.5 6.5 9 Q 8 9.75 9.5 9 Q 10.25 7.5 9.5 6 Q 8 5.1 6.5 6 Z"
          />
        </svg>
        <p>Cabin</p>
      </button>
      <button @click="changeComponent(`video`)" style="left: 52%" type="submit">
        <svg
          xmlns="http://www.w3.org/2000/svg"
          width="16"
          height="16"
          fill="currentColor"
          class="bi bi-camera-video-fill"
          viewBox="0 0 16 16"
        >
          <path
            fill-rule="evenodd"
            d="M0 5a2 2 0 0 1 2-2h7.5a2 2 0 0 1 1.983 1.738l3.11-1.382A1 1 0 0 1 16 4.269v7.462a1 1 0 0 1-1.406.913l-3.111-1.382A2 2 0 0 1 9.5 13H2a2 2 0 0 1-2-2V5z"
          />
        </svg>
        <p>Video</p>
      </button>
    </div>
  </div>
</template>

<script>
import Audio from '../components/Audio.vue'
import Cabin from '../components/Cabin.vue'
import Video from '../components/Video.vue'

export default {
  name: 'Fifth',
  data() {
    return {
      currentComponent: 'audio'
    }
  },
  methods: {
    changeComponent(name) {
      this.currentComponent = name
      if (name === 'audio') {
        this.$refs.indicatorFifth.children[0].style.left = 45 + `%`
        this.$refs.indicatorFifth.children[1].style.left = 45 + `%`
      }
      if (name === 'cabin') {
        this.$refs.indicatorFifth.children[0].style.left = 48.75 + `%`
        this.$refs.indicatorFifth.children[1].style.left = 48.75 + `%`
      }
      if (name === 'video') {
        this.$refs.indicatorFifth.children[0].style.left = 52.5 + `%`
        this.$refs.indicatorFifth.children[1].style.left = 52.5 + `%`
      }
    }
  },
  components: {
    audio: Audio,
    cabin: Cabin,
    video: Video
  },
  mounted() {}
}
</script>

<style scoped>
svg {
  top: 10%;
  left: 0%;
  position: relative;
  padding-bottom: 0;
  z-index: 2;
  fill: white;
}

p {
  top: 0%;
  left: 50%;
  /* bottom: 7em; */
  transform: translate(-50%, -50%);
  position: relative;
  padding-bottom: 0;
  z-index: 2;
  fill: white;
}

#back-box {
  position: absolute;
  background-color: #020738;
  height: 95vh;
  width: 100%;
  /* bottom: 30px; */
  top: 0;
  border-radius: 0 0 30px 30px;
  box-sizing: border-box;
  border-bottom: 0.5px solid white;
  border-left: 1px solid white;
  border-right: 1px solid white;
  z-index: -3;
  overflow: hidden;
  /* display: flex; */
}

#white-border {
  position: absolute;
  background-color: #ffffff;
  height: 92vh;
  width: 98.5vw;
  bottom: 30px;
  top: 50%;
  left: 50%;
  /* bottom: 7em; */
  transform: translate(-50%, -50%);
  border-radius: 25px 25px 25px 25px;
  box-sizing: border-box;
  clip-path: polygon(
    0 0,
    0 100%,
    42.5% 100%,
    45% 95%,
    55% 95%,
    57.5% 100%,
    100% 100%,
    100% 0
  );
}

button {
  position: absolute;
  top: 94%;
  height: 6%;
  width: 3.5%;
  font-size: 60%;
  color: white;
  background: none;
  /* border: 1px solid red; */
  border: none;
}
</style>
