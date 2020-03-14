<template>
  <div class="hello">
    <dg-table :columns="columns" :datas="users">
      <template slot="firstName" slot-scope="data">{{ data.value['firstName'] }}</template>
      <template slot="lastName"  slot-scope="data">{{ data.value['lastName'] }}</template>
      <template slot="fullName"  slot-scope="data">{{ data.value['fullName'] }}</template>
    </dg-table>
  </div>
</template>

<script>
import DgTable from "./DgTable";

export default {
  name: "HelloWorld",
  components: {
    "dg-table": DgTable
  },
  data() {
    return {
      users:[
        {firstName: 'km', lastName: 'wang', fullName: 'km wang'},
        {firstName: 'jeff', lastName: 'liao', fullName: 'jeff wang'},
      ],
      columns:['firstName', 'lastName', 'fullName']
    };
  }
};
</script>

<style scoped>
h2 {
  font-weight: normal;
}
</style>
