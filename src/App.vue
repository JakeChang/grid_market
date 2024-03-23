<template>
    <div class="w-full h-screen grid grid-cols-3">
        <TradingView container="container1" symbol="COINBASE:BTCUSD"></TradingView>
        <TradingView container="container2" symbol="COINBASE:ETHUSD"></TradingView>
        <TradingView container="container3" symbol="COINBASE:ADAUSD"></TradingView>
        <TradingView container="container4" symbol="COINBASE:MATICUSD"></TradingView>
        <TradingView container="container5" symbol="COINBASE:LINKUSD"></TradingView>
        <TradingView container="container6" symbol="COINBASE:GMTUSD"></TradingView>
    </div>
</template>

<script>
// import { onMounted } from 'vue';
import TradingView from './components/TradingView.vue';

export default {
    name: 'App',
    components: {
        TradingView,
    },
}
</script>
