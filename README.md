# Css_precompiler-stylus(css预编译处理stylus)

## css 预编译技术有很多
less(weui基于less构建)  sass正流行  postcss当红  stylus轻量且优美

```
npm i stylus -g  //全局安装stylus
browser-sync start --server "./" --files "*.*"   //实时更新
stylus --watch demo.styl --out demo.css   //实时编译向外输出

```

## stylus的规则
stylus中的函数有点类似于js编程，模块化，面向对象，函数式的css

函数就是可复用的代码，stylus编译的实质是node.js文本的替换

*定义变量*
```
a.button
    -webkit-border-radius 5px
    -moz-border-radius 5px    
    border-radius 5px
    
可以写成
border-radius()
    -webkit-border-radius arguments    
    -moz-border-radius arguments   
    border-radius arguments  
a.button
    border-radius(5px)
```
*引用下一级*
```
border-radius()
    -webkit-border-radius arguments
    -moz-border-radius arguments    
    border-radius arguments  
fonts=Helvatia,Arial,sans-serif
baseColor=red
body
    font 12px fonts   
    color baseColor    
a.button
    border-radius(5px)  
    &:hover 
        color baseColor      
   ```
   
   * stylus的核心-——嵌套*
     嵌套之间用tab键
   ```
     ul>(li>a{a$})*3     
        <ul>        
        <li><a href="">a1</a></li>        
        <li><a href="">a2</a></li>       
        <li><a href="">a3</a></li>       
    </ul>
        body         
    color red  
    ul  
        li    
            color blue         
            a         
                background-color @color
                ``` 
   






