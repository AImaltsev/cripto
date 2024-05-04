<template>
  <ul>
    <li @click="setCrypto('BTC')" :class="{ 'active': cryptoNow === 'BTC' }">Bitcoin</li>
    <li @click="setCrypto('ETH')" :class="{ 'active': cryptoNow === 'ETH' }">ETH</li>
    <li @click="setCrypto('USDT')" :class="{ 'active': cryptoNow === 'USDT' }">USDT</li>
  </ul>
</template>

<script>
export default {
  props: {
    setCrypto: {
      type: Function,
      required: true,
    },
    cryptoNow: {
      type: String,
      required: true,
    }
  },
  data() {
    return {
      current: ''
    }
  },

}
</script>

<style scoped>
ul {
  list-style: none;
  width: 200px;
  padding: 0;
  border-radius: 3px;
  border: 3px solid #000;
}

li {
  display: block;
  background: #1a032d;
  color: #fff;
  padding: 20px 0;
}

li:hover, li:active {
  background: #24043e;
  cursor: pointer;
}

.active {
  background: #24043e;
}
</style>