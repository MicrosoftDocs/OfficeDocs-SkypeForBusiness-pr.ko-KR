---
title: Microsoft Teams에 오신 것을 환영합니다.
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: LolaJ
description: 조직에서 Microsoft Teams를 배포하기 위한 올바른 경로를 찾습니다. Teams 인프라 및 Microsoft 365 혹은 Office 365를 통한 Teams의 사용에 대해 알아보세요.
localization_priority: Priority
search.appverid: MET150
ms.collection:
- M365-collaboration
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.dashboard.allteamsdocuments
appliesto:
- Microsoft Teams
ms.openlocfilehash: 11fe80ef9ee96b0eb1c4c9f4ebc1613549efc059
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/06/2020
ms.locfileid: "46582465"
---
# <a name="welcome-to-microsoft-teams"></a>Microsoft Teams에 오신 것을 환영합니다.
조직에서 Microsoft Teams의 관리자인 경우 제대로 찾아오셨습니다. Teams를 시작할 준비가 되면 [Teams 배포 방법](How-to-roll-out-teams.md)과 함께 시작해보겠습니다.

Teams를 새로 사용하는 사용자로서 자세히 알아보려면 당사의 짧은 [Teams에 오신 것을 환영합니다](https://www.youtube.com/embed/s3aQV3T0D6c) 비디오를 시청하세요(55초).

Teams 관리자를 위한 Teams에 오신 것을 환영합니다 비디오를 놓치지 마세요(3분 조금 초과).

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE47cdp]

