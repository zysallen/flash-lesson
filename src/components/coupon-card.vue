<template>
    <div class="card" :class="{disabled}">
        <div class="top">
            <span>{{name}}</span>
            <div>{{ disabled ? '已领取' : '立即领取' }}</div>
        </div>
        <div class="bottom">有效日期：领取{{date}}天内有效</div>
    </div>
</template>

<script>
    export default {
    	props: ['name','date','disabled'],
    }
</script>

<style lang="scss" scoped>
    $couponBg: 'https://s1.ax1x.com/2018/09/20/imZYe1.png';
    .card {
        background-image: url($couponBg);
        background-size: 100% 100%;
        background-repeat: no-repeat;
        width: 90vw;
        height: 140px;  
        display: flex;
        flex-direction: column;
        justify-content: space-between;
        padding-top: 20px;
        padding-bottom: 30px;
        box-sizing: border-box;
        margin-bottom: 15px;
        .top {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding-left: 45px;
            padding-right: 10px;
            span {
                font-size: 24px;
                color: white;
            }
            div {
                height: 26px;
                width: 78px;
                line-height: 26px;
                background: white;
                color: #ff0000;
                font-size: 12px;
                text-align: center;
                border-radius: 13px;
            }
        }
        .bottom {
            font-size: 14px;
            color: #333;
            padding-left: 12px;
        }
    }
    .disabled {
        filter: grayscale(100%);
    }
</style>
