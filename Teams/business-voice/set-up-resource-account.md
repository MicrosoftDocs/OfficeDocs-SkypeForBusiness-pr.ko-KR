---
title: 리소스 Microsoft Teams 전화 시스템 설정
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
f1.keywords:
- NOCSH
ms.localizationpriority: medium
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- Teams_Business_Voice
search.appverid: MET150
description: 자동 참석자에 사용할 Microsoft Teams 전화 시스템 리소스 계정을 설정하는 방법에 대해 자세히 알아보습니다.
appliesto:
- Microsoft Teams
ms.openlocfilehash: a0953ef81ef3128da858733931a43238531e83b6
ms.sourcegitcommit: e86e3824c300c24e022d5cb1848338278a5a96a8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/03/2022
ms.locfileid: "63053247"
---
# <a name="step-4-set-up-a-teams-phone-system-resource-account"></a>4단계: Teams 전화 시스템 계정 설정

리소스 계정은 특정 사용자에게 할당되지 않습니다. 대신 무료 가상 사용자 라이선스를 사용하는 리소스 계정은 가상 사용자 라이선스의 디바이스 및 서비스에서 Microsoft 365. 이 Microsoft Teams 리소스 계정은 전화 번호가 할당된 다음 자동 참석자 및 통화 큐와 연결됩니다.

리소스 계정을 자동 참석자에 연결하고 큐를 호출하면 하나 이상의 무료 전화 번호를 추가할 수 있습니다. 예를 들어 한 리소스 계정을 로컬 호출자에 대한 자동 참석자에 전화 번호와 연결할 수 있습니다. 장거리 통화의 경우 다른 리소스 계정을 무료 전화 번호와 동일한 자동 참석자에 연결할 수 있습니다.

이 문서의 섹션에서는 리소스 계정을 설정한 다음 전화 번호를 할당하는 방법을 보여 니다. 나중에 리소스 계정을 자동 참석자와 연결합니다.

## <a name="obtain-virtual-user-licenses"></a>가상 사용자 라이선스 획득

리소스 계정에는 자동 참석자 및 호출 큐를 사용하려면 라이선스가 필요합니다. 표준 - *가상 사용자 Microsoft Teams 전화 무료 라이선스를 사용할 수* 있습니다.

> [!NOTE]
> 통화 계획 번들 라이선스 평가판 기간에 등록한 Teams 전화 다음 단계만 수행하면 됩니다. 통화 계획 번들 Teams 전화 구매한 경우 가상 라이선스가 계정에 이미 적용되어야 합니다.
>
> 가상 라이선스가 이미 있는지 확인하려면 전역 Microsoft 365 계정을 사용하여 로그인합니다. 그런 다음 청구로 > [제품으로 이동합니다](https://admin.microsoft.com/Adminportal/Home#/subscriptions). 가상 라이선스가 있는 경우 표준 Microsoft Teams 전화 **가상 사용자로 표시됩니다**.

1. 전역 Microsoft 365 관리 센터 사용자와 로그인합니다. 일반적으로 이 계정은 등록하는 데 사용한 Microsoft 365.
2. 왼쪽 탐색 창에서 <a href="https://admin.microsoft.com/Adminportal/Home#/catalog" target="_blank">**BillingPurchase** > </a> **servicesAdd-onsSee** >  >  모든 추가 기능 제품으로 **이동합니다**.
3. 끝까지 스크롤하여 표준 – **Microsoft Teams 전화 라이선스를 찾** 습니다. 세부 **정보를 선택한** 다음 구매 **를 선택합니다**.
4. 라이선스 구매 페이지에서 원하는 가상 사용자 라이선스 수를 선택합니다. 설정할 각 자동 참석자 및 통화 큐에 대해 하나의 가상 라이선스가 필요합니다. 더 많은 라이선스를 바로 구매하지 않고도 향후 더 많은 자동 참석자 및 통화 큐를 쉽게 설정할 수 있도록 5개 이상의 라이선스를 선택하는 것이 좋습니다.
5. 라이선스가 없는 모든 사용자에게 자동으로 할당 선택 **을 선택하지 않습니다**.
6. 지금 **체크 아웃을 선택합니다**.
7. 주문을 확인하고 **다음을 선택한** 다음 주문 **을 선택합니다**.

> [!NOTE]
> 비용이 0이라도 라이선스를  구입해야 합니다.

## <a name="create-a-resource-account"></a>리소스 계정 만들기

표준 - 가상 Microsoft Teams 전화 라이선스를  받은 후 리소스 계정을 만들 수 있습니다.

1. Microsoft Teams 관리자 센터를 열고 전역 관리자인 사용자와 로그인합니다. 일반적으로 이 계정은 등록하는 데 사용한 Microsoft 365.
2. 왼쪽 탐색 창에서 <a href="https://admin.teams.microsoft.com/company-wide-settings/resource-accounts" target="_blank">**Org-wide 설정****Resource 계정** > 으로 이동합니다</a>.
3. **추가** 를 선택합니다.
4. 리소스 계정 **추가 창** 에서 표시 이름을 **입력한 다음** 사용자 이름을 **입력합니다**. 리소스 계정의 목적을 설명하기 위해 "기본 줄 자동 참석자"처럼 설명이 있는 표시 이름을 선택하세요.
5. 리소스 **계정 유형에서** **자동 참석을 선택합니다**.
6. **저장** 을 선택합니다.

## <a name="assign-a-license"></a>라이선스 할당

리소스 계정을 만든 후 표준 - 가상 Microsoft Teams 전화 라이선스 또는 표준 Teams 전화 *할당해야* 합니다.

1. 전역 Microsoft 365 관리 센터 사용자와 로그인합니다. 일반적으로 이 계정은 등록하는 데 사용한 Microsoft 365.
1. 왼쪽 탐색 창에서 <a href="https://admin.microsoft.com/Adminportal/Home#/users" target="_blank">**UsersActive 사용자로** >  **이동합니다**</a>.
1. 리소스 계정을 선택합니다.
1. 라이선스 **및 앱** 탭의 라이선스에서 표준 **Microsoft Teams 전화 가상 사용자를 선택합니다**.
1. 변경 **내용 저장을** 선택한 다음 닫 **습니다**.

## <a name="assign-a-service-number"></a>서비스 번호 할당

1. Microsoft Teams 관리자 센터를 열고 전역 관리자인 사용자와 로그인합니다. 일반적으로 이 계정은 등록하는 데 사용한 Microsoft 365.
1. 왼쪽 탐색 창에서 <a href="https://admin.teams.microsoft.com/company-wide-settings/resource-accounts" target="_blank">**Org-wide 설정****Resource 계정** > 으로 이동합니다</a>.
1. 방금 만든 리소스 계정을 선택한 다음 할당 **/할당을 클릭합니다**.
1. 숫자 **전화 드롭** 다운에서 Online을 **선택하세요**.
1. 할당된 **전화 번호 상자** 에서 사용할 번호를 검색하고 추가를 **클릭합니다**. 국가 코드(예: **+1** 250 555 0012)를 포함해야 합니다.
1. **저장** 을 클릭합니다.

> [!div class="nextstepaction"]
> [다음 단계: 사용자에게 전화 번호 할당](set-up-assign-numbers.md)
