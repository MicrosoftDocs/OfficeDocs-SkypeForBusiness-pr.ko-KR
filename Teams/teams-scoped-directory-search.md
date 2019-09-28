---
title: Microsoft 팀 범위 디렉터리 검색 사용
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 06/21/2019
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: sbhatta
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
description: Microsoft 팀 범위 디렉터리 검색을 사용 하 여 디렉터리의 사용자 지정 된 보기를 제공 하는 방법에 대해 알아봅니다.
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4e3b95e9d8de04abc6299a52a27cf07d95365a4f
ms.sourcegitcommit: 1721acdd507591d16a4e766b390b997979d985e5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/27/2019
ms.locfileid: "37305802"
---
# <a name="use-microsoft-teams-scoped-directory-search"></a>Microsoft 팀 범위 디렉터리 검색 사용

Microsoft 팀 범위 디렉터리 검색을 통해 조직에서 사용자가 조직의 다른 사용자를 찾고 통신 하는 방법을 제어 하는 가상 경계를 만들 수 있습니다. 

Microsoft 팀은 조직에서 사용자에 게 디렉터리에 대 한 사용자 지정 보기를 제공할 수 있습니다. Microsoft 팀은 [Exchange 주소록 정책을](https://docs.microsoft.com/exchange/address-books/address-book-policies/address-book-policies) 사용 하 여 이러한 사용자 지정 보기를 지원 합니다. 정책을 사용 하도록 설정한 후에는 다른 사용자를 검색 하 여 반환 된 결과 (예: 채팅을 시작 하거나 팀에 구성원을 추가 하는 것)는 구성 된 정책에 따라 범위가 지정 됩니다. 범위 검색이 적용 되는 경우 사용자가 팀을 검색 하거나 검색할 수 없습니다. 

> [!NOTE]
> Exchange 하이브리드 환경에서이 기능은 온-프레미스 사서함이 아닌 Exchange Online 사서함 에서만 작동 합니다.

## <a name="when-should-you-use-scoped-directory-searches"></a>범위 디렉터리 검색은 언제 사용 해야 하나요?

범위 디렉터리 검색에 도움이 되는 시나리오는 주소록 정책 시나리오와 유사 합니다. 예를 들어 다음과 같은 경우 범위 디렉터리 검색을 사용 하는 것이 필요할 수 있습니다.

- 조직에 테 넌 트 내에 별도로 유지 하려는 회사가 여러 개 있습니다. 
- 학교에서 교사와 학생 간의 채팅을 제한 하려고 합니다. 
 
주소록 정책을 사용 하는 방법에 대 한 자세한 내용은 [Exchange Online에서 주소록 정책을](https://docs.microsoft.com/exchange/address-books/address-book-policies/address-book-policies)참조 하세요.

> [!IMPORTANT]
> 주소록 정책은 사용자의 가상 구분을 디렉터리 관점에서 제공 합니다. 사용자는 전체 전자 메일 주소를 제공 하 여 계속 해 서 다른 사람들과 통신을 시작할 수 있습니다. 또한 신규 또는 업데이트 된 주소록 정책을 적용 하기 전에 이미 캐싱된 사용자 데이터는 최대 30 일 동안 사용자가 사용할 수 있도록 유지 된다는 점에 유의 해야 합니다.

## <a name="turn-on-scoped-directory-search"></a>범위 디렉터리 검색 설정

1. 주소록 정책을 사용 하 여 조직을 가상 하위 그룹으로 구성 합니다. 자세한 내용은 [주소록 정책에 대 한 절차](https://docs.microsoft.com/exchange/address-books/address-book-policies/address-book-policies)를 참조 하세요.

2. Microsoft 팀 관리 센터에서 **조직 전체 설정** > **팀 설정을**선택 합니다.

3. **검색**에서 **Exchange 주소록 정책 (apb)을 사용 하는 팀의 범위 디렉터리 검색** **옆에 있는 토글을**켭니다.

    ![Microsoft 팀 관리 센터의 범위 디렉터리 검색](media/teams-scoped-directory-search-image1.png)



