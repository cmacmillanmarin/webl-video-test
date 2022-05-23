<!--
    ~/components/WebGL.vue
-->

<template>
    <div class="c-webgl in-layout grid">
        <div class="col-6" data-webgl-canvas>
            <video autoplay loop muted>
                <source :src="videoSrc" type="video/mp4">
                Your browser does not support the video tag.
            </video>
        </div>
        <div class="col-6" style="opacity: 0" data-webgl-canvas-fixed>
            <video autoplay loop muted>
                <source :src="videoSrc" type="video/mp4">
                Your browser does not support the video tag.
            </video>
        </div>
    </div>
</template>

<script>

import WebGL from "~/assets/js/webgl/Index";

export default {
    name: "WebGL",
    async mounted() {
        this.webgl = new WebGL();
        await this.webgl.create();
        this.webgl.update();
    },
    computed: {
        videoSrc() {
            return "/video/test.mp4"
        }
    }
}
</script>