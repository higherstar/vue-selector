<template>
  <div class="card-box">

    <h2>Customize Path</h2>

    <multi-select
      multi-select-label="Folder Path"
      multi-select-type="Folder"
      :select-list="folderPaths"
    />

    <multi-select
     multi-select-label="File Path"
     multi-select-type="File"
     :select-list="filePaths"
    />

  </div>
</template>

<script>
  import MultiSelect from "../components/MultiSelect";

  export default {
    name: 'customize-path',
    components: {MultiSelect},
    data: function () {
      return {
        'filePaths': [
          'order_date',
          'order_number',
          'line_item_name',
          'file_name'
        ],
        'folderPaths': [
          'order_date',
          'order_number',
          'line_item_name',
          'file_name',
          'file_name_extension'
        ]
      }
    }
  }
</script>

<style scoped>
  .card-box {
    padding: 20px;
    box-shadow: 0 0 8px 0 rgba(0, 0, 0, 0.06), 0 1px 0 0 rgba(0, 0, 0, 0.02);
    border-radius: 5px;
    -moz-border-radius: 5px;
    background-clip: padding-box;
    margin: 20px auto;
    background-color: white;
  }
</style>
