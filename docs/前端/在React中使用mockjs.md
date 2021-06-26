导入依赖：

```bash
npm install mockjs
npm install axios
```

生成随机数据：

```js
import Mock from 'mockjs'//ES6写法
Mock.mock("/info",{
    id: "@id()",
    username: "@cname()",
    date: "@date()",
    avatar: "@image('200x200','red','#fff','avatar')",
    description: "@paragraph()",
    ip: "@ip()",
    email: "@email()"
})
```

导入并使用：

```js
import axios from 'axios';
import './mock/index'
```

```jsx
componentDidMount(){
    //接口地址与拦截地址要一致
    axios.get("/info")
        .then((res)=>{
        console.log(res.data)
    }).catch(err=>{
        console.log(err)
    });
}
```

> 注意mock的随机文件也要放在是src目录下