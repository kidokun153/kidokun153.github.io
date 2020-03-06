---
layout: item
title: tokushu
date: 2020-03-06
---

## ffmpegでcrfを変えつつエンコードしてみる
<br>

### 元動画
"20200214 金 mezaJK_kuji_tsutsumi.mp4" 26s 1440×810 (SAR4:3なので16:9で再生される)<br>
以下test.mp4とする。
<br><br>


### コマンド
<pre class="prettyprint">
ffmpeg -i "%~1" -vf bwdif=1 -c:v libx264 -crf 20 -c:a copy -bsf:a aac_adtstoasc "%~dpn1-encoded-crf20.mp4"
ffmpeg -i "%~1" -vf bwdif=1 -c:v libx264 -crf 23 -c:a copy -bsf:a aac_adtstoasc "%~dpn1-encoded-crf23.mp4"
ffmpeg -i "%~1" -vf bwdif=1 -c:v libx264 -crf 25 -c:a copy -bsf:a aac_adtstoasc "%~dpn1-encoded-crf25.mp4"
ffmpeg -i "%~1" -vf bwdif=1 -c:v libx264 -crf 28 -c:a copy -bsf:a aac_adtstoasc "%~dpn1-encoded-crf28.mp4"

ffmpeg -i "%~1" -vf bwdif=0 -c:v libx264 -crf 20 -c:a copy -bsf:a aac_adtstoasc "%~dpn1-encoded-crf20-20fps.mp4"
ffmpeg -i "%~1" -vf bwdif=0 -c:v libx264 -crf 23 -c:a copy -bsf:a aac_adtstoasc "%~dpn1-encoded-crf23-30fps.mp4"
ffmpeg -i "%~1" -vf bwdif=0 -c:v libx264 -crf 25 -c:a copy -bsf:a aac_adtstoasc "%~dpn1-encoded-crf25-30fps.mp4"
ffmpeg -i "%~1" -vf bwdif=0 -c:v libx264 -crf 28 -c:a copy -bsf:a aac_adtstoasc "%~dpn1-encoded-crf28-30fps.mp4"
</pre>

