---
title: 조직의 교대 근무 앱 관리
author: LanaChin
ms.author: v-lanachin
ms.reviewer: aaku
manager: samanro
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
- Microsoft Cloud for Retail
description: 조직의 일선 작업자를 위해 Teams Shifts 앱을 설정하고 관리하는 방법을 알아봅니다.
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
- microsoftcloud-healthcare
- microsoftcloud-retail
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 2dcc945795da34ed3045ffadbc55445303b48281
ms.sourcegitcommit: 836926a4914eb33fc3e0d8d6c84cee886cb1a5a7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/29/2022
ms.locfileid: "65137009"
---
# <a name="manage-the-shifts-app-for-your-organization-in-microsoft-teams"></a>Microsoft Teams에서 조직의 교대 근무s 앱 관리

## <a name="overview-of-shifts"></a>교대 근무 개요

Microsoft Teams Shifts 앱은 일선 작업자를 연결하고 동기화된 상태로 유지합니다. 팀을 위한 빠르고 효과적인 시간 관리 및 커뮤니케이션을 위해 먼저 모바일을 구축했습니다. 교대 근무를 통해 일선 근로자와 관리자는 모바일 장치를 사용하여 일정을 관리하고 연락을 유지할 수 있습니다.

- 관리자는 팀의 교대 근무 일정을 만들고 업데이트하고 관리합니다. 관리자는 한 사람에게 메시지(“바닥에 액체가 흘러 있네요.”)를 보내거나 전체 팀에 메시지(“지역 GM이 20분 후에 도착합니다.”)를 보낼 수 있습니다. 이뿐만 아니라 정책 문서, 뉴스 게시판 및 비디오를 보낼 수도 있습니다.
- 직원은 예정된 교대 근무를 보고, 그날에 예정된 다른 사람을 확인하고, 교대 근무를 변경하거나 제안하고, 휴가를 요청합니다.

Shifts는 현재 게스트를 지원하지 않는다는 것을 알아야 합니다. 즉, 팀의 게스트는 Teams에서 게스트 액세스가 켜져 있을 때 교대 근무 일정을 추가하거나 사용할 수 없습니다.

> [!Note]
> 다른 플랫폼의 교대 근무 기능에 대한 자세한 내용은 [플랫폼별 Teams 기능](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3)을 참조하세요.

## <a name="availability-of-shifts"></a>교대 근무의 가용성

교대 근무는 Teams를 사용할 수 있는 모든 엔터프라이즈 SKU에서 사용할 수 있습니다.

> [!NOTE]
> 교대 근무는 정부 커뮤니티 클라우드(GCC) 환경에서 사용할 수 있지만 GCC High 또는 DoD 환경에서는 사용할 수 없습니다.

## <a name="location-of-shifts-data"></a>교대 근무 데이터의 위치

