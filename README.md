# maven-plugin-dependency-sample
Testing maven plugin dependency resolve when it's in the same project

# what the problem is
`plugin-dependency-module` is a normal dependency. `business-module` tries to use it, but as a `plugin dependency`. Maven cannot see that `plugin-dependency-module` is part of a project and it fails. In case of normal `dependency` (not `plugin-dependency`) maven can handle it.

Error is:
```
[ERROR]   The project io.github.xshadov.sample:business-module:1.0.0 (...\business-module\pom.xml) has 1 error
[ERROR]   Unresolveable build extension: Plugin org.springframework.cloud:spring-cloud-contract-maven-plugin:3.1.1 or one of its dependencies could not be resolved: Could not find artifact io.github.xshadov.sample:plugin-dependency-module:jar:1.0.0 ... (...) -> [Help 2]
```

# running

`mvn clean install`
