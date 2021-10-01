---
title: Microsoft Teams 범위 디렉터리 검색 사용
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.date: 06/21/2019
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: sbhatta
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
description: 범위가 지정된 디렉터리 Microsoft Teams 사용하여 디렉터리의 사용자 지정 보기를 제공하는 방법을 알아보십시오.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: f69a4d94743e443fd20f53f5eb35d26b6d69e3b3
ms.sourcegitcommit: cfc48dc03550c093c4405fb5984648188f523699
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/01/2021
ms.locfileid: "60046234"
---
# <a name="use-microsoft-teams-scoped-directory-search"></a>Microsoft Teams 범위 디렉터리 검색 사용

Microsoft Teams 범위가 지정된 디렉터리 검색을 사용하면 조직에서 사용자가 조직에서 다른 사용자를 찾고 통신하는 방법을 제어하는 가상 경계를 만들 수 있습니다. 

Microsoft Teams 사용자에 대한 디렉터리의 사용자 지정 보기를 제공할 수 있습니다. Microsoft Teams 정보 장벽 [정책을](/microsoft-365/compliance/information-barriers) 사용하여 이러한 사용자 지정 보기를 지원합니다. 정책을 사용하도록 설정하면 다른 사용자를 검색하여 반환된 결과(예: 채팅을 시작하거나 팀에 구성원을 추가하는)는 구성된 정책에 따라 범위가 지정됩니다. 범위가 지정된 검색이 적용된 경우 사용자는 어떤 팀도 검색하거나 검색할 수 없지만 해당 팀의 기존 구성원은 활성 정보 장벽 정책에서 허용하는 한 사용자를 추가할 수 있습니다.

> [!NOTE]
> 하이브리드 Exchange 환경에서 이 기능은 Exchange Online 사서함에서만 작동하며, 프레미스 사서함에서는 사용할 수 없습니다.

의 [주소](/exchange/address-books/address-book-policies/address-book-policies)Exchange Online.

## <a name="when-should-you-use-scoped-directory-searches"></a>범위가 지정한 디렉터리 검색을 언제 사용해야 하나요?

범위가 지정된 디렉터리 검색에서 이점이 있는 시나리오는 주소 책 정책 시나리오와 유사합니다. 예를 들어 다음과 같은 상황에서 범위가 지정한 디렉터리 검색을 사용할 수 있습니다.

- 조직의 테넌트 내에 별도로 유지하려는 여러 회사가 있는 경우 
- 학교에서 교사와 학생 간의 채팅을 제한하려고 하는 경우 
 
주소 책 정책을 사용하는 방법을 알아보고자 하는 경우 에서 정보 [장벽 정책을 Exchange Online.](/microsoft-365/compliance/information-barriers)

> [!IMPORTANT]
> 주소 책 정책은 디렉터리 관점에서 사용자만 가상으로 구분하는 기능을 제공합니다. 또한 새 주소 또는 업데이트된 주소 책 정책을 적용하기 전에 이미 캐시된 모든 사용자 데이터가 최대 30일 동안 사용자에게 제공될 수 있습니다.

## <a name="turn-on-scoped-directory-search"></a>범위가 지정된 디렉터리 검색 켜기

1. 정보 장벽 정책을 사용하여 조직을 가상 하위 조직으로 구성합니다. 자세한 내용은 정보 장벽 [정책 정의를 참조하세요.](/microsoft-365/compliance/information-barriers-policies)

2. 관리 Microsoft Teams 설정 에서 **org-wide** 설정을  >  **Teams 선택합니다.**

3. **검색에서** ABP(주소 Teams 정책)을 사용하여 Exchange 범위 디렉터리 검색 옆에 있는 토글을 **켜십시오.** 

    ![관리 센터에서 범위가 Microsoft Teams 검색합니다.](media/teams-scoped-directory-search-image1.png)

> [!IMPORTANT]
> 이 변경은 복제하는 데 몇 시간이 걸릴 수 있습니다.
