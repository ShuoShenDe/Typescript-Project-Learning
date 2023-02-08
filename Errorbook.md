# yarn install

### Syntax Error: Unexpected identifier

`git lfs pull --include .yarn/`
`corepack enable`

### Error: ENOSPC: System limit for number of file watchers reached, watch '/home/badis/Desktop/react-native/albums/node_modules/.staging'

The meaning of this error is that the number of files monitored by the system has reached the limit!!
Result: The command executed failed! Or throw a warning (such as executing a react-native start VSCode)
Solution:
Modify the number of system monitoring files on Ubuntu
`sudo gedit /etc/sysctl.conf`

Add a line at the bottom
`fs.inotify.max_user_watches=524288`

Then save and exit!
`sudo sysctl -p`

# Run project
node_modules/@types/react/index"' has no default export
That happens because babel (the one that you were using before) assumes modules.export as default export while typescript (the one that you are using now) does not.

You can use this syntax by simply adding "allowSyntheticDefaultImports": true and "esModuleInterop":true to your tsconfig.json

{
  ...
  "compilerOptions": {
    "allowSyntheticDefaultImports": true,
    "esModuleInterop": true,
  },
  ...
}

# NetwrokError

![image](https://user-images.githubusercontent.com/31400000/216576194-c230f757-4b69-4416-af8c-c654d0db29df.png)

# Project info

- `yarn`: Facebook、Google、Exponent 和 Tilde 联合推出了一个新的 JS 包管理工具
- `yarn.lock`: 安装版本统一：为了防止拉取到不同的版本 =`package-lock.json`
- `tsc`: 的全称是 TypeScript Compiler，也就是将 TypeScript 转码为 JavaScript 代码的编译器。
- `tsconfig.json`： 文件是用于描述将 TypeScript 转为 JavaScript 代码的配置文件。
- `babel.config.json`: 编译工具，例如typescript不对path进行编译，需要babel帮助
- > Babel is a toolchain that is mainly used to convert ECMAScript 2015+ code into a backwards compatible version of JavaScript in current and older browsers or environments. Here are the main things Babel can do for you:
  > Transform syntax Polyfill features that are missing in your target environment (through a third-party polyfill such as core-js)
  > Source code transformations (codemods). It is useful if you have multiple packages (ie multiple package.json) directories in your project that utilize a single babel config
- `.vscode/launch.json`:
- `jest`: Jest is a delightful JavaScript Testing Framework with a focus on simplicity.
- `package.json`: "dependencies": Packages required by your application in production.
                "devDependencies": Packages that are only needed for local development and testing.
                --save-prod flag for dependencies (the default behavior of npm install) or the --save-dev flag for devDependencies.
- `webpack`:
  > [Webpack](https://webpack.js.org/guides/getting-started/#basic-setup) is used to compile JavaScript modules. Once installed, you can interact with webpack either from its CLI or API.
  > We also need to adjust our package.json file in order to make sure we mark our package as private, as well as removing the main entry. This is to prevent an accidental publish of your code. Works for the package.json scripts.
  > Run `npx webpack`, which will take script at src/index.js as the entry point, and will generate dist/main.js as the output.
- `eslintrc`:
  > ESLint is a configurable JavaScript linter. It helps you find and fix problems in your JavaScript code. Problems can be anything from potential runtime bugs, to not following best practices, to styling issues. The ESLint CLI is a command line interface that lets you execute linting from the terminal. The CLI has a variety of options that you can pass to its commands.
  > The ESLint Node.js API lets you use ESLint programmatically from Node.js code. The API is useful when developing plugins, integrations, and other tools related to [ESLint](https://eslint.org/docs/latest/user-guide/getting-started).
- `mcap`: MCAP is a modular container format and logging library for pub/sub messages with arbitrary message serialization. can transfer bag to mcap. Import in the tsc.
- `prettierrc`: Prettier is an opinionated code formatter with support for Typicscript. Formatting from the command line or from the editor, either via a keyboard shortcut or automatically whenever you save a file.

- `React`: A JavaScript library for building user interfaces. [React](https://reactjs.org/) used in code.

- `Node.js`：在[调试](https://blog.csdn.net/Taobaojishu/article/details/125437831)模式下提供了两种 flag 选项，一个是 --inspect , 另一个则是 --inspect-brk ，两者都可以让 Node.js 程序以调试模式启动，唯一区别即是 --inspect-brk 会在调试器未被 attach 前阻塞 Node.js 脚本的执行，这个特性在老版本的 Node Debug 插件中被广泛使用，用于保障在调试执行前设置断点等。而在 JavaScript Debugger 中，采用了一个全新的脚本运行模式，让 Node.js 的调试可以不再依赖 --inspect-brk , 其原理即是向在 JavaScript Debug Terminal 中运行的脚本注入 NODE_OPTIONS 选项。

# Supplementary knowledge

- [JavaScript 中的 CJS,AMD,UMD 和 ESM 是什么
  ](https://www.imyangyong.com/blog/2020/11/javascript/JavaScript%20%E4%B8%AD%E7%9A%84CJS,AMD,UMD%E5%92%8CESM%E6%98%AF%E4%BB%80%E4%B9%88/#:~:text=ESM%E6%98%AF%E6%9C%80%E5%A5%BD%E7%9A%84,%E5%90%8C%E6%AD%A5%E7%9A%84%EF%BC%8C%E5%90%8E%E7%AB%AF%E9%80%82%E7%94%A8%E3%80%82)

  > ESM 是最好的模块格式，这得益于它简单的语法、异步特性和支持 tree-shaking。\
  > UMD 在任何地方都能运行，通常用作在 ESM 不能运行的情况下的后备方案。\
  > CJS 是同步的，后端适用。\
  > AMD 是异步的，前端适用

- [npm 、cnpm、 yarn 、 pnpm 主要区别](https://wuxinhua.com/posts/Node-js-Package-Manager-And-Npm-Dependency-Installation-Mechanism/)
  > npm 是 Node Package Manager 的简称 \
  > cnpm 完整的 npmjs 镜像 \
  > Yarn 是一个快速可靠安全的依赖管理工具，由 Facebook 联合其它几个互联网公司主导的一个开源项目 锁版本 \
  > pnpm 快和节省磁盘空间
