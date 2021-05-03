# try_node-pdf

## nodenv で node リスト最新化

```bash
$ git -C "$(nodenv root)"/plugins/node-build pull
...
 create mode 100644 share/node-build/10.24.1
 create mode 100644 share/node-build/12.22.1
 create mode 100644 share/node-build/14.16.1
 create mode 100644 share/node-build/15.14.0
$ nodenv install --list |grep ^14.16
14.16.0
$ nodenv versions
* 12.16.1 (set by /home/***/.anyenv/envs/nodenv/version)
  14.15.4
  14.15.5
  14.16.0
$ nodenv install 14.16.1
$
```

## node ローカルインストール

```bash
$ nodenv local 14.16.1
$ node -v
v14.16.1
$ npm -v
6.14.12
```

## webpack 導入（フロントエンド用）

- [最新版で学ぶwebpack 5入門 JavaScriptのモジュールバンドラ](https://ics.media/entry/12140/)
- [webpack の基本的な使い方](https://www.webdesignleaves.com/pr/jquery/webpack_basic_01.html)

```bash
$ npm init -y
$ npm i -D webpack webpack-cli
$ cp -p package.json package.json.org
$ vi package.json
$ diff package.json package.json.org
7d6
<     "build": "webpack",
$ npm run build
```

## フロントエンドを Typescript 化

- [最新版TypeScript+webpack 5の環境構築まとめ](https://ics.media/entry/16329/)

```bash
$ npm i -D ts-loader
$ npx tsc --init --rootDir src-wp --outDir docs --esModuleInterop --resolveJsonModule --lib es2019,dom --module commonjs
```
