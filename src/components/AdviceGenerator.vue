<template>
  <section class="card">
    <h1 class="card__title">Advice #<span>117</span></h1>
    <p class="card__description">
      "It is easy to sit up and take notice, what's difficult is getting up and
      taking action"
    </p>
    <img src="../assets/pattern-divider-mobile.svg" alt="" />
    <button class="card__button">
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
