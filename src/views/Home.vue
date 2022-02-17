<template>
  <div id="home" class="wrapper">
    <div class="container">
      <h1 class="mb-4">Portfolio</h1>
      <small style="color: #cccccc; display: block" class="mb-4"
        >https://images.unsplash.com/photo-1633332755192-727a05c4013d?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=880&q=80</small
      >
      <div class="row">
        <app-form @submit="updatePortfolio"></app-form>
        <app-portfolio
          @savePortfolio="saveToLS"
          :portfolio="portfolio"
        ></app-portfolio>
      </div>
    </div>
  </div>
</template>

<script>
import AppForm from "@/components/AppForm.vue";
import AppPortfolio from "@/components/AppPortfolio.vue";

export default {
  components: {
    AppForm,
    AppPortfolio,
  },
  data() {
    return {
      portfolio: {
        name: null,
        job: null,
        image: null,
        description: [],
      },
    };
  },
  methods: {
    updatePortfolio(data) {
      const formData = data;
      console.log(formData[0]);

      switch (data[0]) {
        case "s-name":
          this.updateName(data[1]);
          break;
        case "s-job":
          this.updateJob(data[1]);
          break;
        case "s-image":
          this.updateImage(data[1]);
          break;
        case "s-decription":
          this.updateDescription(data[1]);
          break;
        default:
          console.log("Выбран неправильный тип");
          break;
      }
    },
    updateName(value) {
      this.portfolio.name = value;
    },
    updateJob(value) {
      this.portfolio.job = value;
    },
    updateImage(value) {
      this.portfolio.image = value;
    },
    updateDescription(value) {
      this.portfolio.description.push(value);
    },
    saveToLS() {
      localStorage.setItem("portfolio", JSON.stringify(this.portfolio));
    },
  },
  mounted() {
    const currentPortfolio = localStorage.getItem("portfolio");
    // console.log(currentPortfolio)
    if (currentPortfolio !== null) {
      try {
        this.portfolio = JSON.parse(currentPortfolio);
      } catch (error) {
        console.log(error);
      }
    }
  },
};
</script>
