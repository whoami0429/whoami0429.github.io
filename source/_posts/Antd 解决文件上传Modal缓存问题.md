---
title: Antd 解决文件上传Modal缓存问题
date: 2021-12-22 16:53:30
tags: [Vue,前端,Antd] #文章标签，可空，多标签请用格式，注意:后面有个空格
description: Antd 解决文件上传Modal缓存问题
comments: false  

---
# 举例一
{% codeblock lang:Vue %}
<a-form-item
        :labelCol="labelCol"
        :wrapperCol="wrapperCol"
        label="上传附件">
        <div :key="uploadKey">
        <a-upload
          name="file"
          :multiple="true"
          :action="uploadAction"
          :headers="tokenHeader"
          @change="handleChange">
          <a-button> <a-icon type="upload" /> 点击选择上传文件 </a-button>
        </a-upload>
        </div>
</a-form-item>
data () {
      return {
        uploadKey: '',
 		visible: false,
    },

 watch: {
      visible() {
        if (this.visible) {
          this.uploadKey = ''
        } else {
          this.uploadKey = Math.random()
        }
      },
    },

{% endcodeblock %}
在upload 组件外加一个key 赋随机值，即可清除缓存
通过监听弹窗modal 的开闭状态 更改key的值，建议关闭状态时更改为随机key ，避免影响操作效果