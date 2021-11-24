<template>
  <table class="table">
    <thead>
      <tr>
        <th scope="col">#</th>
        <th scope="col">Name</th>
        <th scope="col">Account Balance</th>
        <th scope="col">System Start Date</th>
        <th scope="col">Active</th>
        <th scope="col">Users</th>
      </tr>
    </thead>
    <tbody>
      <tr v-for="item in companies" :key="item.id">
        <td>
          <img :src="item.company_logo" />
        </td>
        <td>{{ item.company_name }}</td>
        <td>{{ item.balance }}</td>
        <td>{{ item.system_start_date }}</td>
        <td>{{ item.is_active }}</td>
        <td>{{ item.users.length }}</td>
      </tr>
    </tbody>
  </table>
</template>

<script>
export default {
  name: "Table",
  props: {
    companies: {
      type: Array,
      default: () => [],
    },
  },
};
</script>
