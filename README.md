<!--index.wxml-->
<view class="container">
  <image src='{{src}}' mode='widthFix'></image>
  <text>{{name}}</text>
  <button open-type="getUserInfo" bindtap="getMyInfo">
        点击获取头像和昵称
  </button>
</view>
