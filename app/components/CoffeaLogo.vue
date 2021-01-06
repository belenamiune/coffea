<template>
  <img
    class="coffeaLogo"
    alt="coffea Logo"
    src="images/logo.svg"
  >
  
</template>

<style>

  .coffeaLogo {
    margin-top: 12em;
    justify-content: center;
    transition: 1s;
    position: relative;
    animation: mymove 3s;
    animation-timing-function: ease-in;
  }


@keyframes mymove {
  from {left: -200px;}
  to {left: 15px;}
}
</style>
