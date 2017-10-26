# Front-End Checklist 前端開發清單

此為自己翻譯的學習文件，請從此[連結](https://github.com/thedaviddias/Front-End-Checklist)參考原作者 David Dias 的 Github 內容


---

[![Join the chat at https://gitter.im/Front-End-Checklist/Lobby](https://badges.gitter.im/Front-End-Checklist/Lobby.svg)](https://gitter.im/Front-End-Checklist/Lobby?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=badge)
[![Front‑End_Checklist followed](https://img.shields.io/badge/Front‑End_Checklist-followed-brightgreen.svg)](https://github.com/thedaviddias/Front-End-Checklist/)
[![Contributors](https://img.shields.io/github/contributors/thedaviddias/Front-End-Checklist.svg)](https://github.com/thedaviddias/Front-End-Checklist/graphs/contributors)
[![StackShare](https://img.shields.io/badge/tech-stack-0690fa.svg?style=flat)](https://stackshare.io/thedaviddias/front-end-checklist)
[![CC0](https://img.shields.io/badge/license-CC0-green.svg)](https://creativecommons.org/publicdomain/zero/1.0/)

**Front-End Checklist** 是一份在網站 / HTML 頁面發佈到生產環境前，提供所有需要測試元素的詳細清單

這份清單基於前端開發人員多年經驗的累積，以及其他開源清單而成。

## 目錄

1. **[Head](#head)**
2. **[HTML](#html)**
3. **[Webfonts](#webfonts)**
4. **[CSS](#css)**
5. **[Images](#images)**
6. **[JavaScript](#javascript)**
7. **[Security](#security)**
8. **[Performance](#performance-1)**
9. **[Accessibility](#accessibility)**
10. **[SEO](#seo)**

## How to use?

**Front-End Checklist** 中的所有項目都是大部分專案所必需的，但某些元素可以省略或者不是那麼重要（在管理 Web APP 的情況下，你可能不需要 RSS 訂閱）。我們將元素區分成 3 種等級：

* ![Low][low_img] 表示該項目是**推薦**使用的，但在某些特定情況下可以省略。

* ![Medium][medium_img] 表示該項目是**強烈推薦**的，但可能在某些特殊情況下被省略。某些元素如果省略可能會降低性能或 SEO。

* ![High][high_img] 表示項目**不能省略**，否則可能導致頁面有訪問性的功能障礙或 SEO 的問題。應該優先測試這些元素。

某些資源有特定的圖示，幫助你理解清單上不同類型的內容：

* 📖: 文件或文章
* 🛠: 線上工具 / 測試工具
* 📹: 媒體或視頻內容

---

## Head

> **Notes:** 你可以從 [a list of everything](https://github.com/joshbuchea/HEAD) 找到`<head>`標籤內可操作的內容

### Meta tag

* [ ] **Doctype:** ![High][high_img] Doctype 是 HTML5 的標準宣告，寫在 HTML 網頁的開頭

```html
<!-- Doctype HTML5 -->
<!doctype html>
```

> 📖 [Determining the character encoding - HTML5 W3C](https://www.w3.org/TR/html5/syntax.html#determining-the-character-encoding)

*下方 3 個 meta tags (Charset, X-UA Compatible and Viewport) 需要寫於`<head>`標籤內的起始處*

* [ ] **Charset:** ![High][high_img] 正確宣告網頁字符集 ( UTF-8 )

```html
<!-- 設置文檔的字符編碼 -->
<meta charset="utf-8">
```

* [ ] **X-UA-Compatible:** ![Medium][medium_img] 設置 IE 兼容模式

```html
<!-- 指示 Internet Explorer 使用最新的渲染引擎 -->
<meta http-equiv="x-ua-compatible" content="ie=edge">
```

> 📖 [Specifying legacy document modes (Internet Explorer)](https://msdn.microsoft.com/en-us/library/jj676915(v=vs.85).aspx)

* [ ] **Viewport:** ![High][high_img] 正確宣告瀏覽器窗口設置

```html
<!-- 窗口用於響應式網頁設計 -->
<meta name="viewport" content="width=device-width, initial-scale=1">
```

* [ ] **Title:** ![High][high_img] 所有網頁都使用 title ( SEO : Google 計算 title 的 總字符寬度為 472 ~ 482 px 之間， 平均可容納 55 個字元 )

```html
<!-- 文件標題 -->
<title>Page Title less than 65 characters</title>
```

> 📖 [Title - HTML - MDN](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/title)

* [ ] **Description:** ![High][high_img] 提供網頁的描述，它是唯一的且限制於150個字元內

```html
<!-- Meta 描述 -->
<meta name="description" content="Description of the page less than 150 characters">
```

* [ ] **Favicons:** ![Medium][medium_img] 設置網頁的favicon，確保每個 favicon 被創建且顯示正常，如果只有`favicon.ico`，把它放在網站的根目錄下，通常你不需要使用任何標記即可顯示，但最佳做法是以下方範例的方式來連結。現在推薦使用 **PNG** 格式來取代`.ico`格式。( 尺寸 : 32 x 32像素 )

```html
<!-- 標準 favicon -->
<link rel="icon" type="image/x-icon" href="https://example.com/favicon.ico">
<!-- 推薦 favicon 格式 -->
<link rel="icon" type="image/png" href="https://example.com/favicon.png">
```

> * 🛠 [Favicon Generator](https://www.favicon-generator.org/)
> * 🛠 [RealFaviconGenerator](https://realfavicongenerator.net/)
> * 📖 [Favicon Cheat Sheet](https://github.com/audreyr/favicon-cheat-sheet)
> * 📖 [Favicons, Touch Icons, Tile Icons, etc. Which Do You Need? - CSS Tricks](https://css-tricks.com/favicon-quiz/)
> * 📖 [PNG favicons - caniuse](https://caniuse.com/#feat=link-icon-png)

* [ ] **Apple Touch Icon:** ![Low][low_img] 供 Apple 設備呈現的 favicon。( 圖標至少 200 x 200 像素尺寸以支持可能需要的所有尺寸)

```html
<!-- Apple Touch Icon -->
<link rel="apple-touch-icon" href="/custom-icon.png">
```

> 📖 [Configuring Web Applications](https://developer.apple.com/library/content/documentation/AppleApplications/Reference/SafariWebContent/ConfiguringWebApplications/ConfiguringWebApplications.html)

- [ ] **Windows Tiles:**![Low][low_img] windows 的動態磚設置

```html
<!-- Microsoft Tiles -->
<meta name="msapplication-config" content="browserconfig.xml" />
```

browserconfig.xml 文件至少需含以下 xml 標記:

```xml
<?xml version="1.0" encoding="utf-8"?>
<browserconfig>
   <msapplication>
     <tile>
        <square70x70logo src="small.png"/>
        <square150x150logo src="medium.png"/>
        <wide310x150logo src="wide.png"/>
        <square310x310logo src="large.png"/>
     </tile>
   </msapplication>
</browserconfig>
```

> 📖 [Browser configuration schema reference](https://msdn.microsoft.com/en-us/library/dn320426(v=vs.85).aspx)

* [ ] **Canonical:** ![Medium][medium_img] 使用 `rel="canonical"` 來避免重複的內容。( 目的是讓搜尋引擎不要索引放置該宣告的頁面，而去索引指向的頁面 )

```html
<!-- 有助於防止重複內容的問題 -->
<link rel="canonical" href="http://example.com/2017/09/a-new-article-to-red.html">
```

### HTML tags

* [ ] **Language tag:** ![High][high_img] 設置當前頁面使用的語系

```html
<html lang="en">
```

* [ ] **Direction tag:** ![Medium][medium_img] 設置網頁的文章流向 ( 可被設定在其他 HTML 標籤上 )

```html
<html dir="rtl">
```

> 📖 [dir - HTML - MDN](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes/dir)

* [ ] **Alternate language:** ![Low][low_img] 設置當前頁面的替代語系

```html
<link rel="alternate" href="https://es.example.com/" hreflang="es">
```

* [ ] **Conditional comments:** ![Low][low_img] for IE 使用的條件式註解

> 📖 [About conditional comments (Internet Explorer) - MSDN - Microsoft](https://msdn.microsoft.com/en-us/library/ms537512(v=vs.85).aspx)

* [ ] **RSS feed:** ![Low][low_img] 供專案類型為部落格或含有文章的網頁提供 RSS 連結

* [ ] **CSS Critical:** ![Medium][medium_img] CSS critical 集合並渲染頁面中可見部分的 CSS。在主要的 CSS 調用前以單行 ( 最小化 ) 的方式嵌入`<style></style>`中

> 🛠 [Critical by Addy Osmani on Github](https://github.com/addyosmani/critical)

* [ ] **CSS order:** ![High][high_img] `<head>`中的 CSS 文件需於 JavaScript 文件前載入 ( 除了特定情況時 JS 文件會異步加載到頁面上 )

### Social meta

強烈推薦 ***Facebook OG*** 和 ***Twitter Cards*** ，如有特定需求也可使用其他社交媒體標籤以確保功能顯示正常

* [ ] **Facebook Open Graph:** ![Low][low_img] 確保所有 Facebook Open Graph（OG）都經過測試，沒有錯誤或漏掉信息。圖片至少需要 600 x 315 像素，建議使用 1200 x 630 像素。

```html
<meta property="og:type" content="website">
<meta property="og:url" content="https://example.com/page.html">
<meta property="og:title" content="Content Title">
<meta property="og:image" content="https://example.com/image.jpg">
<meta property="og:description" content="Description Here">
<meta property="og:site_name" content="Site Name">
<meta property="og:locale" content="en_US">
```

> * 📖 [A Guide to Sharing for Webmasters](https://developers.facebook.com/docs/sharing/webmasters/)
> * 🛠 Test your page with the [Facebook OG testing](https://developers.facebook.com/tools/debug/)

* [ ] **Twitter Card:** ![Low][low_img]

```html
<meta name="twitter:card" content="summary">
<meta name="twitter:site" content="@site_account">
<meta name="twitter:creator" content="@individual_account">
<meta name="twitter:url" content="https://example.com/page.html">
<meta name="twitter:title" content="Content Title">
<meta name="twitter:description" content="Content description less than 200 characters">
<meta name="twitter:image" content="https://example.com/image.jpg">
```

> * 📖 [Getting started with cards — Twitter Developers](https://developer.twitter.com/en/docs/tweets/optimize-with-cards/guides/getting-started)
> * 🛠 Test your page with the [Twitter card validator](https://cards-dev.twitter.com/validator)

**[⬆ back to top](#table-of-contents)**

---

## HTML

### 最佳做法 ( Best practices )

* [ ] **HTML5 Semantic Elements:** ![High][high_img] 適當的使用 HTML5 語意化元素 (header, section, footer, main...)

> 📖 [HTML Reference](http://htmlreference.io/)

* [ ] **Error pages:** ![High][high_img] 存在 404 和 5xx 錯誤頁面。 5xx 錯誤頁面需要集成其 CSS（當前服務器上無法外部調用）

* [ ] **Noopener:** ![Medium][medium_img] 如果你使用`target="_blank"`外部連結，你的連結應包含屬性`rel="noopener"`來避免釣魚攻擊。如果你需要支援舊版 firefox ，使用`rel="noopener noreferrer"`

> 📖 [About rel=noopener](https://mathiasbynens.github.io/rel-noopener/)

* [ ] **Clean up comments:** ![Low][low_img] 非必要的程式碼應於網頁上線前被清除

### HTML 測試 ( HTML testing )

* [ ] **W3C compliant:** ![High][high_img] 所有頁面都需要通過 W3C 驗證器進行測試，以檢測HTML代碼中可能有的問題。

> 🛠 [W3C validator](https://validator.w3.org/)

* [ ] **HTML Lint:** ![High][high_img] 使用工具幫助分析 HTML 代碼中可能有的問題

> 🛠 [Dirty markup](https://dirtymarkup.com/)

* [ ] **Desktop Browsers:** ![High][high_img] 所有頁面於桌機瀏覽器作測試 ( Safari, Firefox, Chrome, Internet Explorer, EDGE... )

* [ ] **Mobile Browsers:**  ![High][high_img] 所有頁面於行動裝置瀏覽器作測試 ( Native browser, Chrome, Safari... )

* [ ] **Link checker:** ![High][high_img] 確保沒有壞掉的連結以及 404 錯誤頁面的出現

> 🛠 [W3C Link Checker](https://validator.w3.org/checklink)

* [ ] **Adblockers test:** ![Medium][medium_img] 你的網站在啟用廣告攔截器的情況下可正確顯示內容 ( 可以提供一則訊息鼓勵使用者停用廣告攔截器 )

- [ ] **Pixel perfect:** ![High][high_img] 頁面接近完美像素。根據素材的質量，可能不會100％準確，但應盡可能與模板質量接近。

> [Pixel Perfect - Chrome Extension](https://chrome.google.com/webstore/detail/perfectpixel-by-welldonec/dkaagdgjmgdmbnecmcefdhjekcoceebi?hl=en)

**[⬆ back to top](#table-of-contents)**

---

## Webfonts

* [ ] **Webfont format:** ![High][high_img] WOFF, WOFF2 和 TTF 是當代瀏覽器通用的格式

> * 📖 [WOFF - Web Open Font Format - Caniuse](https://caniuse.com/#feat=woff).
> * 📖 [WOFF 2.0 - Web Open Font Format - Caniuse](https://caniuse.com/#feat=woff2).
> * 📖 [TTF/OTF - TrueType and OpenType font support](https://caniuse.com/#feat=ttf)
> * 📖 [Using @font-face - CSS-Tricks](https://css-tricks.com/snippets/css/using-font-face/)

* [ ] **Webfont size:** ![High][high_img] Webfont 檔案大小不要超過 2 MB (含所有版本).

**[⬆ back to top](#table-of-contents)**

---

## CSS

> **Notes:** 大部分前端開發人員都會參考 [CSS guidelines](https://cssguidelin.es/) 和 [Sass Guidelines](https://sass-guidelin.es/) 。如果你對 CSS 屬性有疑問，可以訪問 [CSS Reference](http://cssreference.io/)。

* [ ] **Responsive Web Design:** ![High][high_img] 網站使用響應式設計
* [ ] **CSS Print:** ![Medium][medium_img] 提供列印模式下的 CSS 樣式呈現，確保每個頁面都顯示正常
* [ ] **Preprocessors:** ![Medium][medium_img] 你的頁面有使用 CSS 預處理器 ( 推薦使用 [Sass](http://sass-lang.com/) )
* [ ] **Unique ID:** ![High][high_img] 確保每個頁面中的 ID 都是唯一的
* [ ] **Reset CSS:** ![High][high_img] 使用最新的 CSS reset ( reset, normalize 或者 reboot )，如使用 Bootstrap 或 Foundation 等的 CSS 框架，框架本身已包含 reset 設置

> * 📖 [Reset.css](https://meyerweb.com/eric/tools/css/reset/)
> * 📖 [Normalize.css](https://necolas.github.io/normalize.css/)
> * 📖 [Reboot](https://getbootstrap.com/docs/4.0/content/reboot/)

* [ ] **JS prefix:** ![Low][low_img] 有前綴 **js-** 的 class、id 不要作為 CSS 樣式套用

```html
<div id="js-slider" class="my-slider">
<!-- Or -->
<div id="id-used-by-cms" class="js-slider my-slider">
```

* [ ] **CSS embed or line:** ![High][high_img] 避免使用內嵌或行內 CSS : 僅用於有必要的時候 ( 例 : slider 的 background-image， CSS critical 等 )
* [ ] **Vendor prefixes:** ![High][high_img] 使用供應商的 CSS 前綴，讓瀏覽器支援兼容性。

> 🛠 [Autoprefixer CSS online](https://autoprefixer.github.io/)

### 性能 ( Performance )

- [ ] **Concatenation:** ![High][high_img] CSS 文件合併成一個文件 ( 不適用於 HTTP/2 )
- [ ] **Minification:** ![High][high_img] 所有 CSS 文件作最小化壓縮
- [ ] **Non-blocking:** ![Medium][medium_img] 避免因 CSS 文件阻塞導致花更多時間載入 DOM

> * 📖 [loadCSS by filament group](https://github.com/filamentgroup/loadCSS)
> * 📖 [Example of preload CSS using loadCSS](https://gist.github.com/thedaviddias/c24763b82b9991e53928e66a0bafc9bf)

- [ ] **Unused CSS:** ![Low][low_img] 移除未使用的 CSS

> * 🛠 [UnCSS Online](https://uncss-online.com/) 🛠
> * 🛠 [PurifyCSS](https://github.com/purifycss/purifycss)
> * 🛠 [Chrome DevTools Coverage](https://developers.google.com/web/updates/2017/04/devtools-release-notes#coverage)


### CSS 測試 ( CSS testing )

* [ ] **Stylelint:** ![High][high_img] 所有 CSS 或 SCSS 文件沒有任何錯誤

> * 🛠 [stylelint, a CSS linter](https://stylelint.io/)
> * 📖 [Sass guidelines](https://sass-guidelin.es/)

* [ ] **Responsive web design:** ![High][high_img] 所有頁面經過以下斷點測試 : 320px, 768px, 1024px ( 根據不同需求可以設定更多斷點 )

* [ ] **CSS Validator:** ![Medium][medium_img] CSS 經過測試，並排除相關的錯誤。

> 🛠 [CSS Validator](https://jigsaw.w3.org/css-validator/)

* [ ] **Reading direction:** ![High][high_img] 如果有文章流向的需求，應測試所有頁面的 LTR 和 RTL languages 顯示

> * 📖 [Building RTL-Aware Web Apps & Websites: Part 1 - Mozilla Hacks](https://hacks.mozilla.org/2015/09/building-rtl-aware-web-apps-and-websites-part-1/)
> * 📖 [Building RTL-Aware Web Apps & Websites: Part 2 - Mozilla Hacks](https://hacks.mozilla.org/2015/10/building-rtl-aware-web-apps-websites-part-2/)

**[⬆ back to top](#table-of-contents)**

---

## Images

> **Notes:** 想了解更完整的圖片優化內容，請查看 Addy Osmani 的 **[Essential Image Optimization](https://images.guide/)**

### 最佳做法 ( Best practices )

* [ ] **Optimization:** ![High][high_img] 所有圖像都經過優化且可在瀏覽器中呈現。 WebP 格式可用於關鍵頁面（如首頁）

> * 🛠 [Imagemin](https://github.com/imagemin/imagemin)
> * 🛠 Use [ImageOptim](https://imageoptim.com/) to optimise your images for free.

* [ ] **Retina:** ![Low][low_img] 提供x2 或 3x 的圖像以支持視網膜顯示
* [ ] **Sprite:** ![Medium][medium_img] 小圖片統一存成一個 sprite 檔 ( icons 可統一存成一個 SVG sprite )
* [ ] **Width and Height:** ![High][high_img] 所有`<img>`標籤有設定 width 和 height ( 不含單位 px 或 % )

> ***Note:*** 許多開發人員認為設定圖片寬高會與響應式設計不兼容，但實際上不是這樣。

* [ ] **Alternative text:** ![High][high_img] 所有`<img>`應有替代文字 ( alt ) 來描述圖片內容
* [ ] **Lazy loading:** ![Medium][medium_img] 圖片使用 lazyloaded ( 也應提供 noscript 當作備案 )

**[⬆ back to top](#table-of-contents)**

---

## JavaScript

### 最佳做法 ( Best practices )

* [ ] **JavaScript Inline:** ![High][high_img] 避免使用行內 JavaScript ( 與 HTML 寫在一起 )
* [ ] **Concatenation:** ![High][high_img] 合併 JavaScript 文件
* [ ] **Minification:** ![High][high_img] JavaScript 文件最小化壓縮 ( 可於檔名加入後綴 `.min` )

> [Minify Resources (HTML, CSS, and JavaScript)](https://developers.google.com/speed/docs/insights/MinifyResources)

* [ ] **JavaScript security:**

> [Guidelines for Developing Secure Applications Utilizing JavaScript](https://www.owasp.org/index.php/DOM_based_XSS_Prevention_Cheat_Sheet#Guidelines_for_Developing_Secure_Applications_Utilizing_JavaScript)*

* [ ] **Non-blocking:** ![Medium][medium_img] 使用`async`或是`defer`屬性來異步載入 JavaScript 文件

> 📖 [Remove Render-Blocking JavaScript](https://developers.google.com/speed/docs/insights/BlockingJS)

* [ ] **Modernizr:** ![Low][low_img] 如果你需要某些特定功能，可以使用自定義 Modernizr 在`<html>`標籤中添加 classes。

> 🛠 [Customize your Modernizr](https://modernizr.com/download?setclasses)

### JavaScript 測試 ( JavaScript testing )

* [ ] **ESLint:** ![High][high_img] 沒有被 ESLint 標記錯誤（ 根據你的配置或標準規則 ）

> * 📖 [ESLint - The pluggable linting utility for JavaScript and JSX](https://eslint.org/)

**[⬆ back to top](#table-of-contents)**

---

## Security

### 掃瞄並檢查網站 ( Scan and check your web site )

> * [securityheaders.io](https://securityheaders.io/)
> * [Observatory by Mozilla](https://observatory.mozilla.org/)
> * [ASafaWeb - Automated Security Analyser for ASP.NET Websites](https://asafaweb.com/)

### 最佳做法 ( Best practices )

* [ ] **HTTPS:** ![Medium][medium_img] 使用 HTTPS 於每個頁面和所有外部內容 ( 插件，圖像... )

> * 🛠 [Let's Encrypt - Free SSL/TLS Certificates](https://letsencrypt.org/)
> * 🛠 [Free SSL Server Test](https://www.ssllabs.com/ssltest/index.html)
> * 📖 [Strict Transport Security](http://caniuse.com/#feat=stricttransportsecurity)

* [ ] **HTTP Strict Transport Security (HSTS):** ![Medium][medium_img] HTTP header 設置為 “強制安全傳輸”。

> * 🛠 [Check HSTS preload status and eligibility](https://hstspreload.org/)
> * 📖 [HTTP Strict Transport Security Cheat Sheet - OWASP](https://www.owasp.org/index.php/HTTP_Strict_Transport_Security_Cheat_Sheet)
> * 📖 [Transport Layer Protection Cheat Sheet - OWASP](https://www.owasp.org/index.php/Transport_Layer_Protection_Cheat_Sheet)

* [ ] **Cross Site Request Forgery (CSRF):** ![High][high_img] 確保向你的服務器端發出的請求是合法且來自你的網站/應用程序，以防止發生CSRF攻擊。

> 📖 [Cross-Site Request Forgery (CSRF) Prevention Cheat Sheet  - OWASP](https://www.owasp.org/index.php/Cross-Site_Request_Forgery_(CSRF)_Prevention_Cheat_Sheet)

* [ ] **Cross Site Scripting (XSS):** ![High][high_img] 你的網頁或網站沒有跨網站指令碼的問題。

> * 📖 [XSS (Cross Site Scripting) Prevention Cheat Sheet  - OWASP](https://www.owasp.org/index.php/XSS_(Cross_Site_Scripting)_Prevention_Cheat_Sheet)
> * 📖 [DOM based XSS Prevention Cheat Sheet  - OWASP](https://www.owasp.org/index.php/DOM_based_XSS_Prevention_Cheat_Sheet)

* [ ] **Content Type Options** ![Medium][medium_img] 阻止 Google Chrome 和 Internet Explorer 嘗試將響應的內容類型與服務器聲明的內容類型進行比較

> * 📖 [X-Content-Type-Options - Scott Helme](https://scotthelme.co.uk/hardening-your-http-response-headers/#x-content-type-options)

* [ ] **X-Frame-Options (XFO)** ![Medium][medium_img] 保護你的訪客免受駭客攻擊

> * 📖 [X-Frame-Options - Scott Helme](https://scotthelme.co.uk/hardening-your-http-response-headers/#x-frame-options)
> * 📖 [RFC7034 - HTTP Header Field X-Frame-Options](https://tools.ietf.org/html/rfc7034)

**[⬆ back to top](#table-of-contents)**

---

## Performance

### 最佳做法 ( Best practices )

- [ ] **Weight page:** ![High][high_img] 每個頁面大小於 0 ~ 500KB 之間

> * 🛠 [Website Page Analysis](https://tools.pingdom.com)
> * 📖 [Size Limit: Make the Web lighter](https://evilmartians.com/chronicles/size-limit-make-the-web-lighter)

- [ ] **Minified:** ![Medium][medium_img] 你的 HTML 有最小化壓縮
> 🛠 [W3C Validator](https://validator.w3.org/)

* [ ] **Lazy loading:** ![Medium][medium_img] 圖片，腳本和 CSS 需要 lazy loaded 以改善當前頁面的響應時間 ( 請見各部分的詳細說明 )

* [ ] **Cookie size:** 如果使用 Cookie，請確保每個 Cookie 不超過 4096 個字節，且域名下不超過 20 個 cookie

> * 📖 [Cookie specification: RFC 6265](https://tools.ietf.org/html/rfc6265)
> * 📖 [Cookies](https://developer.mozilla.org/en-US/docs/Web/HTTP/Cookies)
> * 🛠 [Browser Cookie Limits](http://browsercookielimits.squawky.net/)

### 準備即將到來的請求 ( Preparing upcoming requests )

> 📖 [Explanation of the following techniques](https://css-tricks.com/prefetching-preloading-prebrowsing/)

* [ ] **DNS resolution:** ![Low][low_img] 使用`dns-prefetch`於空閒時間提前載入第三方服務器的 DNS

```html
<link rel="dns-prefetch" href="https://example.com">
```

* [ ] **Preconnection:** ![Low][low_img] 使用`preconnect`提前在空閒時間完成服務器的 DNS 查詢，TCP 三向交握以及 TLS 協商。

```html
<link rel="preconnect" href="https://example.com">
```

* [ ] **Prefetching:** ![Low][low_img] 使用`prefetch`提前在空閒時間請求即將需要的資源 ( 例 : lazy lorded 的圖像 )

```html
<link rel="prefetch" href="image.png">
```

* [ ] **Preloading:** ![Low][low_img] 使用`preload`提前加載當前頁面需要的資源 ( 例 : 放在`<body>`結尾處的 script )

```html
<link rel="preload" href="app.js">
```

> 📖 [Difference between prefetch and preload](https://medium.com/reloading/preload-prefetch-and-priorities-in-chrome-776165961bbf)

### 效能測試 ( Performance testing )

* [ ] **Google PageSpeed:** ![High][high_img] 所有的網頁都經過測試 ( 不僅是首頁 )，且至少達到 90/100 的評分

> * 🛠 [Google PageSpeed](https://developers.google.com/speed/pagespeed/insights/)
> * 🛠 [Test your mobile speed with Google](https://testmysite.withgoogle.com)
> * 🛠 [WebPagetest - Website Performance and Optimization Test](https://www.webpagetest.org/)

**[⬆ back to top](#table-of-contents)**

---

## Accessibility

> **Notes:** 你可以參考播放清單 [A11ycasts with Rob Dodson](https://www.youtube.com/playlist?list=PLNYkxOF6rcICWx0C9LVWWVqvHlYJyqw7g) 📹

### 最佳做法 ( Best practices )

- [ ] **Progressive enhancement:** ![Medium][medium_img] 主要功能如主導航和搜尋應該在沒有啟用 JavaScript 的情況下工作

> 📖 [Enable / Disable JavaScript in Chrome Developer Tools](https://www.youtube.com/watch?v=kBmvq2cE0D8)

- [ ] **Color contrast:** ![Medium][medium_img] 顏色對比應至少通過 WCAG AA 標準 ( AAA for 行動裝置 )

> 🛠 [Contrast ratio](https://leaverou.github.io/contrast-ratio/)

#### Headings

* [ ] **H1:** ![High][high_img] 所有頁面都有非網站 title 的 H1 標籤
* [ ] **Headings:** ![High][high_img] 標題應使用正確的順序 ( H1 至 H6 )

> 📹 [Why headings and landmarks are so important -- A11ycasts #18](https://www.youtube.com/watch?v=vAAzdi1xuUY&index=9&list=PLNYkxOF6rcICWx0C9LVWWVqvHlYJyqw7g)

#### Landmarks

- [ ] **Role banner:** ![High][high_img] `<header>`有`role="banner"`屬性
- [ ] **Role navigation:** ![High][high_img] `<nav>`有`role="navigation"`屬性
- [ ] **Role main:** ![High][high_img] `<main>`有`role="main"`屬性

> 📖 [Using ARIA landmarks to identify regions of a page](https://www.w3.org/WAI/GL/wiki/Using_ARIA_landmarks_to_identify_regions_of_a_page)

### 語意化 ( Semantics )

- [ ] **Specific HTML5 input types are used:** ![Medium][medium_img] 對於顯示自定義鍵盤和不同類型小工具的行動裝置尤其重要。

> 📖 [Mobile Input Types](http://mobileinputtypes.com/)

### 表單 ( Form )

* [ ] **Label:** ![High][high_img] 標籤與每個輸入表單元素相關聯。如果無法顯示標籤，請改用`aria-label`

> 📖 [Using the aria-label attribute - MDN](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/ARIA_Techniques/Using_the_aria-label_attribute)

### 無障礙測試 ( Accessibility testing )

* [ ] **Accessibility standards testing:** ![High][high_img] 使用 WAVE 工具測試頁面是否符合輔助功能標準

> 🛠 [Wave testing](http://wave.webaim.org/)

* [ ] **Keyboard navigation:** ![High][high_img] 僅用鍵盤以可能出現的操作順序測試你的網站，確保所有互動元素都可訪問及使用
* [ ] **Screen-reader:** ![Medium][medium_img] 所有頁面經過螢幕閱讀器的測試 ( VoiceOver, ChromeVox, NVDA or Lynx )
* [ ] **Focus style:** ![High][high_img] 如果 focus 被禁用，使用 CSS 的可見狀態替代

> 📹 [Managing Focus - A11ycasts #22](https://www.youtube.com/watch?v=srLRSQg6Jgg&index=5&list=PLNYkxOF6rcICWx0C9LVWWVqvHlYJyqw7g)

**[⬆ back to top](#table-of-contents)**

---

## SEO

* [ ] **Google Analytics:** ![High][high_img] 安裝 Google Analytics 且正確配置
* [ ] **Headings logic:** ![Medium][medium_img] 標題文字有助於了解當前頁面中的內容
* [ ] **sitemap.xml:** ![High][high_img] 有 sitemap.xml 檔，並提交給 Google Search Console ( 以前的 Google 網站管理員工具 )
* [ ] **robots.txt:** ![High][high_img] The robots.txt 沒有阻擋網頁被搜索

> * 🛠 Test your robots.txt with [Google Robots Testing Tool](https://www.google.com/webmasters/tools/robots-testing-tool)

* [ ] **Structured Data:** ![High][high_img] 使用結構化數據的頁面經過測試且沒有錯誤。結構化數據有助於爬蟲工具了解當前頁面的內容

> * 📖 [Introduction to Structured Data - Search - Google Developers](https://developers.google.com/search/docs/guides/intro-structured-data)
> * 🛠 Test your page with the [Structured Data Testing Tool](https://developers.google.com/structured-data/testing-tool/)

* [ ] **Sitemap HTML:** ![Medium][medium_img] 提供 HTML 網站地圖，可通過網站頁尾中的鏈接進行訪問

> * 📖 [Sitemap guidelines - Google Support](https://support.google.com/webmasters/answer/183668?hl=en)
> * 🛠 [Sitemap generator](https://websiteseochecker.com/html-sitemap-generator/)


**[⬆ back to top](#table-of-contents)**

---

## Translation

The Front-End Checklist 也提供其他語言版本，感謝所有的翻譯者!


* 🇯🇵 Japanese: [miya0001/Front-End-Checklist](https://github.com/miya0001/Front-End-Checklist)
* 🇪🇸 Spanish: [eoasakura/Front-End-Checklist-ES](https://github.com/eoasakura/Front-End-Checklist-ES)
* 🇨🇳 Chinese: [JohnsenZhou/Front-End-Checklist](https://github.com/JohnsenZhou/Front-End-Checklist)
* 🇰🇷 Korean: [kesuskim/Front-End-Checklist](https://github.com/kesuskim/Front-End-Checklist)
* 🇧🇷 Portuguese: [jcezarms/Front-End-Checklist](https://github.com/jcezarms/Front-End-Checklist)

---

## Front-End Checklist Badge

如果想顯示你有遵循前端清單的規定，請將此徽章放在 README 文件上！

➔ [![Front‑End_Checklist followed](https://img.shields.io/badge/Front‑End_Checklist-followed-brightgreen.svg)](https://github.com/thedaviddias/Front-End-Checklist/)

```md
[![Front‑End_Checklist followed](https://img.shields.io/badge/Front‑End_Checklist-followed-brightgreen.svg)](https://github.com/thedaviddias/Front-End-Checklist/)
```

**[⬆ back to top](#table-of-contents)**

---

## Contributing

**透過 issue 或 pull request 來建議更改或添加內容**

### Guide

**Front-End Checklist** 由兩個分支組成 :

#### 1. `master`

該分支包含自動反映在 [Front-End Checklist](http://frontendchecklist.com/) 網站上的`README.md`文件

#### 2. `develop`

這個分支用於對結構及內容進行一些重大更改。最好使用主分支來修復小錯誤或添加新項目

### Contributors

查看所有 [contributors](https://github.com/thedaviddias/frontendchecklist/graphs/contributors)

## Support

如果你有任何疑問或建議，可透過 Gitter or Twitter 與我聯繫 :

* [Chat on Gitter](https://gitter.im/Front-End-Checklist/Lobby?utm_source=share-link&utm_medium=link&utm_campaign=share-link)
* [Twitter](https://twitter.com/thedaviddias)

## Authors

**[David Dias](https://github.com/thedaviddias/Front-End-Checklist)**

## License

[![CC0](https://i.creativecommons.org/p/zero/1.0/88x31.png)](https://creativecommons.org/publicdomain/zero/1.0/)

**[⬆ back to top](#table-of-contents)**

[low_img]: http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-low.png
[medium_img]: http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-medium.png
[high_img]: http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-high.png
