# pagination
通过封装element-ui的pagination达到项目内复用

组件引用写法：

`<page :total="total" :size="size" :sizes="sizes" @getPageMsg="getPageMsg"></page>`

###### getPageMsg：获取分页信息；
###### total：数据的总长度；Number
###### size：每页展示的条数；Number
###### sizes：每页展示条数的可选数组；Array