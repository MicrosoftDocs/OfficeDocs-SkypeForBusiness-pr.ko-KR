---
title: Microsoft 팀에서 사용자에 대 한 전화 회의 ID 다시 설정
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 6e12242c-55f7-4bf4-90d7-0f36c0326b8e
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
description: 'Microsoft 팀에서 사용자의 모임 전화 회의 ID를 다시 설정 하는 단계와 모임 업데이트 및 마이그레이션 도구에 대 한 링크를 확인 하는 방법에 대해 알아보세요. '
ms.openlocfilehash: 2c33238ba324dc35c19a4649f58e50a7162e569a
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41838238"
---
# <a name="reset-a-conference-id-for-a-user-in-microsoft-teams"></a>Microsoft 팀에서 사용자에 대 한 전화 회의 ID 다시 설정

동적 전화 회의 ID는 전화 접속 전화 번호와 함께 모임 초대 맨 아래에 포함 되며, 발신자가 모임에 전화를 걸 때 사용할 수 있습니다. 사용자가 전화 번호를 누르면 모임에 대 한 자동 전화 교환은 발신자에 게이 회의 ID를 입력 하도록 요청 하 여 모임에 참석할 수 있도록 합니다.
  
> [!NOTE]
> 회의 공급자가 Microsoft 인 경우에는 기본적으로 사용자의 회의 Id가 동적 으로만 설정 됩니다. 아쉽게도이 기능은 지원 되지 않으므로이를 정적으로 변경할 수 없습니다. 전화 회의 Id는 자동으로 오디오 회의를 사용 하도록 설정 된 Microsoft 팀 사용자 에게만 설정 됩니다. 


## <a name="resetting-the-conference-id-for-a-user"></a>사용자의 전화 회의 ID 다시 설정

![](media/teams-logo-30x30.png) **Microsoft 팀 관리 센터를 사용 하 여** microsoft 팀 로고를 표시 하는 아이콘

1. 왼쪽 탐색 창에서 **사용자**를 클릭 한 다음 사용 가능한 사용자 목록에서 사용자를 선택 합니다.

2. **편집**을 클릭 합니다.

3. **오디오 회의** 에서 **전화 회의 ID 재설정**을 클릭 합니다.

2. **전화 회의 ID 다시 설정** 창에서 **원래 대로**를 클릭 합니다. 전화 회의 ID가 자동으로 만들어지고 새 전화 회의 ID를 사용 하 여 사용자에 게 전자 메일이 전송 됩니다. 기본적으로 전자 메일은 사용자에 게 전송 되지만,이 기능은 해제할 수 있습니다.   

    
> [!NOTE]
> 전화 회의 ID를 다시 설정 하면 새 전화 회의 ID가 포함 된 전자 메일이 사용자에 게 전송 됩니다. 이 전자 메일은 대부분의 경우 Office 365 사서함 인 기본 전자 메일 주소로 전송 됩니다. 전자 메일에는 새로운 전화 회의 ID, 기본 전화 접속 전화 번호 및 기존 모임 업데이트에 대 한 지침이 포함 되어 있습니다. 
  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="what-else-should-i-know"></a>알아야 할 기타 사항

- **오디오 회의** 섹션의 사용자에 대 한 **전자 메일에서 회의 정보 보내기를** 클릭 하 여 전화 회의 ID를 포함 하는 전자 메일에서 모든 회의 정보를 사용자에 게 보낼 수 있습니다. PIN은 전송 되지 않습니다.
    
- 전화 회의 ID에는 7 자리 숫자가 포함 되며 길이는 변경할 수 없습니다.
    
- 다시 설정한 후에는 **전화 회의 id**아래에 나열 된 새 전화 회의 id를 확인할 수 있습니다.
    
- 새 전화 회의 ID를 만든 후에는 발신자가 이전 회의 ID를 사용할 수 없습니다. 사용자에 게 기존 모임 초대를 다시 예약 하 여 새 회의 ID가 초대에 추가 되었는지 알려 주어 야 합니다. 

## <a name="want-to-know-more-about-windows-powershell"></a>Windows PowerShell에 대 한 자세한 정보를 확인 하 고 싶으신가요?

Windows PowerShell은 사용자 및 허용 되지 않거나 수행할 수 있는 사용자를 관리 하는 방법에 대해 설명 합니다. Windows PowerShell을 사용 하면 여러 작업을 수행할 때 일상 업무를 단순화할 수 있는 단일 관리 지점을 사용 하 여 Office 365를 관리할 수 있습니다. Windows PowerShell을 시작 하려면 다음 항목을 참조 하세요.
    
  - [Office 365 PowerShell을 사용 해야 하는 이유](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Windows PowerShell을 사용 하 여 Office 365를 관리 하는 가장 좋은 방법](https://go.microsoft.com/fwlink/?LinkId=525142)
    
Windows PowerShell에 대 한 자세한 내용은 [Microsoft 팀 PowerShell 참조](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) 에서 자세한 내용을 참조 하세요.
    
## <a name="related-topics"></a>관련 항목

[오디오 회의 PIN 재설정](reset-the-audio-conferencing-pin-in-teams.md)
