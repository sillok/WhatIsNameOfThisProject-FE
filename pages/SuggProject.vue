<template>
  <v-col>
    <v-row>
      <v-col class="text-center">
          <v-textarea
            name="input-7-1"
            v-model="item"
            label="프로젝트의 컨셉을 입력 해 주십시오"
          ></v-textarea>
      </v-col>
    </v-row>
    <v-row>
      <v-col class="text-center">
        <v-btn
          :loading="loading"
          :disabled="loading"
          color="blue-grey"
          class="ma-2 white--text"
          fab
          @click="sendName"
          style="float: right;"
        >
          <v-icon dark>
            mdi-send
          </v-icon>
        </v-btn>
      </v-col>
    </v-row>
    <v-row v-if="response">
      <v-col>
        <v-card>
        <v-card-title class="headline">
          흠... 제 생각에는요...
        </v-card-title>
        <v-card-text>
          {{ result }}
        </v-card-text>
      </v-card>
      </v-col>
    </v-row>
  </v-col>
</template>

<script>

import axios from 'axios'

export default {
  name: 'SuggProjectPage',
  data() {
    return {
      response: false,
      loading: false,
      result: "대충응답대충응답대충응답대충응답대충응답",
      item: "",
    }
  },
  methods: {
    sendName: function() {
      this.loading = true
      this.response = false
      let it = this
      if(this.item == '') {
        alert("컨셉을 입력해 주십시오")
        this.loading = false
        return
      }
      axios.post('http://172.30.1.85:8000/fastname', {
        item: this.item,
      }, {
        timeout: 5000,
      })
      .then(function (response) {
        it.response = true
        it.loading = false
        it.result = response.data.answer
      })
      .catch(function (error) {
        it.response = false
        it.loading = false
        alert(error.data.detail)
      })
    }
  }

}
</script>
