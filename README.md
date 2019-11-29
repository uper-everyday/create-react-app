~~~~
1.react-scripts是create-react-app生成项目所有的依赖
~~~~
#####从react，es6，babel,webpack编辑到打包，react-scripts都做了。
~~~~
**通过npm run 执行下面命令实际上是运行 node_modules/react-srcipt/script下对应的脚本文件；**
**npm run eject : 将隐藏的配置导出；需要知道的是create-react-app脚手架本质上是使用react-scripts进行配置项目，所有配置文件信息都被隐藏起来(node_modules/react-scripts)；当需要手动修改扩展webpack配置时有时就需要将隐藏的配置暴露出来；特别需要注意的是该操作是一个单向操作，一旦使用eject，那么就不能恢复了(再次将配置隐藏)；**

**npm run build : 项目打包，在生产环境中编译代码，并放在build目录中；所有代码将被正确打包，并进行优化、压缩同时使用hash重命名文件；执行该命令前需要在package.json中新增条配置"homepage": "."（上面配置文件已给出）, 同时build后的项目需要在服务器下才能访问；否则打开的将是空白页面；**

public: 公共目录，该目录下的文件都不会被webpack进行加载、解析、打包；通过npm run         build进行打包时该项目下的所有文件将会直接被复制到build目录下
favicon.ico : 是网站图标[可替换删除]
index.html: 页面模板，webpack打包后将输出文件引入到该模板内；补充：index.html中通过环境变量%PUBLIC_URL% 来指向public目录路径；
manifest.json: PWA将应用添加至桌面的功能的实现依赖于 manifest.json 。通过manifest.json 文件可以对图标、名称等信息进行配置。
 ~~~~ 
 ~~~~  
 registerServiceWorker.js: service worker 是在后台运行的一个线程，可以用来处理离线缓存、消息推送、后台自动更新等任务；registerServiceWorker就是为react项目注册了一个service worker，用来做资源的缓存，这样你下次访问时，就可以更快的获取资源。而且因为资源被缓存，所以即使在离线的情况下也可以访问应用（此时使用的资源是之前缓存的资源）。注意，registerServiceWorker注册的service worker 只在生产环境中生效，并且该功能只有在https下才能有效果；
 ~~~~
 `
   npm install babel-plugin-transform-decorators-legacy插件
   Package.json里babel加上plugins配置 "plugins":["transform-decorators-legacy"]
   
     "babel": {
       "presets": [
         "react-app"
       ],
       "plugins":["transform-decorators-legacy"]   
     },
   上面的步骤都完成了话就可以用@connect注解的方法来优化`