최종 사용자 Teams 도움말을 찾고 있는 경우 앱의 왼쪽에 있는 **도움말**을 클릭하거나 [Microsoft Teams 도움말 센터](https://support.office.com/teams)로 이동합니다. 교육을 받으려면 [Microsoft Teams 교육](training-microsoft-teams-landing-page.md)으로 이동합니다. 

## <a name="teams-architecture"></a>Teams 아키텍처

Teams는 Microsoft 365 그룹, Microsoft Graph, Microsoft 365 및 Office 365의 나머지와 동일한 엔터프라이즈 수준의 보안, 규정 준수 및 관리 용이성을 기반으로 빌드됩니다. Teams는 Azure Active Directory(Azure AD)에 저장 된 ID를 활용합니다. Teams는 사용자가 오프라인 상태이거나 네트워크 상태가 불규칙해도 계속해서 작동합니다.

Microsoft 365의 환경에서 Teams가 부합하는 위치를 확인하려면 이 아키텍처 포스터 [Microsoft 365의 일부로서의 Teams](teams-architecture-solutions-posters.md#teams-as-part-of-microsoft-365)를 확인하세요.

팀을 만들면 다음과 같은 항목이 생성됩니다.
- 새 [Microsoft 365 그룹](office-365-groups.md)
- 팀 파일을 저장하는 [SharePoint Online](sharepoint-onedrive-interact.md) 사이트 및 문서 라이브러리
- [Exchange Online](exchange-teams-interact.md) 공유 사서함 및 일정
- OneNote 전자 필기장
- Planner, Power BI 등과 같은 다른 Microsoft 365 및 Office 365 앱으로 연결

기존의 그룹에서 팀을 만들면 해당 그룹의 구성원, 사이트, 사서함 및 전자 필기장이 Teams에 표시됩니다. 자세한 내용은 [IT 설계자용 Microsoft 365의 그룹](teams-architecture-solutions-posters.md#groups-in-microsoft-365) 포스터를 참조하세요.

Teams를 사용자 지정하고 확장하려면 [앱, 봇 그리고 커넥터](deploy-apps-microsoft-teams-landing-page.md)를 통해 타사 앱을 추가합니다. Teams를 사용하여 조직 외부의 사용자를 팀 또는 채널에 [게스트로 추가](guest-access.md)하여 포함시킬 수 있습니다. Microsoft 365 및 Office 365의 일부로서 Teams는 조직에 필요한 팀워크 허브를 구축할 수 있는 견실한 [개발 플랫폼](https://docs.microsoft.com/microsoftteams/platform)을 제공합니다. 

> [!TIP]
> Teams 아키텍처에 대한 자세한 내용은 [Teams 플랫폼 아카데미](https://aka.ms/TeamsPlatformAcademy)에 있는 비디오를 시청하세요.


## <a name="managing-teams"></a>Teams 관리하기

관리자는 Microsoft Teams 관리 센터를 통해 Teams를 관리합니다. 빠르게 살펴보기 위해서는 Teams 관리 센터 비디오(3:03분)를 사용하여 Teams 관리를 시청하세요.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE476Yi]

자세한 정보:

- [Teams 관리자 역할을 사용하여 Teams를 관리](using-admin-roles.md)
- [Teams 관리 센터에서 Teams를 관리](manage-teams-skypeforbusiness-admin-center.md)
- [새로운 Teams 관리 센터로 전환하는 동안 Teams를 관리](manage-teams-in-modern-portal.md)
- [Office 365 혹은 Microsoft 365에서 Teams 기능 관리](enable-features-office-365.md)

조직에서 Teams와 다른 모든 Microsoft 365 혹은 Office 365 제품 및 서비스에 대한 최신 정보를 확인하려면 [메시지 센터](https://admin.microsoft.com/AdminPortal/Home#/MessageCenter) 및 [Teams 로드맵](https://www.microsoft.com/microsoft-365/roadmap?rtc=1&filters=Microsoft%20Teams)을 반드시 확인하세요. 사용자에게 계속해서 정보를 제공하고 준비된 상태로 유지를 시켜주는데 도움이 되는 새로운 기능과 업데이트된 기능, 계획된 변경 사항 그리고 문제에 대한 공지 사항을 확인할 수 있습니다. 

## <a name="upgrade-from-skype-for-business-to-teams"></a>비즈니스용 Skype에서 Teams로 업그레이드
Teams는 Microsoft 365 및 Office 365에서의 지능형 커뮤니케이션을 위한 기본 클라이언트이며 결국 비즈니스용 Skype Online을 대체합니다. Teams에 제공될 새로운 기능에 대한 최신 정보를 확인하려면 [Microsoft 365 로드맵](https://aka.ms/O365Roadmap)을 참조하세요. 지속적인 채팅 및 메시징 기능을 보완하기 위해 Teams는 완전히 통합된 기본으로 제공되는 음성 및 비디오를 통해 포괄적인 모임 및 통화 환경을 제공합니다. Microsoft Teams 블로그에서 [Teams는 이제 완벽한 모임 및 통화 솔루션입니다](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-is-now-a-complete-meeting-and-calling-solution/ba-p/236042)를 확인하세요.

비즈니스용 Skype를 실행 중이고 Teams로 업그레이드할 준비가 되었거나 비즈니스용 Skype 및 Teams를 함께 실행 중이고 Teams로 완전히 이동할 준비가 된 경우에 전환이 제대로 진행되도록 도움을 줄 수 있는 도구, 팁 및 지침이 있습니다. 자세한 내용은 [Teams로 업그레이드](upgrade-start-here.md)를 참조하세요.

## <a name="teamwork"></a>팀워크
모든 팀은 상이합니다. 공동 작업을 수행하는 데 모든 접근 방식을 충족시킬 수 있는 단 한가지의 방식은 없습니다. Microsoft 365 및 Office 365는 모든 팀의 고유한 요구 사항을 충족하도록 설계되었으며 사용자가 목적에 맞도록 만들어진 통합된 응용 프로그램을 통해 통신, 공동 작업 그리고 더 많은 작업을 달성할 수 있도록 해줍니다.

사용할 Microsoft 365 혹은 Office 365 앱과 서비스를 결정할 때는 조직에서 수행하는 작업 및 팀에서 필요한 대화의 유형에 대해서 고려합니다. 

- 팀워크의 허브로서 **Teams**는 조직 외부의 사용자를 포함하여 사용자들이 활발하게 실시간으로 연결하고 공동 작업을 하여 업무를 수행할 수 있는 곳입니다. 문서를 공동 작성하거나, 모임을 진행하고 있거나 혹은 다른 앱 및 서비스에서 함께 작업을 하던지에 상관없이 작업이 진행 중인 곳에서 바로 대화를 나누어보세요. Teams는 비공식적인 채팅을 하고, 프로젝트에서 신속히 반복 적용을 하고, 팀 파일을 사용하여 작업을 하고, 공유 결과물을 가지고 공동 작업을 할 수 있는 곳입니다. 

- 친숙한 전자 메일 환경에서 더욱 공식적이고 구조적인 방식으로 공동 작업을 하거나 대상이 지정되고 및 직접 통신이 필요한 경우에 공동 작업을 하기 위한 **Outlook**.

- 사이트, 포털, 지능형 콘텐츠 서비스, 비즈니스 프로세스 자동화 그리고 엔터프라이즈 검색을 위한 **SharePoint**. SharePoint는 팀들 간에 모든 유형의 콘텐츠를 쉽게 공유하고 액세스할 수 있도록 팀워크의 중앙에 콘텐츠를 유지합니다. Outlook, Yammer 및 Teams와의 긴밀한 통합을 통해 여러 대화 환경에서 원활한 콘텐츠 공동 작업을 수행할 수 있습니다.

- 사용자가 초대하는 사용자들과 파일을 저장하고 공유할 수 있는 **비즈니스용 OneDrive**. 사용자가 비즈니스용 OneDrive에 저장하는 콘텐츠는 사용자가 다른 사용자와 공유할 때까지 비공개이기에 공유할 목적이 아니거나 공유할 준비가 되지 않은 개인 및 초안 문서를 저장하는 데 가장 적합한 옵션입니다.

- 조직 전체에서 사용자를 연결할 수 있는 **Yammer**. 회사 전체의 이니셔티브를 주도하고 모범 사례를 공유하며 관심있는 공통 주제 혹은 업무 분야에 대한 커뮤니티를 구축하세요. 아이디어를 크라우드 소싱하여 회사 전체 사용자들과의 공개 토론을 촉진하세요.

- **Office 앱**은 Word, Excel, PowerPoint 및 OneNote를 비롯하여 사용자가 알고 정기적으로 사용하는 모든 친숙한 도구입니다. 

## <a name="teams-content-updates"></a>Teams 콘텐츠 업데이트

[업데이트된 Teams 주제의 주간 목록](teams-updates.md)을 참조하세요.

## <a name="teams-known-issues"></a>Teams의 알려진 문제점

[Teams 문제 해결](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams). 참조

## <a name="teams-client-release-notes"></a>Teams 클라이언트 릴리스 정보

[Teams에서의 새로운 기능](https://support.office.com/article/what-s-new-in-microsoft-teams-d7092a6d-c896-424c-b362-a472d5f105de)을 참조하세요.

