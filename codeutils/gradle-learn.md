
[gradle教程地址][gradletutoraddr]

[gradletutoraddr]: https://dongchuan.gitbooks.io/gradle-user-guide-/the_java_plugin/

[gradle tutor](https://dongchuan.gitbooks.io/gradle-user-guide-/the_java_plugin/)

#### 添加任务

    task hello{
        print "Hello World"
    }
    
    hello.doFirst{
        print "do first, after task"
    }
    
    hello.doLast{
        print "do last, after first"
    }
    
    hello << {
        print "i am same as doLast"
    }

##### 任务依赖(*被依赖的任务会先执行*)

    task sayHello (dependsOn: hello){
        print "i am depends on hello task"
    }

#### 添加插件
    
    apply plugin: 'java'

#### 指定依赖仓库

    repositories {
        mavenCentral() //中央仓库
        maven {
            url "http://repo.mycompany.com/maven"
        }
        ivy {
            url "http://repo.mycompany.com/repo"
        }
        ivy {
            url "../local-repo"
        }
        maven {
            url "../local-repo"
        }
    }

#### 添加依赖

    dependencies {
        compile "group:name:version"
    }
##### 依赖作用域
    
    *compile
    *runtime
    *testCompile
    *testRuntime

##### 依赖其他项目

    dependencies {
        compile project(':other-project')
    }

#### 定制MANIFEST.MF

    sourceCompatibility = 1.8
    version = '1.0'
    jar {
        manifest {
            attributes 'title' : 'gradle',
            'author' : 'zhaoji',
            'version' : '1.0'
        }
    }

#### 发布文件

    apply plugin: 'maven'
    uploadArchives {
        repositories {
            flatDir {
                dirs 'repos'
            }
        }
        repositories {
            mavenDeployer {
                repository(url: "file://local/repo")
            }
        }
    }

#### 生成eclipse项目

    apply plugin : 'eclipse'
    gradle eclipse
