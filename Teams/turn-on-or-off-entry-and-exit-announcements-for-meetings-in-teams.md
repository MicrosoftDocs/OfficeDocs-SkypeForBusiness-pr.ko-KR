---
title: 모임에 대한 입장 및 종료 공지를 켜거나 Teams
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: f2c7b5ea-07b6-4b77-8023-bec9596fcc32
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-apr2020
description: 관리자는 모임에서 입장 및 종료 공지 사항을 켜거나 끄는 방법에 대해 Microsoft Teams 수 있습니다.
ms.openlocfilehash: f3705284745d6fa470835d45369239b3a22f9713
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58604327"
---
# <a name="turn-on-or-off-entry-and-exit-announcements-for-meetings-in-microsoft-teams"></a>모임에 대한 입장 및 종료 공지를 켜거나 Microsoft Teams

오디오 회의를 Microsoft 365 또는 Office 365 경우 오디오 회의 브리지가 있습니다. 회의 브리지에는 사람들이 모임에 전화하는 데 사용할 하나 이상의 전화 Microsoft Teams 수 있습니다.
  
회의 브리지는 전화를 사용하여 모임에 전화 접속하는 사용자에 대한 호출에 응답합니다. 회의 브리지는 회의 자동 참석자로부터 음성 프롬프트를 사용하여 발신자에 응답한 다음 설정에 따라 알림을 재생하고 발신자들에게 이름을 기록할 것을 요청하고 PIN 보안을 설정할 수 있습니다. PIN은 Microsoft Teams 모임 이끌이에게 주어지며, 모임을 시작할 수 없는 경우 모임을 시작할 수 Microsoft Teams 있습니다. 그러나 PIN이 모임을 시작하는 데 필요하지 않은지 설정할 수 있습니다.

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="setting-meeting-join-options"></a>모임 조인 옵션 설정

![Microsoft Teams 로고를 나타내는 아이콘](media/teams-logo-30x30.png) **Microsoft Teams 관리 센터 사용**

이러한 정책을 관리하려면 전역 관리자 또는 Teams 서비스 관리자여야 합니다. 관리 역할 및 사용 권한 가져오기에 대한 내용은 [Teams 관리자 역할 사용](./using-admin-roles.md)을 참조하세요.

1. 관리 센터에 로그인합니다.

2. 왼쪽 탐색에서 모임 회의  >  **브리지로 이동합니다.**

3. 컨퍼런스 브리지  페이지의 맨 위에 있는 브리지 **설정.**

4. Bridge **설정 창에서** 모임 항목 및 종료 알림을 사용하도록 설정하거나 **사용하지 않도록 설정합니다.** 기본적으로 선택됩니다. 모임을 지우면 모임에 이미 참가한 사용자에게 다른 사용자가 모임에 참가하거나 나가는 경우 알림을 들을 수 없습니다.

5. **진입/종료 공지 유형에서** 이름 **또는 전화** 번호 또는 **톤을 선택합니다.**

   > [!NOTE]
   > 기본적으로 외부 참가자는 전화 접속 참가자의 전화 번호를 볼 수 없습니다. 이러한 전화 번호의 프라이버시를 유지하려면 **입장/종료** **알림** 유형에 대해 톤을 선택하십시오(이로 인해 Teams가 번호를 읽을 수 없음).

6. 이름 또는 전화 **번호를 선택한** 경우 모임에 참가하기 전에 발신자 요청에 자신의 이름을 기록하도록 설정하거나 사용하지 **않도록 설정합니다.**

7. **저장** 을 클릭합니다.

## <a name="want-to-know-more-about-windows-powershell"></a>자세한 정보를 Windows PowerShell

Windows PowerShell 모든 것은 사용자 관리와 사용자가 허용되거나 허용되지 않는 작업을 관리하는 것입니다. 이 Windows PowerShell 여러 작업을 수행할 때 일상적인 작업을 단순화할 수 Microsoft 365 Office 365 관리 지점을 사용하여 관리 또는 관리 작업을 관리할 수 있습니다. 다음 항목을 Windows PowerShell 다음 항목을 참조하세요.

- [PowerShell 또는 Microsoft 365 Office 365 이유](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)

- [사용자와 함께 Microsoft 365 또는 Office 365 가장 Windows PowerShell](/previous-versions//dn568025(v=technet.10))

자세한 내용은 Windows PowerShell [PowerShell](/powershell/module/teams/?view=teams-ps) Microsoft Teams 참조를 참조하세요.
  
## <a name="related-topics"></a>관련 항목

[오디오 회의 일반적인 질문](audio-conferencing-common-questions.md)