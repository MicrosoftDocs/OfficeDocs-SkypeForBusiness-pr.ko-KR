---
title: SharePoint Online 및 비즈니스용 OneDrive가 Microsoft 팀과 상호 작용 하는 방법
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 05/08/2019
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: snigdhav
search.appverid: MET150
description: SharePoint Online과 비즈니스용 OneDrive가 Microsoft 팀과 상호 작용 하는 방법, 즉 개인 채팅 파일 저장 방법, 팀, 채널, 문서 라이브러리 간의 관계에 대해 알아봅니다.
localization_priority: Normal
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: af1d12eda58dc481ba28bf96ff4ecbfeab8ed5f0
ms.sourcegitcommit: 100ba1409bf0af58e4430877c1d29622d793d23f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/01/2019
ms.locfileid: "37572551"
---
# <a name="how-sharepoint-online-and-onedrive-for-business-interact-with-microsoft-teams"></a>SharePoint Online 및 비즈니스용 OneDrive가 Microsoft 팀과 상호 작용 하는 방법

> [!Tip]
> 다음 세션에서 팀이 Azure Active Directory (AAD), Office 365 그룹, Exchange, SharePoint 및 비즈니스용 OneDrive와 상호 작용 하는 방법에 대해 알아보세요. [Microsoft 팀의 기초](https://aka.ms/teams-foundations)

Microsoft 팀의 각 팀은 SharePoint Online에 팀 사이트가 있으며, 팀의 각 채널은 기본 팀 사이트 문서 라이브러리 내에서 폴더를 가져옵니다. 대화 내에서 공유 된 파일은 문서 라이브러리에 자동으로 추가 되며 SharePoint에 설정 된 사용 권한 및 파일 보안 옵션은 팀 내에 자동으로 반영 됩니다.

개인 채팅 파일은 발신자의 비즈니스용 OneDrive 폴더에 저장 되며, 모든 참가자에 게 파일 공유 프로세스의 일부로 사용 권한이 자동으로 부여 됩니다.

사용자가 SharePoint Online 라이선스를 할당 하 고 사용 하도록 설정 하지 않은 경우 Office 365의 비즈니스용 OneDrive 저장소가 없습니다. 파일 공유는 채널에서 계속 작동 하지만, 사용자는 Office 365의 비즈니스용 OneDrive 저장소 없이도 채팅에서 파일을 공유할 수 있습니다.

SharePoint Online 문서 라이브러리 및 비즈니스용 OneDrive에 파일을 저장 하면 테 넌 트 수준에서 구성 된 모든 준수 규칙이 따릅니다. 

> [!NOTE]
> 현재 Microsoft 팀에서는 SharePoint 온-프레미스와 통합이 지원 되지 않습니다.

다음은 팀, 채널, 문서 라이브러리 간의 관계 예입니다.

모든 팀에 대해 SharePoint 사이트가 만들어지고 **공유 문서** 폴더가 팀에 대해 만든 기본 폴더입니다. **일반** 채널 (각 팀의 기본 채널)을 포함 하 여 각 채널에는 **공유 문서의**폴더가 있습니다.

![SharePoint Online의 공유 문서 폴더 다이어그램](media/Understand_how_SharePoint_Online_and_OneDrive_for_Business_interact_with_Microsoft_Teams_image1.png)

> [!NOTE]
> 현재 기본 SharePoint 사이트 및 문서 라이브러리를 다른 항목으로 바꿀 수 없습니다. 당신이 원하는 대로이를 생각 합니다. [팀 로드맵](https://aka.ms/teamsroadmap) 또는 [팀 UserVoice](https://aka.ms/TeamsUserVoice) 를 확인 하 여 예정 된 기능을 유지 합니다.

> [!TIP]
> 기존 SharePoint 사이트 페이지나 기존 SharePoint 문서 라이브러리에 연결 되는 탭을 팀에 추가 하려면 다음을 실행 합니다.
> 1. 탭 옆에 있는 더하기 기호를 선택 합니다.
> 2. 기존 SharePoint 사이트 페이지 또는 기존 문서 라이브러리의 **문서 라이브러리** 에 대해 **SharePoint** 를 선택 합니다.
> 3. 적절 한 페이지 또는 문서 라이브러리를 선택 합니다.

모든 사용자에 대해 OneDrive 폴더 **Microsoft 팀 채팅 파일** 은 다른 사용자 (1:1 또는 1: 다)와 개인 채팅 내에 공유 된 모든 파일을 저장 하는 데 사용 되며, 사용 권한은 의도 된 사용자 에게만 액세스를 제한 하도록 자동으로 구성 됩니다.

![Microsoft 팀 채팅 파일 이라는 OneDrive 폴더의 다이어그램](media/Understand_how_SharePoint_Online_and_OneDrive_for_Business_interact_with_Microsoft_Teams_image2.png)

## <a name="channel-files-tab"></a>채널 파일 탭

> [!INCLUDE [new feature coming soon](includes/new-feature-coming-soon-section.md)]

팀의 **파일** 탭은 SharePoint 문서 보기와 유사 합니다. 사용자는 **파일** 탭에서 다음을 수행할 수 있습니다.

- **새** 파일 메뉴의 추가 옵션을 참조 하세요.
- 파일을 로컬 드라이브에 동기화 합니다.
- **모든 문서** 메뉴에서 **목록** 보기를 바둑판식으로 압축 하 여 **목록을** **타일** 보기로 전환 합니다.
- 주의가 필요 하거나 맬웨어가 있는 파일을 식별 합니다.
- 파일의 읽기 전용 또는 체크 아웃 여부를 즉시 확인할 수 있습니다.
- 파일을 체크 아웃 하 고 체크 인 합니다.
- 파일의 정렬 순서를 고정, 제거 및 변경 합니다.
- 메타 데이터가 필요한 파일 식별
- 여러 필터 옵션 중에서 선택 합니다.
- 열 머리글을 기준으로 파일을 그룹화 합니다.
- 열 설정 수정 (왼쪽 또는 오른쪽, 숨기기) 및 열 너비를 조정 합니다.

## <a name="default-link-type-setting"></a>기본 링크 종류 설정

SharePoint 및 OneDrive에는 파일에 대해 만들어지는 링크에 대 한 기본 링크 종류를 지정 하는 관리자 설정이 있습니다. 팀은 관리자가 SharePoint 및 OneDrive에 대해 설정한 설정을 다시 사용 하 여 동일한 접근 방식을 채택 하 고 있습니다. 이 접근 방법에 대 한 자세한 내용은 [사용자가 공유할 링크를 가져올 때 기본 링크 유형 변경](https://docs.microsoft.com/sharepoint/change-default-sharing-link)에 설명 되어 있습니다. 

## <a name="more-information"></a>추가 정보

SharePoint에서 팀과 공동 작업 하는 방법에 대 한 자세한 내용은 [sharepoint 및 팀](https://techcommunity.microsoft.com/t5/Microsoft-SharePoint-Blog/SharePoint-and-Teams-Better-Together/ba-p/189593)을 참조 하세요.

팀의 게스트 환경에 대 한 자세한 내용은 [게스트 환경을](guest-experience.md)읽어 보세요.

