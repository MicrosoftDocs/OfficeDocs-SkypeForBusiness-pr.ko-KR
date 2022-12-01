---
title: Microsoft Teams에서 게스트 액세스 설정 또는 해제
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
- chat-teams-channels-revamp
ms.localizationpriority: medium
f1.keywords:
- CSH
appliesto:
- Microsoft Teams
description: Office 365 관리자로서 Microsoft Teams에서 게스트 액세스 기능을 설정하거나 해제하는 방법을 알아보세요.
ms.openlocfilehash: 906a5554d4dbcb03efabb2300a5a900ad3c8dc21
ms.sourcegitcommit: dc5b3870fd338f7e9ab0a602a44eaf9feb595b2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/30/2022
ms.locfileid: "69199100"
---
# <a name="turn-guest-access-in-microsoft-teams-on-or-off"></a>Microsoft Teams에서 게스트 액세스 설정 또는 해제

이 문서에서는 Teams에서 통화, 모임 및 채팅을 포함하여 게스트 액세스 설정을 구성하는 방법을 설명합니다. Teams의 게스트 액세스에는 Azure AD, Microsoft 365 그룹 및 SharePoint의 설정을 포함하여 Microsoft 365에서 다른 설정을 구성해야 합니다. Teams에 게스트를 초대할 준비가 되었다면 다음 중 하나를 읽어 보세요.

- 일반적인 사용을 위해 Teams에서 게스트 액세스를 구성하려면 [팀에서 게스트와 공동 작업](/microsoft-365/solutions/collaborate-as-team)을 참조하세요.
- Azure Active Directory를 사용하는 파트너 조직과 공동 작업을 수행하고 게스트가 팀 액세스를 위해 자체 등록할 수 있도록 허용하려면 [관리되는 게스트로 B2B 엑스트라넷 생성](/microsoft-365/solutions/b2b-extranet)을 참조하세요.

> [!NOTE]
> 다른 조직의 사용자와 모임을 찾고, 통화하고, 채팅하고, 설정하려는 경우 [외부 액세스](manage-external-access.md)를 사용하세요.

## <a name="configure-guest-access-in-the-teams-admin-center"></a>Teams 관리 센터에서 게스트 액세스 구성

1. [Microsoft Teams 관리 센터](https://admin.teams.microsoft.com/)에 로그인합니다.

2. **사용자** > **게스트 액세스를** 선택합니다.

3. **Teams에서 게스트 액세스 허용을** **켜** 기로 설정합니다.

    ![게스트 액세스 스위치를 켜기로 설정하도록 허용합니다.](media/guest-access-setting.png)

4. **통화**, **모임** 및 **메시징** 에서 게스트에 허용하려는 항목에 따라 각 기능에 대해 **켜****기 또는 끄** 기를 선택합니다.

      - **개인 전화 걸기** – 게스트가 피어 투 피어 전화를 걸 수 있도록 허용하려면 이를 **켬** 으로 설정합니다.
      - **IP 비디오** - 게스트가 통화 및 모임에서 비디오를 사용할 수 있도록 **이 설정을 켭** 니다.
      - **화면 공유 모드** – 이 설정은 게스트에 대한 화면 공유의 가용성을 제어합니다.
          - 게스트가 Teams에서 화면을 공유할 수 있는 기능을 제거하려면 이 설정을 **사용 안 함** 으로 설정합니다.
          - 개별 응용 프로그램을 공유하도록 허용하려면 이 설정을 **단일 응용 프로그램** 으로 설정합니다.
          - 전체 화면 공유를 허용하려면 이 설정을 **전체 화면** 으로 설정합니다.
      - **지금 모임** – 게스트가 Microsoft Teams에서 지금 모임 기능을 사용할 수 있도록 **이 설정을 켜** 세요.
      - **보낸 메시지 편집** - 게스트가 이전에 보낸 메시지를 편집할 수 있도록 허용하려면 이를 **켬** 으로 설정합니다.
      - **보낸 메시지 삭제** – 게스트가 이전에 보낸 메시지를 **삭제할 수** 있도록 이 설정을 켭니다.
      - **채팅 삭제** - 게스트가 전체 채팅 대화를 삭제할 수 있도록 이 설정을 **켜** 세요.
      - **채팅** – 게스트가 Teams에서 채팅을 사용할 수 있도록 허용하려면 이를 **켬** 으로 설정합니다.
      - **대화의 Giphy – 게스트가 대화에서** Giphys **를 사용할** 수 있도록 이 설정을 켭니다. Giphy는 사용자가 애니메이션 GIF 파일을 검색하고 공유할 수 있는 온라인 데이터베이스 및 검색 엔진입니다. 각 Giphy에는 콘텐츠 등급이 할당됩니다.
      - **Giphy 콘텐츠 등급** – 드롭다운 목록에서 등급을 선택합니다.
          - **모든 콘텐츠 허용** - 게스트는 콘텐츠 등급과 상관없이 모든 Giphy를 채팅에 삽입할 수 있습니다.
          - **보통** - 게스트는 채팅에 Giphy를 삽입할 수 있지만 성인용 콘텐츠는 보통으로 제한됩니다.
          - **Strict** – 게스트는 채팅에 Giphys를 삽입할 수 있지만 성인 콘텐츠 삽입은 제한됩니다.
      - **대화의 밈 - 게스트가 대화에서** **밈을 사용할** 수 있도록 이 설정을 켭니다.
      - **대화의 스티커 – 게스트가 대화에서** **스티커를 사용할** 수 있도록 이 설정을 켭니다.
      - **메시지에 대한 몰입형 리더** - 게스트가 [Teams에서 몰입형 리더](https://support.microsoft.com/topic/a700c0d0-bc53-4696-a94d-4fbc86ac7a9a)**를 사용할** 수 있도록 이 설정을 켭니다.

    ![Teams의 게스트 권한 설정입니다.](media/manage-guest-access-image1.png)

5. **저장** 을 선택합니다.

## <a name="turning-guest-access-off"></a>게스트 액세스 끄기

Teams에서 게스트 액세스를 해제하면 기존 게스트가 해당 팀에 액세스할 수 없게 됩니다. 하지만, 팀에서 제외되지 않습니다. 여전히 팀의 사람들에게 표시되며 @멘션될 수 있습니다. Teams 게스트 액세스를 다시 켜면 다시 액세스할 수 있습니다.

게스트 액세스를 해제하려는 경우 팀 소유자에게 해당 팀에서 게스트 계정을 수동으로 제거하도록 조언할 수 있습니다. 이러한 게스트는 액세스 권한이 없지만 팀에 계정이 표시되면 팀의 다른 사람들에게 혼란을 초래할 수 있습니다.


## <a name="see-also"></a>참고 항목

[Microsoft 365를 사용하여 안전한 공동 작업 설정](/microsoft-365/solutions/setup-secure-collaboration-with-teams)

[특정 팀에서 게스트 차단](/microsoft-365/solutions/per-group-guest-access)

[Set-CsTeamsClientConfiguration](/powershell/module/skype/set-csteamsclientconfiguration)
