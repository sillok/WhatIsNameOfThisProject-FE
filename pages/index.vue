<template>
  <v-row justify="center" align="center">
    <v-col cols="12" sm="8" md="6">
      <v-card class="logo py-4 d-flex justify-center">
        <ThinkingFace />
      </v-card>
      <v-card>
        <v-card-title class="headline">
          Hmm...
        </v-card-title>
        <v-card-text>
          <p>개발할 때 프로젝트, 함수, 변수 등의 이름 때문에 고민한 적 있으신가요?</p>
          <p>AI가 당신의 작명을 대신 해 드립니다!</p>
          
          <hr class="my-3">
          
        </v-card-text>
        <v-card-actions>
          <v-spacer />
          <v-btn
            color="primary"
            nuxt
            to="/SuggProject"
          >
            시작하기
          </v-btn>
        </v-card-actions>
      </v-card>
    </v-col>
  </v-row>
</template>

<script>
export default {
  name: 'IndexPage'
}
</script>
