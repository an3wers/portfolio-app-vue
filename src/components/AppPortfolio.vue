<template>
  <div class="col-lg-8">
    <div v-if="!portfolio.name" class="card mb-3">
      <div class="card-body">
        <div style="color: #cccccc; text-align: center">
          Пользователь еще не добавлен
        </div>
      </div>
    </div>
    <div v-else class="card mb-3">
      <div class="row g-0">
        <div class="col-md-4">
          <img
            v-if="portfolio.image"
            :src="portfolio.image"
            class="img-fluid rounded-start"
            alt="..."
          />
          <svg
            v-else
            class="bd-placeholder-img img-fluid rounded-start"
            width="100%"
            height="200"
            xmlns="http://www.w3.org/2000/svg"
            role="img"
            aria-label="Placeholder: Image"
            preserveAspectRatio="xMidYMid slice"
            focusable="false"
          >
            <title>Placeholder</title>
            <rect width="100%" height="100%" fill="#868e96"></rect>
            <text x="40%" y="50%" fill="#dee2e6" dy=".3em">Image</text>
          </svg>
        </div>
        <div class="col-md-8">
          <div class="card-body">
            <h5 class="card-title">{{ portfolio.name }}</h5>
            <p class="card-text">
              <small class="text-muted">{{ portfolio.job }}</small>
            </p>
          </div>
        </div>
      </div>
    </div>
    <div class="card mb-3">
      <div v-if="portfolio.description.length > 0" class="card-body">
        <div
          v-for="(descr, index) in portfolio.description"
          :key="index"
          class="card-body__profile-descr"
        >
          {{ descr }}
        </div>
      </div>
      <div v-else class="card-body">
        <div style="color: #cccccc; text-align: center">
          Описание еще не добавлено
        </div>
      </div>
    </div>
    <button
      @click="$emit('savePortfolio')"
      :disabled="!portfolio.name"
      class="btn btn-lg btn-primary"
    >
      Сохранить
    </button>
  </div>
</template>

<script>
export default {
  props: {
    portfolio: {
      type: Object,
    },
  },

  emits: ["savePortfolio"],

  // methods: {
  //   savePortfolioToLs() {
  //     // console.log(JSON.stringify(this.portfolio))
  //     localStorage.setItem('portfolio', JSON.stringify(this.portfolio))
  //   }
  // },

  // mounted() {
  //   const currentPortfolio = localStorage.getItem('portfolio')
  //   // console.log(currentPortfolio)
  //   if (currentPortfolio !== null) {
  //     try {
  //       // this.portfolio = JSON.parse(currentPortfolio)
  //     } catch (error) {
  //       console.log(error)
  //     }
  //   }
  // }
};
</script>
