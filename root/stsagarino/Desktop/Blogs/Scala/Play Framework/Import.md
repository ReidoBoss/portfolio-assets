### Do Not Do This:

```scala
import scala.concurrent.{Future, ExecutionContext}
```

### Do This Instead:

```scala
import scala.concurrent.Future
import scala.concurrent.ExecutionContext
```

By importing each object or class on a separate line, you make the code easier to read and modify, especially as the project grows.

## Import Order

Imports should be organized in the following sequence:

1. **Java imports**
2. **Scala imports**
3. **Play Framework imports**
4. **Library dependencies** (if required)
5. **Models**
6. **Utilities and error handling**

### Example

Here’s an example of how to structure imports in a Scala file:

```scala
// Java imports
import javax.inject._
import java.util.UUID

// Scala imports
import scala.concurrent.Future
import scala.concurrent.ExecutionContext

// Play Framework imports
import play.api.db.slick.DatabaseConfigProvider

// Library dependencies
import cats.data._
import cats.implicits._
import slick.jdbc.PostgresProfile

// Models
import domain.project._
import domain.responses._
import domain.workspace.WorkspaceDoesNotExist
import repo._

// Utilities or Errors
import utilities.errors
import utilities.implicits
```

Since we have **.scalafmt**, to automatically format for everything above. We don't really have to about to worry about these things but just keep this in mind.

## How Scala formatter is configured.

If a new package is added, please add it here relative to where it should be located.
This is file located at the root folder and named `.scalafmt.conf`

```properties
# Import groups
rewrite.imports.groups = [
  # Java Imports
  [
    "java\\..*",
    "javax\\..*"
  ],
  # Scala Imports
  ["scala\\..*"],
  # Play Imports
  ["play\\..*"],
  # Dependency Imports
  [
    "cats\\..*",
    "org\\..*",
    "slick\\..*"
  ],
  # Model Imports
  [
    "domain\\..*",
    "repo\\..*",
    "service\\..*",
    "actors\\..*"
  ],
  # Utility Imports
  [
    "modules\\..*",
    "forms\\..*",
    "utilities\\..*"
  ]
]

```
