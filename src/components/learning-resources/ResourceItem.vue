<template>
  <li>
    <div>
      <header>
        <h2>{{title}}</h2>
        <button>Delete</button>
      </header>
      <p>{{description}}</p>
      <nav>
        <a :href="link">View resource</a>
      </nav>
    </div>
  </li>
</template>

<script>
export default {
  name: "ResourceItem",
  props: ['title', 'description', 'link']
}
</script>

<style scoped>

</style>