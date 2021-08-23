---
title: SharePoint 및 OneDrive 상호 작용하는 Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: snigdhav
search.appverid: MET150
description: SharePoint & OneDrive 상호 작용을 Teams. 개인 채팅 파일 & 팀, 표준 채널, 문서 & 상호 작용합니다.
localization_priority: Normal
ms.collection:
- M365-collaboration
- SPO_Content
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: b47ca7c1c0a9a5154f681a8e09d175ba17ad8013
ms.sourcegitcommit: 85017cf88789c750836780dad2ef707c1c6c39b4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/16/2021
ms.locfileid: "58359195"
---
# <a name="how-sharepoint-and-onedrive-interact-with-microsoft-teams"></a>SharePoint 및 OneDrive 상호 작용하는 Microsoft Teams

> [!Tip]
> 다음 세션을 통해 Teams(AAD), Azure Active Directory, Microsoft 365, Exchange SharePoint 및 [OneDrive:](https://aka.ms/teams-foundations) Microsoft Teams

각 Microsoft Teams 팀 사이트가 SharePoint 팀 사이트가 있으며, 팀의 각 표준 채널은 기본 팀 사이트 문서 라이브러리 내의 폴더를 얻습니다. 각 [개인 채널은](private-channels.md) 자체적으로 별도의 SharePoint 있습니다. 이러한 팀 사이트 및 채널 사이트에 대한 자세한 내용은 연결된 사이트 및 채널 Teams 관리를 [참조하세요.](/sharepoint/teams-connected-sites)

대화 내에서 공유된 파일은 문서 라이브러리에 자동으로 추가되고, SharePoint에 설정된 사용 권한 및 파일 보안 옵션은 Teams에서 자동으로 반영됩니다. 사이트 주소 변경의 영향을 확인 SharePoint 사이트 주소 변경 [을 참조하세요.](/sharepoint/change-site-address)

개인 채팅 파일은 보낸 사람 OneDrive 폴더에 저장되며 파일 공유 프로세스의 일부로 모든 참가자에게 권한이 자동으로 부여됩니다.

사용자가 라이선스에 할당되지 SharePoint 경우 사용자에게 OneDrive 저장소가 Microsoft 365. 파일 공유는 표준 채널에서 작동하지만 사용자는 채팅에서 파일을 공유할 수 OneDrive 저장하지 Microsoft 365.

파일을 문서 라이브러리에 SharePoint 및 OneDrive 조직 수준에서 구성된 모든 규정 준수 규칙이 따릅니다. 

> [!NOTE]
> SharePoint 서버와의 통합은 지원되지 Teams.

다음은 팀, 표준 채널 및 문서 라이브러리 간의 관계 예제입니다.

모든 팀에 대해 SharePoint 사이트가 만들어지며 공유 **문서** 폴더는 팀에 대해 만든 기본 폴더입니다. 일반 채널(각  팀의 기본 채널)을 포함한 각 표준 채널에는 공유 문서의 **폴더가 있습니다.**

![공유 문서 폴더의 다이어그램에서 SharePoint.](media/Understand_how_SharePoint_Online_and_OneDrive_for_Business_interact_with_Microsoft_Teams_image1.png)

기본 사이트 SharePoint 및 문서 라이브러리를 다른 사이트로 바꿀 수 없습니다.

모든 사용자에 대해 채팅 OneDrive  Microsoft Teams 폴더는 다른 사용자와 개인 채팅 내에서 공유된 모든 파일을 저장하는 데 사용됩니다(1:1 또는 1:다), 의도된 사용자에 대한 액세스를 제한하기 위해 자동으로 구성된 권한.

![채팅 파일이라는 OneDrive 폴더의 Microsoft Teams 다이어그램](media/Understand_how_SharePoint_Online_and_OneDrive_for_Business_interact_with_Microsoft_Teams_image2.png)

공용 팀의 경우 SharePoint 팀 사이트는 "외부 사용자를 제외한 모든 사용자" 액세스로 프로비전됩니다. 공개 팀은 해당 팀의 구성원이 아닌 Teams 공개 팀에 표시되지 않습니다. 그러나 팀 사이트의 URL을 사용하여 SharePoint 팀 사이트의 콘텐츠에 액세스할 SharePoint 있습니다. 

## <a name="channel-files-tab"></a>채널 파일 탭

**문서의** 파일 탭은 Teams 문서 보기와 SharePoint 밀접하게 입니다. 파일 **탭에서** 사용자는 다음을 할 수 있습니다.

- 새 파일 메뉴에서 추가 **옵션을** 참조하세요.
- 파일을 로컬 드라이브에 동기화합니다.
- 모든 **문서 메뉴에서** 목록  보기에서 **압축 목록으로** **타일 보기로 전환합니다.**
- 주의가 필요하거나 맬웨어가 있는 파일을 식별합니다.
- 파일이 읽기 전용인지 또는 체크 아웃인지 즉시 확인할 수 있습니다.
- 파일을 체크 아웃하고 체크 인합니다.
- 파일 정렬 순서를 고정, 고정 및 변경합니다.
- 메타데이터가 필요한 파일 식별
- 더 많은 필터 옵션에서 선택합니다.
- 열 제목을 기준으로 파일을 그룹화합니다.
- 열 설정(왼쪽 또는 오른쪽 이동, 숨기기) 및 열 너비를 수정합니다.

## <a name="default-link-type-setting"></a>기본 링크 유형 설정

사용자가 파일을 공유하는 경우 기본적으로 표시된 공유 링크의 유형은 SharePoint 관리 센터에 설정됩니다. 사용자가 [정보를 공유하기 위한](/sharepoint/change-default-sharing-link) 링크를 얻을 때 기본 링크 형식 변경을 참조하세요.

## <a name="related-topics"></a>관련 항목

[연결된 Teams 채널 사이트 관리](/SharePoint/teams-connected-sites)

[SharePoint 및 Teams: 더 나은 을 함께 사용할 수 있습니다.](https://techcommunity.microsoft.com/t5/Microsoft-SharePoint-Blog/SharePoint-and-Teams-Better-Together/ba-p/189593)

[게스트 환경의 모양](guest-experience.md)
