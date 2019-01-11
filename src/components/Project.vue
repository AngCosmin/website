<template>
    <div class="card">
        <div class="header">
            <h3>{{ title }}</h3>
        </div>

        <img class="banner" :src="getBannerPath(banner)"/>        

        <div class="content" v-html="description"></div>

        <div class="footer">
            <span class="skill" v-for="technology in technologies" v-bind:key="technology">
                {{ technology }}
            </span>
        </div>
    </div>
</template>

<script>
    export default {
        props: [
            'title',
            'description',
            'technologies',
            'banner',
        ],
        methods: {
            getBannerPath (filename) {
                return filename ? require(`../assets/img/${filename}`) : ''
            }
        }
    }    
</script>