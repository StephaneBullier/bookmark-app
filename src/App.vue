<template>
  <the-header title="RememberMe"></the-header>
  <stored-resources :resources="storedResources"></stored-resources>
</template>

<script>
import { v4 as uuidv4 } from 'uuid';
import TheHeader from "@/components/layout/TheHeader";
import StoredResources from "@/components/learning-resources/StoredResources";

export default {
  name: "App",
  components: {
    TheHeader,
    StoredResources
  },
  data() {
    return {
      storedResources: [
        {
          id: uuidv4(),
          title: 'Official Guide',
          description: 'The official Vue.js documentation',
          link: 'https://v3.vuejs.org/'
        },
        {
          id: uuidv4(),
          title: 'Google',
          description: 'Learn to google',
          link: 'https://www.google.com/'
        }
      ]
    }
  }
}
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Roboto:wght@400;700&display=swap');

*,
*::before,
*::after {
  -webkit-box-sizing: border-box;
  box-sizing: border-box;
}

html {
  font-family: sans-serif;
  line-height: 1.15;
  -webkit-text-size-adjust: 100%;
  -moz-text-size-adjust: 100%;
  -ms-text-size-adjust: 100%;
  text-size-adjust: 100%;
  -ms-overflow-style: scrollbar;
  -webkit-tap-highlight-color: transparent;
}

article, aside, dialog, figcaption, figure, footer, header, hgroup, main, nav, section {
  display: block;
}

body {
  margin: 0;
  font-family: Roboto, "Helvetica Neue", Arial, sans-serif;
  font-size: 1rem;
  font-weight: 400;
  line-height: 1.5;
  color: #212529;
  text-align: left;
  background-color: #fff;
}
</style>