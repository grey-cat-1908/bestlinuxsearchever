<template>
  <v-container class="linux">
    <h1>Результаты</h1>
    <v-row>
      <v-col v-for="item in to_show" :key="item.name">
        <v-card
            class="mx-auto"
            max-width="344"
        >
          <v-img
              :src="item.avatar"
              height="200px"
          ></v-img>

          <v-card-title>
            {{ item.name }}
          </v-card-title>

          <v-card-text>
            {{ item.text }}
          </v-card-text>


          <v-card-actions>
            <v-btn
                color="orange lighten-2"
                text
                :href="item.url"
            >
              пОдРоБнЕе
            </v-btn>
          </v-card-actions>
        </v-card>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
import linuxes_file from '@/assets/linuxes.json'

export default {
  name: 'Home',
  data () {
    return {
      selected: this.$route.query.attributes,
      to_show: [],
      update: false
    }
  },
  created () {
    this.selected = this.selected.split(',')
    this.selected.pop()
    for (let i in linuxes_file) {
        for (let j in this.selected) {
          if (linuxes_file[i].tags.includes(this.selected[j])) {
            this.update = true
          }
          else {
            this.update = false
            break;
          }
      }
      if (this.update === true) {
        this.to_show.push(linuxes_file[i])
      }
    }
  }
}
</script>
