<template>
    <div>
        <h1 v-if="show" >{{data}}</h1>
        <h1 v-else >{{msg}}</h1>
        <button v-on:click="hello('Data')">Get Hello function</button>
        <button v-on:click="displayFunction()">Toogle</button>
        <div>
            <h1>For loop in Vue Js</h1>
            <table>
                <tr>
                    <td>Id</td>
                    <td>Name</td>
                    <td>Email</td>
                </tr>
                <tr v-for="user in users" :key="user.id">
                    <td>{{user.id}}</td>
                    <td>{{user.name}}</td>
                    <td>{{user.email}}</td>
                </tr>
            </table>
        </div>
    </div>
</template>

<script>
export default {
    name: 'Home',
    props: {
        data: String,
        msg: String
    },
    methods: {
        hello(data){
            alert(data);
        },
        displayFunction(){
            this.show= !this.show;
        }
    },
    data(){
        return {
            show: false,
            users:[
                {id:1,name:'Pepe',email:'pepe@gmail.com'},
                {id:2,name:'Pepe 2',email:'pepe2@gmail.com'},
                {id:3,name:'Pepe 3',email:'pepe3@gmail.com'},
                {id:4,name:'Pepe 4',email:'pepe4@gmail.com'},
            ]
        }
    }
}
</script>