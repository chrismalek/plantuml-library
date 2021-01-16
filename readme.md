# Cedar Hills Group PlantUML Diagram Library


- PlantUML standard includes for CHG Diagrams


## Attribution and Thanks


- Many of the ideas here were copied from [https://github.com/RicardoNiepel/C4-PlantUML](https://github.com/RicardoNiepel/C4-PlantUML)


## Usage

Styling

```plantuml
@startuml
!include https://raw.githubusercontent.com/chrismalek/plantuml-library/master/library/styling-v2.plantuml

rectangle "hello world"

@enduml
```



Library
```plantuml
@startuml
!include https://raw.githubusercontent.com/chrismalek/plantuml-library/master/library/styling-v2.plantuml
!include https://raw.githubusercontent.com/chrismalek/plantuml-library/master/library/library-v2.plantuml




$boundary("client","Client Network"){
    $boundary("client.psoft","PeopleSoft System"){
         $component("client.psoft.ae", "Data Exporter", "Application Engine") {
            $component("client.psoft.ae.egress", "Egress Options", "configuration")   
         }
         $component("client.smtp", "SMTP Server", "SMTP")
     }

}
@enduml
```