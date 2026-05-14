---
description: Customer Journey Analytics 및 Adobe Analytics에서 데이터 피드 기능을 비교하는 방법 알아보기
keywords: 클릭스트림, 데이터 피드, 데이터피드, 데이터 피드
title: Customer Journey Analytics 및 Adobe Analytics의 데이터 피드 기능 비교
feature: Components
hide: true
exl-id: 32b71016-7c53-409f-9ce4-521a40e2eb96
source-git-commit: 46d54e388fecac0b62eccfe54fe91620a46474a7
workflow-type: tm+mt
source-wordcount: '934'
ht-degree: 2%

---

# Customer Journey Analytics 및 Adobe Analytics에서 데이터 피드 비교

Customer Journey Analytics 및 Adobe Analytics의 데이터 피드를 사용하면 원시 데이터를 서드파티 플랫폼으로 내보낼 수 있습니다. 이전에 Adobe Analytics에서 데이터 피드를 사용한 적이 있는 경우 다음 정보를 사용하여 사용 가능한 기능과 개념의 차이점을 이해하십시오.

| **개념 및 구성 옵션** | **Customer Journey Analytics** | **Adobe Analytics** |
|---------|----------|---------|
| **데이터 입력**<br/>&#x200B;데이터 피드에 수집 및 포함될 수 있는 데이터 형식입니다. | 웹 데이터, 콜 센터 데이터, 판매 시점 데이터 등을 포함한 크로스 채널 데이터 입력을 지원합니다. | 주로 웹 및 모바일 데이터 입력을 지원합니다. 다른 데이터 유형(예: 콜 센터 또는 판매 시점 데이터)은 데이터 소스를 통해 수집할 수 있지만 처리 기능은 매우 제한적입니다. |
| **데이터 처리**<br/>&#x200B;사용 중인 제품에 따라 다른 단계에서 데이터가 처리됩니다. | 데이터는 **보고 시간**&#x200B;에 처리되므로 결합, 파생 필드 및 세분화와 같은 기록 데이터를 변경하는 데 많은 보고 기능을 사용할 수 있습니다. | 데이터는 **수집 시간**&#x200B;에 처리되므로 처리 규칙 및 VISTA 규칙과 같은 보고 기능은 이전 데이터에 영향을 주지 않습니다. |
| **배달 빈도**<br/>&#x200B;데이터 피드를 보내는 빈도와 피드에 포함된 시간을 결정합니다. | **일별**(데이터 보기의 시간대에 있는 자정부터 자정까지) 또는 **시간별**. | **일별**(보고서 세트 시간대의 자정에서 자정까지) 또는 **시간별**. 15분 피드는 가능하지만 기본적으로 사용할 수 없습니다. |
| **늦게 도착하는 히트**<br/>&#x200B;타임스탬프가 이전 배달 빈도 기간에 속하지만 해당 기간이 이미 지난 후에 도착하는 히트. <p>예를 들어 늦게 도착하는 히트는 오프라인일 때 이벤트를 버퍼링하여 다시 연결할 때 보내는 모바일 앱에서 가져올 수 있습니다.</p> | **처리 지연** 설정은 내보내기를 트리거하기 전에 빈도 창이 닫힌 후 시스템이 대기하는 시간을 제어하여 지연된 데이터가 도착할 때까지 추가 시간을 허용합니다. | 늦게 도착하는 히트는 **늦게 도착하는 히트** 구성 옵션을 통해 **포함 또는 제외**&#x200B;될 수 있습니다. <p>**전환 확인 기간** 설정은 지연된 데이터를 포함하도록 시스템이 도달하는 이전 시간을 제어합니다.</p> |
| **잘못된 히트**<br/>&#x200B;타임스탬프가 받은 순서와 일치하지 않는 히트. | Customer Journey Analytics은 스트리밍과 배치 데이터를 모두 수락하므로 지정된 사용자에 대한 이벤트가 타임스탬프 순서로 도착할 것이라는 보장은 없습니다. Customer Journey Analytics은 보고서 시간에 사람당 타임스탬프별로 데이터를 재정렬합니다. <p>**처리 지연** 설정을 사용하면 내보내기 전에 일괄 처리 데이터가 도착할 수 있는 시간을 더 많이 제공하여 데이터 피드 출력에서 잘못된 이벤트를 줄일 수 있습니다. 게재 시 이벤트 주문은 보장되지 않습니다.</p><p>**중요**: 데이터 피드 배달의 히트 순서가 보장되지 않으므로 데이터 피드 데이터의 최종 소비자는 잘못된 타임스탬프를 개인별로 처리할 수 있어야 합니다.</p> | Adobe Analytics을 사용하려면 수집 시 방문자별로 데이터가 순서대로 도착해야 하지만 데이터 피드 배달에서 히트 주문은 보장되지 않습니다.</p> |
| **다시 채우기 기간**<br/>&#x200B;두 지난 날짜 사이의 이전 데이터를 내보냅니다. | 연결의 롤링 데이터 창으로 제한됩니다. | 보고서 세트 데이터 보존 한도로 제한됨: 기본적으로 **25개월**. |
| **Segmentation** | 세그먼트는 데이터 보기 세그먼트, 피드별 세그먼트 또는 둘 다를 통해 데이터 피드에 적용할 수 있습니다. | 세그먼트를 적용할 수 없습니다. |
| **결합** | 지원됨. 여러 장치의 이벤트를 한 사람에게 연결하여 장치 간 ID 확인을 활성화합니다. | 지원되지 않습니다. 결합된 데이터는 Adobe Analytics 데이터 피드를 통해 내보낼 수 없습니다. |
| **스키마**<br/>&#x200B;데이터 피드 스키마는 데이터 피드에 포함할 수 있는 열을 결정합니다. | 데이터 피드 스키마는 데이터 보기 구성을 기반으로 합니다.  데이터 피드 스키마에 포함할 수 있는 구성 요소는 데이터 보기 구성에서 사용할 수 있는 구성 요소의 하위 집합입니다.</p> | ~1,100개 이상의 변수에 대한 사전 정의된 정적 목록입니다. 많은 열을 **사전 및 사후 처리 쌍**(예: `eVar1` / `post_eVar1`)으로 내보내 열 수의 대부분을 차지합니다. |
| **조회**<br/> 동적 조회를 사용하면 데이터 피드에서 추가 조회 파일을 받을 수 있습니다. 그렇지 않으면 사용할 수 없습니다. | 조회 및 분류는 모두 데이터 보기에서 직접 조정된 차원으로 사용할 수 있으므로 필요하지 않습니다. 데이터 보기에서 조회 또는 분류를 차원으로 조정하는 경우 해결된 값은 별도의 참조 파일이 아닌 이벤트 데이터와 인라인으로 Parquet 출력에 일반 열로 표시됩니다. | 데이터 피드 열의 숫자를 실제 값과 일치시키는 데 사용됩니다. 특정 항목 집합(브라우저, OS, 모바일 장치)에만 해당되며, 데이터 피드와 함께 제공되는 별도의 파일로 적용됩니다. |
| **세션 정의**<br/> <!--(could be included in the data processing section instead)--> | 데이터 보기에 정의되어 있습니다. | 컬렉션 시간에 정의됩니다. |
| **계산된 지표**<br/> | 사용할 수 없음 | 사용할 수 없음 |
| **지속성 모델** | 유연합니다. 데이터 보기의 지속성 설정(할당 및 만료)은 피드가 생성될 때 보고서 시간에 적용됩니다. 데이터 보기에서 사용할 수 있는 모든 할당 설정을 지원합니다. **원래**, **가장 최근**, **모두**, **처음 알려짐** 및 **마지막 알려짐**. | **가장 최근(마지막 터치)** 및 **원래 값(첫 번째 터치)** 속성 모델만 표시됩니다. 선형 할당은 마지막 터치와 동일하게 처리됩니다. |
| **출력 파일 형식** | 쪽모이 세공<p>는 기본적으로 복잡한 중첩 및 구조화된 데이터를 지원합니다. 제품 목록은 구조화된 배열/중첩된 개체로 표시됩니다. </p><p>BigQuery, Snowflake 또는 Apache Spark와 같이 읽을 수 있는 Parquet 인식 도구가 필요합니다.</p> | TSV<p>사람이 읽을 수 있는 평면형 행. 는 구조화된 데이터를 기본적으로 지원하지 않습니다. 제품 목록과 같은 복잡한 필드는 사용자 지정 구문 분석 논리를 필요로 하는 배타적으로 구분된 문자열로 인코딩해야 합니다.</p> |
| **게재 대상** | Amazon S3, Azure RBAC, Azure SAS, Google Cloud Platform, Snowflake | Amazon S3, Azure RBAC, Azure SAS, Google Cloud Platform **SFTP**&#x200B;도 지원합니다. |

