<template>
    <div id="about">
        <div class="aboutMe">
            <h3>A bit about me</h3>
            <h2>I am a UI/UX designer who is passionate about creating <span>beautiful and joyful digital experiences. Besides design, I love music, games and travelling.</span> </h2>
        </div>
        <div class="gridImages">
            <div class="images" v-for="image in images" :key="image.id">
                <img :src="image.img" :alt="image.title">
            </div>
        </div>
    </div>
  
</template>

<script>
export default {
    data() {
        return {
            images: [
                {img: require('@/assets/music.png'),
                    title: 'A guitar',
                    id: 1
                },
                {img: require('@/assets/games.png'),
                    title: 'Gaming Console',
                    id: 2
                },
                {img: require('@/assets/travelling.png'), title: 'A man on a Hike',
                    id: 3
                }
            ]
        }
    },

}
</script>

<style scoped>
#about {
    /* display: flex;
    align-content: center; */
    padding-block: 74px;

    display: grid;
    grid-template-columns: 1fr 1fr;
    align-items: center;
}
.aboutMe {
    text-align: left;
    width: 90%;

}
.aboutMe h3 {
    text-transform: uppercase;
    font-size: 24px;
    margin-bottom: 16px;
}
.aboutMe h2 {
    font-size: 32px;
}
.gridImages {
    display: grid;
        gap: 10px;
        grid-template-columns: repeat(2, 1fr);
}

.images:first-child {
    grid-row: span 2;
    margin-top: 180px;
}
.images > img {
    width: 280px;
}
@media (max-width: 900px) {
    #about {
        display: unset;
    }
    .aboutMe {
        text-align: center;
        width: 100%;
    }
    .aboutMe h3 {
        font-size: 20px;
    }
    .aboutMe h2 {
        font-size: 25px;
        text-align: center;
        width: 100%;
    }
    .gridImages {
        display: none;
    }
}

</style>