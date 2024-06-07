<template>
  <!-- <div class="container-fluid"> -->
    <Header />

    <slot />
  <!-- </div> -->
</template>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=League+Spartan:wght@400&display=swap');
.spartan {
  font-family: League Spartan;
}
.container-fluid {
  background-color: #6278b1;
}

.bg-primary {
  background-color: #3b4b77 !important;
}
@media only screen and (max-width : 600px) {
  .container-fluid{
    background-color: #6278b1;
    height: 100vh;
    width: 100%;
  }
}
</style>
