<template>
  <div class="common-names">
    <p class="content-label">Common Names:</p>
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
.common-names {
  display: flex;
  height: 100px;
  min-height: 100px;
  padding: 10px;
  box-sizing: border-box;
  padding-left: 0;
}
p {
  margin: 0;
}
.content-label {
  width: 30%;
  box-sizing: border-box;
}
ul.content-contaier {
  border: 1px solid #aaaaaa;
  border-radius: 5px;
  height: 100%;
  min-height: 100%;
  width: 70%;
  padding: 10px;
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
