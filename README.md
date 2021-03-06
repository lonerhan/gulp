# gulp构建工具
> * 支持LESS、SASS转CSS，支持CSS自动添加前缀；
> * 支持JS校验、压缩；支持图片压缩；
> * 支持静态资源版本管理；

---
## 构建过程:
``` bash
# 全局安装gulp
npm i -g gulp

# shell 切换至工作目录（`gulpfile.js`存放目录）
cd xxx/xx

# 安装依赖
npm i

# 开发构建（在 localhost:3333 端口、支持热重启）
npm run dev

# 生产构建
npm run build
```

---
## 基本目录:
#### 截图:
![目录结构](https://github.com/no-nothing/gulp/blob/master/README/catalogue.jpg)

#### 说明:
- `src/` 为开发目录
 - `embedded/` **'embedded'**项目目录
 - `pcHome/` **'pcHome'**项目目录
 - `popup/` **'popup'**项目目录
    - `css/` 压缩后输出至 *`dist/popup/img/`*
    - `fonts/` 存放字体文件，构建后会复制到 *`dist/popup/js/`*
    - `img/` 压缩后输出至 *`dist/popup/img/`*
    - `js/` 压缩后输出至 *`dist/popup/js/`*
    - `less/` 处理后输出至 *`src/popup/js/`*
    - `lib/` 存放第三方库，构建后会复制到 *`dist/popup/js/`*
    - `index.html`
- `dist/` 最后输出目录（开发阶段不用管它）
- `rev/` 静态文件版本管理对照表存放目录（gulp脚本生成，可以不用管它）

#### 自定义目录:
1. 开发目录默认为`src`,由`gulpfile.js`内的`DEVELOPMENT_PATH`变量定义；
2. 必须给定项目目录，请修改`gulpfile.js`内的`PROJECT_NAME`变量；
3. 不推荐自定义其他目录，否则要修改`gulpfile.js`内的`G_PATH`变量；

---
## gulp命令
> `shell`下切换到工作目录（`gulpfile.js`存放目录），执行如下命令

1. `gulp sprite`：合成雪碧图
2. `gulp watch:less`：实时编译LESS
3. `gulp watch:sass`：实时编译SASS
4. `gulp watch:browser`：开发构建，等同 `npm run dev`
5. `gulp build`：生产构建，等同 `npm run build`

---
## 其他:
1. `gulpfile.js`内有详细注释。
2. 已修复无法压缩`jpg jpeg`图片的BUG。
 - 阅读`gulp-imagemin`源码后发现这个插件只能传入`plugins`(Array Object)，不可传入`options`(Original Object)。

---
## 参考资料：
- [x] [gulp详细入门教程](http://www.ydcss.com/archives/18) 
- [x] [gulp系列教程](https://gold.xitu.io/entry/568f915700b0bca0ca22768e)
- [x] [npm官网(这里有插件的详细介绍)](https://www.npmjs.com/)
- [x] [gulp-rename插件](https://segmentfault.com/q/1010000006872625)
