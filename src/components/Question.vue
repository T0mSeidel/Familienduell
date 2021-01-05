<template>
  <div class="question-item">
    <b-container>
      <b-row>
        <b-col cols="1">
          <b-form-spinbutton
            id="inline-form-input-position"
            v-model="question.pos"
            min="1"
            size="sm"
            vertical
          ></b-form-spinbutton>
        </b-col>

        <b-col cols="10">
          <b-card no-body class="mb-1">
            <b-card-header header-tag="header" class="p-1" role="tab">
              <b-form inline>
                <b-button
                  block
                  v-b-toggle="'accordion-' + question.pos"
                  variant="warning"
                  >{{ question.title }}</b-button
                >
              </b-form>
            </b-card-header>
            <b-collapse
              :id="`accordion-${question.pos}`"
              accordion="my-accordion"
              role="tabpanel"
            >
              <b-card-body>
                <b-form-group>
                  <b-form-input
                    size="sm"
                    v-model="question.title"
                  ></b-form-input>

                  <br />

                  <b-form inline>
                    <b-form-group
                      label-cols-sm="2"
                      label="Antwort Platz 1"
                      label-for="inline-a1"
                    >
                      <b-input
                        id="inline-a1"
                        size="sm"
                        v-model="question.antwort1"
                        placeholder="Anzahl der Antwort"
                      >
                      </b-input>
                      <b-input
                        antwort1_bezeichnung="inline-a1-bezeichnung"
                        size="sm"
                        v-model="question.antwort1_bezeichnung"
                        placeholder="Antwort hier eingeben"
                      >
                      </b-input>
                    </b-form-group>

                    <b-form-group
                      label-cols-sm="2"
                      label="Antwort Platz 2"
                      label-for="inline-a2"
                    >
                      <b-input
                        id="inline-a2"
                        size="sm"
                        v-model="question.antwort2"
                        placeholder="Anzahl der Antwort"
                      >
                      </b-input>
                      <b-input
                        antwort2_bezeichnung="inline-a2-bezeichnung"
                        size="sm"
                        v-model="question.antwort2_bezeichnung"
                        placeholder="Antwort hier eingeben"
                      >
                      </b-input>
                    </b-form-group>

                    <b-form-group
                      label-cols-sm="2"
                      label="Antwort Platz 3"
                      label-for="inline-a3"
                    >
                      <b-input
                        id="inline-a3"
                        size="sm"
                        v-model="question.antwort3"
                        placeholder="Anzahl der Antwort"
                      >
                      </b-input>
                      <b-input
                        antwort3_bezeichnung="inline-a3-bezeichnung"
                        size="sm"
                        v-model="question.antwort3_bezeichnung"
                        placeholder="Antwort hier eingeben"
                      >
                      </b-input>
                    </b-form-group>

                    <b-form-group
                      label-cols-sm="2"
                      label="Antwort Platz 4"
                      label-for="inline-a4"
                    >
                      <b-input
                        id="inline-a4"
                        size="sm"
                        v-model="question.antwort4"
                        placeholder="Anzahl der Antwort"
                      >
                      </b-input>
                      <b-input
                        size="sm"
                        antwort4_bezeichnung="inline-a4-bezeichnung"
                        v-model="question.antwort4_bezeichnung"
                        placeholder="Antwort hier eingeben"
                      >
                      </b-input>
                    </b-form-group>

                    <b-form-group
                      label-cols-sm="2"
                      label="Antwort Platz 5"
                      label-for="inline-a5"
                    >
                      <b-input
                        id="inline-a5"
                        size="sm"
                        v-model="question.antwort5"
                        placeholder="Anzahl der Antwort"
                      >
                      </b-input>
                      <b-input
                        antwort5_bezeichnung="inline-a5-bezeichnung"
                        size="sm"
                        v-model="question.antwort5_bezeichnung"
                        placeholder="Antwort hier eingeben"
                      >
                      </b-input>
                    </b-form-group>
                  </b-form>
                  <br />
                </b-form-group>
              </b-card-body>
            </b-collapse>
          </b-card>
        </b-col>
        <b-col cols="1">
          <button
            type="button"
            class="close"
            aria-label="Close"
            @click="$emit('delete-question', question)"
          >
            <span aria-hidden="true">&times;</span>
          </button>
        </b-col>
      </b-row>
    </b-container>
  </div>
</template>

<script>
export default {
  name: "Question",
  props: ["question"],
  methods: {},

  data() {
    return {};
  },
};
</script>

<style scoped>
.question-item {
  padding: 8px;
  border-bottom: 1px #ccc solid;
}
</style>