<template>
  <div class="hello">
    <input type="text" v-model="name" />
    <button @click.prevent="Reset">Reset</button>
    <payment></payment>
  </div>
</template>

<script>
import Payment from "./Payment";

const initial = {
  name: "Name",
};
export default {
  components: {
    payment: Payment,
  },
  name: "HelloWorld",
  props: {
    msg: String,
  },
  data() {
    return initial;
  },
  methods: {
    Reset() {
      this.$data = { ...this.$data, ...initial };
      alert(this.$data.name);
    },
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
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
