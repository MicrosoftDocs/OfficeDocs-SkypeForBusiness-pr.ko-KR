---
title: Microsoft Teams에 대한 게스트 액세스 켜기 또는 끄기
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
ms.reviewer: sbhatta
search.appverid: MET150
description: Office 365 관리자로 Microsoft 팀에서 게스트 액세스 기능을 설정 하거나 해제 하는 방법에 대해 알아봅니다.
ms.custom: ms.teamsadmincenter.orgwidesettings.guestaccess.turnonguestaccessarticle
f1.keywords:
- CSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: 43c225cad121d88d14bb6f179f48b452a61d89d7
ms.sourcegitcommit: 762e303509940f830c304e00a98b05796bf5537f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/01/2020
ms.locfileid: "48333248"
---
# <a name="turn-on-or-turn-off-guest-access-to-microsoft-teams"></a>Microsoft Teams에 대한 게스트 액세스 켜기 또는 끄기

기본적으로 게스트 액세스 기능은 꺼져있습니다. Microsoft 365 또는 Office 365 관리자는 관리자 또는 팀 소유자가 게스트를 추가할 수 있으려면 먼저 팀에 대 한 게스트 액세스를 설정 해야 합니다.

게스트 액세스를 설정한 후 변경 내용이 적용 되는 데 몇 시간이 걸릴 수 있습니다. 사용자가 팀에 게스트를 추가하려고 할 때 "관리자에게 문의하세요."라는 메시지가 표시되면 게스트 액세스가 켜지지 않았거나 설정이 아직 적용되지 않았을 가능성이 큽니다.

> [!IMPORTANT]
> 게스트 액세스를 설정 하는 것은 Azure Active Directory, Microsoft 365, SharePoint, 팀의 설정에 따라 달라 집니다. 자세한 내용은 [팀에서 게스트 공동 작업](https://docs.microsoft.com/microsoft-365/solutions/collaborate-as-team)을 참조 하세요.

## <a name="configure-guest-access-in-the-teams-admin-center"></a>Teams 관리 센터에서 게스트 액세스 구성하기

1. Microsoft Teams 관리 센터에 로그인합니다.

2. **조직 전체 설정** > **게스트 액세스**를 선택합니다.

3. **Microsoft Teams에서 게스트 액세스 허용**을 **켬**으로 설정합니다.

    ![게스트 액세스 허용 스위치를 켜기로 설정하기 ](media/set-up-guests-image1.png)

4. **통화**, **모임**, **메시징**에서 게스트 사용자에게 허용할 항목에 따라 각 기능에 대한 **켬** 또는 **끔**를 선택합니다.

      - **개인 전화 걸기** – 게스트가 피어 투 피어 전화를 걸 수 있도록 허용하려면 이를 **켬**으로 설정합니다.
      - **IP 비디오 허용** - 게스트가 통화 및 모임에서 비디오를 사용하도록 허용하려면 이를 **켬**으로 설정합니다.
      - **화면 공유 모드** – 이 설정은 게스트 사용자에 대한 화면 공유 가용성을 제어합니다. 
          - 게스트가 Teams에서 화면을 공유할 수 있는 기능을 제거하려면 이 설정을 **사용 안 함**으로 설정합니다. 
          - 개별 응용 프로그램을 공유하도록 허용하려면 이 설정을 **단일 응용 프로그램**으로 설정합니다. 
          - 전체 화면 공유를 허용하려면 이 설정을 **전체 화면**으로 설정합니다.
      - **모임 시작 허용** – 게스트가 Microsoft Teams에서 모임 시작 기능을 사용하도록 허용하려면 이를 **켬**으로 설정합니다.
      - **보낸 메시지 편집** - 게스트가 이전에 보낸 메시지를 편집할 수 있도록 허용하려면 이를 **켬**으로 설정합니다.
      - **게스트가 보낸 메시지를 삭제할 수 있음** – 게스트가 이전에 보낸 메시지를 삭제할 수 있도록 허용하려면 이를 **켬**으로 설정합니다.
      - **채팅** – 게스트가 Teams에서 채팅을 사용할 수 있도록 허용하려면 이를 **켬**으로 설정합니다.
      - **대화에서 Giphys 사용** - 게스트가 대화에서 Giphys를 사용할 수 있도록 허용하려면 이를 **켬**으로 설정합니다. Giphy는 사용자가 애니메이션 GIF 파일을 검색하고 공유할 수 있는 온라인 데이터베이스 및 검색 엔진입니다. 각 Giphy에는 콘텐츠 등급이 할당됩니다.
      - **Giphy 콘텐츠 등급** – 드롭다운 목록에서 등급을 선택합니다.
          - **모든 콘텐츠 허용** - 게스트는 콘텐츠 등급과 상관없이 모든 Giphy를 채팅에 삽입할 수 있습니다.
          - **보통** - 게스트는 채팅에 Giphy를 삽입할 수 있지만 성인용 콘텐츠는 보통으로 제한됩니다.
          - **엄격** - 게스트는 채팅에 Giphy를 삽입할 수 있지만 성인용 콘텐츠 삽입은 제한됩니다.
      - **대화에서 밈 사용** - 게스트가 대화에서 밈을 사용할 수 있도록 허용하려면 이를 **켬**으로 설정합니다.
      - **대화에서 스티커 사용** – 게스트가 대화에서 스티커를 사용할 수 있도록 허용하려면 이를 **켬**으로 설정합니다. 

5. **저장**을 클릭합니다.

## <a name="external-access-federation-vs-guest-access"></a>외부 액세스 (페더레이션) 및 게스트 액세스

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]

## <a name="see-also"></a>참고 항목

[특정 팀의 게스트 사용자 차단](https://docs.microsoft.com/microsoft-365/solutions/per-group-guest-access)

[Set-CsTeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration)