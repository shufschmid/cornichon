<script>
export default {
  data() {
    return {
      anzahl_menschen: 500,
    };
  },
  computed: {
    // a computed getter
    anzahl_anhaenger() {
      // `this` points to the component instance
      return (Math.floor(this.anzahl_menschen / 100))-1;
    },
  },

  // `mounted` is a lifecycle hook which we will explain later
  mounted() {
    // `this` refers to the component instance.
    console.log(this.count); // => 1

    // data can be mutated as well
    this.anzahl_menschen = 620;
  },
};
</script>

<template>
  <div>
    <main>Anzahl Personen: <input type="number" v-model="anzahl_menschen" style="width:60px"/> Illustrationen: ©<a href="http://tram-basel.ch">tram-basel.ch</a>
      <input
        type="range"
        min="100"
        max="10000"
        v-model="anzahl_menschen"
        width="500"
        style="width: 100%"
      />
      
      <hr />

      <img
        v-for="n in anzahl_anhaenger"
        src="https://www.g-st.ch/trambasel/bvb_blt/typen/pic1416_11.gif" width="69"
      /><img src="https://www.g-st.ch/trambasel/bvb_blt/typen/pic659_11.gif"/>
    </main>
  </div>
</template>
