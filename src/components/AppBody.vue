<template>
  <v-container class="fill-height">
    <v-responsive
      class="align-centerfill-height mx-auto"
      width="100"
      max-width="900"
    >
      <div class="d-flex justify-center align-center">
        <img class="mx-1" height="60" src="@/assets/logo_v4.svg" />

        <h1 class="mx-1 text-h4 font-weight-bold">Timezone App</h1>
      </div>
      <div class="py-2" />

      <v-stepper mobile :items="['', '', '', '']">
        <template v-slot:item.1>
          <v-card title="Select time" flat>
            <v-text-field
              v-model="time"
              :active="modal2"
              :focused="modal2"
              prepend-icon="mdi-clock-time-four-outline"
              readonly
            >
              <v-dialog v-model="modal2" activator="parent" width="auto">
                <v-time-picker v-if="modal2" v-model="time"></v-time-picker>
              </v-dialog>
            </v-text-field>
          </v-card>
        </template>

        <template v-slot:item.2>
          <v-card title="Выбрать дату" flat>
            Lorem ipsum dolor sit amet, consectetur adipiscing elit. Donec
            ultrices sollicitudin tincidunt. Maecenas nec efficitur purus, vitae
            scelerisque tellus. Sed nec ullamcorper augue. Maecenas eleifend
            magna ut sollicitudin finibus. Vestibulum luctus placerat convallis.
            Proin urna sem, auctor quis volutpat et, vehicula a purus. Vivamus
            dignissim varius dictum. Mauris massa odio, rutrum sed elementum
            quis, congue et tortor. Vivamus id cursus quam. Cras a placerat
            velit. Vestibulum sagittis commodo pharetra. Sed arcu nunc, ornare
            non imperdiet et, pretium feugiat sapien. Vestibulum in ligula vitae
            turpis ultrices lobortis. Donec congue velit pellentesque, imperdiet
            lorem nec, mattis ex. Nulla in blandit velit. Vestibulum non odio
            sed eros rutrum faucibus. Vestibulum tristique tellus eu elementum
            cursus.
          </v-card>
        </template>

        <template v-slot:item.3>
          <v-card title="Выбрать время" flat>
            <br />asfaf<br />asfaf<br />asfaf<br />asfaf
          </v-card>
        </template>

        <template v-slot:item.4>
          <v-card title="Подтвердить выбор" flat>
            <br />asfaf<br />asfaf<br />asfaf<br />asfaf
          </v-card>
        </template>
      </v-stepper>
    </v-responsive>
  </v-container>
</template>


<script>
import { VTimePicker } from "vuetify/labs/VTimePicker";

export default {
  components: {
    VTimePicker,
  },
  data() {
    return {
      tick: 5,
      time: "11:15",
      timeStep: "10:10",
      tickLabels: Array.from(Array(25).keys()),
    };
  },
  methods: {
    allowedHours: (v) => v % 2,
    allowedMinutes: (v) => v >= 10 && v <= 50,
    allowedStep: (m) => m % 10 === 0,
  },
};
</script>
