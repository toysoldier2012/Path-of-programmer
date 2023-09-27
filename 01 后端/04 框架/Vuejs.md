
# Hello Vuejs

``` html 
<!DOCTYPE html>
<html>
    <head>
        <meta charset="UTF-8" />
        <title>Hello Vue</title>
        <script type="text/javascript" src="/HelloVue/vue.js"></script>
    </head>

    <body>
        <div id="root">
            <h1>Hello {{name}} </h1>
            单项数据绑定：<input type="text" :value="name"/>
            双向数据绑定：<input type="text" v-model="school">
            <ul>
                <li> {{campus[0]}} </li>
                <li> {{campus[1]}} </li>
                <li> {{campus[2]}} </li>
            </ul>
        </div>
        <script type="text/javascript">
            Vue.config.productionTip = false;

            const vm = new Vue({
                data: {
                    name: 'xiaoyu',
                    school: 'abc',
                    campus: ["Paris", "Lyon", "Lille"]
                }
            });
            vm.$mount(' #root ');

            let person = {
                name:'yezi',
                sex:'f'
            }

            let number = 18
            
            // Object.defineProperty(person, 'age', {
            //     value:18, 
            //     enumerable:true, 
            //     writable:true, 
            //     configurable:true
            // })
            
            Object.defineProperty(person, 'age', {
                get:function(){
                    return number
                },

                set(value){
                    number = value
                }
            })

            console.log(person)
            console.log(Object.keys(person))
        </script>
    </body>
</html>
```