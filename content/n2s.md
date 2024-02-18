---
title: 迁移 网易云 / QQ 音乐到 Apple Music, Youtube Music, Spotify
date: 2018-11-14T10:37:58+05:30
lastmod: 2021-07-17T10:37:58+05:30
author: yueyericardo
draft: false
---

<!-- 浮动广告 -->
<!-- 正方形 -->
<!-- <div id="ads-header">
<script async src="https://pagead2.googlesyndication.com/pagead/js/adsbygoogle.js?client=ca-pub-8845711146723582"
crossorigin="anonymous"></script>
<ins class="adsbygoogle"
style="display:block"
data-ad-client="ca-pub-8845711146723582"
data-ad-slot="2259978748"
data-ad-format="auto"
data-full-width-responsive="true"></ins>
<script>
(adsbygoogle = window.adsbygoogle || []).push({});
</script>
</div> -->
<!-- 浮动广告 end -->

<p style="text-align: center ">
    <a target="_blank" href="https://github.com/yueyericardo/Netease-to-Spotify">Github</a> &nbsp;/&nbsp;
    <a target="_blank" href="https://binaryify.github.io/NeteaseCloudMusicApi/#/">API</a> &nbsp;/&nbsp;
    <a target="_blank" href="https://github.com/bjason/163MusicToSpotify">Ref</a>
</p>

<p>迁移你的网易云歌单 / QQ音乐歌单到Youtube Music, Spotify, Apple Music<br>
Last Updated On: 2021.07.17</p>
<h3 id="1-输入网易云的歌单ID"><a href="#1-输入歌单ID" class="headerlink" title="1. 输入歌单ID"></a>1. 输入歌单 ID</h3>
<ul>
  <li>网易云音乐歌单（可输入歌单 URL 自动检测 ID）</li>
    例如 <a target="_blank" href="https://music.163.com/#/playlist?id=167900089">https://music.163.com/#/playlist?id=167900089</a>
    <br>歌单 ID = <code>167900089</code>
    <li>QQ音乐歌单 （仅支持输入歌单 ID）</li>
    例如 <a target="_blank" href="https://y.qq.com/n/yqq/playlist/7382629476.html">https://y.qq.com/n/yqq/playlist/7382629476.html</a>
    <br>歌单 ID = <code>7382629476</code>
</ul>

<div style="text-align: center">
  <div style="display: inline-flex; margin: 5px 10px;">
    <input style="margin:auto 0;" type="radio" name="tag" value="netease" checked>
    <span style="margin:auto 5px; padding: 0 5px;">网易云</span>
  </div>
  <div style="display: inline-flex; margin: 5px 10px;">
    <input style="margin:auto 0;" type="radio" name="tag" value="qq">
    <span style="margin:auto 5px; padding: 0 5px;">QQ音乐</span>
  </div>
</div>

<p style="text-align: center; text-decoration: blink;">
    <input id="playlistId" class="search-input" name="playlistId" placeholder="PlaylistID eg: 167900089">
    <button id="submit" type="submit" class="button-netease">
    <!-- <button class="button-netease"> -->
    <!-- 2021.07.17 博主正在修复中... -->
    Search
    </button>
</p>

<div class="loader" id="loader">
  <div class="dot"></div>
  <div class="dot"></div>
  <div class="dot"></div>
  <div class="dot"></div>
</div>

<p class="result">
    歌单名:  <span id="plname" style="color: #E5001C; font-weight: bold;"></span>
    <br>
    曲目数: <span id="numsongs" style="color: #E5001C; font-weight: bold;"></span>
</p>


<h3 id="2-复制下面所生成的文字版歌单"><a href="#2-复制下面所生成的文字版歌单" class="headerlink" title="2. 复制下面所生成的文字版歌单"></a>2. 复制下面所生成的文字版歌单</h3><p><textarea id="output" name="result" class="textarea">
</textarea></p>
<p style="text-align: center">
  <button id="trimSingers" class="button-netease" style="width: 180;" trimed=0>仅保留第一个歌手
  </button>
    <button id="copy" class="button-netease" style="width: 180;">点我复制
    </button>
