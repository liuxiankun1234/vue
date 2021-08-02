<template>
    <div>
        <div v-on="listener">
            <input type="text" class="input" :value="value"/>
        </div>
        <input type="text" class="input" :value="value"/>
    </div>
</template>

<script>
export default {
    name: 'component-input',
    data() {
        return {
        }
    },
    props: {
        value: {
            type: String,
            default: ''
        }
    },
    computed: {
        listener() {
            return {
                // Pass all component listeners directly to input
                ...this.$listeners,
                // Override input listener to work with v-model
                input: (event) => this.$emit('input', event.target.value)
            }
        }
    },
    created() {
        console.log('------------------>', this)
    }
};
</script>

<style scoped>

.input {
  width: 100%;
  padding: 8px 10px;
}
</style>
