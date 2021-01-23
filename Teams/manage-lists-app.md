---
title: 조직의 목록 앱 관리
author: cichur
ms.author: v-cichur
ms.reviewer: anach,v-jasuk
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
description: 조직의 사용자에 대해 Teams에서 목록 앱을 관리하는 방법을 배워야 합니다.
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- microsoftcloud-healthcare
- m365initiative-lists
appliesto:
- Microsoft Teams
ms.custom: ''
ms.openlocfilehash: e0fb125ede9300395e045a0c5640abd075547562
ms.sourcegitcommit: 04eba352d9e203aa9cd1282c4f4c7158a0469678
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2021
ms.locfileid: "49944613"
---
# <a name="manage-the-lists-app-for-your-organization-in-microsoft-teams"></a>Microsoft Teams에서 조직의 목록 앱 관리

## <a name="overview-of-lists"></a>목록 개요

Microsoft Teams의 목록 앱은 조직의 사용자가 정보를 추적하고, 작업을 구성하고, 워크플로를 관리하는 데 도움이 됩니다. 목록에서 사용자는 사용자 지정 가능한 보기, 규칙 및 경고를 사용하여 문제, 자산, 루틴, 연락처, 인벤토리, 인시던트, 대출, 환자 등의 데이터를 추적하여 팀의 모든 사용자를 동기화할 수 있습니다.

Teams에서 사용자는 채널의 탭으로 목록에 액세스합니다. 클릭하여 탭 갤러리를 열고 새 목록 앱 탭 인스턴스를 채널에 추가하여 **+** 시작할 수 있습니다.

![탭 갤러리에서 앱 나열](media/lists-tab.png)

사용자는 동일한 팀 내에서 또는 액세스 권한이 있는 다른 SharePoint 사이트에서 새 목록을 만들거나 기존 목록을 고정할 수 있습니다. 기존 목록의 구조에 따라 기본 제공 서식 파일이나 Excel 통합 문서에서 데이터를 가져와 새 목록을 처음부터 만들 수 있습니다. 목록 앱은 Teams 데스크톱, 웹 및 모바일 클라이언트에서 사용할 수 있습니다.

![목록 앱에서 목록을 만드는 방법](media/lists-create-list.png)

## <a name="templates"></a>템플릿

목록의 템플릿은 사용자에 대한 일반적인 정보 추적 시나리오에 맞게 조정됩니다. 각 서식 파일은 목록 보기 및 세부 정보 보기 수준 모두에 미리 정의되어 있는 목록 구조, 양식 레이아웃 및 서식 옵션이 제공되어 사용자가 빠르게 시작할 수 있도록 합니다. 템플릿을 선택하면 일부 샘플 데이터와 함께 목록의 모양을 미리 볼 수 있습니다. 다음은 조직의 팀이 목록에서 미리 정의한 서식 파일을 사용하는 방법에 대한 몇 가지 예입니다.

- 문제를 추적하고 문제 추적기 템플릿을 사용하여 문제를 해결합니다.
- 이벤트 iterary 템플릿을 사용하여 모든 이벤트 세부 정보를 구성합니다.
- 환자 템플릿을 사용하여 의료 조직에서 의료 팀의 환자 요구 및 상태를 기록하여 진료를 모니터링하고 조정합니다.
- 대출 템플릿을 사용하여 대출 애플리케이션의 상태를 추적합니다.

## <a name="example-scenario"></a>예제 시나리오

지역 우체국은 해당 지역의 메일을 정렬하고 배달하는 업무를 담당합니다. 매일 아침 우체국에는 매일 목표를 검토하고, 공지 사항을 공유하고, 알려진 인시던트에 대해 논의할 수 있는 팀이 있습니다.

휴지통이 끝날 때 메일 운송업체는 메일을 수리하고 배달 경로를 시작해야 합니다. 사고는 차량 사고, 개 관련 문제 또는 소셜 불안 시위와 같은 경로를 따라 발생할 수 있습니다. 메일 통신 사업자에서 인시던트가 발생하면 모바일 장치에서 Teams를 사용하여 인시던트 세부 정보를 기록합니다. 인시던트 세부 정보는 팀 채널의 목록에서 추적됩니다. 현장에서 메일 통신업체를 비롯한 팀의 모든 사람이 이 정보를 보고 정보를 계속 알 수 있습니다.

