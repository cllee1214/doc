### 上传图片组件

1. 基本使用：


```
// html
<image-uploader v-model='formData.head' sourcecode='head' :display='currentHeadUrl'></image-uploader>


// js
import imageUploader from "@/components/Upload/imageUploader";
export default {
    currentHeadUrl: '',
    formData: {
        id: 0,
        real_name: "",
        head: 0,
        mobile: '',
        email: '',
        password: '',
        repeat_password: ''
    },
}
```

2.  组件文档：


| props       |         描述                          | 可选值 | 默认值 |类型   | require|
| ----------- | -------------------------------------|--------|--------|-------|-------|
| resourceType|      图片上传之后返回类型[^1]              | 'id', 'url'|   id   | String| 否
| display     |    组件回显图片地址                    |   -     |     -   | String|否
| sourcecode  |    文件上传场景代码                    |    -   |    -    | String|是
| drive       |    上传文件驱动                        |'local', 'obs', 'cos'| cos| String|否
| tips        |    文字提示                        |-| -| String|否
| accept      |    允许上传的图片格式                   |-| ['png', 'jpeg', 'jpg']| Array|否


[^1]: 图片上传成功之后，根据业务选择，可以返回图片的url地址或者文件id。


### 带有跳转链接的按钮组件（link-button）

1. 基本使用

```
// 引入组件
import LinkButton from '@/components/LinkButton'

<!-- 基本使用 -->
<link-button path='/work/profit' class="fr">创作收益</link-button>
```

2. 组件文档：

| props       |         描述                          | 可选值 | 默认值 |类型   | require|
| ----------- | -------------------------------------|--------|--------|-------|-------|
|   type      |     按钮类型   | 同elementui button组件|   text   | String| 否
|   path      |     跳转地址   | --|   text   | String| 是
|   query     |     跳转地址之后带的查询参数   | 具体文档见vue router 的query|   --   | Object| 否

