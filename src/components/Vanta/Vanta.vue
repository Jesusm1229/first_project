<template>
  
    <v-vanta id="Vanta" ref="vanta" effect="globe" :options="options">      
    </v-vanta>
  
</template>

<script>

import VVanta from 'vue-vanta';

export default {
  components: { VVanta },
  data() {
    return {
      options: {
        mouseControls: true,
        touchControls: true,
        gyroControls: false,
        minHeight: 200,
        minWidth: 400,
        scale: 1.0,
        scaleMobile: 1.0,
        color: "#ffffff",
        backgroundColor: "#1b83c3",
      }
    };
  },
  props: {
    typeJustifyContent: {
      require: true,
      type: String,
    },
    removeBackgroundImage: {
      require: true,
      type: Boolean,
    },
  },
  updated() {
    this.$refs.background.style.justifyContent = this.typeJustifyContent;

   
  },
};

</script>

<style scoped>
 div#Vanta{
  width: 100%;
  height: 45vw;

  display: flex;
  flex-direction: column;
  justify-content: space-between;
  align-items: flex-start;

  background-color: var(--black);
  background-repeat: no-repeat;
  background-size: cover;
  background-position: top;
} 


@media screen and (max-width: 822px) {
  div#Background {
    align-items: center;

    background-color: var(--black);

    height: 35rem;
  }
}
</style>
