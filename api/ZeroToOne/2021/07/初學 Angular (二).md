# 介紹 VS Code

1. 編輯區域
   ![image](https://user-images.githubusercontent.com/37999690/127434268-3a21da40-2774-4cde-b37d-c981846094e2.png)

1. 功能區域 - 檔案總管、搜尋、Git、Debug、擴充套件

   ![image](https://user-images.githubusercontent.com/37999690/127434548-807397dc-e0bd-4778-b2a8-b9b4efb9413f.png)

1. 控制命令 : 輸入關鍵字，搜尋 VS Code 功能 ( `F1` )

   ![image](https://user-images.githubusercontent.com/37999690/127434692-aa0ef88b-8b4a-42e2-9e43-af83af05492e.png)

1. 開啟、關閉終端機 ( `Ctrl +` ` )

   ![image](https://user-images.githubusercontent.com/37999690/127434861-8ba829af-47d2-4b94-8ef5-3ede68033029.png)

1. 搜尋檔案 ( `Ctrl + E` )
   ![image](https://user-images.githubusercontent.com/37999690/127438905-fb8f94c7-1264-4ae8-bc3c-103342b44927.png)

1. 錯誤提示
   ![image](https://user-images.githubusercontent.com/37999690/127440112-5232828d-05a6-46fc-a734-7b520032690c.png)

## angular 組成

> Angular 應用程式會包含模組(module)，而模組底下又會包含許多子元件(Component)

![image](https://user-images.githubusercontent.com/37999690/127448980-cab8de9a-0d94-4a3e-9273-8047e6756247.jpg)

> Angular 的頁面會透過 js 去呼叫元件出來執行，元件再呼叫樣板(html)呈現在畫面上，動態呈現 js

![image](https://user-images.githubusercontent.com/37999690/127452898-d0b9d157-0351-4e80-99ca-8e0b83c1e4ae.jpg)

## Component

![image](https://user-images.githubusercontent.com/37999690/127620894-24363d45-d7e7-4a39-815f-cfc408a9df41.png)

以 App.Component.ts 為例，他的 selector 可以對應到 index.html 的 `<app-root></app-root>`，也就是說，網頁啟動時會先啟動 module，然後呼叫 Component 去讀取 css 以及 template，再將 相對應的 selector 取代掉。

## npm start

![image](https://user-images.githubusercontent.com/37999690/127457685-05ae8420-9ee3-4a12-a74f-c19dab1573e7.png)

> 其實 `npm start` 這個指令是幫我們下 `ng serve -o`
>
> 並且在開發伺服器啟動之前，透過 Webpack 把目前 source code 中所有的 TypeScript 編譯成 JavaScript 檔，再把所有的 JacaScript 合併再一起
> Webpack 會幫我們產生以下檔案
>
> 1. vender.js
> 1. polyfills.js
> 1. style.css
> 1. style.js
> 1. main.js
> 1. runtime.js
>
> 在我們打開首頁(index.html)時，就會預設載入這些檔案
> ![image](https://user-images.githubusercontent.com/37999690/127458600-6c379c9a-9be3-4559-acf0-c00a5d2e8025.png)
