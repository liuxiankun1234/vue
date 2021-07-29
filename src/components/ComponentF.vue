<template>
    <div class="component-f">
        {{name}}
        <button @click="modify">修改</button>
    </div>
</template>
<script>
export default {
    name: 'component-f',
    props: {
        name: String,
        require: true
    },
    methods: {
        modify() {
            this.$emit('update:name', this.name.toUpperCase())
        }
    }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
