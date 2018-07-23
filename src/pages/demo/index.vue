<template>
    <div class="container">
        <div class="head" >
            <!-- <div class="logo" :animation="logoinfo"><img src="../../../static/imgs/bigear.png" alt=""></div> -->
            <div class="title" :animation="bigear">山东大耳朵软件</div>
        </div>
        <div class="description"  @click="callme" >联系电话:132-8799-1199</div>
        <div id="content">
            <ul>
                <li>
                    <!-- <img src="../../../static/imgs/wechat-service-and-miniapp.jpg" alt=""> -->
                    <span>
                        <strong>小程序（公众号）</strong>
                        <p>定制开发、运营小程序，为企业提供新媒体推广。</p>
                    </span>
                </li>
                <li>
                    <!-- <img src="../../../static/imgs/rnn.jpg" alt=""> -->
                    <span>
                        <strong>深度学习(人工智能)</strong>
                        <p>专注于递归神经网络（RNN）在企业级生产中的应用</p>
                    </span>
                </li>
                <li>
                    <!-- <img src="../../../static/imgs/d3js.jpg" alt=""> -->
                    <span>
                        <strong>大数据</strong>
                        <p>主要方向为数据多维展示和抽象，致力于探索大数据可视化和数据内联逻辑开发。</p>
                    </span>
                </li>
            </ul>
        </div>
        <div class="footer"></div>
    </div>

</template>
<script>
    export default {
      data () {
        return {
          bigear: null,
          logoinfo: null
        }
      },
      methods: {
        callme () {
          wx.makePhoneCall({
            phoneNumber: '13287991199'
          })
        }
      },
      created () {
        const animation = wx.createAnimation({
          transformOrigin: '50% 50%',
          duration: 2000,
          timingFunction: 'ease-in-out',
          delay: 500
        })
        animation.rotateX(30).step({ duration: 1000 })
        animation.translate(0, 30).step({ duration: 2000 })
        animation.scale(1.3).step({ duration: 1000 })
        this.bigear = animation.export()
        this.logoinfo = animation.export()
      },
      onShareAppMessage: function (res) {
        return {
          title: '大耳朵软件',
          path: '/pages/demo/main',
          imageUrl: '/static/imgs/bigear_mini.png'
        }
      }
    }
</script>
<style scoped>
.container {
    display: grid;
    grid-template-rows: 100px 80px auto 30px;
    align-self: center;
    padding: 0;
}
.head {
    display: flex;
    line-height: auto;
    margin: 0;
    padding: 0;
    background: linear-gradient(#0e5ba3, #88b183);
}
.title {
    padding:0;
    padding-left: 25px;
    line-height: 120px;
    font-size: 26px;
    font-weight: 500;
    color:white;
}

.head img {
    padding: 0 10px;
    width:80px;
    height: 80px;

}
.description {
    font-size: 16px;
    padding: 10px 0;
    background: linear-gradient(#88b183,#0e5ba3);
    margin-bottom: 20px;
    text-align: center;
    color:white;
    border-bottom: 3px #1a3cac;
    border-bottom-style: inset;
    font-family:'Times New Roman', Times, serif;
}
.content{
    display: grid;
    border: 3px solid fuchsia;
    grid-template-columns: 5% auto 5%;
    grid-template-rows: auto;
    justify-content: center;
}

ul {
    list-style-type: none;
    perspective: 1000px;
    align-self: center;
}
ul li {
    display: grid;
    width: 85%;
    grid-template-rows: auto 10%;
    border-radius: 10px;
    padding: 10px;
    margin: 5px 10px;
}
li img {
    border: 3px rgba(10,20,100,.2);
    width: 85%;
    border-style:groove;
    align-self: center;
    justify-self: center;
}
span {
    align-self: center;
    justify-self: center;
}
span strong{
    font-size: 18px;
    color:coral;
    font-weight: bold;
    font-family: 'Courier New', Courier, monospace;
}
span p{
    font-size: 16px;
    color:#161d27;
    font-family:'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
}
ul li:nth-child(1) {
    background: #ccb3cc;
}
ul li:nth-child(2) {
    background: #a1dfc7;
}
ul li:nth-child(3) {
    background: #a1ce66;
}
.footer {
    font-size: 18px;
    color:chartreuse;
    line-height: 180px;
}
</style>
