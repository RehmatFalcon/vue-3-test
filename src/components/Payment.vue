<template>
  <h3>Payment</h3>
  Paid: <input type="number" v-model="paymentData.paid" /> <br />
  Discount:
  <input type="number" v-model="paymentData.discount" />
  <br />
  Total:
  <input type="number" disabled v-model="totalPaid" />
</template>
<script lang="ts">
import { reactive, computed } from "vue";
export default {
  setup() {
    const paymentData = reactive({
      paid: 0,
      discount: 0,
    });
    const totalPaid = computed(
      () =>
        parseFloat(paymentData.paid || 0) +
        parseFloat(paymentData.discount || 0)
    );
    return {
      paymentData,
      totalPaid,
    };
  },
};
</script>