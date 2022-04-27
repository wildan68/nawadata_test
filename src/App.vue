<template>
  <div class="mainapp">
    <Question1/>
    <Question2/>
  </div>
</template>

<script>
import Question1 from './components/question_1.vue'
import Question2 from './components/question_2.vue'

export default {
  components: {
    Question1,
    Question2,
  }
}
</script>