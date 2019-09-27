  ## 在ul，li标签中显示用v-for循环获取后台数据库的内容
  + 运用v-for在div中进行后台数组的for循环，然后获取单行的数组从而再获取单个数据这样就可以在ul,li中获取查询到后端数据库中的数据。
* html中的代码

 ```html
 <div class="listlist"  v-for="item in list">
          <ul class="list_ul" >
            <li class="list_li1" v-html="item.student_name "></li>
            <li class="list_li2" v-html="item.school"></li>
            <li class="list_li3" v-html="item.phone"></li>
        </ul>
</div>
```

* js前后端交互的代码

```js
<script>
export default {
  data() {
    return {
    },
     created(){
        axios.get("http://127.0.0.1:7001/getstudent", {}).then(res => {
            this.list= res.data;
        console.log(this.list)
      }),
     }
  }
  }
</script>
```