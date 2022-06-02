<template>
    <button v-on:click="this.increment">count is {{this.count}}</button>
    <h1>{{publishedBooksMessage}}</h1>
</template>
<script>
    export default {
        data() {
            return {
                count: 1,
                obj: {
                    name: 'John Doe',
                    books: [
                        'vue2-Advanced Guide',
                        'vue3-Advanced Guide',
                        'vue4-Advanced Guide'
                    ]
                }
            }
        },

        methods: {
            increment() {
                this.count++
            }
        },

        computed: {
            publishedBooksMessage() {
                return this.obj.books.length > 0 ? 'Yes' : 'No';
            }
        },

        // `mounted` is a lifecycle hook which we will explain later
        mounted() {
            // `this` refers to the component instance.
            console.log(this.count) // => 1

            // data can be mutated as well
            this.count = 2
        }
    }
</script>