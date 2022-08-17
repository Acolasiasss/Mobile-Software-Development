完整代码展示：**

## **完整代码展示：**
**app.json文件的完整代码如下：**
```
{
  "pages":[
    "pages/index/index"
  ],
  "window":{
    "backgroundTextStyle":"light",
    "navigationBarBackgroundColor": "#228811",
    "navigationBarTitleText": "我的微信小程序",
    "navigationBarTextStyle":"white"
  },
  "style": "v2",
  "sitemapLocation": "sitemap.json"
}
```
**WXML文件（pages/index/index.wxml）的完整代码如下：**
```
<!--index.wxml-->
<view class="container">
  <image src='{{src}}' mode='widthFix'></image>
  <text>{{name}}</text>
  <button open-type="getUserInfo" bindtap="getMyInfo">
        点击获取头像和昵称
  </button>
</view>
```
**WXSS文件(pages/index/index.wxss)的完整代码如下：**
```
/**index.wxss**/
.container{
  height:100vh;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: space-around;
}

image{
  width:300rpx;
  border-radius: 50%;
}
```
**JS文件(pages/index/index.js)的完整代码如下：**
```
// index.js
const app = getApp()

Page({
  data: {
    src: '../../images/logo.png',
    name: '新用户'
  },

  onLoad() {
    if (wx.getUserProfile) {
      this.setData({
        canIUseGetUserProfile: true
      })
    }
  },

  getMyInfo: function(e) {
    wx.getUserProfile({
      desc: '展示用户信息', 
      success: (res) => {
        console.log(res)
        this.setData({
          src: res.userInfo.avatarUrl,
          name: res.userInfo.nickName
        })
      }
    })
  },

})
```


id: 77626d2181f4482db2ddcc782a223684
parent_id: 608ba7a941b84d50afa0f6f54d336520
created_time: 2022-08-17T07:00:37.982Z
updated_time: 2022-08-17T07:06:36.502Z
is_conflict: 0
latitude: 34.77320000
longitude: 113.72200000
altitude: 0.0000
author: 
source_url: 
is_todo: 0
todo_due: 0
todo_completed: 0
source: joplin-desktop
source_application: net.cozic.joplin-desktop
application_data: 
order: 0
user_created_time: 2022-08-17T07:00:37.982Z
user_updated_time: 2022-08-17T07:06:36.502Z
encryption_cipher_text: 
encryption_applied: 0
markup_language: 1
is_shared: 0
share_id: 
conflict_original_id: 
master_key_id: 
type_: 1