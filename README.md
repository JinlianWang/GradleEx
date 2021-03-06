##### Notes 

* How to manually download gradle.zip and use it in gradle wrapper (to work around)? 

  Use `distributionUrl=file:///Users/atk847/Downloads/gradle-2.10-bin.zip`

* How to use local Maven repositoary? 

  Use 
  ```
  repositories {
     mavenLocal()
  }
  ```
  It will looks into ~/.m2/settings.xml for information where the local Maven repository 
  is located. If no information is found, it assumes ~/.m2/repository.  In order to make 
  use of a non-standard local maven repository, use 
  ```
  repositories {
      maven {
          url 'file://export/home/me/.m2/repositor'
      }
  }
  ```
 * How to create gradle wrapper? 
 
    Use `gradle wrapper --gradle-version 2.13`. 
    
 * How to create a parent gradle, like a parent POM? 
 
    Define a gradle script (something like a parent pom), then apply it (something like extending) in my build.gradle file through `apply from: 'https://youUrlHere/parent.gradle'`
    
 * How to use local jar files? 
 
    Per `https://stackoverflow.com/questions/20700053/how-to-add-local-jar-file-dependency-to-build-gradle-file`, use 

    ```
    dependencies {
      compile files('libs/something_local.jar')
    }

    or
    dependencies {
      compile fileTree(dir: 'libs', include: ['*.jar'])
    }

    or 

    repositories {
     flatDir {
         dirs 'libs'
     }
    }
    ```
 
 * Use C1 Snapshots? 
 
   Use 
   
   ```
    repositories {
        maven {
        url 'https://nexus.kdc.capitalone.com/mother/content/groups/CI_Snapshots'
      }
    }
  ```

##### References

* https://spring.io/guides/gs/gradle/
* http://www.vogella.com/tutorials/Gradle/article.html


