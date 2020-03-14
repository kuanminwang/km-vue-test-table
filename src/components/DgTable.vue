<template>
  <div class="container">
    <table>
      <thead>
        <tr>
          <th v-for="column in columns" :key="column">{{ column }}</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="(data, idx) in datas" :key="idx">
          <td v-for="column in columns" :key="column">
            <slot :name="column" :value="data"></slot>
          </td>
        </tr>
      </tbody>
    </table>
  </div>
</template>

<script>
export default {
  props: {
    columns: {
      type: Array,
      required: true
    },
    datas: {
      type: Array,
      required: true
    }
  },
  data() {
    return {
      status: "critical"
    };
  },
  methods: {
    changeStatus() {
      this.status = "normal";
    }
  }
};
</script>

<style>
  table{
    border: 1px solid black;
  }
</style>
