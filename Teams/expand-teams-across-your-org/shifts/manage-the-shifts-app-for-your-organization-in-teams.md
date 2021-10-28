---
title: 조직의 교대 근무 앱 관리
author: serdarsoysal
ms.author: serdars
ms.reviewer: lisawu,gumariam
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
description: 조직의 프런트라인 작업자를 위해 Teams Shifts 앱을 설정하고 관리하는 방법에 대해 자세히 알아보습니다.
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
- microsoftcloud-healthcare
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 87389dfaba68de8cfe02f3291e03d593bb9de75b
ms.sourcegitcommit: 3a8bec0445cee5cd776fb1991f093a0ec4351852
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/28/2021
ms.locfileid: "60605834"
---
# <a name="manage-the-shifts-app-for-your-organization-in-microsoft-teams"></a>Microsoft Teams에서 조직의 교대 근무s 앱 관리

> [!IMPORTANT]
> 2020년 6월 30일부터 Microsoft StaffHub는 사용 중지됩니다. Microsoft Teams에 StaffHub 기능을 구축하고 있습니다. 현재 Teams에는 일정 관리를 위한 교대 근무 앱이 포함되어 있으며 시간이 지날 때 추가 기능이 배포될 것입니다. 2020년 6월 30일 StaffHub에서 모든 사용자에 대해 작동이 중지되었습니다. StaffHub를 여는 모든 사용자에게 Teams를 다운로드하라는 메시지가 표시됩니다. 자세한 내용은 [Microsoft StaffHub는 사용 중지됨](microsoft-staffhub-to-be-retired.md)을 참조하세요.  

## <a name="overview-of-shifts"></a>교대 근무 개요

이 앱의 Shifts Microsoft Teams 프런트라인 작업자가 연결되고 동기화됩니다. 팀을 위한 빠르고 효과적인 시간 관리 및 통신을 위해 먼저 모바일을 구축했습니다. Shifts를 통해 프런트라인 작업자와 관리자가 모바일 디바이스를 사용하여 일정을 관리하고 연락할 수 있습니다.

- 관리자는 팀의 교대 근무 일정을 만들고 업데이트하고 관리합니다. 관리자는 한 사람에게 메시지(“바닥에 액체가 흘러 있네요.”)를 보내거나 전체 팀에 메시지(“지역 GM이 20분 후에 도착합니다.”)를 보낼 수 있습니다. 이뿐만 아니라 정책 문서, 뉴스 게시판 및 비디오를 보낼 수도 있습니다.
- 직원은 예정된 교대 근무를 보고, 그날에 예정된 다른 사람을 확인하고, 교대 근무를 변경하거나 제안하고, 휴가를 요청합니다.

Shifts가 현재 게스트를 지원하지 않는 것을 아는 것이 중요합니다. 즉, 팀의 게스트는 Teams에서 게스트 액세스가 켜져 있을 때 교대 근무 일정을 추가하거나 사용할 수 없습니다. 

> [!Note]
> 다른 플랫폼의 교대 근무 기능에 대한 자세한 내용은 [플랫폼별 Teams 기능](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3)을 참조하세요.

## <a name="availability-of-shifts"></a>교대 근무의 가용성

교대 근무는 Teams를 사용할 수 있는 모든 엔터프라이즈 SKU에서 사용할 수 있습니다.

## <a name="location-of-shifts-data"></a>교대 근무 데이터의 위치

