## lv0

1.f12,发现cat=dog

<img src="https://gitee.com/home-changan/picture/raw/master/202212101928655.png" alt="image-20221210191738341" style="zoom: 67%;" />

2.改网址

<img src="https://gitee.com/home-changan/picture/raw/master/202212101928110.png" alt="image-20221210191845429" style="zoom: 50%;" />

## lv1

1.f12发现提示，设置了WAF，需要绕过，还发现了url提示

![image-20221210191925951](https://gitee.com/home-changan/picture/raw/master/202212101928877.png)

2.跳转至calc.php页面，发现黑名单

<img src="https://gitee.com/home-changan/picture/raw/master/202212101928465.png" alt="image-20221210192213382" style="zoom:67%;" />

3.绕过WAF需要在变量前加空格，绕过黑名单用到了chr(47),url为calc.php num=var_dump(scandir(chr(47)))

<img src="https://gitee.com/home-changan/picture/raw/master/202212101928773.png" alt="image-20221210192403640" style="zoom: 67%;" />

4.发现f1agg,跳转至calc.php num=var_dump(file_get_contents(chr(47).f1agg))

![image-20221210192759659](https://gitee.com/home-changan/picture/raw/master/202212101928716.png)

## lv2

1.f12发现password需要等于404但不能为数字（需要绕过is_numeric函数）所以在数字后需要加一个字母，还发现需要用POST请求

<img src="https://gitee.com/home-changan/picture/raw/master/202212102021047.png" alt="image-20221210202125242" style="zoom:67%;" />

2.进入菜单中的buyflag界面，通过burp截取请求，并发送给repeater

<img src="https://gitee.com/home-changan/picture/raw/master/202212102032509.png" alt="image-20221210202616812" style="zoom:50%;" />

3.发现必须是cuit才能购买，修改cookie参数

<img src="https://gitee.com/home-changan/picture/raw/master/202212102033823.png" alt="image-20221210202839540" style="zoom:50%;" />

4.发现需要上传密码，先修改请求（需要添加一行参数：Content-Type: application/x-www-form-urlencoded）

然后空一行传参

<img src="https://gitee.com/home-changan/picture/raw/master/202212102033260.png" alt="image-20221210203135533" style="zoom:50%;" />

5.发现需要交钱，于是补充一行参数，参数之间&隔开

<img src="https://gitee.com/home-changan/picture/raw/master/202212102033803.png" alt="image-20221210203231630" style="zoom:50%;" />







