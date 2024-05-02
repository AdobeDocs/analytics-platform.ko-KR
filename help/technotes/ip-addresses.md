---
title: Customer Journey Analytics에서 사용하는 IP 주소
description: 조직 방화벽이 Adobe에서 생성하는 IP 주소를 차단하는 경우 이 목록을 사용하여 방화벽 설정을 업데이트하십시오.
solution: Customer Journey Analytics
feature: Basics
exl-id: 5c52986c-7ff3-45b5-9039-2bfb6529238c
role: Admin
source-git-commit: 39e4c17336d3648cbf20cace535668d14510186f
workflow-type: tm+mt
source-wordcount: '192'
ht-degree: 31%

---

# Customer Journey Analytics에서 사용하는 IP 주소

일부 방화벽 구성은 Adobe 데이터 수집 서버나 데이터에 액세스하는 서버에서 오는 IP 주소를 차단합니다. 이 범위 목록을 사용하여 액세스를 허용하고 조직 내에서 데이터를 전송할 수 있도록 조직의 방화벽 설정을 변경할 수 있습니다.

이 페이지에는 다음과 같이 아웃바운드 시스템이 작동하기 위해 ip 주소를 허용 목록에 추가하다에 추가해야 합니다. [클라우드 공급자로 데이터 내보내기](/help/analysis-workspace/export/export-cloud.md).

>[!IMPORTANT]
>
>Adobe은 이 문서를 최신 상태로 유지하기 위해 최선을 다하고 있지만 IP 범위 목록이 동일하게 유지된다고 보장하지는 못합니다. 비즈니스의 성장 및 확장과 같은 변경 가능성이 있을 수 있으며, 인터넷 레지스트리에서 Adobe의 IP 주소 공간을 변경해야 하거나, 인터넷 서비스 공급자가 제대로 작동하지 않을 수 있습니다.

## VA7: 미국 및 아메리카 고객

| IP 블록(CIDR 표기법) |
| --- |
| `52.254.106.192/28` |
| `52.254.107.80/28` |
| `52.254.106.240/28` |
| `52.254.107.32/28` |
| `52.254.106.176/28` |
| `52.254.106.144/28` |
| `52.254.107.64/28` |
| `20.186.185.181` |
| `20.186.185.239` |
| `52.254.106.160/28` |
| `40.70.154.136/29` |
| `20.22.83.112` |
| `52.254.107.16/28` |
| `52.254.105.192/28` |
| `52.254.107.144/28` |
| `52.254.106.0/28` |
| `52.254.106.224/28` |
| `52.254.107.128/28` |
| `52.254.106.208/28` |
| `20.186.185.227` |
| `52.254.107.0/28` |

## NLD2: 유럽

| IP 블록(CIDR 표기법) |
| --- |
| `40.74.6.128/28` |
| `51.144.184.248/29` |
| `40.74.7.192/28` |
| `40.74.7.128/28` |
| `40.74.7.176/28` |
| `20.50.23.153` |
| `40.74.6.80/28` |
| `40.74.6.144/28` |
| `40.74.5.128/28` |
| `51.105.144.1` |
| `51.105.144.81` |
| `40.74.4.176/28` |
| `52.142.236.87` |
| `40.74.4.144/28` |
| `20.101.246.9` |
| `40.74.4.160/28` |
| `40.74.7.160/28` |
| `40.74.7.144/28` |
| `40.74.3.176/28` |
| `51.124.70.4` |
| `40.74.6.96/28` |
| `40.74.7.208/28` |
| `40.74.6.112/28` |

## AUS5: 오스트레일리아

| IP 블록(CIDR 표기법) |
| --- |
| `20.43.110.192/28` |
| `20.40.185.111` |
| `20.43.97.95` |
| `20.43.111.16/28` |
| `20.193.38.208/28` |
| `20.43.110.64/28` |
| `20.40.185.225` |
| `20.43.110.112/28` |
| `20.43.110.224/28` |
| `20.193.36.37` |
| `20.43.110.240/28` |
| `20.43.111.32/28` |
| `20.40.185.185` |
| `20.43.111.0/28` |
| `20.43.110.208/28` |
| `20.43.110.96/28` |
| `20.43.110.48/28` |
| `20.43.110.128/28` |
| `20.43.110.160/28` |
| `20.43.110.80/28` |
| `20.193.56.144/28` |
| `20.193.56.160/28` |
| `20.43.110.176/28` |
| `20.43.110.144/28` |
| `20.53.111.113` |
| `20.193.56.128/28` |
| `20.227.32.175` |

## CAN2: 캐나다

| IP 블록(CIDR 표기법) |
| --- |
| `20.116.159.80/28` |
| `20.116.159.224/28` |
| `20.116.159.192/28` |
| `20.116.159.64/28` |
| `20.151.241.173` |
| `20.116.159.128/28` |
| `20.116.159.208/28` |
| `20.116.159.48/28` |
| `20.151.240.247` |
| `20.116.159.0/28` |
| `20.220.243.238` |
| `20.116.175.240/28` |
| `20.116.155.128/28` |
| `20.116.248.0/28` |
| `20.151.241.138` |
| `20.116.159.144/28` |
| `20.116.175.224/28` |
| `20.116.248.16/28` |
| `20.151.241.124` |
| `20.116.159.160/28` |
| `20.116.159.96/28` |
| `20.104.5.248` |
| `20.116.159.112/28` |
| `20.116.159.176/28` |
| `20.116.159.32/28` |
| `20.116.158.240/28` |

>[!MORELIKETHIS]
>
>[Customer Journey Analytics에서 사용하는 도메인](domains.md)
>
>[Adobe Experience Cloud에서 사용하는 IP 주소](https://experienceleague.adobe.com/en/docs/core-services/interface/data-collection/ip-addresses)