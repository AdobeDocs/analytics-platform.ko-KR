---
title: Customer Journey Analytics 시작하기
description: Customer Journey Analytics를 시작합니다.
translation-type: ht
source-git-commit: fb2b5868db69bfff3345abcd69b0b70112fdcf3c

---


# Customer Journey Analytics 시작하기

Customer Journey Analytics를 구현하려면 이 워크플로우를 따라야 합니다. 일부 초기 작업은 Adobe Experience Platform에서 수행되고, 일부는 Customer Journey Analytics에서 수행됩니다.

| 작업 | 수행 위치 | 세부 사항 |
|---|---|---|
| **1단계: Adobe Experience Platform으로 데이터 가져오기** | Adobe Experience Platform | 데이터 업로드를 위한 그래픽 인터페이스 및 API를 포함하여 스트리밍과 배치 사용 사례에 대한 데이터를 수집하는 방법에는 여러 가지가 있습니다. Experience Platform은 다음과 같은 위치에서 데이터를 가져올 수 있습니다.<ul><li>S3 스토리지</li><li>Azure Blob 저장소</li><li>Kafka 스트림</li><li>SFTP 전송</li><li>CSV 파일 업로드</li><li>JSON 파일 업로드</li></ul> |
| **2단계: 데이터 스키마 준비하기** | Adobe Experience Platform | [XDM(Adobe Experience Data Model)](https://www.adobe.io/apis/experienceplatform/home/xdm.html)을 사용하여 고객 경험 데이터를 표준화하고 고객 경험 관리를 위한 스키마를 정의할 수 있습니다. |
| **3단계: 스키마를 기반으로 하여 데이터 세트 만들기** | Adobe Experience Platform | 플랫폼의 데이터는 이메일 데이터 세트, CRM 데이터 세트, POS 데이터 세트, Adobe Analytics 데이터 세트 등과 같은 데이터 세트로 구성됩니다. 각 데이터 세트는 스키마와 데이터 배치로 구성됩니다. [Experience Platform](https://www.adobe.io/apis/experienceplatform/home/tutorials/alltutorials.html#!api-specification/markdown/narrative/tutorials/creating_a_dataset_tutorial/creating_a_dataset_tutorial.md)에서 데이터 세트를 만들 수 있습니다.<br>Customer Journey Analytics로 가져올 수 있는 데이터 세트에 대한 스키마가 유연하지만 일부 기본 규칙을 준수해야 합니다. Platform으로 업로드하기 전에 데이터가 이러한 요구 사항을 충족하는지 확인하는 것이 가장 좋습니다. 스키마에는 지표와 차원이 모두 포함됩니다.<br>Customer Journey Analytics와 호환되는 데이터 유형은 다음 세 가지가 있습니다.<ul><li>**이벤트 데이터**: 시간에 따라 이벤트를 나타내는 데이터(예: 웹 방문, 상호 작용, 거래, POS 데이터, 설문 조사 데이터, 광고 노출 데이터 등)입니다. 고객 ID 또는 쿠키 ID와 타임스탬프가 있는 일반적인 클릭스트림 데이터입니다. 이벤트 데이터를 사용하면 원하는 ID를 사용할 수 있습니다.</li><li>**조회 데이터**: 이 데이터는 이벤트 또는 프로필 데이터에 있는 값 또는 키를 조회하는 데 사용됩니다. 예를 들어 이벤트 데이터의 숫자 ID를 제품 이름에 매핑하는 조회 데이터를 업로드할 수 있습니다.</li><li>**프로필 데이터**: 이벤트 데이터의 방문자, 사용자 또는 고객에게 적용되는 데이터입니다. 예를 들어 고객에 대한 CRM 데이터를 업로드할 수 있습니다.</li></ul> |
| **4단계: 플랫폼 데이터 세트와 Customer Journey Analytics 간 연결 만들기** | Customer Journey Analytics | [연결 만들기](/help/connections/create-connection.md)를 참조하십시오. |
| **5단계: 데이터 보기 만들기** | Customer Journey Analytics | [데이터 보기 만들기](/help/data-views/create-dataview.md)를 참조하십시오. |
| **6단계: Workspace에서 교차 채널 데이터 보고하기** | Customer Journey Analytics | [기본 분석 수행](/help/projects/perform-basic-analysis.md) 및 [고급 분석 수행](/help/projects/perform-adv-analysis.md)을 참조하십시오. |

## 전제 조건

Customer Journey Analytics를 사용할 수 있는 고객은 다음과 같습니다.

* Adobe Analytics [Select, Prime 또는 Ultimate](https://www.adobe.com/kr/analytics/compare-adobe-analytics-packages.html) 고객 및
* [Adobe Experience Platform](https://www.adobe.com/kr/experience-platform.html)이 프로비저닝된 고객 및
* Customer Journey Analytics SKU를 구입한 고객

## 데이터 스키마 준비하기

[스키마 편집기를 사용하여 스키마 만들기](https://www.adobe.io/apis/experienceplatform/home/tutorials/alltutorials.html#!api-specification/markdown/narrative/tutorials/schema_editor_tutorial/schema_editor_tutorial.md)

## 1단계: Adobe Experience Platform으로 데이터 가져오기

CJA에서 Experience Platform 데이터를 활용하려면 먼저 해당 데이터를 Platform으로 수집해야 합니다. 다음과 같은 여러 가지 방법으로 데이터를 수집할 수 있습니다.

* 기존 Adobe Analytics 데이터를 가져오려면 Adobe Analytics Platform 커넥터를 사용하십시오.
* 다른 데이터를 수집하려면 S3 스토리지, Azure Blob 저장소, Kafka 스트림, SFTP 전송, CSV 파일 업로드, JSON 파일 업로드와 같은 형식을 사용합니다.

### 1a단계: 기존 Analytics 데이터를 Adobe Experience Platform으로 가져오기

최신 Adobe Analytics Platform 커넥터를 사용하여 기존 Adobe Analytics 데이터를 Platform으로 가져옵니다. 보고서 세트당 하나의 소스 연결을 만들 수 있습니다. Adobe Experience Platform 설명서의 [Adobe Analytics와 소스 연결 만들기](https://www.adobe.io/apis/experienceplatform/home/tutorials/alltutorials.html#!api-specification/markdown/narrative/tutorials/sources_tutorial/adobe-analytics-ui-tutorial.md)를 참조하십시오.

연결이 만들어지면 들어오는 데이터를 포함하도록 대상 스키마와 데이터 세트가 자동으로 생성됩니다. 또한 데이터 다시 채우기가 발생하고 최대 13개월 동안의 이전 데이터가 수집됩니다. 초기 수집이 완료되면 `Step 4`를 진행하여 이 Analytics 데이터 세트와 Customer Journey Analytics 간의 연결을 만들 수 있습니다.

### 1b단계: 다른 데이터 유형 수집

[배치 수집](https://www.adobe.io/apis/experienceplatform/home/data-ingestion/data-ingestion-services.html#!api-specification/markdown/narrative/technical_overview/ingest_architectural_overview/ingest_architectural_overview.md) 기능을 사용하면 데이터를 배치 파일로 Experience Platform에 수집할 수 있습니다. 배치는 단일 단위로 수집할 하나 이상의 파일로 구성된 데이터 단위입니다. 배치가 수집되면 배치는 성공적으로 수집된 레코드 수와 실패한 레코드 수 및 관련 오류 메시지를 설명하는 메타데이터를 제공합니다. 플랫 .CSV 파일(XDM 스키마에 매핑됨) 및 Parquet 데이터 프레임처럼 수동으로 업로드한 데이터 파일은 이 방법을 사용하여 수집해야 합니다.

[스트리밍 수집](https://www.adobe.io/apis/experienceplatform/home/data-ingestion/data-ingestion-services.html#!api-specification/markdown/narrative/technical_overview/streaming_ingest/streaming_ingest_overview.md) 기능을 사용하여 클라이언트 및 서버측 장치에서 실시간으로 Experience Platform으로 데이터를 보낼 수 있습니다.

[다른 소스 커넥터](https://www.adobe.io/apis/experienceplatform/home/data-ingestion/data-ingestion-services.html#!api-specification/markdown/narrative/technical_overview/acp_connectors_overview/acp-connectors-overview.md)를 사용하여 외부 소스에서 데이터를 수집할 수 있으며 Platform 서비스를 사용하여 들어오는 데이터를 구조화, 레이블 지정 및 향상시키는 기능을 제공할 수 있습니다. Adobe 애플리케이션(Adobe Analytics, Audience Manager, Experience Platform Launch, Target), 클라우드 기반 스토리지(Azure Blob, Amazon S3, FTP/SFTP, Google Cloud 스토리지), 타사 소프트웨어 및 CRM(Microsoft Dynamics 365, Salesforce)과 같은 다양한 소스에서 데이터를 수집할 수 있습니다.

## 2단계: 데이터 스키마 준비하기

bnbnbnbn
