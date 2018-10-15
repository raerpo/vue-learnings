<template>
    <ul class="list-group list-unstyled">
        <li 
            class="list-group-item media" 
            v-for="video in videos" 
            :key="video.etag"
            @click="onVideoSelect(video)"
        >
            <img class="mr-3" :src="thumbnailUrl(video)" />
            <div class="media-body">
                <p>{{ video.snippet.title }}</p>
            </div>
        </li>
    </ul>
</template>

<script>
export default {
    name: 'VideList',
    props: ['videos'],
    methods: {
        thumbnailUrl: function(video) {
            return video.snippet.thumbnails.default.url;
        },
        onVideoSelect: function(video) {
            this.$emit('videoSelect', video);
        }
    }
}
</script>

<style scoped>
    li {
        display: flex;
    }
    li:hover {
        background-color: #eee;
        cursor: pointer;
    }
</style>