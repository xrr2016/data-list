# Data-list

[![](https://img.shields.io/npm/dm/@femessage/data-list.svg#align=left&display=inline&height=20&originHeight=20&originWidth=140&status=done&width=140)](https://www.npmjs.com/package/@femessage/data-list)
[![](https://img.shields.io/npm/v/@femessage/data-list.svg#align=left&display=inline&height=20&originHeight=20&originWidth=80&status=done&width=80)](https://www.npmjs.com/package/@femessage/data-list)
![](https://img.shields.io/npm/l/@femessage/data-list.svg#align=left&display=inline&height=20&originHeight=20&originWidth=78&status=done&width=78)
[![](https://img.shields.io/badge/PRs-welcome-brightgreen.svg#align=left&display=inline&height=20&originHeight=20&originWidth=90&status=done&width=90)](https://github.com/FEMessage/data-list/pulls)

More easy to use scrolling to load more list components<br />![](https://cdn.nlark.com/yuque/0/2019/gif/224563/1561712793658-9351ad70-4b43-4115-bc31-bf507781759c.gif#align=left&display=inline&height=560&originHeight=560&originWidth=320&size=0&status=done&width=320)

<a name="65f5152b"></a>

## Table of Contents

* [Introduction](https://www.yuque.com/deepexi-serverless/onx52o/dgfllg?translate=en#Introduction)
* [Feature](https://www.yuque.com/deepexi-serverless/onx52o/dgfllg?translate=en#Feature)
* [Demo](https://www.yuque.com/deepexi-serverless/onx52o/dgfllg?translate=en#Demo)
* [Pre Install](https://www.yuque.com/deepexi-serverless/onx52o/dgfllg?translate=en#Pre-Install)
* [Quick start](https://www.yuque.com/deepexi-serverless/onx52o/dgfllg?translate=en#Quick-start)
* [Example](https://www.yuque.com/deepexi-serverless/onx52o/dgfllg?translate=en#Example)
  * [Basic](https://www.yuque.com/deepexi-serverless/onx52o/dgfllg?translate=en#basic)
  * [Slot content](https://www.yuque.com/deepexi-serverless/onx52o/dgfllg?translate=en#slot-content)
  * [Reset](https://www.yuque.com/deepexi-serverless/onx52o/dgfllg?translate=en#reset)
* [License](https://www.yuque.com/deepexi-serverless/onx52o/dgfllg?translate=en#License)
* [Contributors](https://www.yuque.com/deepexi-serverless/onx52o/dgfllg?translate=en#Contributors)

<a name="Introduction"></a>

## Introduction

**What is `data-list`**<br />`data-list` Components are based [V-infinite-loading](https://peachscript.github.io/vue-infinite-loading/) Packaged list rendering component. Get started `data-list` The component is relatively simple. you only need to configure the url and data return path to process data, which can provide unlimited scrolling, sliding and loading more data, etc.<br />**Why**<br />The daily needs to face a large number of list rendering scenes, usually the data processing logic of these lists is reusable. And `data-list` Only a simple configuration is needed to achieve:

* Incoming `url` The data will be obtained and returned
* Automatically determine the current page, whether it has reached the last page, and stop loading the data
* Prompt for scenes such as no data, no more data, request errors, etc. (customizable)
* You can save the list scrolling status, return after accessing the details page, and return to the previous scrolling position

<a name="Feature"></a>

## Feature

* Just configure `url` And `数据在接口返回的路径` Data can be obtained
* Bring your own drop-down load more, paging data processing
* Support storage request parameters, you can turn up the page to get the previous page data, get the next page data down<br />**[⬆Back to Top](https://www.yuque.com/deepexi-serverless/onx52o/dgfllg?translate=en#table-of-contents)**

<a name="Demo"></a>

## Demo

* [Online demo](https://femessage.github.io/data-list)<br />**[⬆Back to Top](https://www.yuque.com/deepexi-serverless/onx52o/dgfllg?translate=en#table-of-contents)**

<a name="5bc0fb1f"></a>

## Pre Install

Make sure you have installed it correctly `axios`

```bash
yarn add axios
```

Then register globally `axios`

```javascript
import Vue from 'vue'
import axios from 'axios'
Vue.prototype.$axios = axios
```

**[⬆Back to Top](https://www.yuque.com/deepexi-serverless/onx52o/dgfllg?translate=en#table-of-contents)**

<a name="06ad314b"></a>

## Quick start

```sh
# Step1 安装
yarn add @femessage/data-list
```

```vue
// Step2 在需要渲染列表的 .vue 文件中
<template>
  <data-list ref="dataList" :url="url">
    <ul slot-scope="props">
      <li v-for="(item, index) in props.list" :key="index">
        {{item.name}}
      </li>
    </ul>
  </data-list>
</template>
<script>
import DataList from '@femessage/data-list'
export default {
  name: 'data-list',
  components: {DataList},
  data() {
    return {
      url: 'https://easy-mock.com/mock/5c323f1b2188f1589db6af5f/data-list'
    }
  }
}
</script>
```

**[⬆Back to Top](https://www.yuque.com/deepexi-serverless/onx52o/dgfllg?translate=en#table-of-contents)**

<a name="Example"></a>

## Example

<a name="basic"></a>

### Basic

![](https://cdn.nlark.com/yuque/0/2019/gif/224563/1561712793428-d597adc3-e741-443e-9c52-65fa5ae46b89.gif#align=left&display=inline&height=560&originHeight=560&originWidth=320&size=0&status=done&width=320)<br />**[⬆Back to Top](https://www.yuque.com/deepexi-serverless/onx52o/dgfllg?translate=en#table-of-contents)**

<a name="72668cd2"></a>

### Slot content

![](https://cdn.nlark.com/yuque/0/2019/gif/224563/1561712793541-047e59ab-6487-4000-96f3-505e236e2323.gif#align=left&display=inline&height=560&originHeight=560&originWidth=320&size=0&status=done&width=320)<br />**[⬆Back to Top](https://www.yuque.com/deepexi-serverless/onx52o/dgfllg?translate=en#table-of-contents)**

<a name="reset"></a>

### Reset

![](https://cdn.nlark.com/yuque/0/2019/gif/224563/1561712793411-86387fdf-7ca9-4430-a052-19f56913787f.gif#align=left&display=inline&height=560&originHeight=560&originWidth=320&size=0&status=done&width=320)<br />**[⬆Back to Top](https://www.yuque.com/deepexi-serverless/onx52o/dgfllg?translate=en#table-of-contents)**

<a name="License"></a>

## License

[MIT](./LICENSE)<br />**[⬆ Back to Top](#table-of-contents)**

<a name="Contributors"></a>

## Contributors

Thanks goes to these wonderful people ([emoji key](https://allcontributors.org/docs/en/emoji-key)):

| [![](https://avatars2.githubusercontent.com/u/20613509?v=4#alt=listars&width=100)<br />**listars**](https://github.com/listars)<br />[💻](https://github.com/FEMessage/data-list/commits?author=listars) [🐛](https://github.com/FEMessage/data-list/issues?q=author%3Alistars) [📖](https://github.com/FEMessage/data-list/commits?author=listars) [💡](#example-listars) | [![](https://avatars3.githubusercontent.com/u/9384365?v=4#alt=levy&width=100)<br />**levy**](http://levy.work)<br />[👀](#review-levy9527) [🤔](#ideas-levy9527) | [![](https://avatars3.githubusercontent.com/u/19513289?v=4#alt=EVILLT&width=100)<br />**EVILLT**](https://evila.me)<br />[🚇](#infra-evillt) | [![](https://avatars3.githubusercontent.com/u/26338853?v=4#alt=OuZuYu&width=100)<br />**OuZuYu**](http://67.216.223.155/resume/)<br />[🐛](https://github.com/FEMessage/data-list/issues?q=author%3AOuZuYu) | [![](https://avatars3.githubusercontent.com/u/19591950?v=4#alt=Donald%20Shen&width=100)<br />**Donald Shen**](https://donaldshen.github.io/portfolio)<br />[🐛](https://github.com/FEMessage/data-list/issues?q=author%3Adonaldshen) [💬](#question-donaldshen) |
| -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |

