<template>
  <div class="fixed-center text-center">
    <h2>ESP32</h2>

    <!-- <model-viewer src="../../public/model.glb"> </model-viewer> -->
    <!-- <model-gltf src="../../public/model.gltf"></model-gltf> -->
    <model-viewer camera-controls src="model.gltf"> </model-viewer>
    <model-viewer
      camera-controls
      src="https://firebasestorage.googleapis.com/v0/b/quasar3d-fb3c2.appspot.com/o/model3D%2Fmodel.glb?alt=media&token=3f1bffe3-9e0b-4fa3-96b8-f20c28affdcc"
    >
    </model-viewer>
    <model-viewer
      camera-controls
      crossorigin="use-credentials"
      src="https://cdn.glitch.com/36cb8393-65c6-408d-a538-055ada20431b/Astronaut.glb?1542147958948"
    >
    </model-viewer>
    <!-- <div class="image-map">
      <img src="../../public/assets/ESP32.svg" alt="esp32" />
      <ul>
        <li v-for="(item, i) in espPin" :key="i">
          <a
            href="#"
            @click="example"
            :style="{ left: item.posi.l + 'px', top: item.posi.t + 'px' }"
            :class="item.class"
            @mouseover="upHere = true"
            @mouseleave="upHere = false"
          >
            <span>{{ item.nam }}</span>
            <q-tooltip
              transition-show="rotate"
              transition-hide="rotate"
              content-style="font-size: 16px; background-color:rgba(0,0,0,0.0)"
              :offset="[10, 10]"
            >
              <q-card
                class="my-card text-white"
                style="background: radial-gradient(circle, #35a2ff 0%, #014a88 100%)"
              >
                <q-card-section>
                  <div class="text-h6">{{ item.nam }}</div>
                  <div class="text-subtitle2">by John Doe</div>
                </q-card-section>

                <q-card-section class="q-pt-none">
                  Lorem, ipsum dolor sit amet consectetur adipisicing elit.
                  Harum beatae modi hic dolores corrupti sit, similique sapiente
                  magnam ad soluta iure eos tempora, error rerum ut nam, minima
                  quisquam rem.
                </q-card-section>
              </q-card>
            </q-tooltip>
          </a>
        </li>
        <li></li>
        <li class="v">
          <a href="#" @click="example"><span>3.3V</span></a>
        </li>
        <li class="gnd">
          <a href="#"><span>GND</span></a>
        </li>
        <li class="D15">
          <a href="#"><span>D15</span></a>
        </li>
        <li class="D2">
          <a href="#"><span>D2</span></a>
        </li>
        <li class="D4">
          <a href="#"><span>D4</span></a>
        </li>
      </ul>
    </div> -->
    <!-- <p v-show="active">Show</p> -->
    <!-- <div @mouseover="mouseOver">Hover over me!</div> -->
    <!-- <div @mouseover="upHere = true" @mouseleave="upHere = false"> -->
    <!-- <h2>Something Something</h2> -->
    <!-- <some-component v-show="upHere"></some-component> -->
    <!-- {{ upHere }} -->
    <!-- </div> -->
    <q-dialog v-model="card">
      <q-card class="my-card">
        <q-img src="https://cdn.quasar.dev/img/chicken-salad.jpg" />

        <q-card-section>
          <q-btn
            fab
            color="primary"
            icon="place"
            class="absolute"
            style="top: 0; right: 12px; transform: translateY(-50%);"
          />

          <div class="row no-wrap items-center">
            <div class="col text-h6 ellipsis">
              Cafe Basilico
            </div>
            <div
              class="col-auto text-grey text-caption q-pt-md row no-wrap items-center"
            >
              <q-icon name="place" />
              250 ft
            </div>
          </div>

          <q-rating v-model="stars" :max="5" size="32px" />
        </q-card-section>

        <q-card-section class="q-pt-none">
          <div class="text-subtitle1">
            $・Italian, Cafe
          </div>
          <div class="text-caption text-grey">
            Small plates, salads & sandwiches in an intimate setting.
          </div>
        </q-card-section>

        <q-separator />

        <q-card-actions align="right">
          <q-btn v-close-popup flat color="primary" label="Reserve" />
          <q-btn v-close-popup flat color="primary" round icon="event" />
        </q-card-actions>
      </q-card>
    </q-dialog>
    <ul>
      <!-- <li v-for="(item, i) in espPin" :key="i">
        <a href="#" @click="example"
          ><span>{{ item.posi.l }}</span></a
        >
      </li> -->
      <!-- <li class="v">
        <a href="#" @click="example"><span>3.3V</span></a>
      </li>
      <li class="gnd">
        <a href="#"><span>GND</span></a>
      </li>
      <li class="D15">
        <a href="#"><span>D15</span></a>
      </li>
      <li class="D2">
        <a href="#"><span>D2</span></a>
      </li>
      <li class="D4">
        <a href="#"><span>D4</span></a>
      </li> -->
    </ul>
  </div>
