# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## 项目概述

单文件 HTML/CSS/JS 应用（`index.html`），24 种传染病的防护知识培训游戏。无框架依赖，纯原生实现。

## 开发要点

- 所有代码在 `index.html` 单文件中，内联 `<style>` + `<script>`
- CSS 变量驱动主题系统：`:root` 定义默认蓝，`.theme-warm/.theme-forest/.theme-purple` 定义替代主题，`body.dark` 叠加暗色
- 游戏数据 `DISEASES` 数组在 JS 顶部，每题追踪通过 `recordDiseaseResult()` → localStorage
- 状态管理在 `state` 全局对象，每个模式独立子状态（`state.mode1/mode2/mode3`）
- 页面布局：`.container` flex，`.sidebar`（260px sticky）+ `.main-area`（flex:1），≤768px 上下堆叠
- 导航切换通过 `switchTab()` → `renderTab()` → 具体 `renderXxx()` 函数，用 `.nav-btn` 的 `data-tab` 属性匹配