</p>

<h3 id="3-转移到-Youtube-Music-or-Spotify-or-Apple-Music"><a href="#3-转移到-Youtube-Music-or-Spotify-or-Apple-Music" class="headerlink" title="3. 转移到 Youtube Music or Spotify or Apple Music"></a>3. 转移到 Youtube Music or Spotify or Apple Music</h3>
<ul>
<li>
    Go to <a class=" a-spotify" target="_blank" href="https://www.tunemymusic.com/zh-CN">TunemyMusic</a>
</li>
    <ul>
    <li>STEP 1: 选择来源<code>从文本</code> </li>
    <li>STEP 2: 粘贴刚刚复制的内容到文本框中</li>
    <li>STEP 3: 选择 <code>Youtube</code> or <code>Spotify</code> or <code>Apple Music</code>作为目的地</li>
    <li>STEP 4: 开始移动</li>
    </ul>
<li>
    如果有帮到你，请点个赞吧！ <span style="cursor: pointer;" onclick="hitlovecounter()"> ❤️ </span><span id="lovecount"></span><span id="lovecountThanks" style="visibility: hidden; color: #E5001C;"> Thanks!</span>
</li>
</ul>

<!-- 手机广告 -->
<!-- <div id="ads-mobile">
<ins class="adsbygoogle"
     style="display:inline-block;width:500px;height:90px"
     data-ad-client="ca-pub-8845711146723582"
     data-ad-slot="7013551905"></ins>
<script>
     (adsbygoogle = window.adsbygoogle || []).push({});
</script>
</div> -->
<!-- 手机广告 end -->

<h3 id="5-Summary"><a href="#5-Summary" class="headerlink" title="5. Summary"></a>5. Summary</h3><p>
成功率<br>
Youtube Music: 158/166  <br>
Spotify: 104/166  <br>
Apple Music: 90/166  <br>
</p>
<h3 id="6-FAQ"><a href="#6-FAQ" class="headerlink" title="6. FAQ"></a>6. FAQ</h3>
<ol>
  <li>报错的可能原因 (1): 输入的歌单 id / 链接 不存在（输入错误），或者歌单为隐私状态。 </li>
  <li>报错的可能原因 (2): <ul>
  <li>经测试，大部分用户的《我喜欢的音乐》歌单都崩掉了... <code>2021.07.17</code></li>
  <li>可能的解决办法：翻到歌单最底部，<code>Cmd / Ctrl + A</code> 全选所有歌曲，右键创建新歌单，再使用新歌单的链接导出文本。
  </li>
  </ul>
  </li>
  <li>歌单超过 1000 首怎么办？<br>
  	1000 首是 <a href="https://binaryify.github.io/NeteaseCloudMusicApi/#/">API</a> 的限制，同时也是为了减少服务器资源的滥用。<br>
	  如果有报错，请按照如上步骤创建歌单，确保至少能导出 1000 首之后，在 <a href="https://github.com/yueyericardo/Netease-to-Youtube-or-Spotify/issues/4">GITHUB 留言板</a>，留下歌单 URL。<br>
  <li>TunemyMusic 点不了“开始”那个按钮？点了没反应<br> 查看了之前的评论，TunemyMusic 可能需要科学上网才能使用。</li>
  <li>如有其他问题，请在评论中提出。</li>
</ol>


### 7. 更新历史
- 2022-07-30：[Fix] 网易云 API 更新 cookie
- 2021-08-21：[Fix] 支持网易云的新链接格式 ?playlistid=12345678
- 2021-07-16：[Fix] 网易云封闭了所有《我喜欢的音乐》
- 2021-06-10：[Fix] 网易云完全禁止了在非登录状态查看歌单详情
- 2021-02-09：[Feature] 保留 所有/第一位 歌手
- 2020-05-29：[Fix] 网易云限制只能获得歌单前 6-10 首歌
- 2020-03-04：[Feature] 支持 QQ 音乐
- 2018-11-14：[Feature] 支持 网易云 音乐


