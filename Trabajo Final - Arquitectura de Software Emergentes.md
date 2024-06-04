**Universidad Peruana de Ciencias Aplicadas**

Ingeniería de Software

Ciclo: VIII

Sección: WS82

Profesor: Royer Edelwer Rojas Malasquez

**INFORME DE TRABAJO FINAL**

**FastPorte**

Integrantes:

* Botello Saldarriaga, Anthony Jean Pierre - U20201B846
* Cierto Espiritu, Abel Angel - U20201B561
* Lévano Cavero, Eduardo Sebastián - U20201C172
* Sabino Ramírez, Rodrigo Alexander - U20201B801
* Villegas Peralta, Branco Alberto - U20201C082

Mayo, 2024

---

# Registro de Versiones del Informe

| Versión | Fecha    | Autor            | Descripción de modificación                                                      |
| ------- | -------- | ---------------- | -------------------------------------------------------------------------------- |
| 1.0     | 12/04/24 | Sebastián Lévano | Creación del proyecto con Markdown Introducción del proyecto Cap I, II, III y IV |
| 1.1.0   | 01/05/24 | Anthony Botello  | Adición del Cap V y del bounded context PersonalData                             |
| 1.1.1   | 02/05/24 | Rodrigo Sabino   | Adicion del bounded context Hiring                                               |
| 1.1.2   | 02/05/24 | Abel Cierto      | Adición del Cap V y del bounded context SearchService                            |
| 1.1.3   | 03/05/24 | Branco Villegas  | Adición del Cap V y del bounded context Location                                 |

---

