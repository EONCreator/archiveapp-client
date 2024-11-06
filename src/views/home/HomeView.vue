<script>
  import ToolBar from './components/ToolBar/ToolBar.vue'
  import Helper from './components/Helper/Helper.vue'
  import FileList from './components/FileList/FileList.vue'

  export default {
    components: {
      ToolBar,
      Helper,
      FileList
    }
  }
</script>

<style lang="scss" scoped>
  @import "./style.scss";
</style>

<template>
  <div class="panel">
    <ToolBar></ToolBar>
    <div class="content">
      <Helper></Helper>
      <FileList></FileList>
    </div>
  </div>
</template>

<style>
  body {
    width:100%;
  }

  .content {
    display: flex;
    height: 100%;
  }
</style>