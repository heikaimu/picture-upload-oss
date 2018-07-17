基于vue的七牛图片上传组件

[演示地址](http://39.108.140.212/picture-upload-qn/index.html)

### 安装
```
npm i picture-upload-oss -S
```

### 引入
test.vue
```
import PictureUploadOss from './lib/picture-upload-oss';
<PictureUploadOss
      equipment="mobile"
      :width="100"
      :borderRadius="5"
      :maxNum="maxNum"
      :maxSize="maxSize"
      :allowType="allowType"
      :ossConfig="ossConfig"
      :path="path"
      @finishUploadAll="finishUploadAll">
</PictureUploadOss>
```

```
data () {
      return {
        maxNum: 4,
        maxSize: 1024 * 1024 * 1,
        allowType: 'jpeg/jpg/png',
        path: '/test',
        ossConfig: {
          region: '******',  //bucket 所在的区域, 默认 oss-cn-hangzhou
          accessKeyId: '******',
          accessKeySecret: '******',
          bucket: '******',
          secure: false // true是https， false是http
        }
      }
    }
```

### 参数解释

| 参数             | 描述                      | 可选值             | 默认值                            |
|------------------|--------------------------|--------------------|----------------------------------|
| equipment        | 用于切换pc和移动端的样式   | pc,mobile          | pc                               |
| width            | 小图片的尺寸              |                    | 100                              |
| borderRadius     | 小图片的圆角              |                    | 5                                |
| maxNum           | 最大上传数                |                    | 9                                |
| maxSize          | 最大上传的图片尺寸         |                    | 1024 x 1024                      |
| allowType        | 图片类型                  |                    | jpeg/jpg/png                     |
| path             | oss中的图片存储路径        |                    |                                  |
| ossConfig        | Oss的配置信息             |                    |                                  |

### 派发事件
| 函数名           | 描述                      |
|------------------|--------------------------|
| finishUploadAll  | 图片上传完的派发事件       |
