```plantuml
@startuml

!include library.plantuml


LAYOUT_LEFT_RIGHT
skinparam nodesep 50
skinparam ranksep 20

title Hello title

header hello header
footer hello footer



rectangle "Test Rectangle"

rectangle "Outer Rectangle" {
  rectangle "Rectangle" as rect1
  rectangle "2nd rectange" as rect2
  rect1 --> rect2: Here is some 
}
package "hello" as pack {

}



database "db\nnote" as db1 {

}


Boundary(boundary1, "first boundry")
Boundary(boundary2, "Second Boundry", "type param")

boundary1 -> boundary2


Boundary(boundparent1, "Parent") {

  rectangle "Child" as child1
  database "inside db" as db2
  child1 -> db2
}


BoundaryPackage("bp1", "Boundary Package 1") {
  rectangle "hello inside boundary package"
}


b-->c: Hello
ba*-->ca:hello
bb*....>cb:hello


Actor "Actor 1" as act1
interface "interface" as Inter1
act1 ->Inter1: here is some text



actor actor
agent agent
artifact artifact
boundary boundary
card card
cloud cloud
component component
control control
database database
entity entity
file file
folder folder
frame frame

interface  interface
node node
package package
queue queue

stack stack
rectangle rectangle
storage storage
usecase usecase


@enduml



```


```plantuml
!include library.plantuml

' !include https://raw.githubusercontent.com/chrismalek/plantuml-library/master/library/library.plantuml
' skinparam linetype ortho

Boundary("c.n", "Client Network") {
    rectangle "uploader" as p.u
}

Boundary("gcp", "GCP"){


    Boundary("gcp.proj", "GCP Project") {
        rectangle "Cloud Run API" as gcp.cr.api
        rectangle "Cloud Storage" as gcp.cs.bucket
        rectangle "PUB/SUB" AS gcp.ps.fileEvent
        database "FireStore" as gcp.fs.db {
            rectangle "File Table"
        }

        gcp.cr.api --> gcp.cs.bucket
        gcp.cs.bucket --> gcp.ps.fileEvent: Storage\nNotifications
        gcp.ps.fileEvent --> gcp.cr.api: File Event Listener\nv1/pubsub/fileEvent


    }

}

p.u --> gcp.cr.api: v1/data/inbound - xml files

```



```plantuml
@startuml 
help skinparams
@enduml

```

Define

```plantuml
@startuml

!define SEQUENCE (S,#AAAAAA) Database Sequence
!define TABLE (T,#FFAAAA) Database Table

class USER << TABLE >>
class ACCOUNT << TABLE >>
class UID << SEQUENCE >>
USER "1" -- "*" ACCOUNT
USER -> UID
@enduml


```





```plantuml

@startuml
!procedure defaulttest($x, $y="DefaultY", $z="DefaultZ")
note over Alice
  x = $x
  y = $y
  z = $z
end note
!endprocedure

defaulttest(1, 2, 3)
defaulttest(1, 2)
defaulttest(1)
@enduml

```


```plantuml
@startuml



!unquoted procedure $element($alias, $description="", $label="", $technology="", $size=12, $colour="green")
rectangle $alias as "
<color:$colour><<$alias>></color>
==$label==
//<size:$size>[$technology]</size>//

  $description"
!endprocedure

rectangle "hello containter" as cont {

$element(myalias, "This description is\non several lines", $size=10, $technology="Java", $label="hello label")
}
@enduml

```

----


