<template>
  <ul>
    <resource-item
        v-for="resource in resources"
        :title="resource.title"
        :description="resource.description"
        :link="resource.link"
        :key="resource.id"
    ></resource-item>
  </ul>
</template>

<script>
import ResourceItem from '@/components/learning-resources/ResourceItem';
export default {
  name: 'StoredResources',
  components: {
    ResourceItem
  },
  inject: ['resources']
}
</script>

<style scoped>
ul {
  list-style: none;
  margin: 0 auto;
  padding: 0;
  max-width: 40rem;
}
</style>