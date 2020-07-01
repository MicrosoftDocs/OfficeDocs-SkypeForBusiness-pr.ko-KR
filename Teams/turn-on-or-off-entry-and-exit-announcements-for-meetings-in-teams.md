---
title: 팀에서 모임에 대 한 알림 입력/해제 및 종료
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
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-apr2020
description: 관리자는 Microsoft 팀 모임에서 입력 및 종료 알림을 설정 하거나 해제 하는 방법에 대해 알아볼 수 있습니다.
ms.openlocfilehash: ae2e8936b3fe0dbac0ba0d6ad7bfad3ab2e322ef
ms.sourcegitcommit: 60b859dcb8ac727a38bf28cdb63ff762e7338af8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/30/2020
ms.locfileid: "44938557"
---
# <a name="turn-on-or-off-entry-and-exit-announcements-for-meetings-in-microsoft-teams"></a>Microsoft 팀에서 모임에 대 한 시작 및 종료 알림 설정 또는 해제

Microsoft 365 또는 Office 365에서 오디오 회의를 설정 하는 경우 오디오 회의 브리지가 제공 됩니다. 회의 브리지에는 사용자가 Microsoft 팀 모임에 전화를 걸 때 사용 하는 하나 이상의 전화 번호가 포함 될 수 있습니다. 
  
회의 브리지가 휴대폰을 사용 하 여 모임에 전화를 거는 사용자에 대 한 통화에 응답 합니다. 회의 브리지는 회의 자동 전화 교환에서 음성 메시지를 사용 하 여 발신자에 응답 한 다음 설정에 따라 알림을 재생 하 고, 발신자에 게 이름을 기록 하도록 요청 하 고, PIN 보안을 설정할 수 있습니다. PIN은 Microsoft 팀 모임 이끌이에게 제공 되며, Microsoft 팀 앱을 사용 하 여 모임을 시작할 수 없는 경우 모임을 시작할 수 있습니다. 그러나 모임 시작에 PIN이 필요 하지 않도록 설정할 수 있습니다.

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="setting-meeting-join-options"></a>모임 참가 옵션 설정

![Microsoft Teams 로고를 나타내는 아이콘](media/teams-logo-30x30.png) **Microsoft Teams 관리 센터 사용**

이러한 변경 작업을 수행 하려면 관리자 여야 합니다.

1. 의 관리 센터에 로그인  <a href="https://admin.teams.microsoft.com" target="_blank">https://admin.teams.microsoft.com</a> 합니다.

2. 왼쪽 탐색 창에서 **모임**  >  **회의 브리지로**이동 합니다. 

3. **회의 브리지** 페이지 맨 위에서 **브리지 설정을**클릭 합니다. 

4. **브리지 설정** 창에서 모임 항목을 사용 하거나 사용 하지 않도록 설정 **하 고 알림을 종료**합니다. 이 옵션이 기본적으로 선택 되어 있습니다. 이 확인란을 선택 취소 하면 모임에 참가 한 사용자에 게 다른 사용자가 모임에 입장 하거나 떠날 때 알림이 표시 되지 않습니다.
    
5. **입력/종료 알림 유형에**서 **이름 또는 전화 번호** 또는 **톤**을 선택 합니다.

   > [!NOTE]
   > 기본적으로 외부 참가자는 전화를 건 참가자의 전화 번호를 볼 수 없습니다. 이러한 전화 번호의 프라이버시를 유지하려면 **입장/종료** **알림** 유형에 대해 톤을 선택하십시오(이로 인해 Teams가 번호를 읽을 수 없음).
    
6. **이름 또는 전화 번호**를 선택한 경우 **전화 건 사람이 모임에 참가 하기 전에 해당 이름을 기록해 달라고 요청**하거나 사용 하지 않도록 설정 합니다.
    
7. **저장**을 클릭합니다.

## <a name="want-to-know-more-about-windows-powershell"></a>Windows PowerShell에 대 한 자세한 정보를 확인 하 고 싶으신가요?

Windows PowerShell은 사용자 및 허용 되지 않거나 수행할 수 있는 사용자를 관리 하는 방법에 대해 설명 합니다. Windows PowerShell을 사용 하면 여러 작업을 수행할 때 일상 업무를 단순화할 수 있는 단일 관리 지점을 사용 하 여 Microsoft 365 또는 Office 365를 관리할 수 있습니다. Windows PowerShell을 시작 하려면 다음 항목을 참조 하세요.
    
  - [Microsoft 365 또는 Office 365 PowerShell을 사용 해야 하는 이유](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Windows PowerShell을 사용 하 여 Microsoft 365 또는 Office 365을 관리 하는 최상의 방법](https://go.microsoft.com/fwlink/?LinkId=525142)
    
Windows PowerShell에 대 한 자세한 내용은 [Microsoft 팀 PowerShell 참조](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) 에서 자세한 내용을 참조 하세요.
  
## <a name="related-topics"></a>관련 항목

[오디오 회의 일반적인 질문](audio-conferencing-common-questions.md)
