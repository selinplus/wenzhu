<template>
    <div class="container">
        <div class="logo">
            <img src="../../../static/imgs/wenzhu_title.png">
        </div>
        <div class="description">
            <ul>
                <li class="title" @click="whg">无花果栽植技术推广:15098663307</li>
                <li class="title" @click="lanmei">蓝莓栽植技术推广:15098663307</li>
                <li class="title" @click="dayingtao">大樱桃栽植技术推广:18660044166</li>
            </ul>
        </div>
        <div class="address">地址:山东省烟台市福山区张格庄镇姜家村(村中)</div>
        <div id="content">
            <ul>
                <li class="img-t" v-for="(ad,index) in tips" :key="index">
                    <img :src="ad.src" :data-list="tips" :data-src="ad.src" class="intro-img" @click="previewImg">
                </li>
            </ul>
        </div>
    </div>

</template>
<script>
    export default {
      data () {
        return {
          bigear: null,
          tips: [
            {src: 'https://res.cloudinary.com/selinplus/image/upload/v1532335028/business/wenzhu/1.png'},
            {src: 'https://res.cloudinary.com/selinplus/image/upload/v1532335028/business/wenzhu/2.png'},
            {src: 'https://res.cloudinary.com/selinplus/image/upload/v1532335028/business/wenzhu/3.png'},
            {src: 'https://res.cloudinary.com/selinplus/image/upload/v1532335028/business/wenzhu/4.png'},
            {src: 'https://res.cloudinary.com/selinplus/image/upload/v1532335028/business/wenzhu/5.png'},
            {src: 'https://res.cloudinary.com/selinplus/image/upload/v1532335028/business/wenzhu/6.png'}
          ],
          logoinfo: null
        }
      },
      methods: {
        previewImg (e) {
          const src = e.currentTarget.dataset.src
          const imgList = e.currentTarget.dataset.list
          let dealList = []
          imgList.forEach(element => {
            dealList.push(element.src)
          })
          wx.previewImage({
            current: src,
            urls: dealList
          })
        },
        whg () {
          wx.makePhoneCall({
            phoneNumber: '15098663307'
          })
        },
        lanmei () {
          wx.makePhoneCall({
            phoneNumber: '15098663307'
          })
        },
        dayingtao () {
          wx.makePhoneCall({
            phoneNumber: '18660044166'
          })
        }
      },
      onShareAppMessage: function (res) {
        return {
          title: '文竹园林',
          path: '/pages/index/main',
          imageUrl: '/static/imgs/zhuzi.png'
        }
      }
    }
</script>
<style scoped>
.container {
    display: grid;
    grid-template-rows: 40px 150px 30px auto;
    grid-template-columns: auto;
    align-items: center;
    padding: 5px 10px;
    margin: 0;
}
.logo {
    padding:10px;
    border-bottom:1px solid gray;
}
div img {
    width: 85vw;
    height:30px;
}
.description {
    font-size: 16px;
    padding: 10px 0;
    margin-bottom: 20px;
    text-align: center;
    color:#3d5b04;
    font-family:'Times New Roman', Times, serif;
}
.address {
    font-family:'Times New Roman', Times, serif;
    color:#3d5b04;
    font-size: 16px;
    border-bottom: 1px outset gray;
}
#content{
    display: grid;
    grid-template-columns: auto;
    grid-template-rows: auto;
    justify-content: center;
}
ul {
    list-style-type:circle;
    perspective: 1000px;
    justify-content: center;
    display: flex;
    flex-wrap: wrap;
}
.img-t {
    border-radius: 10px;
    border: 1px outset gray;
    padding: 5px;
    margin: 5px;
}
.title {
    text-align: center;
    border-bottom: 1px solid gray;
    padding: 10px;
    margin: 0;
}
li img {
    border: 3px rgba(10,20,100,.2);
    width: 35vw;
    height: 35vw;
    border-style:groove;
    align-self: center;  
}
</style>
