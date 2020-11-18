<template>
    <div class="question-item">
        <br>
        <b-form-group>
                    <button type="button" class="close" aria-label="Close" @click="$emit('delete-question', question)">
                    <span aria-hidden="true">&times;</span>
                    </button>
                    
                    <h2> {{question.title}} </h2>

                    <br>

                    <b-form-input size="sm" v-model="question.title"></b-form-input>

                    <br>

                    <b-form inline>

                        <b-form-group 
                            label-cols-sm="2"
                            label="Position Frage"
                            label-for="inline-form-input-position"
                            >
                        <b-input id="inline-form-input-position"
                        class ="mb-2 mr-sm-2 mb-sm-0"
                        v-model="question.pos">
                        </b-input>
                        </b-form-group>

                    
                        <b-form-group 
                            label-cols-sm="2"
                            label="Antwort Platz 1"
                            label-for="inline-a1">

                            <b-input id="inline-a1"
                            class ="mb-2 mr-sm-2 mb-sm-0"
                            v-model="question.antwort1">
                            </b-input>
                        </b-form-group>

                        <b-form-group 
                            label-cols-sm="2"
                            label="Antwort Platz 2"
                            label-for="inline-a2">

                            <b-input id="inline-a2"
                            class ="mb-2 mr-sm-2 mb-sm-0"
                            v-model="question.antwort2">
                            </b-input>
                        </b-form-group>

                        <b-form-group 
                            label-cols-sm="2"
                            label="Antwort Platz 3"
                            label-for="inline-a3">

                            <b-input id="inline-a3"
                            class ="mb-2 mr-sm-2 mb-sm-0"
                            v-model="question.antwort3">
                            </b-input>
                        </b-form-group>

                        <b-form-group 
                            label-cols-sm="2"
                            label="Antwort Platz 4"
                            label-for="inline-a4">

                            <b-input id="inline-a4"
                            class ="mb-2 mr-sm-2 mb-sm-0"
                            v-model="question.antwort4">
                            </b-input>
                        </b-form-group>

                        <b-form-group 
                            label-cols-sm="2"
                            label="Antwort Platz 5"
                            label-for="inline-a5">

                            <b-input id="inline-a5"
                            class ="mb-2 mr-sm-2 mb-sm-0"
                            v-model="question.antwort5">
                            </b-input>
                        </b-form-group>
                    </b-form>
                    <br>
                </b-form-group>
        </div>
</template>

<script>
export default {
    name: "Question",
    props: ["question"],
    methods :
    {
    }
}
</script>

<style scoped>

      .question-item{
        padding: 8px;
        border-bottom: 1px #ccc solid;
    }

</style>