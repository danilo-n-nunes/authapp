<template>
<div>
    <v-container>
        <v-row>
            <v-col>Nome <label><strong>{{name}}</strong></label></v-col>
            <v-col>Email <label>{{email}}</label></v-col>
            <v-col>Token</v-col>
        </v-row>
    </v-container>
</div>
  
</template>

<script>
export default {
    name: "User",
    data(){
        return {
            name: "",
            email: "",
            token: ","
        }
    },
    mounted(){
        this.get_user()
    },
    methods: {
        async get_user(){
            var token = localStorage.getItem("jwt");
            console.log(token)
            await this.$http.get("/dashboard/user",{
                headers: { Authorization: "Bearer " + token }
            }).then(response => {
                console.log(response.data.user.name)
                this.name = response.data.user.name
                this.email = response.data.user.email
                console.log(this.name+' '+this.email)
            })
        }
    }
}
</script>

<style>

</style>