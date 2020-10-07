<template>
  <div class="editors">
    <p class="content-label">Editors:</p>
    <ul class="content-contaier">
      <li v-for="(item, idx) in items" :key="idx">
        {{ item }}
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  props: {
    items: {
      type: Array,
      default: () => []
    }
  }
};
</script>

<style lang="scss" scoped>
ul.content-contaier {
  border: 1px solid #aaaaaa;
  border-radius: 5px;
  height: 120px;
  min-height: 120px;
  width: 100%;
  padding: 10px;
  width: 100%;
  box-sizing: border-box;
  // width: 60%;
  li {
    margin-bottom: 5px;
  }
  li:last-child {
    margin-bottom: 0;
  }
  overflow-y: scroll;
}
</style>