Teams로 이동하기 전에 메일 통신 사업자는 우체국으로 돌아가 하드 복사 양식을 작성하여 Excel 스프레드시트에 입력된 인시던트를 보고해야 합니다. Teams는 메일 통신사에게 먼저 목록을 사용하여 현장에서 인시던트가 발생하면 보고하고, 인시던트 세부 정보를 팀 구성원과 공유하고, 채널에서 인시던트에 대한 대화를 나누고, 인시던트 해결을 위한 인시던트에 대한 경험을 제공합니다.

## <a name="what-you-need-to-know-about-lists"></a>목록에 대해 알아야 할 항목

### <a name="lists-is-available-in-every-team-and-channel"></a>목록은 모든 팀 및 채널에서 사용할 수 있습니다.

목록은 모든 Teams 사용자에 대해 사전 설치되어 있으며 모든 팀 및 채널의 탭 갤러리에서 직접 사용할 수 있습니다. 즉, 사용자가 Teams 앱 스토어로 이동하여 설치할 필요가 없습니다.

### <a name="lists-and-sharepoint"></a>목록 및 SharePoint

목록 데이터는 SharePoint Online 팀 사이트에 저장됩니다. SharePoint Online이 Teams와 상호 작용하는 방법에 대한 자세한 내용은 SharePoint Online 및 [비즈니스용 OneDrive가 Teams와 상호 작용하는 방법을 참조하세요.](SharePoint-OneDrive-interact.md)

