<template>
    <div class="component-slot">
        <header>
            header: <slot name="header" :bookInfo="bookInfo">>default component header</slot>
        </header>
        <main>
            main: <slot name="default" :bookInfo="bookInfo">default component main</slot>
        </main>
        <footer>
            main: <slot name="footer">default component footer</slot>
        </footer>
    </div>
</template>
<script>
export default {
    name: 'component-f',
    props: {
       
    },
    data() {
        return {
            bookInfo: {
                name: '这个杀手不凉'
            }
        }
    },
    methods: {
       
    },
    created() {
        console.log(this.$parent.a)
    }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
