<template>
  <CardMain :items="items" />
</template>

<script>
import CardMain from "./components/CardMain.vue";
export default {
  name: "App",
  components: { CardMain },
  data() {
    return {
      items: [
        {
          title: "How many team members can I invite?",
          body: "You can invite up to 2 additional users on the Free plan. There is no limit on team members for the Premium plan.",
        },
        {
          title: "What is the maximum file upload size?",
          body: "No more than 2GB. All files in your account must fit your allotted storage space.",
        },
        {
          title: "How do I reset my password?",
          body: "Click “Forgot password” from the login page or “Change password” from your profile page. A reset link will be emailed to you.",
        },
        {
          title: "Can I cancel my subscription?",
          body: "Yes! Send us a message and we’ll process your request no questions asked.",
        },
        {
          title: "Do you provide additional support?",
          body: "Chat and email support is available 24/7. Phone lines are open during normal business hours.",
        },
      ],
    };
  },
};
</script>

<style>
@import url("https://fonts.googleapis.com/css2?family=Kumbh+Sans:wght@400;700&display=swap");
:root {
  /*  Primary */
  --background-linear-gradient: linear-gradient(
    180deg,
    rgba(175, 103, 233, 1) 30%,
    rgba(101, 101, 231, 1) 100%
  );
  --text-very-dark-desaturated-blue: hsl(238, 29%, 16%);
  --text-soft-red: hsl(14, 88%, 65%);
  --text-very-dark-grayish-blue: hsl(237, 12%, 33%);
  --text-dark-grayish-blue: hsl(240, 6%, 50%);
  --light-grayish-blue: hsl(240, 5%, 91%);
}
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
html {
  /* font-size: 10px; */
  /* 10px / 16px = 0.625 = 62.5% */
  /* Percentage of user's browser font-size setting */
  font-size: 62.5%;
}
body {
  background: var(--background-linear-gradient);
  max-width: 100vw;
  min-height: 100vh;
  display: grid;
  place-items: center;
}
#app {
  font-family: "Kumbh Sans", sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  /* background: rgb(175, 103, 233); */
}
</style>
