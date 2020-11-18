<template>
   <div>
         <b-container class="bv-example-row">
                <b-row class="text-center">
                <b-col></b-col>
                <b-col md="8">
                <br>
                <AddQuestions />
                <QuestionList v-bind:questions="ListOfQuestions" v-on:delete-question="deleteQuestion"/>
                </b-col>
                <b-col></b-col>
            </b-row>
            </b-container>
   </div>
</template>

<script>
import AddQuestions from './AddQuestions'
import QuestionList from './QuestionList'

export default {

   name: "EditQuestions",
   props: ["ListOfQuestions"],
   components:{
      AddQuestions,
      QuestionList
   },

   methods:{
         deleteQuestion(question){
            this.$emit('delete-question', question.pos)
         }
   }
}
</script>

<style scoped>

</style>