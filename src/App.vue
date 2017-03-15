<template>
    <div id="app">
        <hello></hello>
    </div>
</template>

<script>
    import Hello from './components/Hello.vue'

    export default {
        name: 'app',
        components: {
            Hello
        },
        created() {
            this.getSession()
        },
        methods: {
            getSession() {
                this.$http.get('http://core-web-api.herokuapp.com/api/session')
                    .then(
                        (response) => {
                            console.log(response)
                        },
                        (error) => {
                            console.warn(error)
                        }
                    )
            }
        }
    }
</script>
