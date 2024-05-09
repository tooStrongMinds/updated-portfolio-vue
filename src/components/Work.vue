<template>
    <div id="work">
        <h2>Selected <span>Works</span></h2>
        <div class="myworks">
            <div class="card" v-for="work in works" :key="work.title" :class="{even: work.id % 2 === 0, odd: work.id % 2 !== 0}">
                <img :src="work.img" :alt="work.title">
                <div class="description">
                    <h4>{{ work.title }}</h4>
                    <h3>{{ work.desc }} <span>{{ work.spanned }}</span></h3>
                    <p>{{ work.tag }}</p>
                    <button @mouseover="changeArrow(true, work.id)" @mouseleave="changeArrow(false, work.id)">View More <i v-show="!isHovered[work.id]" class="fa-solid fa-angle-right"></i> <i v-show="isHovered[work.id]" class="fa-solid fa-arrow-right"></i ></button>
                </div>
                
            </div>
        </div>
    </div>
  
</template>

<script>
export default {
    data() {
        return {
            isHovered: {},
            works: [
                {img: require('@/assets/webone.png'),
                    title: 'Real Estate Template',
                    desc: 'Lorem ipsum dolor sit amet, consectetur', spanned:'adipiscing elit. Ultrices lorem non feugiat egestas amet.',
                    tag: 'Website Design',
                    id: 1
                },
                {img: require('@/assets/webtwo.png'),
                    title: 'Plant identification app',
                    desc: 'Lorem ipsum dolor sit amet, consectetur', spanned:'adipiscing elit. Ultrices lorem non feugiat egestas amet.',
                    tag: 'Mobile App',
                    id: 2
                },
                {img: require('@/assets/webthree.png'),
                    title: 'smart home app',
                    desc: 'Lorem ipsum dolor sit amet, consectetur', spanned:'adipiscing elit. Ultrices lorem non feugiat egestas amet.',
                    tag: 'Mobile App',
                    id: 3
                },
                {img: require('@/assets/webfour.png'),
                    title: 'Logo animation',
                    desc: 'Lorem ipsum dolor sit amet consectetur',spanned:'adipiscing elit. Ultrices lorem non feugiat egestas amet.',
                    tag: 'Animation',
                    id: 4
                },
            ]
        }
    },
    methods: {
        changeArrow(state, id) {
            this.isHovered[id] = state
        }
    }
}
</script>

<style>
    #work {
        padding-block: 80px;
    }
    .myworks {
        margin-top: 97px;
        display: flex;
        flex-direction: column;
        gap: 97px;
    }
    .card {
        display: flex;
        align-items: center;
        gap: 32px;

}
span {
    font-weight: 600;
}
.card img {
    width: 50%;
}
.description {
    text-align: left;
    display: flex;
    flex-direction: column;
    align-self: flex-end;
}
.description h4 {
    text-transform: uppercase;
    font-size: 16px;
    letter-spacing: 4%;
    line-height: 150%;
    margin-bottom: 16px;

}
.description h3 {
    font-weight: 100;
    font-size: 32px;
}
.description p {
    font-weight: 100;
    font-size: 18px;
    margin-top: 24px;
}
.even {
    display: flex;
    flex-direction: row-reverse;
}
button {
    background-color: #010208;;
    color: #e3e4e6;
    width: fit-content;
    border-radius: 100px;
    padding: 8px 16px;
    cursor: pointer;
    text-transform: uppercase;

    margin-top: 32px;

    border-color: rgba(227, 228, 230, 0.55);
}

button:hover {
    padding: 10px 30px;
    background: linear-gradient(99deg, #BC3CD8 0.07%, #C54B8C 106.32%);
    transition: padding 0.3s linear;
    border: none;
}
button i {
    margin-left: 8px;
}

@media (max-width: 900px) {
    .card {
        display: flex;
        flex-direction: column;
    }
    .card img {
        width: 60%;
    }
    .description {
        text-align: center;
    }
    .description h3 {
        font-size: 25px;
    }
    .description h4 {
        font-size: 16px;
    }
    button {
        display: flex;
        align-items: center;
        margin: auto;
        margin-top: 20px;
    }
    button i {
        font-size: 15px;
    }
}
</style>