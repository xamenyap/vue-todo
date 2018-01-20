<template>
  <form>
    <div class="form-group">
      <label for="title">Title:</label>
      <input type="text" class="form-control" id="title" v-model="title">
    </div>
    <div class="form-group">
      <label for="description">Description:</label>
      <input type="text" class="form-control" id="description" v-model="description">
    </div>
    <button type="button" class="btn btn-primary" @click="submitTodoItem">Submit</button>
  </form>
</template>

<script>
  export default {
    data() {
      return {
        title: '',
        description: ''
      }
    },
    methods: {
      submitTodoItem() {
        this.title = this.title.trim();
        this.description = this.description.trim();

        if (this.title === '' || this.description === '') {
          alert('Title and description cannot be empty');
          return;
        }
        this.$emit('todo-item-submitted', {title: this.title, description: this.description});
      }
    }
  }
</script>
