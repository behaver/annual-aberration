# AnnualAberration

[![GitHub license](https://img.shields.io/badge/license-MIT-brightgreen.svg)](#) [![npm version](https://img.shields.io/npm/v/react.svg?style=flat)](https://www.npmjs.com/package/@behaver/annual-aberration) [![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](#)

## 简介

AnnualAberration 是一个用于计算天体周年光行差的组件。

本组件计算支持的坐标系统有：赤道坐标和黄道坐标，计算结果的历元标准为 J2000 历元，单位为：弧度。

## 安装

通过 npm 安装，在你的 node 项目目录下执行：

`npm i --save @behaver/annual-aberration`

安装完成后，调用即可：

`const AnnualAberration = require('@behaver/annual-aberration');`

## 用例

```js
const AnnualAberration = require('@behaver/annual-aberration');
const { JDateRepository } = require("@behaver/jdate");
const { SphericalCoordinate3D } = require('@behaver/coordinate');

let AA = new AnnualAberration({
  time: new JDateRepository(18, 'j2000'),
  sc: new SphericalCoordinate3D(1, 1.123, 1.55),
  system: 'ecliptic',
});

let res = AA.get();
```

## API

`constructor(options)`

构造函数:

* options.time   计算时间
* options.sc     天体球坐标
* options.system 坐标系统

`get()`

获取周年光行差

`get time()`

获取计算时间

`set time(time)`

设置计算时间

## 许可证书

The MIT license.