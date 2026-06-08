# Dawn

[![Build status](https://github.com/shopify/dawn/actions/workflows/lighthouse-ci.yml/badge.svg?branch=main)](https://github.com/Shopify/dawn/actions/workflows/lighthouse-ci.yml?query=branch%3Amain)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg?color=informational)](/CONTRIBUTING.md)

[快速开始](#快速开始) |
[与 Dawn 保持同步](#与-dawn-保持同步) |
[开发者工具](#开发者工具) |
[贡献指南](#贡献指南) |
[行为准则](#行为准则) |
[主题商店提交](#主题商店提交) |
[许可证](#许可证)

Dawn 采用 HTML 优先、按需使用 JavaScript 的主题开发方式。它是 Shopify 首个开源主题，内置性能优化、灵活性和 [Online Store 2.0 功能](https://www.shopify.com/partners/blog/shopify-online-store)，也是构建 Shopify 主题的参考实现。

- **原生 Web 体验：** 主题运行在[常青 Web](https://www.w3.org/2001/tag/doc/evergreen-web/) 之上。我们充分利用最新 Web 浏览器的特性，同时通过渐进增强（而非 polyfill）支持旧版浏览器。
- **精简、快速、可靠：** 功能与设计默认「不添加」，除非满足上述要求。代码以质量为先。主题应有意图地构建，不必支持 Shopify 的每一项功能。
- **JavaScript 非必需，优雅降级：** 在编写第一行 JavaScript 之前，我们从 HTTP、语义化 HTML 和 CSS 中榨取每一丝速度与功能。JavaScript 仅用于渐进增强功能。
- **服务端渲染：** HTML 必须由 Shopify 服务器通过 Liquid 渲染。业务逻辑和平台原语（如翻译、货币格式化）不应放在客户端。页面局部异步按需渲染可以，但应作为渐进增强谨慎使用。
- **功能优先，而非像素级完美：** Web 并不要求每个页面在每个浏览器引擎中像素级一致。通过语义化标记、渐进增强和巧妙设计，我们确保主题在任何浏览器中都能正常工作。

你可以在[贡献指南](https://github.com/Shopify/dawn/blob/main/.github/CONTRIBUTING.md#theme-code-principles)中找到更详细的主题代码原则说明。

## 快速开始

1. Fork 本仓库并克隆到本地：

```sh
git clone git@github.com:your-username/dawn.git
cd dawn
```

2. 按照[这些步骤](https://shopify.dev/themes/tools/cli/installation)安装 [Shopify CLI](https://github.com/Shopify/shopify-cli)。
3. 在 `dawn/` 目录下启动开发服务器：

```sh
shopify theme serve
```

> :information_source: 开始主题开发前，你需要能访问一个 Shopify 店铺。如果还没有，可以创建一个[开发商店](https://shopify.dev/themes/tools/development-stores)。

## 与 Dawn 保持同步

假设你基于 Dawn 开发新主题，但仍希望拉取最新改动，可以添加一个指向本 Dawn 仓库的 `upstream` 远程源。

1. 进入本地主题目录。
2. 查看远程仓库列表，确认同时存在 `origin` 和 `upstream`：

```sh
git remote -v
```

3. 如果没有 `upstream`，可以添加一个指向 Shopify Dawn 仓库的远程源：

```sh
git remote add upstream https://github.com/Shopify/dawn.git
```

4. 将 Dawn 的最新改动拉取到你的仓库：

```sh
git fetch upstream
git pull upstream main
```

## 开发者工具

Shopify 主题团队在开发过程中会使用多种实用工具。Dawn 已配置好可直接配合这些工具使用。

### Shopify CLI

[Shopify CLI](https://github.com/Shopify/shopify-cli) 帮助你更快地构建 Shopify 主题，用于自动化和增强本地开发流程。它内置一套主题开发命令——从在 Shopify 店铺上管理主题（创建、发布、删除等），到启动本地主题开发服务器，一应俱全。

你可以参考这份[主题开发者快速入门指南](https://github.com/Shopify/shopify-cli#quick-start-guide-for-theme-developers)开始使用。

### Theme Check

我们推荐使用 [Theme Check](https://github.com/shopify/theme-check) 来验证和 lint 你的 Shopify 主题。

Dawn 的 [VS Code 扩展列表](https://github.com/Shopify/dawn/blob/update-README/.vscode/extensions.json) 中已包含 Theme Check。如果你使用 Visual Studio Code 作为编辑器，在 fork 并克隆 Dawn 后首次打开 VS Code 时，会提示安装 [Theme Check VS Code](https://marketplace.visualstudio.com/items?itemName=Shopify.theme-check-vscode) 扩展。

Theme Check 已集成到 [Dawn 的 GitHub Actions](https://github.com/Shopify/dawn/tree/main/.github/workflows) 中，也可通过 Shopify CLI 的 `shopify theme check` 命令运行。

### Shopify/lighthouse-ci-action

我们热爱高性能网站！因此创建了 [Shopify/lighthouse-ci-action](https://github.com/Shopify/lighthouse-ci-action)。它会在每次提交时对店铺的首页、商品页和集合页运行一系列 [Google Lighthouse](https://developers.google.com/web/tools/lighthouse) 审计，确保新增代码不会随时间降低店铺性能。

Dawn 使用 [GitHub Actions](https://github.com/features/actions) 在每次提交时运行 Shopify/lighthouse-ci-action。[这是起步配置](https://github.com/Shopify/dawn/blob/main/.github/workflows/lighthouse-ci.yml)，我们建议采用它来确保你构建出更好的主题。欢迎在此基础上继续扩展！

## 贡献指南

想通过贡献 Dawn 让电商对所有人更好？我们非常欢迎你的帮助！请阅读我们的[贡献指南](https://github.com/Shopify/dawn/blob/main/.github/CONTRIBUTING.md)，了解开发流程、如何提交 bug 修复与改进，以及如何为 Dawn 构建功能。

## 行为准则

所有希望通过代码或 Issue 贡献的开发者，请先阅读我们的[行为准则](https://github.com/Shopify/dawn/blob/main/.github/CODE_OF_CONDUCT.md)。

## 主题商店提交

[Shopify 主题商店](https://themes.shopify.com/) 是 Shopify 商家寻找主题、展示和支持业务的平台。作为主题合作伙伴，你可以为主题商店创建主题，触达不断增长的全球创业者群体。

如果你有兴趣成为 [Shopify 主题合作伙伴](https://themes.shopify.com/services/themes/guidelines) 并为 Shopify 平台构建主题，请确保遵循[主题商店要求](https://shopify.dev/themes/store/requirements)列表。

## 许可证

Copyright (c) 2021-present Shopify Inc. 详见 [LICENSE](/LICENSE.md)。
