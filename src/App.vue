<template>
    <div class="container">
        <div class="row">
            <div class="col-xs-12 col-sm-8 col-sm-offset-2 col-md-6 col-md-offset-3">
                <div class="form-group">
                    <label>UserName</label>
                    <input class ="form-control" type="text" v-model = "user.username">
                </div>
                <div class="form-group">
                    <label>mail</label>
                    <input class ="form-control" type="text" v-model = "user.mail">
                </div>
                <button class="btn btn-primary" @click="submit">Submit</button>
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        data() {
            return {
                user: {
                    username: '',
                    mail: ''

                }
            };
        },
        methods: {
            submit(){
                console.log(this.user);
            }
        },
        
    }
</script>

<style>
</style>
