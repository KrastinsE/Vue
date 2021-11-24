<template>
  <div>
    <div class="form-group">
      <label for="search" class="form-label"></label>
      <input v-model="query" type="text" class="form-control" placeholder="Search (capital letters)">
    </div>
    <ul class="list text-center">
      <li v-for="(item, key) in filteredData" :key="key">
        {{item.currencyPair}}
        <br />
        {{item.bidPrice}} - {{item.bidAmount}} | {{item.offerPrice}} - {{item.offerAmount}}
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: "MarketView",
  props: {
    data: {
      type: Array,
      required: true
    }
  },
  computed: {
    filteredData() {
      if (this.query.length == 0) {
        return this.data;
      }

      return this.data.filter((item) => item.currencyPair.includes(this.query) || item.bidPrice.toString().includes(this.query) || item.bidAmount.toString().includes(this.query) || item.offerPrice.toString().includes(this.query) || item.offerAmount.toString().includes(this.query))
    }
  },
  data() {
    return {
      query: ''
    }
  },
}
</script>

<style lang="css">

ul {
  list-style-type: none;
}

</style>