<template>
  <div class="inputer">
    <input type="text" v-model="content" @keyup.enter="onConfirm">
  </div>
</template>

<script>
export default {
  data: function() {
    return {
      content: ''
    }
  },
  methods: {
    onConfirm: function() {
      this.$emit('new',this.content);
      this.content = '';
    }
  }
}
</script>

<style>

  .inputer {
    display: flex;
      border: 1px solid #eee;
      margin: 5px;
    flex-basis: 0;
  }
  input {
      flex-grow: 1;
      display: block;
      -webkit-appearance: none;
      font-size: 20px;
      padding: 5px;
      border: none;
  }

</style>
