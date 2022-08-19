<template>
  <div>
    <!-------Bag Image-- this where we set the background image for the app---->
    <div id="bag" v-bind:class="{ burst: ended }"></div>

    <!-------Bag Health-- the bag health div creates outide border for the bag health div---->
    <div id="bag-health">
      <div v-bind:style="{ width: health + '%' }"></div><!----this div has a background color of crimson and a percentage set to reduce the 
      bg color when the bag is punched------the v-bind:style allows to set a vue data value on the styling inside html from the script-->
    </div>
    <!-------Bag Controls---buttons to control the punching and restarting --->
    <div id="controls">
      <button v-on:click="throwPunch" v-show="!ended">Punch</button>
      <button v-on:click="restartPunch">Restart</button>
    </div>
  </div>
</template>

<script>
export default {
  name: "PunchBag",

  data() {
    return {
      health: 200,//initial health of bag set to 100
      ended: false,
    };
  },

  methods: {
    throwPunch() {
      this.health -= 10;
      if (this.health <= 0) {
        this.ended = true;
      }
    },
    restartPunch() {
      this.health = 100;
      this.ended = false;
    },
  },

  computed: {},
};
</script>

<style scoped>
#bag {
  background: url("~@/assets/bag.png");
  width: 200px;
  height: 500px;
  margin: 0 auto;
  background-size: cover;
  background-repeat: no-repeat;
}

#bag.burst {
  background: url("~@/assets/bag-burst.png");
  background-size: cover;
}

#bag-health {
  width: 200px;
  border: 5px solid #000;
  margin: 50px auto 20px auto;
}

#bag-health div {
  height: 20px;
  background-color: crimson;
}

#controls {
  margin: 0 auto;
  width: 120px;
}

/* #controls button {
  padding: 0.7rem 2rem;
  border: none;
  outline: none;
} */
</style>