<template>
  <ul class="data-list">
    <li v-for="item in items">{{item.text}}: {{item.value}}</li>
  </ul>
</template>

<script>
export default {
data() {
  return {
    items: []
  }
},
mounted() {
  this.items = JSON.parse(localStorage.getItem('items'))
}
}
</script>

<style scoped>
.data-list {
width: 300px;
position: absolute;
top: 20%;
left: calc(50% - 150px);
background: #fff;
border: 5px solid tomato;
border-radius: 20px;
}
</style>

