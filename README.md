## 前置准备
1.需要在本地开启网易云接口服务，接口服务在我另一个仓库[Api](https://github.com/Hay-J/NeteaseCloudMusicApi-Clone4.0.23.git)，服务开启后，就不用管了；
2.修改utils/request.js下的baseUrl为本地ip地址，例如："http://192.168.0.105:3000"，注：这里不用localhost是因为在小程序端实机调试时会获取不到数据，且实机调试时手机和电脑网络需要在同一局域网下

## 安装
```
$ git clone https://github.com/Hay-J/My-NeteaseMusic.git
$ npm install
```
## 运行
```
1.在Hbuilder打开工程文件，点击“运行到浏览器”或者是“小程序模拟器”
2.在浏览器访问http://localhost:8081/，注意网页需要打开调试模式切换为移动设备
```
## 项目预览
1. <img src="README.assets/image-20211130152154539.png" alt="首页" style="zoom:50%;" />

首页这里有骨架屏加载动效（只在首页加了，其他页面加可以参考uview），为了体现效果延时了0.5s，可在pages/index下修改

2. <img src="README.assets/image-20211130153545390.png" alt="歌单列表" style="zoom:50%;" />

这个页面没什么特殊功能，不过布局要注意的地方蛮多的

3. <img src="README.assets/image-20211130152654685.png" alt="搜索页-默认" style="zoom: 50%;" />

<img src="README.assets/image-20211130152742908.png" alt="搜索页-搜索推荐" style="zoom: 50%;" />

<img src="README.assets/image-20211130152817032.png" alt="搜索页-结果页" style="zoom:50%;" />

搜索页包含三个页面，根据不同情况显示不同的页面，默认进来显示热门搜索和历史搜索，如果有历史搜索则显示，没有则不显示，且历史搜索唯一且置顶；

当在搜索框输入搜索词会根据搜索词请求搜索推荐的接口，这里做了防抖，减少对接口请求次数；

点击搜索时，显示搜索结果页，这个页面实现了上拉（点击）加载更多和返回顶部功能，返回顶部也做了防抖。

4. <img src="README.assets/image-20211130153903582.png" alt="播放页1" style="zoom:50%;" />

<img src="README.assets/image-20211130153929667.png" alt="播放页2" style="zoom:50%;" />

<img src="README.assets/image-20211130154006436.png" alt="播放页3" style="zoom:50%;" />

<img src="README.assets/image-20211130154042171.png" alt="播放页4" style="zoom:50%;" />

播放页面也是这个项目最主要的部分，实现了自动播放（这个在H5有时候不行，小程序肯定可以，有需要可以分开处理，让H5不自动播放，我这里没分开，我懒= =）、歌词滚动、自动续播、上下一首、一键收听、上拉（点击）加载更多、播放列表等功能。

