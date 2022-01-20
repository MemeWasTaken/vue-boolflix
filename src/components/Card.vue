<template>
    <ul class="card">
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
            // info: Object,
            'title',
            'originalTitle',
            'lang',
            'rate'
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
                
                    default:
                        return lang ;

                }
            }
        },
    };
</script>

<style>

</style>