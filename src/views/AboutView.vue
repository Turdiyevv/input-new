<template>
  <div class="about">
    <v-app-bar height="34">
      <v-btn small text @click="goHome"><v-icon> mdi-arrow-left</v-icon></v-btn>
    </v-app-bar>
    <v-data-table
      hide-default-footer
      v-model="selected"
      :headers="headers"
      :items="desserts"
      item-key="name"
      show-select
      class="elevation-1 ma-2">
    </v-data-table>
  </div>
</template>

<script>
export default {
  name: 'AboutView',
  data () {
    return {
      selected: [],
      headers: [
        {
          text: 'Dessert (100g serving)',
          align: 'start',
          sortable: false,
          value: 'name'
        },
        { text: 'Calories', value: 'calories' },
        { text: 'Fat (g)', value: 'fat' },
        { text: 'Carbs (g)', value: 'carbs' },
        { text: 'Protein (g)', value: 'protein' },
        { text: 'Iron (%)', value: 'iron' }
      ],
      desserts: [
        { name: 'Frozen Yogurt', calories: 159, fat: 6.0, carbs: 24, protein: 4.0, iron: '1%' },
        { name: 'Ice cream sandwich', calories: 237, fat: 9.0, carbs: 37, protein: 4.3, iron: '1%' },
        { name: 'Eclair', calories: 262, fat: 16.0, carbs: 23, protein: 6.0, iron: '7%' },
        { name: 'Cupcake', calories: 305, fat: 3.7, carbs: 67, protein: 4.3, iron: '8%' },
        { name: 'Gingerbread', calories: 356, fat: 16.0, carbs: 49, protein: 3.9, iron: '16%' },
        { name: 'jdhasi', calories: 356, fat: 16.0, carbs: 49, protein: 3.9, iron: '16%' },
        { name: 'slkacm', calories: 356, fat: 16.0, carbs: 49, protein: 3.9, iron: '16%' },
        { name: ' oqwi9', calories: 356, fat: 16.0, carbs: 49, protein: 3.9, iron: '16%' },
        { name: 'HYW', calories: 356, fat: 16.0, carbs: 49, protein: 3.9, iron: '16%' },
        { name: 'qposk', calories: 356, fat: 16.0, carbs: 49, protein: 3.9, iron: '16%' },
        { name: 'q[spl', calories: 356, fat: 16.0, carbs: 49, protein: 3.9, iron: '16%' },
        { name: '[pol]', calories: 356, fat: 16.0, carbs: 49, protein: 3.9, iron: '16%' },
        { name: ';osjdiw', calories: 356, fat: 16.0, carbs: 49, protein: 3.9, iron: '16%' },
        { name: 'poppi', calories: 356, fat: 16.0, carbs: 49, protein: 3.9, iron: '16%' },
        { name: 'poiyt', calories: 356, fat: 16.0, carbs: 49, protein: 3.9, iron: '16%' },
        { name: '[qslq]', calories: 356, fat: 16.0, carbs: 49, protein: 3.9, iron: '16%' },
        { name: ';lsqpsk', calories: 356, fat: 16.0, carbs: 49, protein: 3.9, iron: '16%' },
        { name: 'qlqpkws', calories: 356, fat: 16.0, carbs: 49, protein: 3.9, iron: '16%' },
        { name: 'eqrwe', calories: 356, fat: 16.0, carbs: 49, protein: 3.9, iron: '16%' },
        { name: 'gsyx', calories: 356, fat: 16.0, carbs: 49, protein: 3.9, iron: '16%' },
        { name: 'vshbvc', calories: 356, fat: 16.0, carbs: 49, protein: 3.9, iron: '16%' },
        { name: 'alsj', calories: 356, fat: 16.0, carbs: 49, protein: 3.9, iron: '16%' }
      ]
    }
  },
  methods: {
    goHome () {
      this.$router.push({ name: 'home' })
    }
  }
}
</script>
