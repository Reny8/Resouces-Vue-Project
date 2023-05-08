<template>
  <header>
    <h1>ResourcesApp</h1>
  </header>
  <TheNavBar :toggleResources="toggleResources" :toggleForm="toggleForm" />
  <DisplayResources
    :resources="resources"
    :showResources="showResources"
    :handleDelete="handleDelete"
  />
  <AddResource :handleAdd="handleAdd" :showForm="showForm" />
</template>

<script>
import TheNavBar from './components/TheNavBar.vue';
import DisplayResources from './components/DisplayResources.vue';
import AddResource from './components/AddResource.vue';

export default {
  name: 'App',
  components: {
    TheNavBar,
    DisplayResources,
    AddResource,
  },
  data() {
    return {
      showResources: true,
      showForm: false,
      resources: [
        {
          title: 'vue guide',
          description: 'The official Vue.js documentation.',
          link: 'https://vuejs.org/guide/introduction.html',
        },
        {
          title: 'google',
          description: 'Learn more about google by clicking here.',
          link: 'https://cloud.google.com/docs/',
        },
      ],
    };
  },
  methods: {
    toggleResources() {
      this.showResources = !this.showResources;
    },
    toggleForm() {
      this.showForm = !this.showForm;
    },
    handleAdd(item) {
      this.resources.push(item);
    },
    handleDelete(link) {
      const newArray = this.resources.filter((item) => item.link !== link);
      this.resources = newArray;
    },
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
header {
  width: 100%;
  background-color: #600b2c;
  color: white;
  box-shadow: rgba(0, 0, 0, 0.2) 0px 2px 7px -1px,
    rgba(0, 0, 0, 0.14) 0px 1px 1px 0px, rgba(0, 0, 0, 0.12) 0px 1px 3px 0px;
  padding: 0.5rem;
}
header h1 {
  filter: drop-shadow(2px 2px 2px black);
}
body {
  margin: 0rem;
}
section {
  box-shadow: rgba(0, 0, 0, 0.2) 0px 2px 7px -1px,
    rgba(0, 0, 0, 0.14) 0px 1px 1px 0px, rgba(0, 0, 0, 0.12) 0px 1px 3px 0px;
  margin: 2rem 4rem;
  padding: 1rem;
  border-radius: 3px;
}
</style>
