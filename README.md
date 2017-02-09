Cookie-parser API for Scala.js
================================
This is a Scala.js type-safe binding for [cookie-parser](https://www.npmjs.com/package/cookie-parser)

Cookie parsing with signatures.

#### Build Dependencies

* [ScalaJs.io v0.3.x](https://github.com/ldaniels528/scalajs.io)
* [SBT v0.13.13](http://www.scala-sbt.org/download.html)

#### Build/publish the SDK locally

```bash
 $ sbt clean publish-local
```

#### Running the tests

Before running the tests the first time, you must ensure the npm packages are installed:

```bash
$ npm install
```

Then you can run the tests:

```bash
$ sbt test
```

#### Examples

```scala
import io.scalajs.JSON
import io.scalajs.npm.cookieparser._
import io.scalajs.npm.express.{Express, Request, Response}

val app = Express()
app.use(CookieParser("test123"))

val results = CookieParser.JSONCookie("foo=bar; equation=E%3Dmc%5E2")
println(s"cookies => ${JSON.stringify(results.orNull)}")
```

#### Artifacts and Resolvers

To add the `CookieParser` binding to your project, add the following to your build.sbt:  

```sbt
libraryDependencies += "io.scalajs.npm" %%% "cookie-parser" % "1.4.3"
```

Optionally, you may add the Sonatype Repository resolver:

```sbt   
resolvers += Resolver.sonatypeRepo("releases") 
```