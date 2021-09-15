<template>
  <v-container style="">
    <v-form>
      <h1>кАкОй ЛиНуКс тЕбЕ нУжЕн?</h1>
      <p>ЭтОт тЕсТ оПрЕдЕлИт ЛиНуКс ДлЯ вАс</p>
      <h3>СОБИРАЕТЕСЬ ЛИ ВЫ ИСПОЛЬЗОВАТЬ ЛИНУКС ДЛЯ ВЗЛОМОВ????????</h3>
      <v-checkbox
          v-model="selected"
          label="Да"
          value="hack"
      ></v-checkbox>
      <h3>ВЫ ОПЫТНЫЙ ПРОГРАММИСТ?????????</h3>
      <v-checkbox
          v-model="selected"
          label="Да"
          value="coder"
      ></v-checkbox>
      <h3>ВЫ СОБИРАЕТЕСЬ ИСПОЛЬЗОВАТЬ ЛИНУКС ДЛЯ СЕРВЕРА ИЛИ ВМЕСТО ВИНДОУС??????</h3>
      <v-checkbox
          v-model="selected"
          label="Для Сервера"
          value="server"
      ></v-checkbox>
      <v-checkbox
          v-model="selected"
          label="Вместо Виндоус"
          value="no_windows"
      ></v-checkbox>
      <h3>ВАМ НУЖНА ПРОСТОТА ИСПОЛЬЛЗОВАНИЯ??????</h3>
      <v-checkbox
          v-model="selected"
          label="Да"
          value="easy"
      ></v-checkbox>
      <h3>ВАМ НУЖЕН КРАСИВЫЙ ЛИНУКС?????</h3>
      <v-checkbox
          v-model="selected"
          label="Да"
          value="beautiful"
      ></v-checkbox>
      <h3>ВЫ СОБИРАЕТЕСЬ ИГРАТЬ НА ЛИНУКСЕ??????</h3>
      <v-checkbox
          v-model="selected"
          label="Да"
          value="gaming"
      ></v-checkbox>
      <v-btn :to="check()">УзНаТь ПоДхОдЯщИй дЛя ВаС ЛинУкС</v-btn>
    </v-form>
  </v-container>
</template>

<script>
  export default {
    name: 'Home',
    data () {
      return {
        selected: []
      }
    },
    methods: {
      check() {
        var string_for_url = '/result?attributes='
        for (let i in this.selected) {
          string_for_url += `${this.selected[i]},`
        }
        return string_for_url
      }
    }
  }
</script>
