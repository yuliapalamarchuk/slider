<template>
  <div class="q-pa-md q-gutter-sm">
    <!-- <Slider /> -->
    <q-btn
      v-for="filter in backdropFilterList"
      :key="filter.label"
      color="primary"
      :label="filter.label"
      no-caps
      @click="filter.onClick"
    />

    <q-dialog v-model="dialog" :backdrop-filter="backdropFilter">
      <q-card class="modal-auth">
        <q-card-actions align="right">
          <q-btn
            icon="close"
            flat
            dense
            v-close-popup
            class="modal-auth__close"
          />
        </q-card-actions>
        <q-card-section
          class="row items-center justify-center q-pb-none modal-auth__title"
        >
          Авторизация
        </q-card-section>

        <q-card-section>
          <label for="login" class="modal-auth__label">Логин</label>
          <q-input id="login" rounded outlined v-model="text" />
        </q-card-section>

        <q-card-section class="ma">
          <label for="password" class="modal-auth__label">Пароль</label>
          <q-input id="lopasswordgin" rounded outlined v-model="text" />
        </q-card-section>

        <q-card-section class="modal-auth__btn-wrapper">
          <q-btn
            unelevated
            rounded
            color="primary"
            label="Войти"
            class="modal-auth__btn"
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

<style scoped>
.modal-auth__title {
  font-family: "Unbounded";
  font-size: 48px;
  font-weight: 700;
  line-height: 57.6px;
  text-align: left;
  padding: 0;
}

.modal-auth {
  max-width: 640px;
  min-width: 480px;
  border-radius: 40px;
  background-color: #f2f1ec;
}

.modal-auth__btn {
  font-family: "Nunito Sans";
  font-size: 24px;
  font-weight: 700;
  line-height: 32.74px;
  text-align: left;
  color: #414143 !important;
  min-width: 480px;
  background: #c9ff22 !important;
  margin: 0 0 64px 0;
  padding-top: 0;
}

.modal-auth__label {
  font-family: "Nunito Sans";
  font-size: 20px;
  font-weight: 600;
  line-height: 24px;
  text-align: left;
}
.modal-auth__btn-wrapper {
  padding-bottom: 0;
}
</style>
