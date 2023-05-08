<template>
  <section>
    <form>
      <label>
        Title
        <input />
      </label>
      <label>
        Description
        <textarea></textarea>
      </label>
      <label>
        <Link></Link>
        <input />
      </label>
      <button>add resource</button>
    </form>
  </section>
</template>
<script>
export default {
  name: 'AddResource',
  props: ['counter'],
  data() {
    return {
      newResource: {
        id: 0,
        title: '',
        description: '',
        link: '',
      },
    };
  },
};
</script>
<style></style>
