<template>
    <div class="component-mixin">
        <div v-inner:[top]="200"></div>
        <input type="text" v-focus>
        {{bookInfo.bookName}}
    </div>
</template>
<script>
const mixin = {
    data() {
        return {
            bookInfo: {
                bookName: '这个杀手不凉',
                price: 12
            }
        }
    }
}
export default {
    name: 'component-mixin',
    mixins: [mixin],
    props: {
       
    },
    data() {
        return {
            top: 'top'
        }
    },
    directives: {
        inner: {
            bind: function(el, context, vnode) {
                console.log(el, context, vnode)
                el.innerHTML = 'AAAAA'
                el.style.position = 'fixed'
                console.log(context.arg, context.value)
                el.style[context.arg] = context.value + 'px'
            }
        },
        focus: {
            // 被绑定的元素插入到父节点时调用。
            inserted: function(el) {
                el.focus();
            },
            update: function() {
                console.log('%c focus addListener update %c', red)
            }
        }
    },
    methods: {
       
    }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
