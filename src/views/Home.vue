<template>
  <div>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png">
    <HelloWorld v-bind:msg="$t('homeDescription')"/>
  </div>
  <h4>{{answer}}</h4>
  <div class="container">
  <form class="form-inline justify-content-center align-items-start" @submit.prevent="getAnswer()">
    <div class="form-group align-items-start justify-content-center row">
      <label for="question">{{$t('question')}}</label>
      <textarea id="question" class="form-control mr-5 ml-5 mb-3" required rows="10" cols="40"></textarea>
      <button class="btn btn-primary" type="submit">{{$t('ask')}}</button>
    </div>
  </form>
  </div>
  </div>
</template>
<style scoped lang="scss">
textarea {
  resize: none;
}
</style>
<script lang="ts">
import { Options, Vue } from 'vue-class-component'
import HelloWorld from '@/components/HelloWorld.vue'
import { messages } from '@/messages' // @ is an alias to /src

@Options({
  created () {
    this.$watch(this.locale, () => {
      this.answer = ''
    })
  },
  components: {
    HelloWorld
  },
  data: function () {
    return {
      answer: '',
      locale: function () {
        return this.$i18n.locale
      }
    }
  },
  methods: {
    getAnswer () {
      const { answers } = messages[this.$i18n.locale]
      this.answer = answers[Math.floor(Math.random() * answers.length)]
    }
  }
})
export default class Home extends Vue {}
</script>
