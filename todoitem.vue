<template>
  <li @click="handdelete"><a>{{content}}</a></li>
</template>

<script>
  export default{
    props:['content','index'],
    methods: {
    handdelete(){
        this.$emit('delete',this.index)
      }
    }
  }
</script>


<style scoped>
  li{
    margin-top: 10px;
  }
  li a{
    background: yellow;
    cursor: pointer;
  }
</style>
