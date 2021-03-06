## 3. Dependencies

由于各个Spring Data模块的初始日期不同，大多数模块带有不同的主版本号和次版本号。 找到兼容版本的最简单的方法是依靠Spring Data Release Train BOM，我们提供兼容的版本定义。 在Maven项目中，你可以在POM的`<dependencyManagement/>`部分声明这个依赖关系：

示例1.使用Spring Data发行版BOM

```xml
<dependencyManagement>
  <dependencies>
    <dependency>
      <groupId>org.springframework.data</groupId>
      <artifactId>spring-data-releasetrain</artifactId>
      <version>${release-train}</version>
      <scope>import</scope>
      <type>pom</type>
    </dependency>
  </dependencies>
</dependencyManagement>
```

当前版本是`Kay-M1`。 版本号是按字母顺序升序，目前可用的[如下](https://github.com/spring-projects/spring-data-commons/wiki/Release-planning)。 版本名称遵循以下模式：`$ {name} - $ {release}`其中release可以是以下之一：
- `BUILD-SNAPSHOT` - current snapshots
- `M1`, `M2` etc. - 里程碑
- `RC1`, `RC2` etc. - 发布候选版本
- `RELEASE` - GA release
- `SR1`, `SR2` etc. - service releases `服务版本`

使用BOM的工作示例可以在我们的[Spring Data示例库](https://github.com/spring-projects/spring-data-examples/tree/master/bom)中找到。 如果这是在原地声明Spring数据模块，你想使用没有版本的`<dependencies/>`块。

示例2.声明对Spring Data模块的依赖性
```xml
<dependencies>
  <dependency>
    <groupId>org.springframework.data</groupId>
    <artifactId>spring-data-jpa</artifactId>
  </dependency>
<dependencies>
```
