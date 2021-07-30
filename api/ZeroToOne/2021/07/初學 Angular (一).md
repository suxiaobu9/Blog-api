# 環境設定

1. 安裝 Chocolatey

   - Powershell 管理者權限

   ```powershell
   Set-ExecutionPolicy Bypass -Scope Process -Force; [System.Net.ServicePointManager]::SecurityProtocol = [System.Net.ServicePointManager]::SecurityProtocol -bor 3072; iex ((New-Object System.Net.WebClient).DownloadString('https://chocolatey.org/install.ps1'))
   ```

1. 安裝工具

   1. Google Chrome
   1. git
   1. nodejs
   1. vs code

   - Powershell 管理者權限

   ```powershell
   choco install -y GoogleChrome git nodejs visualstudiocode
   ```

1. 安裝 angular cli

   - cmd

     ```cmd
     npm i -g @angular/cli
     ```

1. 安裝 vs Code 擴充套件包

   - cmd

     ```cmd
     保哥的angular擴充套件包
     code --install-extension "doggy8088.angular-extension-pack"
     ```

1. 新增一個 angular 專案

   - cmd

     ```cmd
     cd C:\
     mkdir CodeSource
     cd C:\CodeSource
     ng new demo1

     Would you like to add Angular routing? y
     Which stylesheet format would you like to use? CSS
     ```

1. 進入資料夾，開啟 vscode

   - cmd

     ```cmd
     cd demo1
     code .
     ```

   這邊可以發現，之前下指令裝的 angular 擴充套件包安裝成功

   ![image](https://user-images.githubusercontent.com/37999690/127256465-c020da75-c115-4a57-859a-1a92438cac1b.png)

1. 更改 package.json 後儲存 ，讓 angular 跑完可以自動開啟網頁

```json
{
  ...
  "scripts": {
    ...
    "start": "ng serve -o",
    ...
  },
  ...
}
```

1. 在 vs code 中開啟終端機(快捷鍵 `Ctrl+`\` )用終端機把 angular 跑起來

   ```powershell
    # powershell
    npm start
   ```

   ![image](https://user-images.githubusercontent.com/37999690/127257137-88633b68-dca6-4e86-8b16-1329c9c6cea7.png)

   因為改 `package.json` 的關係，瀏覽器會自動開啟初始 angular 頁面

   ![image](https://user-images.githubusercontent.com/37999690/127256178-90d1aedf-4b55-4ff5-b593-e572f6de3d38.png)

## 資料夾內容

1. src

   > angular 應用程式主要的原始碼

   1. src\ `app`

      > 應用程式主檔案

   1. src\ `index.html`

      > 主要進入的 html (首頁)

   1. src\ `styles.css`

      > 全域用的 css

   1. src\ `main.ts`

      > - 初始進入程式，預設匯入 app.codule.ts。
      > - main.ts -> app.module.ts -> app.component.ts

1. src\app

   - `*.component.ts`

     > 主要處理 TypeScript 邏輯的檔案

   - `*.component.html`

     > \*.component.ts 的 html 範本

   - `*.component.css`

     > 專屬於 \*.component.html 的 css

   - `*.component.spec.ts`

     > 單元測試用的，定義如何測試這個 component

1. `angular.json`

   > Angular CLI 的設定檔

1. `.editorconfig`

   > 編輯器設定檔，告知編輯器 (在這邊就是 vs code) 如何處理 tab 符號、換行符號

1. `.gitignore`

   > 定義不用進版控的檔案或資料夾

1. `package.json`

   > 目前專案的 npm 設定檔

1. `tsconfig.json`

   > TypeScript 相關設定

1. `node_module`

   > 透過 npm 安裝的套件

1. `assets`

   > - 通常會放 angular 需要的靜態檔案
   > - 靜態檔案需要在 `angular.json` 的 build : options : assets 加入路徑
   > - assets\.getkeep 是為了讓 git 版控時不要忽略空資料夾

1. `environments`

   > - angular 用到的環境變數，可以在不同開發環境使用不同變數
   >
   > ```typescript
   > // environment.ts 開發環境
   > export const environment = {
   >  production: false
   >  api: 'http://localhost:port/'
   > };
   > ```
   >
   > ```typescript
   > // environment.prod.ts 正式環境
   > export const environment = {
   >  production: true
   >  api: 'http://www.YourApi.com/'
   > };
   > ```
   >
   > 這樣在 local 端開發時，程式吃到的 api 就會是 <http://localhost:port/>，發布時 api 就會是 <http://www.YourApi.com/>

1. src\ `favicon.icon`

   ![image](https://user-images.githubusercontent.com/37999690/127420930-746738b6-41ae-4a81-a3bb-053819212701.png)

1. src\ `polyfills.ts`

   > 對舊瀏覽器(IE)的相容性設定

1. `karma.conf.js`

   > karma 這個單元測試工具會用到的設定

1. src\ `test.ts`

   > 單元測試所需要的檔案，`karma.conf.js` 會需要他
