<template>
    <div id="clock">
        <p class="date">{{ date }}</p>
        <p class="time">{{ time }}</p>
        <p class="text">MY DIGITAL CLOCK</p>
    </div>
</template>
<style language="scss">
    p {
        margin: 0;
        padding: 0;
    }
    #clock {
        font-family: 'Share Tech Mono', monospace;
        color: #0f0f0f;
        text-align: center;
        position: absolute;
        left: 50%;
        top: 50%;
        transform: translate(-50%, -50%);
        color: #656768;
        text-shadow: 0 0 20px rgba(10, 175, 230, 1),  0 0 20px rgba(10, 175, 230, 0);
    }
    .time {
        letter-spacing: 0.05em;
        font-size: 80px;
        padding: 5px 0;
    }
    .date {
        letter-spacing: 0.1em;
        font-size: 24px;
    }
    .text {
        letter-spacing: 0.1em;
        font-size: 12px;
        padding: 20px 0 0;
    }
    
</style>

<script>
import Vue from 'vue'
export default {

    DigitalClock(){
        var clock = new Vue({
            el: '#clock',
            data () {
                return {
                    time: '',
                    date: ''
                }
            }
        });

        var week = ['SUN', 'MON', 'TUE', 'WED', 'THU', 'FRI', 'SAT'];
        setInterval(updateTime, 1000);
        updateTime();
        function updateTime() {
            var cd = new Date();
            clock.time = zeroPadding(cd.getHours(), 2) + ':' + zeroPadding(cd.getMinutes(), 2) + ':' + zeroPadding(cd.getSeconds(), 2);
            clock.date = zeroPadding(cd.getFullYear(), 4) + '-' + zeroPadding(cd.getMonth()+1, 2) + '-' + zeroPadding(cd.getDate(), 2) + ' ' + week[cd.getDay()];
        }

        function zeroPadding(num, digit) {
            var zero = '';
            for(var i = 0; i < digit; i++) {
                zero += '0';
            }
            return (zero + num).slice(-digit);
        }
    }
}
</script>