# Contenido
- [Student Outcome](#student-outcome)
- [Capítulo I: Introducción](#capítulo-i-introducción)
  - [1.1. Startup Profile](#11-startup-profile)
    - [1.1.1. Descripción de la Startup](#111-descripción-de-la-startup)
    - [1.1.2. Perfiles de integrantes del equipo](#112-perfiles-de-integrantes-del-equipo)
  - [1.2. Solution Profile](#12-solution-profile)
    - [1.2.1. Antecedentes y Problemática](#121-antecedentes-y-problemática)
    - [1.2.2. Lean UX Process](#122-lean-ux-process)
        - [1.2.2.1.  Lean UX Problem Statements](#1221-lean-ux-problem-statements)
        - [1.2.2.2 Lean UX Assumptions](#1222-lean-ux-assumptions)
        - [1.2.2.3. Lean UX Hypothesis Statements](#1223-lean-ux-hypothesis-statements)
        - [1.2.2.4. Lean UX Canvas](#1224-lean-ux-canvas)
  - [1.3. Segmentos Objetivo](#13-segmentos-objetivo)
- [Capítulo II: Requirements Elicitation & Analysis](#capítulo-ii-requirements-elicitation--analysis)
  - [2.1. Competidores](#211-competidores)
    - [2.1.1. Análisis Competitivo](#211-análisis-competitivo)
    - [2.1.2. Estrategias y tácticas frente a competidores](#212-estrategias-y-tácticas-frente-a-competidores)
  - [2.2. Entrevistas](#22-entrevistas)
    - [2.2.1. Diseño de entrevistas](#221-diseño-de-entrevistas)
    - [2.2.2. Registro de entrevistas](#222-registro-de-entrevistas)
    - [2.2.3. Análisis de entrevistas](#223-análisis-de-entrevistas)
  - [2.3. Needfinding](#23-needfinding)
    - [2.3.1. User Personas](#231-user-personas)
    - [2.3.2. User Task Matrix](#232-user-task-matrix)
    - [2.3.3. Empathy Mapping](#233-empathy-mapping)
    - [2.3.4. As-is Scenario Mapping](#234-as-is-scenario-mapping)
  - [2.4. Ubiquitous Language](#24-ubiquitous-language)
- [Capítulo III: Requirements Specification](#capítulo-iii-requirements-specification)
  - [3.1. To-Be Scenario Mapping](#31-to-be-scenario-mapping)
  - [3.2. User Stories](#32-user-stories)
  - [3.3. Impact Mapping](#33-impact-mapping)
  - [3.4. Product Backlog](#34-product-backlog)
- [Capítulo IV: Strategic-Level Software Design](#capítulo-iv-strategic-level-software-design)
  - [4.1. Strategic-Level Attribute-Driven Design](#41-strategic-level-attribute-driven-design)
	  - [4.1.1.Design Purpose](#411-design-purpose)
	  - [4.1.2. Attribute-Drive Design Inputs](#412-attribute-drive-design-inputs)
		  - [4.1.2.1. Primary Functionality (Primary User Stories)](#4121-primary-functionality(primary-user-stories))
		  - [4.1.2.2. Quality attribute Scenarios](#4122-quality-attribute-scenarios)
		  - [4.1.2.3. Constraints](#4123-constraints)
	  - [4.1.3. Architectural Drivers Backlog](#413-architectural-drivers-backlog)
	  - [4.1.4. Architectural Design Decisions](#414-architectural-design-decisions)
	  - [4.1.5. Quality Attribute Scenario Refinements](#415-Quality-Attribute-Scenario-Refinements)
  - [4.2. Strategic-Level Domain-Driven Design](#42-strategic-level-domain-driven-design)
	- [4.2.1. EventStorming](#421-eventstorming)
	- [4.2.2. Candidate Context Discovery](#422-candidate-context-discovery)
	- [4.2.3 Domain Message Flows Modeling](#423-domain-message-flows-modeling)
	- [4.2.4 Bounded Context Canvases](#424-bounded-context-canvases)
	- [4.2.5 Context Mapping](#424-bounded-context-canvases)
  - [4.3. Software Architecture](#43-software-architecture)
	- [4.3.1. Software Architecture System Landscape Diagram](#431-software-architecture-system-landscape-diagram)
	- [4.3.2. Software Architecture Context Level Diagrams](#432-software-architecture-context-level-diagrams)
	- [4.3.3 Software Architecture Container Level Diagrams](#433-software-architecture-container-level-diagrams)
	- [4.3.4 Software Architecture Deployment Diagrams](#434-software-architecture-deployment-diagrams)
- [Capítulo V: Tactical-Level Software Design](#capítulo-v-tactical-level-software-design)
  - [5.1. Bounded Context: Hiring](#51-bounded-context-hiring)
    - [5.1.1. Domain Layer](#511-domain-layer)
    - [5.1.2. Interface Layer](#512-interface-layer)
    - [5.1.3. Application Layer](#513-application-layer)
    - [5.1.4. Infrastructure Layer](#514-infrastructure-layer)
    - [5.1.5. Bounded Context Software Architecture Component Level Diagrams](#515-bounded-context-software-architecture-component-level-diagrams)
    - [5.1.6. Bounded Context Software Architecture Code Level Diagrams](#516-bounded-context-software-architecture-code-level-diagrams)
      - [5.1.6.1. Bounded Context Domain Layer Class Diagrams](#5161-bounded-context-domain-layer-class-diagrams)
      - [5.1.6.2. Bounded Context Database Design Diagram](#5162-bounded-context-database-design-diagram)
  - [5.2. Bounded Context: PersonalData](#52-bounded-context-personaldata)
    - [5.2.1. Domain Layer](#521-domain-layer)
    - [5.2.2. Interface Layer](#522-interface-layer)
    - [5.2.3. Application Layer](#523-application-layer)
    - [5.2.4. Infrastructure Layer](#524-infrastructure-layer)
    - [5.2.5. Bounded Context Software Architecture Component Level Diagrams](#525-bounded-context-software-architecture-component-level-diagrams)
    - [5.2.6. Bounded Context Software Architecture Code Level Diagrams](#526-bounded-context-software-architecture-code-level-diagrams)
      - [5.2.6.1. Bounded Context Domain Layer Class Diagrams](#5261-bounded-context-domain-layer-class-diagrams)
      - [5.2.6.2. Bounded Context Database Design Diagram](#5262-bounded-context-database-design-diagram)
  - [5.3. Bounded Context: Location](#53-bounded-context-location)
    - [5.3.1. Domain Layer](#531-domain-layer)
    - [5.3.2. Interface Layer](#532-interface-layer)
    - [5.3.3. Application Layer](#533-application-layer)
    - [5.3.4. Infrastructure Layer](#534-infrastructure-layer)
    - [5.3.5. Bounded Context Software Architecture Component Level Diagrams](#535-bounded-context-software-architecture-component-level-diagrams)
    - [5.3.6. Bounded Context Software Architecture Code Level Diagrams](#536-bounded-context-software-architecture-code-level-diagrams)
      - [5.3.6.1. Bounded Context Domain Layer Class Diagrams](#5361-bounded-context-domain-layer-class-diagrams)
      - [5.3.6.2. Bounded Context Database Design Diagram](#5362-bounded-context-database-design-diagram)
  - [5.4. Bounded Context: SearchService](#54-bounded-context-searchservice)
    - [5.4.1. Domain Layer](#541-domain-layer)
    - [5.4.2. Interface Layer](#542-interface-layer)
    - [5.4.3. Application Layer](#543-application-layer)
    - [5.4.4. Infrastructure Layer](#544-infrastructure-layer)
    - [5.4.5. Bounded Context Software Architecture Component Level Diagrams](#545-bounded-context-software-architecture-component-level-diagrams)
    - [5.4.6. Bounded Context Software Architecture Code Level Diagrams](#546-bounded-context-software-architecture-code-level-diagrams)
      - [5.4.6.1. Bounded Context Domain Layer Class Diagrams](#5461-bounded-context-domain-layer-class-diagrams)
      - [5.4.6.2. Bounded Context Database Design Diagram](#5462-bounded-context-database-design-diagram)
- [Capítulo VI: Solution UX Design](#capítulo-vi-solution-ux-design)
  - [6.1. Style Guidelines](#61-style-guidelines)
	- [6.1.1. General Style Guidelines](#611-general-style-guidelines)
	- [6.1.2. Web, Mobile & Devices Style Guidelines](#612-web-mobile-devices-style-guidelines)
  - [6.2. Information Architecture](#62-information-architecture)
	- [6.2.1. Labeling Systems](#621-labeling-systems)
	- [6.2.2. Searching Systems](#622-searching-systems)
	- [6.2.3. SEO Tags and Meta Tags](#623-seo-tags-and-meta-tags)
	- [6.2.4. Navigation Systems](#624-navigation-systems)
  - [6.3. Landing Page UI Design](#63-landing-page-ui-design)
	- [6.3.1. Landing Page Wireframe](#631-landing-page-wireframe)
	- [6.3.2. Landing Page Mock-up](#632-landing-page-mock-up)
  - [6.4. Applications UX/UI Design](#64-applications-ux-ui-design)
	- [6.4.1. Applications Wireframes](#641-applications-wireframes)
	- [6.4.2. Applications Wireflow Diagrams](#642-applications-wireflow-diagrams)
	- [6.4.3. Applications Mock-ups](#643-applications-mock-ups)
	- [6.4.4. Applications User Flow Diagrams](#644-applications-user-flow-diagrams)
  - [6.5. Applications Prototyping](#65-applications-propotyping)
- [Capítulo VII: Product Implementation, Validation & Deployment](#capítulo-vii-product-implementation-validation-deployment)
  - [7.1. Software Configuration Management](#71-software-configuration-management)
	- [7.1.1. Software Development Environment Configuration](#711-software-development-environment-configuration)
	- [7.1.2. Source Code Management](#712-source-code-management)
	- [7.1.3. Source Code Style Guide & Management](#713-source-code-style-guide-management)
	- [7.1.4. Software Deployment Configuration](#714-software-deployment-configuration)
  - [7.3. Validation Interviews](#73-validation-interviews)
    - [7.3.1. Diseño de Entrevistas](#731-diseño-de-entrevistas)
    - [7.3.2. Registro de Entrevistas](#732-registro-de-entrevistas)
    - [7.3.3. Evaluaciones según heuristicas](#733-evaluaciones-según-heuristicas)
  - [7.4. Video About-the-Product](#74-video-about-the-product)

- [Conclusiones](#conclusiones)
- [Recomendaciones](#recomendaciones)

--- 

# Student Outcome

| Criterio específico                                                                                                                                                                    | Acciones realizadas                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            | Conclusiones                                                                                                                                                                                                                                                                                                                                                         |
| -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Comunica oralmente sus ideas y/o resultados con objetividad a público de diferentes especialidades y niveles jerarquicos, en el marco del desarrollo de un proyecto en ingeniería.     | **Eduardo Sebastián Lévano Cavero**<br>*TB1* <br>Durante el video de exposición se transmitió de manera adecuada la problemática hallada en el sector de transporte de mercadería y como se solucionaría por medio de la implementación de una página web para comunicar a transportistas con personas que requieran de sus servicios. Asimismo, se detallo como esta diseñada la propuesta y su sustentación.<br><br>**Anthony Botello** <br>*TB1* <br>En el vídeo de exposición se indicaron a los competidores, así como también se explicó la matriz DAFO de nuestra organización. Finalmente, se expusieron resultados acerca de las entrevistas realizadas.<br>*TP*<br>En mi presentación audiovisual se describió de manera adecuada cada uno de los elementos que intervienen en el bounded context PersonalData y, de la misma forma, se explicaron los diagramas mostrados.<br><br>**Rodrigo Alexander Sabino Ramirez** <br>*TB1* <br>Durante mi exposición, comuniqué de manera clara y objetiva los resultados de mi proyecto en ingeniería, destacando la fase de Needfinding. Presenté User Personas y una matriz de tareas de usuario, usando herramientas como Empathy Mapping y As-is Scenario Mapping. Además, delineé el escenario futuro de la plataforma propuesta, detallando User Stories, Impact Mapping y un Product Backlog completo.<br>_TP_  <br>La capacidad de comunicar efectivamente en un contexto oral es esencial en ingeniería,  <br>especialmente cuando se trata de explicar y justificar decisiones de diseño como las  <br>presentadas en el capítulo sobre el "Bounded Context: Search Service".  <br>En el capítulo 5 se detalla la implementación de una interfaz de usuario que permite a los  <br>clientes cargar imágenes de productos para transporte y recibir sugerencias automatizadas  <br>sobre los transportistas adecuados.<br>**Abel Angel Cierto Espiritu**<br>*TB1* <br>Durante el desarrollo de este primer avance, comunique de manera eficaz el objetivo del diseño al desarrollar la aplicación web. También, detalle acerca de las funcionalidades primarias  que considero que son importantes y definir los atributos de calidad para una buena aplicación es necesaria. Los constraints nos sirven para tener claro las limitaciones del sistema al momento de desarrollar la aplicación web.<br><br>_TP_<br>La capacidad de comunicar efectivamente en un contexto oral es esencial en ingeniería,  <br>especialmente cuando se trata de explicar y justificar decisiones de diseño como las  <br>presentadas en el capítulo sobre el "Bounded Context: Search Service".  <br>En el capítulo 5 se detalla la implementación de una interfaz de usuario que permite a los  <br>clientes cargar imágenes de productos para transporte y recibir sugerencias automatizadas  <br>sobre los transportistas adecuados.<br><br>**Branco Alberto Villegas Peralta**<br>*TB1*<br>Durante el proyecto, me enfoqué en comunicar nuestros avances y resultados de manera clara y objetiva. Presenté nuestras ideas durante el proceso de Event Storming y facilité discusiones sobre el modelado de flujo de mensajes del dominio. Mi objetivo era asegurarme de que todos los miembros del equipo, independientemente de su especialidad o nivel jerárquico, comprendieran el progreso y las decisiones tomadas en el proyecto.<br><br>_TP_<br>En el avance actual del proyecto, he presentado el bounded context location de "FastPorte" a un público diverso, incluyendo a compañeros de clase, profesores. Durante esta presentación, expliqué claramente el propósito de bounded context y cómo contribuye a mejorar la plataforma. | *TB1*<br>En la exposición de la presente entrega se comunico eficientemente las bases del proyecto desarrollado y el proceso que llevo a corroborar que efectivamente es una solución adecuada para la problemática encontrada. Asimismo, se presentaron las herramientas para utilizadas para las primeras fases de implementación del proyecto y su planteamiento. |
| Comunica en forma escrita ideas y/o resultados con objetividad a público de diferentes especialidades y niveles jerarquicos, en el marco del desarrollo de un proyecto en ingeniería.. | **Eduardo Sebastián Lévano Cavero**<br>*TB1* <br>Se documento con éxito y de manera adecuada la introducción al proyecto, describiendo la problemática con antecedentes, ilustrando las posibles soluciones y como se busca solucionarlo de una manera más eficiente por medio del desarrollo de la presenta investigación.<br><br>**Anthony Botello** <br>*TB1* <br>Se redactaron y documentó información y análisis de nuestros competidores y de la misma forma se evidenciaron las entrevistas realizadas y el análisis de ellas. Por otro lado, se definieron los Primary User Stories y los Quality Attribute Scenarios.<br>*TP*<br>Se agregó el bounded context correspondiente a PersonalData. Para ello, se definieron los elementos que intervienen en cada capa, así como también se diseñó el diagrama de componentes, el diagrama de clases y el diagrama de base de datos para este apartado.<br><br>**Rodrigo Alexander Sabino Ramirez** <br>*TB1* <br>En la elaboración de la primera entrega, me centré en comunicar de manera precisa y objetiva aspectos específicos. Utilizando el concepto de Ubiquitous Language, desarrollé un lenguaje común que facilitó la comprensión entre los miembros del equipo y los stakeholders. Además, identifiqué las limitaciones (Constraints) del proyecto y elaboré un Architectural Drivers Backlog para guiar el diseño arquitectónico. <br><br>**Abel Angel Cierto Espiritu** <br>*TB1* <br>Los resultados de elegir drivers de arquitecturas permite un buen funcionamiento en la escalabilidad y mantenimiento del sistema. Por último los escenarios de los atributos que se requiere refinar permite una mejora continua en la aplicación web.<br><br>_TP_  <br>Se utiliza diagramas de arquitectura y clases, así como descripciones de las entidades y objetos de valor  <br>involucrados en el servicio, lo que facilita a los lectores entender el flujo de datos y las interacciones dentro  <br>del sistema. Esta estructura de comunicación asegura que tanto desarrolladores como administradores no técnicos  <br>puedan apreciar la funcionalidad del sistema y sus implicaciones en el servicio de transporte, destacando la importancia  <br>de una documentación bien estructurada y objetiva en proyectos de ingeniería.<br><br>**Branco Alberto Villegas Peralta**<br>*TB1*<br>Durante el proyecto, utilicé herramientas como EventStorming para explorar y descubrir los contextos relevantes. Luego, modelé los flujos de mensajes del dominio para comprender las interacciones entre los diferentes componentes del sistema. Utilicé Bounded Context Canvases para delinear los límites y responsabilidades de cada contexto, y realicé un mapeo de contextos para visualizar las relaciones entre ellos. Finalmente, documenté nuestra arquitectura de software utilizando varios diagramas, incluidos contexto, contenedor y despliegue, para comunicar nuestra visión de manera efectiva a todas las partes interesadas.<br><br>_TP_ <br>En cuanto a la comunicación escrita, elaboré un documento detallado describiendo el bounded context location para el proyecto "FastPorte".  <br>Este documento, que forma parte del informe de avance, explica en profundidad el detalle del bounded context que se alinea con los objetivos del proyecto y detalla las fuentes de datos y los procesos implementados.                                                                                                                                                                                                                                                                                          | *TB1*<br>En el informe se detalló los aspectos más importantes acerca de la base de la solución propuesta y las herramientas que se usaron para validar la misma. Por otro lado, se incluyeron los diagramas adecuados para cada sección con su respectiva descripción para brindar la mayor cantidad de información.                                                |

---

# Capítulo I: Introducción

## 1.1. Startup Profile

### 1.1.1. Descripción de la Startup

Somos un grupo de estudiantes de la Universidad Peruana de Ciencias Aplicadas y en conjunto identificamos una oportunidad de negocio relacionada con el sector transporte, precisando en el transporte de mercadería.

Nos dimos cuenta de que conseguir transporte de carga, mudanza, envío de paquetes, etc., cuando eres un cliente que necesita de ese servicio, no es muy práctico y sencillo, ya sea por diversas razones: no contar con ese tipo de contactos, no saber dónde buscar, confiabilidad, entre otros. Todo esto hace que la situación se complique cuando un cliente normal, un usuario del día a día que necesite servicios de este rubro, se vea limitado en opciones. Por otro lado, sabemos que existen transportistas independientes que brindan el servicio de movilidad particular ya sea para diferentes rubros y que no tienen la oportunidad de llegar a más personas que las de su propio entorno, lo que hace poco variado su lista de clientes y por ende limita su círculo de trabajo.

Por lo anterior expuesto, hemos creado FastPorte, una plataforma que conecta transportistas de los rubros de carga, mudanza, envío de paquetes, etc. con personas (clientes o personas naturales) que requieren de sus servicios. Funcionará de la siguiente manera: un transportista se registrará con sus datos personales, completará su perfil, incluyendo sus datos personales, documentación tales como: licencia y permisos, tipo de vehículo y tipo de transporte brinda, cuenta bancaria (la cual la aplicación utilizará para depositarle el porcentaje correspondiente al ser contratado por un cliente) y la región en la que labura. Finalmente, esperará a que un cliente lo contacte. Por otro lado, una persona que requiera de transporte se registrará con sus datos personales, buscará a un transportista por el rubro que necesite, podrá visualizar el tipo de transporte y el vehículo usado por dicho usuario transportista, la zona donde brinda el servicio o hasta dónde puede llegar, así como las reseñas de anteriores clientes que tuvieron el servicio con él y de elegirlo, tendrá que rellenar un formulario con los detalles del viaje y hacer el pago del servicio mediante la aplicación, que estará conectada a un servicio de pagos. Finalmente, el transportista acudirá al lugar acordado.

##### MISIÓN

Hacer la búsqueda de servicio de transporte para traslado de mercadería o paquetes, confiable y seguro para cada usuario.

##### VISIÓN

Convertirnos en el servicio de búsqueda de transportes preferido por los peruanos que cada vez supere aún más las expectativas de cada cliente.

### 1.1.2. Perfiles de integrantes del equipo

| Integrante                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         | Eduardo Sebastián Lévano Cavero                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | -------------------------------------------------- |
| Mi nombre es Sebastián, tengo 21 años y soy estudiante de Ingeniería de Software en la Universidad Peruana de Ciencias Aplicadas. Elegí esta carrera porque me fascina crear y diseñar procesos que faciliten procesos complejos. Por ello, cuando tengo un poco de tiempo libre lo uso para relajarme y para aprender más de lo que me apasiona, la programación, se puede decir que es uno de mis hobbies. Además, de la programación también disfruto de jugar vóley, fútbol o algún videojuego con mis amigos. | ![Sebastián Perfil](img/integrantes/sebastian.jpg) |

| Integrante                                                                                                                                                                                                                                                                                                                                                                                                                 | Botello Saldarriaga, Anthony Jean Pierre       |
| -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------- |
| Tengo 21 años y soy estudiante de Ingeniería de Software con conocimientos de matemática y habilidades en programación en el lenguaje C++. Actualmente curso el sétimo ciclo de la carrera y mi meta es ser un profesional destacado el cual rija sus decisiones por sus valores y el bien de la cliente donde labore. Me interesa el desarrollo de la tecnología y los avances que existen en la inteligencia artificial. | ![Anthony Perfil](img/integrantes/anthony.png) |

| Integrante                                                                                                                                                                                                                                                                                                                                                                                           | Sabino Ramírez, Rodrigo Alexander              |
| ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------- |
| Estudiante de sétimo ciclo de la carrera de Ingeniería de Software. Me considero una persona proactiva con pensamiento estratégico, con habilidades en el ámbito de la programación y un gran espíritu investigador. Para este proyecto puedo aportar parte de mi conocimiento adquirido en el curso. Además, de las habilidades blandas tales como el trabajo en equipo, comunicación, entre otras. | ![Rodrigo Perfil](img/integrantes/rodrigo.png) |

| Integrante                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    | Villegas Peralta, Branco Alberto             |
| ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------- |
| Estudiante en el octavo ciclo de la carrera de Ingeniería de Software en la Universidad Peruana de Ciencias Aplicadas, me destaco por mi firme compromiso con la excelencia académica, respaldado por una actitud proactiva y una comunicación efectiva. Esta combinación me capacita para abordar desafíos con determinación y encontrar soluciones eficaces de manera constante. Mi capacidad para mantener la empatía y la tolerancia en situaciones diversas me facilita trabajar de manera colaborativa en equipo y adaptarme sin dificultad a diversos entornos. En términos de habilidades técnicas, poseo sólidos fundamentos en desarrollo web, destacándome en HTML, CSS y JavaScript, lo que me permite crear interfaces atractivas y funcionales. Además, mi dominio versátil en lenguajes de programación como C++, Python, Java, SQL y C# me permite afrontar desafíos desde múltiples perspectivas y encontrar soluciones innovadoras en diferentes contextos. | ![Branco Perfil](img/integrantes/branco.png) |

| Integrante                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       | Cierto Espíritu, Abel Angel              |
| -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------- |
| Estudiante en el octavo ciclo de la carrera de Ingeniería de Software en la Universidad Peruana de Ciencias Aplicadas, me encanta la programación y durante el avance de la carrera adquirí habilidades en lenguajes de programación como C++, C#, Python, TypeScript, Java y SQL para base datos. Asimismo, aprendí acerca de frameworks como Angular, Vue y el desarrollo de aplicaciones móviles en Flutter. En síntesis, estoy dispuesto a ser parte de este equipo de desarrollo y seguir aprendiendo nuevas habilidades en torno a la arquitectura de software emergentes. | ![Abel Perfil](img/integrantes/abel.png) |

## 1.2. Solution Profile

El producto que proponemos como equipo es FastPorte una aplicación que permite conectar a transportistas con personas que requieran de su servicio. Este proceso se llevará a cabo de manera sencilla, accesible y segura, tanto para el cliente como para los transportistas.

### 1.2.1. Antecedentes y Problemática

##### ANTECEDENTES:

Con respecto a nuestra propuesta, nuestra competencia es la siguiente:

- **Trippy Perú:** Herramienta móvil desarrollada en Perú que permite a los padres registrados el poder visualizar la ubicación en tiempo real de la movilidad de sus hijos.
- **MiCargaApp:** Aplicación peruana que conecta a usuarios con clientes que requieran enviar cargas a partir de una tonelada a cualquier ciudad del país. Permite transportar todo tipo de carga, desde mudanzas hasta líquidos peligrosos.
- **MuberZ:** Es una aplicación para mudanzas pequeñas o de productos específicos como un electrodoméstico en Lima. El servicio puede incluir únicamente el traslado, así como el embalaje y el desembalaje.

##### PROBLEMÁTICA

- **What(Qué)**
  En la actualidad existen diversas aplicaciones que ofrecen el servicio de transporte, sin embargo, la mayoría de estas están enfocadas en el ámbito urbano como: Uber, Didi, Cabify, etc. Nosotros proponemos una solución para el ámbito de mercadería o transporte de carga. De esta manera, facilitaremos tanto para el transportista como el cliente la forma de contactar y gozar de un buen servicio.
- **When(Cuando)**
  La problemática surge al momento en que alguien busca un medio de transporte para el rubro de transporte de mercadería o carga. En muchas ocasiones, solo encontramos servicios de taxi que ofrecen diferentes aplicaciones. Sin embargo, no sabemos dónde buscar cuando requerimos de transporte más grande o de mayor capacidad, ya sea para transportar mercadería en cajas o cantidades mucho más grandes de carga de algún tipo.
- **Where(Dónde)**
  Nuestro servicio se dará a nivel nacional en un futuro, sin embargo, por ahora, y para comenzar, nos consolidaremos en la capital y luego iremos creciendo hacia otras regiones para cumplir con nuestra visión como startup.
- **Who(Quién)**
  **FastPorte** está dirigida a todas las personas que deseen encontrar de manera más rápida y confiable un servicio de transporte de carga según la disponibilidad. Por otra parte, también está dirigido a todos los transportistas que quieran brindar este servicio, ampliar su zona de servicio y atraer a más clientes potenciales a contratarlos para así obtener más ingresos.
- **Why(Por qué)**
  Como mencionamos anteriormente, esta propuesta se plantea por la necesidad de una plataforma en la cual los transportistas particulares ligados al rubro de transporte de carga puedan ofrecer sus servicios y que las personas o clientes puedan ver que tienen opciones y elegir el tipo de servicio que requieren. Además, porque será un espacio donde los trabajadores que se dediquen a transportar ya sean carga, mercadería, paquetes, etc., de forma particular podrán aumentar su público y por ende obtener más ganancias.
- **How(Cómo)**
  Funcionará de la siguiente manera: un transportista se registrará con sus datos personales, completará su perfil, incluyendo sus datos personales, documentación tales como: licencia y permisos, tipo de vehículo y tipo de transporte brinda, cuenta bancaria (la cual la aplicación utilizará para depositarle el porcentaje correspondiente al ser contratado por un cliente), el lugar por donde circula y hasta que trayecto puede llegar, finalmente esperará a que un cliente lo contacte. Por otro lado, una persona que requiera de transporte se registrará con sus datos personales, buscará a un transportista por el rubro que necesite, podrá visualizar el tipo de transporte y el vehículo usado por dicho usuario transportista, la zona donde brinda el servicio o hasta dónde puede llegar, así como las reseñas de anteriores clientes que tuvieron el servicio con él y de elegirlo, tendrá que rellenar un formulario con los detalles del viaje y hacer el pago del servicio mediante la aplicación, que estará conectada a una pasarela de pagos.
- **How much(Cuánto)**
  En el Perú son pocas las clientes que compiten directamente con nosotros ya que la mayoría de las aplicaciones de transporte están enfocadas solo a la mudanza o al transporte de carga pesada mayor a una tonelada. Por lo tanto, seríamos el único startup que abarque el área de transporte de carga sin limitaciones, desde solicitar un miniván para transportar un par de cajas hasta solicitar transporte de carga pesada para mercadería, encargos pesados, etc.

### 1.2.2. Lean UX Process

#### 1.2.2.1. Lean UX Problem Statements

El servicio de transporte es una actividad fundamental cuando eres un empresario y requieres de este medio para trasladar mercadería o productos. Sin embargo, no solo está relacionado a empresarios, pues podría ser una persona natural quien requiera de este servicio para el transporte de cajas o carga pesada. Hemos observado que existen plataformas que nos brindan información de servicio de transporte, sin embargo, están relacionadas a un sector en específico siendo más específicos en el área urbana. Además, existe una preocupación sobre la confiabilidad y seguridad de la información proporcionada. ¿Cómo podemos desarrollar una plataforma integral que abarque el sector de transporte de carga, proporcionando a empresarios, personas naturales y profesionales de diversos campos un acceso centralizado para adquirir servicios de transporte? ¿Cómo garantizamos la seguridad y confiabilidad de la información ofrecida en esta plataforma?

Los trabajadores del sector transporte son clave para distintos negocios, emprendimientos y clientes, pero es sabido que muchos de ellos suelen tener trabajos eventuales independientes como transportistas de carga, movilidad de personas, servicio de mudanza, etc. Hemos observado que no hay un lugar confiable en el que este grupo de trabajadores pueda ofrecer sus servicios y así ganar un extra o quizá aumentar su demanda y redes de contacto. ¿Cómo podemos empoderar a los trabajadores del sector transporte, que a menudo realizan trabajos independientes, para que ofrezcan sus servicios de manera confiable y generen ingresos adicionales? ¿Qué herramientas y plataformas podríamos desarrollar para facilitar la conexión entre estos trabajadores y un público más amplio, asegurando al mismo tiempo la confianza y calidad en los servicios ofrecidos?

#### 1.2.2.2. Lean UX Assumptions

##### CARACTERÍSTICAS

- Registro de usuarios identificados correctamente (transportista y cliente).
- Visualización de los perfiles de los transportistas. En este apartado deberán subir información relevante para el servicio, así como también fotos de su vehículo.
- Los clientes podrán ver la reputación del transportista que será puntuada mediante estrellas, así como también leerán comentarios recibidos por anteriores clientes que usaron su servicio.
- Para realizar el contrato, los clientes tendrán que llenar un formulario con los siguientes datos del servicio: fecha, hora, lugar, tipo de servicio, origen, destino, cantidad de personas o peso, el monto a pagar y una descripción adicional.
- Se le notificará al transportista de sus solicitudes de servicio y él decidirá si aceptarlas o no.
- Pago del servicio de forma online. (El pago lo recibirá el transportista una vez terminado el trabajo)
- Ver el historial de servicios brindados (transportista) y el historial de servicios contratados (cliente)
- Un foro para formar una comunidad.
- Ver la ubicación en tiempo real del transporte usando la tecnología GPS.
- Elegir el tipo de transporte que necesite el cliente usando filtros.

##### BUSINESS OUTCOMES

- Aumentar las opciones del cliente al elegir el transporte que solicitan.
- Dar seguridad a los usuarios en el proceso de pago y en la elección del transportista.
- Que el transportista reciba un pago seguro y disfrute de nuestro servicio.
- Fomentar el uso de nuestro servicio para conseguir más usuarios.

##### BENEFICIOS DEL USUARIO

- Para el transportista, aumentar la cantidad de personas a las que brinde su servicio y por lo tanto obtener más ganancias.
- Para el cliente, aumentar sus opciones de transporte, así como también poder elegir el servicio referenciándose de los comentarios y puntuación del transportista.
- Para el cliente, evitar la búsqueda del servicio de transporte que necesita en diferentes sitios en internet.
- Para el cliente, estar al tanto del transporte que contrató usando GPS.
- Compartir su experiencia y opinión en un foro.

##### BUSINESS ASSUMPTIONS

- Creemos que los usuarios quieren un lugar seguro donde el transportista y el cliente puedan brindar y adquirir el servicio respectivamente.
- Los transportistas quieren un lugar donde llegar a más personas y aumentar sus ingresos mediante la prestación de sus servicios.
- Nuestros usuarios quieren que la información brindada sea verídica y que el pago sea seguro.
- Estas necesidades se pueden resolver con una aplicación que conecte transportistas con clientes para que adquieran un servicio seguro y de acuerdo con sus necesidades.
- Los usuarios iniciales son transportistas que brinden sus servicios de transporte relacionado a un rubro en particular.
- El valor número 1 que una persona quiere de la aplicación es que sea rápida, confiable y que dé la suficiente seguridad cuando contrate el servicio de transporte.
- Obtendremos clientes a través de anuncios que saldrán cuando una persona busque algún servicio de transporte en internet o cuando un transportista busque en algún sitio web a personas que requieran de su servicio.
- Obtendremos ingresos a través de publicidad no invasiva dentro de la aplicación y mediante una comisión cuando haya algún pago de servicio.
- Mi competencia principal en el mercado será los startups que están relacionadas con el transporte, sin embargo, estas están dirigidas a un público en específico.
- Los venceremos debido a que abarcamos de manera completa el rubro de transporte de carga pesada y mercadería y a la publicidad establecida en sitios de internet claves.
- El mayor riesgo que le puede suceder a la aplicación es que la información sobre un transportista sea errónea o falsa y por lo tanto cause problemas con el cliente cuando se preste el servicio.
- Resolveremos esto cuidando y organizando mejor la información, así como también pidiendo pruebas de la información que un transportista proporciona.

##### USER ASSUMPTIONS

- ¿Quién es el usuario?  
  Las personas que brinden servicio de transporte relacionado a algún rubro y las personas entre 20 a 40 años que requieran de este servicio.
- ¿Dónde encaja nuestro producto en su trabajo o vida?
  Para los transportistas encaja en su trabajo y en el caso de los clientes, en su vida.
- ¿Qué problemas tiene nuestro producto y cómo se pueden resolver?
  Al ser relativamente nuevo, nuestro producto puede enfrentar problemas relacionados a la experiencia de usuario, ya que tendrá varias opciones. Sin embargo, leyendo los comentarios de la comunidad con respecto al producto se podría solucionar de tal manera que actualicemos y optimicemos estas características.
- ¿Cuándo y cómo es usado nuestro producto?
  Nuestro producto será de fácil uso y será usado cuando un cliente necesite del servicio de transporte en el ámbito de carga pesada o transporte de mercadería, siempre y cuando haya un transportista registrado que haga tal servicio.
- ¿Qué características son importantes?
  Que sea de fácil uso, que los call to action sean sencillos de entender y que sea de gran utilidad tanto para el transportista como para el cliente.
- ¿Cómo debe verse nuestro producto y cómo debe comportarse?
  Debe tener una interfaz amigable, sencilla y con los colores adecuados. Tendrá un diseño que trasmita confianza, seriedad y seguridad.

#### 1.2.2.3. Lean UX Hypothesis Statements

-	**Creemos** que proporcionar un medio donde se pueda brindar servicios de transporte, puede aumentar la solicitud de los transportistas que cuentan con poca demanda y ampliar su zona de trabajo
**Sabremos** que hemos tenido éxito
**Cuando** la demanda e ingresos generados por dichos transportistas aumentan y sobrepasan la cantidad aproximada que solían generar antes de brindar sus servicios a través de la plataforma.

-	**Creemos** que proporcionar una plataforma donde una persona, que necesite el servicio de transporte, pueda buscar ofertas de servicio mediante una amplia diversidad de vehículos ofrecidos por los transportistas registrados, y generar confianza en el servicio brindado
**Sabremos** que hemos tenido éxito
**Cuando** el porcentaje de satisfacción de los clientes se vea reflejada en las estadísticas, reseñas y calificaciones que estos brinden a los transportistas una vez recibido el servicio contratado.

-	**Creemos** que utilizar el GPS para rastrear el transporte en tiempo real mejorará la confianza y seguridad de los clientes
**Sabremos** que hemos tenido éxito
**Cuando** la calificación promedio de los transportistas aumente en un 20% en comparación con la línea de base previa a la implementación del GPS.

-	**Creemos** que mostrar la reputación, en base a reseñas y calificaciones, de los transportistas aumentará la confianza y respaldará la fiabilidad en el servicio que brindan
**Sabremos** que es cierto
**Cuando** los ingresos mensuales y la frecuencia de solicitud de servicios por parte del grupo de transportistas con mejor calificación aumenten en un 30% en comparación con los transportistas con una calificación promedio o aquellos que no cuenten con ninguna calificación.

-	**Creemos** que mostrar la reputación de los transportistas aumentará los contratos de aquellos con mejor calificación
**Sabremos** que es cierto
**Cuando** los ingresos mensuales del grupo de transportistas con mejor calificación aumenten en un 35% en comparación con la línea de base previa a la implementación de la reputación.

-	**Creemos** que nuestro producto aumentará las ganancias mensuales de los transportistas independientes
**Sabremos** que estamos en lo correcto
**Cuando** los ingresos reportados por los transportistas el segundo mes de uso aumente en 15%.

-	**Creemos** que tener anuncios en internet, aumentará el número de nuevos de usuarios
**Sabremos** que es cierto 
**Cuando** notemos un incremento mensual del 10% de nuevos usuarios

-	**Creemos** que nuestra aplicación perdurará en el mercado 
**Sabremos** que es cierto 
**Cuando** los usuarios sigan evaluando y calificando el funcionamiento de la aplicación de manera regular durante un periodo de al menos 2 años.

-	**Creemos** que la implementación de una función de seguimiento de rutas personalizadas aumentará la retención de usuarios.
**Sabremos** que es cierto 
**Cuando** observemos que el porcentaje de usuarios que utilizan esta función al menos una vez al mes aumenta en un 15% en   comparación con el mes anterior.

-	**Creemos** que simplificar el proceso de pago y ofrecer opciones de pago adicionales mejorará la satisfacción del usuario.
**Sabremos** que que hemos tenido éxito
**Cuando** la encuesta de satisfacción del usuario muestre un aumento del 20% en la puntuación de satisfacción en los dos meses siguientes a la implementación de estas mejoras.

#### 1.2.2.4. Lean UX Canvas

| **LEAN UX CANVAS**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     | **Lean UX Canvas**                                                                                                                                                                                                                                                                                                                                                                                                                                | *Fecha: 04/04/2024* *Iteración: 1*                                                                                                                                                                                                                                                                                                                                                                                                                                            |
| ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **1. Business problem**<br><br>Hemos identificado una necesidad en el mercado de transporte, donde los usuarios buscan opciones seguras y confiables para diferentes tipos de servicios de transporte, como transporte de carga, transporte de mercaderías, carga pesada y más. Al mismo tiempo, existe una oportunidad para trabajadores interesados en ofrecer sus servicios de transporte en una plataforma confiable y rentable.<br><br>¿Cómo podemos desarrollar una plataforma integral que abarque todos los sectores de transporte, proporcionando a empresarios, personas naturales y profesionales de diversos campos un acceso centralizado para adquirir servicios de transporte?<br>                                                                                                                                                                                                                                                                                                                      | **5.Solutions**<br><br>- Aplicación que conecta transportistas con personas que requieran de sus servicios.<br>- Un proceso riguroso de registro para transportistas, que incluye la verificación de documentos y papeles de su vehículo.<br>- Ayuda a los transportistas independientes a aumentar sus ingresos y a encontrar clientes que necesitan transporte.                                                                                 | **2.Business Outcomes**<br>- Expandir las opciones de transporte para los usuarios.<br>- Garantizar la seguridad de los usuarios en el proceso de pago.<br>- Garantizar que los transportistas reciban pagos seguros y protegidos.<br>- Fomentar el uso de nuestro servicio para conseguir más usuarios.                                                                                                                                                                      |
| **3. User**<br><br>Nuestro producto tiene dos tipos de usuarios:<br><br>- Personas con edades comprendidas entre 20 y 40 años que requieren servicios de transporte seguro para diferentes necesidades, como transporte de carga, transporte de mercadería, etc.<br>- Personas que ofrecen servicios de transporte y desean obtener ingresos adicionales utilizando la plataforma                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |                                                                                                                                                                                                                                                                                                                                                                                                                                                   | **4. User outcomes & benefits**<br><br>- Para el transportista, aumentar la cantidad de personas a las que brinde su servicio. Así podrá obtener más ganancias y mayores oportunidades de generación de ingresos a través de la plataforma.<br>- Para el cliente, aumentar sus opciones de transporte.  Para elegir entre una amplia gama de servicios de transporte seguros y confiables, informándose a través de comentarios y puntuaciones de los transportistas.<br>     |
| **6. Hypotheses**<br><br>- Creemos que proporcionar un medio donde se pueda brindar diversos servicios relacionados al transporte, puede aumentar la solicitud de los transportistas que cuentan con poca demanda y ampliar su zona de trabajo. **Sabremos** que hemos tenido éxito **cuando** la demanda e ingresos generados por dichos transportistas aumentan y sobrepasan la cantidad aproximada que solían generar antes de brindar sus servicios a través de la plataforma.<br>- **Creemos** que proporcionar una plataforma donde una persona, que necesite el servicio de transporte, pueda buscar ofertas de servicio mediante una amplia diversidad de vehículos ofrecidos por los transportistas registrados, y generar confianza en el servicio brindado. **Sabremos** que hemos tenido éxito **cuando** el porcentaje de satisfacción de los clientes se vea reflejada en las estadísticas, reseñas y calificaciones que estos brinden a los transportistas una vez recibido el servicio contratado.<br> | **7. ¿Qué es lo más importante que      necesitamos aprender primero?**<br> <br>- Necesitamos aprender a implementar métodos efectivos que garanticen de los documentos de los transportistas y evaluar su disposición para cumplir con los requisitos de registro. <br>- Necesitamos aprender a implementar métodos de pago seguros y realizar encuestas o pruebas de usuario para evaluar la disposición de los clientes para utilizarlos. <br> | **8. ¿Cuál es la menor cantidad de trabajo que debemos hacer para aprender la siguiente cosa más importante?**<br><br>- Realizar entrevistas breves con un pequeño grupo representativo de clientes para comprender si prefieren nuestro método de conectar transportistas con aquellos que necesitan sus servicios.<br>- Realizar encuestas breves a un grupo inicial de transportistas para conocer su opinión sobre la idea y si propondrían cambios en algún aspecto.<br> |

## 1.3. Segmentos Objetivo
Dentro de nuestro segmento objetivo, hemos identificado dos grupos de usuarios distintos:
##### Segmento Clientes
- Personas que residen en todo el territorio peruano, lima y provincias, y que necesitan servicios de transporte de mercadería, carga pesada, entre otros.
- Se dirige tanto a hombres como a mujeres cuyas edades están en el rango de 20 a 40 años.
**Características clave:**
- Preocupados por la seguridad y confiabilidad de los servicios de transporte.
- Buscan soluciones convenientes y eficientes para satisfacer sus necesidades de transporte.
- Buscan una amplia gama de ofertas en transporte para así poder elegir la que más se adapte a su necesidad.
**Necesidades y deseos:**
- Acceso a una amplia variedad de opciones de transporte.
- Garantía de seguridad en los servicios y transacciones.
- Facilidad en el proceso de reserva y pago.
- Información detallada sobre los transportistas y sus servicios, incluyendo calificaciones y comentarios.
##### Segmento Transportistas
- Personas mayores de 25 años que ofrecen servicios de transporte de forma independiente y cumplen con los requisitos legales para brindar estos servicios.
- Interesados en ganar ingresos adicionales y aumentar su visibilidad para atraer a más clientes.
**Características clave:**
- Poseen vehículos adecuados y cumplen con la documentación requerida para operar legalmente.
- Buscan oportunidades flexibles para generar ingresos.
- Valoran la retroalimentación positiva y la construcción de una buena reputación en el mercado.
**Necesidades y deseos:**
- Acceso a una plataforma confiable para ofrecer sus servicios de transporte.
- Oportunidades para recibir reservas y aumentar sus ingresos.
- Mecanismos para asegurar el pago oportuno por sus servicios.
- Exposición a una base de clientes más amplia y oportunidades de crecimiento.

---

# Capítulo II: Requirements Elicitation & Analysis
## 2.1. Competidores
### 2.1.1. Análisis Competitivo

![Analisis Competitivo - Tabla](img/Capitulo_2/Competidores/Imagen1.png)

### 2.1.2. Estrategias y tácticas frente a competidores

![Analisis Competitivo - Tabla](img/Capitulo_2/Competidores/Imagen2.png)

## 2.2. Entrevistas
### 2.2.1. Diseño de entrevistas
**Preguntas al segmento cliente:**
-	¿Cuál es tu nombre, qué edad tienes y a qué te dedicas?
-	¿Qué opinas de los servicios de transporte de mercadería en el Perú?
-	¿Alguna vez contactaste con un servicio de traslado de productos? ¿Por qué medio obtuviste el contacto?
    - SÍ ¿Tuviste algún problema con el servicio de traslado de productos que contactaste? ¿Qué pasó? ¿Cómo hizo para solucionarlo?
    - NO ¿Por qué razón?
-	 ¿Qué tan complicado se te hace encontrar un servicio de traslado de productos?
-	 ¿Qué tan a menudo necesitas un servicio de traslado de productos?
-	¿A quién recurres cuando necesitas el servicio de traslado de tus productos?
-	¿Qué tan importante consideras el estar pendiente de la ubicación de tu producto en tiempo real?
-	¿Considera importante conocer el modelo y el año del vehículo que va a trasladar su producto?
-	¿Qué opina acerca de una aplicación que te facilite encontrar un servicio de traslado de productos?
    - El entrevistador explica acerca de la aplicación
-	¿Estaría dispuesto a probarla? ¿Por qué?
-	¿Qué cree que podría mejorar o añadir a nuestra propuesta?

**Preguntas al segmento transportista:**
-	¿Cuál es tu nombre, qué edad tienes y a qué te dedicas?
-	¿Cuánto tiempo lleva trabajando en este empleo o de esta forma?
-	¿Qué opinas de los servicios de transporte de mercadería en el Perú? 
-	¿Qué tan frecuente recibe pedidos para transportar productos? aproximadamente 3-4 veces a la semana
-	¿Hacer servicios de transporte es tu única forma de ingresos o de qué otra forma te ganas el dinero? actualmente si
-	¿Cuánto es lo que gana normalmente en un día de trabajo? entre 100 y 150 depende de los envíos, pero hay varios días que no hay pedidos que movilizar
-	¿De qué manera haces conocer a las demás personas de tus servicios? mayormente me contactan personas que algún contacto les recomendó, también me encuentro en páginas en Facebook
-	¿Tuvo algún inconveniente con sus clientes? ¿Qué pasó? ¿Cómo solucionaron el problema? algunas veces existe el tráfico y algunos clientes no son tan pacientes como otros. pero siempre intento resolver conversando las cosas. 
-	¿Qué opinas de poder contar con una aplicación que te permita encontrar clientes que necesiten de tus servicios como transportista? muy buena ya que es un método en el cual recibiría más clientes. por ejemplo, el servicio de pedido de taxis online cambio totalmente ese rubro y lo convirtió más fácil y seguro para el taxista y el cliente.
    - El entrevistador explica acerca de la aplicación
-	¿Estaría dispuesto a probar nuestra aplicación? ¿Por qué?
-	¿Qué cree que podría mejorar o añadir a nuestra propuesta?


### 2.2.2. Registro de entrevistas
#### Entrevista N° 1
| ![Entevista 1 - Evidencia](img/Capitulo_2/Entrevistas/Entrevista1.jpg)                                                                                        |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <u>**Datos del entrevistado**</u> <br> Nombre y apellidos: Carlos Alipio Sánchez Salazar <br>	Edad: 19 <br>	Distrito: Carabayllo <br>	Segmento: Transportista |

#### Entrevista N° 2
| ![Entevista 2 - Evidencia](img/Capitulo_2/Entrevistas/Entrevista2.png)                                                                       |
| -------------------------------------------------------------------------------------------------------------------------------------------- |
| <u>**Datos del entrevistado**</u> <br> Nombre y apellidos: Edgard Miranda Lloclla <br>	Distrito: Sullana, Piura <br>	Segmento: Transportista |

#### Entrevista N° 3
| ![Entevista 3 - Evidencia](img/Capitulo_2/Entrevistas/Entrevista3.png)                                                                                           |
| ---------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <u>**Datos del entrevistado**</u> <br> Nombre y apellidos: Diego Seminario Centeno <br> Edad: 24 años<br>	Distrito: Cercado de Lima <br>	Segmento: Transportista |

#### Entrevista N° 4
| ![Entevista 4 - Evidencia](img/Capitulo_2/Entrevistas/Entrevista4.png)                                                                                       |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| <u>**Datos del entrevistado**</u> <br> Nombre y apellidos: Teodoro Geiner Liberato Villanueva <br> Edad: 52 años<br>	Distrito: Huacho <br>	Segmento: Cliente |

#### Entrevista N° 5
| ![Entevista 5 - Evidencia](img/Capitulo_2/Entrevistas/Entrevista5.png)                                                                                                     |
| -------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <u>**Datos del entrevistado**</u> <br> Nombre y apellidos: Alexandro Daniel Villarruel Mandujano <br> Edad: 24 años<br>	Distrito: Villa El Salvador <br>	Segmento: Cliente |

#### Entrevista N° 6
| ![Entevista 6 - Evidencia](img/Capitulo_2/Entrevistas/Entrevista6.png)                                                                               |
| ---------------------------------------------------------------------------------------------------------------------------------------------------- |
| <u>**Datos del entrevistado**</u> <br> Nombre y apellidos: Ítalo Paolo Sabino Ramírez <br> Edad: 23 años<br>	Distrito: Callao <br>	Segmento: Cliente |

### 2.2.3. Análisis de entrevistas
![Analisis de entrevistas - Tabla](img/Capitulo_2/Entrevistas/Analisis.png)

## 2.3 Needfinding

### 2.3.1 User Persona

###### _User Persona Manuel Segura, usuario Cliente_

![User Persona Cliente](img/Capitulo_2/Needfinding/1.png)

###### _User Persona Manuel Segura, usuario Transportista_

![User Persona Transportista](img/Capitulo_2/Needfinding/2.png)
### 2.3.2 User Task Matrix
###### _User Task Matrix del usuario cliente_

|                           **Tareas**                            | **Frecuencia** | **Importancia** |
| :-------------------------------------------------------------: | :------------: | :-------------: |
|  Contactar con un transportista para hacer uso de transporte.   |    Siempre     |      Alta       |
|           Saber cuál será el precio por el transporte           |    Siempre     |      Alta       |
|   Conocer los tipos de transporte que ofrece el transportista   |    Siempre     |      Alta       |
|                Hacer un seguimiento del producto                |  Casi Siempre  |      Alta       |
|  Mostrar los transportistas para brindarle opciones al usuario  |  Casi Siempre  |      Media      |
|               Calificar el servicio con estrellas               | Algunas veces  |      Media      |
| Recomendar el servicio proporcionado por medio de un comentario |   Casi nunca   |      Baja       |
###### _User Task Matrix del usuario transportista_

|                         Tareas                         | Frecuencia | Importancia |
| :----------------------------------------------------: | :--------: | :---------: |
|                Contactar con el cliente                |  A menudo  |    Alta     |
|  Acordar cuál será el producto por llevar y el tamaño  |  A menudo  |    Alta     |
|            Acordar el precio con el cliente            |  Siempre   |    Alta     |
|       Establecer el día de llegada del producto        |  Siempre   |    Alta     |
|          Pactar cuál será el lugar de destino          |  Siempre   |    Alta     |
|                Transportar el producto                 |  Siempre   |    Alta     |
| Evidenciar que el producto ha sido entregado con éxito |  A menudo  |    Media    |
|                 Cobrar por el servicio                 |  Siempre   |    Alta     |
|          Atender las solicitudes del cliente           |  Siempre   |    Alta     |
### 2.3.3 Empathy Mapping

###### *Empathy Mapping del usuario cliente*

![Empathy Mapping Cliente](img/Capitulo_2/Needfinding/3.png)

###### *Empathy Mapping del usuario transportista*

![Empathy Mapping Transportista](img/Capitulo_2/Needfinding/4.png)
### 2.3.4. As-is Scenario Mapping. 

###### *As-is Scenario Mapping del usuario cliente*

![As-is Scenario Mapping Cliente](img/Capitulo_2/Needfinding/5.png)
###### *As-is Scenario Mapping del usuario transportista*

![As-is Scenario Mapping Transportista](img/Capitulo_2/Needfinding/6.png)
## 2.4. Ubiquitous Language.

- **Carrier (Transportista)**

Individuo o empresa que proporciona servicios de transporte.

- **Client (Cliente)** 

Individuo o empresa que requiere servicios de transporte.

- **Service type (Tipo de servicio)**

Clasificación de los servicios de transporte ofrecidos, como carga, mudanza, movilidad, etc.

- **Carrier profile (Perfil de transportista)**

Información detallada proporcionada por los transportistas al registrarse, incluyendo datos personales, documentación, tipo de vehículo y servicios ofrecidos.

- **Client profile (Perfil de cliente)** 

Información proporcionada por los clientes al registrarse, incluyendo detalles personales e información de viajes anteriores.

- **Trip form (Formulario de viaje)** 

Formulario completado por el cliente con los detalles del viaje, incluyendo origen, destino, fecha, hora, tipo de carga, etc.

- **Payment (Pago del servicio)**

Proceso mediante el cual el cliente realiza el pago por el servicio de transporte a través de la plataforma FastPorte, utilizando un servicio de pago integrado.

- **Reviews (Reseñas)**

Comentarios y calificaciones dejados por clientes anteriores sobre su experiencia con un transportista específico, ayudando a otros clientes a tomar decisiones informadas.

- **Service area (Zona de servicio)**

Área geográfica donde un transportista está disponible para proporcionar servicios, especificada en su perfil.

- **Service contract (Contrato - Acuerdo de servicio)**

Acuerdo entre el cliente y el transportista cuando se confirma un viaje, estableciendo las condiciones y términos de la prestación del servicio.

- **Vehicle (Vehículo)**

Modo de transporte utilizado por los transportistas para proporcionar servicios.

- **License and permits (Licencia y permisos)**

Documentación legal requerida para que los transportistas operen sus vehículos y proporcionen servicios de transporte.

- **Rates (Tarifas)**

Precios cobrados por los transportistas por sus servicios de transporte.

- **Trip confirmation (Confirmación de viaje)**

Confirmación de una reserva de viaje realizada por el cliente con un transportista.

- **Service status (Estado del servicio)**

Estado actual del servicio de transporte, indicando si está pendiente, en progreso o completado.

- **Transportation request (Solicitud de transporte)**

Solicitud realizada por el cliente para servicios de transporte.

- **Service history provided (Historial de servicios brindados)**

Registro de servicios proporcionados por el transportista.

- **Service history contracted (Historial de servicios contratados)**

Registro de servicios contratados por el cliente.

- **Customer rating (Calificación del cliente)**

Calificación proporcionada por los transportistas para los clientes basada en su comportamiento e interacción durante el viaje.

- **Carrier rating (Calificación del transportista)**

Calificación proporcionada por los clientes para los transportistas basada en su desempeño y calidad del servicio.

- **Trip cancellation (Cancelación de viaje)**

Cancelación de un viaje reservado por el cliente con un transportista.

- **Invoicing (Facturación)**

Emisión de facturas por los servicios de transporte proporcionados.

- **Trip alerts (Alertas de viaje)**

Notificaciones sobre detalles o actualizaciones de viaje enviadas a clientes o transportistas.

- **Shipment tracking (Rastreo de envíos)**

Seguimiento de la ubicación y estado de las mercancías transportadas durante el tránsito.

- **Service tracking (Seguimiento del servicio)**

Seguimiento del progreso y estado de un servicio de transporte.

- **Customer service (Servicio de atención al cliente)**

Soporte y asistencia proporcionada a los clientes con respecto a los servicios de transporte.

- **Availability calendar (Calendario de disponibilidad)**

Calendario que muestra la disponibilidad de los transportistas para proporcionar servicios de transporte.

---

# Capítulo III: Requirements Specification 
## 3.1. To-Be Scenario Mapping. 

###### _To-Be Scenario Mapping del usuario cliente_

![To Be Scenario Mapping Cliente](img/Capitulo_2/Needfinding/7.png)
###### _To-Be Scenario Mapping del usuario transportista_

![To Be Scenario Mapping Transportista](img/Capitulo_2/Needfinding/8.jpg)

## 3.2. User Stories. 

##### _Desarrollo de los User Stories_
![HU-001](img/Capitulo_3/User_Stories/1.png)
![HU-002](img/Capitulo_3/User_Stories/2.png)
![HU-003](img/Capitulo_3/User_Stories/3.png)
![HU-004](img/Capitulo_3/User_Stories/4.png)
![HU-005](img/Capitulo_3/User_Stories/5.png)
![HU-006](img/Capitulo_3/User_Stories/6.png)
![HU-007](img/Capitulo_3/User_Stories/7.png)
![HU-008](img/Capitulo_3/User_Stories/8.png)
![HU-009](img/Capitulo_3/User_Stories/9.png)
![HU-010](img/Capitulo_3/User_Stories/10.png)
![HU-011](img/Capitulo_3/User_Stories/11.png)
![HU-012](img/Capitulo_3/User_Stories/12.png)
![HU-013](img/Capitulo_3/User_Stories/13.png)
![HU-014](img/Capitulo_3/User_Stories/14.png)
![HU-015](img/Capitulo_3/User_Stories/15.png)
![HU-016](img/Capitulo_3/User_Stories/16.png)
![HU-017](img/Capitulo_3/User_Stories/17.png)
![HU-018](img/Capitulo_3/User_Stories/18.png)
![HU-019](img/Capitulo_3/User_Stories/19.png)
![HU-020](img/Capitulo_3/User_Stories/20.png)
![HU-021](img/Capitulo_3/User_Stories/21.png)
![HU-022](img/Capitulo_3/User_Stories/22.png)
![HU-023](img/Capitulo_3/User_Stories/23.png)
![HU-024](img/Capitulo_3/User_Stories/24.png)



### EPICS
Las Epics que identificamos son las siguientes:

###### _Desarrollo de las Epics_

| Código | Título                            | Epic                                                                                                     |
| ------ | --------------------------------- | -------------------------------------------------------------------------------------------------------- |
| EP01   | Registro de información           | Como usuario deseo registrarme dentro de la aplicación para comenzar a usarla.                           |
| EP02   | Registro de información adicional | Como usuario deseo poder almacenar información adicional para recibir/brindar un servicio personalizado. |
| EP03   | Búsqueda de servicios disponibles | Como cliente deseo tener un resultado de búsqueda preciso de los servicios y vehículos disponibles.      |
| EP04   | Contrato del servicio             | Como usuario quiero rellenar la información necesaria para solicitar un servicio.                        |
| EP05   | Seguimiento del servicio          | Como cliente quiero conocer la ubicación del transporte.                                                 |
| EP06   | Informes sobre el servicio        | Como cliente deseo hacer un reporte del servicio dentro de la aplicación.                                |
| EP07   | Forma de pago                     | Como usuario quiero tener una forma de pago dentro de la aplicación.                                     |
| EP08   | Notificación de contratos         | Como usuario quiero notificaciones que me den información de los contratos.                              |
| EP09   | Visualización de perfiles         | Como usuario quiero ver la información que hay en el perfil de un cliente o transportista.               |
| EP10   | Información de contratos          | Como usuario quiero tener la información de mis contratos.                                               |

## 3.3. Impact Mapping. 

Link para una visualización más detallada: [https://drive.google.com/file/d/1Z_48YO0enDocx_Bz8IzVSlgUXCc-bnF5/view?usp=sharing](https://drive.google.com/file/d/1Z_48YO0enDocx_Bz8IzVSlgUXCc-bnF5/view?usp=sharing)

###### _Impact Mapping de los usuarios cliente y transportista_

![Impact Mapping](img/Capitulo_2/Needfinding/9.jpg)
## 3.4. Product Backlog.

##### _Desarrollo del Product Backlog_

| **User Story ID** | **Título**                                  | **Descripción**                                                                                                                                                                             | **Story Points (8/5/3/2/1)** |
| ----------------- | ------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :--------------------------: |
| **HU-011**        | Realizar el seguimiento por GPS             | Como cliente <br><br>Quiero seguir el transcurso del transportista     <br><br>Para sentirme seguro con el servicio                                                                         |            **8**             |
| **HU-007**        | Visualizar la información del transportista | Como cliente <br><br>Quiero observar el perfil del transportista<br><br>Para contratarlo                                                                                                    |            **5**             |
| **HU-008**        | Contratar el servicio                       | Como cliente <br><br>Quiero contratar el servicio<br><br>Para acceder a los servicios del transportista                                                                                     |            **5**             |
| **HU-009**        | Realizar el pago                            | Como cliente <br><br>Quiero realizar el pago del servicio<br><br>Para no tener deudas pendientes                                                                                            |            **5**             |
| **HU-017**        | Notificar del trabajo                       | Como transportista                      <br><br>Quiero que me notifiquen cuando un cliente requiere de mis servicios <br><br>Para no perderme de algún contrato                             |            **5**             |
| **HU-018**        | Informar del contrato propuesto             | Como transportista<br><br>Quiero leer la información del servicio propuesto   <br><br>Para decidir si aceptar el trabajo                                                                    |            **5**             |
| **HU-006**        | Buscar un vehículo                          | Como cliente <br><br>Quiero buscar el tipo de vehículo adecuado<br><br>Para así contratarlo                                                                                                 |            **5**             |
| **HU-022**        | Comentar el servicio brindado               | Como cliente<br><br>Quiero dejar un comentario acerca de mi experiencia con el conductor luego de terminar el servicio<br><br>Para ayudar a los demás usuarios en su elección de conductor. |            **5**             |
| **HU-001**        | Registrar al transportista                  | Como transportista<br><br>Quiero registrarme dentro de la aplicación<br><br>Para navegar dentro de ella                                                                                     |            **3**             |
| **HU-002**        | Registrar al cliente                        | Como cliente<br><br>Quiero registrarme dentro de la aplicación<br><br>Para navegar dentro de ella                                                                                           |            **3**             |
| **HU-023**        | Iniciar sesión como cliente                 | Como cliente<br><br>Quiero iniciar sesión en la aplicación<br><br>Para acceder a los servicios de transporte y gestionar mi perfil de usuario de manera segura y conveniente.               |            **3**             |
| **HU-024**        | Iniciar sesión como transportista           | Como cliente<br><br>Quiero iniciar sesión en la aplicación<br><br>Para acceder a los servicios de transporte y gestionar mi perfil de usuario de manera segura y conveniente.               |            **3**             |
| **HU-020**        | Ver la información del usuario              | Como usuario  <br><br>Quiero visualizar mi perfil y los datos que ingrese en el registro.<br><br>Para corroborar que los datos son correctos                                                |            **3**             |
| **HU-005**        | Editar mi perfil de usuario                 | Como usuario de la aplicación<br><br>Quiero poder editar los datos de mi perfil<br><br>Para mantener mis datos actualizados                                                                 |            **3**             |
| **HU-012**        | Ver el historial de contratos               | Como usuario<br><br>Quiero revisar el historial de contratos <br><br>Para tener un registro                                                                                                 |            **3**             |
| **HU0-013**       | Revisar el servicio                         | Como cliente  <br><br>Quiero decidir revisar el servicio brindado<br><br>Para sentirme más seguro                                                                                           |            **3**             |
| **HU-016**        | Ver el estado del contrato propuesto        | Como cliente <br><br>Quiero saber el estado de mi oferta de trabajo <br><br>Para saber si fue aceptada o rechazada                                                                          |            **3**             |
| **HU-019**        | Reportar una incidencia                     | Como cliente <br><br>Quiero reportar alguna incidencia que haya sucedido <br><br>Para mejorar el servicio dentro de la aplicación                                                           |            **3**             |
| **HU-021**        | Ver el contrato finalizado                  | Como transportista<br><br>Quiero rellenar mi información de pago<br><br>Para recibir el pago correspondiente por el servicio brindado.                                                      |            **3**             |
| **HU-003**        | Registrar un transporte                     | Como transportista <br><br>Quiero almacenar la información de mi transporte y el servicio que ofrezco <br><br>Para que el cliente tenga una noción del servicio que brindo                  |            **2**             |
| **HU-004**        | Registrar su experiencia                    | Como transportista<br><br>Quiero registrar mi experiencia de trabajo <br><br>Para generar confianza al cliente                                                                              |            **2**             |
| **HU-015**        | Guardar los datos de la tarjeta             | Como cliente <br><br>Quiero guardar los datos de mi tarjeta<br><br>Para usarla de manera más rápida en mis siguientes pagos                                                                 |            **2**             |
| **HU-010**        | Cerrar sesión en la aplicación              | Como usuario transportista<br><br>Quiero salir de la aplicación<br><br>Para iniciar sesión en otra cuenta como cliente                                                                      |            **1**             |
| **HU-014**        | Acceder a las preguntas frecuentes          | Como usuario<br><br>Quiero acceder a un banco de preguntas frecuentes sobre la aplicación<br><br>Para despejar dudas que tenga sobre algunos procesos                                       |            **1**             |

---

# Capítulo IV: Strategic-Level Software Design
## 4.1. Strategic-Level Attribute-Driven Design
### 4.1.1. Design Purpose
El propósito fundamental del proceso de diseño de FastPorte es crear una aplicación web que facilite de manera eficiente la conexión entre transportistas y clientes que requieren servicios de transporte diversificados. Nuestra meta principal es crear una plataforma de vanguardia que proporcione una solución integral y eficiente para las necesidades de transporte de nuestros clientes y al mismo tiempo ofrezca oportunidades de crecimiento y desarrollo para los transportistas colaboradores. Nuestros objetivos se centran en la eficiencia, la seguridad, la escalabilidad y la experiencia del usuario, con una visión hacia la sostenibilidad en la industria del transporte.

**OBJETIVOS CLAVE:**

1. **Conexión Eficiente:** FastPorte tiene como objetivo principal proporcionar una interfaz de usuario intuitiva que permita a los clientes buscar y reservar fácilmente servicios de transporte. La aplicación debe garantizar que los transportistas adecuados estén disponibles para satisfacer las necesidades específicas de cada cliente.
1. **Seguridad y Confianza:** La seguridad de las transacciones y la confiabilidad de los transportistas son fundamentales para nuestro diseño. Nos comprometemos a verificar a fondo a los transportistas y proporcionar a los clientes información transparente y reseñas para tomar decisiones informadas.
1. **Escalabilidad:** FastPorte debe ser diseñado con la capacidad de crecer y adaptarse a medida que aumenta la demanda de servicios de transporte. Esto implica un diseño modular y escalable que permita la incorporación sencilla de nuevos transportistas y características adicionales.
1. **Eficiencia Operativa:** La aplicación debe optimizar la gestión de rutas, el tiempo de entrega y los recursos de los transportistas para garantizar que tanto los clientes como los transportistas obtengan el máximo valor de FastPorte.
1. **Experiencia del Usuario:** Buscamos proporcionar una experiencia de usuario excepcional, con una interfaz intuitiva y amigable que permita a los usuarios navegar sin problemas por la plataforma y realizar reservas de manera rápida y sencilla.
1. **Integración y Adaptabilidad:** FastPorte se diseñará para ser compatible con una variedad de dispositivos y sistemas, lo que permitirá futuras expansiones y la incorporación de nuevas características tecnológicas y de mercado.
1. **Sostenibilidad:** Si bien FastPorte se lanza en un dominio competitivo, aspiramos a ser líderes en la adopción de prácticas sostenibles en la industria del transporte, alentando la eficiencia energética y reduciendo la huella de carbono en la logística de transporte.

### 4.1.2. Attribute-Driven Design Inputs
#### 4.1.2.1. Primary Functionality (Primary User Stories)
| Epic /<br>User story ID | Título                               | Descripción                                                                                                                                                                     | Criterios de Aceptación                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               | Relacionado con (EpicID) |
| :---------------------- | :----------------------------------- | :------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :----------------------- |
| HU-006                  | Buscar un vehículo                   | Como cliente, quiero buscar el tipo de vehículo adecuado, para así contratarlo.                                                                                                 | <p>**Escenario N°1: El cliente busca el vehículo adecuado para contratarlo** </p><p>  </p><p>**Dado que** el cliente quiere buscar un vehículo adecuado para el servicio que requiere</p><p>**Y** se ubica en la sección “Buscar”. </p><p>**Y** se selecciona el tipo de vehículo que desea contratar</p><p>**Y** la cantidad/peso que va a transportar</p><p>**Cuando** presiona en “Enviar”</p><p>**Entonces** se le mostrarán los resultados de los vehículos acorde a su búsqueda</p>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             | EP03                     |
| HU-008                  | Contratar el servicio                | Como cliente, quiero contratar el servicio, para acceder a los servicios del transportista.                                                                                     | <p>**Escenario N°1: El cliente desea contratar el servicio** </p><p>  </p><p>**Dado que** el cliente desea contratar el servicio para obtener los servicios del transportista </p><p>**Y** se encuentra en el perfil del transportista </p><p>**Cuando** presiona el botón “Contratar” en la parte inferior del perfil</p><p>**Entonces** aparece un formulario para realizar el contrato**  </p><p>**Y** si lo completa pasará a realizar el pago</p>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                | EP04                     |
| HU-009                  | Realizar el pago                     | Como cliente, quiero realizar el pago del servicio, para no tener deudas pendientes.                                                                                            | <p>**Escenario N°1: El cliente realiza el pago de forma correcta**</p><p></p><p>**Dado que** el cliente ha iniciado sesión en la aplicación móvil<br>**Y** le llega una notificación de aceptación de su oferta de trabajo</p><p>**Cuando** presione “Ver más detalles”, le aparecerá la pantalla de pago </p><p>**Y** complete de forma correcta los datos de su tarjeta</p><p>**Y** presione “Pagar”</p><p>**Entonces** le aparecerá un cuadro de confirmación</p>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  | EP07                     |
| HU-011                  | Realizar el seguimiento por GPS      | Como cliente, quiero seguir el transcurso del transportista, para sentirme seguro con el servicio.                                                                              | <p>**Escenario N°1: El cliente revisa el transcurso de su viaje**</p><p>  </p><p>**Dado que** el cliente desea observar la ubicación actual del transportista</p><p>**Cuando** se ubique en el servicio que se está realizando </p><p>**Entonces** podrá observar la ubicación actual del transportista**  </p>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       | EP05                     |
| HU-016                  | Ver el estado del contrato propuesto | Como cliente, quiero saber el estado de mi oferta de trabajo, para saber si fue aceptada o rechazada.                                                                           | <p>**Escenario N°1: El cliente recibe una notificación de aceptación** </p><p>  </p><p>**Dado que** el cliente ha iniciado sesión en la aplicación  </p><p>**Cuando** un transportista acepte su oferta de trabajo </p><p>**Entonces** se le mostrará en la pestaña de notificaciones un mensaje que diga que el transportista ha aceptado su oferta de trabajo </p><p></p><p>**Escenario N°2: El cliente recibe una notificación de rechazo** </p><p>  </p><p>**Dado que** el cliente ha iniciado sesión en la aplicación  </p><p>**Cuando** un transportista rechace la oferta de trabajo </p><p>**Entonces** se le mostrará en la pestaña de notificaciones un mensaje que diga que el transportista ha rechazado su oferta de trabajo </p>                                                                                                                                                                                                                                                                                                                                                                                                                        | EP08                     |
| HU-017                  | Notificar el trabajo                 | Como transportista, quiero que me notifiquen cuando un cliente requiera de mis servicios, para no perderme de algún contrato.                                                   | <p>**Escenario N°1: El transportista es notificado de un contrato nuevo** </p><p>  </p><p>**Dado que** el transportista ha iniciado sesión en la aplicación móvil</p><p>**Cuando** algún cliente le proponga un contrato  <br>**Entonces** le aparecerá una nueva notificación</p>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    | EP08                     |
| HU-022                  | Comentar el servicio brindado        | Como cliente, quiero dejar un comentario acerca de mi experiencia con el conductor luego de terminar el servicio, para ayudar a los demás usuarios en su elección de conductor. | <p>**Escenario N°1:  El cliente deja un comentario exitosamente**</p><p></p><p>**Dado que** el cliente está autenticado en la aplicación</p><p>**Cuando** finalice un servicio</p><p>**Entonces** debe tener la opción de "Dejar un comentario" sobre el conductor.</p><p>**Dado que** el cliente seleccionó la opción "Dejar un comentario"</p><p>**Cuando** calificó al conductor con una calificación de 1 a 5 estrellas y escribió un comentario</p><p>**Entonces** su reseña debe ser registrada y visible públicamente para otros usuarios.</p><p></p><p>**Escenario N°2: El cliente tiene problemas al dejar un comentario**</p><p></p><p>**Dado que** el cliente está autenticado en la aplicación</p><p>C**uando** finalice un servicio, si la aplicación no permite dejar comentarios</p><p>E**ntonces** debe recibir un mensaje de error indicando que no se pueden dejar comentarios en este momento.</p><p>**Dado que** el cliente seleccionó la opción "Dejar un comentario"</p><p>**Si** no califica al conductor o no escribe un comentario</p><p>**Entonces** debe recibir un mensaje de error preguntándole si está seguro de omitir su reseña.</p> | EP06                     |

#### 4.1.2.2. Quality attribute Scenarios
Los escenarios de atributos de calidad son una parte fundamental del diseño de la arquitectura de software, ya que ayudan a definir cómo el sistema debe comportarse en situaciones específicas para cumplir con los requisitos de calidad esperados. En esta sección, se presenta la especificación inicial de los escenarios de atributos de calidad que tienen un impacto significativo en la arquitectura de la solución propuesta para FastPorte. Estos escenarios se han identificado con el objetivo de orientar el proceso de diseño hacia la creación de una plataforma que cumpla con las expectativas y necesidades de nuestros usuarios. 

Durante la fase de análisis, se han identificado varios atributos de calidad clave que son críticos para el éxito de FastPorte. Estos atributos incluyen usabilidad, fiabilidad, seguridad, portabilidad y mantenibilidad. Cada uno de estos atributos se refleja en una serie de escenarios que representan situaciones específicas en las cuales se evaluará el desempeño de la plataforma. 

Hemos identificado la facilidad de uso en acciones como la navegación y la modificación de datos personales, así como la respuesta rápida a las solicitudes de servicio y estrategias de tolerancia a fallos. Además, se prioriza la seguridad de los datos del usuario y la accesibilidad desde diversos dispositivos. Se enfatiza la necesidad de implementar cambios eficientemente para garantizar la continuidad del servicio.

A continuación, se presenta una tabla que detalla cada uno de los escenarios identificados, incluyendo el atributo de calidad correspondiente, la fuente del estímulo, la condición considerada, el componente afectado, el entorno, la respuesta esperada y la medida asociada.

|    Atributo    |    Fuente     |                                      Estímulo                                       |                Artefacto                 |                            Entorno                             |                                                       Respuesta                                                        |                                           Medida                                            |
| :------------: | :-----------: | :---------------------------------------------------------------------------------: | :--------------------------------------: | :------------------------------------------------------------: | :--------------------------------------------------------------------------------------------------------------------: | :-----------------------------------------------------------------------------------------: |
|   Usabilidad   |    Cliente    |                       Accede por primera vez a la aplicación                        |       Interfaces de la aplicación        | <p>- Cliente nuevo </p><p>- Aplicación cargada y funcional</p> |     Las interfaces son intuitivas, permitiendo al cliente aprender a utilizar la aplicación en menos de 5 minutos      |       Tiempo necesario para que el cliente aprenda a usar la aplicación, ≤ 5 minutos        |
|   Usabilidad   |    Cliente    |             Intenta modificar su información personal en la aplicación              |    Interfaz de comunicación amigable     |                   - Nuevos datos personales                    |     La plataforma muestra una interfaz de comunicación amigable para realizar la modificación de datos personales      |             Tiempo necesario para completar la modificación de datos personales             |
|   Usabilidad   |    Cliente    |           Tiene la opción de dejar un comentario y calificar al conductor           | Formulario de calificación y comentarios |              - Servicio de transporte finalizado               |                  El proceso para dejar un comentario y calificar al conductor es sencillo e intuitivo                  |                 Tiempo necesario para completar el proceso de calificación                  |
|   Fiabilidad   |    Cliente    |            Solicita un servicio de transporte a través de la aplicación             |     Sistema de solicitud de servicio     |               - Cliente tiene una señal estable                |                                   La aplicación responde en un máximo de 5 segundos                                    |                       Tiempo de respuesta de la aplicación (segundos)                       |
|   Fiabilidad   | Sistema / Red |          Prevenir fallas e implementar estrategias de tolerancia a fallos           |                 Sistema                  |     - El sistema cuenta con una conexión de red inestable      | El sistema implementa estrategias de tolerancia a fallos, como el reintentar automáticamente en caso de errores de red |          Eficacia de las estrategias de tolerancia a fallos (porcentaje de éxito)           |
|   Seguridad    |    Cliente    |         Inicia sesión en su cuenta para solicitar un servicio de transporte         |        Módulo de inicio de sesión        |  - El cliente cuenta con sus credenciales de inicio de sesión  |      Si el inicio de sesión es exitoso, el cliente podrá realizar sus actividades con normalidad en la plataforma      |                     Éxito del inicio de sesión (valor booleano: sí/no)                      |
|   Seguridad    |    Sistema    | Almacena y utiliza los datos de tarjeta de crédito de los clientes de manera segura |   Base de datos de tarjetas de crédito   |                 - Sistema Base de datos segura                 |  Los datos de tarjeta de crédito se almacenan de forma segura y se utilizan para procesar los pagos de manera segura   | Seguridad en el almacenamiento y uso de datos de tarjeta de crédito (valor booleano: sí/no) |
|  Portabilidad  |    Cliente    |                Accede a la aplicación desde cualquier navegador web                 |             Navegadores web              |          - Cliente accede desde otro navegadores web           |                         La aplicación es accesible desde cualquier navegador web sin problemas                         |    Tiempo necesario para cargar la aplicación desde diferentes navegadores (en segundos)    |
| Mantenibilidad | Desarrollador |                      Agrega una nueva función en la aplicación                      |      Código fuente de la aplicación      |  - El desarrollador se encuentra en el entorno de desarrollo   |                   Los cambios se reflejan en la plataforma sin necesidad de un despliegue adicional                    |             Tiempo necesario para reflejar cambios en la plataforma (en horas)              |


#### 4\.1.2.3. Constraints
En la búsqueda por diseñar una arquitectura de software sólida y efectiva que integre los principios de microservicios y Domain-Driven Design (DDD) para nuestra propuesta, es fundamental considerar las restricciones arquitectónicas que guiarán nuestro proceso. Estas restricciones, derivadas de factores técnicos, regulatorios y empresariales, desempeñarán un papel clave en la toma de decisiones, asegurando que nuestra solución aborde de manera efectiva las necesidades y se ajuste a las limitaciones que puedan afectar su implementación.

| Technical Story ID | Título                                            | Descripción                                                                                                                                          | Criterios de Aceptación                                                                                                                                                                                                                                                                                                                                                                                                | Relacionado con (Epic ID) |
| :----------------- | :------------------------------------------------ | :--------------------------------------------------------------------------------------------------------------------------------------------------- | :--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :------------------------ |
| CON-01             | Principios de Domain-Driven Design (DDD)          | La arquitectura de la aplicación debe seguir los principios de Domain-Driven Design (DDD) para modelar el dominio de manera efectiva.                | <p>Escenario: Cuando se realizan cambios en el modelo de dominio.</p><p>- **Dado que** la aplicación sigue los principios de Domain-Driven Design,</p><p>- **Cuando** los equipos de desarrollo actualizan el modelo de dominio,</p><p>- **Entonces** los cambios se reflejan de manera precisa en la arquitectura de la aplicación.</p><p></p>                                                                        | EP01                      |
| CON-02             | Escalabilidad Horizontal Eficiente                | La escalabilidad horizontal debe ser una consideración clave en la arquitectura, permitiendo la expansión de recursos de manera eficiente.           | <p>Escenario: Durante periodos de alta demanda de usuarios.</p><p>- **Dado que** la aplicación debe escalar horizontalmente de manera eficiente,</p><p>- **Cuando** el número de usuarios concurrentes aumenta significativamente,</p><p>- **Entonces** la aplicación es capaz de distribuir la carga de manera eficiente y mantener un rendimiento óptimo.</p><p></p>                                                 | EP03                      |
| CON-03             | Redundancia y Recuperación ante Desastres         | La aplicación debe ser diseñada con redundancia y recuperación ante desastres para garantizar la disponibilidad continua del servicio.               | <p>Escenario: En caso de fallo de un servidor principal.</p><p>- **Dado que** la aplicación se ha diseñado con redundancia y recuperación ante desastres,</p><p>- **Cuando** un servidor principal falla,</p><p>- **Entonces** la aplicación se conmuta automáticamente al servidor secundario sin pérdida de datos o interrupción del servicio.</p><p></p>                                                            | EP04                      |
| CON-04             | Uso de Servicios en la Nube y Contenedores        | Se debe utilizar un proveedor de servicios en la nube y aprovechar servicios de contenedores como Kubernetes.                                        | <p>Escenario: Durante el despliegue y escalado de la aplicación.</p><p>- **Dado que** se utilizan servicios en la nube y contenedores para desplegar la aplicación,</p><p>- **Cuando** se despliegan nuevas instancias de la aplicación o se escalan los recursos,</p><p>- **Entonces** la orquestación de contenedores asegura una distribución eficiente de la carga y una respuesta rápida a la demanda.</p><p></p> | EP02                      |
| CON-05             | Adaptabilidad y Agilidad en las Mejoras           | La plataforma debe ser altamente adaptable para incorporar nuevas características y mejoras de manera ágil y eficiente.                              | <p>Escenario: Al introducir una nueva funcionalidad.</p><p>- **Dado que** se prioriza la adaptabilidad y agilidad en el desarrollo,</p><p>- **Cuando** se introduce una nueva funcionalidad o se realiza una mejora,</p><p>- **Entonces** los usuarios pueden acceder a la nueva funcionalidad sin interrupciones en el servicio y sin necesidad de una actualización manual.</p><p></p>                               | EP06                      |
| CON-06             | Independencia y Desacoplamiento de Microservicios | Los microservicios deben ser independientes y desacoplados, lo que permite a los equipos de desarrollo trabajar de manera autónoma en cada uno.      | <p>Escenario: Cuando se actualiza un microservicio específico.</p><p>- **Dado que** los microservicios están diseñados para ser independientes y desacoplados,</p><p>- **Cuando** se actualiza un microservicio específico,</p><p>- **Entonces** los cambios en ese microservicio no afectan el funcionamiento de otros microservicios y la aplicación continúa funcionando sin problemas.</p><p></p>                  | EP09                      |
| CON-07             | Gestión de Versiones y Control de Cambios         | Debe implementarse un sistema de gestión de versiones y control de cambios para mantener la integridad del código y la colaboración efectiva.        | <p>Escenario: Durante la implementación de una nueva funcionalidad.</p><p>- **Dado que** se implementa un sistema de gestión de versiones y control de cambios,</p><p>- **Cuando** se implementa una nueva funcionalidad o se realiza un cambio en el código,</p><p>- **Entonces** todos los cambios están registrados y documentados adecuadamente en el sistema de control de versiones.</p><p></p>                  | EP08                      |
| CON-08             | Documentación Integral de Microservicios          | Los microservicios deben estar documentados de manera correcta para facilitar su comprensión y uso por parte de otros desarrolladores.               | <p>Escenario: Al integrar un nuevo microservicio.</p><p>- **Dado que** cada microservicio está completamente documentado,</p><p>- **Cuando** un desarrollador necesita integrar un nuevo microservicio en la aplicación,</p><p>- **Entonces** la documentación proporciona información clara y detallada sobre su funcionamiento y cómo se integra con el resto del sistema.</p><p></p>                                | EP10                      |
| CON-09             | Modularidad y Flexibilidad Arquitectónica         | La arquitectura debe ser altamente modular, lo que permite la sustitución o actualización de componentes individuales sin afectar a todo el sistema. | <p>Escenario: Al actualizar un componente del sistema.</p><p>- **Dado que** la arquitectura se basa en principios de modularidad y flexibilidad,</p><p>- **Cuando** se actualiza o reemplaza un componente del sistema,</p><p>- **Entonces** la implementación de los cambios se realiza de forma aislada y no afecta negativamente a otros componentes del sistema.</p><p></p>                                        | EP05                      |
| CON-10             | Seguridad de Datos y Privacidad del Usuario       | La seguridad de datos y la privacidad del usuario deben ser prioritarias, cumpliendo con las regulaciones de protección de datos aplicables.         | <p>Escenario: Al acceder a datos sensibles.</p><p>- **Dado que** la seguridad de datos y la privacidad del usuario son prioritarias,</p><p>- **Cuando** un usuario accede a datos sensibles o realiza una transacción,</p><p>- **Entonces** la información se almacena y se transmite de forma segura, protegiendo la privacidad del usuario y cumpliendo con las regulaciones de privacidad aplicables.</p><p></p>    | EP07                      |
| CON-11             | Estrategia de Respaldo y Recuperación de Datos    | Se debe implementar una estrategia de respaldo y recuperación de datos para garantizar la integridad y disponibilidad de la información crítica.     | <p>Escenario: Durante una restauración de datos de emergencia.</p><p>- **Dado que** se implementa una estrategia de respaldo y recuperación de datos,</p><p>- **Cuando** se produce una pérdida de datos o una interrupción del servicio,</p><p>- **Entonces** los datos críticos se pueden restaurar rápidamente y el servicio se restablece sin pérdida de funcionalidad.</p><p></p>                                 | EP01                      |
| CON-12             | Fechas de Entrega Inamovibles                     | Las fechas de entrega de los hitos del proyecto son inamovibles y no pueden ser pospuestas.                                                          | <p>Escenario: Durante el cumplimiento de un hito del proyecto.</p><p>- **Dado que** las fechas de entrega son inamovibles,</p><p>- **Cuando** se planifica y ejecuta el desarrollo del proyecto,</p><p>- **Entonces** los hitos del proyecto se entregan dentro del plazo establecido sin retrasos significativos.</p><p></p>                                                                                          | EP03                      |

<a name="_toc163118301"></a>
### 4.1.3. Architectural Drivers Backlog
Como equipo nos embarcamos en un proceso colaborativo para desarrollar una solución innovadora que abordara las complejidades del sector del transporte. Reconociendo las dificultades que enfrentan tanto los usuarios cotidianos como los transportistas independientes. Este proceso implicó una serie de pasos, desde la identificación de oportunidades de negocio hasta la definición de los requisitos arquitectónicos clave, que se documentaron en el Arquitectural Driver Backlog (ADB) para guiar el desarrollo futuro de la solución.

| Driver ID | Título de Driver                                     | Descripción                                                                                                                                                  | Importancia para Stakeholders (High, Medium, Low) | Impacto en Architecture Technical Complexity (High, Medium, Low) |
| :-------- | :--------------------------------------------------- | :----------------------------------------------------------------------------------------------------------------------------------------------------------- | :------------------------------------------------ | :--------------------------------------------------------------- |
| D01       | Escalabilidad para el crecimiento futuro             | Permitir que la plataforma FastPorte maneje un aumento significativo en el volumen de usuarios y transacciones a medida que crece el negocio.                | High                                              | High                                                             |
| D02       | Seguridad de datos y privacidad                      | Garantizar la protección adecuada de la información confidencial de los usuarios y la integridad de los datos.                                               | High                                              | High                                                             |
| D03       | Interfaz de usuario intuitiva y amigable             | Diseñar una interfaz que sea fácil de usar y que brinde una experiencia positiva para los clientes y transportistas.                                         | High                                              | Medium                                                           |
| D04       | Integración con servicios de pago                    | Facilitar el proceso de pago para los usuarios al integrar métodos de pago seguros y confiables en la plataforma.                                            | High                                              | Medium                                                           |
| D05       | Notificaciones en tiempo real                        | Proporcionar a los usuarios actualizaciones instantáneas sobre el estado de sus viajes y transacciones.                                                      | Medium                                            | High                                                             |
| D06       | Adaptabilidad a múltiples dispositivos y plataformas | Garantizar que la plataforma sea accesible y funcione de manera óptima en una variedad de dispositivos y sistemas operativos.                                | Medium                                            | High                                                             |
| D07       | Gestión eficiente de la carga de trabajo             | Implementar herramientas y sistemas para administrar eficazmente la carga de trabajo de los transportistas y optimizar su tiempo y recursos.                 | Medium                                            | High                                                             |
| D08       | Mantenibilidad y escalabilidad del código            | Desarrollar un código limpio y modular que sea fácil de mantener y ampliar a medida que evoluciona la plataforma.                                            | Medium                                            | High                                                             |
| D09       | Análisis y generación de informes de datos           | Implementar herramientas para recopilar y analizar datos operativos y de rendimiento, y generar informes significativos para informar la toma de decisiones. | Low                                               | High                                                             |

### <a name="_toc163118302"></a>4.1.4. Architectural Design Decisions
Para crear decisiones de diseño arquitectónico basados en los drivers arquitectónicos, utilizaremos la siguiente matriz:

| Driver ID | Título de Driver                                     | Pattern 1                        | Pattern 2                                     | Pattern 3                                    |
| :-------- | :--------------------------------------------------- | :------------------------------- | :-------------------------------------------- | :------------------------------------------- |
| D01       | Escalabilidad para el crecimiento futuro             | Microservicios                   | Autoescalado                                  | Colas de mensajes                            |
| D02       | Seguridad de datos y privacidad                      | Gateway de API segura            | Encriptación de datos en reposo y en tránsito | Autenticación y autorización basada en roles |
| D03       | Interfaz de usuario intuitiva y amigable             | Diseño responsive                | Arquitectura micro fronted                    | Patrones de diseño de UI/UX                  |
| D04       | Integración con servicios de pago                    | Pasarela de pago de terceros     | API de pagos unificada                        | Servicios web seguros                        |
| D05       | Notificaciones en tiempo real                        | Event Sourcing                   | WebSockets                                    | Sistema de colas de mensajes                 |
| D06       | Adaptabilidad a múltiples dispositivos y plataformas | Diseño responsive                | PWA (Progressive Web Apps)                    | Cross-Platform Development Frameworks        |
| D07       | Gestión eficiente de la carga de trabajo             | Orquestación de contenedores     | Colas de trabajo                              | Escalado automático                          |
| D08       | Mantenibilidad y escalabilidad del código            | Código limpio y principios SOLID | Arquitectura basada en componentes            | Integración y entrega continua (CI/CD)       |
| D09       | Análisis y generación de informes de datos           | Almacenes de datos               | Procesamiento de eventos en tiempo real       | Herramientas BI (Business Intelligence)      |

### <a name="_toc163118303"></a>4.1.5. Quality Attribute Scenario Refinements

<table><tr><th colspan="3" valign="top"><b>Scenario Refinement for Scenario 1</b></th></tr>
<tr><td colspan="2" valign="top">Scenario(s):</td><td colspan="1" valign="top">Escalabilidad para el crecimiento Futuro</td></tr>
<tr><td colspan="2" valign="top">Business Goals</td><td colspan="1" valign="top">Asegurar la expansión sostenible y la competitividad en el mercado</td></tr>
<tr><td colspan="2" valign="top">Relevant Quality Attributes</td><td colspan="1" valign="top">Tiempo de respuesta para la implementación de capacidad adicional no superior a 3 min después de detectar aumentos en la demanda</td></tr>
<tr><td colspan="1" rowspan="6" valign="top">Scenario Components</td><td colspan="1" valign="top">Stimulus</td><td colspan="1" valign="top">La plataforma FastPorte experimenta un aumento del 300% en el volumen de usuarios y transacciones en un periodo de 4 semanas</td></tr>
<tr><td colspan="1" valign="top">Stimulus Source</td><td colspan="1" valign="top">Incremento significativo en el número de usuarios activos y transacciones simultáneas</td></tr>
<tr><td colspan="1" valign="top">Environment</td><td colspan="1" valign="top">En operación normal bajo condiciones de carga de trabajo aumentadas</td></tr>
<tr><td colspan="1" valign="top">Artifact (if known)</td><td colspan="1" valign="top">Los servidores ejecutan la lógica de negocio y manejan las solicitudes de los usuarios. Componentes como balanceadores de carga.</td></tr>
<tr><td colspan="1" valign="top">Response</td><td colspan="1" valign="top">El sistema debe escalar de manera automática para manejar el aumento de carga, manteniendo los tiempos de respuesta dentro de los parámetros aceptables y sin degradar la experiencia del usuario ni la integridad de los datos.</td></tr>
<tr><td colspan="1" valign="top">Response Measure</td><td colspan="1" valign="top">El tiempo de respuesta para transacciones críticas no debe exceder los 2 segundos, y el sistema debe ser capaz de aumentar su capacidad (ya sea mediante escalado horizontal o vertical) dentro de los 3 minutos siguientes a la detección del incremento en la carga de trabajo.</td></tr>
<tr><td colspan="2" valign="top">Questions</td><td colspan="1" valign="top">¿Existen proyecciones o estimaciones del crecimiento esperado en el volumen de usuarios y transacciones a lo largo del tiempo?</td></tr>
<tr><td colspan="2" valign="top">Issues</td><td colspan="1" valign="top">A medida que un sistema se escala, su complejidad operativa puede aumentar significativamente. ¿Cómo se planea manejar esta complejidad adicional?</td></tr>
</table>


<table><tr><th colspan="3" valign="top">Scenario Refinement for Scenario 2</th></tr>
<tr><td colspan="2" valign="top">Scenario(s):</td><td colspan="1" valign="top">Mantenibilidad y escalabilidad del código</td></tr>
<tr><td colspan="2" valign="top">Business Goals</td><td colspan="1" valign="top">Acelerar el tiempo de lanzamiento al mercado de nuevas funcionalidades, manteniendo o mejorando la calidad del software.</td></tr>
<tr><td colspan="2" valign="top">Relevant Quality Attributes</td><td colspan="1" valign="top">Mantenibilidad y Escalabilidad</td></tr>
<tr><td colspan="1" rowspan="6" valign="top">Scenario Components</td><td colspan="1" valign="top">Stimulus</td><td colspan="1" valign="top">La necesidad de modificar, extender, o escalar componentes del sistema para introducir nuevas funcionalidades, mejorar el rendimiento, o adaptarse a cambios en el entorno tecnológico o del negocio.</td></tr>
<tr><td colspan="1" valign="top">Stimulus Source</td><td colspan="1" valign="top">Equipo de desarrollo, cambios en requisitos del negocio, actualizaciones tecnológicas.</td></tr>
<tr><td colspan="1" valign="top">Environment</td><td colspan="1" valign="top">Desarrollo y mantenimiento post-lanzamiento.</td></tr>
<tr><td colspan="1" valign="top">Artifact (if known)</td><td colspan="1" valign="top">Código fuente, documentación del sistema, tests automatizados.</td></tr>
<tr><td colspan="1" valign="top">Response</td><td colspan="1" valign="top">El sistema facilita las modificaciones, extensiones y escalado con un mínimo impacto en los componentes existentes y sin degradar la calidad general o el rendimiento.</td></tr>
<tr><td colspan="1" valign="top">Response Measure</td><td colspan="1" valign="top">El tiempo requerido para implementar una nueva funcionalidad o modificar una existente no debe aumentar de manera significativa a medida que el sistema crece.</td></tr>
<tr><td colspan="2" valign="top">Questions</td><td colspan="1" valign="top">¿Cómo se estructurará el código para facilitar su comprensión y modificación?</td></tr>
<tr><td colspan="2" valign="top">Issues</td><td colspan="1" valign="top">Asegurar que el sistema escale de manera efectiva sin comprometer el rendimiento bajo cargas de trabajo elevadas.</td></tr>
</table>
## 4.2. Strategic-Level Domain-Driven Design.

### 4.2.1. EventStorming

###### *Step 1: Unstructured Exploration*
![driver](img/Capitulo_4/Event_Storming/Imagen1.png)
###### *Step 2: Timelines, Step 3: Pain Points, Step 4: Pivotal Points*
![Step 2 Part 1](img/Capitulo_4/Event_Storming/Imagen2.png)
![Step 2 Part 2](img/Capitulo_4/Event_Storming/Imagen3.png)
![Step 2 Part 3](img/Capitulo_4/Event_Storming/Imagen4.png)

###### *Step 5: Commands, Step 6: Policies, Step 7: Read models, Step 8: External Systems*

![Step 5, 6, 7, 8,  Part 1](img/Capitulo_4/Event_Storming/Imagen5.png)
![Step 5, 6, 7, 8,  Part 2](img/Capitulo_4/Event_Storming/Imagen6.png)
![Step 5, 6, 7, 8,  Part 3](img/Capitulo_4/Event_Storming/Imagen7.png)

###### *Step 9: Aggregates, Step 10: Bounded Contexts*

![Step 9,  10](img/Capitulo_4/Event_Storming/Imagen8.png)
Enlace de Figma para una mejor visualización: [https://www.figma.com/file/RqNZH8CXgzb4YsO1sjOR7v/Event-Storming---FastPorte?type=whiteboard&node-id=0%3A1&t=PA6eDILnRHf7lfWC-1](https://www.figma.com/file/RqNZH8CXgzb4YsO1sjOR7v/Event-Storming---FastPorte?type=whiteboard&node-id=0%3A1&t=PA6eDILnRHf7lfWC-1)

### 4.2.2. Candidate Context Discovery

Utilizando la metodología de eventstorming y adoptando el enfoque de "start-with-simple", empleamos una línea de tiempo como herramienta para discernir potenciales candidatos dentro de nuestro contexto definido. Estos candidatos identificados son los siguientes:

**Búsqueda de Vehículos**
Este bounded context se centra en la búsqueda de vehículos, integrando eventos como la inspección de perfiles de transportistas, la reconsideración de opciones por parte de los usuarios, y el regreso a la sección principal. Utiliza comandos para elegir vehículos, aplicar filtros, y aprovechar una API de inteligencia artificial, junto con políticas para manejar usuarios fuera de cobertura y ofrecer recomendaciones personalizadas. Su objetivo es optimizar la selección de transporte, haciéndola eficiente y adaptada a las necesidades del usuario.

![Búsqueda de vehículos Bounded Context](img/Capitulo_4/Candidate_Context_Discovery/Imagen1.png)
**Servicios**
Este Bounded Context aborda servicios de transporte, enfocándose en eventos clave como el retorno de usuarios a la página principal, accesos al soporte, aceptaciones de ofertas por transportistas, seguimientos GPS, y servicios concluidos. Los comandos gestionan ofertas y el estado de registro de vehículos, mientras que la política de GPS activado mejora la transparencia y la experiencia de seguimiento. Su propósito es optimizar las interacciones entre clientes y transportistas, asegurando una comunicación efectiva y una mayor satisfacción en el servicio.

![Servicios Bounded Context](img/Capitulo_4/Candidate_Context_Discovery/Imagen2.png)

**Cliente**
Este Bounded Context se centra en la experiencia del cliente dentro de una aplicación de servicios de transporte, abarcando eventos desde el registro en la aplicación hasta la realización de ofertas por servicios. Los eventos clave incluyen la búsqueda de transportistas que se ajusten a las necesidades específicas del cliente, la visualización de perfiles de transportistas y sus vehículos, y la elección de una opción de transporte. Los comandos disponibles permiten el registro de usuarios y la selección de vehículos, mientras que las políticas garantizan que los usuarios operen dentro de la cobertura y con datos ingresados correctamente. Este contexto busca facilitar la conexión entre clientes y transportistas, asegurando un proceso de selección eficiente y satisfactorio.

![Cliente Bounded Context](img/Capitulo_4/Candidate_Context_Discovery/Imagen3.png)

**Transportista**
Este Bounded Context se centra en los transportistas, desde su registro en la aplicación hasta el registro de nuevos vehículos, incluyendo el acceso a sus perfiles y el llenado de información vehicular. Los comandos principales son para registrar tanto al usuario como al vehículo, con políticas que aseguran la correcta o incorrecta entrada de datos. Este contexto apunta a facilitar la gestión de transportistas y sus vehículos, promoviendo la precisión en el registro de información.

![Transportista Bounded Context](img/Capitulo_4/Candidate_Context_Discovery/Imagen4.png)

### 4.2.3. Domain Message Flows Modeling

**Escenario 1: Cliente Solicita Servicio de Transporte**
En este escenario, un cliente utiliza una aplicación de servicios de transporte para solicitar un servicio de transporte de sus paquetes desde un lugar de recogida hasta un destino. El cliente inicia sesión en la aplicación. Luego, toma una foto de los paquetes para adjuntarla a la solicitud de transporte. La aplicación envía la solicitud junto con la foto al sistema de búsqueda de vehículos, que utiliza una API de inteligencia artificial para encontrar el transporte adecuado. Una vez encontrado, el sistema notifica al cliente sobre la asignación del transporte, proporcionando detalles adicionales

![Escenario 1](img/Capitulo_4/Domain_Message_Flows_Modeling/Imagen1.png)

**Escenario 2: Transportista Realiza el Servicio de Transporte**
En este escenario, un transportista utiliza una aplicación de servicios de transporte para llevar a cabo un servicio de transporte de paquetes. El transportista inicia sesión en la aplicación, revisa las solicitudes de transporte disponibles y acepta una de ellas. Luego, se dirige al lugar de recogida donde recoge los paquetes del cliente. Una vez recogidos, inicia el servicio de transporte y se dirige al destino. Durante el viaje, el sistema realiza un seguimiento GPS del transporte. Una vez que llega al destino y entrega los paquetes, se registra la finalización del servicio y se notifica al cliente sobre la entrega exitosa.

![Escenario 2](img/Capitulo_4/Domain_Message_Flows_Modeling/Imagen2.png)

### 4.2.4. Bounded Context Canvases

**Búsqueda de Vehículos**
Este bounded context se centra en el problema del dominio y es la búsqueda de vehículos, con el objetivo de optimizar la selección de opciones de transporte para los usuarios. En cuando a los subdominios se encuentra la inspección de los perfiles de transportistas y reconsideración de opciones, selección y filtrado de vehículos.

![Búsqueda de vehículos Canvas](img/Capitulo_4/Bounded_Context_Canvases/Imagen1.png)

**Servicios**
El Bounded Context Canvas para servicios de transporte es una herramienta estratégica diseñada para definir y delinear las características clave de este dominio específico dentro de un sistema de software. Proporciona una visión integral de cómo este contexto interactúa con los usuarios, gestiona datos y se comunica con otros contextos o sistemas.

![Servicios Canvas](img/Capitulo_4/Bounded_Context_Canvases/Imagen2.png)

**Transportista**
Este Bounded Context se centra en la gestión integral de los transportistas y sus vehículos, desde el registro inicial en la aplicación hasta la actualización continua de su información vehicular y personal. Este contexto define cómo los transportistas interactúan con la plataforma, estableciendo procesos y políticas claras para el registro de usuarios y vehículos, la validación de datos, y la comunicación entre la plataforma y los transportistas.

![Transportista Canvas](img/Capitulo_4/Bounded_Context_Canvases/Imagen3.png)

### 4.2.5. Context Mapping

Después de obtener cuáles serían nuestros Bounded Contexts, se realizó la elaboración de las relaciones estructurales entre estos. Para ello, se tomó en cuenta posibles diseños candidatos para el Context Mapping, el cual se desarrolló considerando los patrones de relaciones entre Bounden Contexts establecidos en Domain-Driven Desgin. Se utilizó la herramienta online DomoRoboto para elaborar el Context Mapping de la siguiente imagen:

![Context Mapping](img/Capitulo_4/Context_Mapping/Imagen1.png)
## 4.3. Software Architecture.

### 4.3.1. Software Architecture System Landscape Diagram.

El diagrama de System Landscape que presentamos muestra el diseño central de nuestro sistema de transporte de paquetes, con el "FastPorte Platform" en su corazón. Este núcleo sirve como la central de gestión de paquetes, conectando a los "Clientes" con el "Carrier" adecuado para su transporte. La plataforma proporciona una interfaz clara y eficaz por medio de la cual los clientes pueden estimar la cantidad de paquetes a enviar y seleccionar el vehículo idóneo para su entrega. Este enfoque no solo optimiza la eficiencia del proceso, sino que también eleva la satisfacción de todos los actores involucrados, garantizando una experiencia de transporte fluida y sin contratiempos.

![Landscape Diagram](img/Capitulo_4/Software_Architecture_System_Landscape_Diagram/Imagen1.png)

### 4.3.2. Software Architecture Context Level Diagrams.

###### ***Diagrama de Contexto de FastPorte***

![Diagrama de Contexto](img/Capitulo_4/Software_Architecture_Context_Level_Diagrams/Imagen1.png)

| Elemento       | Responsabilidad                                                                |
| -------------- | ------------------------------------------------------------------------------ |
| Client         | Usuario de FastPorte el cual busca contratar servicios de transportista        |
| Carrier        | Usuario de FastPorte el cual busca promocionar sus servicios de transporte     |
| Admin          | Usuario administrador que tiene acceso a todas las funciones de FastPorte      |
| FastPorte      | El sistema que se desarrollará para FastPorte                                  |
| GoogleMaps     | API de GoogleMaps para poder utilizar los servicios de geolocalización         |
| RENIEC System  | Sistema externo para verificar los datos personales de los usuarios            |
| E-mail System  | Sistema de correo electrónico externo para validar servicios                   |
| Payment System | Sistema de pago externo para poder realizar pagos en la aplicación web / móvil |

### 4.3.3. Software Architecture Container Level Diagrams.
###### *Diagrama de Contenedores de FastPort*

![Diagrama de Contenedores](img/Capitulo_4/Software_Architecture_Container_Level_Diagrams/Imagen1.png)

### 4.3.4. Software Architecture Deployment Diagrams.

Para el desarrollo de aplicaciones en este proyecto, se optó por utilizar Azure debido a las necesidades específicas del proyecto. Se eligieron instancias que mejor se adaptaban a los requisitos de rendimiento y escalabilidad, proporcionando así un entorno óptimo para el desarrollo y despliegue de aplicaciones.

Una de las ventajas más significativas de usar Azure fue la rapidez en las peticiones, lo que resultó en un rendimiento mejorado de las aplicaciones. Esta característica fue crucial para satisfacer las demandas de alta disponibilidad y respuesta rápida del proyecto.

**Creación de Imágenes Docker**
Las imágenes Docker para los servicios y componentes del proyecto se crearon utilizando IntelliJ IDEA, Maven y Docker Compose. Este enfoque aseguró una integración y gestión fluidas del entorno de desarrollo, facilitando la creación y mantenimiento de las imágenes Docker.

**Gestión de Contenedores Docker**
Inicialmente, todas las pruebas se realizaron localmente para garantizar que los contenedores funcionaran según lo esperado. Tras corregir los errores identificados, los contenedores se subieron a Azure. Este proceso garantizó que los contenedores fueran robustos y estables antes de su implementación en el entorno de producción.
###### *Cloud Architecture Deployment Diagram*

![Cloud Architecture Deployment Diagram](img/Capitulo_4/Software_Architecture_Deployment_Diagrams/Imagen1.png)

---
# Capítulo V: Tactical-Level Software Design
## 5.1. Bounded Context: Hiring
El Bounded Context "Hiring" se enfoca en el proceso de contratacion de drivers. Su principal objetivo es gestionar la creacion de contratos entre los clientes y los conductores contratados. Este proceso implica la definicion detallada del contrato, asi como la recoleccion y verificacion de la informacion necesaria del conductor, licencias, historial y datos personales relevantes.
### 5.1.1. Domain Layer

**Entities**

- **Contract:** 

  Esta entidad representa un componente fundamental en el sistema de gestión de transporte, proporcionando un registro estructurado de los acuerdos contractuales entre la empresa y los conductores, e incluyendo tanto información contractual como personal relevante para la operación y administración efectiva del servicio de transporte.

**Value Objects:**

- **StatusContract:** 

  Este objeto de valor es esencial para representar el estado de un contrato de manera coherente y estructurada dentro del modelo de dominio de la aplicación. Al utilizarlo como un value object, se asegura la consistencia en la forma en que se maneja y se muestra el estado de los contratos en la aplicación.

**Aggregates:**

- **Contract:** 

  Este Aggregate agrupa la información relacionada con los contratos de conductor dentro del sistema de gestión de transporte. Actúa como una colección cohesiva de datos que encapsula los detalles contractuales y personales de cada conductor contratado. Esto incluye detalles contractuales como los términos y condiciones, la fecha de inicio y finalización del contrato, tarifas acordadas, así como información personal del conductor, como nombre, datos de contacto y cualquier otro detalle pertinente para la gestión de contratos.
### 5.1.2. Interface Layer
**Controllers:** 

- **HiringController:** 

  Este controlador constituye un componente fundamental dentro de la arquitectura de la aplicación, encargado de gestionar el proceso de contratación de conductores en nuestra plataforma de transporte. En este controlador, se encuentran implementadas diversas funcionalidades CRUD destinadas a interactuar con los datos relacionados con los conductores dentro del sistema. Estas operaciones van desde la creación de nuevos contratos de conductor hasta la actualización de información contractual y la eliminación de registros existentes, según sea necesario.

### 5.1.3. Application Layer
**Services:**

- **HiringService:**

  Este servicio constituye un componente central en la arquitectura de la aplicación, encargado de gestionar todas las operaciones relacionadas con la contratación de conductores dentro del sistema de transporte. Se dedica a manejar de manera integral y segura los datos esenciales para la gestión de la contratación de conductores. Este servicio abarca desde la creación inicial de contratos de conductor hasta la recuperación y actualización de información contractual

### 5.1.4. Infrastructure Layer

**Repositories:**

- **HiringRepository:** 

  Cumple un papel fundamental al facilitar la interacción con la base de datos para gestionar la persistencia de datos relacionados con los contratos de conductores en nuestra aplicación.


### 5.1.5. Bounded Context Software Architecture Component Level Diagrams
En la siguiente imagen se presenta el diagrama de componentes del bounded context “Hiring”.

![Componen Level Diagrams](img/Capitulo_5/Bounded_Context_Hiring/Software_Architecture_Component_Level_Diagrams.png)

### 5.1.6. Bounded Context Software Architecture Code Level Diagrams
A continuación, se presentará el diagrama de clases para el bounded context correspondiente, así como también el diagrama de base de datos.

#### 5.1.6.1. Bounded Context Domain Layer Class Diagrams
En esta sección se muestra el diagrama de clases correspondiente al Bounded Context "Hiring". En este diagrama se pueden observar las clases de la capa de dominio así como sus relaciones con las clases de las demás capas.

![Code Level Diagram](img/Capitulo_5/Bounded_Context_Hiring/Domain_Layer_Class_Diagrams.png)

#### 5.1.6.2. Bounded Context Database Design Diagram

![Data Base Diagram](img/Capitulo_5/Bounded_Context_Hiring/Database_Desing_Diagram.png)

## 5.2. Bounded Context: PersonalData
El Bounded Context "PersonalData" se centra en la gestión y el manejo de los datos personales de los usuarios dentro de nuestra aplicación. Este contexto delimitado encapsula todos los aspectos relacionados con la recopilación, almacenamiento y manipulación de la información personal de los usuarios, garantizando su seguridad, privacidad y coherencia en todo momento.
### 5.2.1. Domain Layer
**Entities**

- **Carrier:** 

  Esta entidad representa a un transportista que presta sus servicios dentro de la aplicación. Tiene atributos de índole personal como nombres, datos de la cuenta, foto, número de celular, dirección, experiencia, etc.

- **Client:** 

  Esta entidad representa a un cliente que busca los servicios de un transportista. Tiene atributos como nombres, datos de la cuenta, foto, descripción, celular, lista de tarjetas, etc.

**Value Objects:**

- **Name:** 

  Este objeto de valor es útil para representar nombres de personas de una manera coherente y estructurada en el modelo de dominio. Al utilizarlo como un value object, se garantiza la consistencia en la forma en que se manejan y se muestran los nombres en la aplicación.

- **Account:** 

  Es útil para encapsular la información relacionada con la cuenta de un usuario, como el nombre de usuario y la contraseña. Con esto, se hace un manejo de la cuenta de una manera más segura.

- **Type:** 

  Se utiliza para representar el tipo de usuario en el sistema. Este objeto de valor está diseñado para encapsular y definir el tipo de entidad dentro del contexto de la aplicación, ya sea un transportista o un cliente.

**Aggregates:**

- **Carrier:** 

  Este Aggregate agrupa la información relacionada con los transportistas, incluidos sus datos personales, información de cuenta y otros atributos relevantes. La entidad Carrier actuaría como la raíz del Aggregate, y los objetos de valor como Name y Account podrían ser parte de los datos personales del transportista.

- **Client:** 

  Este Aggregate agrupa la información relacionada con los clientes que utilizan los servicios de transporte. Al igual que con el Aggregate de Transportista, la entidad Client actuaría como la raíz del Aggregate, y los objetos de valor podrían representar los datos personales y la información de la cuenta del cliente.

### 5.2.2. Interface Layer
**Controllers:** 

- **PersonalDataController:** 

  Este controlador constituye una pieza esencial de la capa de interfaz de nuestra aplicación, enfocándose en la administración de datos relacionados a los usuarios (clients y carriers) dentro del ecosistema de nuestra aplicación. En este controlador, se encuentran implementadas diversas funcionalidades CRUD destinadas a interactuar con los datos de los usuarios. Estas operaciones abarcan desde la obtención de una lista completa de los conductores y clientes hasta la búsqueda específica de uno por medio de su identificador único.

### 5.2.3. Application Layer
**Services:**

- **PersonalDataService:**

  Este servicio se encarga de gestionar todas las operaciones relacionadas con los usuarios dentro de la aplicación. Desde la creación y recuperación de perfiles de usuario hasta la actualización y eliminación de información personal. El personalDataService asegura una gestión coherente y segura de los datos de los usuarios. Además, integra lógica de negocio adicional.

### 5.2.4. Infrastructure Layer

**Repositories:**

- **ClientRepository:** 

  Facilita la conexión con la base de datos para gestionar la persistencia de datos relacionados con los clientes en nuestra aplicación.

- **CarrierRepository:** 

  Establece la conexión con la base de datos para administrar la persistencia de datos relacionados con los transportistas o carriers en nuestra aplicación.

### 5.2.5. Bounded Context Software Architecture Component Level Diagrams
En la siguiente imagen se presenta el diagrama de componentes del bounded context “PersonalData”.

![Component Level Diagram](img/Capitulo_5/Bounded_Context_PersonalData/Software_Architecture_Component_Level_Diagrams.png)

### 5.2.6. Bounded Context Software Architecture Code Level Diagrams
A continuación, se presentará el diagrama de clases para el bounded context correspondiente, así como también el diagrama de base de datos.

#### 5.2.6.1. Bounded Context Domain Layer Class Diagrams
En esta sección se muestra el diagrama de clases correspondiente al Bounded Context "PersonalData". En este diagrama se pueden observar las clases de la capa de dominio así como sus relaciones con las clases de las demás capas.

![Code Level Diagram](img/Capitulo_5/Bounded_Context_PersonalData/Domain_Layer_Class_Diagrams.png)

#### 5.2.6.2. Bounded Context Database Design Diagram

![Database Design Diagram](img/Capitulo_5/Bounded_Context_PersonalData/Database_Design_Diagram.png)

## 5.3. Bounded Context: Location
Este Bounded Context se encarga de gestionar todas las ubicaciones geográficas relacionadas con los usuarios y operaciones de la aplicación. Incluye la manipulación de direcciones de carga, descarga y cualquier punto relevante que requiera geolocalización precisa. Esta capacidad es fundamental para optimizar rutas, calcular distancias, y asegurar la precisión en la logística y distribución.
### 5.3.1. Domain Layer
**Entities**
- **Location**: Representa una ubicación geográfica concreta, como puede ser la dirección de un cliente o de un punto de carga y descarga. Tiene atributos como ID, dirección, latitud, longitud, descripción.

**Value Objects:**
- **Coordinates:** Encapsula la latitud y longitud para garantizar que las coordenadas sean siempre válidas y consistentes.
- **Address**: Representa una dirección postal completa, incluyendo calle, ciudad, código postal y país.

**Aggregates:**
- **LocationAggregate:** Agrega la entidad Location con los objetos de valor Coordinates y Address. Location actúa como raíz de agregado.
### 5.3.2. Interface Layer

**LocationRepository**: Maneja la persistencia de las entidades de Location, permitiendo operaciones CRUD sobre la base de datos. Tendrá la responsabilidad de Inserción, actualización, eliminación y recuperación de ubicaciones.
### **5.3.5. Bounded Context Software Architecture Component Level Diagrams.**

El diagrama ilustra el Bounded Context "Location" del sistema FastPorte, que administra las ubicaciones geográficas de transportistas y facilita servicios de localización a través de una aplicación web. La Web App actúa como interfaz principal para clientes que buscan servicios de transporte, conectándose a través de un API Gateway que canaliza las solicitudes a componentes como el SeguridadController. Este controlador gestiona la seguridad y localización, procesando las solicitudes mediante el LocationApplicationService. Este servicio utiliza el LocationFacade para interactuar con Google Maps, proporcionando datos georreferenciales y mapas detallados. La información de ubicación es gestionada en el Domain Layer y almacenada en la Database Location, asegurando la precisión y eficiencia en el servicio de transporte ofrecido por FastPorte.
![Component Level Diagram](img/Capitulo_5/Bounded_Context_Location/img1.png)

### 5.3.6. Bounded Context Software Architecture Code Level Diagrams

A continuación, se presentará el diagrama de clases para el bounded context correspondiente, así como también el diagrama de base de datos.

#### 5.3.6.1. Bounded Context Domain Layer Class Diagrams

El diagrama de clases del Bounded Context "Location" muestra cómo se organizan las entidades clave para gestionar la información de ubicación y de usuario en el sistema. Incluye las clases Location, User, Address y Coordinates, con Location conteniendo detalles como nombre y descripción junto con un objeto Coordinates que almacena la latitud y longitud. La clase User está vinculada estrechamente con Address, mostrando una composición que indica que cada usuario tiene una dirección, y está relacionada con Coordinates, sugiriendo que cada usuario tiene una ubicación geográfica definida. La interfaz LocationInterface proporciona métodos para manipular las ubicaciones, incluyendo obtener, actualizar, agregar y eliminar ubicaciones. Este diseño facilita la interacción eficiente entre la información de usuario y sus ubicaciones geográficas dentro del sistema, permitiendo un manejo estructurado tanto de los datos personales como de las coordenadas geográficas.


![Component Level Diagram](img/Capitulo_5/Bounded_Context_Location/img2.png)


#### 5.3.6.2. Bounded Context Database Design Diagram

El diagrama de diseño de base de datos para el Bounded Context "Location" muestra cómo las tablas Location, Coordinates y Address están interrelacionadas para almacenar información sobre ubicaciones. Cada tabla Location se enlaza a través de identificadores únicos a las tablas Coordinates, que almacena latitud y longitud, y Address, que guarda detalles de calle y ciudad. Este esquema permite una gestión eficiente y estructurada de los datos geográficos y de dirección dentro del sistema.

![Component Level Diagram](img/Capitulo_5/Bounded_Context_Location/img3.png)


---
## 5.4. Bounded Context: SearchService

El Bounded Context "Search" se centra en la gestión de la búsqueda del servicio a contratar. En este contexto, el usuario ingresa una foto del producto o productos que desea transportar y el sistema a través de una IA reconoce el objeto y sugiere un transporte con las dimensiones adecuadas para el usuario solicitante.

### 5.4.1. Domain Layer

**Entities**

- **Carrier:**

  Esta entidad representa a un transportista que presta sus servicios dentro de la aplicación. Tiene atributos de índole personal como nombres, datos de la cuenta, foto, número de celular, dirección, experiencia, etc.
- **Client:**

  Esta entidad representa a un cliente que busca los servicios de un transportista. Tiene atributos como nombres, datos de la cuenta, foto, descripción, celular, lista de tarjetas, etc.
- **Service:**

  Esta entidad está enfocada en la búsqueda del servicio de transporte e implementa la funcionalidad relacionado con la búsqueda y obtención de los vehículos adecuados.

**Value Objects:**

- **Name:**

  Este objeto de valor es útil para representar nombres de personas de una manera coherente y estructurada en el modelo de dominio. Al utilizarlo como un value object, se garantiza la consistencia en la forma en que se manejan y se muestran los nombres en la aplicación.
- **Account:**

  Es útil para encapsular la información relacionada con la cuenta de un usuario, como el nombre de usuario y la contraseña. Con esto, se hace un manejo de la cuenta de una manera más segura.
- **Service request:**

  Se utiliza para representar el ingreso de una búsqueda de servicio al sistema. Este objeto de valor está diseñado para encapsular y definir el tipo de servicio a contratar de acuerdo con el vehículo seleccionado dentro del contexto de la aplicación.
- **Origin Place:**

  Este término identifica la ubicación geográfica desde la cual se recogerá la carga para su posterior entrega en el destino final. Es importante especificar con precisión el "Origin Place" para planificar adecuadamente la logística del transporte y garantizar una gestión eficiente de los recursos y tiempos.
- **Destination Place:**

  "Destination Place" se refiere al lugar de destino o punto final al que se llevará la carga transportada. Este término identifica la ubicación geográfica donde se entregará la carga después de su transporte desde el lugar de origen. Es esencial especificar claramente el "Destination Place" para planificar la ruta de transporte, calcular los tiempos de entrega y asegurar una distribución eficiente de la carga.
- **Type Vehicle:**

  El vehículo de transporte de carga que será utilizado para llevar a cabo el servicio. Esto incluye camiones, furgonetas, remolques, entre otros. La elección del tipo de vehículo adecuado dependerá de factores como el tamaño y peso de la carga a transportar, la distancia del viaje, las restricciones de acceso y las preferencias del cliente. Es fundamental seleccionar el tipo de vehículo correcto para garantizar una entrega eficiente y segura de la carga.

**Aggregates:**

- **Carrier:**

  Este Aggregate agrupa la información relacionada con los transportistas, incluidos sus datos personales, información de cuenta y otros atributos relevantes. La entidad Carrier actuaría como la raíz del Aggregate, y los objetos de valor como Name y Account podrían ser parte de los datos personales del transportista.
- **Client:**

  Este Aggregate agrupa la información relacionada con los clientes que utilizan los servicios de transporte. Al igual que con el Aggregate de Transportista, la entidad Client actuaría como la raíz del Aggregate, y los objetos de valor podrían representar los datos personales y la información de la cuenta del cliente.
- **Service:**

  Este Aggregate agrupa la información relacionada con los clientes que solicitan servicios de transporte. La entidad Client actuaría como la raíz del Aggregate, y los objetos de valor podrían representar los datos personales y la información de la cuenta del cliente.

### 5.4.2. Interface Layer.

  La capa de interfaz se ocupa de interactuar con el usuario final y presentar los datos de manera comprensible. Para el contexto "Search", esta capa incluiría:

- **Image Upload Interface:** Interfaz para que los clientes suban imágenes de los productos a transportar.
- **Search Results Interface:** Interfaz para mostrar sugerencias de transportistas con los vehículos adecuados basados en la IA.
- **Booking Interface:** Interfaz para proceder a la reserva del servicio de transporte una vez seleccionado.

### 5.4.3. Application Layer.

La capa de aplicación maneja la lógica del negocio que no es crítica para el dominio pero es esencial para las operaciones de la aplicación:

- **Search Management:** Gestiona la lógica para interpretar la imagen cargada y sugerir el transporte adecuado.
- **Booking Management:** Procesa las reservas de servicios de transporte desde la confirmación hasta la finalización.
- **Notification Service:** Envía notificaciones a los usuarios sobre el estado de su búsqueda o reserva.

### 5.4.4. Infrastructure Layer.

Esta capa soporta la ejecución de las aplicaciones proporcionando recursos técnicos:

- **Image Processing Service:** Servicios de IA para analizar las imágenes subidas y reconocer productos.
- **Database Services:** Gestión de bases de datos para almacenar información sobre clientes, transportistas, y servicios.
- **External API Integration:** Integración con APIs externas para mapas y otras funcionalidades de localización.

### **5.4.5. Bounded Context Software Architecture Component Level Diagrams.**

En la siguiente imagen se presenta el diagrama de componentes del bounded context “SearchService”.

![Component Level Diagram](img/Capitulo_5/Bounded_Context_SearchService/Software_Architecture_Component_Level_Diagrams.png)

### 5.4.6. Bounded Context Software Architecture Code Level Diagrams

A continuación, se presentará el diagrama de clases para el bounded context correspondiente, así como también el diagrama de base de datos.

#### 5.4.6.1. Bounded Context Domain Layer Class Diagrams

En esta sección se muestra el diagrama de clases correspondiente al Bounded Context "SearchService". En este diagrama se pueden observar las clases de la capa de dominio así como sus relaciones con las clases de las demás capas.

![Code Level Diagram](img/Capitulo_5/Bounded_Context_SearchService/Domain_Layer_Class_Diagrams.png)

#### 5.4.6.2. Bounded Context Database Design Diagram

![Database Design Diagram](img/Capitulo_5/Bounded_Context_SearchService/Database_Design_Diagram.png)

---
# Capítulo VI: Solution UX Design 
## 6.1. Style Guidelines 
En esta sección presentaremos las guías de estilo que usaremos para la realización de nuestros mock-ups, prototipo y aplicación web.
### 6.1.1. General Style Guidelines
El estilo general de nuestro product UX/UI design contiene los siguientes colores los cuales se especifican con su código. Así como también la fuente utilizada es Inter.
***Colores del General Style Guidelines***
![Colores del General Style Guidelines](img/Capitulo_6/General_Style_Guidelines/Colores.png)
***Tipo de fuente del General Style Guidelines***
![Tipo de fuente del General Style Guidelines](img/Capitulo_6/General_Style_Guidelines/Fuente.png)
	### 6.1.2. Web, Mobile & Devices Style Guidelines.
Lo siguiente corresponde a la guía de estilos para la versión web. Se puede visualizar con mejor detalle en el siguiente link: [Enlace a Figma](https://www.figma.com/file/ipzddVXEuU5ee0IHE0hLyv/Open-source?node-id=50%3A2) 
***Tipografía utilizada en el General Style Guidelines***
![Tipografía utilizada en el General Style Guidelines](img/Capitulo_6/Web_Style_Guidelines/Tipografia.png)
***Search Interactive Elements del General Style Guidelines***
![Search Interactive Elements del General Style Guidelines](img/Capitulo_6/Web_Style_Guidelines/Search.png)
***Input Interactive Elements del General Style Guidelines***
![Input Interactive Elements del General Style Guidelines](img/Capitulo_6/Web_Style_Guidelines/Input.png)
***Buttons Interactive Elements del General Style Guidelines***
![Buttons Interactive Elements del General Style Guidelines](img/Capitulo_6/Web_Style_Guidelines/Buttons.png)
***Buttons & Slider Interactive Elements del General Style Guidelines***
![Buttons & Slider Interactive Elements del General Style Guidelines](img/Capitulo_6/Web_Style_Guidelines/Slider.png)
***Form Elements del General Style Guidelines***
![Form Elements del General Style Guidelines](img/Capitulo_6/Web_Style_Guidelines/Form.png)
## 6.2. Information Architecture.
En esta sección, mostramos el Information Architecture de FastPorte, donde se plantea la organización y estructura que se manejara para esta propuesta. Teniendo en cuenta, que nuestros usuarios puedan saber dónde se encuentra la información que se está buscando.
### 6.2.1. Labeling Systems.
Para los sistemas de etiquetado, utilizamos el lenguaje formal que refleja la seriedad en la aplicación, buscando así la mejor experiencia para nuestros usuarios.
**Label transportista:**
***Labeling Systems del transportista de FastPorte***
![Labeling Systems del transportista de FastPorte](img/Capitulo_6/Information_Architecture/Labeling_Transportista.png)
**Label cliente:**
***Labeling Systems del cliente de FastPorte***
![Labeling Systems del cliente de FastPorte](img/Capitulo_6/Information_Architecture/Labeling_Cliente.png)
**Transportista:**
- **Sección “Home”**
En esta sección podremos encontrar accesos rápidos que creemos que el usuario podría necesitar, tales como “Recent Contrats” o acceder el historial de contratos pasados
- **Sección “My Profile”**
En este apartado el usuario puede visualizar su perfil como transportista y evidenciar características que le harán llamar la atención de los clientes como una buena opción para contratarlo.
- **Sección “Contracts”** 
Dentro de esta sección podrán ver el historial de los contratos y los contratos que todavía siguen pendientes.
- **Sección “Support”** 
Al hacer click en este apartado el usuario podrá visualizar información de contacto como correo, número y una opción para enviar mensajes directos con el soporte de la aplicación.
- **Sección “Notification”** 
Dentro de esta sección el usuario podrá visualizar los mensajes, solicitudes, contratos y todo tipo de notificaciones entrantes.

**Cliente:**
- **Sección “Home”**
En esta sección podremos encontrar accesos rápidos que creemos que el usuario podría necesitar, tales como “Recent Contrats” o buscar un vehículo directamente.
- **Sección “My Profile”**
En este apartado el usuario puede visualizar su perfil como cliente y evidenciar características que le servirán a los transportistas para tener en cuenta a sus clientes.
- **Sección “Search Vehicles”** 
Dentro de esta sección el usuario podrá ingresar los datos de los requerimientos para el servicio que desea solicitar. Y así el sistema le pueda recomendar el mas adecuado a sus intereses.
- **Sección “Contracts”** 
Dentro de esta sección podrán ver el historial de los contratos y los contratos que todavía siguen pendientes.
- **Sección “Support”** 
Al hacer click en este apartado el usuario podrá visualizar información de contacto como correo, número y una opción para enviar mensajes directos con el soporte de la aplicación.
### 6.2.2. Searching Systems.
***Searching Systems de FastPorte***
![Searching Systems de FastPorte](img/Capitulo_6/Information_Architecture/Searching.png)
### 6.2.3. SEO Tags and Meta Tags.
***SEO Tags and Meta Tags de FastPorte***
![SEO Tags and Meta Tags de FastPorte](img/Capitulo_6/Information_Architecture/SEO.png)
- **Charset Tag**	
Utilizamos charset UTF-8 o Unicode Transformation Format-8, el cual es el formato de codificación de caracteres mundialmente usado por su amplia cantidad de idiomas soportados.
- **Viewport Tag**
Debido a que no todos los dispositivos cuentan con las mismas dimensiones; nos debemos asegurar de que nuestra página funcione correctamente en todos los tamaños y orientaciones de pantalla.
	- *Width:* Controla el tamaño de la ventana gráfica. Se puede configurar en un número específico de píxeles como ancho = 600 o en el valor especial ancho del dispositivo, que es 100vw, o el 100% del ancho de la ventana gráfica. 
	- *Initial-scale:* Controla el nivel de zoom cuando la página se carga por primera vez. Mínimo: 0,1. Máximo: 10. Predeterminado: 1. Valores negativos: ignorados.
	- *Translate:* Para ofrecer la traducción de la página en los resultados de búsqueda.
	- *Snippet:* Para que muestre el título y la descripción en los resultados de búsqueda.
- **Description Tag**
Esta etiqueta se usa para proporcionar una descripción breve de la página. En algunos casos, esta descripción se usa en el fragmento que se muestra en los resultados de la búsqueda.
- **Robots Tag**
Nos sirven para controlar el comportamiento de rastreo y de indexación en los motores de búsqueda.
	- *Index:* Sirve para indicarle al motor de búsqueda si deseamos ser indexados para que aparezca la página en los resultados de búsqueda.
	-	*No-follow:* Indica para no rastrear los links que contenga la página en cuestión, fue implementada para no ser mostrado como resultado los links de nuestra página.
- **Copyright Tag** 
Indica la empresa a la que pertenece la página web.
- **Keywords Tag**
Palabras clave sobre nuestra app, para aparecer en más resultados de búsqueda de usuarios que usen nuestras “keywords”.
- **Rating Tag**
Seleccionamos el rating mayor de 14 años, para tener mayor porcentaje de llegada. Además, al ser una app en la que el dinero es usado, no queremos personas insatisfechas por incentivar a niños gastar dinero sin su permiso.
### 6.2.4. Navigation Systems.
Para el sistema de navegación nos enfocamos en la comodidad y eficiencia que se le debe brindar al usuario, ya que son puntos sumamente importantes, en el que tomamos como prioridad el tiempo en el que el usuario demora en realizar una tarea.
***Navigation Systems de FastPorte***
![Navigation Systems de FastPorte](img/Capitulo_6/Information_Architecture/Navigation.png)
## 6.3. Landing Page UI Design.
En esta sección presentaremos el diseño de nuestra landing page empezando desde modelos de baja fidelidad como los wireframes y luego los mock-ups.
### 6.3.1. Landing Page Wireframe.
Las imágenes a continuación pertenecen a los wireframes realizados para el landing page. Abrir el link para más detalles del wireframe y de la versión mobile web browser: [Enlace a Figma](https://www.figma.com/file/xEc3h40NLBBgX0yLjxhLq9/Wireframe-FastPorte?node-id=0%3A1)
![Landing Page Wireframe 1](img/Capitulo_6/Landing_Page_Wireframe/1.png)
![Landing Page Wireframe 2](img/Capitulo_6/Landing_Page_Wireframe/2.png)
![Landing Page Wireframe 3](img/Capitulo_6/Landing_Page_Wireframe/3.png)
![Landing Page Wireframe 4](img/Capitulo_6/Landing_Page_Wireframe/4.png)
![Landing Page Wireframe 5](img/Capitulo_6/Landing_Page_Wireframe/5.png)
### 6.3.2. Landing Page Mock-up.
Las imágenes a continuación pertenecen a los mock-ups realizados para el landing page. Abrir el link para más detalles de la versión desktop y mobile web browser: [Enlace a Figma](https://www.figma.com/file/xEc3h40NLBBgX0yLjxhLq9/Wireframe-FastPorte?node-id=0%3A1)
**Desktop:**
![Landing Page Mockup Desktop 1](img/Capitulo_6/Landing_Page_Mockup/Desktop1.png)
![Landing Page Mockup Desktop 2](img/Capitulo_6/Landing_Page_Mockup/Desktop2.png)
![Landing Page Mockup Desktop 3](img/Capitulo_6/Landing_Page_Mockup/Desktop3.png)
![Landing Page Mockup Desktop 4](img/Capitulo_6/Landing_Page_Mockup/Desktop4.png)
![Landing Page Mockup Desktop 5](img/Capitulo_6/Landing_Page_Mockup/Desktop5.png)
![Landing Page Mockup Desktop 6](img/Capitulo_6/Landing_Page_Mockup/Desktop6.png)
**Mobile:**
![Landing Page Mockup Mobile 1](img/Capitulo_6/Landing_Page_Mockup/Mobile1.png)
![Landing Page Mockup Mobile 2](img/Capitulo_6/Landing_Page_Mockup/Mobile2.png)
![Landing Page Mockup Mobile 4](img/Capitulo_6/Landing_Page_Mockup/Mobile4.png)
![Landing Page Mockup Mobile 5](img/Capitulo_6/Landing_Page_Mockup/Mobile5.png)
![Landing Page Mockup Mobile 6](img/Capitulo_6/Landing_Page_Mockup/Mobile6.png)
![Landing Page Mockup Mobile 7](img/Capitulo_6/Landing_Page_Mockup/Mobile7.png)
![Landing Page Mockup Mobile 8](img/Capitulo_6/Landing_Page_Mockup/Mobile8.png)
![Landing Page Mockup Mobile 9](img/Capitulo_6/Landing_Page_Mockup/Mobile9.png)
## 6.4. Applications UX/UI Design.
En esta sección presentaremos el diseño de nuestra web application empezando desde modelos de baja fidelidad como los wireframes y luego los mock-ups.
### 6.4.1. Applications Wireframes.
Las siguientes imágenes corresponden a los wireframes de la web applications. El link para visualizarlo a mayor detalle es el siguiente: [Enlace a Figma](https://www.figma.com/file/ipzddVXEuU5ee0IHE0hLyv/Open-source?node-id=0%3A1)
![Application Wiframe 1](img/Capitulo_6/Application_Wireframe/1.png)
![Application Wiframe 2](img/Capitulo_6/Application_Wireframe/2.png)
![Application Wiframe 3](img/Capitulo_6/Application_Wireframe/3.png)
![Application Wiframe 4](img/Capitulo_6/Application_Wireframe/4.png)
![Application Wiframe 5](img/Capitulo_6/Application_Wireframe/5.png)
![Application Wiframe 6](img/Capitulo_6/Application_Wireframe/6.png)
![Application Wiframe 7](img/Capitulo_6/Application_Wireframe/7.png)
![Application Wiframe 8](img/Capitulo_6/Application_Wireframe/8.png)
![Application Wiframe 9](img/Capitulo_6/Application_Wireframe/9.png)
![Application Wiframe 10](img/Capitulo_6/Application_Wireframe/10.png)
![Application Wiframe 11](img/Capitulo_6/Application_Wireframe/11.png)
![Application Wiframe 12](img/Capitulo_6/Application_Wireframe/12.png)
![Application Wiframe 13](img/Capitulo_6/Application_Wireframe/13.png)
![Application Wiframe 14](img/Capitulo_6/Application_Wireframe/14.png)
### 6.4.2. Applications Wireflow Diagrams.
***Interfaz de Entrada***
**Wireflow 1: Registro de Usuario**
![Wireflow 1](img/Capitulo_6/Application_Wireflow/1.png)
Para registrarse el usuario deberá presionar “Create Account” lo cual le aparecerá un formulario. Tras completarlo, presiona “Continue”, aparece un formulario de datos personales. Luego de completarlo, presiona “Continue”. Finalmente, ya está registrado.

**Wireflow 2: Recuperar contraseña**
![Wireflow 2](img/Capitulo_6/Application_Wireflow/2.png)
Para recuperar la contraseña deberá presionar “Forgot your Password?”, lo cual le pedirá el correo correspondiente, presiono “Continue”. Aparecerá un formulario de cambio de contraseña y una vez presionado “Confirm”, realizando la actualización de la contraseña. 

***Interfaz de Transportistas***
**Wireflow 3: Ingreso de Transportista**
![Wireflow 3](img/Capitulo_6/Application_Wireflow/3.png)
Una vez registrado el transportista ingresa sus datos y presiona “Login to your account”. Y así mostrando la interfaz del transportista.

**Wireflow 4: Navegación de “My Profile”**
![Wireflow 4](img/Capitulo_6/Application_Wireflow/4.png)
El Cliente podrá ingresar a su perfil por el botón “My Profile” y podrá navegar “Personal Information”, “Experiencie”, “About the Vehicle” y “Comments”

**Wireflow 5: Navegación de “Contracts”**
![Wireflow 5](img/Capitulo_6/Application_Wireflow/5.png)
El transportista podrá navegar por los diferentes secciones de “Contracts” y el cual podrá navegar por “Offers”, “Pending Contracts” y “History”

**Wireflow 6: Aceptar/Rechazar ofertas de Trabajo**
![Wireflow 6](img/Capitulo_6/Application_Wireflow/6.png)
El transportista en “Offers” podrá Aceptar con el botón “Accept” y rechazar con el botón “Decline” y el cual informará la realización de su decisión, luego de presionar “Accept” regresará a la sección “Offers” mostrándole las ofertas disponibles.

**Wireflow 7: Soporte al cliente**
![Wireflow 7](img/Capitulo_6/Application_Wireflow/7.png)
El transportista para que pueda llegar a soporte al cliente debe presionar “Support” en donde le llevará a la sección al soporte al cliente.

**Wireflow 8: Notificación de oferta de Trabajo**
![Wireflow 8](img/Capitulo_6/Application_Wireflow/8.png)
El Transportista podrá revisar las ofertas desde el icono de notificaciones y al presionar “See more details” podrá observar todas las ofertas que este posee.

**Wireflow 9: Contrato Finalizado**
![Wireflow 9](img/Capitulo_6/Application_Wireflow/9.png)
Después de finalizar concluir servicio, aparecerá una notificación de contrato finalizado y luego de presionar “Details” aparecerá un formulario para realizar el pago el cual al presionar “Cancel” regresará a la pantalla con la notificación que debe de cancelar, por otro lado al presionar “ACCEPT AND CONFIRM” le aparecerá un recuadro que el pago será realizado en las 24 horas y al presionar “Accept” regresará a la pantalla principal.

**Wireflow 10: Cerrar Sesión**
![Wireflow 10](img/Capitulo_6/Application_Wireflow/10.png)
Para Cerrar Sesión presiona su nombre y aparece el botón “Log Out” el cual le permitirá cerrar su sesión.

***Interfaz de Cliente***
**Wireflow 11: Ingreso de Cliente**
![Wireflow 11](img/Capitulo_6/Application_Wireflow/11.png)
Una vez registrado el cliente ingresa sus datos y presiona “Login to your accout”. Y así mostrando la interfaz del cliente.

**Wireflow 12: Ingresar en “My Profile”**
![Wireflow 12](img/Capitulo_6/Application_Wireflow/12.png)
El Cliente podrá ingresar a su perfil por el botón “My Profile” y podrá editar su información 

**Wireflow 13: Contrato Rechazado**
![Wireflow 13](img/Capitulo_6/Application_Wireflow/13.png)
Cuando le rechazan un contrato, le aparecerá una notificación al presionar la 
campana.

**Wireflow 14: Realizar Depósito**
![Wireflow 14](img/Capitulo_6/Application_Wireflow/14.png)
Al haber terminado el servicio le aparecerá una notificación en la campana, luego de presionar “See more details” le presentará un formulario de cancelación al cual podrá completarlo

**Wireflow 15: Contratar conductor**
![Wireflow 15](img/Capitulo_6/Application_Wireflow/15.png)
Para contratar a un conductor se presiona “Search Vehicles”, el cual le aparecerá un formulario que deberá completar los datos “Type of service”, “Size of vehicle” y “Complete documentation”, luego le aparecerán los conductores correspondientes. Presionando la flecha le aparecerá su información del conductor para poder contratarlo, luego presionamos “Contract” aparecerá otro formulario de “Request service” tras completarlo y presionar “SUBMIT” aparece un recuadro indicándonos “The driver has been notified” presionamos “Accept” y será realizado así el contrato.

**Wireflow 16: Navegación en “Contracts”**
![Wireflow 16](img/Capitulo_6/Application_Wireflow/16.png)
En la sección podrá navegar por las diversas secciones Pending contracts y History.

**Wireflow 17: Navegación en “Support”**
![Wireflow 17](img/Capitulo_6/Application_Wireflow/17.png)
El cliente para que pueda llegar a soporte al cliente debe presionar “Support” en donde le llevará a la sección al soporte al cliente.

---
# Capítulo VII: Product Implementation, Validation & Deployment
## 7.1. Software Configuration Management 
### 7.1.1. Software Development Environment Configuration 
- **Project Management**
Se hizo uso de software que permite la comunicación en tiempo real y de edición rápida y compartida, de esta forma se trabajó con eficiencia. Algunos softwares utilizados fueron Google services (Drive, Documents, Meet) y Microsoft Outlook. Para el registro de versiones y creación de repositorios se hizo uso de GitHub ya que es una plataforma que nos permite registrar de manera ordenada cada uno de los commits que realizamos y realizaremos.
- **Product UX/UI Design**
Se empleó Miro y UXPressia para el desarrollo de todo lo relacionado a los segmentos objetivos y sus mapeos. Además, se utilizaron estas herramientas online para el desarrollo de los As-Is y To-Be Scenario Maps. Por otro lado, para el desarrollo de los mockups, wireframes, wireflows y el prototipo de la aplicación web, se empleó Figma.

Además, se creó un repositorio específico en GitHub para el UX/UI design, donde se encuentran los artefactos desarrollados a lo largo del trabajo.
**Repositorio UX-UI Design**
![Repositorio UX-UI Design](img/Capitulo_7/Software_Configuration_Management/1.png)
Link en github: [UX-UI Design](https://github.com/Arquitectura-WS82/UX-UI-Design)
- **Software Development**
Para el desarrollo del software de este proyecto se empleó lo siguiente:
	- **IntelliJ IDEA:** IDE desarrollado por JetBrains especializado para el desarrollo con el lenguaje de programación Java.
	- **Java:** Lenguaje de programación popularmente utilizado en el desarrollo de microservicios debido a su capacidad para ofrecer escalabilidad, portabilidad y robustez.
	- **Git:** La versión consola de sistema de control de versiones GIT, encargado de gestionar repositorios.
-  **Software Testing**
Para los test de aceptación, se usará el lenguaje Gherkin y se subirá al repositorio que mencionaremos más adelante.
- **Software Deployment**
Se realizará la implementación y ejecución de las aplicaciones y servicios en la plataforma de nube de Microsoft, la cual permite escalabilidad y la correcta administración de los recursos creados.
-  **Software Documentation**
Para realizar la documentación del lenguaje de programación Java nos podemos guiar de páginas como Oracle u otras similares. En cualquier caso, es una buena práctica documentar cada servicio para ofrecer un mayor entendimiento a los futuros programadores o en caso se tenga que volver a revisar una implementación previa.

### 7.1.2. Source Code Management 
Para el proyecto que estamos realizando usaremos el sistema de control de versiones Git el cual se verá evidenciado en la plataforma Github ya que nos permite visualizar los cambios hechos en cada versión de manera didáctica y ordenada.
El repositorio creado será gestionado con GitFlow el cual supone tener cinco ramas, sin embargo, en el repositorio solo se mostrarán tres de ellas ya que serán las que tengan los cambios más significativos en nuestro proceso de construcción del proyecto. Los branches que mostraremos en el repositorio de GitHub serán:
**Main:** contendrá las versiones oficiales y estables de nuestro proyecto.
**Develop:** será conformada por todos los features que se vinieron desarrollando para que cuando creamos que está lista para el siguiente paso sea fusionada con la rama reléase.
**Release:** contendrá el código que será publicado oficialmente y será un paso previo antes de pasar a la rama main.
**Feature:** será una rama individual por cada integrante donde suban la parte del código que corresponde a la funcionalidad designada. Cada una de estas será fusionada con la rama _develop_.
$feature <nombre -integrante>/<pequeña-descripción>$
 El nombramiento de los releases se hará teniendo en cuenta el versionamiento semántico 2.0.0 con el cual podremos saber cómo nombrar a nuestras diferentes versiones del proyecto.
 $Mayor.Menor.Parche$
 **El último dígito (Parche):** se utilizará para indicar que hubo un parche. Solo para indicar que se arreglaron algunos errores mas no hubo cambios grandes.
**El segundo dígito (Menor):** se cambiará (aumentará) para indicar que se añadieron características al proyecto que son compatibles con la versión pasada. Si este dígito aumenta, el número del parche empezará en 0.
**El primer dígito (Mayor):** Aumentará cada vez que haya un cambio significativo y además cuando la versión actual no sea compatible con la versión anterior.
Por último, se hará uso de conventional commits para los textos de mensajes en cada commit que se realice. La estructura es la siguiente:
$<type>[optional scope]: <description>$
$[optional body]$
$[optional footer(s)]$
Sin embargo, para este trabajo, por lo general se usará la siguiente estructura que es similar a la mostrada anteriormente:
$<type>: <description>$
Con respecto a los repositorios que usaremos en el proyecto, serán los siguientes:
**Repositorio Frontend Applications**
![Repositorio Frontend Applications](img/Capitulo_7/Software_Configuration_Management/2.png)
Link en github: [Frontend Web Applications](https://github.com/Arquitectura-WS82/frontend-web-applications)
**Repositorio Microservices**
![Repositorio Microservices](img/Capitulo_7/Software_Configuration_Management/3.png)
Link en github: [Microservices](https://github.com/Arquitectura-WS82/web-services)
**Repositorio Landing Page**
![Repositorio Landing Page](img/Capitulo_7/Software_Configuration_Management/4.png)
Link en github: [Landing Page](https://github.com/Arquitectura-WS82/landing-page)
Los tests de aceptación serán subidos al siguiente repositorio:
**Repositorio Acceptance Tests**
![Repositorio Acceptance Tests](img/Capitulo_7/Software_Configuration_Management/5.png)
Link en github: [Acceptance Tests](https://github.com/Arquitectura-WS82/acceptance-tests)
 
### 7.1.3. Source Code Style Guide & Conventions 
Para el desarrollo de código, se tiene planeado utilizar las convenciones descritas en, Gherkin Conventions for Readable Specifications, Google Java Style Guide y Code Style Java de IntelliJ.
**Principales referencias y convenciones adoptadas o por adoptar en la realización del proyecto:**
**JAVA**
-  Los modificadores de clase y miembro, cuando están presentes, aparecen en el orden recomendado por la especificación del lenguaje Java:
$public$ $protected$ $private$ $abstract$ $default$ $static$ $final$ $transient$ $volatile$ $synchronized$ $native$ $strictfp$
-  Se usa UpperCamelCase para el nombre de las clases.
$ThisIsAnExample$
$thisIsNotAnExample$
- Se usa lowerCamelCase para el nombre de los métodos y parámetros.
$thisIsAnExample$
$ThisIsNotAnExample$

**GHERKIN**
Para los archivos. feature se utilizó el lenguaje Gherkin.
- **Contar con bloques discernibles de Given-When-Then**, los cuales terminaran aplicando el And y un espacio, para tener una fácil detección de donde termina y donde comienza un bloque.
_Bloques discernibles en Gherkin_
![Bloques discernibles](img/Capitulo_7/Software_Configuration_Management/6.png)
- **Utilizar comillas simples,** para poder identificar los parámetros en un paso.
_Comillas simples en Gherkin_
![Comillas Simples](img/Capitulo_7/Software_Configuration_Management/7.png)
### 7.1.4. Software Deployment Configuration 
Para la configuración de despliegue del proyecto en curso, se utilizará Eureka por las siguientes razones: 
- **Registro de Servicios:** Eureka permite que los microservicios se registren automáticamente en un servidor Eureka cuando se inician. Esto significa que cada microservicio que se ejecuta puede hacerse visible para otros componentes de la aplicación.
- **Descubrimiento de Servicios:** Los microservicios pueden consultar el servidor Eureka para obtener información actualizada sobre la ubicación y la disponibilidad de los servicios que necesitan invocar. Esto elimina la necesidad de que los clientes conozcan las direcciones IP o los puertos de los servicios, lo que facilita la comunicación dinámica entre microservicios.
- **Balanceo de Carga:** Eureka se integra fácilmente con balanceadores de carga, lo que permite una distribución equilibrada de las solicitudes entre múltiples instancias de un servicio. Esto mejora la escalabilidad y la disponibilidad de los servicios, ya que las solicitudes se distribuyen de manera uniforme.
![Springboot](img/Capitulo_7/Software_Configuration_Management/8.png)
Para utilizarlo, será necesario importar las dependencias en los servicios de registro, de gateway y los servicios de la solución como podrían ser el de clients, carriers, hiring, etc.
![Dependencies](img/Capitulo_7/Software_Configuration_Management/9.png)
Finalmente, al ejecutar los servicios e ingresar al localhost:8099, aquellos que se han registrado se mostrarán en una tabla al igual que el estado en que se encuentran.

## 7.3. Validation Interviews

Para esta versión del informe hemos realizado entrevistas de validación a nuestros usuarios las cuales se verán a continuación empezando desde el diseño de entrevistas hasta las entrevistas en sí.

### 7.3.1. Diseño de Entrevistas

Para esta versión hemos diseñado y realizado las siguientes preguntas a nuestros usuarios:

- ¿Te gustó la aplicación? ¿Qué parte de la aplicación te gustó más?

- ¿Qué funcionalidad quisieras añadir?

- ¿Hay algún apartado que mejorarías?

- ¿Considera que nuestra aplicación puede competir con las aplicaciones del mercado actual?

- ¿Recomendarías esta aplicación?

### 7.3.2. Registro de Entrevistas

En esta version, hemos realizado las entrevistas que se pueden visualizar en el siguiente link en Microsoft stream: 
https://upcedupe-my.sharepoint.com/:v:/g/personal/u20201b846_upc_edu_pe/EXawTnrPuoRNgQ8vTCSmKLsBbhP_2xHzFfKLvu1GpHRkow?e=vGZCNW

#### Entrevista N° 1

|![Entevista 1 - Validation](img/Capitulo_7/Validation_Interviews/Registro_de_entrevistas/E01.PNG)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
| --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <u>**Datos del entrevistado**</u> <br><br>   **Nombre y apellidos:** Ricardo Vilca<br>   **Distrito:** Ventanilla<br>   **Segmento:** Transportista<br><br>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
| Ricardo es una persona de 25 años quien se dedica al rubro de transporte y trabaja con mayor frecuencia los fines de semana pues es ahí cuando dice obtener mayores ganancias. Ricardo ha tenido la oportunidad de interactuar con la aplicación web que hemos desarrollado y siente que ha sido muy intuitivo y fácil de manejar. La parte que más le gustó fue la parte de las notificaciones porque es muy visible la diferenciación de los estados del contrato. Con respecto a la funcionalidad que quisiera añadir, no lo tiene muy claro pero le gustaría tenerla en una versión móvil. Piensa que puede competir con las aplicaciones del mercado actual y que se pasaría la voz muy rápido entre los transportistas si esta aplicación llega a ser tan beneficiosa como cree que es. |
| **Minuto:** 09:25 – 19:00                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |

#### Entrevista N° 2

| ![Entevista 2 - Validation](img/Capitulo_7/Validation_Interviews/Registro_de_entrevistas/E02.PNG)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
| --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <u>**Datos del entrevistado**</u> <br><br>   **Nombre y apellidos:** Carlos Sanchez<br>   **Distrito:** Ventanilla<br>   **Segmento:** Transportista<br><br>   |
| El entrevistado se llama Carlos Sanchez y reside en Ventanilla, él cabe en el segmento objetivo de Transportista, debido a que en sus vacaciones suele trabajar como ayudante en el servicio de transportar mercadería y realizar mudanzas. En primer lugar, él nos comenta que la aplicación le gustó mucho y que considera que tiene las funcionalidades necesarias para que pueda utilizarla en sus actividades como transportista. En segundo lugar, menciona que la parte más importante para él son los contratos y que el mejoraría la sección del perfil, debido a que está algo desordenado y no se ve tan estético. Por último, dice que si la recomendaría a sus amigos o conocidos.|
| **Minuto:** 00:00 – 09:24 |

#### Entrevista N° 3

| ![Entevista 3 - Validation](img/Capitulo_7/Validation_Interviews/Registro_de_entrevistas/E03.PNG)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
| --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <u>**Datos del entrevistado**</u> <br><br>   **Nombre y apellidos:** Diego Seminario<br>   **Distrito:** Cercado de Lima<br>   **Segmento:** Transportista<br><br>   |
| El entrevistado se llama Diego Seminario y reside Cercado de Lima, él indica considera que la aplicación mostrada fue sencilla de utilizar y bastante intuitiva. Sin embargo, cree que se podría añadir la acción de acceder al perfil de un Transportista al clickear en su nombre o foto, en lugar de hacerlo mediante un botón extra. |
| **Minuto:** 19:00 – 25:04 |

#### Entrevista N° 4

| ![Entevista 4 - Validation](img/Capitulo_7/Validation_Interviews/Registro_de_entrevistas/E04.PNG)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
| --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <u>**Datos del entrevistado**</u> <br><br>   **Nombre y apellidos:** Sergio Liberato<br>   **Distrito:** Huacho<br>   **Segmento:** Cliente<br><br>   |
| Sergio de 20 años es hijo de unos comerciantes de vendedores de Frutos secos el cual apoya en el ciclo de comercio de su producto. En relación con la entrevista este encuentra relación de nuestra aplicación con Uber pero que nosotros tenemos un mercado más amplio. Y que esto puede llegar a tener una aplicación para los mercados o para su negocio familiar, ya que en Uber se enfoca en personas. Lo ve más relacionado a su rubro ya que él realiza una búsqueda de transportista para el traslado de sus productos para la venta, cada cierto tiempo. Lo que nos comentó como aspecto a mejorar es hallar una sección de mensajería o de argumentar la razón del rechazo de la oferta laboral, después de eso lo ve perfecto como anda quedando nuestra aplicación. |
| **Minuto:** 25:04 – 35:50 |

#### Entrevista N° 5

| ![Entevista 5 - Validation](img/Capitulo_7/Validation_Interviews/Registro_de_entrevistas/E05.PNG)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
| --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <u>**Datos del entrevistado**</u> <br><br>   **Nombre y apellidos:** Italo Sabino<br>   **Distrito:** Callao<br>   **Segmento:** Cliente<br><br>   |
| Italo es comerciante de útiles escolares con 23 años, quien suele necesitar de transporte para su mercadería. En relación con la entrevista, él menciona que la parte que más le gustó dentro de las características de la aplicación fue que la aplicación se ve amigable y fácil de usar. Otro aspecto que le gustó fue la versatilidad que tiene la aplicación. Por otra parte, nos menciona que le gustaría tener un sistema de mensajería directa con el transportista. Finalmente, Italo nos menciona que nuestra aplicación cuenta con todas las características suficientes o incluso más funcionalidades como para competir con aplicaciones del mercado actual y el piensa que con un precio menor a la del mercado podremos competir directamente contra aplicaciones que se dedican a este rubro. Así mismo, afirma que por supuesto recomendaría nuestra aplicación. |
| **Minuto:** 45:39 – 50:10 |

#### Entrevista N° 6

| ![Entevista 6 - Validation](img/Capitulo_7/Validation_Interviews/Registro_de_entrevistas/E06.PNG)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
| --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <u>**Datos del entrevistado**</u> <br><br>   **Nombre y apellidos:** Alexandro Villarruel <br>   **Distrito:** Villa El Salvador<br>   **Segmento:** Cliente<br><br>   |
| Alexandro es comerciante de productos textiles con 24 años, quien constantemente requiere de servicios de transporte para su mercadería. En relación con la entrevista, él menciona que la parte que más le gusto dentro de las características de la aplicación fue que tiene muchas funcionalidades donde el usuario puede tener cierta interacción con la aplicación. Otro aspecto que le gusto fue que le resulto fácil de usar. Por otra parte, Alex menciona que no encuentra una funcionalidad que no esté entre sus necesidades. Finalmente, el usuario nos menciona que nuestra aplicación si cuenta con las funcionalidades necesarias para competir, por más de estar en una etapa de inicio tiene potencial para competir con aplicaciones del mercado actual. Así mismo, afirma que por supuesto recomendaría nuestra aplicación. |
| **Minuto:** 35:50 – 45:38 |

### 7.3.3. Evaluaciones según heuristicas
Para este informe, se han realizado las siguientes heurísticas en base al feedback obtenido por las usuarios en las entrevistas. 

**Site o APP a evaluar:** FastPorte de TechCompany

**TAREAS A EVALUAR:**

El alcance de esta evaluación incluye la revisión de la usabilidad de las siguientes tareas:

1. Perfil del usuario
1. Header de la aplicación web
1. Sección Contratos
1. Buscar vehículo

No están incluidas en esta versión de la evaluación las siguientes tareas:

1. Registro de usuario
1. Inicio de sesión
1. Edición de perfil
1. Métodos de pago
1. etc.


ESCALA DE SEVERIDAD:

|Nivel |Descripción|
| :- | :- |
|1|Problema superficial: puede ser fácilmente superado por el usuario o ocurre con muy poca frecuencia. No necesita ser arreglado a no ser que exista disponibilidad de tiempo.|
|2|Problema menor: puede ocurrir un poco más frecuentemente o es un poco más difícil de superar para el usuario. Se le debería asignar una prioridad baja resolverlo de cara al siguiente reléase|
|3|Problema mayor: ocurre frecuentemente o los usuarios no son capaces de resolverlos. Es importante que sean corregidos y se les debe asignar una prioridad alta.|
|4|Problema muy grave: un error de gran impacto que impide al usuario continuar con el uso de la herramienta. Es imperativo que sea corregido antes del lanzamiento. |

TABLA RESUMEN:

|#|Problema|Escala de severidad|Heurística/Principio violada(o)|
| :- | :- | :- | :- |
|1|No existe una función de Log out|4|Usabilidad: Flexibilidad y eficiencia en el uso|
|2|Visualmente más ordenado (My Profile)|1|Usabilidad: Diseño estético y minimalista.|
|3|No existe una sección de mensajes directos|2|<p>Information Architecture: Is it</p><p>valuable?</p>|
|4|Más información en Search Vehicle sobre los servicios del transportista|2|Usabilidad: Diseño estético y minimalista.|

DESCRIPCIÓN DE PROBLEMAS:

##### **PROBLEMA #1:** No existe una función de Log out

Severidad: 4

Heurística violada: Usabilidad: Flexibilidad y eficiencia en el uso

**Problema:** 
Los usuarios pueden iniciar sesión o registrarse en la aplicación de manera exitosa. Asimismo, pueden navegar por esta sin problemas. Sin embargo, cuando desean salir de su cuenta y dejar de hacer uso de la aplicación no pueden, ya que no existe ninguna opción para salir de su cuenta.

![P01](img/Capitulo_7/Validation_Interviews/Heuristicas/P01.PNG)

**Recomendación:** 
Crear una opción “Log Out” en el header de la aplicación para que los usuarios puedan cerrar la sesión de cuenta cuando ya no vayan a hacer uso de la aplicación.

##### *PROBLEMA #2:** Visualmente más ordenado (My Profile)

Severidad: 1

Heurística violada: Usabilidad: Diseño estético y minimalista.

**Problema:**
Un entrevistado indicó que en el apartado del perfil no se ven uniformes las casillas donde se muestra la información del usuario. Esto resulta antiestético y hace un poco complicado disfrutar de la aplicación.

![P02](img/Capitulo_7/Validation_Interviews/Heuristicas/P02.PNG)

**Recomendación:**
Se recomienda cambiar el CSS del componente encargado de la sección de Información, quizá intercambiando Flex por Grid para poder definir el espacio que ocupará cada etiqueta de dicha sección.

##### **PROBLEMA #3:** No existe una sección de mensajes directos

Severidad: 2

Principio violado: Information Architecture: Is it valuable?

**Problema:**
Un entrevistado indicó que le gustaría tener una sección de mensajes directos con el transportista que contrato, ya que eso facilita la comunicación entre ambas partes.

![P03](img/Capitulo_7/Validation_Interviews/Heuristicas/P03.PNG)


**Recomendación:**
Si bien se puede implementar una sección de mensajes directos, los usuarios pueden acceder al perfil de los transportistas, lo cual les permitirá ver sus métodos de contacto como su correo electrónico o su número de celular.




##### **PROBLEMA #4:** Más información en Search Vehicle sobre el driver 

Severidad: 2

Heurística violada: Usabilidad: Diseño estético y minimalista.

**Problema:** 
Un usuario entrevistado indicó que le gustaría ver más información acerca de los servicios del transportista al momento de realizar la búsqueda, debido a que la descripción brindada no le sirve de mucho.

![P04](img/Capitulo_7/Validation_Interviews/Heuristicas/P04.PNG)


**Recomendación:**
Se sugiere cambiar la información mostrada en los cards, en lugar de mostrar la descripción del transportista mostrar más información sobre los servicios que ofrece. Sin embargo, esto también se puede solucionar mostrando un dialog, al realizar una búsqueda por primera vez, el cual indique puede acceder a mayor información del transportista por medio del botón “See Profile”

## 7.4. VídeoAbout-the-Product
Para la sección about the product se ha realizado el siguiente vídeo:

Link para su visualización: 

---

# Conclusiones

- El desarrollo del Lean UX Process ayudó a comprender mejor y aplicar efectivamente las herramientas en nuestra propuesta enfocada al servicio de transportistas hacia clientes. De la misma forma, contribuyó a definir de manera más clara nuestro público objetivo o llámese segmento hacia el cual va enfocada nuestra aplicación.
- Después de culminar la primera parte de nuestro proyecto e identificar los principales problemas que tienen nuestros segmentos, concluimos que sería de mucha ayuda el desarrollo de FastPorte con el fin de mejorar la experiencia de los transportistas al momento de ofrecer sus servicios, al igual que a los clientes sería una herramienta eficiente en su trabajo.
- El desarrollo de entrevistas nos ayudó a esclarecer la visión del proyecto, en cuanto a la perspectiva del usuario y por lo tanto fue importante para mejorar los aspectos de las funcionalidades de la aplicación.
- La transición a microservicios y la contenerización con Docker ha mejorado significativamente la modularidad del sistema. Cada microservicio puede desarrollarse, probarse e implementarse de manera independiente, lo que facilita la escalabilidad y el mantenimiento a largo plazo. Esta arquitectura modular también permite la adopción de tecnologías específicas para cada servicio.
- La contenerización y el uso de orquestadores como Kubernetes han proporcionado un entorno de despliegue más consistente y predecible. Ahora podemos implementar actualizaciones y mejoras de manera más rápida y eficiente, reduciendo el tiempo de inactividad y mejorando la experiencia del usuario. La capacidad de realizar implementaciones continuas se ha vuelto más factible.
- Aunque la arquitectura de microservicios ofrece ventajas claras, también presenta desafíos en la gestión de la complejidad. La coordinación entre microservicios, la configuración adecuada de las relaciones entre ellos y la gestión de versiones son aspectos críticos que requieren atención constante. Además, es esencial tener un equipo bien capacitado y una documentación completa para abordar estos desafíos de manera efectiva.

---
# Recomendaciones

- Se recomienda realizar los diagramas C4 con el lenguaje de programación C# y usando el módulo de Structurizr.Client en Nuget. Esto con el fin de poder gestionar las versiones de la arquitectura realizada. Asimismo, para poder realizar una mejor documentación de cada uno de los servicios implementados.
- Asegurarse de tener una documentación clara y accesible para cada microservicio. Esto facilitará la comprensión y colaboración del equipo, así como la integración de nuevos miembros. Utiliza un formato fácil de seguir, destacando los puntos clave sobre la funcionalidad, API y dependencias.
- Implementar pruebas rigurosas para cada microservicio antes y después de la contenerización. Las pruebas unitarias, de integración y funcionales son fundamentales. Garantizar la estabilidad y la funcionalidad adecuada en un entorno contenerizado minimizará problemas en el despliegue y mejorará la confianza en el sistema.
- Implementar un sólido plan de respaldo y recuperación para los datos de los microservicios. Utilizar soluciones automatizadas para realizar copias de seguridad periódicas y verificar regularmente la capacidad de restauración. Y así lograr un enfoque proactivo hacia la gestión de datos garantizará la integridad y disponibilidad del sistema en caso de fallos inesperados.

--- 
# Anexos
## Repositorio con Informe
Enlace: [Repositorio Trabajo Final](https://github.com/Arquitectura-WS82/TrabajoFinal)
## Entrega TB1
Enlace: [Exposición TB1 en Microsoft Stream](https://upcedupe-my.sharepoint.com/:v:/g/personal/u20201c172_upc_edu_pe/Ec1gj2b9GwhMiIeeW4ZbOQUBjR8V_vwBKCj4ByvhRvIVLg?nav=eyJyZWZlcnJhbEluZm8iOnsicmVmZXJyYWxBcHAiOiJTdHJlYW1XZWJBcHAiLCJyZWZlcnJhbFZpZXciOiJTaGFyZURpYWxvZy1MaW5rIiwicmVmZXJyYWxBcHBQbGF0Zm9ybSI6IldlYiIsInJlZmVycmFsTW9kZSI6InZpZXcifX0%3D&e=mEYRo9)

## Entrega TP

Enlace: [Exposición TP en Microsoft Stream](https://upcedupe-my.sharepoint.com/:v:/g/personal/u20201c172_upc_edu_pe/Ee3gKoJcxupDoCe8-pI8Cb0BtfJhZUx52-sbBh5ShCEz-w?e=pR0RiA)