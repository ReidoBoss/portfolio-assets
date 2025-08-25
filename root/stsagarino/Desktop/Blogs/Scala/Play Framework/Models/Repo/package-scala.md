# Repo package.scala

In here, we will put the implicits of the Custom opaque types.

```scala
package object repo:
  import domain.*

  given JdbcType[IdTask] =
    MappedColumnType.base[IdTask, UUID](_.value, IdTask.apply)

  given JdbcType[NameTask] =
    MappedColumnType.base[NameTask, String](_.value, NameTask.apply)

end repo

```
