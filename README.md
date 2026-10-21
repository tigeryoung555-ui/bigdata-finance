# 大数据财务分析与决策学习网站

《大数据财务分析与决策》课程**单文件自包含**离线学习平台，通过 GitHub Pages 直接托管。

## 这是什么

- 整站只有一个文件：`index.html`（约 1.1MB）。
- 所有样式、脚本、图片（base64）已全部内联，**无任何外部请求**，离线可用、断网也能打开。
- 覆盖：登录（教师 / 学生双角色）、6 个课程模块、案例、实验、3 套测验、成绩按方案 A/B 计算并存 `localStorage`。

## 线上访问

推送到 GitHub 后访问：

```
https://<你的用户名>.github.io/<仓库名>/
```

若放在某个仓库的子目录，则为：

```
https://<你的用户名>.github.io/<仓库名>/<子目录名>/
```

## 如何更新内容（重要）

`index.html` 是**打包产物**，不要直接改。源码与工具链在原始工程目录：

```
D:\Documents\qwen-agent\h3y0n8t3sp\default\大数据财务分析与决策学习网站-20260904T234518490Z\
```

标准维护流程：

1. 改源码：`src/*.js`（data.js 题库/课程、images.js 图片、app.js 逻辑）或根 HTML 的 `<style>`。
2. 重新打包：在该目录运行 `node pack.js`，会重新生成 `history/v1/delivery/大数据财务分析与决策学习网站.html`。
3. 拷回本仓库：把上一步产物覆盖为 `github-pages/index.html`。
4. 自检：在该目录运行 `node verify.js`（jsdom 实跑体检，应 12/12 通过、0 报错）。
5. `git add index.html && git commit && git push`。

## 学生入口二维码

拿到线上 URL 后，在原始工程目录运行：

```
node gen_qr.js https://<你的用户名>.github.io/<仓库名>/
```

生成 `学生入口二维码.png`，学生用**系统相机扫**即可打开。

## 说明

- 移动端已做 `@media(max-width:768px)` 适配（底部固定导航栏）。
- 托管在 GitHub Pages；国内访问可能偶发较慢，如需稳定可同步一份到腾讯云 LighthouseCOS / CloudBase。
