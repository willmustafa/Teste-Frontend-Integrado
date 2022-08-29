<template>
  <main>
    <div class="container">
      <CardContainer>
        <TableStriped :dataFetched="data" :itens="itens" />
      </CardContainer>
    </div>
  </main>
</template>

<script>
import axios from "axios";
import CardContainer from "../components/CardContainer.vue";
import TableStriped from "../components/TableStriped.vue";

export default {
  data() {
    return {
      data: null,
      itens: [
        { label: "Nome", item: "name" },
        { label: "Cidade", item: "address.city" },
        { label: "Empresa", item: "company.name" },
        { label: "Telefone", item: "phone" },
        { label: "Email", item: "email" },
        { label: "Categorias", item: "company.bs" },
      ],
    };
  },
  created() {
    this.fetchData();
  },
  methods: {
    async fetchData() {
      await axios
        .get("https://jsonplaceholder.typicode.com/users")
        .then((res) => (this.data = res.data));
    },
  },
  components: { CardContainer, TableStriped },
};
</script>

<style scoped></style>
