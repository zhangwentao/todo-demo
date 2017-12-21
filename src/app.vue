<template>
  <div id="app">
    <h2 class="app-title">TODO-DEMO</h2>
    <Inputer @new="handleInput"/>
    <ToDoList
    v-if="listData.length>0"
    :dataList="listData"
    @remove="onItemRemove"/>
    <p v-else class="tip">no todos yet,please input some then press Enter key.</p>
  </div>
</template>

<script>
import ToDoList from './ToDoList.vue';
import Inputer from './inputer.vue';

export default {
  data: function() {
    return {
      listData: [
        {content: 'ok1'},
        {content: 'ok2'},
        {content: 'ok2'}
      ]
    }
  },
  components: {
    ToDoList,
    Inputer
  },
  methods: {
    handleInput: function(content) {
      this.listData.push({
        content
      })
    },
    onItemRemove: function(index) {
      this.listData.splice(index,1);
    }
  }
}
</script>

<style scoped>
  #app {
    width: 400px;
    margin: 50px auto;
    border: 1px dashed #e99;
    min-height: 600px;
  }

  .tip {
    text-align: center;
  }

  .app-title {
    font-size: 60px;
    color: rgba(0,0,0,.8);
    text-align: center;
  }

</style>
