<template>
    <form @submit.prevent="submit" class="form">
        <my-input
            name="username"
            :rules="{required: true, min: 5}"
            :value="username.value"
            @update="update"
            type="text"
        />
        <my-input
            name="password"
            :rules="{required: true, min: 10}"
            :value="password.value"
            @update="update"
            type="password"
        />
        <my-button 
            name="Button"
            color="white"
            background="darkslateblue"
            :disabled="!valid"
        />
    </form>
</template>

<script>

import MyButton from './MyButton.vue'
import MyInput from './MyInput.vue'

export default {
    components:{
        MyButton,
        MyInput
    },
    data(){
        return{
            username:{
                value:'',
                valid:false
            },
            password:{
                value:'',
                valid:false
            }
        }
    },
    computed:{
        valid(){
            return this.username.valid && this.password.valid
        }
    },
    methods:{
        submit($evt){
            console.log('Submit')
        },
        update(payload){
            //this[payload.name.toLowerCase()].value = payload.value
            this[payload.name.toLowerCase()] = {
                value: payload.value,
                valid: payload.valid
            }
        }
    }
}
</script>

<style scoped>
body{
    font-family: Arial;
}
.form{
    max-width: 400px;
    width: 50%;
}
</style>