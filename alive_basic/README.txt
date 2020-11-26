一.源文件read:
1.Catfish.java
    声明CatFish这个类，并继承父类LIving Being。它拥有生死的状态，每次游动耗费的能量
    所处的行，列；对应图片的名称，年龄，能量的属性
    开始模拟，并声明方法去获得上述属性
    声明方法去判断鱼的生死状态
    重点：声明方法swimIfPossile,使鱼游动，消耗能量，并且达到随机移动的目的（详见代码Line137~145）
              声明方法LiveALittle，根据鱼的能量值判断返回死亡还是年龄+1后继续游动
2.HtmlImage.Java文件声明了HtmlImage类
   声明两个字符串：imageName（图片名称）
    	              alternateText(如果图像不可用,要显示的文本)
   构造一个带两个参数的方法：HtmlImage,其中两个参数分别是前面两个字符串的值
   声明一个可变字符串，为了后面显示图片
3.HtmlTable.java
   大概是在构造池塘的格子（即表格）。
4.HtmlAnchor.java
    声明HtmlAnchor 类 允许编程访问服务器上的 HTML <a> 元素(就是建立超链接)
5.HtmlPage.java		
     声明HtmlPage类，便于Servlet new出来它从而创建新的页面	
6.LivingBeing.java
    声明Living Being类（不是很懂），便于创建catfish对象
7.MySimulation.java
    (里面多了一段判断数组的布尔值的代码)并且使用了迭代器去遍历并选择Map中的对象
8.Simulation.java
       进行对整个池塘的模拟
          包括声明方法诸如：添加生物，取随机数，模拟时间块等
9.SimulationServlet.java
          重要：通过调用之前各个源文件所声明的类（尤其是方法）最终实现模拟池塘与鱼游动的过程
10.SimulationView.java
           重要：配置了后面所需要的图片的url
二：两个HTMl文件的差异（MySimulation简称MS，initialWorldFish简称为iWF）
      1.仔细看了MySimulation后发现这两个页面其实存在“套娃现象”，
          iWF指向SimulationServlet
          MS指向MySimulation.，而后者输出的新的html页面又将指向SimulationServlet
         即最终达到了同样的目的，然而MS将多经历一步（具体表现为MS第一次的按钮的value为redisplayform，而后变成鱼iWF相同的Start Simulation）
         这其中具体的实现过程主要靠MySimulation这个servlet来实现