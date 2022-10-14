<template>
    <p>
        <img class="icon" :src="`/curriculo/img/${icon}-icon.png`">
        <span>
            <slot />
        </span>
    </p>
</template>

<script>
export default {
    props: {
        icon: {
            type: String,
            default: '',
            required: true
        }
    }
}
</script>

<style scoped>
    .icon {
        width: 20px;
        height: 20px;
        filter: invert(1);
        opacity: .7;
        margin-right: 5px;
    }

    p {
        display: flex;
    }
</style>