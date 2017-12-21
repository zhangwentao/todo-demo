<template>
  <div class="todo-item">
    <p>{{content}}</p>
    <a href="javascript:;" class="remove-btn" @click.pevent="notifyRemove">&times;</a>
  </div>

</template>

<script>
export default {
  props: {
    content: {
      type: String,
      required:true
    },
    index: Number
  },
  data: function(){
    return {

    }
  },
  methods: {
    notifyRemove: function() {
      this.$emit('remove',this.index);
    }
  }
}
</script>

<style scoped>
  .todo-item {
    display: flex;
    border: 1px solid;
    padding-left: 5px;
    margin: 5px;
    align-items: center;
  }

  p {
    flex-grow: 1;
  }

  .remove-btn {
    display: block;
    flex-grow: 0;
    width: 20px;
    height: 20px;
    color: brown;
  }

</style>
