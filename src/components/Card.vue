<template>
    <div class="col position-relative text-white text-center p-2">

        <div class="element-card">
            <div class="poster overflow-hidden">
                <img v-if="image" :src="poster" alt="" class="img-poster"> 
                <img v-else src="https://yify-subs.net/images/default_thumbnail.svg" alt="" class="img-placeholder">
            </div>
            <div class="hidden position-absolute">
                <div class="text d-flex justify-content-around align-items-center overflow-auto">
                    <div class="title"> 
                        <span class="title-span">Titolo: {{ title }}</span>
                    </div>
                    <div v-show="originalTitle !== title" class="original-title">
                        <span>Titolo originale: {{ originalTitle }}</span>
                    </div>
                    <p>
                        {{ plot }}
                    </p>
                    <span class="langauge">Lingua: <i :class="'flag flag-' + getFlag(lang)"></i></span>
                    <div class="average-rate"> 
                        <div> Voto: </div>
                        <div class="stars d-flex justify-content-center">
                            <i  
                            v-for="vote in 5"
                            :key="vote"
                            :class="(vote <= roundNumber(rate)) ? 'fas fa-star' : 'far fa-star'"
                            />
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        name: "Card",
        props: [
            'image',
            'poster',
            'title',
            'originalTitle',
            'lang',
            'rate',
            'plot'
            
        ],
        methods: {
            getFlag(lang) {
                switch (lang) {
                    case 'en':
                        return 'us'; //Or UK
                    case 'ko' :
                        return 'kr' ;
                    case 'ja' :
                        return 'jp' ;
                    case 'ur' :
                        return 'pk' ;
                    case 'zh' :
                        return 'cn' ;
                    case 'el' :
                        return 'gr' ;
                    case 'hi' :
                        return 'in' ;
                    default:
                        return lang ;

                }
            },
            roundNumber(num) {
                const number = parseFloat(num);
                return Math.round(number / 2);
             },
        },
    };
</script>

<style lang="scss" scoped>
    
    .element-card {
        display: flex;
        flex-direction: column;
        align-items: center;
        height: 100%;
        width: 300px;

        .poster {
            height: 450px;
            border-radius: 20px;

            img {
                width: 100%;
                height: 100%;
            }
        }
    }
    .hidden {
        display: none;
        background-color: #2D2D2D;
        opacity: 0.9;
        border-radius: 18px;
        width: 300px;
        height: 450px;
        cursor: pointer;

        .text {
            height: 100%;
            padding: 0.5em;
            opacity: 1;
            flex-direction: column;
        }
    }
    .element-card:hover .hidden {
        display: block;
    }

</style>