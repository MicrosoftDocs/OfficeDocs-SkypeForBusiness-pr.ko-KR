---
title: Microsoft 팀에서 데스크톱 공유 구성
author: LolaJacobsen
ms.author: Lolaj
manager: serdars
ms.reviewer: jastark
ms.date: 03/22/2019
ms.topic: article
ms.service: msteams
search.appverid: MET150
description: 사용자가 팀 채팅 또는 모임에서 데스크톱을 공유할 수 있도록 모임 정책 구성
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0bf213b919ee0bea344807f932e16240587b2b84
ms.sourcegitcommit: b92b673e718e34b6ebda6de57ad69eb6651faa98
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/24/2019
ms.locfileid: "36183641"
---
<a name="configure-desktop-sharing-in-microsoft-teams"></a>Microsoft 팀에서 데스크톱 공유 구성
============================================

데스크톱 공유를 통해 사용자는 모임 또는 채팅 중에 화면이 나 앱을 발표할 수 있습니다. 관리자는 Microsoft 팀에서 화면 공유를 구성 하 여 사용자가 전체 화면, 앱 또는 파일을 공유 하도록 할 수 있습니다. 사용자가 제어권을 부여 하거나 요청 하 고 PowerPoint 공유를 허용 하 고 화이트 보드를 추가 하 고 공유 노트를 허용 하도록 할 수 있습니다. 또한 익명 또는 외부 사용자가 공유 화면의 제어권을 요청할 수 있는지 여부도 구성할 수 있습니다.

화면 공유를 구성 하려면 새 모임 정책을 만든 다음 관리 하려는 사용자에 게 할당 합니다.

**Microsoft 팀 관리 센터**

1.  > 모임 ******모임 정책을**선택 합니다.

    ![모임 정책을 선택한 것을 보여 주는 스크린샷](media/configure-desktop-sharing-image1.png)

2. **모임 정책** 페이지에서 **새 정책을**선택 합니다.

    ![모임 정책 메시지를 보여 주는 스크린샷](media/configure-desktop-sharing-image2.png)

3. 정책에 고유한 제목을 지정 하 고 간략 한 설명을 입력 합니다.

4. **콘텐츠 공유**아래 드롭다운 목록에서 **화면 공유 모드** 를 선택 합니다.

   - **전체 화면** – 사용자가 전체 데스크톱을 공유할 수 있습니다.
   - **단일 응용 프로그램** – 사용자가 화면 공유를 단일 활성 응용 프로그램으로 제한할 수 있습니다.
   - **사용 안 함** – 화면 공유 기능을 해제 합니다.

    ![공유 모드 옵션을 보여 주는 스크린샷](media/configure-desktop-sharing-image3.png)

5. 다음 설정을 설정 하거나 해제 합니다.

    - **참가자가 제어권을 부여 하거나 요청할 수 있도록 허용** -팀 멤버가 발표자의 데스크톱 또는 응용 프로그램에 대 한 제어권을 부여 하거나 요청할 수 있습니다.
    - **외부 참가자가 제어권을 부여 하거나 요청 하도록 허용** – 게스트 및 외부 (페더레이션된) 사용자가 발표자의 데스크톱 또는 응용 프로그램에 대 한 제어권을 부여 하거나 요청할 수 있습니다.
    - **Powerpoint 공유 허용** -사용자가 powerpoint 프레젠테이션을 업로드 하 고 공유할 수 있는 모임을 만들 수 있습니다.
    - **화이트 보드 허용** – 사용자가 화이트 보드를 공유할 수 있습니다.
    - **공유 메모 허용** -사용자가 공유 메모를 찍을 수 있습니다.

6. **저장**을 클릭 합니다.

## <a name="use-powershell-to-configure-shared-desktop"></a>PowerShell을 사용 하 여 공유 데스크톱 구성

[Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps) cmdlet을 사용 하 여 데스크톱 공유를 제어할 수도 있습니다. 다음 매개 변수를 설정 합니다.

- 설명
- ScreenSharingMode
- AllowParticipantGiveRequestControl
- AllowExternalParticipantGiveRequestControl
- AllowPowerPointSharing
- AllowWhiteboard 보드
- AllowSharedNotes

[CsTeamsMeetingPolicy cmdlet을 사용 하는 방법에 대해 자세히 알아보세요](https://docs.microsoft.com/en-us/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps).

