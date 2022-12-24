<template>
  <v-col>
    <v-row>
      <v-col class="text-center">
          <v-textarea
            name="input-7-1"
            label="프로젝트의 컨셉을 입력 해 주십시오"
            hint="대충사용방법대충사용방법대충사용방법대충사용방법대충사용방법"
          ></v-textarea>
      </v-col>
    </v-row>
    <v-row>
      <v-col class="text-center">
        <v-btn
          :loading="loading5"
          :disabled="loading5"
          color="blue-grey"
          class="ma-2 white--text"
          fab
          @click="loader = 'loading5'"
          style="float: right;"
        >
          <v-icon dark>
            mdi-send
          </v-icon>
        </v-btn>
      </v-col>
    </v-row>
  </v-col>
</template>

<script>
export default {
  name: 'InspirePage'
}
</script>
