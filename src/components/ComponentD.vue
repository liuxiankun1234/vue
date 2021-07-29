<template>
    <div class="component-d">
        <input 
            type="checkbox" 
            v-bind:checked="checked"
            v-on:change="$emit('change', $event.target.checked)"
        />
        <br />
            <!-- :checked="checked" @change="change"> checkbox -->
        {{name}}
        <input type="text" v-model="name"> 
    </div>
</template>
<script>
import { data } from '../common/index.js'
export default {
    name: 'component-d',
    model: {
        prop: 'checked',
        event: 'change'
    },
    props: {
        checked: Boolean,
        name: String
    },
    created() {
        console.log(`B created~~~~~~~~~~~~~~~~~~~~`)
    },
    mounted() {
        console.log(`B mounted~~~~~~~~~~~~~~~~~~~~`)
    },
    methods: {
        change(e) {
            this.$emit('change', e.target.checked)
        }
    }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
