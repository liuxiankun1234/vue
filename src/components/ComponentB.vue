<template>
    <div>
        {{firstName}} {{name}}
        <button @click="modify">修改B值</button>
    </div>
</template>
<script>
export default {
    name: 'B',
    props: {
        name: {
            type: Object,
            default: {
                a: '12'
            }
        },
        firstName: {
            validator: function (value) {
                // 这个值必须匹配下列字符串中的一个
                return ['success', 'warning', 'danger'].indexOf(value) !== -1
            }
        }
    },
    data () {
        return {
           
        }
    },
    methods: {
        modify() {
            this.$emit('modify')
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
