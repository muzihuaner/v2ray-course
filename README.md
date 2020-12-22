# v2ray-course
<h2 id="user-content-前言">前言</h2>
<p>什么是V2ray?</p>
<p><a href="https://www.v2ray.com/" rel="nofollow">V2Ray(Project V)</a>&nbsp;相对于 Shadowsocks，V2Ray 更像全能选手，拥有更多可选择的协议 / 传输载体 (Socks、HTTP、TLS、TCP、mKCP、WebSocket )，还有强大的路由功能，不仅仅于此，它亦包含 Shadowsocks 组件，你只需要安装 V2Ray，你就可以使用所有的 V2Ray 相关的特性包括使用 Shadowsocks，由于 V2Ray 是使用 GO 语言所撰写的，天生的平台部署优势，下载即可使用</p>
<h2>流程</h2>
<p>总结一下此文章的大致流程，此 V2Ray 教程可百分百帮助你搭建 V2Ray 使用。哪怕你只是一个小白。</p>
<ul>
<ul>
<li>购买一个 VPS<br />想要搭建 V2Ray，就必须要拥有一台 VPS。</li>
<li>获取 VPS 信息<br />我们必须要知道 VPS IP 地址，root 用户密码，SSH 端口</li>
<li>安装 SSH工具<br />要登录 VPS，当然需要 SSH 客户端</li>
<li>登录 VPS<br />使用 SSH 配置 VPS SSH 信息，然后登录</li>
<li>安装 V2Ray<br />安装过程你可以随意选择你喜欢的传输协议或者配置 Shadowsocks</li>
<li>V2Ray 安装完成<br />此时你可以使用客户端配置 V2Ray 使用了</li>




</ul>




