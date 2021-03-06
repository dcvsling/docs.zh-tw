

# [.NET 微服務：容器化 .NET 應用程式的架構](index.md)


## [容器和 Docker 簡介](container-docker-introduction/index.md)


### [什麼是 Docker？](container-docker-introduction/docker-defined.md)


### [Docker 術語](container-docker-introduction/docker-terminology.md)


### [Docker 容器、影像和登錄](container-docker-introduction/docker-containers-images-registries.md)


## [針對 Docker 容器在 .NET Core 和 .NET Framework 之間進行選擇](net-core-net-framework-containers/index.md)


### [一般指引](net-core-net-framework-containers/general-guidance.md)


### [針對 Docker 容器選擇 .NET Core 的時機](net-core-net-framework-containers/net-core-container-scenarios.md)


### [針對 Docker 容器選擇 .NET Framework 的時機](net-core-net-framework-containers/net-framework-container-scenarios.md)


### [決策表：用於 Docker 的 .NET Frameworks](net-core-net-framework-containers/container-framework-choice-factors.md)


### [針對 .NET 容器要設為目標的作業系統](net-core-net-framework-containers/net-container-os-targets.md)


### [官方 .NET Docker 映像](net-core-net-framework-containers/official-net-docker-images.md)


## [架構容器和微服務應用程式](architect-microservice-container-applications/index.md)


### [容器化整合型應用程式](architect-microservice-container-applications/containerize-monolithic-applications.md)


### [Docker 應用程式中的狀態和資料](architect-microservice-container-applications/docker-application-state-data.md)


### [服務導向架構](architect-microservice-container-applications/service-oriented-architecture.md)


### [微服務架構](architect-microservice-container-applications/microservices-architecture.md)


### [每個微服務的資料統治權](architect-microservice-container-applications/data-sovereignty-per-microservice.md)


### [邏輯架構與實體架構](architect-microservice-container-applications/logical-versus-physical-architecture.md)


### [分散式資料管理的挑戰和解決方案](architect-microservice-container-applications/distributed-data-management.md)


### [識別每個微服務的網域模型界限](architect-microservice-container-applications/identify-microservice-domain-model-boundaries.md)


### [微服務之間的通訊](architect-microservice-container-applications/communication-between-microservices.md)


### [非同步訊息通訊](architect-microservice-container-applications/asynchronous-message-based-communication.md)


### [建立、發展以及版本化微服務 API 和合約](architect-microservice-container-applications/maintain-microservice-apis.md)


### [微服務可定址性和服務登錄](architect-microservice-container-applications/microservices-addressability-service-registry.md)


### [根據微服務建立複合 UI，包括多個微服務所產生的虛擬 UI 形狀和配置](architect-microservice-container-applications/microservice-based-composite-ui-shape-layout.md)


### [微服務中的復原和高可用性](architect-microservice-container-applications/resilient-high-availability-microservices.md)


### [協調微服務和多容器應用程式的高延展性和可用性](architect-microservice-container-applications/scalable-available-multi-container-microservice-applications.md)


### [使用 Azure Service Fabric](architect-microservice-container-applications/using-azure-service-fabric.md)


## [Docker 應用程式的開發程序](docker-application-development-process/index.md)


### [Docker 應用程式的開發工作流程](docker-application-development-process/docker-app-development-workflow.md)


## [在 Linux 或 Windows Nano Server 主機上部署單一容器 NET Core Web 應用程式](net-core-single-containers-linux-windows-server-hosts/index.md)


## [將舊版整合型 NET Framework 應用程式移轉至 Windows 容器](containerize-net-framework-applications/index.md)


## [設計和開發多容器和微服務 NET 應用程式](multi-container-microservice-net-applications/index.md)


### [設計微服務導向應用程式](multi-container-microservice-net-applications/microservice-application-design.md)


### [建立簡單資料驅動 CRUD 微服務](multi-container-microservice-net-applications/data-driven-crud-microservice.md)


### [使用 docker-compose.yml 定義多容器應用程式](multi-container-microservice-net-applications/multi-container-applications-docker-compose.md)


### [使用作為容器執行的資料庫伺服器](multi-container-microservice-net-applications/database-server-container.md)


### [實作微服務之間的事件通訊 (整合事件)](multi-container-microservice-net-applications/integration-event-based-microservice-communications.md)


