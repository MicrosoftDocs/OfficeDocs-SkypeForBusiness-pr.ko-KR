---
title: Microsoft Teams에서 데스크톱 공유 구성하기
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.reviewer: jastark
ms.date: 03/22/2019
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
f1.keywords:
- NOCSH
description: 사용자가 팀 대화방 또는 모임에서 데스크톱을 공유할 수 있도록 모임 정책을 구성 하는 방법에 대해 알아봅니다.
ms.collection:
- M365-collaboration
ms.custom: seo-marvel-mar2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 857c9c4d830cb3264a83a41b555d26ee004751de
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/06/2020
ms.locfileid: "46581749"
---
<a name="configure-desktop-sharing-in-microsoft-teams"></a>Microsoft Teams에서 데스크톱 공유 구성하기
============================================

데스크톱 공유를 통해 사용자는 모임이나 채팅 도중에 화면이나 앱을 표시할 수 있습니다. 관리자는 사용자가 전체 화면, 앱 또는 파일을 공유할 수 있도록 Microsoft Teams에서 화면 공유를 구성할 수 있습니다. 사용자가 제어권을 주거나 요청하고, PowerPoint 공유를 허용하고, 화이트보드를 추가하고, 공유 노트를 허용하도록 할 수 있습니다. 익명 사용자나 외부 사용자가 공유 화면의 제어권을 요청할 수 있는지 여부도 구성할 수 있습니다.

화면 공유를 구성하려면 새 모임 정책을 만든 다음 관리하려는 사용자에게 할당합니다.

**[Microsoft Teams 관리 센터](https://admin.teams.microsoft.com/)에서**

1. **모임** > **모임 정책**을 선택합니다.

    ![선택한 모임 정책을 보여 주는 스크린샷](media/configure-desktop-sharing-image1.png)

2. **모임 정책** 페이지에서 **새 정책**을 선택합니다.

    ![모임 정책 메시지를 보여 주는 스크린샷](media/configure-desktop-sharing-image2.png)

3. 정책에 고유한 제목을 지정하고 간략한 설명을 입력합니다.

4. **콘텐츠 공유** 아래의 드롭다운 목록에서 **화면 공유 모드**를 선택합니다.

   - **전체 화면** – 사용자가 전체 데스크톱을 공유할 수 있습니다.
   - **단일 응용 프로그램** – 사용자가 단일 활성 응용 프로그램으로 화면 공유를 제한하도록 합니다.
   - **사용 안 함** – 화면 공유를 끕니다.

    ![공유 모드 옵션을 보여 주는 스크린샷](media/configure-desktop-sharing-image3.png)

5. 다음 설정을 켜거나 끕니다.

    - **참가자가 제어권을 부여 하거나 요청할 수 있도록 허용** -팀 멤버가 발표자의 데스크톱 또는 응용 프로그램에 대 한 제어권을 부여 하거나 요청할 수 있습니다.
    - **외부 참가자가 제어권을 부여 하거나 요청할 수 있도록 허용** -이것은 사용자 단위 정책입니다. 조직에서이 사용자에 대해이 집합을 보유 하 고 있는지 여부는 모임 이끌이가 설정한 내용에 관계 없이 외부 참가자가 수행할 수 있는 작업을 제어 하지 않습니다. 이 매개 변수는 해당 조직의 모임 정책 내에서 설정한 공유자에 따라 외부 참가자가 제어권을 부여 하거나 공유자 화면 제어권을 요청할 수 있는지 여부를 제어 합니다.
    - **PowerPoint 공유 허용** – 사용자가 PowerPoint 프레젠테이션을 업로드하고 공유하도록 허용하는 모임을 만들 수 있습니다.
    - **화이트보드 허용** – 사용자가 화이트보드를 공유할 수 있습니다.
    - **공유 노트 허용** – 사용자가 공유 노트를 작성할 수 있습니다.

6. **저장**을 클릭합니다.

## <a name="use-powershell-to-configure-shared-desktop"></a>PowerShell을 사용하여 공유 데스크톱 구성하기

[Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps) cmdlet을 사용하여 데스크톱 공유를 제어할 수도 있습니다. 다음 매개 변수를 지정합니다.

- Description
- ScreenSharingMode
- AllowParticipantGiveRequestControl
- AllowExternalParticipantGiveRequestControl
- AllowPowerPointSharing
- AllowWhiteboard
- AllowSharedNotes

[CsTeamsMeetingPolicy cmdlet을 사용하는 방법에 대해 자세히 알아보세요](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps).

