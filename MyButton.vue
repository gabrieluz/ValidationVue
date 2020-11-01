<template>
    <button 
        :id="name"
        :style="{background, color}"
        :disabled="disabled"
    >
        {{name}}
    </button>
</template>

<script>
export default {
    props:{
        name:{
            type:String,
            required:true
        },
        color:{
            type:String
        },
        background:{
            type:String
        },
        disabled:{
            type: Boolean
        }
    }
}
</script>

<style scoped>
button:disabled{
    opacity: 0.5;
}
button{
    background: none;
    color: none;
    border: none;
    border-radius: 5px;
    padding: 10px 40px;
    font-size: 16px;
    cursor: pointer;
    
}
button:hover{
    filter: brightness(125%);
}
</style>