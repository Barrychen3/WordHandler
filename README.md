# WordHandler
word处理工具初版

声明:本工具是基于POI-3.13开发的,需要引入对应的jar包,并与POI有着较高的耦合度,使用前需注意!

场景:通过Word模板来实现动态的word生成

  基本要求:
  
    1:替换文本中的内容
    
    2:替换表格中的内容(不用动态生成表格)
    
    3:替换后的内容应该与替换前的内容格式相同
    
    4:模板修改方便
    
现有工具分析:

  freeMarker:
  
    使用方法:通过word生成xml文件,将xml文件作为模板来生成动态的word文件
    
    优点:如果模板固定,能够通过它强大的替换功能来生成动态的word文件
    
    缺点:xml文件很难修改,每次修改word模板都要重新生成一次xml,而且还需要手动的修改xml文件.
    
  java poi
  
    使用方法:直接读取word文件,替换里面各个部分的内容
    
    优点:直接使用word文件作为模板
    
    缺点:本身的替换逻辑无法保留格式
    
  为什么选择封装POI:
  
    1:因为时间和学习成本(懒)的问题,没有研究docx的xml规则,因此决定直接对现有的工具进行封装,来实现需求.
    
    2:freeMarker本身只是对通用的模板进行处理,底层并不能直接解析word文件.
    而poi本身就是对word文件进行操作的,因此可以对直接在poi的api上进一步的封装.
  
说明:

  一:支持文件类型(docx)
  
    一.1 标签:${key}待替换的内容.
    
    一.2 支持对文本和表格中的标签进行替换
    
    一.3 测试用例见test/*


