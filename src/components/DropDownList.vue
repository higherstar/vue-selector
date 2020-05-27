<template>
  <div class="dropdown-list">
    <span v-for="item in items" v-on:click="addItem(item)">{{item}}</span>
  </div>
</template>

<script>
  export default {
    name: 'drop-down-list',
    props: ['items'],
    methods: {
      addItem(item) {
        this.$emit('add', item)
      }
    }
  }
</script>

<style scoped>
  .dropdown-list {
    display: flex;
    flex-direction: column;
    position: absolute;
    background: white;
    width: 100%;
    padding: 5px 5px;
    box-shadow: 0 0 8px 0 rgba(0, 0, 0, 0.1), 0 1px 0 0 rgba(0, 0, 0, 0.06);
    max-height: 200px;
    overflow-y: auto;
    z-index: 1000;
  }

  .dropdown-list span {
    height: 30px;
    cursor: pointer;
    padding: 5px 10px;
    color: #444;
  }

  .dropdown-list span:hover, .dropdown-list span:active {
    background: #71b6f9;
    color: white;
  }

</style>
