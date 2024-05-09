<template>
    <div id="home">
      <h1>I’m a designer specialising in <span>UI/UX</span> and <span>Interaction Design</span></h1>
      <i class="fa-solid fa-angle-down"></i>
    </div>
  
    <div class="clients">
      <h2>Some of <span>the clients I have designed for</span></h2>

      <div class="image-container">
          <div v-for="(image, index) in images" :key="index" id="logo-container">
            <img class="logo" :src="image.isColored ? image.coloredSrc : image.src" :alt="'Logo'"
              @mouseover="handleMouseover(index)"
              @mouseleave="handleMouseleave(index)" >
          </div>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        images: [
          {
            src: require('@/assets/Airbnb-logo.png'),
            coloredSrc: require('@/assets/Airbnb-colored-logo.png'),
            
          },
          {
            src: require('@/assets/Google-logo.png'),
            coloredSrc: require('@/assets/Google-colored-logo.png')
          },
          {
            src: require('@/assets/Microsoft-logo.png'),
            coloredSrc: require('@/assets/Microsoft-colored-logo.png')
          },
          {
            src: require('@/assets/FedEx-logo.png'),
            coloredSrc: require('@/assets/FedEx-logo-colored.png')
          }
        ]
      };
    },
    methods: {
      handleMouseover(index) {
        this.images[index].isColored = true
      },
      handleMouseleave(index) {
        this.images[index].isColored = false
      }
    }
  };
  </script>
  
  <style scoped>
  #home {
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    gap: 200px;
    margin: auto;
    max-height: 100vh;
    padding-top: 250px;

  }
  
  
  h2 {
    width: 50%;
  }

  
  i {
    font-size: 30px;
    /* margin-top: 240px; */
    flex-grow: 1;
  }
  .clients {
    margin-top: 80px;
    margin-bottom: 130px;
  }
  
  
  .image-container {
    display: flex;
    align-items: center;
    justify-content: space-between;
    
    margin-block: 80px; 
  }

  
  .logo {
    width: 70%;

    transition: filter 0.5s ease-in-out;
    filter: grayscale(100%);
  }
  
  .logo:hover {
    filter: grayscale(0%);
  }

  @media (max-width: 900px) {
    #home {
      gap: 150px;
    }
    
    h2 {
      width: 80%;
      font-size: 28px;
    }
    .image-container {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 30px;
    }
    .clients {
      margin-bottom: 50px;
    }
  }
  </style>
  