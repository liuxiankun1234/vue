<template>
    <!-- <hello-world-input :user="this.name">
        {{ msg }}
    </hello-world-input> -->
    <div>
        <div id="hello_world">
            welcome to Your Vue.js App
        </div>
        
        <!-- <component-sss :name="this.a"></component-sss> -->
        <!-- <component-b :firstName="this.b" @modify="modify"></component-b> -->

        <!-- <component-c class="a1" data-component-name="component-c"></component-c> -->
        <!-- <component-c></component-c> -->
        <!-- <ComponentC/> -->
        <!-- <component-d v-model="checked" :name="msg" @change="changeCheckbox"/> -->
        <component-f :name.sync="msg"/>


        <br>
        <br>
        <br>
        <h3>component-mixin</h3>
        <component-mixin/>
        
        <br>
        <br>
        <br>
        <h3>component-slot</h3>
        <!-- <ComponentSlot>
            <template #header="{bookInfo}">
                title {{bookInfo.name}}
            </template>
            <template #default="{bookInfo: {name, price=12}}">
                title 书籍名称{{name}} price: {{price}}
            </template>
            <template #footer>
                ComponentSlot!!!    
            </template>
        </ComponentSlot> -->



        <BaseInputText
            v-model="newTodoText"
            placeholder="New todo"
            @keydown.enter="addTodo"
        />
    </div>
    
</template>
<script>
import HelloWorldInput from './HelloWordInput.vue'
import ComponentB from './ComponentB.vue'
import ComponentC from './ComponentC.vue'
import ComponentD from './ComponentD.vue'
import ComponentF from './ComponentF.vue'
import ComponentSlot from './ComponentSlot.vue'
import ComponentMixin from './ComponentMixin.vue'
import BaseInputText from './ComponentInput.vue'

export default {
    name: 'HelloWorld',
    components: { HelloWorldInput, ComponentB, ComponentD, ComponentF, ComponentSlot, ComponentMixin, BaseInputText },
    data () {
        return {
            newTodoText: "111",
            checked: true,
            a: 'A',
            b: 'success',
            user: {
                name: '123'
            },
            msg: 'Welcome to Your Vue.js App'
        }
    },
    methods: {
        addTodo(aa) {
            console.log('addTodo', this.newTodoText)
        },
        changeCheckbox(checked) {
            console.log(this.checked, checked)
        },
        handleClickParent() {
            // console.log('handleClickParent')
        },
        handleClickSon(e) {
            console.log(this)
        },
        changeInputValue(v) {
            console.log(v, this.user.name)
        },
        modify() {
            this.b = 'warning'
        }
    },
    created(){
        console.log('created~~~~~~~~~~~~~~~~~~')      
    },
    mounted() {
        console.log('mounted~~~~~~~~~~~~~~~~~~')   
    },
    beforeUpdate() {
        console.log('beforeUpdate~~~~~~~~~~~~~~~~~~~~~~')
    },
    watch: {
        checked(checked) {
            console.log(checked)
        },
        msg(value) {
            console.log(1111111111, value)
        }
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
