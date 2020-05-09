<template>
  <div class="container">
    <frontHeader></frontHeader>
  </div>
</template>

<script>

  import frontHeader from "./components/header";
  export default {
    name: 'front_index',
    components:{frontHeader},
    data() {
      return {
        dialogVisible:false,
        form: {
          text: '',
        },
      }
    },
    methods:{
      login:function(){}
    },

    computed: {
      message() {
        return 'The webmaster said that you can not enter this page...'
      }
    }
  }
</script>

<style lang="scss" scoped>

  .container{
    display: flex;
    flex-direction: column;
  }




  .main{
    display: flex;
    padding-top: 80px;
    flex-shrink: 0;
    height: 100%;
    flex-direction: column;
    justify-content: center;
    align-items: center;
  }

</style>
