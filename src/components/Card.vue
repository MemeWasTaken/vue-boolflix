<template>
    <ul class="card">
        <li>
            <img v-if="image" :src="poster" alt="" class="img-poster"> 
            <img v-else src="https://yify-subs.net/images/default_thumbnail.svg" alt="" class="img-placeholder">
        </li>
        <li> {{ title }} </li>
        <li> {{ originalTitle }} </li>
        <li> <i :class="'flag flag-' + getFlag(lang)"></i> </li>
        <li>
            <i
            v-for="vote in 5"
            :key="vote"
            :class="(vote <= roundNumber(rate)) ? 'fas fa-star' : 'far fa-star'"
            />
        </li>
    </ul>
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

    .img-poster {
        border-radius: 15px;
    }

    .img-placeholder {
        width: 342px;
        height: auto;
        border-radius: 15px;
    }

</style>