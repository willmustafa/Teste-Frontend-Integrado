<template>
  <table>
    <thead>
      <tr>
        <th scope="col" v-for="(item, index) in itens" v-bind:key="index">
          {{ item.label }}
        </th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <th scope="col" v-for="(item, index) in itens" v-bind:key="index">
          <input type="text" :name="item.item" v-on:input="filterData" />
        </th>
      </tr>
      <tr v-for="(item, index) in dataFetched.data" v-bind:key="index">
        <th scope="row" v-for="(itemName, index) in itens" v-bind:key="index">
          {{ getPropertyFromObject(item, itemName.item) }}
        </th>
      </tr>
    </tbody>
  </table>
</template>

<script>
export default {
  props: ["dataFetched", "itens"],
  data() {
    return {
      filteredData: null,
    };
  },
  methods: {
    getPropertyFromObject(obj, item) {
      return item.split(".").length > 1
        ? obj[item.split(".")[0]][item.split(".")[1]]
        : obj[item];
    },
    filterData(event) {
      const filterValue = event.target.name;
      console.log(this.getPropertyFromObject(this.data, filterValue));
    },
  },
};
</script>

<style scoped>
input {
  width: 80%;
  position: relative;
  display: table-cell;
  background: var(--background);
  border: 1px solid white;
  color: white;
}

input:focus,
input:focus-visible {
  border: 1px solid var(--background-darker);
}

table {
  width: 100%;
  border-collapse: collapse;
  background-color: var(--background-darker);
}

thead th {
  vertical-align: bottom;
  padding: 0.75rem;
}

th {
  border: 1px solid rgba(0, 0, 0, 0.2);
  padding: 0.25rem 0.1rem;
}

tbody tr:nth-of-type(2n + 1) {
  background-color: var(--background);
}
</style>
