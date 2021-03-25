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
- m365initiative-externalcollab
ms.reviewer: rafarhi
search.appverid: MET150
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
- ms.teamsadmincenter.orgwidesettings.guestaccess.turnonguestaccessarticle
localization_priority: Normal
f1.keywords:
- CSH
appliesto:
- Microsoft Teams
description: Office 365 관리자로서 Microsoft Teams에서 게스트 액세스 기능을 설정하거나 해제하는 방법을 알아보세요.
ms.openlocfilehash: 34759e601f5c0cd232bcd6227ff5c7d1fef1d3fe
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51107404"
---
# <a name="turn-on-or-turn-off-guest-access-to-microsoft-teams"></a>Microsoft Teams에 대한 게스트 액세스 켜기 또는 끄기

> [!Note]

> **2021년 2월까지** 게스트 액세스는 기본적으로 해제됩니다. Teams에 대한 게스트 액세스를 켜야만 관리자 또는 팀 소유자가 게스트를 추가할 수 있습니다. 게스트 액세스를 설정한 후 변경 내용이 적용될 수 있는 데 몇 시간이 걸릴 수 있습니다. 사용자가 게스트를  팀에 추가하려고 할 때 관리자에게 문의하는 메시지가 표시될 경우 게스트 액세스가 설정되지 않았거나 설정이 아직 유효하지 않을 수 있습니다.

> **2021년 2월** 이후에는 이 설정을 구성하지 않은 기존 & 신규 고객에 대해 기본적으로 Microsoft Teams의 게스트 액세스가 설정됩니다. 이 변경이 구현되면 Microsoft Teams에서 게스트 액세스 기능을 아직 구성하지 않은 경우 해당 기능이 테넌트에서 사용하도록 설정됩니다. 게스트 액세스가 조직에 대해 비활성화된 상태로 유지하려면 게스트 액세스 설정이 서비스  기본값 대신 Off로 설정되어 있는지 **확인해야 합니다.**

> [!IMPORTANT]
> 게스트 액세스를 설정하는 것은 Azure Active Directory, Microsoft 365, SharePoint 및 Teams의 설정에 따라 달라집니다. 자세한 내용은 [팀에서 게스트와 공동 작업](/microsoft-365/solutions/collaborate-as-team)을 참조하세요.

## <a name="configure-guest-access-in-the-teams-admin-center"></a>Teams 관리 센터에서 게스트 액세스 구성

1. [Microsoft Teams 관리 센터](https://admin.teams.microsoft.com/)에 로그인합니다.

2. **조직 전체 설정** > **게스트 액세스** 를 선택합니다.

3. **Microsoft Teams에서 게스트 액세스 허용** 을 **켬** 으로 설정합니다.

    ![게스트 액세스 허용 스위치를 켜기로 설정하기 ](media/guest-access-setting.png)

4. **통화**, **모임**, **메시징** 에서 게스트 사용자에게 허용할 항목에 따라 각 기능에 대한 **켬** 또는 **끔** 를 선택합니다.

      - **개인 전화 걸기** – 게스트가 피어 투 피어 전화를 걸 수 있도록 허용하려면 이를 **켬** 으로 설정합니다.
      - **IP 비디오 허용** - 게스트가 통화 및 모임에서 비디오를 사용하도록 허용하려면 이를 **켬** 으로 설정합니다.
      - **화면 공유 모드** – 이 설정은 게스트 사용자에 대한 화면 공유 가용성을 제어합니다.
          - 게스트가 Teams에서 화면을 공유할 수 있는 기능을 제거하려면 이 설정을 **사용 안 함** 으로 설정합니다.
          - 개별 응용 프로그램을 공유하도록 허용하려면 이 설정을 **단일 응용 프로그램** 으로 설정합니다.
          - 전체 화면 공유를 허용하려면 이 설정을 **전체 화면** 으로 설정합니다.
      - **모임 시작 허용** – 게스트가 Microsoft Teams에서 모임 시작 기능을 사용하도록 허용하려면 이를 **켬** 으로 설정합니다.
      - **보낸 메시지 편집** - 게스트가 이전에 보낸 메시지를 편집할 수 있도록 허용하려면 이를 **켬** 으로 설정합니다.
      - **게스트가 보낸 메시지를 삭제할 수 있음** – 게스트가 이전에 보낸 메시지를 삭제할 수 있도록 허용하려면 이를 **켬** 으로 설정합니다.
      - **채팅** – 게스트가 Teams에서 채팅을 사용할 수 있도록 허용하려면 이를 **켬** 으로 설정합니다.
      - **대화에서 Giphys 사용** - 게스트가 대화에서 Giphys를 사용할 수 있도록 허용하려면 이를 **켬** 으로 설정합니다. Giphy는 사용자가 애니메이션 GIF 파일을 검색하고 공유할 수 있는 온라인 데이터베이스 및 검색 엔진입니다. 각 Giphy에는 콘텐츠 등급이 할당됩니다.
      - **Giphy 콘텐츠 등급** – 드롭다운 목록에서 등급을 선택합니다.
          - **모든 콘텐츠 허용** - 게스트는 콘텐츠 등급과 상관없이 모든 Giphy를 채팅에 삽입할 수 있습니다.
          - **보통** - 게스트는 채팅에 Giphy를 삽입할 수 있지만 성인용 콘텐츠는 보통으로 제한됩니다.
          - **엄격** – 게스트는 채팅에 Giphys를 삽입할 수 있지만 성인 콘텐츠 삽입은 제한됩니다.
      - **대화에서 밈 사용** - 게스트가 대화에서 밈을 사용할 수 있도록 허용하려면 이를 **켬** 으로 설정합니다.
      - **대화에서 스티커 사용** – 게스트가 대화에서 스티커를 사용할 수 있도록 허용하려면 이를 **켬** 으로 설정합니다.

    ![Teams의 게스트 사용 권한 설정](media/manage-guest-access-image1.png)

5. 저장을 **선택합니다.**

## <a name="external-access-federation-vs-guest-access"></a>외부 액세스(페더레이션) 대 게스트 액세스

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]

## <a name="see-also"></a>참고 항목

[Microsoft 365를 사용하여 안전한 공동 작업 설정](/microsoft-365/solutions/setup-secure-collaboration-with-teams)

[특정 팀에서 게스트 사용자 차단](/microsoft-365/solutions/per-group-guest-access)

[Set-CsTeamsClientConfiguration](/powershell/module/skype/set-csteamsclientconfiguration)