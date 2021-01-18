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
!include https://raw.githubusercontent.com/chrismalek/plantuml-library/master/library/styling-v2.plantuml
!include https://raw.githubusercontent.com/chrismalek/plantuml-library/master/library/library-v2.plantuml


$boundary("client","Client Network"){
    $boundary("erp","ERP System", "PeopleSoft", "Additional Text"){
    $component("batch1", "Data Exporter", "batch", "Additional text")
    $component("smtp", "SMTP Server", "SMTP")
    
    batch1 --> smtp

  
}


@enduml
```