### 8. Thanks For the Donation
感谢 `豆子` `我真的真的真的很不错` `*涛` `i*p` `胡小桐` `Johnny_Ren` `Takumi` `石墨` 等的大力支持！


<!-- donation -->
<div style="margin: 120px 0 150px; position: relative; width: 100%;">
	<a id="github" href="https://github.com/yueyericardo/" target="_blank" class="pos-f tr3" title="Github"></a>
	<div id="DonateText" class="tr3">Donate</div>
	<ul id="donateBox" class="list pos-f tr3">
		<li id="PayPal"><a href="https://www.paypal.me/yyrcd" target="_blank" title="PayPal付款页">PayPal</a></li>
		<li id="AliPay" data-footnote="点击查看支付宝付款码"><a  title="支付宝付款码">AliPay</a></li>
		<li id="WeChat" data-footnote="点击查看微信付款码"><a  title="微信付款码">WeChat</a></li>
	</ul>
	<div id="QRBox" class="pos-f left-100">
		<div id="MainBox"></div>
	</div>
</div>
<!-- donation end -->

<!-- 横向广告Bottom -->
<!-- <ins class="adsbygoogle"
     style="display:block"
     data-ad-client="ca-pub-8845711146723582"
     data-ad-slot="7153406290"
     data-ad-format="auto"
     data-full-width-responsive="true"></ins>
<script>
     (adsbygoogle = window.adsbygoogle || []).push({});
</script> -->
<!-- 横向广告Bottom end -->

<!-- search and show -->
<script type="text/javascript">
    $("#submit").click(function(){
    a = $('input[name="tag"]:checked').val();
    console.log("playlist: " + a)
    qq = false
    if (a == 'qq'){
      var qq = true;
    }
    console.log(qq);

    $("#loader").show();
    var playlistId = $("#playlistId").val();

    if(!playlistId){
      if (qq){
        playlistId = 7382629476;
      }else{
        playlistId = 167900089;
      }
    }
    var url;
    if (qq){
      idIsInt = parseInt(playlistId);
      if (!idIsInt){
        alert("输入的不是歌单id");
        $("#loader").hide();
        return; 
      }
      url = `https://qqapi.yyrcd.com/songlist?id=${playlistId}`;
    }else{
      idIsInt = parseInt(playlistId);
      if (!idIsInt){
        console.log('Input: String, treat as URL, try to extract ID');
        patten = /[\?\&]id=([0-9]+)/g;   // https://music.163.com/#/playlist?id=167900089
        result = patten.exec(playlistId);
        if (result){
          playlistId = result[1];
        }else{
          patten = /playlist\/([0-9]+)/g;  // https://music.163.com/playlist/167900089
          result = patten.exec(playlistId);
          if (result){
            playlistId = result[1];
          }else{
            patten = /playlistid=([0-9]+)/g;  // https://music.163.com/playlistid=167900089
            result = patten.exec(playlistId);
            if (result){
              playlistId = result[1];
            }else{
              alert("输入的不是歌单id / URL无法检测");
              $("#loader").hide();
              return;
            }
          }
        }
        console.log('Find ID:', playlistId);
      }else{
        console.log('Input number: ', playlistId);
      }

      url = `https://music.yyrcd.com/n2s?id=${playlistId}`;
      let pw = localStorage.getItem('pw');
      if (pw) {
        url = `${url}&pw=${pw}`;
      }
    }

    function get_qq(result){
      var list = [];
      var data = result.data;

      console.log(data);

      var playlistName = data.dissname;
      var tracks = data.songlist;
      var numsongs = tracks.length;
      console.log(tracks);
      console.log(tracks.length);

      for (i=0; i<tracks.length; i++){
          var title = tracks[i].songname;
          singers = tracks[i].singer;
          singers_list = []
          for (j=0; j<singers.length; j++){
            singers_list.push(singers[j].name);
          }
          author = singers_list.join(" / ");
          var custom = title +' - '+ author +'\n' ;
          list.push(custom);
          }
      output = list.join("");
      return [output, playlistName, numsongs];
    }

    $.ajax({
        type: "GET",
        url: url,
        dataType: 'json',
        success: function(result){
            console.log(result);
            if (qq){
              [output, playlistName, numsongs] = get_qq(result);
            }else{
              var output = result.info;
              var playlistName = result.playlistName;
              var numsongs = result.numsongs;
            }
            $("#output").val(output);
            $('#plname').text(playlistName);
            $('#numsongs').text(numsongs);
            $("#loader").hide();
            sessionStorage.setItem('tmpplaylist', output);
            return false;
            },
        error: function(request) {
            alert("此歌单（包括大部分用户的《我喜欢的音乐》歌单都）暂时无法访问，请查看 FAQ 中可能的解决办法");
            $("#loader").hide();
            return false;
          }
        });
    });
