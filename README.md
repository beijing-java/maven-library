### github仓库
+ 创建本地maven仓库
  
  以某一文件为maven仓库，
  引入方式：

  ```
  	 releaseRepo="file:///D:/WProjectSVN/local-maven-library"
  ```

+ 然后先再在本地打包出aar文件
  
  引入mave插件，这里我使用的是网上的封装插件
  root项目最外层加
  //一款可以简单上传Maven库的插件
    //https://github.com/easilycoder/EasyDependency
    classpath 'tech.easily:EasyDependencyPlugin:1.0.1'
  //添加应用插件
  apply plugin: 'easy-dependency'

+ 新建github仓库
  
  在自己的github上新建一个仓库，名字看自己喜好。

+ 将打包好的文件通过git上传至github仓库
  
  可以把打包好的所有文件上传，也可以直接放置一个arr文件。

+ 使用方式:两步走

  + 项目build.gradle加入maven仓库,这里由于放置到github，所以改为
  ```
  maven{ url 'https://raw.githubusercontent.com/beijing-java/maven-library/master'}
  ```
  + 在app.gradle中引入

    ```
     implementation "你定义的groupId:你定义的artifactId:你定义的version"
    ```
