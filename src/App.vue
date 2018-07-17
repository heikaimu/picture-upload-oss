<template>
  <div id="app">
    <PictureUploadOss
      equipment="mobile"
      :width="100"
      :borderRadius="5"
      :maxNum="maxNum"
      :maxSize="maxSize"
      :allowType="allowType"
      :ossConfig="ossConfig"
      :path="path"
      @finishUploadAll="finishUploadAll"
    ></PictureUploadOss>
  </div>
</template>

<script>
  import PictureUploadOss from './lib/picture-upload-oss';
  export default {
    name: 'app',
    data () {
      return {
        maxNum: 4,
        maxSize: 1024 * 1024 * 1,
        allowType: 'jpeg/jpg/png',
        path: 'publicity/article/1/articlevideo',
        ossConfig: {
          region: 'oss-cn-shenzhen',  //bucket 所在的区域, 默认 oss-cn-hangzhou
          accessKeyId: 'LTAIsncTQDlxqm6J',
          accessKeySecret: 'qT03tPGWlLVS8eyzoibXgffwoZjDcZ',
          bucket: 'cdsx-test',
          secure: false
        }
      }
    },
    methods: {
      finishUploadAll(res) {
        console.log(res);
      }
    },
    components: {
      PictureUploadOss
    }
  }
</script>

<style lang="scss">
</style>
