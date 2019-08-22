# Visualization
This part is the lessons i learnt during studying.

matplotlib中绘画知识点。
一、原理
基于面向对象编程的思想，采用了面向对象式的绘画原理，整体上分为Figure->Axes->Chart(hist,bar,barh,scatter,pie,plot...)
为了便于理解，Figure看作为窗口/画板，Axes看作为窗口中的一个区域/画纸（画纸的骨架），Chart看作为画在画纸上的各种图表。从而可以综合理解：可以先有一张画板，在画板上铺上几张画纸，从而在各张画纸上分别绘画各种图表。

二、Figure/窗口
1.figure()
（1）函数及参数
matplotlib.pyplot.figure(num=None, figsize=None, dpi=None, facecolor=None, edgecolor=None, frameon=True, FigureClass=<class 'matplotlib.figure.Figure'>, clear=False, **kwargs)
1）num：窗口的编号，有则以该数值为窗口ID，无则默认为1,2,3，递增。
plt.figure()与plt.figure(num=3)
2)figsize:窗口的大小,整数元组，默认为无
plt.figure(num=6,figsize=(5,8))
3)dpi:窗口的分辨率
4）facecolor：可选参数，表示窗口的背景颜色，颜色的设置是通过RGB，范围是'#000000'~'#FFFFFF'，其中每2个字节16位表示RGB的0-255
5）edgecolor:可选参数，表示窗口的边框颜色，如果没有提供则默认为figure,edgecolor
6）frameon:可选参数，表示是否绘制窗口的图框，默认是
7）FigureClass：暂不了解
8）clear:可选参数，默认是false,如果提供参数为ture，并且该窗口存在的话 则该窗口内容会被清除

（2）方法



三、Axes/区域（坐标轴）
（1）Axes类
matplotlib.axes.Axes(fig,rect,facecolor=None,frameon=True,sharex=None,sharey=None,label='',xscale=None,yscale=None,**kwargs)
1)fig:添加至的窗口
2）rect:[left,bottom,width,height],离左下角的距离以及区域的大小
3）sharex,sharey:与其他Axes实例共享x,y
4)frameon:区域的边界线是否可见
5）其他:adjustable,agg_filter,alpha,anchor,animated,aspect,autoscale_on...2
（2）绘制
1）Axes.plot
Axes.plot(self,*args,scalex=True,scaley=True,data=None,**kwargs)
*args:x,y,fmt('rc')
**kwargs:color,label,linestyle,linewidth,marker,markersize...



（1）创建Axes对象
1）sublpots()                     
fig,axes=plt.subplots(2, 2)，生成2X2的子区域
注：plt.plot()紧跟最近的一个区域
2）subplot()
ax1=plt.subplot(2,2,1)

（2）
1）若有多个Axes时，调整他们之间的间距
fig.subplots_adjust(left=0.2, bottom=0.1, right=0.8, top=0.8,hspace=0.5)
2）统一设置Axes
ax1.set(xlim=[-10,12],ylim=[-6,4],title='This is TU1',xlabel='xlabel',ylabel='ylabel',facecolor='#ffeedd')
3）添加网格
ax1.grid(True)



四、chart/图表
