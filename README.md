# upload-image-preview
图片上传预览


createObjectUrl和fileReader两种方式预览上传图片

todo
上传可以用FormData来处理，整理下文档 

使用FormData对象添加字段方式上传文件

HTML代码

<div id="uploadForm">
    <input id="file" type="file"/>
    <button id="upload" type="button">upload</button>
</div>
这里没有<form>标签，也没有enctype="multipart/form-data"属性。

javascript代码

var formData = new FormData();
formData.append('file', $('#file')[0].files[0]);
$.ajax({
    url: '/upload',
    type: 'POST',
    cache: false,
    data: formData,
    processData: false,
    contentType: false
}).done(function(res) {
}).fail(function(res) {});