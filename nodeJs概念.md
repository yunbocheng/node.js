# Node.js
##  1. Node.js 概念

### 1.1 Node.js是什么

- Node.js不是一门语言。
- Node.js不是一个库、不是框架。
- Node.js是一个JavaScript运行时环境。
- 简单点来讲就是 Node.js 可以解析和执行JavaScript代码。
- 以前只有浏览器可以解析和执行JavaScript代码。
- 也就是说：现在的JavaScript完全脱离浏览器来运行，一切都归公于Node.js
- Node.js是单线程的。其他的都是多线程的。
- Node.js是一个能够在服务端运行JavaScript的开源代码、跨平台JavaScript运行环境。
- Node.js偶数版是开发板，奇数版是测试版

### 1.2 浏览器中的JavaScript

- EcmaScript（基础语法、if、var、function、Object、Array）
- DOM
- BOM

### 1.3 Node.js中的JavaScript

- 没有DOM、BOM对象，因为在服务端 不处理业务。
- 存在 EcmaScript。
- 在Node这个JavaScript执行环境中为 JavaScript提供了一些服务器级别的操作 API
  - 文件读写。
  - 网络服务的构建
  - 网络通信
  - http服务器

### 1.4 Node.js中Script与浏览器中的Script的区别

- 在Node.js中不存在DOM、BOM对象，只是存在EcmaScript基础语法。所以不存在getElemetById等方法。Node.js中使用的基本语法和JavaScript中的语法是一样的。只是在原有语法的基础之上增加了一些服务器级别的操作API。

### 1.5 Node.js的特性

- event-driven : 事件驱动
- non-blocking I/O model ：非阻塞IO模型(异步)
- lightweight and efficient : 轻量和高效

**JavaScript引擎是一个专门处理JavaScript脚本的虚拟机，一般会附带在网页浏览器之中。**

## 2.NPM概念

- NPM(Node Package Manager) 。
- CommonJS包规范是理论，NPM是其中一种实践。NPM就相当于是一个包管理器。
- 包里面存在的都是模块，一个模块就是一个JS文件。
- 对于Node而言，NPM帮助其完成了第三方模块的发布、安装和依赖等。借助NPM，Node与第三方模块之间形成了一个生态系统。
- NPM不是我们自己安装，NPM是我们安装Node.js时候送的。

### 2.1 NPM的基本命令

- **npm -v** : 查看当前NPM的版本。
- **npm version** :  查看当前node.js中所有依赖的版本。
- **npm -l ** : 查看npm的配置。
- **npm config list -l** : 查看npm命令列表。

- **npm init ** : 初始化一个 package.json。在我们从网上下载安装npm包的时候，他会下载到执行下载命令的路径下，把下载之后的包存储到这个当前目录的文件夹下。但是，在下载的时候，他会查看当前目录下是否存在 package.json 这个文件，如果不存在，他会报错，并且将下载的包下载到别的路径下。所以我们需要先使用 **npm init**命令来创建一个package.json文件。需要注意的是：创建这个包不是必须的，有的使用不创建也不会报错，建议还是提前创建一个。
- **npm init -y** : 使用 npm init -y 或者 npm init -f 可以跳过提问阶段，直接生成一个新的package.json文件。
- **npm search 包名** ： 用于搜索npm库中的包。可以跟字符串，也可以跟正则表达式。(需要连接网络)

