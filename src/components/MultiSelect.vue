<template>
  <div class="multi-select">
    <label>{{multiSelectLabel}}</label>
    <div class="select-container">
      <div class="select-box">
        <div class="form-control multi-select">

          <filter-item
            v-for="(filter, index) in filterList"
            v-bind:key="index"
            v-bind:index="index"
            v-bind:filter-name="filter"
            v-bind:customizeType="multiSelectType"
            v-on:remove="removeFilter(filter, index)">
          </filter-item>

          <input type="text" placeholder="Customize path..." v-on:click="onClickMultiSelect">
        </div>
      </div>
    </div>
    <drop-down-list
      v-if="dropDownList.length > 0 && showDropDown"
      :items="dropDownList"
      v-on:add="addFilter"
    >
    </drop-down-list>
  </div>
</template>

<script>
  import DropDownList from './DropDownList'
  import FilterItem from './FilterItem'

  export default {
    name: 'multi-select',
    components: {FilterItem, DropDownList},
    data: function() {
      return {
        showDropDown: false,
        filterList: [],
        dropDownList: []
      }
    },
    props: [
      'multiSelectLabel',
      'multiSelectType',
      'selectList'
    ],
    methods: {
      onClickMultiSelect() {
        this.showDropDown = !this.showDropDown
      },
      addFilter(filter) {
        this.filterList.push(filter)
        this.dropDownList.splice(this.dropDownList.indexOf(filter), 1)
      },
      removeFilter(filter, index) {
        this.dropDownList.push(filter)
        this.filterList.splice(index, 1)
      }
    },
    mounted() {
      this.filterList = [...this.selectList]
    }
  }
</script>

<style scoped>

  .multi-select {
    position: relative;
  }

  .form-control {
    background-color: #fff;
    background-clip: padding-box;
    border: 1px solid #ced4da;
    border-radius: .25rem;
    font-size: 1rem;
    font-weight: 400;
    line-height: 1.5;
  }

  .select-container {
    position: relative;
    margin-bottom: 10px;
  }

  .select-container .select-box {
    position: relative;
  }

  .select-container .select-box .multi-select {
    display: flex;
    flex-wrap: wrap;
    height: auto;
    padding-right: 25px;
    padding-left: 0;
    padding-bottom: 1px;
  }

  .select-container .select-box .multi-select input {
    flex: 1;
    min-width: 50px;
    height: 25px;
    border: 0;
    outline: none;
    margin-left: 10px;
    margin-bottom: 5px;
  }
</style>
