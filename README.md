## signature_pad_wechat

signature_pad support wechat miniprogram

This is a rewrite of original signature_pad, starting and borrowing from [this fork](https://github.com/szimek/signature_pad).

## Installation

```bash
# with npm
npm install signature_pad_wechat -S
# with yarn
yarn add signature_pad_wechat -S
```

## Usage

```typescript
import { SignaturePad, SignaturePadWechat } from 'signature_pad_wechat';

// 在微信小程序中使用
wx.createSelectorQuery()
  .select(`#canvas`)
  .fields({
    node: true,
    size: true,
  })
  .exec((res: any[]) => {
    const { width, height } = res[0];

    const canvas: WechatMiniprogram.Canvas = res[0].node;

    const signaturePad = new SignaturePadWechat(canvas, {
      minWidth: 2,
      maxWidth: 5,
      penColor: 'rgb(0, 0, 0)',
    });
  });

// 正常网页使用
const canvas = document.querySelector('canvas');

const signaturePad = new SignaturePad(canvas, {
  minWidth: 2,
  maxWidth: 5,
  penColor: 'rgb(0, 0, 0)',
});
```

选项参数与 [signature_pad](https://www.npmjs.com/package/signature_pad) 一致
