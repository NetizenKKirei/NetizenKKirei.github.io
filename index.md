---
layout: splash
permalink: /
title: "网友KKirei的个人空间"
header:
  overlay_color: "#000"
  overlay_filter: "0.5"
  overlay_image: /assets/splash/alice-by-sea.jpg
  overlay_html: '<div class="bg-overlay"></div>'
  actions:
    - label: "关于我"
      url: "/about/"
excerpt: ""
intro:
  - excerpt: "欢迎，这里是网友KKirei的个人空间，用于记录我的学习与思考。"
---

<style>
/* ====== 全屏背景设置 ====== */
.page__hero--overlay {
  position: fixed !important;
  top: 0 !important;
  left: 0 !important;
  width: 100% !important;
  height: 100% !important;
  z-index: -1 !important;
  background-size: cover !important;
  background-position: center !important;
  margin: 0 !important;
  padding: 0 !important;
}

/* ====== 透明导航栏 ====== */
.site-header {
  background: transparent !important;
  border-bottom: none !important;
  position: relative !important;
  z-index: 10 !important;
}

.site-title, .site-title:visited, .page-link {
  color: white !important;
  text-shadow: 1px 1px 3px rgba(0,0,0,0.8) !important;
}

/* ====== 内容区域调整 ====== */
.page-content {
  position: relative !important;
  z-index: 5 !important;
  background: transparent !important;
}

/* 确保主要内容在背景图上 */
.page-content .wrapper {
  background: rgba(255, 255, 255, 0.9); /* 半透明白色背景 */
  padding: 2rem;
  border-radius: 8px;
  margin-top: 20vh; /* 从背景图顶部开始的位置 */
  max-width: 800px;
  margin-left: auto;
  margin-right: auto;
}

/* ====== 背景遮罩层 ====== */
.bg-overlay {
  position: absolute !important;
  top: 0 !important;
  left: 0 !important;
  width: 100% !important;
  height: 100% !important;
  background: rgba(0,0,0,0.4) !important;
  z-index: 1 !important;
}

/* ====== 页脚修复 ====== */
.site-footer {
  position: relative;
  z-index: 5;
  background: rgba(255, 255, 255, 0.9); /* 半透明白色背景 */
  padding: 1rem;
  text-align: center;
  margin-top: 2rem;
}
</style>

{% include feature_row id="intro" type="center" %}
