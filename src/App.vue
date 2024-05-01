<template>
  <h1>CRYPTO</h1>
  <Input :chamngeAmount="chamngeAmount" :convert="convert"/>
  <p v-if="error != ''">{{ error }}</p>
  <div class="selectors">
    <Selector :setCrypto="setCryptoFirst" />
    <Selector :setCrypto="setCryptoSecond" />
  </div>
  
</template>

<script>
import Input from './components/input.vue'
import Selector from './components/Selector.vue'

export default {
  components: { Input, Selector },
  data () {
    return {
      amount: 0,
      cryptoFirst: '',
      cryptoSecond: '',
      error: '',
    }
  },
  methods: {
    chamngeAmount(val) {
      this.amount = val
    },
    setCryptoFirst(val) {
      this.cryptoFirst = val
    },
    setCryptoSecond(val) {
      this.cryptoSecond = val
    },
    convert(){
      if(this.amount <= 0) {
        this.error = "Введите число больше 0";
        return;
      } else if (this.cryptoFirst == this.cryptoSecond) {
        this.error = 'Выберете разные валюты';
        return;
      } else if (this.cryptoFirst == '' || this.cryptoSecond == '') {
        this.error = 'Выберете валюту';
        return;
    }this.error = '';
  }
    
    
  }
}
</script>



<style scoped>
.selectors {
  display: flex;
  justify-content: space-between;
  width: 500px;
  margin: 0 auto;
}
</style>
