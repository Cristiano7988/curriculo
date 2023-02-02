<template>
    <p>
        <b>{{topText}}</b>
        <span v-if="pillText" class="pill" :style="[BG.brown, color.grey]">
            {{pillText}}
        </span>
        <br />
        {{bottomText}}
    </p>
</template>

<script>
import { color, BG } from "@/assets/styles/paleta.json";

export default {
    data () {
        return { color, BG }
    },
    props: {
        topText: {
            type: String,
            default: ''
        },
        bottomText: {
            type: String,
            default: ''
        },
        pillText: {
            type: String,
            default: ''
        }
    }
}
</script>