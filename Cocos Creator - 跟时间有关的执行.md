- setTimeout(fn, time); 
- setInterval(fn, time);
- component.scheduleOnce(fn, time);
- component.schedule(fn, time); 

    以上四种方式在对付延时或者重复操作的情况下使用。

    如果使用的是倒计时，则推荐setTimeout（也可以使用setInterval，不过可能会在离屏的时候报错）。
    
    这是因为倒计时必须在时间上相对精确一些，离开屏幕的时候也需要将计时运作起来，而schedule系列的并不会在离屏的时候计时。

    如果也就指精确到完成动作、动画这种层次的话应该使用schedule系列，或者Action(普通动作函数),Tween(基于Action封装的链式动作函数)系列的延时加回调的方式，而不是setTimeout。这也是跟离屏是否计时有关。