{style="table-layout:auto"}

<!-- Is this useful info to accompany the table? Not sure... **Hits**<br/>  | Only Hit 5 is in the data feed window. However, because the reporting window also includes Hit 4 and Hit 3 (which are late-arriving hits with timestamps from a previous data feed window), they are also included in the current data feed window.<p>Hits are reordered in the data feed according to their timestamp, as follows: Hit 3, Hit 4, Hit 5.</p> | Only Hit 5 is in the data feed window. However, because a lookback is configured and it includes Hit 4 and Hit 3 (which are late-arriving hits with timestamps from a previous data feed window), they are also included in the current data feed window. (If a lookback was not configured, only Hit 5 would be included in the data feed.) <p>Hits are shown in the data feed in the order they were received, as follows: Hit 4, Hit 3, Hit 5.</p> -->

<!-- Is all of this info redundant?  **Late-arriving hits**<br/> (If you send us data that is out of order per person would be if you are setting the timestamp. You can set the timestamp in 2 ways: you can have Adobe set the timestamp, based on when we received the data. Or you can set it yourself. If you're setting the timestamps and you sending us data that is out of order, it messes things up in AA. In AA, data needs to come in order per visitor. We need the right order of events. But in CJA, it doesn't matter what timestamps are on the data. CJA doesn't assign a timestamp to a hit. That is done upstream. CJA reorders the data once it arrives, so that everything is in the proper time sequence. Then we can do the report-time processing. That means you can have both streaming data and batch data. It doesn't matter. At the time it arrives, we reorder it and it becomes in order per person as a result. So in CJA we'll give you all the data we received in the last day or hour, but it's limited to the beginning of the reporting window. Most likely a huge chunk of the data you get in a day or hour belongs to that day or hour. If all you did was batch data from a call center, then that is what you would get out. In CJA, data can come in and it doesn't matter when it came in. So the data feed ustomer has to be able to handle this on their side. So wherever they're putting the data, it needs to handle the fact that timestamps could potentially be all over the place. This might be a challenge for some customers. They need to know this. Needs to be able to handle out of order data per person. It doesn't matter across people. ) Hits that should have been included in a previous data feed, but for some reason they arrived late (such as through timestamped hits or data sources). <p>These late-arriving hits are included in the current data feed at the time they arrive, even though their timestamps are within a previous data feed window. Every time a data feed processes data, it looks at any late hits that have arrived and batches them in the next data feed file that is sent.</p>  | Late-arriving hits that occur within the **[!UICONTROL Reporting window]** are always included. <p>The lookback window for these late-arriving hits is controlled through the **[!UICONTROL Reporting window]** configuration option.</p><p>Hits are automatically reordered based on timestamps; original values are persisted (no change feed).</p> | Can be included or excluded. Configurable with the **[!UICONTROL Late-arriving hits]** configuration option.<p>The lookback window for these hits is configured through the **[!UICONTROL Lookback window]** configuration option that is available for this specific purpose.</p><p>Hits are shown in the order in which they are received; they are not reordered according to timestamp.</p>   -->