### [針對開發或測試環境使用 RabbitMQ 實作事件匯流排](multi-container-microservice-net-applications/rabbitmq-event-bus-development-test-environment.md)


### [訂閱事件](multi-container-microservice-net-applications/subscribe-events.md)


### [測試 ASP.NET Core 服務和 Web 應用程式](multi-container-microservice-net-applications/test-aspnet-core-services-web-apps.md)


## [解決具有 DDD 和 CQRS 模式之微服務中的商務複雜度](microservice-ddd-cqrs-patterns/index.md)


### [在微服務中套用簡化 CQRS 和 DDD 模式](microservice-ddd-cqrs-patterns/apply-simplified-microservice-cqrs-ddd-patterns.md)


### [在 eShopOnContainers 的 DDD 微服務中套用 CQRS 和 CQS 方式](microservice-ddd-cqrs-patterns/eshoponcontainers-cqrs-ddd-microservice.md)


### [在 CQRS 微服務中實作讀取/查詢](microservice-ddd-cqrs-patterns/cqrs-microservice-reads.md)


### [設計 DDD 導向微服務](microservice-ddd-cqrs-patterns/ddd-oriented-microservice.md)


### [設計微服務網域模型](microservice-ddd-cqrs-patterns/microservice-domain-model.md)


### [使用 .NET Core 實作微服務網域模型](microservice-ddd-cqrs-patterns/net-core-microservice-domain-model.md)


### [Seedwork (網域模型的可重複使用基底類別和介面)](microservice-ddd-cqrs-patterns/seedwork-domain-model-base-classes-interfaces.md)


### [實作值物件](microservice-ddd-cqrs-patterns/implement-value-objects.md)


### [使用列舉類別，而非列舉類型](microservice-ddd-cqrs-patterns/enumeration-classes-over-enum-types.md)


### [設計網域模型層中的驗證](microservice-ddd-cqrs-patterns/domain-model-layer-validations.md)


### [用戶端驗證 (展示層中的驗證)](microservice-ddd-cqrs-patterns/client-side-validation.md)


### [網域事件：設計和實作](microservice-ddd-cqrs-patterns/domain-events-design-implementation.md)


### [設計基礎結構持續性層](microservice-ddd-cqrs-patterns/infrastructure-persistence-layer-design.md)


### [實作與 Entity Framework Core 的基礎結構持續性層](microservice-ddd-cqrs-patterns/infrastructure-persistence-layer-implemenation-entity-framework-core.md)


### [使用 NoSQL 資料庫作為持續性基礎結構](microservice-ddd-cqrs-patterns/nosql-database-persistence-infrastructure.md)


### [設計微服務應用程式層和 Web API](microservice-ddd-cqrs-patterns/microservice-application-layer-web-api-design.md)


### [使用 Web API 實作微服務應用程式層](microservice-ddd-cqrs-patterns/microservice-application-layer-implementation-web-api.md)


## [實作復原應用程式](implement-resilient-applications/index.md)


### [處理部分失敗](implement-resilient-applications/handle-partial-failure.md)


### [處理部分失敗的策略](implement-resilient-applications/partial-failure-strategies.md)


### [使用指數輪詢來實作重試](implement-resilient-applications/implement-retries-exponential-backoff.md)


### [實作復原 Entity Framework Core SQL 連線](implement-resilient-applications/implement-resilient-entity-framework-core-sql-connections.md)


### [使用指數輪詢來實作自訂 HTTP 呼叫重試](implement-resilient-applications/implement-custom-http-call-retries-exponential-backoff.md)


### [利用 Polly 使用指數輪詢來實作 HTTP 呼叫重試](implement-resilient-applications/implement-http-call-retries-exponential-backoff-polly.md)


### [實作斷路器模式](implement-resilient-applications/implement-circuit-breaker-pattern.md)


### [健康狀態監視](implement-resilient-applications/monitor-app-health.md)


## [保護 NET 微服務和 Web 應用程式](secure-net-microservices-web-applications/index.md)


### [關於 .NET 微服務和 Web 應用程式中的授權](secure-net-microservices-web-applications/authorization-net-microservices-web-applications.md)


### [在開發期間安全地儲存應用程式密碼](secure-net-microservices-web-applications/developer-app-secrets-storage.md)


### [使用 Azure Key Vault 在實際執行階段保護密碼](secure-net-microservices-web-applications/azure-key-vault-protects-secrets.md)


## [金鑰附帶](key-takeaways.md)
