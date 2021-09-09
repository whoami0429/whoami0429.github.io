---
title: 六位随机码+时间延时5min
date: 2021-09-08 09:38:23
tags: [blog,java,hexo] #文章标签，可空，多标签请用格式，注意:后面有个空格
description: 第一次用hexo
comments: false  
cover: /allimg/image.png

---
 # 六位随机码+时间延时5min

{% codeblock lang:java %}
String code = "";
Random random = new Random(); 
for (int i = 0; i < 6; i++) { 
int r = random.nextInt(10); //每次随机出一个数字（0-9） 
code = code + r; //把每次随机出的数字拼在一起 
} 
//失效时间 
SimpleDateFormat sdf = new SimpleDateFormat("yyyy-MM-dd HH:mm:ss"); 
Date now = new Date(); 
System.out.println("当前时间：" + sdf.format(now)); 
Calendar nowTime = Calendar.getInstance(); 		
nowTime.add(Calendar.MINUTE, 5); //当前时间加5min
System.out.println("截止时间：" + sdf.format(nowTime.getTime()));
{% endcodeblock %}
