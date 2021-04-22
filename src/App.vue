<template>
  <div>
    <h3>Swiper some text</h3>
    <Swiper
      class="swiper_text"
      :content="texts"
      :duration="5"
      @onSwiperChange="changeActive"
    >
      <span>{{ texts[active] }}</span>
    </Swiper>
    <h3>Vertical Swiper</h3>
    <Swiper class="swiper_img" :content="images" :direction="direct[i]">
    </Swiper>
    <br />
    <button @click="clickchange">Change direction</button>
  </div>
</template>

<script>
import Swiper from "./components/swiper.vue";

export default {
  name: "App",
  components: {
    Swiper
  },
  data() {
    return {
      active: 0,
      direct: ["column-reverse", "column"],
      i: 0,
      texts: ["vue-swiper", "From Sissi_Li", "2021-4-22"],
      images: [
        "https://dummyimage.com/360x240/fff3cd/333&text=Swiper_xixi",
        "https://dummyimage.com/360x240/d6d8d9/333&text=Swiper_xixi",
        "https://dummyimage.com/360x240/cce5ff/333&text=Swiper_xixi"
      ]
    };
  },
  methods: {
    changeActive(n) {
      this.active = n;
    },
    clickchange() {
      if (this.i === 0) {
        this.i++;
      } else {
        this.i = 0;
      }
      // console.log(this.direct[this.i])
    }
  }
};
</script>

<style lang="scss" scoped>
.swiper {
  &_text {
    width: 150px;
    text-align: center;
    margin: 0 auto;
  }
  &_img {
    height: 240px;
    text-align: center;
    margin: 0 auto;
  }
}

button {
  background-color: rgb(199, 206, 206);
  height: 25px;
  width: 150px;
  margin: 0 auto;
  text-align: center;
  display: block;

  &:hover {
    background-color: white;
    color: rgb(52, 53, 53);
  }
  &:active {
    background-color: darkgray;
    color: white;
  }
}
h3 {
  text-align: center;
  margin: 45px 0px 30px 0px;
}
</style>
