# webapp-Flexible
# 移动端页面开发之——lib-flexible.js

# 1.前置知识了解
    设备像素比（dpr） ＝ 物理像素 / 设备独立像素
## 反正我看到上面的那几个专业知识点就是一脸闷逼，都是些啥东西哦~~~~~我一直觉得学习知识就因该浅显简单明了。PS：推荐大家去看看《三傻大闹宝莱坞》，反正我的大学是白读了~~~~~跑题了！！！！！！！！！！！

#这就是我的理解：
    dpr= 屏幕像素/css像素
以iphone6为例子：iPhone6的设备宽度和高度为375pt * 667pt，pt不要管什么鬼东西，就当是没有或者px
。老子又不搞那麽复杂的， 而其dpr为2，根据上面公式，我们可以很轻松得知其物理像素为750pt * 1334pt

#  好好好------收    回正题----------------

lib—Flexible.js使用rem单位，根据<html>的font-size计算出元素的盒模型大小。
# Flexible会将视觉稿分成100份（主要为了以后能更好的兼容vh和vw），而每一份被称为一个单位a。同时1rem单位被认定为10a。~~~~~这特么又是一段晦涩的话。
### 你就不能直接给个公式，让我们套用就可以了嘛》》》》
   10a=1rem=视觉稿尺寸/10（特么不就是UI给我们的PSD文件尺寸）
# 对于视觉稿上的元素尺寸换算，只需要原始的px值除以rem基准值即可。假如设计稿宽度为750px,其中某div宽度为200px*200px，尺寸可以转换成为:
100a=10rem=750px ===> 1rem=75px
# 200/75 * 200/75 = 2.666rem*2.666rem


#  使用注意点：
# 1. 直接用阿里提供的官方cdn：<script src="http://g.tbcdn.cn/mtb/lib-flexible/0.3.4/??flexible_css.js,flexible.js"></script>
# 2. 或者将插件下载到本地，然后引入flexible_css.js和flexible.js文件

# 3.元素宽高一律用rem来指定
# 4. 不必手动指定根元素的font-size
# 5. 不必手动指定meta标签

# 6.文字大小用px，如：
div {
width: 10rem;
height: 4rem;
font-size: 12px; // 默认写上dpr为1的font-size
}
[data-dpr="2"] div { font-size: 24px; }
[data-dpr="3"] div { font-size: 36px; }


#   最后——————————————
# 打开控制台看看效果咯~~~~~~~~~~~~~~~~~~~~ 