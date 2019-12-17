# UnxpectedIdentifier

Execute `yarn dev` 


**I'm submitting a bug report**

>  ERROR in ./src/pages/home/layout.html (./node_modules/html-webpack-plugin/lib/loader.js!./src/pages/home/layout.html)
>     Module build failed (from ./node_modules/**html-loader**/index.js):
>     Error: **Line 14: Unexpected identifier**
>         at ErrorHandler.constructError (C:\Users\xxxxxx\node_modules\esprima\dist\esprima.js:3396:22)

**Line 14 is the where the** `catch` **statement is.**

Layout.html 
```
 <script>
        if ('serviceWorker' in navigator) {
            window.addEventListener('load', () => {
                navigator.serviceWorker.register('p-cache.js') // register the serviceWorker
                    .then(reg => console.log('Service Worker: Registered (Pages)'))
                    .catch(err => console.log(`Service Worker: Error: ${err}`));   // <-- Line 14
            });
        }
    </script>
```

Layout.html is configured as a template page in webpack.config:
 `new HtmlWebpackPlugin({ template :  './src/pages/home/layout.html',`


Everything works fine until I put this script into the head seaction.


**Webpack version:**
4.41.2

**HTML-Loader version:**
 "html-loader": "^0.5.5",

**Please tell us about your environment:**
Windows 10


**Current behavior:**
Error

**Expected/desired behavior:**
No Error

* **If the current behavior is a bug, please provide the steps to reproduce and if possible a minimal demo of the problem along with a gist/jsbin of your webpack configuration.** 


* **What is the expected behavior?**


* **What is the motivation / use case for changing the behavior?**

 
* **Browser:** [all | Chrome XX | Firefox XX | IE XX | Safari XX | Mobile Chrome XX | Android X.X Web Browser | iOS XX Safari | iOS XX UIWebView | iOS XX WKWebView ] 
 
* **Language:** [all | TypeScript X.X | ES6/7 | ES5 | Dart | ...] 
