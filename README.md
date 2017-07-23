junit-casperjs 
==============

JUnit Runner to CasperJS (http://casperjs.org/) Tests.

All files sufixed with `.test.js` on classpath will be executed as a TestCase.

**IMPORTANT**
My (bekce) version runs `casperjs test` command as instructed [here](http://docs.casperjs.org/en/latest/testing.html).

Example:
```javascript
casper.test.begin('Demo CasperIT test', function suite(test) {
    casper.start().then(function() {
        this.setContent('<div class="heaven"></div>');
        test.assertDoesntExist('.taxes');
    }).run(function() {
        test.done();
    });
});
```

## Current Version
0.4.1-SNAPSHOT

##PhantomJS and CasperJS executable
If the `casperjs` or `phantomjs` aren't in the PATH, you may set the java System Properties `casperjs.executable` and `phantomjs.executable` to say to `CasperRunner` where the executables are, e.g.: 
```
mvn test -Dcasperjs.executable=/opt/casperjs/bin/casperjs -Dphantomjs.executable=/opt/phantomjs/bin/phantomjs
```

## Example
 * JUnit Test Class: [CasperTest.java](src/test/java/com/github/raonifn/casperjs/junit/CasperTest.java)

 * Casper Test: [example.test.js](src/test/casperjs/example.test.js)

## Maven users
Install with: `mvn -DskipTests clean install`

* Dependency
```xml
<dependency>
   <groupId>com.github.raonifn</groupId>
   <artifactId>casperjs-junit</artifactId>
   <version>0.4.1-SNAPSHOT</version>
</dependency>
```
