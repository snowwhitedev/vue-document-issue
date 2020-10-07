<template>
  <div class="published-version">
    <fieldset>
      <legend>Published Version</legend>
      <div class="info-header">
        <div class="info-header-item">
          <p class="content-label">Type:</p>
          <p>{{ pubtype }}</p>
        </div>
        <div class="info-header-item">
          <p class="content-label">Availability:</p>
          <p>{{ availability }}</p>
        </div>
        <div class="info-header-item">
          <p class="content-label">Language:</p>
          <p>{{ language }}</p>
        </div>
      </div>
      <div class="main-info">
        <div class="volume-info">
          <div class="volume-info-item">
            <p class="content-label">Website Publisher or Periodical Title:</p>
            <p class="volume-content">{{ info.title }}</p>
          </div>
          <div class="volume-info-item">
            <p class="content-label">Volume or Issue:</p>
            <p class="volume-content">{{ info.volume }}</p>
          </div>
          <div class="volume-info-item">
            <p class="content-label">Published Date:</p>
            <p class="volume-content">{{ info.date }}</p>
          </div>
        </div>
        <div class="locator-info-wrapper">
          <fieldset>
            <legend>Locator Information</legend>
            <div class="locator-info">
              <div class="locator-info-item">
                <p class="content-label">ISBN:</p>
                <p>{{ locator.isbn }}</p>
              </div>
              <div class="locator-info-item">
                <p class="content-label">UUID:</p>
                <p>{{ locator.uuid }}</p>
              </div>
              <div class="locator-info-item">
                <p class="content-label">Search Info:</p>
                <p>{{ locator.search }}</p>
              </div>
              <div class="locator-info-item">
                <p class="content-label">URL:</p>
                <p>{{ locator.url }}</p>
              </div>
              <div class="locator-info-item">
                <p class="content-label">DOI:</p>
                <p>{{ locator.doi }}</p>
              </div>
            </div>
          </fieldset>
        </div>
      </div>
     </fieldset>
  </div>
</template>

<script>
export default {
  props: {
    pubtype: {
      type: String,
      default: null
    },
    availability: {
      type: String,
      default: null
    },
    language: {
      type: String,
      default: null
    },
    info: {
      type: Object,
      default: () => {}
    },
    locator: {
      type: Object,
      default: () => {}
    }
  }
}
</script>

<style lang="scss" scoped>
.published-version {
  border: 1px solid #aaaaaa;
  border-radius: 5px;
  padding: 10px;
  max-height: 400px;
  overflow-y: auto;
}
.info-header {
  display: flex;
  align-items: center;
  margin-bottom: 10px;
}
.info-header-item {
  display: flex;
  align-items: center;
  margin-right: 30px;
}
.main-info {
  padding-left: 30px;
}
.volume-info-item {
  display: flex;
  align-items: center;
  margin-top: 5px;
  .content-label {
    width: 29%;
  }
}
.locator-info-wrapper {
  margin-top: 10px;
}
.locator-info-item {
  display: flex;
  align-items: center;
  margin-top: 5px;
}
</style>