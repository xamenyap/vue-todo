<template>
  <div class="panel panel-default">
    <div class="panel-heading">
      {{title}}
    </div>
    <div class="panel-body">
      <div v-if="this.items.length === 0">
        <span>There is no item in your list.</span>
      </div>
      <div v-else>
        <item-box v-for="(item, index) in items" :key="index" :item="item"></item-box>
      </div>
    </div>
    <div class="panel-footer">
      <item-form @todo-item-submitted="addNewTodoItem"></item-form>
    </div>
  </div>
</template>

<script>
  import ItemBox from './ItemBox'
  import ItemForm from './ItemForm'

  export default {
    components: {
      ItemBox,
      ItemForm
    },
    data() {
      return {
        title: 'Your TODOs list',
        showModal: false,
        items: []
      }
    },
    methods: {
      addNewTodoItem(payload) {
        this.items.push(
          {
            title: payload.title,
            description: payload.description,
            date: (new Date()).toLocaleString(),
          }
        );
      }
    }
  }
</script>
