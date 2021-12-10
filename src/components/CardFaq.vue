<template>
  <section class="faq">
    <h2 class="faq-title">FAQ</h2>
    <div
      class="faq-content"
      :class="{ open: currentToggle === indx }"
      v-for="(item, indx) in faqs"
      :key="indx"
      @click="toggleEvent(indx)"
    >
      <h3 class="faq-content__title">{{ item.title }}</h3>
      <div>
        <svg
          class="svg"
          data-v-4fa7a832=""
          width="10"
          height="7"
          xmlns="http://www.w3.org/2000/svg"
        >
          <path
            data-v-4fa7a832=""
            d="M1 .799l4 4 4-4"
            stroke="#F47B56"
            stroke-width="2"
            fill="none"
            fill-rule="evenodd"
          ></path>
        </svg>
      </div>
      <transition name="fade">
        <p class="faq-content__content" v-if="currentToggle === indx">
          {{ item.body }}
        </p>
      </transition>
    </div>
  </section>
</template>

<script>
export default {
  name: "CardFaq",
  props: ["faqs"],
  data() {
    return {
      currentToggle: 1,
    };
  },
  methods: {
    toggleEvent(indx) {
      this.currentToggle = indx;
    },
  },
};
</script>

<style scoped>
.faq {
  padding: 15rem 2.3rem 5rem;
}
.faq-title {
  font-size: 3.2rem;
  color: var(--text-very-dark-desaturated-blue);
  text-align: center;
  margin-bottom: 3rem;
}
.faq-content {
  display: grid;
  grid-template-columns: 1fr auto;
  align-items: center;
  color: var(--text-very-dark-grayish-blue);
  column-gap: 2.9rem;
  row-gap: 1rem;
  padding-top: 2rem;
  padding-bottom: 2rem;
  border-bottom: 1px solid var(--light-grayish-blue);
  cursor: pointer;
}
.faq-content__title {
  font-weight: 400;
  font-size: 1.3rem;
  color: var(--text-very-dark-grayish-blue);
}
.faq-content__title:hover {
  color: var(--text-soft-red);
}
.faq-content.open .faq-content__title {
  font-weight: 700;
}
.svg {
  transition: transform 0.3s;
}
.faq-content.open .svg {
  transform: rotate(180deg);
}
.faq-content__content {
  /* display: none; */
  font-size: 1.2rem;
  line-height: 1.5;
  color: var(--text-dark-grayish-blue);
}
.fade-enter-active {
  transition: all 0.5s ease;
}
.fade-enter-from {
  transform: translateY(-25px);
  opacity: 0;
}
.fade-leave-to {
  transform: translateX(-25px);
  opacity: 0;
}
.fade-leave-active {
  transition: all 0.3s ease;
}
@media (min-width: 1000px) {
  .faq {
    text-align: left;
    padding: 5rem 7rem 2rem 0;
  }
  .faq-title {
    text-align: left;
  }
}
</style>
