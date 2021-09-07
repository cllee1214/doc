### 详情组件

1. 组件引入：

```
import DetailView from '@/components/DetailView'
```

2. 文档：

    props:
    * info: 需要展示的详情信息

    * renderConfig: 如何展示详情信息的相关配置，见下表


  |  参数 |                   说明                | 默认值 |
  |:-----:|:-------------------------------------|---------|
  |  span | 定义单元格宽度所占比例，用 | 分割，竖线前面对应key的宽度，后面对应值的宽度 | 默认值根据显示模式自动获取 |
  |  order | 在所有单元格中的顺序 | 按照传入的数据默认顺序 |
  |  label | 当前key对应的中文 | 默认显示key |
  |  hidden | 是否展示当前字段 | 默认展示 |
  |  isImage | 作为图片显示 | - |
  |  isIDCard | 作为身份证显示 | false |
  |  display | 显示模式，可选值为 default json list table | 根据对应的值自动判断 |
  |  fields | table展示的字段相关配置，只有在display为table时才生效，fields.key为需要展示的字段，label为展示字段的标题， width为宽度，参照element-vue table组件  |  |
  |  tableMaxHeight | table最大高度，只有在display为table时才生效，参照element-vue table组件  | - |
  |  formatter | 格式化数据函数，参数为当前值的key value。把此函数的返回值用于显示 | - |

3. 示例：

``` 
// json类型的
 post_data: {
    label: '发送数据',
    span: '2|10',
    display: 'json'
}

//table类型的，和elemnt的table组件一样。展示的字段为name 和 date，标题分别为 ‘名字’和‘日期’
 testTable1: {
    label: '表数据',
    display: 'table',
    tableMaxHeight： 400，
    span: '4|20',
    fields: [
        {
            key: 'name',
            label: '名字',
            width: 60
        },
        {
            key: 'date',
            label: '日期'
        }
    ]
}

//  xxxxx为最终显示结果
route: {
    label: '路由',
    span: '2|4',
    order: 0,
    formatter: function({value, key}) {
        // key为 route， value为相关的值
        return 'xxxxx'
    }
}
```


