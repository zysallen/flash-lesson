<template>
    <div class="container">
        <div class="wave">
            <h3>极速刷小程序 </h3>
            <h3>大学生的神器</h3>
        </div>

        <div class="start" @click="start">点击开启</div>
    </div>
</template>

<script>

    export default {
    	data() {
    		return {
    			motto: 'Hello World',
    			userInfo: {}
    		}
    	},
    	methods: {
    		start() {
    			const url = '../home/main'
    			wx.switchTab({ url })
    		},
    		getUserInfo() {
    			// 调用登录接口
    			wx.login({
    				success: () => {
    					wx.getUserInfo({
    						success: res => {
    							this.userInfo = res.userInfo
    						}
    					})
    				}
    			})
    		}
    	},

    	created() {
    		// 调用应用实例的方法获取全局数据
    		// this.getUserInfo()
    	}
    }
</script>

<style lang="scss" scoped>
    //跳过图床
    $waveBg: 'https://s1.ax1x.com/2018/09/19/iewV76.png';

    .wave {
    	width: 100vw;
    	height: 45vh;
    	background-size: 100% 100%;
        background-repeat: no-repeat;
        box-sizing: border-box; 
        padding-top: 15vh;
        background-image: url($waveBg);
        h3{
            font-size: 30px;
            color: white;
            margin: 0 auto;
            width: 100%;
            text-align: center;
        }
    }
    .start {
        width: 50vw;
        height: 36px;
        line-height: 36px;
        font-size: 18px;
        color: white;
        border-radius: 18px;
        background: #2400ff;
        font-weight: bold;
        text-align: center;
        margin: 0 auto;
        margin-top: 15vh;
    }
</style>
