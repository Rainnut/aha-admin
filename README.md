# sass

* 解析sass文件生成css
  * yarn add sass -D
  * cd node_modules/.bin
  * sass sass/main.scss css/style.css

# npm script

* 通过script简写上述命令，自动在.bin中执行，不需要进入.bin目录
* 可以使用script的前置钩子pre和后置钩子post

# yarn build

* sass sass/main.scss css/style.css --watch
  * 监听scss文件变化，触发编译成css

# yarn serve

* browser-sync .
  * 将当前目录作为服务器启动

# yarn start

* yarn add npm-run-all -D
  1、简化。官方npm run-script命令不能运行多个脚本，因此如果我们要运行多个脚本，则有点多余。让我们通过类似球形的样式来缩短它。
  之前：npm run clean && npm run build:css && npm run build:js && npm run build:html
  之后：npm-run-all clean build:*

  2、跨平台。有时我们&可以并行运行多个命令，但是cmd.exe（npm run-script默认情况下使用）不支持&。一半的Node.js用户在Windows上使用它，因此使用&may可能会阻止贡献。npm-run-all --parallel在Windows上也能很好地工作。
* run-p build serve
  * 直接使用run-script的话，因为sass --watch监听文件变化，会导致serve无法启动
  * run-p并行执行；run-s顺序执行
  * & 并行执行；&& 顺序执行。
