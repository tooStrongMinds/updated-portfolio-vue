<template>
  <nav>
      <div class="navbar">
        <img :src="image" alt="Design Logo" class="designLogo">
        <div class="menu">
            <div class="menusnav">
                <i
                    class="fas fa-bars"
                    @click="showMenu()" v-if="!showMobileMenu">
                </i>
                <i class="fa-solid fa-xmark" @click="closeMenu()" v-if="showMobileMenu"></i>
            </div>
            <div class="nav-content" :class="this.showMobileMenu ? 'open-menu' : 'closed-menu'">
                <ul class="nav-list" @click="closeMenu">
                    <li class="nav-item" >
                        <a href="#home" class="nav-link" @click="toggleActive('home')" :class="{active: activeSection === 'home'}" >Home</a>
                    </li>
                    <li class="nav-item">
                        <a href="#work" class="nav-link" @click="toggleActive('works')" :class="{active: activeSection === 'works'}">Works</a>
                    </li>
                    <li class="nav-item" >
                        <a href="#about" class="nav-link" @click="toggleActive('about')" :class="{active: activeSection === 'about'}">About</a>
                    </li>
                </ul>
            </div>
        </div>
        
      </div>
  </nav>
</template>

<script>
import Logo from "../assets/logo.png";
export default {
    name: 'NavigationBar',
    

    data() {
        return {
            image: Logo, 
            showMobileMenu: false,
            activeSection: 'home'
        }
    },
    methods: {
        toggleActive(section) {

           this.activeSection = section
        },
        showMenu() {
            this.showMobileMenu= true;
        },
        closeMenu() {
            this.showMobileMenu=false;
        }

    }
}
</script>

<style scoped>
.navbar {
    position: fixed;
    top: 0;
    padding: 20px 0;
    width: 90%;
    margin: auto;
    background-color: #010208;


    display: flex;
    align-items: center;
    justify-content: space-between;

    z-index: 100;

}
.fa-bars, .fa-xmark {
    display: none;
}
img {
    width: 100px;
}
.nav-list {
    list-style: none;
    display: flex;
    position: relative;
}
.nav-item {
    margin-left: 2rem;
    position: relative;
}
.nav-link {
    color: #e3e4e6;
    text-decoration: none;
    text-transform: uppercase;
    font-weight: bold;
    font-size: 14px;
    position: relative;
    transition: color 0.3s linear;

}
.nav-link:hover, .nav-link.active {
    background-image: linear-gradient(99deg, #BC3CD8 0.07%, #C54B8C 106.32%); /* Your gradient colors */
  -webkit-background-clip: text; 
  background-clip: text;
  color: transparent;

  padding-bottom: 3px;

  border-bottom: 3px solid #e3e4e6;
  border-bottom-left-radius: 2px;
  border-bottom-right-radius: 2px;
}
.nav-link:hover::before {
    position: absolute;
	/* height: 100%; */
	height: 5px;
	/* top: 0; */
	bottom: 0;
	z-index: 0;
    width: 50%;
    color: #fff;
}
@media (max-width: 768px) {
    
    /* .menu {
        padding-top: 10px;
        position: absolute;
        width: 100%;
    } */
    .designLogo {
        position: relative;
    }
    .open-menu {
        opacity: 1;
        /* background: red;; */
        height: 150px;

        margin-top: 30px;
    }
    .closed-menu {
        opacity: 0;
        height: 0;
        padding: 0;
    }
    .nav-content {
        flex-direction: column;
        z-index: 100;
        position: relative;
        transition: all 0.3s ease-in-out;
    }
    .nav-list {
        flex-direction: column;
        gap: 30px;
    }
    .fa-bars, .fa-xmark {
        display: block;
        text-align: right;
        padding: 0 10px 10px 0;
        cursor: pointer;


        position: relative;
    }
    /* .fa-xmark {
        margin-top: 100px;
    } */
    

}

</style>