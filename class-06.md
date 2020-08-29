# NODE.JS

[Home](https://sayefdeen.github.io/reading-notes301/).

## What is Node.js?

There are plenty of definitions to be found online:

- Node.js is a javaScript runtime built on Chrome's V8 JavaScript engine.

- Node.js is an event-based, non-blocking, asynchronous I/O runtime that uses Google's V8 JavaScript engine and libuv library.

**The V8 engine** is the open-source javaScript engine that runs in Google Chrome and other Chromium-based web browsers, including Brave, Opera, and Vivaldi. it was desgined with performance in mind and is responsible for compiling JavaScript directly to native machine code that your computer can execute.

This means that Node.js is a programe we can use to execute JavaScript on our computers, In other words, It's a JavaScript runtime.

## Installing a Package Locally.

Create your project folder then type this in your terminal in the same path of your folder

        npm init -y

This will create and auto-populate a package.json file in the same folder, Next use npm to install the [lodash package](https://www.npmjs.com/package/lodash) and save it as project dependency

        npm install lidash --save

create a file named `test.js` and add the following:

```javascript
const _ = reqire('lodash');

const arr = [0, 1, false, 2, ' ', 3];
console.log(_.compact(arr));
```

Finally run the script using node test.js You should see [1,2,3] output to the terminal.

If you look at the content ot the directory, you'll notice a folder entitled `node_modules`. This is where npm has saved loadsh and any libraries that loadsh depends on, The `node_modules` folder shouldn't be cheacked in to version control, and can, in fact, be re-created at any time by running npm install from within the project’s root.

If you open the `package.json` file, you’ll see lodash listed under the `dependencies` field. By specifying your project’s dependencies in this way, you allow any developer anywhere to clone your project and use npm to install whatever packages it needs to run.

## What is Node.js Used For?

Installing (via npm) and running (via Node) various build tools — designed to automate the process of developing a modern JavaScript application.
