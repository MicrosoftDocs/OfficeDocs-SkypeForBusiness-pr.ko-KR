---
title: 조직의 Shifts 앱 관리
author: cichur
ms.author: v-cichur
ms.reviewer: lisawu,gumariam
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
description: 조직의 일선 작업자용 Teams에서 Shifts 앱을 설정하고 관리하는 방법을 배워야 합니다.
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
- microsoftcloud-healthcare
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 218b041d83cde91a23201ab864160ce3b8b7cb6e
ms.sourcegitcommit: fdef9b52247097e5cae64f01b6b2b710c5b203cf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/20/2021
ms.locfileid: "49909092"
---
# <a name="manage-the-shifts-app-for-your-organization-in-microsoft-teams"></a>Microsoft Teams에서 조직의 Shifts 앱 관리

> [!IMPORTANT]
> 2020년 6월 30일부로 Microsoft StaffHub가 사용 중지됩니다. Microsoft Teams에 StaffHub 기능을 구축하고 있습니다. 현재 Teams에는 일정 관리를 위한 Shifts 앱이 포함되어 있으며 시간이 지날 때 추가 기능이 출시됩니다. StaffHub는 2020년 6월 30일 모든 사용자에 대한 작업을 중지했습니다. StaffHub를 열려고 하는 모든 사람이 Teams를 다운로드할 수 있는 메시지를 보여 주게 됩니다. 자세한 내용은 [Microsoft StaffHub가 사용 중지된 것을 참조합니다.](microsoft-staffhub-to-be-retired.md)  

## <a name="overview-of-shifts"></a>Shifts 개요

Microsoft Teams의 Shifts 앱은 일선 작업자를 연결하고 동기화합니다. 팀을 위한 빠르고 효과적인 시간 관리 및 커뮤니케이션을 위한 모바일이 먼저 구축됩니다. Shifts를 사용하면 일선 직원들과 관리자가 모바일 장치를 사용하여 일정을 관리하고 연락을 유지할 수 있습니다.

- 관리자는 팀의 교대 근무 일정을 만들고, 업데이트하고, 관리합니다. 한 사람("바닥에 유출이 있습니다") 또는 전체 팀("지역 GM이 20분 내 도착")으로 메시지를 보낼 수 있습니다. 정책 문서, 뉴스 게시판 및 비디오를 보낼 수 있습니다. 
- 직원은 예정된 교대 근무를 보고, 그 날에 예약된 다른 사람, 교대 근무 바꾸기 또는 제안 요청 및 근무 시간 요청 

Shifts는 현재 게스트 사용자를 지원하지 않는다는 점에 유의해야 합니다. 즉, Teams에서 게스트 액세스가 설정되어 있는 경우 팀의 게스트를 추가하거나 교대 근무 일정을 사용할 수 없습니다. 

> [!Note]
> 다양한 플랫폼의 Shifts 기능에 대한 자세한 내용은 플랫폼에 따라 [Teams 기능을 참조하세요.](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3)

## <a name="availability-of-shifts"></a>Shifts의 가용성

Shifts는 Teams를 사용할 수 있는 모든 Enterprise SKUS에서 사용할 수 있습니다.

## <a name="location-of-shifts-data"></a>Shifts 데이터의 위치

