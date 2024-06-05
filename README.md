### Matplotlib
Some personal notes when using Matplotlib

<details>
  <summary> 数据读取 </summary>
  numpy.genfromtxt() 数据文件读取，注意三点：
  文件格式：设置合适分隔符和数据类型  
  错误处理：提供了多种错误或缺失数据选项  
  内存使用：对于大文件，可以块的形式加载数据  

  - 分隔符：delimiter=','
  - 数据类型：dtype=[('myint', '<i8'), ('myfloat', '<f8'), ('mystring', 'S5')]
  - 缺失填充： missing_values='NA', filling_values=(np.nan)  
  - 去头尾：skip_header=1, skip_footer=1
  - 选取列：usecols=(0,-1) or [0,1,2]

</details>


<details>
  <summary> 色条 </summary>  
  
  - 色条添加：fig.colorbar(im,ax,'horizontal',format=formatter,...)  
    在图窗加色条，formatter是设置字符格式,formatter=mpl.ticker.StrmethodFormatter('x:.{f}')
    
  - 色条归一化  
    在画图函数参数中的norm可以根据数据归一化  
    norm=mpl.colors.Normalize(-wlim/n,wlim/n)  
    以contourf函数为例：ax.contourf(X,Y,Z,norm=norm,cmap=mpl.cm.get_cmap("ReBu)  
</details>

<details>
  <summary> 子图布局 </summary>
  
  - 全等排布：子图大小一致  
    fig,axes=plt.subplots(row_n, col_n, figsize=(,), sharex=True, sharey=True)  
    
  - 规整的不等排布：子图大小不同  
    spec=fig.add_gridspec(row_n, col_n, width_ratios=[,,],height_ratios=[,,])  
    选单框做子图：ax=fig.add_subplot(spec[nrow,ncol])  
    用多个框做子图：ax=fig.add_subplot(spec[:2,1:3])  
</details>

<details>
  <summary> 坐标轴消除</summary>  

  - 全部消除：plt.axis("off")
  - 选择消除：ax.get_xaxis().set_visible(False) [对三维不管用]  
</details>
