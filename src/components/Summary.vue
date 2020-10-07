<template>
  <div class="summary">
    <div class="summary-item">
      <p class="content-label">Type:</p>
      <p class="summary-content">{{ doctype }}</p>
    </div>
     <div class="summary-item">
      <p class="content-label">Pages:</p>
      <p class="summary-content">{{ pages }}</p>
    </div>
     <div class="summary-item">
      <p class="content-label">Date:</p>
      <p class="summary-content">{{ date }}</p>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    doctype: {
      type: String,
      default: null
    },
    pages: {
      type: Number,
      default: null
    },
    date: {
      type: String,
      default: null
    }
  }
}
</script>

<style lang="scss" scoped>
.summary {
  height: 100px;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  padding: 10px;
  box-sizing: border-box;
}
.summary-item {
  display: flex;
}
</style>