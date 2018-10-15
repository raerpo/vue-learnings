<template>
    <div v-if="video">
        <div class="embed-responsive embed-responsive-16by9">
         <iframe class="embed-responsive-item" :src="videoData.url" allowfullscreen></iframe>
        </div>
        <h4>{{ videoData.title }}</h4>
        <p>{{ videoData.description }}</p>
    </div>
</template>

<script>
export default {
    name: 'VideoPlayer',
    props: ['video'],
    computed: {
        videoData: function() {
            const { title, description } = this.video.snippet;
            const { videoId } = this.video.id;
            const url = `https://www.youtube.com/embed/${videoId}`;
            return {
                title,
                description,
                url
            }
        }
    }
}
</script>

<style>
h4 {
    margin-top: 1rem;
}
</style>