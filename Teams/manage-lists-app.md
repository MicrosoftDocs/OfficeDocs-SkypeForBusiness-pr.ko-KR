---
title: 조직의 목록 앱 관리
author: LanaChin
ms.author: v-lanac
ms.reviewer: anach,v-jasuk
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 조직의 사용자를 위해 팀에서 목록 앱을 관리 하는 방법에 대해 알아봅니다.
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: ''
ms.openlocfilehash: d8225198a3d56c731193d72e98d4ebebe2954a2f
ms.sourcegitcommit: 0a51738879b13991986a3a872445daa8bd20533d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2020
ms.locfileid: "48766738"
---
# <a name="manage-the-lists-app-for-your-organization-in-microsoft-teams"></a>Microsoft 팀에서 조직의 목록 앱 관리

## <a name="overview-of-lists"></a>목록 개요

Microsoft 팀의 목록 앱은 조직의 사용자가 정보를 추적 하 고, 작업을 구성 하 고, 워크플로를 관리할 수 있도록 합니다. 사용자는 목록을 사용 하 여 문제점, 자산, 루틴, 연락처, 재고, 사건, 대출, 환자 등의 데이터를 추적 하 고, 사용자 지정 가능한 보기, 규칙 및 알림을 사용 하 여 팀의 모든 구성원을 동기화 된 상태로 유지할 수 있습니다.

팀에서 사용자는 채널에서 목록을 탭으로 액세스할 수 있습니다. 클릭 **+** 하 여 탭 갤러리를 열고 새 목록 앱 탭 인스턴스를 채널에 추가 하 여 시작 하세요. 

![탭 갤러리의 목록 앱 스크린샷](media/lists-tab.png)

사용자가 새 목록을 만들거나 같은 팀 내에서 또는 액세스 권한이 있는 다른 SharePoint 사이트에서 기존 목록을 고정할 수 있습니다. 새 목록은 기본 제공 서식 파일에서 기존 목록의 구조를 기반으로 만들거나 Excel 통합 문서에서 데이터를 가져와 처음부터 만들 수 있습니다. 목록 앱은 팀 데스크톱, 웹 및 모바일 클라이언트에서 사용할 수 있습니다.

![목록 앱에서 목록을 만드는 방법에 대 한 스크린샷](media/lists-create-list.png)

## <a name="templates"></a>템플릿과

목록의 서식 파일은 사용자에 대 한 일반적인 정보 추적 시나리오에 맞게 조정 됩니다. 각 서식 파일에는 목록 보기 및 자세히 보기 수준에서 미리 정의 된 목록 구조, 양식 레이아웃 및 서식 옵션이 제공 되며,이를 통해 사용자가 빠르게 시작할 수 있습니다. 서식 파일을 선택한 후 몇 가지 예제 데이터와 함께 목록이 표시 되는 모양에 대 한 미리 보기를 가져옵니다. 다음은 조직의 팀에서 목록에 미리 정의 된 서식 파일을 사용 하는 방법에 대 한 몇 가지 예입니다.

- 문제를 추적 하 고 문제 추적기 서식 파일을 사용 하 여 클로저로 전환 합니다.
- 이벤트 여행 서식 파일을 사용 하 여 모든 이벤트 세부 정보를 구성 합니다.
- 환자 서식 파일을 사용 하 여 의료 기관에서 상태 팀의 요구 사항과 상태를 기록 하 여 주의를 모니터링 하 고 조정 합니다.
- 대출금 서식 파일을 사용 하 여 대출 응용 프로그램의 상태를 추적 합니다.

## <a name="example-scenario"></a>예제 시나리오

지역 우체국은 학구에서 메일을 정렬 하 고 배달 하는 업무를 담당 합니다. 우체국에는 매일 목표를 검토 하 고, 공지 사항을 공유 하 고, 알려진 사고에 대해 토론할 수 있는 팀 huddle 있습니다.

Huddle 후 메일 캐리어가 메일을 선택 하 고 배달 경로를 시작 합니다. 사고는 경로 (예: 차량 사고, 강아지 관련 문제점 또는 소셜 unrest protest)에 따라 발생할 수 있습니다. 메일 캐리어가 인시던트를 발생 하면 모바일 장치에서 팀을 사용 하 여 팀 채널의 목록에서 추적 되는 인시던트 세부 정보를 기록 합니다. 필드의 메일 통신 회사를 포함 하 여 팀의 모든 사용자가이 정보를 보고 알림을 받을 수 있습니다.