</ul>
<h2 id="user-content-购买一个vps">购买一个VPS</h2>
<p>想要搭建 V2Ray， 拥有一个 VPS 是必需的。</p>
<p>这个嘛...为了避免广告嫌疑，自己看着买</p>
<p>哪个套餐好？<br />一般来说，推荐购买 香港线路&nbsp;或&nbsp;CN2 GIA 线路，或者哪个便宜选择那个，说着当然如果你使用量比较多或者想要分享给同学和朋友一起用的话，选择合适的套餐即可。又或者你土豪的话，选择最贵的也行。</p>
<p>VPS 速度：香港线路 &gt; CN2 GIA 线路 &gt; CN2 线路 &gt; 普通线路</p>
<p>香港套餐 VPS 的速度最快。&nbsp;如果你非常在乎速度的话，建议购买香港线路的 VPS，当然，但价格贵，流量相对其他套餐来说也是比较少的&hellip;&hellip;退一步的选择是 CN2 GIA 线路，这个线路的速度也比较好。</p>
<p>线路是比较重要的，像香港和 CN2 GIA 线路到晚上一般不会怎么炸，其他的到了晚上可能会出现很慢慢的感觉。</p>
<p>自己看情况买吧，嘿嘿~</p>
<h2>获取 VPS 信息</h2>
<p>这个一般在后台或者购买时发送给你的邮件里有</p>
<p><img src="https://img2020.cnblogs.com/blog/1783030/202012/1783030-20201222122947972-2062557553.png" alt="" loading="lazy" /></p>
<p>&nbsp;</p>
<h2>&nbsp;安装 SSH工具</h2>
<p>这个工具是用来连接VPS的</p>
<p><strong>PC端</strong></p>
<p><strong>XShell：</strong></p>
<p><strong>https://www.netsarang.com/zh/xshell/</strong></p>
<p><strong>FinalShell（我用的这个）</strong></p>
<p><strong>http://www.hostbuf.com/</strong></p>
<p><strong>手机端</strong></p>
<p><strong>安卓：</strong></p>
<p><strong>JuiceSSH</strong></p>
<p><strong>https://huangenet.lanzous.com/iguAEjlekmb</strong></p>
<p><strong>iOS：</strong></p>
<p><strong>Termius</strong></p>
<p><strong>https://apps.apple.com/cn/app/termius-ssh-client/id549039908</strong></p>
<h2><strong>登录 VPS</strong></h2>
<p><strong>这里以XShell为例：</strong></p>
<p>在桌面找到 Xshell ，打开它，新建一个会话。</p>
<p><strong><img src="https://camo.githubusercontent.com/632f5ea0e0fb486c2640a5b65e8875bee3e5516151161104271d022148e52788/68747470733a2f2f692e6c6f6c692e6e65742f323031382f31322f32372f356332346630633864373866362e6a7067" alt="新建会话" data-canonical-src="https://i.loli.net/2018/12/27/5c24f0c8d78f6.jpg" /></strong></p>
<p>主机写上你的 VPS IP 地址，端口写上 SSH 端口。</p>
<p><strong><img src="https://camo.githubusercontent.com/8d885adc232ab1264573f38b5449579c1c7933c71917a25ee30a89588b7a9353/68747470733a2f2f692e6c6f6c692e6e65742f323031382f31312f31382f356266313638343733353737362e706e67" alt="new" data-canonical-src="https://i.loli.net/2018/11/18/5bf1684735776.png" /></strong></p>
<p>之后点击 用户身份验证，用户名：<code>root</code>，密码：你的 root 密码。然后点击确定</p>
<p><strong><img src="https://camo.githubusercontent.com/e8caa931333c3eb9fb6c500436390b0aea980d1d4862dffa6be0672977a741e9/68747470733a2f2f692e6c6f6c692e6e65742f323031382f31312f31382f356266313638343733376633632e706e67" alt="user-and-passwd" data-canonical-src="https://i.loli.net/2018/11/18/5bf1684737f3c.png" /></strong></p>
<p>之后选择连接。</p>
<p><strong><img src="https://camo.githubusercontent.com/407a5f1979b8d5a373499130d0826aa37b6e46c260ce9beb5ff774235d89e882/68747470733a2f2f692e6c6f6c692e6e65742f323031382f31312f31382f356266313638343733396161622e706e67" alt="连接" data-canonical-src="https://i.loli.net/2018/11/18/5bf1684739aab.png" /></strong></p>
<p>然后会提示SSH安全警告，选择，接受并保存。</p>
<p><strong><img src="https://camo.githubusercontent.com/396df3da4c4b550eb56983bb952e238ec8097fd0b7da194e4e153761c1164ddc/68747470733a2f2f692e6c6f6c692e6e65742f323031382f31312f31382f356266313566346230346337322e706e67" alt="SSH 安全警告" data-canonical-src="https://i.loli.net/2018/11/18/5bf15f4b04c72.png" /></strong></p>
<p>这是登录成功后的界面</p>
<p><strong><img src="https://camo.githubusercontent.com/fdf386dcf4c7fafbfd511c08ffa700337f813a7021b77b71dd95a8fa874e14f3/68747470733a2f2f692e6c6f6c692e6e65742f323031382f31312f31382f356266313566346230636433332e706e67" alt="登陆成功" data-canonical-src="https://i.loli.net/2018/11/18/5bf15f4b0cd33.png" /></strong></p>
<p>&nbsp;其他的软件基本差不多的连接步骤</p>
<h2 id="user-content-安装-v2ray">安装 V2Ray</h2>
<h3 id="toc-head-1">一键脚本</h3>
<p>这边推荐三个一键脚本，都是经过本人亲自测试过的，如果你是 CentOS 系统需要<strong><code>关闭防火墙</code></strong>或者<strong><code>放行相关端口</code></strong></p>
<div class="cnblogs_code">
<pre><span style="color: #000000;"># Centos关闭防火墙
systemctl stop firewalld.service
systemctl disable firewalld.service</span></pre>
</div>
<p>如果提示&nbsp;<code>curl: command not found</code>&nbsp;，那是因为你的 VPS 没装&nbsp;<code>curl</code>，安装命令：</p>
<div class="cnblogs_code">
<pre><span style="color: #000000;"># CentOS：
yum update </span>-y &amp;&amp; yum install curl -<span style="color: #000000;">y
# Debian</span>/<span style="color: #000000;">Ubuntu：
apt</span>-<span style="color: #0000ff;">get</span> update -y &amp;&amp; apt-<span style="color: #0000ff;">get</span> install curl -y</pre>
</div>
<h4 id="toc-head-2">1. 233boy 一键脚本</h4>
<p>Github地址：https://github.com/233boy/v2ray/wiki</p>
<p>233boy 的 V2Ray 搭建脚本貌似有 BUG 用户无法自定义端口，不过依然能够正常安装使用，支持单用户及多种协议，非常推荐</p>
<div class="cnblogs_code">
<pre># CentOS <span style="color: #800080;">7</span> 、Debian <span style="color: #800080;">8</span> 、Ubuntu <span style="color: #800080;">16</span> ，Debian <span style="color: #800080;">9</span><span style="color: #000000;">（推荐）
bash </span>&lt;(curl -s -L https:<span style="color: #008000;">//</span><span style="color: #008000;">git.io/v2ray.sh)</span></pre>
</div>
<p><img src="https://img2020.cnblogs.com/blog/1783030/202012/1783030-20201222124747787-1233204883.png" alt="" loading="lazy" /></p>
<p>&nbsp;</p>
<p>&nbsp;</p>
<p>&nbsp;</p>
<h4 id="toc-head-3">2. v2-ui 一键脚本</h4>
<p>GitHub 地址：<a href="https://github.com/sprov065/v2-ui" rel="nofollow" target="_blank">https://github.com/sprov065/v2-ui</a><br />支持多协议多用户的一键安装脚本，带有 WEB管理面板，详见作者 GitHub</p>
<div class="cnblogs_code">
<pre>bash &lt;(curl -Ls https:<span style="color: #008000;">//</span><span style="color: #008000;">blog.sprov.xyz/v2-ui.sh)</span></pre>
</div>
<h4 id="toc-head-4">3. multi-v2ray 一键脚本</h4>
<p>GitHub 地址：<a href="https://github.com/Jrohy/multi-v2ray" rel="nofollow" target="_blank">https://github.com/Jrohy/multi-v2ray</a><br />这是个脚本作者一直在维护，支持多用户及多种协议（详见作者 GitHub ）和 Docker 部署，不过个人觉得还是 233boy 版的好用</p>
<div class="cnblogs_code">
<pre><span style="color: #000000;"># 安装中文版
source </span>&lt;(curl -sL https:<span style="color: #008000;">//</span><span style="color: #008000;">multi.netlify.com/v2ray.sh) --zh</span></pre>
</div>
<p><img src="https://img2020.cnblogs.com/blog/1783030/202012/1783030-20201222125031412-1864860996.png" alt="" loading="lazy" /></p>
<p>&nbsp;</p>
<p>&nbsp;</p>
<p>&nbsp;安装方法看各自的使用说明，基本上都是&ldquo;傻瓜式&rdquo;安装</p>
<h3 id="toc-head-5">其他说明</h3>
<h4 id="toc-head-6">V2Ray 时间要求</h4>
<p>VPS 服务器时间与 V2Ray 客户端所在设备时间，两者最好保持一致，不要误差太大。这是 V2Ray 自身要求，与脚本无关。SSH 连接服务器，输入&nbsp;<code>date</code>&nbsp;命令，可以查看服务器时间。</p>
<p>如果时间不对，这样操作</p>
<div>
<div>
<p>软件时间： 查看方式 date，是是距离1970.1.1的时间差；</p>
<p>硬件时间： sudo hwclock -r，硬件时间是BIOS的时间。</p>
<p>&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; -w : 将软件时间写入到硬件时间；</p>
<p>&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; -r&nbsp; &nbsp;: 读取硬件时间。</p>
<p>查看并同步软件时间和硬件时间：</p>
</div>
</div>
<div class="cnblogs_code">
<pre>执行命令： sudo hwclock -w; hwclock -<span style="color: #000000;">r ; date

或者 sudo hwclock </span>--systohc</pre>
</div>
<h4 id="toc-head-7">V2Ray 协议说明</h4>
<div class="cnblogs_code">
<pre><span style="color: #000000;">没啥需求就用 TCP
追求更加安全就用 WS </span>+<span style="color: #000000;"> TLS
ISP 多作怪用动态端口
VPS 网络不好就用 mKCP</span></pre>
</div>
<h3>v2ray配置成功，客户端连接不上报错<code>context deadline exceeded</code>,</h3>
<p>必须关闭防火墙（或者开启对应v2ray端口和ss端口）</p>
<div class="cnblogs_code">
<pre><span style="color: #000000;">systemctl status firewalld.service #查看防火墙状态

systemctl stop firewalld.service #执行停止运行防火墙命令

systemctl disable firewalld.service #禁止防火墙自启动

防火墙其他命令

systemctl start firewalld.service #启动
systemctl enable firewalld.service #开机启动</span></pre>
</div>
<h2>V2ray客户端的使用</h2>
<ol><ol>
<li>
<p>Windows客户端下载地址：</p>
<table>
<thead>
<tr><th align="left">客户端</th><th align="left">下载地址</th></tr>
</thead>
<tbody>
<tr>
<td align="left">V2RayN（荐）</td>
<td align="left"><a href="https://github.com/2dust/v2rayN/releases" rel="nofollow" target="_blank">https://github.com/2dust/v2rayN/releases</a></td>
</tr>
<tr>
<td align="left">Clash</td>
<td align="left"><a href="https://github.com/Fndroid/clash_for_windows_pkg/releases" rel="nofollow" target="_blank">https://github.com/Fndroid/clash_for_windows_pkg/releases</a></td>
</tr>
<tr>
<td align="left">Mellow</td>
<td align="left"><a href="https://github.com/mellow-io/mellow/releases" rel="nofollow" target="_blank">https://github.com/mellow-io/mellow/releases</a></td>
</tr>
<tr>
<td align="left">Qv2ray</td>
<td align="left"><a href="https://github.com/Qv2ray/Qv2ray/releases" rel="nofollow" target="_blank">https://github.com/Qv2ray/Qv2ray/releases</a></td>
</tr>
</tbody>
</table>
</li>
<li>
<p>Mac客户端下载地址：</p>
<table>
<thead>
<tr><th align="left">客户端</th><th align="left">下载地址</th></tr>
</thead>
<tbody>
<tr>
<td align="left">V2RayU（荐）</td>
<td align="left"><a href="https://github.com/yanue/V2rayU/releases" rel="nofollow" target="_blank">https://github.com/yanue/V2rayU/releases</a></td>
</tr>
<tr>
<td align="left">ClashX</td>
<td align="left"><a href="https://github.com/yichengchen/clashX/releases" rel="nofollow" target="_blank">https://github.com/yichengchen/clashX/releases</a></td>
</tr>
<tr>
<td align="left">Mellow</td>
<td align="left"><a href="https://github.com/mellow-io/mellow/release" rel="nofollow" target="_blank">https://github.com/mellow-io/mellow/release</a></td>
</tr>
<tr>
<td align="left">Qv2ray</td>
<td align="left"><a href="https://github.com/Qv2ray/Qv2ray/releases" rel="nofollow" target="_blank">https://github.com/Qv2ray/Qv2ray/releases</a></td>
</tr>
</tbody>
</table>
</li>
<li>
<p>Linux客户端下载地址：</p>
<table>
<thead>
<tr><th align="left">客户端</th><th align="left">下载地址</th></tr>
</thead>
<tbody>
<tr>
<td align="left">Qv2ray</td>
<td align="left"><a href="https://github.com/Qv2ray/Qv2ray/releases" rel="nofollow" target="_blank">https://github.com/Qv2ray/Qv2ray/releases</a></td>
</tr>
<tr>
<td align="left">Mellow</td>
<td align="left"><a href="https://github.com/mellow-io/mellow/releases" rel="nofollow" target="_blank">https://github.com/mellow-io/mellow/releases</a></td>
</tr>
<tr>
<td align="left">V2rayL</td>
<td align="left"><a href="https://github.com/jiangxufeng/v2rayL/releases" rel="nofollow" target="_blank">https://github.com/jiangxufeng/v2rayL/releases</a></td>
</tr>
</tbody>
</table>
</li>
<li>
<p>安卓客户端下载地址：</p>
<table>
<thead>
<tr><th align="left">客户端</th><th align="left">下载地址</th></tr>
</thead>
<tbody>
<tr>
<td align="left">V2RayNG（荐）</td>
<td align="left"><a href="https://github.com/2dust/v2rayNG/releases" rel="nofollow" target="_blank">https://github.com/2dust/v2rayNG/releases</a></td>
</tr>
<tr>
<td align="left">Kitsunebi</td>
<td align="left"><a href="https://apkpure.com/kitsunebi/fun.kitsunebi.kitsunebi4android" rel="nofollow" target="_blank">https://apkpure.com/kitsunebi/fun.kitsunebi.kitsunebi4android</a></td>
</tr>
<tr>
<td align="left">BifrostV</td>
<td align="left"><a href="https://apkpure.com/bifrostv/com.github.dawndiy.bifrostv" rel="nofollow" target="_blank">https://apkpure.com/bifrostv/com.github.dawndiy.bifrostv</a></td>
</tr>
</tbody>
</table>
</li>
<li>
<p>iOS客户端客户端下载地址：<br />IOS目前没有发现免费的客户端，付费的有：Shadowrocket、pepi、i2Ray、Kitsunebi 和 Quantumult，需要去美区商店下载。</p>


</li>


</ol></ol>
<h3>使用方法：</h3>
<h2>Windows 客户端</h2>
<h2 id="下载-v2rayn">下载 V2RayN</h2>
<p>下载链接：<a href="https://github.com/2dust/v2rayN/releases/latest" rel="nofollow" target="_blank">&nbsp;https://github.com/2dust/v2rayN/releases/latest</a></p>
<p>然后选择 v2rayN-Core.zip 下载<br />下载好了之后，解压，然后打开解压的文件夹<br />目录结构大概如下图所示</p>
<p>
<img src="https://i.loli.net/2018/08/03/5b642bc166d29.png" alt="" loading="lazy" /></p>
<h2 id="获取-v2ray-客户端配置">获取 V2Ray 客户端配置</h2>
<p>SSH 登录你的 VPS （如果你没登录）<br />输入&nbsp;<code>v2ray url</code></p>
<p>然后复制 vmess 链接 （将链接全选，然后鼠标右键，再选择复制即可）</p>
<h2 id="配置-v2rayn">配置 V2RayN</h2>
<p>双击&nbsp;<code>v2rayN.exe</code>&nbsp;启动，然后在任务栏托盘找到 V2RayN 图标并双击它<br />添加一个 VMess 服务器</p>
<p>
<img src="https://i.loli.net/2018/02/10/5a7ef4f42264c.png" alt="" loading="lazy" /></p>
<p>从剪贴板导入 URL</p>
<p>
<img src="https://i.loli.net/2018/02/10/5a7ef4f422311.png" alt="" loading="lazy" /></p>
<blockquote>
<p>重要提醒！由于 V2RayN 暂不支持 QUIC 协议，如果是 QUIC 协议，就算导入了，也是不能正常使用的。</p>


</blockquote>
<p>设置本地监听端口，此处我将它设置为 2333</p>
<p>
<img src="https://i.loli.net/2018/02/10/5a7ef4f425367.png" alt="" loading="lazy" /></p>
<h2 id="启用系统代理">启用系统代理</h2>
<p>在任务栏托盘找到 V2RayN 图标并鼠标右键，然后选择 启动系统代理<br />并且设置 系统代理模式 》PAC 模式<br />之后在 V2RayN 主界面，找到 检查更新 》检查更新 PAC</p>
<h2 id="测试一下">测试一下</h2>
<p>在完成上面的步骤的时候，正常来说，你已经处于翻出去的状态了<br />OK，此时你已经自由了，赶紧打开&nbsp;<a href="https://www.google.com/ncr" rel="nofollow" target="_blank">Google</a>&nbsp;找部十八减的大电影喵喵吧。哈哈</p>
<h2>&nbsp;MAC 平台</h2>
<h2 id="下载-v2rayx">下载 V2RayX</h2>
<p>下载链接：&nbsp;<a href="https://github.com/insisttech/v2rayX-copy/releases" rel="nofollow" target="_blank">https://github.com/insisttech/v2rayX-copy/releases</a><br />选择 V2RayX.app.zip 下载，下载好了之后 ，解压，将 V2RayX.app 复制到 程序 文件夹。</p>
<h2 id="获取-v2ray-客户端配置">获取 V2Ray 客户端配置</h2>
<p>使用终端进行 SSH 登录你的 VPS。<br />输入<code>v2ray info</code>&nbsp;回车，你会得到 V2Ray 客户端配置</p>
<h2 id="打开-v2rayx">打开 V2RayX</h2>
<p>第一次打开时会出现需要安全认证的信息，此时你需要点完所有系统弹出的窗口里的<code>是</code>，<code>打开</code>，<code>确认</code>等选项，然后打开<code>系统偏好设置</code>里的<code>安全性与隐私</code>，你就会看见灰色的一条，大概意思为 &ldquo;V2RayX，未被安全认证，是否打开&rdquo;，后面有一个<code>仍要打开</code>的选项，点开就好。然后你就会在状态栏看到 V2RayX 图标</p>
<p>这个时候你点击它就可以看到如下界面：</p>
<p>
<img src="https://i.loli.net/2018/02/09/5a7daaae66c73.png" alt="" loading="lazy" /></p>
<p>然后进行如下操作：</p>
<p>
<img src="https://i.loli.net/2018/02/09/5a7daaae6a89a.png" alt="" loading="lazy" /></p>
<p>1.进行相关配置</p>
<p>
<img src="https://i.loli.net/2018/02/09/5a7daaae68bda.png" alt="" loading="lazy" /></p>
<p>一般的 tcp 只需按照配置在上述界面进行配置，如果有其他需求，点击高级设置选项，再进行配置。</p>
<p>
<img src="https://i.loli.net/2018/02/09/5a7daaae595a8.png" alt="" loading="lazy" /></p>
<p>每一个配置界面都很简单，都是简单的单词。如果你需要 WS + TLS 的话 需要在 WS 和 TLS 界面里的框钩上就行。（有几个钩几个，文本框可以为空，如果你什么都知道的话）配置好后点击 OK 会出现如下界面</p>
<p>
<img src="https://i.loli.net/2018/02/09/5a7daaae5ab59.png" alt="" loading="lazy" /></p>
<p>点击 yes 就好。回到最初的设置界面后也是点击 OK 就完成了配置工作。</p>
<p>2.选择模式。自带全局和 PAC 。推荐全局配置，如果想自己更改 PAC 规则的话，菜单界面有编辑的选项可以进行更改。</p>
<p>3.Start V2Ray. 开启你的新世界。开启 V2RayX 后系统也就开启了代理，无需再去配置浏览器之类的。</p>
<h2 id="登录后自动运行">登录后自动运行</h2>
<p>如果有需求加入开机自启的话可以进行如下操作：打开 macOS 系统设置 -&gt; 用户与组 -&gt; 登录项，把 V2RayX.app 添加到列表中。</p>
<h2 id="手动更新内核">手动更新内核</h2>
<p>在访达（Finder）的应用程序一栏，找到 V2RayX.app，右键选择<code>显示包内容</code>，去<code>Contents/Resources/v2ray</code>&nbsp;目录下替换从&nbsp;<a href="https://github.com/v2ray/v2ray-core/releases/latest" rel="nofollow" target="_blank">v2ray-core repo</a>&nbsp;下载的对应版本的内核内容。但不保证应用的兼容性。</p>
<h2 id="后记">后记</h2>
<p>在使用过程中如果有问题，是软件使用的问题，要去 V2RayX 的&nbsp;<a href="https://github.com/Cenmrev/V2RayX/issues" rel="nofollow" target="_blank">Github</a>&nbsp;上提<code>issues</code>。<br />目前版本在 TLS 的使用上有一小点问题，但不影响使用。本软件开发者不是计算机专业也不是软件工程师，目前还在忙于研究生课程中，所以在更新和修改方面可能会有些慢。所以不要抱怨这个软件功能较少，基本功能可以用就好。:)</p>
<h2>安卓</h2>
<h2 id="下载-v2rayng">下载 V2RayNG</h2>
<p>在 Google Play 下载：&nbsp;<a href="https://play.google.com/store/apps/details?id=com.v2ray.ang" rel="nofollow" target="_blank">V2RayNG</a>&nbsp;并安装<br />或者在 Github 下载 ：<a href="https://github.com/2dust/v2rayNG/releases" rel="nofollow" target="_blank">&nbsp;V2RayNG</a>&nbsp;并安装，备注，选择 app-universal-release.apk 下载</p>
<h2 id="获取-v2ray-客户端配置">获取 V2Ray 客户端配置</h2>
<p>SSH 登录你的 VPS （如果你没登录）<br />输入&nbsp;<code>v2ray qr</code>&nbsp;便会得到一个链接，然后打开链接</p>
<h2 id="配置-v2rayng">配置 V2RayNG</h2>
<p>打开 V2RayNG<br />如果有出现一个默认的配置，先将默认的配置删除掉，点击右边的编辑图标，然后在弹出的配置窗口，再点击右上角的删除图标，将它删除。<br />回到主界面，点击右上角的 &ldquo;+&rdquo; 加号，选择 扫描二维码，(哪里有二维码扫描？我擦，在上面的 [获取 V2Ray 客户端配置] 那里不是叫你打开一个链接了吗)<br />OK，扫描成功<br />点击右上角的菜单 (就是那三个点啊)，选择 设置，将 路由 修改为 绕过大陆地址，之后返回主界面<br />点击右下角的小灰机图标，然后会有一个提示，确定它。<br />Okay，搞定。此时你可以翻墙了，就是那么简单。<br />此时你已经自由了，赶紧打开&nbsp;<a href="https://www.google.com/ncr" rel="nofollow" target="_blank">Google</a>&nbsp;找部十八减的大电影喵喵吧。哈哈</p>
<h2 id="结束">结束</h2>
<p>其实写这个教程有点多余啦，软件之类的都那么简单明了，是个正常人都会配置<br />在 V2RayNG 设置里面还有一个 分应用代理，这个东东就是说，想要说指定相关的程序走代理，如果不设置这个，默认情况下就是所有的程序都走代理<br />那个 MUX 多路复用，一般情况下不建议打开<br />在安卓上，还有一个可能比较好用的 V2Ray 的客户端叫&nbsp;<a href="https://play.google.com/store/apps/details?id=com.github.dawndiy.bifrostv" rel="nofollow" target="_blank">BifrostV</a>&nbsp;，如果你觉得 V2RayNG 用着不顺手的话，可以试试看用它的</p>
<h2 class="post-title">iOS</h2>
<h2 id="kitsunebi">kitsunebi</h2>
<p>目前对 V2Ray 支持最完全的应用，支持所有 vmess 链接使用方案，国区有售，支持 TestFlight。<br />kitsunebi 的 testflight 自动申请页面：<a href="https://docs.google.com/forms/d/1-1ZuYA1qkyDfAn6qzUzNEV3YVZbgr__7b6aFBiKeNHc/closedform" rel="nofollow" target="_blank">https://docs.google.com/forms/d/1-1ZuYA1qkyDfAn6qzUzNEV3YVZbgr__7b6aFBiKeNHc/closedform</a></p>
<p><strong>备注一下：kitsunebi 如果搜索不到，请使用 Kitsunebi Lite</strong><br />如何使用<br />1，扫码导入服务器配置 ( 推荐 )，在小鸡上输入&nbsp;<code>v2ray qr</code>&nbsp;将会得到扫码链接，打开扫码即可。</p>
<p>
<img src="https://i.loli.net/2018/03/10/5aa3e294b276f.jpg" alt="kitsunebi" loading="lazy" /></p>
<p>支持自动导入一键脚本以及由 V2rayN 生成的二维码，<strong>需手动输入 AlterId</strong>。</p>
<p>2，手动填写服务器配置<br />点击右上 &ldquo;+&rdquo; 号导入新服务器，根据服务端配置填写。</p>
<p>
<img src="https://i.loli.net/2018/03/10/5aa3e294b40e4.png" alt="kitsunebi" loading="lazy" /></p>
<p>备注：如果你使用 WS+TLS 方式，记得要配置好路径。</p>
<h2 id="shadowrocket">Shadowrocket</h2>
<p>泛用性极高的代理软件，俗称小火箭。除 vmess 外也支持 ss、ssR、socks5、HTTP、Lua 等类型。缺点是不支持 Vmess KCP，<strong>国区无售</strong>。</p>
<p>如何使用：<br />1，手动填写服务器配置 ( 推荐 )<br />shadowrocket 不支持扫入一键脚 本或 V2rayN 生成的二维码。如何填写以及注意事项见以下。<br /><strong>如果你是使用 TCP 协议的，混淆记得选择 none</strong></p>
<p>
<img src="https://i.loli.net/2018/03/14/5aa87b2f11619.jpg" alt="Shadowrocket" loading="lazy" /></p>
<p>备注：如果你使用 WS+TLS 方式，记得要配置好 WS 的路径。</p>
<p>2，扫码导入服务器配置 ( 不推荐 )<br />正如之前所说，shadowrocket 不支持扫入一键脚本或 V2rayN 生成的二维码，只能扫入 shadowrocket 导出的 vmess 服务器设置，所以这种导入方式没有泛用性。</p>
<h2 id="pepi-原-shadowray">Pepi ( 原 ShadowRay )</h2>
<p>由 shadowrocket 同作者开发的针对 vmess 的应用。缺点是只能从状态球的颜色判断服务器状态，同样不支持 Vmess KCP，<strong>国区无售</strong>，设置类 shadowrocket，如果已经拥有了小火箭，不建议重复购买。</p>
<p>如何使用：<br />手动填写服务器配置<br />进入 Servers 页面，点击右上 &ldquo;+&rdquo; 号导入新服务器，根据服务端配置填写。</p>
<p>
<img src="https://i.loli.net/2018/03/10/5aa3e294bb90b.png" alt="Pepi" loading="lazy" /></p>
<h2 id="结束">结束</h2>
<p>iOS 上的 V2Ray 客户端相的配置对来说会比较麻烦一些，其实自己注意一下一些选项就行。</p>
<h2 id="linux">Linux</h2>
<p>能耍 Linux 的都是大佬了，我懒得写。</p>
<p>好了就这些</p>
<h1><span style="color: #ff0000;">&nbsp;请勿违反国家法律法规，否则后果自负！</span><br /><span style="color: #ff0000;">低调低调低调。</span></h1>
<h1>文章参考：</h1>
<p class="post-title"><strong>centos搭建v2ray</strong></p>
<p class="post-title"><strong>https://blog.ziyiu.com/2020/06/05/Centos%E6%9C%8D%E5%8A%A1%E5%99%A8/centos%E6%90%AD%E5%BB%BAv2ray/</strong></p>
<p><strong>V2Ray搭建详细图文教程</strong></p>
<p><strong>https://github.com/233boy/v2ray/wiki/V2Ray%E6%90%AD%E5%BB%BA%E8%AF%A6%E7%BB%86%E5%9B%BE%E6%96%87%E6%95%99%E7%A8%8B</strong></p>
<p class="entry-title"><strong>V2Ray一键安装脚本 支持多用户管理以及多种协议</strong></p>
<p class="entry-title"><strong>https://m1314.cn/341.html</strong></p>
<p><strong>V2Ray 各平台客户端使用教程 - V2Ray 教程</strong></p>
<p><strong>https://233v2.com/post/4/</strong></p>
<h1><strong>感谢观看！</strong></h1>
