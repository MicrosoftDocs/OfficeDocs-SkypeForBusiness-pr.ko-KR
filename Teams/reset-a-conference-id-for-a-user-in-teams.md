---
title: 사용자에 대한 회의 ID를 Microsoft Teams
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
description: 사용자의 모임 모임 ID를 Microsoft Teams 단계에 대해 알아보고 모임 업데이트 및 마이그레이션 도구에 대한 링크를 얻습니다.
ms.openlocfilehash: 3c266b59bab4c51293d429d4698b3c79fe8b84232d519499f8a1bfa27a0c0d94
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54319781"
---
# <a name="reset-a-conference-id-for-a-user-in-microsoft-teams"></a>사용자에 대한 회의 ID를 Microsoft Teams

동적 회의 ID는 전화 접속 전화 번호와 함께 모임 초대 맨 아래에 포함되어 있습니다. 사용자가 전화 번호에 전화를 걸면 모임의 자동 참석자가 전화 회의에 참석할 수 있도록 발신자에게 이 회의 ID를 입력하도록 요청합니다.
  
> [!NOTE]
> 회의 ID는 자동으로 생성되고, 7-9자리 사이로 설정되며, 사용자에 대해 오디오 회의를 사용하도록 설정할 때 설정됩니다. **정적 회의 신분은 지원되지 않습니다.** 

## <a name="resetting-the-conference-id-for-a-user"></a>사용자에 대한 회의 ID 재설정

![Microsoft Teams 로고를 나타내는 아이콘](media/teams-logo-30x30.png) **Microsoft Teams 관리 센터 사용**

1. 왼쪽 탐색에서 **사용자** 를 클릭한 다음 사용 가능한 사용자 목록에서 사용자를 선택합니다.

2. 편집을 **클릭합니다.**

3. 오디오 **회의에서** 회의 **ID 재설정을 클릭합니다.**

2. 회의 **ID 재설정 창에서** 다시 설정 **을 클릭합니다.** 회의 ID가 자동으로 생성되고 새 회의 ID가 있는 사용자에게 전자 메일이 전송됩니다. 기본적으로 전자 메일은 사용자에게 전송되지만 해제할 수 있습니다.   

    
> [!NOTE]
> 회의 ID를 다시 설정하면 새 회의 ID가 있는 전자 메일이 사용자에게 전송됩니다. 이 전자 메일은 기본 전자 메일 주소로 전송됩니다. 대부분의 경우 해당 전자 메일 Microsoft 365 Office 365 합니다. 전자 메일에는 새 회의 ID, 기본 전화 접속 전화 번호 및 기존 모임 업데이트 지침이 포함되어 있습니다. 
  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="what-else-should-i-know"></a>다른 무엇을 알아야 하나요?

- 오디오 회의 섹션에서 사용자에 대한 전자 메일로 회의 정보 보내기를 클릭하여 회의 ID 및  전화 접속 전화 번호가 포함된 전자 메일에서 모든 회의 정보를 사용자에게 보낼 **수** 있습니다. PIN을 보내지 않습니다.
    
- 7-9자리 회의 ID는 Teams 생성됩니다. 길이는 변경할 수 없습니다.
    
- 다시 설정한 후 회의 ID 에 나열된 새 회의 **ID를 볼 수 있습니다.**
    
- 새 회의 ID를 만든 후 이전 회의 ID는 발신자에서 사용할 수 없습니다. 새 회의 ID가 초대에 추가될 수 있도록 기존 모임 초대를 다시 계획할 수 있도록 사용자에게 알려야 합니다. 

## <a name="want-to-know-more-about-windows-powershell"></a>자세한 정보를 Windows PowerShell?

Windows PowerShell 모든 것은 사용자 관리와 사용자가 허용되거나 허용되지 않는 작업을 관리하는 것입니다. 이 Windows PowerShell 여러 작업을 수행할 때 일상적인 작업을 단순화할 수 Microsoft 365 Office 365 관리 지점을 사용하여 관리 또는 관리 작업을 관리할 수 있습니다. 다음 항목을 Windows PowerShell 다음 항목을 참조하세요.
    
  - [PowerShell을 Office 365 이유](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - [사용자와 함께 Microsoft 365 또는 Office 365 가장 Windows PowerShell](/previous-versions//dn568025(v=technet.10))
    
자세한 내용은 Windows PowerShell [PowerShell](/powershell/module/teams/?view=teams-ps) Microsoft Teams 참조를 참조하세요.
    
## <a name="related-topics"></a>관련 항목

[오디오 회의 PIN 재설정](reset-the-audio-conferencing-pin-in-teams.md)