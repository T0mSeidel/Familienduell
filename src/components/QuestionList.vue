<template>
  <div>
    <div v-bind:key="question.pos" v-for="question in questions">
      <Question
        v-bind:question="question"
        v-on:delete-question="$emit('delete-question', question)"
      />
    </div>
  </div>
</template>

<script>
import Question from "./Question";

export default {
  name: "QuestionList",
  components: {
    Question,
  },
  props: ["questions"],
};
</script>

<style scoped>
</style>