<template>
    <button @click="toggle($event)" :class="classes">
        <span class="hamburger-box">
            <span class="hamburger-inner"></span>
        </span>
    </button>
</template>

<script>
    import VueTypes from "vue-types"
    export default {
        /* data(){
            return {
                opened: false,
            };
        }, */
        props: {
            opened: VueTypes.bool.def(false),
        },
        computed: {
            classes(){
                const cls = "hamburger hamburger--emphatic";
                return this.opened ? `${cls} is-active` : cls;
            }
        },
        methods: {
            toggle(e){
                /* this.opened = !this.opened;
                const eventName = this.opened ? "open" : "close"; */
                const eventName = this.opened ? "close" : "open";
                this.$emit(eventName, e);
            }
        }
    }
</script>


<style lang="scss" scoped>
</style>