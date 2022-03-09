<template>
  <div>
    <v-card ref="form" width="500px" height="330px" class="mx-auto mt-16">
      <v-card-title >login <i class="ml-3">{{ errorMessage }}</i></v-card-title>
      <v-card-text>
        <v-text-field
          label="login" v-model="addName"
          placeholder="input login" outlined dense
          :rules="nameRules" :counter="15">
        </v-text-field>
        <v-text-field
          :append-icon="show ? 'mdi-eye' : 'mdi-eye-off'"
          label="Password" v-model="password"
          placeholder="input password" outlined dense
          :rules="lastNameRUles" :counter="10"
          @click:append="show = !show" :type="show ? 'text' : 'password'">
        </v-text-field>
        <v-checkbox v-model="Disabled"
          color="blue accent-2" label="Do you agree?"
          class="ma-0">
        </v-checkbox>
        <div class="btns">
          <v-btn text @click="reset">Clear</v-btn>
          <v-btn text :disabled= "!Disabled" @click="openPage">submit</v-btn>
        </div>
      </v-card-text>
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
      nameRules: [v => !!v || 'bu joyni to\'ldiring',
        v => (!!v && v.length <= 15) || '15tagacha belgidan foydalanishingiz mumkin',
        v => (!!v && v.length >= 4) || '4tadan ko\'p belgidan foydalanishingiz kerak'
      ],
      lastNameRUles: [
        v => !!v || 'bu joyni to\'ldiring',
        v => (!!v && v.length <= 10) || '10tagacha belgidan foydalanishingiz mumkin',
        v => (!!v && v.length >= 4) || '4tadan ko\'p belgidan foydalanishingiz kerak'
      ]
    }
  },
  methods: {
    openPage () {
      if (this.password === 'salom') {
        this.errorMessage = ''
        this.$router.push({ name: 'about' })
      } else {
        this.errorMessage = 'Xato!'
      }
      this.Disabled = false
    },
    reset () {
      this.addName = ''
      this.password = ''
      this.Disabled = false
      this.$refs.form.reset()
    }
  }
}

</script>
