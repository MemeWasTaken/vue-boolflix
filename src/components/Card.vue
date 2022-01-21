<template>
    <ul class="card">
        <li> <img :src="poster" alt=""> </li>
        <li> {{ title }} </li>
        <li> {{ originalTitle }} </li>
        <li> <i :class="'flag flag-' + getFlag(lang)"></i> </li>
        <li> {{ rate }} </li>
    </ul>
</template>

<script>
    export default {
        name: "Card",
        props: [
            // info: Object,'
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
            }
        },
    };
</script>

<style>

</style>