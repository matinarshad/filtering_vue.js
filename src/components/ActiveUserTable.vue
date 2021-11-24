<template>
  <h4 style="text-align: center">
    Active clients, and the number of active users for the particular client
  </h4>
  <table class="table">
    <thead>
      <tr>
        <th scope="col">#</th>
        <th scope="col">Name</th>
        <th scope="col">Active</th>
        <th scope="col">Users</th>
      </tr>
    </thead>
    <tbody>
      <tr
        v-for="item in companies.filter((company) => company.is_active == true)"
        :key="item.id"
      >
        <td>
          <img :src="item.company_logo" />
        </td>
        <td>{{ item.company_name }}</td>
        <td>{{ item.is_active }}</td>
        <td>{{ item.users.length }}</td>
      </tr>
    </tbody>
  </table>
</template>

<script>
export default {
  name: "ActiveUserTable",
  props: {
    companies: {
      type: Array,
      default: () => [],
    },
  },
};
</script>
