<template>
  <div>
    <v-card width="460px" height="480px" class="mx-auto mt-16 pa-3 rounded-lg grey lighten-5">
      <v-card-title class="py-2 text1">Авторизация</v-card-title>
      <div class="about">{{ errorMessage }} </div>
      <p class="mx-8 pt-1">Войдите в свой аккаунт, чтобы продолжить.</p>
      <v-card-text>
        <div class="text2">ИМЯ ПОЛЬЗОВАТЕЛЯ</div>
        <v-text-field
          class="pb-2"
          label="количество" v-model="addName"
          placeholder="998 xxx xx xx" outlined dense
          :rules="nameRules" :counter="15">
        </v-text-field>
        <span class="text2">ПАРОЛЬ</span>
        <span class="text2 float-right"> <a href="http://gmail.com">Забыли пароль?</a></span>
        <v-text-field
          :append-icon="show ? 'mdi-eye' : 'mdi-eye-off'"
          label="Пароль" v-model="password"
          placeholder="input password" outlined dense
          :rules="lastNameRUles" :counter="10"
          @click:append="show = !show" :type="show ? 'text' : 'password'">
        </v-text-field>
        <v-checkbox v-model="Disabled"
          color="blue accent-2" label="Do you agree?"
          class="checkbox" >
        </v-checkbox>
        <div class="btns">
          <v-btn text @click="reset" color="primary">очистить</v-btn>
          <v-btn text :disabled= "!Disabled" @click="openPage" color="primary">Войти</v-btn>
        </div>
      </v-card-text>
      <div class="py-10 px-5">
        <p class="text2">Нет аккаунта ? <a href="http://gmail.com">Зарегистрируйтесь</a></p>
      </div>
    </v-card>
  </div>
</template>

<script>

export default {
  name: 'HomeView',
  data () {
    return {
      errorMessage: '',
      valid: true,
      show: false,
      addName: '',
      password: '',
      Disabled: false,
      nameRules: [v => !!v || 'заполнить это пространство',
        v => (!!v && v.length <= 15) || 'Вы можете использовать до 15 символов',
        v => (!!v && v.length >= 4) || 'напишите полностью'
      ],
      lastNameRUles: [
        v => !!v || 'заполнить это пространство',
        v => (!!v && v.length <= 10) || 'Вы можете использовать до 10 символов',
        v => (!!v && v.length >= 4) || 'Вы должны использовать более 4 символов'
      ]
    }
  },
  methods: {
    openPage () {
      if (this.password === 'salom' && this.addName === '998900000000') {
        this.errorMessage = ''
        this.$router.push({ name: 'about' })
      } else {
        this.errorMessage = 'Неправильный логин или пароль!'
      }
      this.Disabled = false
    },
    reset () {
      this.addName = ''
      this.password = ''
      this.Disabled = false
      this.errorMessage = ''
    }
  }
}

</script>

<style scoped>
  .text1 {
    margin-left: 94px;
    font-size: x-large;
    opacity: 0.7;
  }
  .checkbox {
    max-width: 160px;
  }
  .btns {
    float: right;
  }
  .about {
    position: absolute;
    text-align: center;
    width: 400px;
    margin-top: 26px;
    color: rgb(245, 20, 20);
  }
  .text2 {
    font-size: 5px;
  }
</style>
