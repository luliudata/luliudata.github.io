---
title: "项目"
layout: default
lang: zh
permalink: /zh/projects/
---

<article markdown="1">
<header><h1>项目</h1></header>

一份正在做或已经做完的小项目清单。

<section id="triptracker-notes" markdown="1">

## 随行 Notes <span style="font-weight: 400; opacity: .6">(TripTracker Notes)</span>

<p>
  <img src="{{ '/images/projects/triptracker-icon.png' | relative_url }}"
       alt="随行 Notes 应用图标"
       width="120" height="120"
       style="border-radius: 22%; box-shadow: 0 2px 8px rgba(0,0,0,.08); float: right; margin: 0 0 1em 1.5em;">
</p>

一款**双语（中文 / English）iOS 旅行规划与清单应用**，
适合喜欢把行程安排得井井有条、又在意数据隐私的人。
使用 React Native + Expo 开发。

**亮点**

- **智能清单** —— 签证、疫苗、行李、证件，按目的地类型分组的模板
- **AI 行程规划** —— 通过 Cloudflare Worker 代理调用
  Google Gemini 2.5 Flash，密钥不会落到设备上
- **注重隐私** —— 旅行数据全部保存在本地；
  没有遥测、没有账号、不接第三方分析
- **真双语** —— UI、日期、AI 的输入和输出都能在中英文之间干净切换

**链接** —
<a href="https://apps.apple.com/app/id6761017367" rel="noopener">App Store</a> ·
<a href="https://github.com/luliudata/triptracker-notes-app" rel="noopener">GitHub</a>

<sub style="opacity: .6">
技术栈：React Native 0.81 · Expo SDK 54 · React 19 · Google Gemini 2.5 Flash · Cloudflare Workers
</sub>

</section>

</article>
