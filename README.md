# vue-img-proxy

<!-- [![Version](http://img.shields.io/npm/v/vue-img-proxy.svg)](https://www.npmjs.com/package/vue-img-proxy)[![Downloads](http://img.shields.io/npm/dm/vue-img-proxy.svg)](https://www.npmjs.com/package/vue-img-proxy) -->

> 这是一个Vue2.x的图片代理组件，当你的页面有图片显示时，发送http请求图片url时必须等待服务器返回才可，使用该组件可图片未加载完成前先显示一张默认图片，图片加载完成后再替换掉默认图片，如果图片加载失败则替换为加载失败的图片

---

**Install**

`npm install vue-img-proxy --save`

**Usage**

***install as global component***

```global
import Vue from 'vue'
import VueImgProxy from 'vue-img-proxy'

Vue.component('VueImgProxy', VueImgProxy)
```

***install as something component***

```something
import VueImgProxy from 'vue-img-proxy'

const app = new Vue({
    components: { VueImgProxy }
})
```

***template code***

```template
<vue-img-proxy :src="img" :title="title" @loaded=""></vue-img-proxy>
```

---

### API

**Attributes**

| property name     | description                              | type    | default value |
| :---------------- | :--------------------------------------- | :------ | :------------ |
| src               | image url                                | String  | null            |
| title             | will replace image title alt attr        | String  | ''         |

**methods**

| property name     | description                              | type     | default value |
| :---------------- | :--------------------------------------- | :------  | :------------ |
| loaded            | image load finished emit                 | function | null          |
