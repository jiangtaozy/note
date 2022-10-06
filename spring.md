- 运行项目

      mvn spring-boot:run

- 安装本地jar包

      mvn install:install-file -Dfile=ojdbc6-11.2.0.jar -DgroupId=com.oracle -DartifactId=ojdbc6 -Dversion=11.2.0 -Dpackaging=jar -DgeneratePom=true

      install:可以将项目本身编译并打包到本地仓库
      install-file:安装文件
      -Dfile=ojdbc6.jar : 指定要打的包的文件位置,这里指当前目录下的ojdbc6.jar
      -DgroupId=com.oracle : 指定当前包的groupId为com.oracle
      -DartifactId=ojdbc6 : 指定当前的artifactfactId为ojdbc6
      -Dversion=11.2.0 : 指定当前包的版本为11.2.0
      -DgeneratePom=true:是否生成pom文件
