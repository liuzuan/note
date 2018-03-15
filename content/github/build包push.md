## <font color=#0099ff size=5 face="黑体">build快速push到github分支ph-pages</font>
----

* 问题：我们每次修改代码后重新打包并将打包后的文件上传到github仓库分支，很麻烦。
* 办法：我们采用一个 npm 包，来帮助我们完成上面的操作：

```
cd my-project/
npm i --save gh-pages
```
* 然后创建 my-project/scripts/deploy-gh-pages.js,添加内容：

```
'use strict';

var ghpages = require('gh-pages');

main();

function main() {
    ghpages.publish('./gh-pages', console.error.bind(console));
}
// ./pg-pages为打包后的文件夹路径，文件夹名视情况修改
```

* package.json 中添加这些代码：

```
"scripts": {
 "deploy": "node ./scripts/deploy-gh-pages.js",
 "publish": "npm run build && npm run deploy",
 "port": "lsof -i :35729"
},
```

* 这样，每次有了修改，运行如下命令完成打包和上传工作

```
npm run publish
```