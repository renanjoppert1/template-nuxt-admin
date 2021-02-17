<template>
  <el-row class="demo-autocomplete">
    <el-col :span="24">
      <el-autocomplete
        class="search-bar-input"
        v-model="state2"
        :fetch-suggestions="querySearch"
        placeholder="Digite sua busca..."
        :trigger-on-focus="false"
        clearable
        @select="handleSelect"
      >
      <i
        class="el-icon-search el-input__icon"
        slot="prefix">
      </i>
      </el-autocomplete>
    </el-col>
  </el-row>
</template>

<script>
  export default {
    data() {
      return {
        links: [],
        state1: '',
        state2: ''
      };
    },
    methods: {
      querySearch(queryString, cb) {
        var links = this.links;
        var results = queryString ? links.filter(this.createFilter(queryString)) : links;
        // call callback function to return suggestions
        cb(results);
      },
      createFilter(queryString) {
        return (link) => {
          return (link.value.toLowerCase().indexOf(queryString.toLowerCase()) === 0);
        };
      },
      loadAll() {
        return [
          { "value": "vue", "link": "https://github.com/vuejs/vue" },
          { "value": "element", "link": "https://github.com/ElemeFE/element" },
          { "value": "cooking", "link": "https://github.com/ElemeFE/cooking" },
          { "value": "mint-ui", "link": "https://github.com/ElemeFE/mint-ui" },
          { "value": "vuex", "link": "https://github.com/vuejs/vuex" },
          { "value": "vue-router", "link": "https://github.com/vuejs/vue-router" },
          { "value": "babel", "link": "https://github.com/babel/babel" }
         ];
      },
      handleSelect(item) {
        console.log(item);
      }
    },
    mounted() {
      this.links = this.loadAll();
    }
  }
</script>

<style lang="scss" scoped>
.search-bar-input{
  width: 100%;
}
</style>
