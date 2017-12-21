<template>
  <div>
    <ToDoItem v-for="item,index of dataList"
    :index="index"
    :key="item.id"
    v-on="listener"
    :content="item.content"/>
  </div>
</template>

<script>
import ToDoItem from './ToDoItem.vue';

export default {
  props: {
    dataList: Array
  },
  components: {
    ToDoItem
  },
  data: function() {
    return {
    };
  },
  computed: {
    listener: function() {
      return this.$listeners
    }
  }

}
</script>

<style>

</style>
