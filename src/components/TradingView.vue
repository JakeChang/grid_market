<template>
    <div :class="container" style="height:100%;width:100%">
        <div class="tradingview-widget-container__widget" style="height:calc(100% - 32px);width:100%"></div>
        <div class="tradingview-widget-copyright"><a href="https://tw.tradingview.com/" rel="noopener nofollow"
                target="_blank"><span class="blue-text">追蹤TradingView上的所有市場</span></a></div>
    </div>
</template>

<script >
import { onMounted } from 'vue';

export default {
    name: 'TradingView',
    props: ['container', 'symbol'],
    setup(props) {

        function setView(container, symbol) {
            console.log(container);
            const widgetPlaceholder = document.getElementsByClassName(container)[0];
            widgetPlaceholder.replaceChildren();
            const script = document.createElement('script');
            script.src = 'https://s3.tradingview.com/external-embedding/embed-widget-advanced-chart.js'
            script.async = true;
            script.innerHTML = JSON.stringify({
                "autosize": true,
                "symbol": symbol,
                "interval": "H",
                "timezone": "Asia/Taipei",
                "theme": "light",
                "style": "1",
                "locale": "zh_TW",
                "enable_publishing": false,
                "allow_symbol_change": true,
                "calendar": false,
                "support_host": "https://www.tradingview.com"
            });
            widgetPlaceholder.appendChild(script);
        }

        onMounted(() => {
            setView(props.container, props.symbol);
        });
    },
}
</script>