팀으로 이동 하기 전에 메일 캐리어가 다시 우체국으로 돌아가 Excel 스프레드시트에 입력 된 인시던트를 보고 하기 위해 하드 카피 양식을 완료 해야 했습니다. 팀은 메일 통신 회사를 사용 하 여 먼저 필드에 인시던트를 보고할 수 있는 모바일 기능을 제공 하 고, 팀 구성원과 사고 세부 정보를 공유 하 고, 채널에서 해당 항목에 대 한 대화를 주고, 문제 해결을 위한 처리를 할 때 발생 합니다.

## <a name="what-you-need-to-know-about-lists"></a>목록에 대해 알아야 할 사항

### <a name="lists-is-available-in-every-team-and-channel"></a>목록은 모든 팀과 채널에서 사용할 수 있습니다.

목록은 모든 팀 사용자를 위해 미리 설치 되어 있으며 모든 팀과 채널의 탭 갤러리에서 직접 사용할 수 있습니다. 즉, 사용자가 설치 하기 위해 팀 app store로 이동할 필요가 없습니다.

### <a name="lists-and-sharepoint"></a>목록 및 SharePoint

목록 데이터는 SharePoint Online 팀 사이트에 저장 됩니다. SharePoint Online이 팀과 상호 작용 하는 방법에 대 한 자세한 내용은 [Sharepoint online 및 비즈니스용 OneDrive가 팀과 상호 작용 하는 방법](SharePoint-OneDrive-interact.md)에 대해 알아보세요.

