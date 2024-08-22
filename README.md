针对Flac3D或UDEC模拟完成后的后处理结果展示不直观的问题，为了提升结果的直观性，可以使用Surfer软件对模拟结果进行后处理。通过Surfer，可以将模拟结果转化为高质量的3D图形，从而显著增强结果展示的效果和分析的价值。

在Flac3D或者UDEC模拟完成后，可以通过内置的Fish语言提取模型变量数据，并以Surfer可以读取的格式组织起来。然后，使用Surfer的多种绘图功能，如等高线图、三维表面图和矢量图等，对提取的数据进行可视化处理。例如，可以通过Surfer生成底板应力的可视化图形，将应力大小与高低直观地表达出来。

重点：针对想要输出的这一层网格单元（一定是单层，查找Z的范围从底部到顶部）输出其info信息与stress信息：

Print stress code：
program log on 

program log-file 'stress105.log'

zone list stress range position-x 0 500 position-y 0 300 position-z 10   13 

program log off
#########################################################

Print info code：
program log on 

program log-file 'zoneinfo105.log'

zone list information range position-x 0 500 position-y 0 300 position-z 10  13 

program log off
#########################################################

注：不同的Flac3D版本输出代码不同，本质都是输出单元的info与stress
