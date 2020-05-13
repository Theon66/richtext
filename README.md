# richtext
修改了wangEditor的源代码，在其中加入了视频上传功能，传上来方便下次使用能找得到

# 配置
```javascript
// 视频上传
wangEditor.customConfig.uploadVideoServer = '${contextPath}/siteInformationController/upload-wang-file'; 
wangEditor.customConfig.uploadVideoHooks = { // 上传完成处理方法
  customInsert: function (insertVideo, result) {
    if (result.errno === 0) {
      result.data.forEach(function (link) {
        link && insertVideo(link);
      });
    } else {
      //自定义上传失败提示
    }
  }
};
```


视频上传代码主要参考了：
https://www.lagou.com/lgeduarticle/99623.html
