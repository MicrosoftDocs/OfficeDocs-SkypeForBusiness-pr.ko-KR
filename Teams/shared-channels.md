---
title: Microsoft Teams의 공유 채널
author: MikePlumleyMSFT
ms.author: mikeplum
manager: serdars
ms.reviewer: arundas
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.custom: chat-teams-channels-revamp
ms.collection:
- M365-collaboration
- m365initiative-securecollab
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.localizationpriority: high
search.appverid: MET150
description: Microsoft Teams에서 공유 채널을 사용하고 관리하는 방법을 알아보세요.
ms.openlocfilehash: b7f151b68bf37ccf3e14e3a442b4d2b1c6acc52f
ms.sourcegitcommit: dc5b3870fd338f7e9ab0a602a44eaf9feb595b2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/30/2022
ms.locfileid: "69199150"
---
# <a name="shared-channels-in-microsoft-teams"></a>Microsoft Teams의 공유 채널

Microsoft Teams의 공유 채널은 팀에 없는 사용자를 초대할 수 있는 공동 작업 공간을 만듭니다. 공유 채널의 소유자나 구성원인 사용자만 채널에 액세스할 수 있습니다. 게스트(조직의 Azure Active Directory 게스트 계정이 있는 사용자)는 공유 채널에 추가할 수 없지만 Azure AD B2B 직접 연결을 사용하여 조직 외부의 사용자를 공유 채널에 참여하도록 초대할 수 있습니다.

모두 다른 팀의 구성원인 사용자 그룹과 공동 작업하려는 경우 공유 채널을 사용할 수 있습니다. 예를 들어 동일한 프로젝트 또는 제품과 관련하여 다양한 부서에서 작업하는 엔지니어링, 영업, 지원 담당자가 공유 채널을 사용하여 공동 작업할 수 있습니다.

공유 채널의 구성원으로 추가된 사용자만 공유 채널을 볼 수 있고 여기에 참여할 수 있습니다. 공유 채널이 연결된 팀의 다른 구성원은 채널을 볼 수 없습니다.

공유 채널이 만들어지면 해당 채널이 상위 팀에 연결되어 다른 팀으로 이동할 수 없습니다. 또한 공유 채널은 표준 채널로 전환할 수 없으며, 그 반대로도 전한할 수 없습니다.

