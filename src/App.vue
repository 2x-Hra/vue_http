<template>
    <div class="container">
        <div class="row">
            <div class="col-xs-12 col-sm-8 col-sm-offset-2 col-md-6 col-md-offset-3">
                <h1>HTTP</h1>
                <div class="form-group">
                    <label>UserName</label>
                    <input class ="form-control" type="text" v-model = "user.username">
                </div>
                <div class="form-group">
                    <label>mail</label>
                    <input class ="form-control" type="text" v-model = "user.mail">
                </div>
                <button class="btn btn-primary" @click="submit">Submit</button>

                <hr>

                <button class="btn btn-primary" @click="getData">Get Data</button>
                <ul class="list-group">
                    <li class="list-group-item" v-for="u in users" :key="u"> {{u.username}} - {{u.mail}}</li>

                </ul>
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
                this.$http.post('',this.user)
                    .then(response => {
                        console.log(response);
                    },error => {
                        console.log(error);
                    }); 
            },
            getData(){
                this.$http.get('')
                 .then(response => {
                    return response.json();                
                 })
                 .then(data =>{
                     const resultArray = [];
                     for(let key in data){
                         resultArray.push(data[key]);
                        }
                        this.users = resultArray;
                 });
            }
        },
        
    }
</script>

<style>
</style>
