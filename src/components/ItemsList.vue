<template>
  <div class="panel panel-default">
    <div class="panel-heading">
      {{title}}
    </div>
    <div class="panel-body">
      <item-content v-for="(item, index) in items" :key="index" :item="item"></item-content>
    </div>
    <div class="panel-footer">
      <input type="button" class="btn btn-primary" value="Add Item" @click="openAddItemModel"/>
    </div>
  </div>
</template>

<script>
  import ItemContent from './ItemContent'

  export default {
    components: {
      ItemContent
    },
    data() {
      return {
        title: 'Your TODOs list',
        items: [
          {
            title: 'test',
            description: 'a description 1',
            date: (new Date()).toLocaleString()
          },
          {
            title: 'test 2',
            description: 'a description 2',
            date: (new Date()).toLocaleString()
          },
          {
            title: 'test 3',
            description: 'a description 3',
            date: (new Date()).toLocaleString()
          }
        ]
      }
    },
    methods: {
      openAddItemModel() {

      }
    }
  }
</script>
