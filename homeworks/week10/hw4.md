## gulp 跟 webpack 有什麼不一樣？我們可以不用它們嗎？
> 1. gulp 是為了讓開發者用自動化的方式處理檔案，包括壓縮、轉譯、改名等等。  
> 2. webpack 是為了讓檔案可以在瀏覽器上執行，其中讓開發者可以用模組化的方式開發，再用 webpack 轉化是 gulp 沒有的優勢。  
> 3. 舉第二題的作業為例， webpack 轉譯 index.js，讓其中引用 utils.js 的行為可以在瀏覽器上使用，不用特別指定還需要參考哪個檔案，比較 gulp 需要開發者自己決定要處理哪些檔案，用途和用法都是不同的。  
> 4. webpack 可以取代 gulp 嗎？（猜測 webpack 也有一些套件可以下載，例如 `rename-webpack-plugin` 提供了改名的功能，是和 `gulp-rename` 相同的），但這兩個套件適用的範圍不同，參考[這篇](https://hk.saowen.com/a/f4901f997ad5a0ea56f2828f29bc826aaa27e75158d769e63e15fb1780701bef)，webpack 的適用範圍是專案依賴較複雜的檔案結構， gulp 則較彈性，可大可小，比如說作業 1 只需要壓縮和轉譯 `.js` 和 `.sass` 檔。  
> 5. 可以不用，只是用了通常比較安全跟方便。  

## hw3 把 todo list 這樣改寫，可能會有什麼問題？
> 1. 原本就已經存在的元素需要移除再重新渲染，是多餘的行為。
> 2. 如果要重新渲染的東西很多，就需要花費很多效能。
> 3. 如果使用者一直觸發渲染，就會一直需要重新更新畫面（可能永遠無法顯示完整的畫面(?）。

## CSS Sprites 與 Data URI 的優缺點是什麼？
> 1. CSS Sprites
>    - 原理：把原本分開的圖片合併成一個圖片，後用 css 可以調整位置的方式讓圖片正確顯示。
>    - 好處：原本需要分開請求的圖片透過 CSS Sprites 只需要請求一次。
>    - 壞處：修改可想而知的麻煩(?，要小心計算位置與大小，且因元素都在同一張上，所以其中一個修改都會影響到其他的元素。
> 2. Data URI
>    - 原理：把圖片用 base64 編碼，直接填入 html 檔。
>    - 好處：不用請求圖片。
>    - 壞處：因為是文字所以瀏覽器不能快取、更換圖片就要重新修改 html、會讓 html 檔案變大、可讀性較圖片差許多。
> 3. 哪個比較好?
>    - [這篇](https://www.oschina.net/translate/css-sprites-vs-data-uris-which-is-faster-on-mobile?lang=chs&p=1) 做實驗的結果是 CSS Sprites 還是比 Data URI 快，在快取（但 Data URI 不是不能快取?）下兩個也都會變快，也說 Data URI 不要大於3-5個。
>    #### Q：通常會用哪個呢？ （猜測還是 CSS Sprites？）
