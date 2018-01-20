<template>
  <div class="col-md-12 content-container">
    <div class="col-md-12 content-title">Title: {{item.title}}</div>
    <div class="col-md-12 content-description">Description: {{item.description}}</div>
    <div class="col-md-12 content-date">Date: {{item.date}}</div>
  </div>
</template>

<script>
  export default {
    props: ['item'],
    created() {
      console.log(this.item);
    }
  }
</script>

<style scoped>
  .content-container {
    border: 1px solid black;
    border-radius: 4px;
    margin-right: 10%;
    margin-bottom: 15px;
    padding: 5px;
  }
  .content-title {
    font-weight: bold;
    width: 100%;
  }
  .content-description {
    width: 100%;
  }
  .content-date {
    width: 100%;
  }
</style>