Shifts 데이터는 현재 북아메리카, 서유럽 및 아시아 태평양의 데이터 센터에 Azure에 저장됩니다. 데이터가 저장되는 위치에 대한 자세한 내용은 내 데이터가 어디에 [있나요?](http://o365datacentermap.azurewebsites.net/)

## <a name="set-up-shifts"></a>Shifts 설정

### <a name="enable-or-disable-shifts-in-your-organization"></a>조직에서 Shifts 사용 또는 사용 안 하도록 설정

Shifts는 조직의 모든 Teams 사용자에 대해 기본적으로 사용하도록 설정됩니다. Microsoft Teams 관리 센터의 앱 관리 페이지에서 구성 [](../../manage-apps.md) 수준에서 앱을 끄거나 끄면 됩니다.

1. Microsoft Teams 관리 센터의 왼쪽 탐색 모음에서 Teams 앱 **관리**  >  **앱으로 이동하세요.**
2. 앱 목록에서 다음 작업 중 하나를 실행합니다.

    - 조직에 대한 Shifts를 해제하려면 Shifts 앱을 검색하고 선택한 다음 차단을 **선택합니다.**
    - 조직에 대한 Shifts를 설정하려면 Shifts 앱을 검색하고 선택한 다음 허용을 **선택합니다.**

### <a name="enable-or-disable-shifts-for-specific-users-in-your-organization"></a>조직의 특정 사용자에 대해 Shifts 사용 또는 사용 안 하도록 설정

조직의 특정 사용자가 Shifts를 사용할 수 있도록 허용하거나 차단하려면 앱 관리 [](../../manage-apps.md) 페이지에서 조직에 대해 Shifts가 켜져 있는지 확인한 다음 사용자 지정 앱 사용 권한 정책을 만들고 해당 사용자에게 할당합니다. 자세한 내용은 [Teams에서 앱 사용 권한 정책 관리를 참조하세요.](../../teams-app-permission-policies.md)

### <a name="use-the-frontlineworker-app-setup-policy-to-pin-shifts-to-teams"></a>FrontlineWorker 앱 설정 정책을 사용하여 Teams에 Shifts 고정

앱 설정 정책을 사용하면 Teams를 사용자 지정하여 조직의 사용자에게 가장 중요한 앱을 강조할 수 있습니다. 정책에 설정된 앱은 Teams 데스크톱 클라이언트의 측면 및 사용자가 빠르고 쉽게 액세스할 수 있는 Teams 모바일 클라이언트의 아래쪽에 있는 앱 바에 &mdash; &mdash; 고정됩니다.
 
Teams에는 조직의 Frontline Workers에 할당할 수 있는 기본 제공 FrontlineWorker 앱 설정 정책이 포함되어 있습니다. 기본적으로 정책에는 활동, Shifts, 채팅 및 통화 앱이 포함됩니다. 

FrontlineWorker 정책을 보기 위해 Microsoft Teams 관리 센터의 왼쪽 탐색 모음에서 **Teams** 앱 설정  >  **정책으로 이동하세요.**

![FrontlineWorker 앱 설정 정책의 스크린샷](../../media/firstline-worker-app-setup-policy.png "Microsoft Teams 관리 센터의 FrontlineWorker 앱 설정 정책 스크린샷")

#### <a name="assign-the-frontlineworker-app-setup-policy-to-users"></a>사용자에게 FrontlineWorker 앱 설정 정책 할당

[!INCLUDE [assign-policy](../../includes/assign-policy.md)]

## <a name="search-the-audit-log-for-shifts-events"></a>Shifts 이벤트에 대한 감사 로그 검색

**(미리 보기)**

감사 로그를 검색하여 조직의 Shifts 활동을 볼 수 있습니다.  감사 로그를 검색하고 감사 로그에 기록된 [Shifts](../../audit-log-events.md#shifts-in-teams-activities) 활동 목록을 보는 방법에 대한 자세한 내용은 Teams에서 이벤트에 대한 감사 로그 검색을 [참조하세요.](../../audit-log-events.md)

감사 로그를 검색하려면 먼저 Security & 준수 센터에서 감사를 [켜야 합니다.](https://protection.office.com) 자세한 내용은 감사 로그 검색 설정 [또는 해제를 참조합니다.](https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014) 감사 데이터는 감사를 설정한 시점에서만 사용할 수 있습니다.

## <a name="related-topics"></a>관련 항목

- [일선 작업자를 위한 교대 근무 도움말](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b)
- [Teams에서 사용자에게 정책 할당](../../assign-policies.md)
