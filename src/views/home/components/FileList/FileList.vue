
<style lang="scss" scoped>
  @import "./styles.scss";
</style>

<template>
  <div class="file-list">
    <div class="toolbar">
      <div class="item">
        <button class="create">Создать папку</button>
      </div>
      <div class="item">
        <input placeholder="Поиск..." />
        <button class="submit"><img src="./../../../../../public/search-icon.svg" /></button>
      </div>
    </div>
      <div class="files">
        <div class="folder" alt="Дата создания: 30.10.2024">
          <div class="content">
            <div class="background"></div>
            <div class="name">Документы</div>
          </div>
        </div>
        <div class="folder">
          <div class="content">
            <div class="background"></div>
            <div class="name">Видео</div>
          </div>
        </div>
        <div class="folder">
          <div class="content">
            <div class="background"></div>
            <div class="name">Изображения</div>
          </div>
        </div>
      </div>
      <div class="footer">
        <Paginator></Paginator>
      </div>
  </div>
</template>

<style>
  body {
    width:100%;
  }
</style>

<script>
  import Paginator from './components/Paginator/Paginator.vue'

  export default {
    components: {
      Paginator
    }
  }
</script>