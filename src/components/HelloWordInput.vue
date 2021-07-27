<script>
export default {
    name: 'HelloWorld',
    props: {
        user: {
            type: String,
            required: true
        }
    },
    data () {
        return {
            innerObj: {
                a: 12
            },
            initName: this.user,
            msg: 'Welcome to Your Vue.js App'
        }
    },
    methods: {
        changeInitName() {
            this.$emit('update:user', this.initName)
        },
        handleClickParent() {
            // console.log('handleClickParent')
        },
        handleClickSon(e) {
            console.log(this)
        },
        changeInputValue(e) {
            this.$emit('input', e.target.value)
        }
    },
    render() {
        const { name } = this;
        console.log('this.$slots.default-------->', this.$slots.default)
        return (
            <div>   
                {this.$slots.default || <slot v-bind:innerObj="innerObj">默认</slot>}
            </div>
        )
    }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
