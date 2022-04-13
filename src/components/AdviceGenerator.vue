<script>
import axios from "axios";
import { reactive } from "vue";

import "animate.css";

export default {
  setup() {
    const advice = reactive({ advice: "", id: "" });

    const loadAdvice = async () => {
      let response = await axios.get("https://api.adviceslip.com/advice");

      advice.advice = response.data.slip.advice;
      advice.id = response.data.slip.id;

      console.log(response.data.slip.advice);
    }; //fetch advice from api

    loadAdvice(); //generate the default advice

    return { advice, loadAdvice };
  },
};
</script>

<template>
  <section class="card animate__animated animate__pulse">
    <h1 class="card__title animate__animated animate__zoomIn">
      Advice #<span>{{ advice.id }}</span>
    </h1>
    <p class="card__description animate__animated animate__zoomIn">
      {{ advice.advice }}
    </p>
    <img src="../assets/pattern-divider-mobile.svg" alt="" />
    <button @click="loadAdvice" class="card__button">
      <img src="../assets/icon-dice.svg" alt="" />
    </button>
  </section>
</template>

<style scoped>
.card {
  @apply rounded-lg mx-4 bg-slate-700 flex flex-col py-6 px-2 gap-6 items-center justify-center text-center sm:max-w-xl;
}

.card__title {
  @apply text-emerald-500;
}

.card__description {
  @apply text-slate-300 text-2xl;
}

.card__button {
  @apply bg-emerald-500 p-3 rounded-full;
}
</style>
