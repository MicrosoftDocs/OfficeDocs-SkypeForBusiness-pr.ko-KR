---
title: Microsoft 팀에 대 한 게스트 액세스 설정 또는 해제
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
ms.reviewer: sbhatta
search.appverid: MET150
description: Microsoft 팀에서 게스트 액세스 기능을 켜거나 끕니다.
ms.custom:
- NewAdminCenter_Update
f1.keywords: ms.teamsadmincenter.orgwidesettings.guestaccess.turnonguestaccessarticle
appliesto:
- Microsoft Teams
ms.openlocfilehash: 357ada56590bb42655e1a45a6e27ab7dac1c4167
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41693643"
---
<a name="turn-on-or-turn-off-guest-access-to-microsoft-teams"></a>Microsoft 팀에 대 한 게스트 액세스 설정 또는 해제
===================================================

기본적으로 게스트 액세스가 꺼져 있습니다. Office 365 관리자는 관리자 또는 팀 소유자가 게스트를 추가할 수 있으려면 먼저 팀에 대 한 게스트 액세스를 설정 해야 합니다. 게스트 액세스를 설정 하려면 [게스트 액세스 검사 목록을](guest-access-checklist.md)사용 합니다. 

게스트 액세스를 설정한 후 변경 내용이 적용 되려면 2-24 시간이 걸립니다. 사용자가 팀에 게스트를 추가 하려고 할 때 "관리자에 게 문의" 라는 메시지가 표시 되 면 게스트 액세스가 설정 되지 않았거나 설정이 아직 유효 하지 않은 것일 수 있습니다.

> [!IMPORTANT]
> 게스트 액세스는 Azure Active Directory, Office 365, SharePoint Online, 팀의 설정에 따라 달라 집니다. 자세한 내용은 [팀에서 게스트 액세스 권한 부여](Teams-dependencies.md)를 참조 하세요.



## <a name="configure-guest-access-in-the-teams-admin-center"></a>팀 관리 센터에서 게스트 액세스 구성

1.  Microsoft 팀 관리 센터에 로그인 합니다.

2.  **조직 전체 설정** > **게스트 액세스**를 선택 합니다.

3. **Microsoft 팀에서 게스트 액세스 허용** 을 **On**으로 설정 합니다.

    ![게스트 액세스 스위치를 On으로 설정 허용 ](media/set-up-guests-image1.png)

4.  **호출**, **모임**, **메시지**에서 게스트 사용자에 게 허용할 사항에 따라 각 접근 권한 값에 대해 **설정** 또는 **해제** 를 선택 합니다.

    - **개인 전화 걸기** – 게스트가 피어 투 피어 통화를 할 수 있도록 **이 설정을 켭니다** .
    - **IP 비디오 허용** -게스트에서 통화 및 모임에 비디오를 사용할 수 **있도록 설정 합니다** .
    - **화면 공유 모드** –이 설정은 게스트 사용자를 위한 화면 공유의 가용성을 제어 합니다. 
       - 이 설정을 **사용 안 함으로** 설정 하 여 게스트가 팀에서 화면을 공유할 수 있는 기능을 제거 합니다. 
       - 개별 응용 프로그램을 공유할 수 있도록이 설정을 **단일 응용 프로그램** 으로 설정 합니다. 
       - 이 설정을 **전체 화면** 으로 전환 하 여 전체 화면 공유를 허용 합니다.
    - **모임 시작 허용** -게스트가 Microsoft 팀의 모임 시작 **기능을 사용할 수 있도록 설정 합니다** .
    - **보낸 메시지 편집** -게스트가 이전에 보낸 메시지를 편집할 수 **있도록 설정 합니다** .
    - **게스트는 전송 된 메시지를 삭제할 수 있습니다** – **이 설정을 사용 하 여 게스트가** 이전에 보낸 메시지를 삭제 하도록 합니다.
    - **채팅** -이 설정을 사용 하 여 게스트가 팀에서 **채팅을 사용할** 수 있도록 합니다.
    - **대화에서 Giphy 사용** -게스트가 대화에 **giphy을 사용할** 수 있도록이 설정을 켭니다. Giphy는 사용자가 애니메이션 GIF 파일을 검색 하 고 공유 하는 데 사용할 수 있는 온라인 데이터베이스 및 검색 엔진입니다. 각 Giphy에는 콘텐츠 등급이 할당 됩니다.
    - **Giphy 콘텐츠 등급** – 드롭다운 목록에서 평점을 선택 합니다.
       - **모든 콘텐츠 허용** -게스트는 콘텐츠 등급에 관계 없이 모든 giphy을 채팅에 삽입할 수 있습니다.
       - **보통** -게스트는 채팅에 giphy를 삽입할 수 있지만, 성인 콘텐츠는 중간에 국한 되지 않습니다.
       - **Strict** – 게스트는 채팅에 giphy를 삽입할 수 있지만 성인용 메일을 삽입 하는 것이 제한 됩니다.
    - **대화에서 밈 사용** -게스트가 **대화를 사용할** 수 있도록이 설정을 켭니다.
    - **대화에서 스티커 사용** – 대화에서 게스트가 **스티커를 사용할 수 있도록 설정 합니다** . 


5.  **저장**을 클릭 합니다.

## <a name="use-powershell-to-turn-guest-access-on-or-off"></a>PowerShell을 사용 하 여 게스트 액세스 설정 또는 해제
[PowerShell을 참조 하 여 게스트 액세스 설정 또는 해제](guest-access-PowerShell.md#use-powershell-to-turn-guest-access-on-or-off)


## <a name="video-adding-guests-in-teams"></a>비디오: 팀에서 게스트 추가

|  |  |
|---------|---------|
| Microsoft 팀에서 게스트 추가   | <iframe width="350" height="200" src="https://www.youtube.com/embed/1daMBDyBLZc" frameborder="0" allowfullscreen></iframe>   | 


## <a name="external-access-federation-vs-guest-access"></a>외부 액세스 (페더레이션) 및 게스트 액세스

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]