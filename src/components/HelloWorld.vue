<template>
  <div class="hello container">
    <b-form class="row">
      <b-form-group class="col-4">
        <label for>Valor</label>
        <b-form-input v-model="valor"/>
      </b-form-group>
      <b-form-group class="col-4">
        <label for>Margem (%)</label>
        <b-input v-model="margem"/>
      </b-form-group>
      <b-form-group class="col-4">
        <label for>Valor Total</label>
        <b-input disabled v-model="valorTotal"/>
      </b-form-group>
    </b-form>
  </div>
</template>

<script>
export default {
  name: "HelloWorld",
  data() {
    return {
      valor: 0,
      margem: 0.77
    };
  },
  computed: {
    valorTotal() {
      return Number(this.valor * (this.margem / 100 + 1)).toFixed(2);
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
