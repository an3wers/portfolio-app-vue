<template>
  <div class="col-lg-4 mb-3">
    <div class="card">
      <div class="card-body">
        <form @submit.prevent="formSubmit">
          <select
            v-model="form.selected"
            class="form-select mb-3"
            aria-label="selector"
          >
            <option value="default" disabled selected>Выберите тип</option>
            <option value="s-name">Имя</option>
            <option value="s-job">Должность</option>
            <option value="s-image">Аватар</option>
            <option value="s-decription">Описание</option>
          </select>
          <textarea
            v-model="form.text"
            class="form-control mb-3"
            id="textarea"
            rows="3"
          ></textarea>
          <button :disabled="!form.text" type="submit" class="btn btn-primary">
            Сохранить
          </button>
        </form>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      form: {
        selected: "default",
        text: null,
      },
    };
  },
  emits: ["submit"],
  methods: {
    formSubmit() {
      this.$emit("submit", [this.form.selected, this.form.text]);
      this.form.text = "";
      this.form.selected = "default";
    },
  },
};
</script>
