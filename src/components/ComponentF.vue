<template>
    <div class="component-f">
        {{name}}
        <button @click="modify">修改</button>
        <transition name="fade">
            <p v-if="show">hello</p>
        </transition>
    </div>
</template>
<script>
export default {
    name: 'component-f',
    props: {
        name: String,
        require: true
    },
    data() {
        return {
            show: true
        }
    },
    methods: {
        modify() {
            this.show = !this.show;
            this.$emit('update:name', this.name.toUpperCase())
        }
    }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.fade-enter-active, .fade-leave-active {
  transition: opacity .5s;
}
.fade-enter, .fade-leave-to /* .fade-leave-active below version 2.1.8 */ {
  opacity: 0;
}
</style>