</template>

<script>
// import modelViewer from "@google/model-viewer";
import { ModelGltf } from "vue-3d-model";

export default {
  // components: { modelViewer },
  components: {
    ModelGltf
  },
  name: "PageIndex",
  data() {
    return {
      stars: 3,
      card: false,
      upHere: false,
      lfPx: 137,
      topPX: 402,
      active: false,
      espPin: [
        { nam: "3.3V", class: "cir", posi: { l: 138, t: 402 } },
        { nam: "GND", class: "cir", posi: { l: 177, t: 402 } },
        { nam: "D15", class: "cir", posi: { l: 217, t: 402 } },
        { nam: "D2", class: "cir", posi: { l: 257, t: 402 } },
        { nam: "D4", class: "cir", posi: { l: 297, t: 402 } },
        { nam: "RX2", class: "cir", posi: { l: 336, t: 402 } },
        { nam: "TX2", class: "cir", posi: { l: 375, t: 402 } },
        { nam: "D5", class: "cir", posi: { l: 415, t: 402 } },
        { nam: "D18", class: "cir", posi: { l: 454, t: 402 } },
        { nam: "D19", class: "cir", posi: { l: 494, t: 402 } },
        { nam: "D21", class: "cir", posi: { l: 533, t: 402 } },
        { nam: "RX0", class: "cir", posi: { l: 573, t: 402 } },
        { nam: "TX0", class: "cir", posi: { l: 612, t: 402 } },
        { nam: "D22", class: "cir", posi: { l: 652, t: 402 } },
        { nam: "D23", class: "cir", posi: { l: 692, t: 402 } },
        { nam: "Vin", class: "cir", posi: { l: 138, t: 8 } },
        { nam: "GND", class: "cir", posi: { l: 177, t: 8 } },
        { nam: "D13", class: "cir", posi: { l: 217, t: 8 } },
        { nam: "D12", class: "cir", posi: { l: 257, t: 8 } },
        { nam: "D14", class: "cir", posi: { l: 297, t: 8 } },
        { nam: "D27", class: "cir", posi: { l: 336, t: 8 } },
        { nam: "D26", class: "cir", posi: { l: 375, t: 8 } },
        { nam: "D25", class: "cir", posi: { l: 415, t: 8 } },
        { nam: "D33", class: "cir", posi: { l: 454, t: 8 } },
        { nam: "D32", class: "cir", posi: { l: 494, t: 8 } },
        { nam: "D35", class: "cir", posi: { l: 533, t: 8 } },
        { nam: "D34", class: "cir", posi: { l: 573, t: 8 } },
        { nam: "VN", class: "cir", posi: { l: 612, t: 8 } },
        { nam: "VP", class: "cir", posi: { l: 652, t: 8 } },
        { nam: "EN", class: "cir", posi: { l: 692, t: 8 } },
        { nam: "GND", class: "cub", posi: { l: 669, t: 71 } },
        { nam: "3.3V", class: "cub", posi: { l: 648, t: 71 } },
        { nam: "9", class: "cub", posi: { l: 627, t: 71 } },
        { nam: "3.3V", class: "cub", posi: { l: 648, t: 71 } }
      ]
    };
  },
  created() {},
  methods: {
    mouseOver: function() {
      this.active = !this.active;
    },
    example() {
      // alert("hola");
    }
  }
};
</script>

<style scoped>
/* li {
  counter-increment: i;
} */

/* li a::after { */
/* works for generated content  */
/* content: "i == " counter(i); */
/* left: 137px; */
/* top: 402px; */
/* does not work anywhere else */
/* background: hsl(calc(counter(i) * 10), 50%, 50%); */
/* } */

/* styles... */
/* body {
  align-items: stretch;
  align-content: stretch;
  display: flex;
  flex-wrap: wrap;
  height: 100vh;
} */

/* div {
  display: flex;
  flex: 1 0 auto;
  white-space: nowrap;
} */
/* 
div::after {
  align-items: center;
  display: flex;
  flex: 1 0 auto;
  justify-content: center;
  padding: 0.5em 1em;
} */
img {
  width: 800px;
}
.image-map {
  /* background-color: aqua; */
  /* width: 480px;
  height: 550px; */
  position: relative;
}
.image-map ul {
  margin: 0;
  padding: 0;
  list-style: none;
}
.image-map a:link,
.image-map a:visited {
  position: absolute;
  display: block;
  /* width: 30px; */
  /* height: 30px; */
  /* color: white; */
  /* text-decoration: none; */
  /* border: 1px solid transparent; */
  /* border-radius: 15em/15em; */
}
.image-map .cir:link,
.image-map .cir:visited {
  border-radius: 15em/15em;
  height: 30px;
  width: 30px;
}
.image-map .cub:link,
.image-map .cub:visited {
  /* border-radius: 15em/15em; */
  height: 8px;
  width: 14px;
}
.image-map a:hover,
.image-map a:focus {
  border: 5px solid gold;
}
</style>