</script>

<!-- copy -->
<script>
    function copyArticle(event){
    const range = document.createRange();
    range.selectNode(document.getElementById('output'));
    const selection = window.getSelection();
    if(selection.rangeCount > 0) selection.removeAllRanges();
    selection.addRange(range);

    document.execCommand('copy');
    }
    function trimSingers(){
      trimbnt = document.getElementById('trimSingers');
      trimed = parseInt(trimbnt.getAttribute('trimed'));
      tmpplaylist = sessionStorage.getItem('tmpplaylist');
      if (tmpplaylist == null){
        return 0;
      }
      console.log(trimed);
      if (trimed){
        console.log('undo');
        trimbnt.setAttribute('trimed', 0);
        trimbnt.innerText = '仅保留第一个歌手';
      }else{
        console.log('trim');
        tmpplaylist = tmpplaylist.replace(/\/[^\-]+\n/g, '\n');  // [^\-]+ 排除/在歌名中的情况
        trimbnt.setAttribute('trimed', 1);
        trimbnt.innerText = '保留所有歌手';
      }
      $("#output").val(tmpplaylist);

    }

    document.getElementById('copy').addEventListener('click', copyArticle, false);
    document.getElementById('trimSingers').addEventListener('click', trimSingers, false);
</script>

<!-- lovecount -->
<script>
function loadlovecounter() {
    var xhr = new XMLHttpRequest();
    xhr.open("GET", "https://api.countapi.xyz/info/yyrcd.com/n2s-love-count");
    xhr.responseType = "json";
    var count = document.getElementById('lovecount');
    xhr.onload = function() {
      count.innerText = this.response.value;
    }
    xhr.send();
}

loadlovecounter()

function hitlovecounter() {
    var xhr = new XMLHttpRequest();
    xhr.open("GET", "https://api.countapi.xyz/hit/yyrcd.com/n2s-love-count");
    xhr.responseType = "json";
    var count = document.getElementById('lovecount');
    var countThanks = document.getElementById('lovecountThanks');
    xhr.onload = function() {
      count.innerText = this.response.value;
      countThanks.style.visibility = "visible";
    }
    xhr.send();
}
</script>

<!-- donation -->
<script>
jQuery(document).ready(function() {
	var QRBox	=	$('#QRBox');
	var MainBox	=	$('#MainBox');
	var AliPayQR	=	'/images/zhifubao.jpeg';
	var WeChanQR	=	'/images/weixin.jpeg';


	function showQR(QR) {
		if (QR) {
			MainBox.css('background-image','url('+QR+')');
		}
		$('#DonateText,#donateBox,#github').addClass('blur');
		QRBox.fadeIn(300,function(argument) {
			MainBox.addClass('showQR');
		});
	}

	$('#donateBox>li').click(function(event) {
		var thisID	=	$(this).attr('id');
		if (thisID === 'AliPay') {
			showQR(AliPayQR);
		} else if (thisID === 'WeChat') {
			showQR(WeChanQR);
		}
	});

	MainBox.click(function(event) {
		MainBox.removeClass('showQR').addClass('hideQR');
		setTimeout (function(a) {
			QRBox.fadeOut(300,function(argument) {
				MainBox.removeClass('hideQR');
			});
			$('#DonateText,#donateBox,#github').removeClass('blur');
		},600);

	});
});
</script>