SharePoint에 설정 된 사용 권한은 목록 앱에서 만든 목록에 적용 됩니다. 기본적으로 목록은 자신이 속한 사이트의 사용 권한을 상속 합니다. 이러한 권한은 사용자가 목록을 만들거나 편집할 수 있는지 여부와 같이 수행할 수 있는 작업 유형을 제어 합니다. 자세한 내용은 sharepoint Server의 [sharepoint](https://docs.microsoft.com/sharepoint/understanding-permission-levels) 및 [사용자 사용 권한 수준과 권한 수준을](https://docs.microsoft.com/sharepoint/sites/user-permissions-and-permission-levels)참조 하세요.

특정 시나리오에서 사용자가 목록에서 수행할 수 있는 작업을 제한할 수 있습니다. 예를 들어 팀의 사용자가 목록 보기를 편집 하 여 모든 팀 구성원에 대해이를 변경 하 고 팀 소유자나 특정 팀 구성원만 목록 보기를 편집할 수 있도록 할 수 있습니다. 자세히 알아보려면 [SharePoint 목록 또는 라이브러리에 대 한 사용 권한 사용자 지정](https://support.microsoft.com/office/customize-permissions-for-a-sharepoint-list-or-library-02d770f3-59eb-4910-a608-5f84cc297782#ID0EAACAAA=Online,_2019,_2016,_2013)을 참고 하세요.

> [!NOTE]
> 이 시점에서 팀의 소유자 및 구성원 권한은 목록 또는 목록 앱의 동작을 제어 하는 팀 사이트의 사용 권한으로 연결 되지 않습니다. 그러나 고객 의견 및 사용에 따라이는 제품의 이후 반복에 대 한 것으로 간주 됩니다.  

### <a name="limitations"></a>따릅니다

목록이 있으면 사용자가 데스크톱, 웹, 모바일 환경을 이용할 수 있습니다. 사용자가 새 목록을 만들거나 팀 모바일 클라이언트의 목록을 사용 하 여 기존 목록을 고정할 수는 없다는 것이 중요 합니다. 팀 모바일 클라이언트에서 목록을 보거나 편집 하려면 먼저 팀 바탕 화면 또는 웹 클라이언트의 목록을 사용 하 여 목록을 만들거나 추가 해야 합니다.

게스트는 목록을 만들거나 삭제할 수 없습니다. 기존 목록에 목록 항목을 추가 하 고, 목록 항목에 대 한 새 대화를 시작 하 고, 목록 항목에 대 한 기존 대화에 회신할 수 있습니다.

### <a name="lists-and-the-sharepoint-app"></a>목록 및 SharePoint 앱

조직의 사용자가 SharePoint 앱을 사용 하 여 목록을 만든 경우 해당 목록은 사용자가 작업을 수행 하지 않고 목록으로 자동으로 이동 됩니다. 팀의 최상의 통합 경험을 얻으려면 목록 앱을 사용 하 여 기존 목록을 고정 다양.

## <a name="set-up-lists"></a>목록 설정

### <a name="enable-or-disable-lists-in-your-organization"></a>조직의 목록 설정 또는 해제

목록은 조직의 모든 팀 사용자에 대해 기본적으로 사용 하도록 설정 됩니다. Microsoft 팀 관리 센터에서 [앱 관리](manage-apps.md) 페이지의 조직 수준에서 앱을 끄거나 켤 수 있습니다.

1. Microsoft 팀 관리 센터의 왼쪽 탐색 창에서 **팀 앱** 으로  >  **앱 관리** 로 이동 합니다.
2. 다음 중 하나를 수행합니다.

    - 조직의 목록을 끄려면 목록 앱을 검색 하 여 선택한 다음 **차단을** 클릭 합니다.
    - 조직에 대 한 목록을 설정 하려면 목록 앱을 검색 하 여 선택한 다음 **허용** 을 클릭 합니다.

### <a name="enable-or-disable-lists-for-specific-users-in-your-organization"></a>조직의 특정 사용자에 대해 목록 사용 또는 사용 안 함

조직의 특정 사용자가 목록을 사용 하는 것을 허용 하거나 차단 하려면 [앱 관리](manage-apps.md) 페이지에서 조직에 대 한 목록이 설정 되어 있는지 확인 한 다음 사용자 지정 앱 사용 권한 정책을 만들어 해당 사용자에 게 할당 합니다. 자세히 알아보려면 [팀에서 앱 권한 정책 관리](teams-app-permission-policies.md)를 참조 하세요.

## <a name="search-the-audit-log-for-list-events"></a>목록 이벤트 감사 로그 검색

목록은 엔터프라이즈 수준의 감사를 사용 하 여 사용할 수 있으므로 보안 & 준수 센터의 감사 로그에서 목록 및 목록 항목 이벤트를 검색 합니다. 자세히 알아보려면 [보안 & 준수 센터에서 감사 로그 검색](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance)을 참조 하세요.

팀의 목록 앱과 관련 된 감사 이벤트 목록은 [SharePoint 목록 활동](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance#sharepoint-list-activities)을 참조 하세요.

감사 로그를 검색 하려면 먼저 [보안 & 준수 센터](https://protection.office.com)에서 감사를 설정 해야 합니다. 감사 데이터는 감사를 설정한 지점 에서만 사용할 수 있다는 점에 유의 하세요.

## <a name="power-automate-power-apps-and-graph-api"></a>Power 자동화, Power Apps 및 Graph API

목록은 목록 양식에 대 한 워크플로 및 [Power 앱](https://docs.microsoft.com/powerapps/maker/canvas-apps/customize-list-form) 의 [전원 자동화](https://preview.flow.microsoft.comconnectors/shared_sharepointonline/?slug=sharepoint) 를 지원 합니다. 개발자는 목록 [API](https://docs.microsoft.com/sharepoint/dev/sp-add-ins/working-with-lists-and-list-items-with-rest) 를 사용 하 여 Microsoft Graph를 통해 목록의 데이터를 원본으로 연결할 수 있습니다.

## <a name="give-feedback-or-report-an-issue"></a>피드백 제공 또는 문제 보고
  
의견을 보내거나 문제를 신고 하려면 팀에서 왼쪽 탐색의 아래쪽에 있는 **도움말** 을 클릭 한 다음 **문제 보고** 를 선택 합니다. **목록을** 선택 하 고 발생 한 문제에 대 한 피드백 또는 세부 정보를 입력 합니다.

## <a name="related-topics"></a>관련 항목

- [도움말 문서를 표시 합니다.](https://support.microsoft.com/office/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b#PickTab=Lists)
