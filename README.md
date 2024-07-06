# vue-proj-test

小白在學習 Vue 的路上  
目標是希望能做成個人blog  
可能會胎死腹中~~  
這專案只有使用 **前端** 技術並且用 **github pages** 展示  
```sh
# Proj：vue-proj-test
# Author：LiuYan
# CreateDate：2024/07/06
```

# 基本工具
包括一些會用到 **軟體** 、官方 **Document**
## 軟體
- IDE：[VS Code](https://code.visualstudio.com/)  
- VS code 的 Vue 開發輔助套件：[Volar](https://marketplace.visualstudio.com/items?itemName=Vue.volar)
## Document
- [Vue](https://vuejs.org/guide/introduction.html)
- [W3School-JS](https://www.w3schools.com/js/default.asp)


# 從建立 Vue 專案到 傳上 Github 且使用 Github Pages
## 參考影片
> [**How to Deploy Your Vite App to Github Pages**](https://www.youtube.com/watch?v=yo2bMGnIKE8&t=155s&ab_channel=LearnVue)  
> Url ：https://youtu.be/yo2bMGnIKE8?si=DyUMHtF53jNawXJI
## 步驟
建立 Vue 專案
```sh
# 初始化建專案
npm create vue@latest

cd <專案名稱>
npm install
```
修改 **vite.config.js**
```js
export default defineConfig({

    //添加這行
    base: "/<專案名稱>/"

})
```
Git 初始化
```sh
git init
git add .
git commit -m "<訊息>"
```
推到 Github
```
git remote add origin <Github repository 網址>
git branch -M main
git push -u origin main
```
Vue 打包
```sh
npm run build
```
打包完會產生 **dist** 資料夾
```sh
# 把他 commit 起來
git add dist -f
git commit -m "<訊息>"
```
創建 [**subtree**](https://docs.github.com/en/get-started/using-git/about-git-subtree-merges) 分支，推送 **dist**
```sh
git subtree push --prefix dist origin gh-pages
```