교대 근무 데이터는 현재 북아메리카, 서유럽 및 아시아 태평양에 위치한 데이터 센터의 Azure에 저장됩니다. 데이터가 저장되는 위치에 대한 자세한 내용은 [내 데이터는 어디에 있나요](http://o365datacentermap.azurewebsites.net/)?를 참조하세요.

## <a name="set-up-shifts"></a>교대 근무 설정

### <a name="enable-or-disable-shifts-in-your-organization"></a>조직에서 교대 근무를 설정하거나 사용하지 않도록 설정

교대 근무는 조직의 모든 Teams 사용자에 대해 기본적으로 사용하도록 설정됩니다. Microsoft Teams 관리자 센터의 [앱 관리](../../manage-apps.md) 페이지에서 조직 수준에서 앱을 끄거나 켤 수 있습니다.

1. Microsoft Teams 관리 센터의 왼쪽 탐색 창에서 **Teams 앱** > **앱 관리** 로 이동합니다.
2. 앱 목록에서 다음 작업 중 하나를 실행합니다.

    - 조직에서 교대 근무를 사용 해제하려면 교대 근무 앱을 검색하고 선택한 다음 **차단** 을 선택하세요.
    - 조직에 대해 교대 근무를 설정하려면 교대 근무 앱을 검색하고 선택한 다음 **허용** 을 선택하세요.

### <a name="enable-or-disable-shifts-for-specific-users-in-your-organization"></a>조직의 특정 사용자에 대해 교대 근무를 사용 또는 사용하지 않도록 설정

조직의 특정 사용자가 Shifts를 사용할 수 있도록 허용하거나 차단하기 위해 앱 관리 페이지에서 조직에 대해 Shifts가 켜져 있는지 [확인하세요.](../../manage-apps.md) 그런 다음 사용자 지정 앱 사용 권한 정책을 만들고 해당 사용자에게 할당합니다. 자세한 내용은 [Teams에서 앱 권한 정책 관리](../../teams-app-permission-policies.md)를 참조하세요.

### <a name="use-the-firstlineworker-app-setup-policy-to-pin-shifts-to-teams"></a>FirstLineWorker 앱 설정 정책을 사용하여 Shifts를 고정하여 Teams

앱 설정 정책을 사용하면 Teams를 사용자 지정하여 조직의 사용자에게 가장 중요한 앱을 강조할 수 있습니다. 정책에 설정한 앱은 Teams 데스크톱 클라이언트의 측면&mdash;표시줄에 있는 앱 모음과 Teams 데스크톱 클라이언트의 하단에 고정되어 있어, &mdash;사용자가 빠르고 쉽게 액세스할 수 있습니다.
 
Teams 프런트라인 작업자에게 할당할 수 있는 기본 제공 FirstLineWorker 앱 설치 정책이 포함되어 있습니다. 기본적으로 이 정책에는 활동, 교대 근무, 채팅 및 통화 앱이 포함됩니다.

FirstLineWorker 정책을 보시고 관리 센터의 왼쪽 Microsoft Teams 앱 설정 Teams  >  **로 이동하세요.**

:::image type="content" source="../../media/firstline-worker-app-setup-policy-new.png" alt-text="관리 센터의 FirstLineWorker 앱 Microsoft Teams 스크린샷" lightbox="../../media/firstline-worker-app-setup-policy-new.png":::

#### <a name="assign-the-firstlineworker-app-setup-policy-to-users"></a>사용자에게 FirstLineWorker 앱 설정 정책 할당

[!INCLUDE [assign-policy](../../includes/assign-policy.md)]

## <a name="search-the-audit-log-for-shifts-events"></a>교대 근무 이벤트에 대한 감사 로그 검색

**(미리 보기 중)**

감사 로그를 검색하여 조직의 교대 근무 활동을 볼 수 있습니다.  감사 로그를 검색하는 방법과 감사 로그에 기록된 [교대 근무 활동](../../audit-log-events.md#shifts-in-teams-activities) 목록을 확인하는 방법에 대한 자세한 내용은 [Teams에서 이벤트에 대한 감사 로그 검색](../../audit-log-events.md)을 참조하세요.

감사 로그를 검색하려면 먼저 [보안 및 준수 센터](https://protection.office.com)에서 감사를 켜야 합니다. 자세한 내용은 [감사 로그 검색 설정 및 해제](https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014)를 참조하세요. 감사 데이터는 감사가 켜진 시점부터만 사용할 수 있습니다.

## <a name="related-topics"></a>관련 주제

- [일선 작업자를 위한 Shifts 도움말](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b)
- [Teams에서 사용자에게 정책 할당](../../policy-assignment-overview.md)
