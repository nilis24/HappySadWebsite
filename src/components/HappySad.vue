<template>
  <div id="background" class="parent red" v-on:click="HandleState">
    <span id="face" class="text unselectable">:(</span>
  </div>
</template>

<script>
  let val = ":(";
  export default {
    name: 'HappySad',
    methods: {
      HandleState: function() {
        if(val == ":(") {
          val = ":)"
          document.getElementById("face").innerHTML = ":)";
          document.getElementById("background").classList.remove("red");
          document.getElementById("background").classList.add("green");
        } else {
          val = ":("
          document.getElementById("face").innerHTML = ":(";
          document.getElementById("background").classList.remove("green");
          document.getElementById("background").classList.add("red");
        }
      }
    },
  }
</script>

<style scoped>
  .parent {
    display: flex;
    width: 100vw;
    height: 100vh;
    justify-content: center;
    align-items: center;
  }

  .green {
    background-color: #23CE6B;
  }

  .red {
    background-color: #FB3640;
  }

  .text {
    font-family: Arial, Helvetica, sans-serif;
    font-size: 10em;
    font-weight: bold;
  }

  .unselectable {
    -moz-user-select: none;
    -khtml-user-select: none;
    -webkit-user-select: none;
    -ms-user-select: none;
    user-select: none;
  }
</style>
