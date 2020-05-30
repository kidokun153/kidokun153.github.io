https://kun153.github.io


# Umi

"Umi" は "Honoka"を元にした日本語も美しく表示できるBootstrapテーマです。

# 文法

## 画像の載せ方
```html
<!--4枚画像-->
<div class="row img-padding row-bottom">
  <div class="col-lg-4 col-sm-6"><img  class="img-fluid" src="hoge.jp" alt="" title="サンプル"></div>
  <div class="col-lg-4 col-sm-6"><img  class="img-fluid" src="" alt="" title=""></div>
  <div class="col-lg-4"></div>
  <div class="col-lg-4 col-sm-6"><img  class="img-fluid" src="" alt="" title=""></div>
  <div class="col-lg-4 col-sm-6"><img  class="img-fluid" src="" alt="" title=""></div>
  <div class="col-lg-4"></div>
</div>

<!--3枚画像-->
<div class="row img-padding">
  <div class="col-lg-4 col-sm-6"><img  class="img-fluid" src="" alt="" title=""></div>
  <div class="col-lg-4 col-sm-6"><img  class="img-fluid" src="" alt="" title=""></div>
  <div class="col-lg-4 col-sm-6"><img  class="img-fluid" src="" alt="" title=""></div>
</div>

<!--2枚画像-->
  <div class="row img-padding">
    <div class="col-lg-4 col-sm-6"><img  class="img-fluid" src=" alt="" title=""></div>
    <div class="col-lg-4 col-sm-6"><img  class="img-fluid" src="" alt="" title=""></div>
    <div class="col-lg-4"></div>
  </div>

   <!--1枚画像-->
  <div class="row img-padding">
    <div class="col-lg-4 col-sm-6"><img  class="img-fluid" src="" alt="" title=""></div>
  </div>
```

## 表
```html
<table class="table table-striped">
  <thead>
    <tr>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td></td>
      <td></td>
      <td></td>
      <td></td>
    </tr>
  </tbody>
</table>
```


## フロントマター

```markdown
---
layout: post
title:  "Potatoes"
date:   2015-11-25
lastchange : 2017-08-13
categories: writing
---
```