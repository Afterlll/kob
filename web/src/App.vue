<template>
  <h1>bot_name : {{ bot_name }}</h1>
  <h1>bot_age : {{ bot_age }}</h1>
  <router-view/>
</template>

<script>
import $ from "jquery";
import { ref } from 'vue';
export default {
  name : 'App',
  setup: () => {
    let bot_name = ref("")
    let bot_age = ref("")

    // 获取数据
    $.ajax({
      url : 'http://localhost:3000/pk/getBotInfo',
      type : 'GET',
      success : resp => {
        bot_name.value = resp.bot_name
        bot_age.value = resp.bot_age 
      }
    })

    return { 
      bot_name, 
      bot_age
    }
  }
}

</script>


<style>
</style>
