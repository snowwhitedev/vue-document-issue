<template>
  <div class="home">
    <div class="doc-title">{{ title }}</div>
    <div class="content-section official-section">
      <div class="official-name">
        <p class="content-label">Official Name:</p>
        <p class="categories">
          <span v-for="catg in categories" :key="catg">
            &nbsp;{{ categories.indexOf(catg) !== 0 ? '| ' + catg : catg }}
          </span>
        </p>
      </div>
      <div class="content-row">
        <common-names class="common-names" :items="commonNames" />
        <Summary
          class="summary"
          :doctype="summary.type"
          :pages="summary.pages"
          :date="summary.date"
        />
      </div>
    </div>
    <div class="content-section">
      <div class="content-row">
        <authors class="authors" :items="authors" />
        <editors class="editors" :items="editors" />
      </div>
      <div class="content-row">
        <published-version
          class="published-version"
          :pubtype="published.pubtype"
          :availability="published.availability"
          :language="published.language"
          :info="published.info"
          :locator="published.locator"
        />
      </div>
    </div>
  </div>
</template>

<script>
// @ is an alias to /src
import CommonNames from '../components/CommonNames.vue';
import Summary from '../components/Summary.vue';
import Authors from '../components/Authors.vue';
import Editors from '../components/Editors.vue';
import PublishedVersion from '../components/PublishedVersion.vue';
export default {
  name: 'Home',
  components: {
    CommonNames,
    Summary,
    Authors,
    Editors,
    PublishedVersion
  },
  data() {
    return {
      title: 'Authority Document Card',
      categories: [
        'series',
        'catalog_id',
        'title',
        'subtitle',
        'version',
        'section',
        'subsection',
        'chapter'
      ],
      commonNames: ['Common Name1', 'Common Name2', 'Common Name3'],
      summary: { type: 'Document Type', pages: 320, date: '2020-10-07' },
      authors: [
        'prefix | first name | middle initial | last name | suffix',
        'prefix | first name | middle initial | last name | suffix',
        'prefix | first name | middle initial | last name | suffix'
      ],
      editors: [
        'prefix | first name | middle initial | last name | suffix',
        'prefix | first name | middle initial | last name | suffix',
        'prefix | first name | middle initial | last name | suffix'
      ],
      published: {
        pubtype: 'ePub',
        availability: 'Free',
        language: 'English',
        info: {
          title: 'The title of periodical or website hosting the document',
          volume: 'Vol.2091',
          date: '2020-10-07'
        },
        locator: {
          isbn: 'ISBN9000091',
          uuid: '123456abcdef',
          search: 'Search Information',
          url: 'https://google.com',
          doi: 'The Locator of DOI'
        }
      }
    };
  }
};
</script>

<style lang="scss" scoped>
p {
  margin: 0;
}
.home {
  width: 100%;
  // height: 80vh;
  max-width: 1200px;
  border: 1px solid #cccccc;
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  padding-bottom: 20px;
  /* margin: 0 auto; */
}
.doc-title {
  text-align: left;
  padding: 10px;
  border-bottom: 1px solid #777777;
}
.official-name {
  display: flex;
  align-items: center;
}
.content-row {
  display: flex;
}
.common-names {
  width: 50%;
}
.summary {
  width: 50%;
  padding-right: 10px;
}
.authors {
  width: 50%;
  padding-right: 10px;
}
.editors {
  width: 50%;
  padding-left: 10px;
}
.published-version {
  margin-top: 10px;
  width: 100%;
}
</style>
