<template>
  <ul>
    <resource-item
        v-for="resource in storedResources"
        :title="resource.title"
        :description="resource.description"
        :link="resource.link"
        :key="resource.id"
    ></resource-item>
  </ul>
</template>

<script>
import { v4 as uuidv4 } from 'uuid';
import ResourceItem from "@/components/learning-resources/ResourceItem";
export default {
  name: "App",
  components: {
    ResourceItem
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

</style>