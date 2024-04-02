<template>
  <div v-if="isOpen" class="popup__bg" @click="close">
    <form class="popup" @click.stop="open">
      <h1 class="title">Анкета</h1>
      <label v-for="item in items">
        <input type="text" :name="item.attr" v-model="item.value"/>
        <div class="label__text">{{item.text}}</div>
      </label>
      <button class="send-popup" @click.stop="send">Отправить</button>
    </form>
  </div>
  <button class="open-popup" v-else @click.prevent="open">Начать</button>

</template>

<script>
export default {
  data(){
    return {
      isOpen: false,
      items: [
        {text: 'Ваше имя', attr: 'name', value: ''},
        {text: 'Ваш e-mail', attr: 'e-mail', value: ''},
        {text: 'Любимая порода собак', attr: 'favDog', value: ''},
        {text: 'Любимый цвет', attr: 'favColor', value: ''},
        {text: 'Имя любимого актера', attr: 'favActor', value: ''},
      ]
    }
  },
  methods: {
    open(){
      this.isOpen = true
    },
    close(){
      this.isOpen = false
    },
    send(){
      this.items.forEach((val)=>{
        if(val.value === ""){
          alert(`Поле "${val.text}" не заполнено`)
        }
      })
      localStorage.setItem('items', JSON.stringify(this.items))

    }
  }
}
</script>