Shifts 데이터는 현재 APAC(아시아 태평양), 유럽 연합(EU) 및 북아메리카 데이터 센터의 Azure에 저장됩니다. 데이터가 저장되는 위치에 대한 자세한 내용은 [내 데이터는 어디에 있나요](http://o365datacentermap.azurewebsites.net/)?를 참조하세요.

Shifts 데이터의 스토리지, 보존, 검색 및 암호화를 비롯한 Shifts 데이터에 대한 자세한 내용은 [Shifts 데이터 FAQ를 참조하세요](shifts-data-faq.md).

## <a name="set-up-shifts"></a>교대 근무 설정

### <a name="enable-or-disable-shifts-in-your-organization"></a>조직에서 교대 근무를 설정하거나 사용하지 않도록 설정

교대 근무는 조직의 모든 Teams 사용자에 대해 기본적으로 사용하도록 설정됩니다. Microsoft Teams 관리자 센터의 [앱 관리](../../manage-apps.md) 페이지에서 조직 수준에서 앱을 끄거나 켤 수 있습니다.

1. Microsoft Teams 관리 센터의 왼쪽 탐색 창에서 **Teams 앱** > **앱 관리** 로 이동합니다.
2. 앱 목록에서 Shifts 앱을 검색하고 선택한 다음 **상태** 토글을 **차단** 또는 **허용** 됨으로 전환합니다.

### <a name="enable-or-disable-shifts-for-specific-users-in-your-organization"></a>조직의 특정 사용자에 대해 교대 근무를 사용 또는 사용하지 않도록 설정

조직의 특정 사용자가 Shifts를 사용하도록 허용하거나 차단하려면 [앱 관리](../../manage-apps.md) 페이지에서 조직에 대해 Shifts가 켜져 있는지 확인합니다. 그런 다음 사용자 지정 앱 권한 정책을 만들고 해당 사용자에게 할당합니다. 자세한 내용은 [Teams에서 앱 권한 정책 관리](../../teams-app-permission-policies.md)를 참조하세요.

### <a name="use-an-app-setup-policy-to-pin-shifts-to-teams"></a>앱 설정 정책을 사용하여 shifts를 Teams 고정

앱 설정 정책을 사용하면 Teams를 사용자 지정하여 조직의 사용자에게 가장 중요한 앱을 강조할 수 있습니다. 정책에 설정한 앱은 Teams 데스크톱 클라이언트의 측면&mdash;표시줄에 있는 앱 모음과 Teams 데스크톱 클라이언트의 하단에 고정되어 있어, &mdash;사용자가 빠르고 쉽게 액세스할 수 있습니다.

Shifts 앱을 추가하여 [사용자 지정 앱 설정 정책을](../../teams-app-setup-policies.md) 만든 다음 사용자에게 [정책을 할당](../../assign-policies-users-and-groups.md) 할 수 있습니다. 또는 Frontline Worker 및 Frontline Manager 정책 패키지의 일부인 앱 설정 정책을 사용할 수 있습니다.

Teams [정책 패키지](../../manage-policy-packages.md)는 조직에서 비슷한 역할을 가진 사용자에게 할당할 수 있는 미리 정의된 정책 및 정책 설정의 컬렉션입니다. Frontline Worker 및 Frontline Manager 정책 패키지의 정책 집합에는 Shifts 앱 및 해당 역할에 대한 통신 및 공동 작업 활동을 지원하는 기타 앱을 고정하는 앱 설정 정책이 포함됩니다.

최전방 작업자 및 최전방 관리자 정책 패키지를 사용하여 일선 인력에 대한 정책을 관리할 때 단순화, 간소화 및 일관성을 제공하는 것이 좋습니다.

## <a name="search-the-audit-log-for-shifts-events"></a>교대 근무 이벤트에 대한 감사 로그 검색

**(미리 보기)**

감사 로그를 검색하여 조직의 교대 근무 활동을 볼 수 있습니다.  감사 로그를 검색하는 방법과 감사 로그에 기록된 [교대 근무 활동](../../audit-log-events.md#shifts-in-teams-activities) 목록을 확인하는 방법에 대한 자세한 내용은 [Teams에서 이벤트에 대한 감사 로그 검색](../../audit-log-events.md)을 참조하세요.

감사 로그를 검색하려면 먼저 [보안 및 준수 센터](https://protection.office.com)에서 감사를 켜야 합니다. 자세한 내용은 [감사 로그 검색 설정 및 해제](https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014)를 참조하세요. 감사 데이터는 감사가 켜진 시점부터만 사용할 수 있습니다.

## <a name="related-articles"></a>관련 기사

- [Teams의 교대 근무](../shifts-for-teams-landing-page.md)
- [데이터 FAQ 이동](shifts-data-faq.md)
- [Shifts 커넥터](shifts-connectors.md)
- [일선 근로자를 위한 교대 근무 도움말](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b)
- [Teams에서 사용자에게 정책 할당](../../policy-assignment-overview.md)