![image-20211218103655136](https://gitee.com/YunboCheng/imageBad/raw/master/image/image-20211218103655136.png)

下载之后可以看到包的名字、描述、作者、日期、版本、

- **npm info ** ： 查看每个模块的具体信息。比如：查看underscore模块的信息。

  ```shell
  $ npm info underscore
  ```

   使用上面的命令返回的是一个JavaScript对象，包含了underscore模块的详细信息。这个对象中的每个成员，都可以直接从info命令查询。

  ```shell
  $ npm info underscore description
  $ npm info underscore homepage
  $ npm info underscore version
  ```

- **npm list** : 以树型的结构列出当前项目安装的所有模块以及他们的依赖项。

  ```shell
  $ npm list    
  $ npm list -global     #加上 global 参数，会列出全局安装的模块
  $ npm list underscore  #npm list 命令也可以列出单个模块
  ```

### 2.3 NPM的下载安装命令

#### 2.3.1 下载安装的基本命令

- **npm install 包名 **  ：从npm库中向该项目中安装一个包。npm在默认情况下会从npm库中搜索或下载包，将包安装到当前目录下的node_modules子目录下。如果在项目的目录下没有node_modules这个目录，那么npm会自动帮我们创建一个并将下载的这个npm包存储到这个目录下。
- **npm i(小写) 包名** ： 他是以上命令的简写形式。install 可以简写为 i。

#### 2.3.2 全局安装与本地安装

**包的安装存在两种形式，本地模式和全局模式。**

- **本地模式：** 就是将从npm中下载的包存储到该项目的 node_modules 目录下，此时这个包只能供这个项目使用。

- **全局模式** ： 使用全局安装的模式，可以将这个包存储到全局中，此时所有的项目都可以使用这个包。全局安装的包一般都是一些工具。都不是在项目中用的，一般是在计算机系统中使用的(编译CSS文件、JS文件、给项目打包等)
- **本地安装  npm install 包名**
- **全局安装  npm install 包名 -g**



#### 2.3.3 **安装指定版本的npm包**

- install命令总是安装模块的最新版本，如果要安装模块的特定版本，可以在模块名后面加上@和版本号。(这个版本号是npm库中存在的。)

```shell
$ npm install 包名@latest
$ npm install 包名@0.1.1
$ npm install 包名@">=0.1.0 <0.2.0"
```

注意：安装下载的版本号的包必须是npm库中存在的。不存在会提示下载失败并报错。

#### 2.3.4 使用不用的参数指定模块属于哪个依赖



#### 2.3.4.1**项目的package.json中存在不同的属性存储下载的npm包。**

**在实际的开发中，我们不会把node_modules目录上传到我们的项目中。这样会降低我们上传和下载的速度，不方便用书使用和我们自己维护。而是会把这项目所需要依赖的npm包名称以及版本存储到 packag.json 中的dependencies属性中，当用户使用我们的这个包的时候，npm会自动的去检测 packag.json 中的dependencies属性中的依赖包，自动从npm库中下载对用的npm包。**



- **dependencies生产依赖** : 这个可以说是我们npm核心的一项内容，称之为 **依赖管理**。这个对象里面的内容就是我们这个项目所依赖的其他的js模块包。下面这段代码表示我们依赖了markdown-it这个包，版本是^8.1.0，代表最小依赖版本是8.1.0，如果这个包有更新，那么当我们使用npm install命令的时候，npm会帮我们下载最新的包。当别人引用我们这个包的时候，包内的依赖包也会被下载下来。

```shell
"dependencies":{"markdown-it":"^8.1.0"}
```

- **devDependencies开发依赖** ：在我们开发的时候会用到的一些包，只是在开发环境中需要用到，但是在别人引用我们包的时候，不会用到这些内容，放在devDependencies的包，在别人引用的时候不会被npm下载。

**总结：存储到dependencies性质中的包在其他用户下载这个项目的时候会自动下载。存储到devDependencies性质中的包只是提供开发者在开发的时候使用，不会在用户下载这个项目的时候一起下载。**



#### 2.3.4.2 将npm存储到不同的依赖属性中

install命令可以使用不同参数，指定所安装的模块属于哪一种性质的依赖关系。即出现在package.json文件中的哪一项中。

- **-save : 依赖模块被添加到  dependencies，可以简化为参数 -S(大写)。**
- **-save-dev : 模块名将被添加到 devDependencies，可以简化为参数-D(大写)。**

```shell
$ npm install 包名 --save
$ npm install 包名 --save-dev
#或者
$ npm install 包名 -S
$ npm install 包名 -D

```



当你有了一个完整的package.json文件的时候，就可以让人一眼看出来，这个模块的基本信息，和这个模块所需要依赖的包。我们可以通过npm install就可以很方便的下载好这个模块所需要的包。

```json
	"devDependencies":{
	"autoprefixer":"^6.4.0",
	"babel-preset-es2015":"^6.0.0",
	"babel-preset-stage-2":"^6.0.0",
	"babel-register":"^6.0.0",
	"webpack":"^1.13.2",
	"webpack-dev-middleware":"^1.8.3",
	"webpack-hot-middleware":"^2.12.2",
	"webpack-merge":"^0.14.1",
	"highlightjs":"^9.8.0"
}

```

- **npm install ** : 下载当前项目依赖的所有包。也就是当前项目中 package.json中dependencies属性中的依赖包。
- **npm install --production** :  install默认会安装dependencies字段和devDependencies字段中的所有模块，如果使用–production参数，可以只安装dependencies字段的模块。

```shell
$ npm install --production
#或者
$ NODE_ENV=production npm install

```

- 一旦安装了某个模块。就可以在代码中用require命令加载这个模块。

```js
var backbone = require('backbone');
console.log(backbone.VERSION)
```

### 2.4 NPM删除包命令

- **npm  remove 包名：** 删除项目中的npm包。
- **npm r(小写) 包名** ： 这个是删除指定包的简化写法。
- **npm remove 包名 --save** : 删除这个npm包的同时删除 package.json中dependenties中的依赖。

### 2.5 执行package.json中的Script脚本

- **npm run : npm不仅可以用于模块管理，还可以用于执行脚本。**package.json文件有一个scripts字段，可以用于指定脚本命令，供npm直接调用。

- **npm run是npm run-script的缩写**。一般都使用前者，但是后者可以更好的反应这个命令的本质。

- package.json文件内容：

```json
{
	"name":"myproject",
	"devDependencies":{
		"jshint":"latest",
		"browserify":"latest",
		"mocha":"latest"
		},
	"scripts":{
		"lint":"jshint **.js",
		"test":"mocha test/"
		}
}
```

- **scripts 脚本** ： 顾名思义，就是一些脚本代码。可以通过**npm run script-key**来调用。
  例如在这个package.json的文件夹下使用 **npm run dev** 就相当于运行了node build/dev-server.js这一段代码。

```json
//脚本
"scripts":{
	"dev":"node build/dev-server.js",
	"build":"node build/build.js",
	"docs":"node build/docs.js",
	"build-docs":"npm run docs & git checkout gh-pages & xcopy /sy dist\\* . & 					git add . & git commit -m 'auto-pages' & git push & git 					checkout master",
	"build-publish":"rmdir /S /Q lib & npm run build &git add . & git commit -						m auto-build & npm version patch & npm publish & git 						push",
    "lint":"eslint --ext .js,.vue src"
	}
```

使用scripts的目的就是为了把一些要执行的代码合并到一起，使用 npm run 来快速的运行，方便省事。

**npm run如果不加任何参数，直接运行，会列出package.json里面所有可以执行的脚本命令。**

##  3. 安装包

- 包是在模块基础上更深一步的抽象，Node的包类似于C/C++的函数库或者Java、.Net的类库。**它将某个独立的功能封装起来，用于发布、更新、依赖管理和版本控制。**
- Node根据CommonJS规范实现了包机制，开发了npm来解决包的发布和获取需求。
- Node的包是一个目录，其中包含了一个JSON格式的包说明文件package.json。

**严格符合CommonJS规范的包应该具备以下特征**

1. package.json必须在包的顶层目录下；
2. 二进制文件应该在bin目录下；
3. JavaScript代码应该在lib目录下；
4. 文档应该在doc目录下；
5. 单元测试应该在test目录下;

Node对包的要求并没有这么严格，只要顶层目录下有package.json，并符合一些规范即可。当然为了提高兼容性，我们还是建议你在制作包的时候，严格遵守CommonJS规范

我们也可以把文件夹封装为一个模块，即所谓的包。包通常是一些模块的集合，在模块的基础上提供了更高层的抽象，相当于提供了一些固定接口的函数库。通过定制package.json，我们可以创建更复杂，更完善，更符合规范的包用于发布。

Node在调用某个包时，会首先检查包中packgage.json文件的main字段，将其作为包的接口模块，如果package.json或main字段不存在，会尝试寻找 index.js 或 index.node 作为包的接口。

**package.json中的一些属性：**

1. package.json是CommonJS规定的用来描述包的文件，完全符合规范的package.json文件应该含有以下字段： **name: 包的名字，必须是唯一的，由小写英文字母、数字和下划线组成，不能包含空格。**
2. description: 包的简要说明。
3. version: 符合语义化版本识别规范的版本字符串。
4. keywords: 关键字数组，通常用于搜索。
5. maintainers: 维护者数组，每个元素要包含name、email(可选)、web(可选)字段。
6. contributors: 贡献者数组，格式与maintainers相同。包的作者应该是贡献者数组的第一个元素。
7. bugs: 提交bug的地址，可以是网址或者电子邮件地址。
8. licenses: 许可证数组，每个元素要包含type（许可证的名称）和 url（链接到许可证文本的地址）字段。
9. repositories: 仓库托管地址数组，每个元素要包含type（仓库的类型，如 git）、URL（仓库的地址）和 path（相对于仓库的路径，可选）字段。
10. dependencies: 包的依赖，一个关联数组，由包名称和版本号组成。

## 4.包的发布

1. 通过使用npm init可以根据交互式回答产生一个符合标准的package.json。创建一个index.js作为包的接口,一个简单的包就制作完成了。

2. 在发布前,我们还需要获得一个账号用于今后维护自己的包,使用**npm adduser**根据提示完成账号的创建 完成后可以使用**npm whoami**检测是否已经取得了账号。也可以在浏览器的npm官网上自己注册一个，然后使用 **npm login** 登录一下自己的账号。之后在使用 **npm publish**就可以直接发布了。

3. 接下来,在package.json所在目录下运行npm publish，稍等片刻就可以完成发布了。

4. 打开浏览器，访问NPM搜索就可以找到自己刚刚发布的包了。

5. 现在我们可以在世界的任意一台计算机上使用**npm install 自己发布的包名**命令来安装它。

6. 如果你的包将来有更新,只需要在package.json文件中修改version字段,然后重新使用npm publish命令就行了。

7. 如果你对已发布的包不满意，可以使用**npm unpublish 包名** 命令来取消发布。

   注意：如果存在多个 hello_npm的版本，可以指定对应的版本进行取消发布。

   ```shell
   npm unpublish  hello_npm2@1.0.0
   ```

**在npm网站上，不同名称的项目只能存在一个。也就是说packag.json中的name属性值是唯一的。并且只能由小写字母、数字、下划线组成。**

**在我们编写这个项目配置的时候使用的数组的形式传递数据。当我们定义的这些配置都传递到了项目中，都会变成一个json格式的数据。这些dependencies属性的值都是以对象的形式存在的。**
