# 对markwo的认知
## 写前
为了完善自己的**wo-editor**，不得已将一个优秀的轮子——**marked.js**给拆得支离破碎，marked.js是一个非常优秀的解析markdown的原生js轮子，以前学的一些js知识早就忘了，因此花了整整一天才完整的将它拆开，然后组装成了一个新的轮子——**markwo**（目前相似度几乎百分百，不过以后会为了完全适应**我网**开发一些新的功能），还是蛮有成就感的，哈哈，以下正文！
## 正文
首先，我得感谢一下伟大的[marked.js](https://github.com/chjj/marked)，感谢这么伟大的轮子！
其次，我得感谢一篇博文：[nodejs源码研究:marked-prettyprint](http://blog.alonestar.org/2014/02/559/)，它给于了我很大的帮助。
___
### markwo的主体框架
    ;function(){
    ...    //定义逻辑与相关组件
    //暴露接口供外部使用
    function markwo(src,opt){
        try{
    	    if (opt)opt = merge({}, markwo.defaults, opt);
    	    return Parser.parse(Lexer.lex(src,opt));
    	}catch(e){
    	    console.log('error');
    	}
    }
    markwo.defaults = { ... };
    this.markwo = markwo;
    }).call(function() {
        return this || (typeof window !== 'undefined' ? window : global);
    }());






