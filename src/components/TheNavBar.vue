<template>
  <section>
    <button :class="{ active: stored }" @click="handleClick">
      stored resources
    </button>
    <button :class="{ active: add }" @click="handleClick">add resources</button>
  </section>
</template>

<script>
export default {
  name: 'TheNavBar',
  props: ['toggleResources', 'toggleForm'],
  data() {
    return {
      stored: true,
      add: false,
    };
  },
  methods: {
    handleClick() {
      this.stored = !this.stored;
      this.add = !this.add;
      this.toggleResources();
      this.toggleForm();
    },
  },
};
</script>

<style scoped>
section {
  display: flex;
  justify-content: space-between;
  gap: 1rem;
}
section button {
  flex: 1 auto;
  text-transform: uppercase;
  color: #360b59;
  background-color: transparent;
  border: none;
  font-weight: 600;
  padding: 1rem;
  border-radius: 3px;
}
section button:hover {
  background-color: #360b596c;
  transition-duration: 500ms;
  color: white;
  cursor: pointer;
}
section button.active {
  background-color: #360b59;
  box-shadow: rgba(0, 0, 0, 0.2) 0px 2px 7px -1px,
    rgba(0, 0, 0, 0.14) 0px 1px 1px 0px, rgba(0, 0, 0, 0.12) 0px 1px 3px 0px;
  color: white;
}
</style>