[공유 채널을 다른 유형의 채널과 비교합니다](/microsoftteams/teams-channels-overview#channel-feature-comparison).

## <a name="getting-started-with-shared-channels"></a>공유 채널 시작

Shared channels is enabled by default in Teams. You can choose if people can create shared channels, if they can share them with people outside your organization, and if they can participate in external shared channels by [creating a channel policy](/MicrosoftTeams/teams-policies).

조직 외부 사용자와 채널을 공유하려는 경우 중요한 계획 고려 사항은 [외부 공동 작업 계획](/microsoft-365/solutions/plan-external-collaboration)을 참조하세요.

조직 외부 사용자와 채널을 공유하려면 Azure AD에서 테넌트 간 액세스 설정을 구성해야 합니다. 채널을 공유하려는 각 조직도 이 구성을 완료해야 합니다. 자세한 내용은 [채널에서 외부 참가자와 공동 작업](/microsoft-365/solutions/collaborate-teams-direct-connect)을 참조하세요.

## <a name="shared-channel-creation"></a>공유 채널 만들기

팀 소유자만 공유 채널을 만들 수 있습니다. 팀 구성원과 게스트는 만들 수 없습니다. 공유 채널을 만드는 기능은 조직 수준에서 관리할 수 있습니다. 관리자는 [정책](teams-policies.md)을 사용하여 조직의 어떤 사용자가 공유 채널을 만들도록 허용되는지를 제어할 수 있습니다.

공유 채널을 만드는 사람은 공유 채널 소유자가 되며 공유 채널 소유자만 공유 채널 소유자만 구성원을 채널에서 직접 추가하거나 제거할 수 있습니다. (원하는 경우 둘 이상의 소유자를 추가할 수 있습니다.) 공유 채널 소유자는 조직의 모든 사용자를 만든 공유 채널에 추가할 수 있습니다. 공유 채널의 구성원은 보안이 적용된 대화 공간을 갖게 되며, 새로 추가된 구성원도 해당 공유 채널의 모든 대화(기존 대화도)를 볼 수 있습니다.

팀 소유자는 팀 내 모든 공유 채널의 이름을 볼 수 있으며, 팀 내 어떤 공유 채널이든 삭제할 수도 있습니다. 팀 소유자가 공유 채널의 구성원이 아니면 대화 또는 공유 채널 내 파일 및 공유 채널의 구성원 목록을 볼 수 없습니다.

팀 구성원은 자신이 추가된 공유 채널만 볼 수 있습니다.

팀을 복제해도 연결된 공유 채널은 복제되지 않습니다.

## <a name="shared-channel-deletion"></a>공유 채널 삭제

삭제된 공유 채널은 삭제 후 30일 이내에 복원할 수 있습니다. 삭제된 공유 채널이 복원되면 모든 이전 멤버 자격(개인 및 팀 공유)이 복원됩니다.

삭제된 팀은 삭제 후 30일 이내에 복원할 수 있습니다. 팀이 삭제되면 모든 공유 채널도 삭제됩니다. 삭제된 팀이 복원되면 모든 공유 채널도 모든 공유 관계와 함께 복원됩니다.

팀을 보관하면 개별 공유는 그대로 유지되지만 부모 팀이 아닌 팀과의 공유는 제거됩니다. 보관된 팀이 보관되지 않은 경우 모든 공유 채널은 개별 공유로만 복원됩니다.

## <a name="adding-and-removing-owners-and-members"></a>소유자와 구성원 추가 및 제거

공유 채널 소유자가 하나 이상의 공유 채널을 운영하는 마지막 소유자일 경우 Teams 클라이언트를 통해 제거할 수 없습니다.

마지막 공유 채널 소유자가 조직을 떠나거나 팀과 연결된 Microsoft 365 그룹에서 제거되면 조직의 공유 채널 구성원이 자동으로 공유 채널 소유자로 승격됩니다. 조직에서 홍보할 구성원이 없으면 공유 채널은 소유자가 없는 상태로 유지됩니다. Teams 관리자는 채널 소유자를 수동으로 할당해야 합니다. 이 상황을 방지하려면 둘 이상의 소유자를 추가하는 것이 좋습니다.

구성원(사용자 유형 속성)으로 변환된 게스트를 포함하여 공유 채널에 추가할 수 없습니다.

> [!NOTE]
> 두 참가자가 Azure Active Directory에서 일치하지 않는 경우 외부 참가자는 이메일 주소가 아닌 UPN을 사용하여 추가해야 합니다.

## <a name="channel-owner-settings"></a>채널 소유자 설정

각 공유 채널에는 구성원 추가 및 제거, 탭 추가, 그리고 전체 채널에 대한 @멘션 기능 등 채널 소유자가 관리할 수 있는 고유한 설정이 있습니다. 이러한 설정은 상위 팀 설정과는 독립됩니다. 공유 채널을 만들면 상위 팀에서 설정이 상속되며, 이후에 해당 설정을 변경하면 상위 팀 설정과 독립적으로 지정됩니다.

공유 채널 소유자는 **채널 관리** 를 클릭한 후 **구성원** 및 **설정** 탭을 사용하여 구성원을 추가하거나 제거하고 설정을 편집할 수 있습니다.

## <a name="shared-channel-owner-and-member-actions"></a>공유 채널 소유자 및 구성원 작업

다음 표에는 소유자, 구성원 및 게스트가 공유 채널에서 수행할 수 있는 작업이 나와 있습니다.

|작업  |팀 소유자|팀 구성원|팀 게스트|공유 채널 소유자|공유 채널 구성원|공유 채널 외부 참가자|
|---------|---------|---------|---------|---------|---------|---------|
|공유 채널 만들기|관리자가 제어|관리자 및 팀 소유자가 제어|아니요|해당 없음|아니요|아니요|
|공유 채널 삭제|예|아니요|아니요|예|아니요|아니요|
|공유 채널 나가기|해당 없음|해당 없음|해당 없음|예(마지막 소유자가 아닌 경우)|예|예|
|공유 채널 편집|아니요|해당 없음|해당 없음|예|아니요|아니요|
|삭제된 공유 채널 복원|예|아니요|아니요|예|아니요|아니요|
|구성원 추가|아니요|해당 없음|해당 없음|예|아니요|아니요|
|설정 편집|아니요|해당 없음|해당 없음|예|아니요|아니요|
|탭 및 앱 관리|아니요|해당 없음|해당 없음|예, 팀용 앱을 설치해야 합니다.|채널 소유자가 제어|아니요|

## <a name="shared-channel-sharepoint-sites"></a>공유 채널 SharePoint 사이트

각 공유 채널에는 [고유한 SharePoint 사이트](/SharePoint/teams-connected-sites)가 있습니다. 별도의 사이트는 공유 채널 파일에 대한 액세스 권한이 공유 채널의 구성원에게만 제한되도록 하기 위함입니다. 이러한 사이트는 기본적으로 문서 라이브러리를 통해 만들어지며, [사이트 관리 인터페이스](https://support.office.com/article/A2F2A5C2-093D-4897-8B7F-37F86D83DF04)를 통해 전체 기능이 적용된 사이트로 손쉽게 업그레이드할 수 있습니다. 각 사이트는 상위 팀의 사이트와 동일한 지역에서 만들어집니다. 이러한 간단한 사이트에는 사용자 지정 템플릿 ID인 "TEAMCHANNEL#1"이 있어 PowerShell 및 Graph API를 통해 더욱 손쉽게 관리할 수 있습니다. 

공유 채널 사이트는 상위 팀의 민감도 레이블을 상속합니다. 이는 채널이 다른 팀과 직접 공유되는 경우에도 마찬가지입니다.

> [!NOTE]
> 채널의 소유자 또는 구성원 권한이 있는 사용자만 공유 채널 사이트의 콘텐츠에 액세스할 수 있습니다. 부모 팀의 사용자와 관리자도 해당 콘텐츠에 액세스할 수 없습니다(채널 구성원인 경우 제외).

사이트 소유자와 구성원 그룹의 구성원 자격은 공유 채널의 구성원 자격과 동기화되어 유지됩니다. 공유 채널 사이트에 대한 사이트 사용 권한은 SharePoint를 통해 독립적으로 관리할 수 없습니다. 

Teams는 공유 채널 사이트의 수명 주기를 관리합니다. 사이트가 Teams 외부에서 삭제되면 공유 채널이 활성 상태인 경우 4시간 이내에 자동으로 복원됩니다. 사이트가 영구적으로 삭제될 경우 새 사이트가 공유 채널에 대해 프로비전됩니다.

공유 채널 또는 공유 채널을 포함하는 팀이 복원되면 사이트도 함께 복원됩니다. 공유 채널 사이트가 복원된 상태에서 공유 채널에 대해 30일의 일시 삭제 기간이 지난 경우 해당 사이트는 독립 실행형 사이트로 작동합니다.

## <a name="shared-channel-messages"></a>공유 채널 메시지

공유 채널 메시지는 그룹 사서함이 아닌 공유 채널과 연결된 전용 시스템 사서함에 저장됩니다.

공유 채널 메시지에 대한 eDiscovery 검색을 수행하는 방법에 대한 자세한 내용은 [Microsoft Teams의 콘텐츠에 대한 eDiscovery 조사 수행](ediscovery-investigation.md)을 참조하세요.

## <a name="considerations-around-file-access-in-shared-channels"></a>공유 채널의 파일 액세스에 대한 고려 사항

공유 채널의 파일, 폴더 및 OneNote 전자 필기장을 [표준 SharePoint 파일 공유](https://support.microsoft.com/office/1fe37332-0f9a-4719-970e-d2578da4941c)를 사용하여 채널 외부(조직 외부는 아님)와 공유할 수 있습니다.

사용자에게 SharePoint를 통해 공유 채널의 파일, 폴더 또는 전자 필기장에 대한 액세스 권한이 부여된 경우, 팀 또는 공유 채널에서 사용자를 제거해도 파일, 폴더 또는 전자 필기장에 대한 사용자의 액세스 권한은 제거되지 않습니다.

기존 전자 필기장이 공유 채널의 탭으로 추가될 경우 공유 채널에 대한 액세스는 변경되지 않습니다. 전자 필기장은 기존 사용 권한을 보존합니다.

## <a name="resources-for-your-users"></a>사용자에 대한 리소스

다음 문서는 공유 채널을 사용하는 조직의 사용자에게 유용할 수 있습니다.

[Teams에서 공유 채널 만들기](https://support.microsoft.com/office/80712457-579e-42b2-b54f-112329578aaa)

[Teams 구성원들과 채팅 공유](https://support.microsoft.com/office/5f60de2d-0080-4e55-b26f-33a9dafa120e)

[팀과 채널 공유](https://support.microsoft.com/office/b2e89992-2708-4583-b11e-bbb6edb4f1c3)

[Teams에서 공유 채널과 다른 채널 유형을 사용하는 이유는 무엇인가요?](https://support.microsoft.com/office/e6ad61d0-6b3f-4e1b-baac-63e2978bd92e)

[Teams의 게스트 및 공유 채널](https://support.microsoft.com/office/612de4ce-e7a3-4579-b086-bb8ff9f2d11e)

[Teams의 공유 채널 소유자 및 구성원 역할](https://support.microsoft.com/office/75b379f4-8e9c-4202-acf1-6ffc3878a2d7)

## <a name="limits-for-shared-channels"></a>공유 채널에 대한 제한

다음 표에서는 최대 채널 및 구성원 수를 설명합니다.

|최대...|값|참고|
|:---------|:----|:----|
|팀 구성원|25,000|팀의 모든 사용자와 공유 채널의 직접 구성원을 포함합니다.|
|팀당 공유 채널|200|팀과 호스트되고 공유됩니다. (30일 복구 기간 동안 삭제된 채널을 포함합니다.)|
|팀과 채널을 공유할 수 있습니다.|50|부모 팀 제외|
|공유 채널의 구성원|최대 50개 팀을 포함하여 5,000명의 직접 구성원 (각 팀은 이 제한을 위해 채널을 한 명의 구성원으로 카운트하여 공유됩니다.)|실시간 업데이트는 한 번에 25,000명의 사용자만 사용할 수 있으며 25,000명의 사용자만 채널 목록에 표시됩니다.|

다음 제한 사항도 적용됩니다.

- Azure AD 회사 또는 학교 계정만 외부 참가자를 지원합니다.

- 공유 채널은 Stream, Planner, Forms를 제외한 탭을 지원합니다.

- 봇, 커넥터 및 메시지 확장은 지원되지 않습니다.

- 기존 팀에서 팀을 만들면 기존 팀의 공유 채널은 복사되지 않습니다.

- 공유 채널의 알림은 누락된 활동 전자 메일에 포함되지 않습니다.

- 공유 채널은 수업 팀에서 지원되지 않습니다.

## <a name="supported-apps-in-shared-channels"></a>공유 채널에서 지원되는 앱

공유 채널용으로 앱을 준비하는 방법에 대한 자세한 내용은 [Microsoft Teams Connect를 사용하여 조직 간 공동 작업을 위해 앱을 여는 방법](https://mybuild.microsoft.com/sessions/4d84d73c-08de-4f56-990b-2a73b2037df1)을 참조하세요.

공유 채널에서 사용할 수 있는 앱은 다음과 같습니다. 

- 활동
- Adobe Acrobat Sign
- Asana
- Calendar Pro
- 통화
- 채팅
- Code by Vivani
- Conceptboard
- Excel
- FileBrowser
- 파일
- Flipgrid
- Freehand by InVision
- HeyTaco
- Jira Cloud
- Kahoot!
- 목록
- Lucidchart
- Lumio
- MeisterTask
- MindMeister
- Mindomo
- Miro
- Monday.com
- MURAL
- Nearpod
- OneNote
- PDF
- Pear Deck
- PowerPoint
- Priority Matrix
- Quicklinks
- Quizlet
- Saved
- Scrum-Poker
- 검색
- SharePoint
- SharePoint Pages
- Slido
- Smartsheet
- SurveyMonkey
- Tasks in a Box
- Teams Manager
- TeamViewer
- 팀워크
- Testportal
- TrackingTime
- Trello
- Vevox
- Visio
- VSTS
- Wakelet
- Web
- Wooclap
- Word
- YouTube
- Zendesk
- Zoho Projects

## <a name="related-topics"></a>관련 주제

[B2B 직접 연결 개요](/azure/active-directory/external-identities/b2b-direct-connect-overview)

[B2B 직접 연결에 대한 테넌트 간 액세스 설정 구성](/azure/active-directory/external-identities/cross-tenant-access-settings-b2b-direct-connect)

[Teams의 팀 및 채널 개요](teams-channels-overview.md)

[Microsoft Teams의 비공개 채널](/microsoftteams/private-channels)
