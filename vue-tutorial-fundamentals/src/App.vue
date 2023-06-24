<script setup>
import HelloWorld from './components/HelloWorld.vue'
import TheWelcome from './components/TheWelcome.vue'
import TutorialPlayGround from './components/TutorialPlayGround.vue';
import FormInputBinding from './components/FormInputBinding.vue';
import ifDirective from './components/ifDirective.vue';
import listBinding from './components/listBinding.vue';
</script>

<template>
  <header>
    <img alt="Vue logo" class="logo" src="./assets/logo.svg" width="125" height="125" />

    <div class="wrapper">
      <HelloWorld msg="You did it!" />
    </div>
  </header>

  <main>
    <TutorialPlayGround msg="This is vue tag attribute!" />

    <div style="border:1px solid gray;padding:10px;margin:10px;">
      <FormInputBinding text="Initial input" />
    </div>

    <div style="border:1px solid gray;padding:10px;margin:10px;">
      <ifDirective />
    </div>

    <div style="border:1px solid gray;padding:10px;margin:10px;">
      <listBinding />
    </div>

    <!-- <TheWelcome /> -->
  </main>
</template>

<style scoped>
header {
  line-height: 1.5;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }
}
</style>
