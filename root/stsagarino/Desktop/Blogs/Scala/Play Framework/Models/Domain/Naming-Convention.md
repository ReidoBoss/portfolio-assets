# Domain Naming Convention

## `case class` and file names must match

```scala
// Task.scala
case class Task(id:IdTask,name:NameTask)
```

## `case classes` must be PascalCased

```scala
// Task.scala
case class WorkspaceMember // ✅
case class workspaceMember // ❌
case class workspacemember // ❌
...
```

## `case classes` should be singular

```scala
  case class WorkspaceMember // ✅
  case class WorkspaceMembers // ❌
```
