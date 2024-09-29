---
layout: page
title: About
description: 记录学习生活
keywords: nooby alan
comments: true
menu: about
permalink: /about/
---

一个曾经的“nooby”转码普通人。

编程教会我如何在复杂的世界中寻找解决方案，如何在失败中汲取经验，如何在每一次的调试中，重塑自己的思维。

我希望通过这个博客，不仅记录我的成长历程，也能分享我对技术、学习和生活的深刻见解。让我们一起在这个数字时代的浪潮中，探索更多可能性！

## 联系

<ul>
{% for website in site.data.social %}
<li>{{website.sitename }}：<a href="{{ website.url }}" target="_blank">@{{ website.name }}</a></li>
{% endfor %}
{% if site.url contains 'mazhuang.org' %}
<li>
my wechat：<br />
<img style="height:192px;width:192px;border:1px solid lightgrey;" src="{{ site.url }}/assets/images/receipt-code-wechat .jpeg" alt="nooby" />
</li>
{% endif %}
</ul>


## Skill Keywords

{% for skill in site.data.skills %}
### {{ skill.name }}
<div class="btn-inline">
{% for keyword in skill.keywords %}
<button class="btn btn-outline" type="button">{{ keyword }}</button>
{% endfor %}
</div>
{% endfor %}
