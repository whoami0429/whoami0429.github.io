---
title: Java流String按逗号分隔
date: 2021-12-22 16:34:30
tags: [Java,后端] #文章标签，可空，多标签请用格式，注意:后面有个空格
description: Java流String按逗号分隔
comments: false  

---
# 举例一
{% codeblock lang:Java %}
List<String> authAgentList = Stream.of(authAgentEntity.getAgentAuth().split(",")).collect(Collectors.toList());
{% endcodeblock %}
https://blog.csdn.net/java_zyq/article/details/88422865