SharePoint에서 설정된 사용 권한은 목록 앱에서 만든 목록에 적용됩니다. 기본적으로 목록은 소속된 사이트의 사용 권한을 상속합니다. 이러한 권한은 사용자가 목록을 만들거나 편집할 수 있는지 여부와 같이 사용자가 수행할 수 있는 작업 유형을 관리합니다. 자세한 내용은 [SharePoint](https://docs.microsoft.com/sharepoint/understanding-permission-levels) Server의 SharePoint 및 사용자 권한 및 사용 권한 수준의 [사용 권한 수준을 참조합니다.](https://docs.microsoft.com/sharepoint/sites/user-permissions-and-permission-levels)

특정 시나리오에서는 사용자가 목록에서 수행할 수 있는 작업을 제한할 수 있습니다. 예를 들어 팀의 사용자가 목록 보기를 편집하여 모든 팀 구성원에 대해 변경하고, 팀 소유자 또는 특정 팀 구성원만 목록 보기를 편집하도록 허용할 수 있습니다. 자세한 내용은 SharePoint 목록 또는 라이브러리에 대한 사용 권한 [사용자 지정을 참조하세요.](https://support.microsoft.com/office/customize-permissions-for-a-sharepoint-list-or-library-02d770f3-59eb-4910-a608-5f84cc297782#ID0EAACAAA=Online,_2019,_2016,_2013)

> [!NOTE]
> 이 시점에서 팀의 소유자 및 구성원 권한은 목록 또는 목록 앱의 동작을 관리하는 팀 사이트의 사용 권한에 어떤 방식으로든 연결되지 않습니다. 그러나 고객 피드백 및 사용 현황에 따라 제품의 향후 이행을 위해 고려됩니다.  

### <a name="limitations"></a>제한 사항

목록을 통해 사용자는 데스크톱, 웹 및 모바일 환경을 사용할 수 있습니다. 사용자가 Teams 모바일 클라이언트의 목록을 사용하여 새 목록을 만들거나 기존 목록을 고정할 수 없습니다. Teams 모바일 클라이언트에서 목록을 보거나 편집하려면 먼저 Teams 데스크톱 또는 웹 클라이언트의 목록을 사용하여 목록을 만들거나 추가해야 합니다.

게스트는 목록을 만들거나 삭제할 수 없습니다. 기존 목록에 목록 항목을 추가하고, 목록 항목에 대한 새 대화를 시작하고, 목록 항목에 대한 기존 대화에 회신할 수 있습니다.

### <a name="lists-and-the-sharepoint-app"></a>목록 및 SharePoint 앱

조직의 사용자가 SharePoint 앱을 사용하여 목록을 만든 경우 해당 목록은 사용자로부터 필요한 작업 없이 자동으로 목록으로 이동됩니다. Teams에서 가장 풍부하고 풍부한 목록 통합 환경을 얻습니다. 목록 앱을 사용하여 기존 목록을 고정합니다.

## <a name="set-up-lists"></a>목록 설정

### <a name="enable-or-disable-lists-in-your-organization"></a>조직에서 목록 사용 또는 사용 안 하도록 설정

목록은 조직의 모든 Teams 사용자에 대해 기본적으로 사용하도록 설정됩니다. Microsoft Teams 관리 센터의 앱 관리 페이지에서 구성 [](manage-apps.md) 수준에서 앱을 끄거나 끄면 됩니다.

1. Microsoft Teams 관리 센터의 왼쪽 탐색 모음에서 Teams 앱 **관리**  >  **앱으로 이동하세요.**
2. 다음 중 하나를 수행합니다.

    - 조직에 대한 목록을 해제하려면 목록 앱을 검색하고 선택한 다음 차단을 **클릭합니다.**
    - 조직에 대한 목록을 켜려면 목록 앱을 검색하고 선택한 다음 허용을 **클릭합니다.**

### <a name="enable-or-disable-lists-for-specific-users-in-your-organization"></a>조직의 특정 사용자에 대한 목록 사용 또는 사용 안 하도록 설정

조직의 특정 사용자가 목록을 사용할 수 있도록 허용하거나 차단하려면 앱 관리 페이지에서 [](manage-apps.md) 조직에 대해 목록이 켜져 있는지 확인한 다음 사용자 지정 앱 사용 권한 정책을 만들고 해당 사용자에게 할당합니다. 자세한 내용은 [Teams에서 앱 사용 권한 정책 관리를 참조하세요.](teams-app-permission-policies.md)

## <a name="search-the-audit-log-for-list-events"></a>목록 이벤트에 대한 감사 로그 검색

목록은 엔터프라이즈 수준 감사를 통해 사용하도록 설정되어 있으므로 Security & 준수 센터의 감사 로그에서 목록을 검색하고 항목 이벤트를 나열할 수 있습니다. 자세한 내용은 Security & 준수 센터에서 감사 [로그 검색을 참조합니다.](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance)

Teams의 목록 앱과 관련된 감사 이벤트 목록은 SharePoint 목록 [활동을 참조하세요.](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance#sharepoint-list-activities)

감사 로그를 검색하려면 먼저 Security & 준수 센터에서 감사를 [켜야 합니다.](https://protection.office.com) 감사 데이터는 감사를 설정한 시점에서만 사용할 수 있습니다.

## <a name="power-automate-power-apps-and-graph-api"></a>Power Automate, Power Apps 및 Graph API

목록은 [워크플로에 대한 Power Automate](https://docs.microsoft.com/power-automate/flow-types) 및 목록 [양식에 대한 Power Apps를](https://docs.microsoft.com/powerapps/maker/canvas-apps/customize-list-form) 지원 합니다. 개발자는 [목록 API를](https://docs.microsoft.com/sharepoint/dev/sp-add-ins/working-with-lists-and-list-items-with-rest) 사용하여 Microsoft Graph를 통해 목록 데이터를 원본으로 연결할 수 있습니다.

## <a name="give-feedback-or-report-an-issue"></a>피드백 제공 또는 문제 보고
  
피드백을 보내거나 문제를 보고하려면  Teams의 왼쪽 탐색 아래쪽에 있는 도움말을 클릭한 다음 문제 **보고를 선택합니다.** 목록을 **선택한** 다음, 발생하는 문제의 사용자 의견이나 세부 정보를 입력합니다.

## <a name="related-topics"></a>관련 항목

- [도움말 설명서를 나열합니다.](https://support.microsoft.com/office/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b#PickTab=Lists)
