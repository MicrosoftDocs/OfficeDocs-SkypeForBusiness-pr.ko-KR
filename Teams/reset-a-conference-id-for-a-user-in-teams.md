---
title: Microsoft Teams에서 사용자의 회의 ID 다시 설정
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
- seo-marvel-mar2020
description: Microsoft Teams에서 사용자의 모임 회의 ID를 다시 설정하는 단계를 알아보고 모임 업데이트 및 마이그레이션 도구에 대한 링크를 얻습니다.
ms.openlocfilehash: 52b547fee5bf027bcef21914e3ba3aa79b0e4e08
ms.sourcegitcommit: 7a9c63ee790108eaa61950ce28ae8027311039d9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/13/2020
ms.locfileid: "46662128"
---
# <a name="reset-a-conference-id-for-a-user-in-microsoft-teams"></a>Microsoft Teams에서 사용자의 회의 ID 다시 설정

동적 전화 회의 ID는 발신자에서 모임에 전화 접속하는 데 사용할 수 있는 전화 접속 전화 번호와 함께 모임 초대의 아래쪽에 포함됩니다. 사용자가 전화 번호로 전화를 걸면 모임의 자동 전화 접속자가 발신자가 이 전화 회의 ID를 입력하도록 요청하여 모임에 참석할 수 있습니다.
  
> [!NOTE]
> 회의 ID는 자동으로 생성되고, 7-9자리 사이가 되며, 사용자에 대해 오디오 회의를 사용하도록 설정하면 설정됩니다. **정적 회의 신분은 지원되지 않습니다.** 

## <a name="resetting-the-conference-id-for-a-user"></a>사용자의 회의 ID 다시 설정

![Microsoft Teams 로고를 나타내는 아이콘](media/teams-logo-30x30.png) **Microsoft Teams 관리 센터 사용**

1. 왼쪽 탐색 모음에서 **[사용자]를** 클릭한 다음 사용 가능한 사용자 목록에서 사용자를 선택합니다.

2. 편집을 **클릭합니다.**

3. 오디오 **회의에서** 회의 **ID 재설정을 클릭합니다.**

2. 다시 설정 **회의 ID 창에서** 재설정을 **클릭합니다.** 회의 ID가 자동으로 만들어지며 새 회의 ID가 있는 전자 메일이 사용자에게 전송됩니다. 기본적으로 전자 메일은 사용자에게 전송되지만 해제할 수 있습니다.   

    
> [!NOTE]
> 회의 ID를 다시 설정하면 새 회의 ID가 있는 전자 메일이 사용자에게 전송됩니다. 이 전자 메일은 대부분의 경우 Microsoft 365 또는 Office 365 사서함의 기본 전자 메일 주소로 전송됩니다. 전자 메일에는 새 전화 회의 ID, 기본 전화 접속 전화 번호 및 기존 모임 업데이트 지침이 포함되어 있습니다. 
  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="what-else-should-i-know"></a>알아야 할 다른 것은 무엇입니까?

- **오디오** 회의 섹션에서 사용자의 전자 메일로 전화 회의 정보 보내기를 클릭하여 전화 회의 ID 및  전화 접속 전화 번호가 포함된 전자 메일로 모든 회의 정보를 사용자에게 보낼 수 있습니다. PIN은 보내지 않습니다.
    
- Teams 서비스에 의해 7-9자리 회의 ID가 만들어집니다. 길이는 변경할 수 없습니다.
    
- 다시 설정되면 회의 ID 아래에 나열된 새 회의 **ID를 볼 수 있습니다.**
    
- 새 전화 회의 ID가 생성되면 발신자에 의해 이전 전화 회의 ID를 사용할 수 없습니다. 새 회의 ID가 초대에 추가될 수 있도록 사용자에게 기존 모임 초대를 다시 계획할지 알려야 합니다. 

## <a name="want-to-know-more-about-windows-powershell"></a>자세한 내용은 Windows PowerShell?

Windows PowerShell 관리는 사용자 및 사용자가 허용되거나 허용되지 않는 작업을 관리하는 것입니다. 이 Windows PowerShell 여러 작업을 수행할 때 일상적인 작업을 간소화할 수 있는 단일 관리 지점을 사용하여 Microsoft 365 또는 Office 365를 관리할 수 있습니다. 다음 항목을 Windows PowerShell 항목을 참조하세요.
    
  - [Office 365 PowerShell을 사용하는 이유](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Microsoft 365 또는 Office 365를 관리하는 가장 좋은 Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
자세한 내용은 Windows PowerShell [Microsoft Teams PowerShell 참조를](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) 참조하세요.
    
## <a name="related-topics"></a>관련 항목

[오디오 회의 PIN 재설정](reset-the-audio-conferencing-pin-in-teams.md)
