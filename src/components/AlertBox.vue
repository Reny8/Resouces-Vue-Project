<template>
  <div>
    <div id="overlay" :class="{ active: open }">
      <dialog open id="alert-box" :class="{ active: open }">
        <h1>invalid input</h1>
        <div>
          <p>Unfortunately, at least one input value is invalid.</p>
          <p>
            Please check all inputs and make sure you enter at least a few
            characters into each input field.
          </p>
        </div>
        <div>
          <button @click="toggleAlertBox">okay</button>
        </div>
      </dialog>
    </div>
  </div>
</template>
<script>
export default {
  name: 'AlertBox',
  props: ['open', 'toggleAlertBox'],
};
</script>

<style scoped>
dialog {
  position: fixed;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%) scale(0);
  background-color: white;
  border-radius: 5px;
  padding: 0rem;
  border: none;
}
dialog.active {
  transform: translate(-50%, -50%) scale(1);
}
dialog h1 {
  margin: 0rem;
  text-align: left;
  background-color: purple;
  color: white;
  text-transform: capitalize;
  padding: 1rem;
  border-radius: 5px 5px 0px 0px;
  box-shadow: rgba(0, 0, 0, 0.2) 0px 2px 7px -1px,
    rgba(0, 0, 0, 0.14) 0px 1px 1px 0px, rgba(0, 0, 0, 0.12) 0px 1px 3px 0px;
}
dialog > div {
  text-align: left;
  padding: 1rem;
}
div#overlay {
  position: fixed;
  opacity: 0;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  transition: 200ms ease-in-out;
  background-color: #7d7d7da4;
  pointer-events: none;
  z-index: 100 !important;
}
dialog div:last-child {
  display: flex;
  flex-direction: row;
  justify-content: flex-end;
}
dialog button {
  margin: 0.1rem;
  text-transform: capitalize;
  border: none;
  font-weight: 600;
  padding: 1rem 2rem;
  border-radius: 3px;
  background-color: purple;
  box-shadow: rgba(0, 0, 0, 0.2) 0px 2px 7px -1px,
    rgba(0, 0, 0, 0.14) 0px 1px 1px 0px, rgba(0, 0, 0, 0.12) 0px 1px 3px 0px;
  color: white;
}
div#overlay.active {
  pointer-events: all;
  opacity: 1;
  z-index: 20 !important;
}
</style>
