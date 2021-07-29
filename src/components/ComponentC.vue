<template>
    <div class="component-c">
        {{counter}}
        <button @click="counter++">counter++</button>
    </div>
</template>
<script>
import { data } from '../common/index.js'
export default {
    inheritAttrs: false,
    name: 'B',
    data() {
        return {
            counter: 0
        }
    },
    created() {
        console.log(`B created~~~~~~~~~~~~~~~~~~~~`)
    },
    mounted() {
        console.log(`B mounted~~~~~~~~~~~~~~~~~~~~`)
    }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
