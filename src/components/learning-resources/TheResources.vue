<template>
  <base-card>
    <base-button
        @click="setSelectedTab('stored-resources')"
        :mode="storedResourceButtonMode"
    >
      Stored Resources
    </base-button>
    <base-button
        @click="setSelectedTab('add-resource')"
        :mode="addResourceButtonMode"
    >
      Add Resource
    </base-button>
  </base-card>
  <keep-alive>
    <component :is="selectedTab"></component>
  </keep-alive>
</template>

<script>
import {v4 as uuidv4} from 'uuid';
import StoredResources from '@/components/learning-resources/StoredResources';
import AddResource from '@/components/learning-resources/AddResource';
export default {
  name: 'TheResources',
  components: {
    AddResource,
    StoredResources
  },
  data() {
    return {
      selectedTab: 'stored-resources',
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
  },
  provide() {
    return {
      resources: this.storedResources,
      addResource: this.addResource,
      removeResource: this.removeResource
    }
  },
  computed: {
    storedResourceButtonMode() {
      return this.selectedTab === 'stored-resources' ? null : 'flat'
    },
    addResourceButtonMode() {
      return this.selectedTab === 'add-resource' ? null : 'flat'
    }
  },
  methods: {
    setSelectedTab(tab) {
      this.selectedTab = tab
    },
    addResource(title, description, link) {
      const newResource = {
        id: uuidv4(),
        title,
        description,
        link
      }
      this.storedResources.unshift(newResource)
      this.selectedTab = 'stored-resources'
    },
    removeResource(id) {
      const resourceIndex = this.storedResources.findIndex(resource => resource.id === id)
      this.storedResources.splice(resourceIndex, 1)
    }
  }
}
</script>

<style scoped>

</style>