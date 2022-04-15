# `dylan-rem`
[![GitHub license](https://img.shields.io/badge/license-MIT-blue.svg)](https://github.com/51wangping/electron-react-template) [![npm version](https://img.shields.io/npm/v/api-switchboard.svg?style=flat)](https://www.npmjs.com/package/dylan-rem) [![Issues](https://img.shields.io/github/issues/julienandreu/switchboard)](https://github.com/51wangping/create-dylan-project/issues) [![NPM Downloads](https://img.shields.io/npm/dm/api-switchboard.svg?style=flat)](https://npmcharts.com/compare/dylan-rem?minimal=true) [![install size](https://packagephobia.com/badge?p=dylan-rem)](https://packagephobia.com/result?p=dylan-rem)


> 这是专为移动端开发设计监听 window resize 改变自动设置 html 的 fontsize 大小。配置插件 postcss 进行将 px 转为 rem 的移动端开发工具库

## Usage

### 安装

```
npm install dylan-rem
```

在项目入库文件中引入 dylan-rem 并初始化
```
import  dylanRem  from 'dylan-rem';

dylanRem.init({
  designWidth: 375,   // 设计稿宽度
  rootValue: 37.5,    // html基础fontSize大小
  maxRatio: 2         // 运行缩放最大比例
});
```

配合 postcss 插件进行 css 单位转换，[请参阅](https://postcss.org/)


```
# 安装
npm install postcss-pxtorem autoprefixer -S


# postcss.config.js
module.exports = {
    plugins: {
        autoprefixer: require('autoprefixer'),
        'postcss-pxtorem': {
            rootValue: 37.5,      // 设计稿宽度 375
            propList: ['*']
        }
    }
}
```

## API

### init 

初始化页面配置

类型

```
init(config: { rootValue?: number; designWidth?: number; maxRatio?: number }): void;
```
参数

参数 | 类型
---|---
option | Option

Option

参数 | 类型 | 必填 | 默认值 | 说明
---|---|---|---|---
designWidth | number | 否 | 375  | 设计稿宽度
rootValue   | number | 否 | 37.5 | 根字体大小
maxRatio    | number | 否 |  2   | 最大缩放比例

### px2Rem
px转换位rem

类型
```

px2Rem(px: string | number, addUnit?: boolean): number | string;
```

参数

参数 | 类型 | 必填 | 默认值 | 说明
---|---|---|---|---
px | string / number | 是 | | 需要转换的px数值
addUnit | boolean | 否 | false | 是否添加单位


### rem2Px

rem转换为px


类型

```
rem2Px(rem: string | number, addUnit?: boolean): number | string;

```

参数

参数 | 类型 | 必填 | 默认值 | 说明
---|---|---|---|---
rem | string / number | 是 | | 需要转换的rem
addUnit | boolean | 否 | false | 是否添加单位