#### `-vf bwdif`
インターレス解除フィルタ
(Bob Weaver Deinterlacing Filter) <br>
based on yadif with the use of w3fdif and cubic interpolation algorithms. It accepts the following parameters<br>
[bwdif - ffmpeg](http://underpop.online.fr/f/ffmpeg/help/bwdif.htm.gz)<br><br>


### 結果
<table class="table table-striped">
	<tr>
		<th>名前</th>
		<th>容量[MB]</th>
		<th>データ速度[kbps]</th>
		<th>フレーム率[fps]</th>
		<th>解像度</th>
	</tr>
	<tr>
		<th>test.mp4</th>
		<td>17.3</td>
		<td>5190</td>
		<td>29.91</td>
		<td>1440×1080</td>
	</tr>
	<tr>
		<th>crf20 bwdif=1</th>
		<td>22.7</td>
		<td>6869</td>
		<td>59.88</td>
		<td>1440×1080</td>
	</tr>
	<tr>
		<th>crf20 bwdif=0</th>
		<td>21</td>
		<td>6358</td>
		<td>29.94</td>
		<td>1440×1080</td>
	</tr>
	<tr>
		<th>crf23 bwdif=1</th>
		<td>15.8</td>
		<td>4709</td>
		<td>59.88</td>
		<td>1440×1080</td>
	</tr>
	<tr>
		<th>crf23 bwdif=0</th>
		<td>15.1</td>
		<td>4509</td>
		<td>29.94</td>
		<td>1440×1080</td>
	</tr>
	<tr>
		<th>crf25 bwdif=1</th>
		<td>12.3</td>
		<td>3636</td>
		<td>59.88</td>
		<td>1440×1080</td>
	</tr>
	<tr>
		<th>crf25 bwdif=0</th>
		<td>12</td>
		<td>3537</td>
		<td>29.94</td>
		<td>1440×1080</td>
	</tr>
	<tr>
		<th>crf28 bwdif=1</th>
		<td>8.58</td>
		<td>2648</td>
		<td>59.88</td>
		<td>1440×1080</td>
	</tr>
	<tr>
		<th>crf28 bwdif=0</th>
		<td>8.46</td>
		<td>2433</td>
		<td>29.94</td>
		<td>1440×1080</td>
	</tr>
</table>

  <div class="row img-padding row-bottom">
    <div class="col-lg-4 col-sm-6"><img  class="img-fluid" src="https://i.imgur.com/pr7vM6z.png" alt="data" title="data"></div>
  </div>
  <br>

### キャプチャ画像(※30fpsのみ)
0s ,1s. 15, 19s
  <!--4枚画像-->
<div class="row img-padding">
  <div class="col-lg-4 col-sm-6"><img  class="img-fluid" src="https://i.imgur.com/3ffQ5iz.jpg" alt="" title="サンプル"></div>
  <div class="col-lg-4 col-sm-6"><img  class="img-fluid" src="https://imgur.com/A2xszGH.jpg" alt="" title=""></div>
  <div class="col-lg-4"></div>
  <div class="col-lg-4 col-sm-6"><img  class="img-fluid" src="https://imgur.com/qMOl2OB.jpg" alt="" title=""></div>
  <div class="col-lg-4 col-sm-6"><img  class="img-fluid" src="https://imgur.com/WqdJGDF.jpg" alt="" title=""></div>
  <div class="col-lg-4"></div>
</div>
test.mp4

<div class="row img-padding">
  <div class="col-lg-4 col-sm-6"><img  class="img-fluid" src="https://i.imgur.com/VsGKEED.jpg" alt="" title="サンプル"></div>
  <div class="col-lg-4 col-sm-6"><img  class="img-fluid" src="https://i.imgur.com/db52DYf.jpg" alt="" title=""></div>
  <div class="col-lg-4"></div>
  <div class="col-lg-4 col-sm-6"><img  class="img-fluid" src="https://i.imgur.com/qKzNtox.jpg" alt="" title=""></div>
  <div class="col-lg-4 col-sm-6"><img  class="img-fluid" src="https://i.imgur.com/8NrUZqz.jpg" alt="" title=""></div>
  <div class="col-lg-4"></div>
</div>
crf20

<div class="row img-padding">
  <div class="col-lg-4 col-sm-6"><img  class="img-fluid" src="https://i.imgur.com/icJuOTB.jpg" alt="" title="サンプル"></div>
  <div class="col-lg-4 col-sm-6"><img  class="img-fluid" src="https://i.imgur.com/yTt3X8D.jpg" alt="" title=""></div>
  <div class="col-lg-4"></div>
  <div class="col-lg-4 col-sm-6"><img  class="img-fluid" src="https://i.imgur.com/huNpoBE.jpg" alt="" title=""></div>
  <div class="col-lg-4 col-sm-6"><img  class="img-fluid" src="https://i.imgur.com/S2R9iAI.jpg" alt="" title=""></div>
  <div class="col-lg-4"></div>
</div>
crf23

<div class="row img-padding">
  <div class="col-lg-4 col-sm-6"><img  class="img-fluid" src="https://i.imgur.com/ZQHaJQX.jpg" alt="" title=""></div>
  <div class="col-lg-4 col-sm-6"><img  class="img-fluid" src="https://i.imgur.com/pYkriJD.jpg" alt="" title=""></div>
  <div class="col-lg-4"></div>
  <div class="col-lg-4 col-sm-6"><img  class="img-fluid" src="https://i.imgur.com/v3NN6aU.jpg" alt="" title=""></div>
  <div class="col-lg-4 col-sm-6"><img  class="img-fluid" src="https://i.imgur.com/H31Fprb.jpg" alt="" title=""></div>
  <div class="col-lg-4"></div>
</div>
crf25

<div class="row img-padding">
  <div class="col-lg-4 col-sm-6"><img  class="img-fluid" src="https://i.imgur.com/9OjSyyH.jpg" alt="" title="サンプル"></div>
  <div class="col-lg-4 col-sm-6"><img  class="img-fluid" src="https://i.imgur.com/gkQ6eL1.jpg" alt="https://i.imgur.com/URgyE26.jpg" title=""></div>
  <div class="col-lg-4"></div>
  <div class="col-lg-4 col-sm-6"><img  class="img-fluid" src="https://i.imgur.com/URgyE26.jpg" alt="" title=""></div>
  <div class="col-lg-4 col-sm-6"><img  class="img-fluid" src="https://i.imgur.com/7xLN1dE.jpg" alt="" title=""></div>
  <div class="col-lg-4"></div>
</div>
crf28

- Bandicamによるキャプチャ ffmpegで切り出したほうが良さそう
<br><br>

#### 評価
もともとの動画がすでに`-crf 23`でエンコードされたものであり、おそらくcrf23より小さい`-crf 20`では無駄に容量やビットレートを割くことになってしまう。`-crf 25`ではなんとなく劣化を感じるような気もするけど微妙なラインである。`-crf 28`では劣化していると確信できるが僅かな劣化だと感じる。<br>
また`-vf bwdif`に関して30fpsと60fpsの違いもわからないうえ、60fpsだと容量を割くだけなので`-vf bwdif=00`で良い事はわかった。<br><br>