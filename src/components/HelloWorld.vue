<template>
    <hello-world-input >
        {{ msg }}
    </hello-world-input>
</template>
<script>
import HelloWorldInput from './HelloWordInput.vue'
export default {
    name: 'HelloWorld',
    props: {
        name: {
            type: String,
            default: '123'
        }
    },
    data () {
        return {
            user: {
                name: '123'
            },
            msg: 'Welcome to Your Vue.js App'
        }
    },
    methods: {
        handleClickParent() {
            // console.log('handleClickParent')
        },
        handleClickSon(e) {
            console.log(this)
        },
        changeInputValue(v) {
            console.log(v, this.user.name)
        }
    },
    watch: {
        msg(value) {
            console.log(1111111111, value)
        }
    },
    components: {
        HelloWorldInput
    },  
    render() {
        const {
            user
        } = this;
        return (
            <div>
                <HelloWorldInput 
                    user={user}
                    on-input={this.changeInputValue}
                />
            </div>
        )
    }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.parent{
    width: 100px;
    height: 100px;
    background-color: red;
}
.son{
    width: 50px;
    height: 50px;
    background-color: pink;
}
</style>
