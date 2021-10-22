<details>
  <summary> Pattern: Microservice Architecture </summary>
  <br/>
  
  Микросервисная архитектура - дизайн патерн проектирования приложений, при котором приложение представляет собой набор независиво развёрнутых сервисов. Чаще используется для проектирования сложных "enterprise" приложений.
  
  Независимые сервисы могут быть написаны на разных языках программирования и могут использовать разные источники хранения данных. Отсюда вытекает первое преимущество: при изменении кодовой базы сервиса не возникнет необходимости собирать и разворачивать полностью всё приложение, достаточно будет ограничиться одним сервисом, где эти изменения происходили. Второе преимущество в более гибком расширении таких приложений, так как сервисы незавимы.
  
  Характерные особенности:
  
  1) Компоненты = сервисы (в противопоставление библиотекам) </br>
     С точки зрения компонентного подхода, сервисы - это внешние по отношению к текущему процессу компоненты, которые общаются посредством запросов от веб-сервисов или RPC (Remote Procedure Call).
     Разделение на сервисы может происходить по принципу бизнес-доменов (domain-driven design) и др.
     Каждый сервис может использовать нужные ему технологии в зависимости от бизнес задачи. 
     В рамках большого приложения над разными сервисами могут работать небольшие многофункциональные команды (дизайнеры, тестировщики, ui-разработчики, backend-разработчики, специалисты по работе с базой данных).
     
  2) Independent deployability </br>
     Сервисы разворачиваются независимо друг от друга (соответственно релизиться тоже могут отдельно). Нужно стремится к тому чтобы сервисы были меньше связаны друг с другом (decoupled), чтобы при изменении одного сервиса не было необходимости менять что-либо ещё. 
 
  3) Smart endpoints and dumb pipes </br>
     Этот подход применяется как альтернатива ESB (Enterprise Service Bus).
     Независимые сервисы = smart endpoints - принимают запросы, обрабатывают их согласно базнес логике и возвращают ответ. Сложная внутренняя имплементация функционала должна быть скрыта (Hexagonal pattern) от интерфейсов, через которые осуществляется взаимодействие с этим функционалом. 
     RESTish protocols = dumb pipes - простые способы взаимодействия.
     
   4) Отдельные базы данных </br>
      Если одному сервису нужны данные из другого сервиса, первый должен запросить эти данные у другого. Это позволит второму сервису определить данные, которые могут быть расшарены или скрыты.
   
  Bottleneck: 
   1) четкие границы между сервисами, которые трудно обойти, что говорит о том, как важно правильно их раставлять
   2) при изменениях интерфейса необходимо учитывать как это повлияет на другие связанные с ним сервисы
   3) ...
     

  Что почитать:
  1. [Microservices](https://martinfowler.com/articles/microservices.html) by Martin Fowler and James Lewis.
  2. [Pattern: Microservice Architecture](https://microservices.io/patterns/microservices.html) by Chris Richardson.
  3. Building Microservices by Sam Newman.
  4. Microservices and Containers by Parminder Kocher.
  
  And you will die 😅

</details>
<br/>
<details>
  <summary> Pattern: Backends For Frontends (API Gateway) </summary>
  <br/>
  
  The API Gateway pattern defines how clients access the services in a microservice architecture.
  
  Что почитать:
  1. [Pattern: Backends For Frontends](https://samnewman.io/patterns/architectural/bff/) by Sam Newman.
  2. [Pattern: API Gateway / Backends for Frontends](https://microservices.io/patterns/apigateway.html) by Chris Richardson.

</details>
<br/>
<details>
  <summary> Pattern: Saga </summary>
  <br/>
  
  Что почитать:
  1. [Pattern: Saga](https://microservices.io/patterns/data/saga.html) by Chris Richardson.

</details>
<br/>
