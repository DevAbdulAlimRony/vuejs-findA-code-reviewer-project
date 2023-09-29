<script>
    export default{
        props: {
            mode: {
                type: String,
                required: false,
                default: null
            },
            link: {
                type: Boolean,
                required: false,
                default: false
            },

            to: {
                type: String,
                required: false,
                default: '/'
            }
        }
    }
</script>

<template>
    <button v-if="!link" :class="mode">
        <slot></slot>
    </button>

    <router-link v-else :to="to" :class="mode">
        <slot></slot>
    </router-link>
</template>