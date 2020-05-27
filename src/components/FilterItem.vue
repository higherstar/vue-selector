<template>
  <div class="filter-item">
    <span v-if="index != 0 && customizeType == 'Folder'" class="filter-divide">/</span>
    <span v-if="index != 0 && customizeType == 'File'" class="filter-divide">_</span>
    <div class="filter">
      <span>{{filterName}}</span>
      <span class="remove" v-on:click="removeFilter">x</span>
    </div>
  </div>

</template>

<script>
  export default {
    name: 'filter-item',
    props: ['filterName', 'index', 'customizeType'],
    methods: {
      removeFilter() {
        this.$emit('remove')
      }
    }
  }
</script>

<style scoped>
  .filter-item {
    display: flex;
    align-items: center;
  }

  .filter {
    background-color: #ebf5ff;
    border: 1px solid #b3d9ff;
    color: #007eff;
    font-weight: 500;
    letter-spacing: 0.05em;
    font-size: 75%;
    line-height: 1;
    text-align: center;
    white-space: nowrap;
    vertical-align: middle;
    border-radius: .25em;
    display: inline-flex;
    height: 25px;
    margin: 0px 5px;
  }

  .filter span {
    padding: 5px;
  }

  .filter .remove {
    border-left: 1px solid #b3d9ff;
    cursor: pointer;
  }
</style>
