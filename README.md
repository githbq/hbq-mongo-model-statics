>  mongo-model-statics
##  mongo-model-statics mongoose 通用静态方法
 

## 关键字
- `param` 参数,结构:`{condition:{}}` condition:为具体查询条件    
- 所有接口返回的都是promise
- 查询条件会走一个过滤规则  
    1. 属性名以 $开头 匹配以某某开始
    2. 属性名以 $结尾 匹配以某某结尾的数据
    3. 属性名以 $属性$ 匹配包含关系
## 方法 
 

### 根据参数获取查询数据的数量

- `_getCount(param)  promise<int>`

###  获取分页数据
 -  `_getPage(param, callback, countcallback)  `
    -  param:`{pageSize,pageIndex,condition}`
    -  callback   对查询出来的promise进行二次定制
    -  countcallback 对查询数据的promise进行二次定制
    -  返回`Promise<{ total, list, pageIndex, pageSize}>`

### 查询数据

-   `_find(param)  Promise<[]>` 

### 查询单条数据  

-   `_findOne(param) Promise<Object>`

### 根据id查询数据 id可以是字符串   

-   `_findById(id)  Promise<Object>`

### 根据参数删除数据

-   `_delete(param)`

### 新增数据

-   `_add(data)`
-   data:数据自身

### 更新数据

-   `_update(condition, updateData, options?)`
-   updateData:将更新的数据
-   options:可选 默认:`{ multi: true,...options}`