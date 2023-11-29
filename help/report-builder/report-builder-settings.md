---
title: Customer Journey Analytics에서 Report Builder에 대한 설정을 구성하는 방법
description: 오프라인 모드, 언어, 기준 날짜 및 문제 해결 설정을 지정하는 방법을 설명합니다.
role: Data Engineer, Data Architect, Admin, User
feature: Report Builder
type: Documentation
exl-id: 32423cb4-1a4c-4ea3-ad4b-9520aff9ae4b
solution: Customer Journey Analytics
source-git-commit: c343a729de4cb13473a7acc04e837b5e5f69809b
workflow-type: tm+mt
source-wordcount: '281'
ht-degree: 87%

---

# Report Builder 설정

**설정** 창을 사용하여 UI에 표시되는 언어 또는 오프라인 모드에서 작동할지 여부와 같은 애플리케이션 수준 설정을 구성합니다. 설정은 즉시 적용되며 변경될 때까지 이후의 모든 세션에 대해 설정됩니다.

Report Builder 설정을 변경하려면

1. **설정** 아이콘을 클릭합니다.

1. 오프라인 모드 활성화를 변경하거나 언어를 선택하거나 문제 해결 로그 설정을 활성화합니다.

1. **적용**&#x200B;을 클릭합니다.

   ![취소 및 적용 단추를 보여 주는 Report Builder 날짜 범위 창입니다.](./assets/image38.png)

## 오프라인 모드

오프라인 모드에서 데이터 블록을 만들고 편집할 때 데이터가 검색되지 않습니다. 대신 시뮬레이션 데이터가 사용되므로 요청이 실행될 때까지 기다리지 않고 데이터 블록을 빠르게 만들고 편집할 수 있습니다. 다시 온라인 상태가 되면 *데이터 블록 새로 고침* 명령 또는 *모든 데이터 블록 새로 고침* 명령은 실제 데이터로 만든 데이터 블록을 새로 고칩니다.

오프라인 모드를 활성화하려면

1. **설정** 아이콘을 클릭합니다.

1. **오프라인 모드 활성화**&#x200B;를 선택합니다.

1. **지표 데이터 표시 형식** 필드에 양의 정수를 입력합니다.

1. **적용**&#x200B;을 클릭합니다.

## 언어

Report Builder UI의 언어를 선택할 수 있습니다. 지원되는 모든 Adobe Analytics 언어를 사용할 수 있습니다.

Report Builder UI에서 사용되는 언어를 선택하려면

1. [설정]을 클릭합니다.

1. **언어** 드롭다운 메뉴에서 언어를 선택합니다.

   ![영어가 선택된 언어 목록을 표시하는 Report Builder 날짜 범위 창.](./assets/image39.png)

1. **적용을 클릭합니다.**

## 문제 해결

문제 해결 설정을 사용하여 모든 클라이언트/서버 데이터를 로컬 파일에 기록합니다. 이 옵션을 사용하면 지원 티켓을 해결하는 데 도움이 됩니다.

문제 해결 옵션을 활성화하려면 **로컬 파일에 요청 기록**&#x200B;을 선택합니다.
