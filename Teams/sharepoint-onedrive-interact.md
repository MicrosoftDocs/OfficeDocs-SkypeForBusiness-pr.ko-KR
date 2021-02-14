---
title: SharePoint Online 및 비즈니스용 OneDrive가 Microsoft Teams와 상호 작용하는 방법
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: snigdhav
search.appverid: MET150
description: SharePoint Online & 비즈니스용 OneDrive와 Teams 상호 작용 개인 채팅 파일 & 팀, 표준 채널, 문서 라이브러리 & 상호 작용합니다.
localization_priority: Normal
ms.collection:
- M365-collaboration
- SPO_Content
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: ff18a0645f81d1892e246ee7432d58a1c728f3ad
ms.sourcegitcommit: 7575fb476a594d70084c603e508dd311ef1d7edb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/05/2021
ms.locfileid: "49757783"
---
# <a name="how-sharepoint-online-and-onedrive-for-business-interact-with-microsoft-teams"></a>SharePoint Online 및 비즈니스용 OneDrive가 Microsoft Teams와 상호 작용하는 방법

> [!Tip]
> Teams에서 AAD(Azure Active Directory), Microsoft 365 그룹, Exchange, SharePoint 및 비즈니스용 OneDrive와 상호 작용하는 방법을 알아보려면 [Microsoft Teams의 기초](https://aka.ms/teams-foundations) 세션을 시청하세요.

Microsoft Teams의 각 팀에는 SharePoint Online의 팀 사이트가 있으며, 팀의 각 표준 채널은 기본 팀 사이트 문서 라이브러리 내의 폴더를 얻습니다. 대화 내에서 공유된 파일은 문서 라이브러리에 자동으로 추가되고, SharePoint에 설정된 사용 권한 및 파일 보안 옵션은 Teams에서 자동으로 반영됩니다. SharePoint에서 사이트 주소를 변경하는 경우의 영향은 사이트 주소 [변경을 참조하세요.](https://docs.microsoft.com/sharepoint/change-site-address)

> [!NOTE]
> 이 문서는 표준 채널에만 적용됩니다. 개인 채널의 아키텍처는 표준 채널과 다릅니다. 각 비공개 채널에는 상위 팀 사이트와 별개인 자체 SharePoint 사이트 모음이 있습니다. 자세한 내용은 [Microsoft Teams의 비공개 채널을 참조하세요.](private-channels.md)

비공개 채팅 파일은 보낸 사람 비즈니스용 OneDrive 폴더에 저장되며 파일 공유 프로세스의 일부로 모든 참가자에게 사용 권한이 자동으로 부여됩니다.

사용자에게 SharePoint Online 라이선스가 할당되지 않고 사용하도록 설정되어 있지 않은 경우, 사용자는 Microsoft 365 또는 Office 365에 비즈니스용 OneDrive 저장소가 없습니다. 파일 공유는 표준 채널에서 계속 작동하지만 사용자는 Microsoft 365 또는 Office 365의 비즈니스용 OneDrive 저장소 없이는 채팅에서 파일을 공유할 수 없습니다.

SharePoint Online 문서 라이브러리와 비즈니스용 OneDrive에 파일을 저장하면 테넌트 수준에서 구성된 모든 규정 준수 규칙을 따릅니다. 

> [!NOTE]
> 현재 SharePoint On-프레미스와의 통합은 Microsoft Teams에서 지원되지 않습니다.

다음은 팀, 표준 채널 및 문서 라이브러리 간의 관계 예제입니다.

모든 팀에 대해 SharePoint 사이트가  만들어지며 공유 문서 폴더는 팀에 대해 만들어진 기본 폴더입니다. 일반 채널(각  팀의 기본 채널)을 포함한 각 표준 채널에는 공유 문서의 **폴더가 있습니다.**

![SharePoint Online의 공유 문서 폴더 다이어그램](media/Understand_how_SharePoint_Online_and_OneDrive_for_Business_interact_with_Microsoft_Teams_image1.png)

> [!NOTE]
> 현재는 기본 SharePoint 사이트 및 문서 라이브러리를 다른 사이트로 바꿀 수 없습니다. 사용자로부터 원하고 있으며 이를 고려하고 있습니다. Teams [로드맵 또는](https://aka.ms/teamsroadmap) [Teams UserVoice를](https://aka.ms/TeamsUserVoice) 확인하여 예정된 기능을 확인할 수 있습니다.

> [!TIP]
> 기존 SharePoint 사이트 페이지 또는 기존 SharePoint 문서 라이브러리에 연결되는 탭을 팀에 추가합니다.
> 1. 탭 옆에 있는 더하기 기호를 선택합니다.
> 2. 기존 **SharePoint** 사이트 페이지의 SharePoint 또는 기존 문서 라이브러리의 **문서** 라이브러리를 선택합니다.
> 3. 적절한 페이지 또는 문서 라이브러리를 선택합니다.

모든 사용자에 대해 OneDrive 폴더 **Microsoft Teams 채팅** 파일은 다른 사용자(1:1 또는 1:다)와 비공개 채팅 내에서 공유되는 모든 파일을 저장하는 데 사용되며, 의도한 사용자만 액세스를 제한하도록 자동으로 구성됩니다.

![Microsoft Teams 채팅 파일이라는 OneDrive 폴더의 다이어그램](media/Understand_how_SharePoint_Online_and_OneDrive_for_Business_interact_with_Microsoft_Teams_image2.png)

공용 팀의 경우 SharePoint 팀 사이트는 "외부 사용자를 제외한 모든 사용자" 액세스로 프로비전됩니다. 공개 팀은 해당 팀의 구성원이 아닌 사람에 대해 Teams에 표시되지 않습니다. 그러나 SharePoint 팀 사이트의 URL을 사용하여 SharePoint 팀 사이트의 콘텐츠에 액세스할 수 있습니다. 

## <a name="channel-files-tab"></a>채널 파일 탭

> [!INCLUDE [new feature coming soon](includes/new-feature-coming-soon-section.md)]

Teams의 **파일** 탭은 SharePoint 문서 보기와 밀접하게 관련이 있습니다. 파일 **탭에서** 사용자는 다음을 할 수 있습니다.

- 새 파일 메뉴에서 추가 **옵션을** 참조하세요.
- 파일을 로컬 드라이브에 동기화합니다.
- 모든 문서 **메뉴에서** 목록 **보기에서** 압축 **목록으로** 타일 **보기로 전환합니다.**
- 주의가 필요하거나 맬웨어가 있는 파일을 식별합니다.
- 파일이 읽기 전용인지 또는 체크 아웃인지 즉시 확인할 수 있습니다.
- 파일을 체크 아웃하고 체크 인합니다.
- 파일 정렬 순서를 고정, 고정 및 변경합니다.
- 메타데이터가 필요한 파일 식별
- 더 많은 필터 옵션에서 선택합니다.
- 열 제목을 기준으로 파일을 그룹화합니다.
- 열 설정(왼쪽 또는 오른쪽으로 이동, 숨기기) 및 열 너비를 수정합니다.

## <a name="default-link-type-setting"></a>기본 연결 형식 설정

SharePoint 및 OneDrive에는 파일에 대해 만들어진 링크의 기본 링크 유형을 지정하기 위한 관리자 설정이 있습니다. Teams는 관리자가 SharePoint 및 OneDrive에 대해 설정한 설정을 다시 사용하여 동일한 접근 방식을 채택하고 있습니다. 이 접근 방식에 대한 자세한 내용은 사용자가 공유 링크를 받을 때 기본 링크 유형 [변경에 설명되어 있습니다.](https://docs.microsoft.com/sharepoint/change-default-sharing-link) 

## <a name="more-information"></a>추가 정보

SharePoint가 Teams에서 작동하는 방식에 대한 자세한 내용은 SharePoint 및 Teams: 더 잘 어우러진 [팀을 참조하세요.](https://techcommunity.microsoft.com/t5/Microsoft-SharePoint-Blog/SharePoint-and-Teams-Better-Together/ba-p/189593)

Teams의 게스트 경험에 대한 자세한 내용은 게스트 환경의 내용을 [읽어보아야 합니다.](guest-experience.md)

