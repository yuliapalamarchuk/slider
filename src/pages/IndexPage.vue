<template>
  <div class="q-pa-md q-gutter-sm">
    <Slider />
    <q-btn
      v-for="filter in backdropFilterList"
      :key="filter.label"
      color="primary"
      :label="filter.label"
      no-caps
      @click="filter.onClick"
    />

    <q-dialog v-model="dialog" :backdrop-filter="backdropFilter">
      <q-card>
        <q-card-actions align="right">
          <q-btn icon="close" flat round dense v-close-popup />
        </q-card-actions>
        <q-card-section
          class="row items-center justify-center q-pb-none text-h6"
        >
          Dialog
        </q-card-section>

        <q-card-section>
          <label for="login">Логин</label>
          <q-input id="login" rounded outlined v-model="text" />
        </q-card-section>

        <q-card-section>
          <label for="password">Пароль</label>
          <q-input id="lopasswordgin" rounded outlined v-model="text" />
        </q-card-section>

        <q-card-section>
          <q-btn
            unelevated
            rounded
            color="primary"
            label="Unelevated Rounded"
          />
        </q-card-section>
      </q-card>
    </q-dialog>
  </div>
</template>

<script>
import Slider from "../components/Slider.vue";
import { ref } from "vue";

export default {
  components: {
    Slider,
  },
  setup() {
    const list = ["blur(4px)"];

    const dialog = ref(false);
    const backdropFilter = ref(null);

    return {
      dialog,
      backdropFilter,
      backdropFilterList: list.map((filter) => ({
        label: filter,
        onClick: () => {
          backdropFilter.value = filter;
          dialog.value = true;
        },
      })),
    };
  },
};
</script>

<style scoped></style>
