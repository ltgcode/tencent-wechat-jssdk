# 项目说明
源码来源：tencent-wx-jssdk
作者：taoqf

URL：[tencent-wx-jssdk](https://www.npmjs.com/package/tencent-wx-jssdk)

本项目添加了自己需要用的小程序的接口的描述，因不熟悉TS，不确定是否有BUG。

# 微信SDK地址
Weixin [JS-SDK](https://mp.weixin.qq.com/wiki?t=resource/res_main&amp;id=mp1421141115)

## SDK Version

1.6.0

## Install

```sh
npm install ltg-wxsdk --save
```

## How to Use

### TypeScript

```ts
// sometime you want import this module, eg. use this with webpack
import { scanQRCode } from 'ltg-wxsdk';

scanQRCode({
	needResult: 0,
	scanType: ['qrCode'],
	success(res) {
		console.log(res);
	}
});
```

or, you could add this module in your tsconfig.json

```json
{
	"compilerOptions": {
		"types": [
			"ltg-wxsdk"
		]
	}
}
```

then use it freely.

```ts

jWeixin.scanQRCode({
	needResult: 0,
	scanType: ['qrCode'],
	success(res) {
		console.log(res);
	}
});

// sometimes you must use WeixinJSBridge, like wexin paying
WeixinJSBridge.invoke("getBrandWCPayRequest", {}, (res) => {
});
```

### javascript

**You will need this only if you would like get your project packed.**

```js
const wx = require('ltg-wxsdk');
wx.scanQRCode({
	needResult: 0,
	scanType: ['qrCode'],
	success(res) {
		console.log(res);
	}
});
```

## Others

### ts Error

If you get this Error:
`[ts] Initializers are not allowed in ambient contexts.`

Try add `"skipLibCheck": true` to `compilerOptions` in file `tsconfig.json`.

Good luck!
