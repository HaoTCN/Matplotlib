### Matplotlib
Some personal notes when using Matplotlib

<details open>
<summary> 色条 </summary>
  
- 在图窗加色条：fig.colorbar(im,ax,'horizontal',format=formatter,...)  
  formatter是设置字符格式,formatter=mpl.ticker.StrmethodFormatter('x:.{f}')
  
- 在画图函数参数中的norm可以根据数据归一化色条  
  norm=mpl.colors.Normalize(-wlim/n,wlim/n)  
  以contourf函数为例：ax.contourf(X,Y,Z,norm=norm,cmap=mpl.cm.get_cmap("ReBu)
</details>

<details open>
<summary> 子图布局 </summary>

- 全等排布：子图大小一致  
  fig,axes=plt.subplots(row_n, col_n, figsize=(,), sharex=True, sharey=True)  
  
- 规整的不等排布：子图大小不同  
  spec=fig.add_gridspec(row_n, col_n, width_ratios=[,,],height_ratios=[,,])  
  选单框做子图：ax=fig.add_subplot(spec[nrow,ncol])  
  用多个框做子图：ax=fig.add_subplot(spec[:2,1:3])
