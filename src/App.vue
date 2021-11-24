<template>
  <div class="col-lg-8 mx-auto p-3 py-md-5">
    <header class="d-flex align-items-center pb-3 mb-5 border-bottom">
      <a
        href="/"
        class="d-flex align-items-center text-dark text-decoration-none"
      >
        <span class="fs-4">📚 SingleView Task 1: Filtering</span>
      </a>
    </header>

    <main>
      <h1>Clients</h1>
      <p class="fs-5">
        Below is a table that contains a generated list of clients. The task is
        to only display active clients and active users
      </p>

      <div class="row g-5">
        <div class="col-md-12">
          <Table :companies="computedCompanies" />
        </div>
        <div class="col-md-12">
          <ActiveUserTable :companies="computedCompanies" />
        </div>
      </div>
    </main>
    <footer class="pt-5 my-5 text-muted border-top">SingleView</footer>
  </div>
</template>

<script>
import Companies from "../example_data/data.json";
import Table from "../src/components/Table";
import ActiveUserTable from "../src/components/ActiveUserTable";

export default {
  name: "App",
  components: {
    Table,
    ActiveUserTable,
  },
  computed: {
    computedCompanies() {
      return Companies;
    },
  },
};
</script>

<style>
@import "~bootstrap/dist/css/bootstrap.css";
</style>
