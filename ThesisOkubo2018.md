---
layout: page
permalink: /thesisokubo/
title: 
---

{% for pub in site.data.okubothesis.publications %}

<style>
.video-holder {
  position: relative;
  display : block;
  width: 100%;
  height: 0;
  padding-bottom: 56.25%;
  padding-top: 0%;
  overflow: hidden;
}
.video-holder iframe, .video-holder object, .video-holder embed {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
}
</style>

<span style="color: #c90016; font-size: 70%;">***{{pub.caption}}***</span> 
<div class="video-holder">
   <video  style="display:block; width:100%; height:{{pub.aspect}}%;" controls>
       <source src="{{pub.file | prepend: "/files/videos/okubothesis/" site.url}}"/>
   </video>
</div>
{% endfor %}





