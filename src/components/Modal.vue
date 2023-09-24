<template>
  <div class="backdrop" @click.self="closeModal">
    <div class="modal" :class="{ sale: theme === 'sale' }">
      <p>modal content</p>
      <slot></slot>
      <div class="actions">
        <slot name="name"></slot>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: ["theme"],
  methods: {
    closeModal() {
      this.$emit("close");
    },
  },
};
</script>

<style>
.modal {
  width: 400px;
  padding: 20px;
  margin: 100px auto;
  background: white;
  border-radius: 10px;
  background-color: brown;
}
.backdrop {
  top: 0px;
  position: fixed;
  background: rgba(0, 0, 0, 0.5);
  width: 100%;
  height: 100%;
}
.modal h1 {
  background: salmon;
}
.modal.actions {
  text-align: center;
  margin: 30px 0 10px 0;
}
.modal.actions a {
  color: #333;
  padding: 8px;
  border-radius: 4px;
  border: 1px solid #eee;
  text-decoration: none;
  margin: 10px;
}
.modal.sale.actions {
  color: white;
}
.modal.sale.actions a {
  color: #eee;
}
</style>