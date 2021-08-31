---
title: 사용자의 회의 ID 보기, 변경 및 재설정
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 77d36233-2aab-4802-ba9c-e9a8885ea643
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
description: 회의 ID를 사용자에 할당하는 Microsoft Teams 및 회의 ID 매개 변수가 무엇일지 배정합니다.
ms.openlocfilehash: 62cbb281af4db60db15676b109b2573c03eb7552
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/30/2021
ms.locfileid: "58733257"
---
# <a name="view-and-reset-a-conference-id-assigned-to-a-user-in-microsoft-teams"></a>사용자에 할당된 회의 ID 보기 및 Microsoft Teams

회의 ID는 Microsoft Teams 또는 오디오 회의에서 오디오 회의를 설정하고 Microsoft를 오디오 회의 공급자로 Microsoft 365 Office 365 사용자에 자동으로 할당됩니다. 할당된 회의 ID는 모임이 예약될 때 모임 초대에 전송됩니다. 사용자가 예약하는 각 모임에 고유한 회의 ID가 할당됩니다. 
  
회의 ID가 사용자에게 자동으로 만들어지지만 사용자가 이 ID를 사용하지 않을 때나 사용자가 회의 ID를 기억하지 못하거나 분실한 경우도 있을 수 있습니다. 관리 센터 또는 Microsoft Teams 사용하여 Windows PowerShell, 변경 및 재설정할 수 있습니다.
  
전화 회의 ID 및 기본 오디오 회의 전화 번호가 있는 사용자에게 전자 메일이 전송되거나, 전화 회의 ID를 다시 설정하면 전화 회의 ID가 포함되지만 PIN이 아닌 다른 전자 메일이 전송됩니다. 회의 [이끌이의 PIN을](reset-a-conference-id-for-a-user-in-teams.md) 다시 설정하는 Microsoft Teams 자세한 내용은 사용자에 대한 회의 ID 재설정을 참조하세요. 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="view-and-reset-conference-ids"></a>회의 아이디 보기 및 재설정

### <a name="to-view-the-conference-id"></a>회의 ID를 보기 위해

![로고가 Microsoft Teams 아이콘입니다.](media/teams-logo-30x30.png) **Microsoft Teams 관리 센터 사용**

1. 왼쪽 탐색에서 **사용자** 를 클릭한 다음 사용 가능한 사용자 목록에서 사용자를 선택합니다.

2. 페이지 맨 위에 있는 편집을 **클릭합니다.**

3. 오디오 **회의에서** 회의 **ID 아래를 봐야 합니다.**

    > [!TIP]
    > 전자 메일 링크에서 회의 정보 보내기를 클릭하여 회의 ID 및 오디오 전화 번호가 포함된 모든 회의 정보를 사용자에게 보낼 **수** 있습니다.
  
**Windows PowerShell**

자세한 [내용은 Microsoft Teams PowerShell 참조를](/powershell/module/teams/?view=teams-ps) 참조하세요.
    
  
### <a name="to-reset-the-conference-id"></a>회의 ID를 다시 설정하는 경우

예를 들어 사용자가 잊어버렸다면 사용자에 대한 회의 ID를 다시 설정할 수 있습니다.
  
![로고가 Microsoft Teams 아이콘입니다.](media/teams-logo-30x30.png) **Microsoft Teams 관리 센터 사용**

1. 왼쪽 탐색에서 **사용자** 를 클릭한 다음 사용 가능한 사용자 목록에서 사용자를 선택합니다.

2. 페이지 맨 위에 있는 편집을 **클릭합니다.**

3. 오디오 **회의에서** 회의 ID **재설정을 클릭합니다.**

4. 회의 **ID 재설정 창에서** 다시 설정 **을 클릭합니다.** 회의 ID가 자동으로 생성되고 새 회의 ID가 있는 사용자에게 전자 메일이 전송됩니다.
  
**Windows PowerShell**

자세한 [내용은 Microsoft Teams PowerShell 참조를](/powershell/module/teams/?view=teams-ps) 참조하세요.


## <a name="what-else-should-you-know"></a>또 어떤 것을 알아야 하나요?

   > [!IMPORTANT]
   >  새 회의 ID를 만들거나 다시 설정한 후 이전 회의 ID를 호출자에서 사용할 수 없습니다. 새 회의 ID가 초대에 추가될 수 있도록 기존 모임 초대를 다시 계획할 수 있도록 사용자에게 알려야 합니다. 
  
    
- 회의 ID는 오디오 회의 브리지에 설정된 숫자의 길이를 충족해야 합니다. 회의 신분증에는 사전 문자 또는 특수 문자를 사용할 수 없습니다. 숫자만 사용할 수 있습니다.
   
    
## <a name="want-to-know-more-about-windows-powershell"></a>자세한 정보를 Windows PowerShell?

Windows PowerShell 모든 것은 사용자 관리와 사용자가 허용되거나 허용되지 않는 작업을 관리하는 것입니다. 이 Windows PowerShell 여러 작업을 수행할 때 일상적인 작업을 단순화할 수 Microsoft 365 Office 365 관리 지점을 사용하여 관리 또는 관리 작업을 관리할 수 있습니다. 다음 항목을 Windows PowerShell 다음 항목을 참조하세요.
    
  - [PowerShell을 Office 365 이유](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - [사용자와 함께 Microsoft 365 또는 Office 365 가장 Windows PowerShell](/previous-versions//dn568025(v=technet.10))
    
자세한 내용은 Windows PowerShell [PowerShell](/powershell/module/teams/?view=teams-ps) Microsoft Teams 참조를 참조하세요.
    
## <a name="related-topics"></a>관련 항목

[오디오 회의를 시도하거나 Microsoft 365 또는 Office 365](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)