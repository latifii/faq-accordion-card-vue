<template>
  <main class="main">
    <img class="box" src="../assets/illustration-box-desktop.svg" alt="box" />
    <div class="card">
      <div class="card-img">
        <img
          class="img-mobile"
          src="../assets/illustration-woman-online-mobile.svg"
          alt="illustration woman online mobile"
        />
        <img
          class="img-desktop"
          src="../assets/illustration-woman-online-desktop.svg"
          alt="illustration woman online mobile"
        />
      </div>
      <CardFaq :faqs="items" />
    </div>
  </main>
</template>

<script>
import CardFaq from "./CardFaq.vue";
export default {
  components: { CardFaq },
  name: "CardMain",
  props: ["items"],
};
</script>

<style scoped>
.main {
  position: relative;
  background-color: #fff;
  border-radius: 2rem;
  width: 32rem;
  margin: 14rem 2rem 6rem;
  background: url(../assets/bg-pattern-mobile.svg), #fff;
  background-repeat: no-repeat;
  background-position: 50% 0;
  background-size: 25rem;
}
.box {
  display: none;
}
.card-img {
  position: absolute;
  top: 0;
  left: 50%;
  transform: translate(-50%, -60%);
  width: 25rem;
  z-index: 2;
}
.img-desktop {
  display: none;
}

.card-faq {
  height: 30rem;
}
@media (min-width: 1000px) {
  .main {
    width: 87rem;
    background: url(../assets/bg-pattern-desktop.svg), #fff;
    background-repeat: no-repeat;
    background-position: -57rem 64%;
    margin: 0;
  }
  .box {
    display: unset;
    position: absolute;
    left: 0;
    top: 50%;
    z-index: 5;
    transform: translate(-50%, -30%);
    animation: upDown 2s infinite;
  }
  @keyframes upDown {
    0% {
      transform: translate(-50%, -30%);
    }
    50% {
      transform: translate(-50%, -35%);
    }
    100% {
      transform: translate(-50%, -30%);
    }
  }
  .card {
    margin: 4rem auto;
    display: grid;
    grid-template-columns: 1fr 1fr;
    column-gap: 5rem;
    height: 50rem;
    overflow: hidden;
  }
  .card-img {
    position: inherit;
    top: inherit;
    left: inherit;
    transform: none;
    transform: translate(-30%, 12%);
    height: 46rem;
  }
  .img-mobile {
    display: none;
  }
  .img-desktop {
    display: unset;
  }
}
</style>
