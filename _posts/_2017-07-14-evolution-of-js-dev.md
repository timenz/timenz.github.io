---
layout: post
title: Evolution of Web Frontend Development
date: 2017-07-14 10:18:22
tags:
---

Ada beberapa teknik yang bisa dipakai untuk mengembed script javascript pada suatu aplikasi web, dan beberapa tahun ini teknik-teknik yang digunakan mengalami perkembangan yang pesat.<!-- more -->

## Original Teknik
Teknik tertua dan yang paling sederhana dimana kamu cuman pengen ngasih sesuatu yang 'flashy' pada aplikasi web adalah embed skrip js-nya di html di dalam tag `<script>`.

```
<button onclick="warnMe">Warning</button>
<script>
  function warnMe () {
    alert('Anda ngeklik Warning')
  }
</script>
```
Juga dimungkinkan embedding external `*.js` file dengan tag `<script>` melalui attribute `src`.

```
<button class="warn-me">Warning</button>
<script src="/static/jquery.js">
<script>
  $(fuction () {
    $('.warn-me').click(function () {
      $('.warn-modal').modal()
    })
  })
</script>
```

Sampai sekarang embedding script js ke html sebenarnya cuman terbatas pada dua teknik ini, selanjutnya terdapat banyak perkembangan pada bagaimana mengatur library js yang dipakai dan runner-runner untuk ngebuild si file js itu.

## Bower
Waktu itu lagi hype dengan NodeJs, javascript yang bisa dipakai buat backend dibarengi dengan munculnya NPM (Node Package Manager) yang ditujukan untuk manage dependency buat aplikasi nodejs, kemudian js yang di-frontend jadi iri maka muncul bower. Prinsip kerja bower kurang lebih sama dengan NPM cuman dikhususkan buat web/frontend.

Bower ini ditujukan untuk merevisi teknik download-embed, dengan memakai bower kita tinggal nge-run script maka package langsung didownload terus kita tinggal embed. Sebagai package manager, bower juga bisa digunakan untuk update package dan menjaga dependency antar package. Meskipun dalam perkembangannya NPM juga bisa dipakai untuk manage package buat web dan popularitas mulai bower berkurang.

```
$ bower install <package>
```

## Grunt & Gulp
Grunt, gulp adalah task runner,


### library
[NPM vs. Bower vs. Browserify vs. Gulp vs. Grunt vs. Webpack ](https://stackoverflow.com/questions/35062852/npm-vs-bower-vs-browserify-vs-gulp-vs-grunt-vs-webpack)
