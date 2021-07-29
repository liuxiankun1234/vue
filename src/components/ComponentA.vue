<template>
    <div>
        {{name}}
    </div>
</template>
<script>
export default {
    props: {
        name: {
            type: String,
            required: true
        }
    },
    created() {
        console.log(`A created~~~~~~~~~~~~~~~~~~~~`)
    },
    mounted() {
        console.log(`A mounted~~~~~~~~~~~~~~~~~~~~`)
    },
    data () {
        return {
            user: {
                name: '123'
            },
            msg: 'Welcome to Your Vue.js App'
        }
    }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
