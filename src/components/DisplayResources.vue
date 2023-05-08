<template>
  <div v-if="showResources">
    <section v v-for="resource in resources" :key="resource.id">
      <div>
        <h2>{{ resource.title }}</h2>
        <p>{{ resource.description }}</p>
        <a :href="resource.link" target="_blank"><p>view resource</p></a>
      </div>
      <div>
        <button>delete</button>
      </div>
    </section>
  </div>
</template>
<script>
export default {
  name: 'DisplayResources',
  props: ['resources', 'showResources'],
};
</script>

<style scoped>
section {
  display: flex;
  justify-content: space-between;
  padding: 2rem 3rem;
}
section div:first-child {
  text-align: left;
}
section div:first-child > p {
  color: #7d7d7d;
}
button {
  text-transform: capitalize;
  color: #360b59;
  background-color: transparent;
  border: none;
  font-weight: 600;
  border-radius: 3px;
}
button:hover {
  cursor: pointer;
  color: purple;
}
h2 {
  text-transform: capitalize;
  margin-top: 0rem;
}
a {
  text-decoration: none;
  color: #bc8627;
  text-transform: capitalize;
}
</style>
