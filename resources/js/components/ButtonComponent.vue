<template>
    <button type="button" @click="buttonClick" :class="color">{{ text }}</button>
</template>

<script>
export default ({
    props:{
        text:{
            type: String,
            default: ""
        },
        color:{
            type: String,
            default: ""
        }
    },
    methods:{
        buttonClick(){
            this.$emit('emitClick')
        }
    }
})
</script>

<style>
button {
  background-color: rgb(0, 102, 255);
  color: white;
  padding: 10px 25px;
  border: none;
  border-radius: 10px;
  cursor: pointer;
}
.red{
  background-color: rgb(255, 0, 60);
}

.green{
  background-color: rgba(5, 135, 1, 0.764);
}

.grey{
  background-color: rgb(97, 95, 96);
}

</style>