<template>
   
    <v-vanta id="Background"
        ref="background" effect="globe" :options="options"></v-vanta>
        
    
</template>

<script>

import VVanta from 'vue-vanta';

  export default {
    name: "Background",
    components: { VVanta },
    data () {
      return {
        options: {
        mouseControls: true,
        touchControls: true,
        gyroControls: false,
        minHeight: 100.00,
        minWidth: 100.00,
        scale: 1.00,
        scaleMobile: 1.00,
        color: '#ffffff',
        backgroundColor: '#1b83c3' 
        }
      }
    },
    props: {
            typeJustifyContent: {
                require: true,
                type: String
            },
            removeBackgroundImage: {
                require: true,
                type: Boolean
            }
        },
        updated() {
            this.$refs.background.style.justifyContent = this.typeJustifyContent;

            if(this.removeBackgroundImage) {
                this.$refs.background.style.backgroundImage = "none";
                this.$refs.background.style.height = "100vh";
            } else {
                this.$refs.background.style.backgroundImage = `url(${require('../../assets/desktop/image-hero.jpg')})`;
                this.$refs.background.style.height = "";
            }
        }
  }


   /*  export default {
        name: "Background",
        components: {

        },
        props: {
            typeJustifyContent: {
                require: true,
                type: String
            },
            removeBackgroundImage: {
                require: true,
                type: Boolean
            }
        },
        updated() {
            this.$refs.background.style.justifyContent = this.typeJustifyContent;

            if(this.removeBackgroundImage) {
                this.$refs.background.style.backgroundImage = "none";
                this.$refs.background.style.height = "100vh";
            } else {
                this.$refs.background.style.backgroundImage = `url(${require('../../assets/desktop/image-hero.jpg')})`;
                this.$refs.background.style.height = "";
            }
        }
    }
 */
</script>

<style scoped>

    div#Background {
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

           

            height: 35rem;
        }
    }

</style>
