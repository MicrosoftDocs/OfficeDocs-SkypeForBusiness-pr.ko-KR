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
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-apr2020
description: Microsoft Teams에서 사용자에게 회의 ID를 할당하는 방법과 회의 ID 매개 변수를 지정해야 하는 방법을 배워야 합니다.
ms.openlocfilehash: 4f24fb85479e6a52c8b2658b7a8a41beb0e1c6ad
ms.sourcegitcommit: 1807ea5509f8efa6abba8462bce2f3646117e8bf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/10/2020
ms.locfileid: "44691154"
---
# <a name="view-and-reset-a-conference-id-assigned-to-a-user-in-microsoft-teams"></a>Microsoft Teams에서 사용자에게 할당된 회의 ID 보기 및 다시 설정

Microsoft 365 또는 Office 365에서 오디오 회의를 설정하고 Microsoft를 오디오 회의 공급자로 사용할 때 회의 ID가 Microsoft Teams 사용자에게 자동으로 할당됩니다. 할당된 회의 ID는 모임이 예약될 때 모임 초대에 전송됩니다. 사용자가 예약하는 각 모임에는 고유한 회의 ID가 할당됩니다. 
  
전화 회의 ID가 자동으로 만들어지며 사용자에게 할당되어도 사용자가 이 ID를 사용하지 못하고 특정 번호로 설정하거나 사용자가 전화 회의 ID를 기억하지 못하거나 분실한 경우도 있을 수 있습니다. Microsoft Teams 관리 센터 또는 Windows PowerShell ID를 보고, 변경하고, 재설정할 수 있습니다.
  
전화 회의 ID와 기본 오디오 회의 전화 번호가 포함된 전자 메일이 사용자에게 전송되거나 전화 회의 ID를 다시 설정하면 전화 회의 ID는 포함하지만 PIN은 포함하지 않는 다른 전자 메일이 전송됩니다. 회의 [이끌이의](reset-a-conference-id-for-a-user-in-teams.md) PIN을 다시 설정하는 방법에 대한 자세한 내용은 Microsoft Teams에서 사용자의 회의 ID 재설정을 참조하세요. 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="view-and-reset-conference-ids"></a>회의 ID 보기 및 재설정

### <a name="to-view-the-conference-id"></a>회의 ID를 보기 위해

![Microsoft Teams 로고를 나타내는 아이콘](media/teams-logo-30x30.png) **Microsoft Teams 관리 센터 사용**

1. 왼쪽 탐색 모음에서 **[사용자]를** 클릭한 다음 사용 가능한 사용자 목록에서 사용자를 선택합니다.

2. 페이지 맨 위에 있는 편집을 **클릭합니다.**

3. 오디오 **회의 아래에서** 회의 **ID를 살펴 봐야 합니다.**

    > [!TIP]
    > 전자 메일 링크에서 전화 회의 정보 보내기를 클릭하여 전화 회의 ID 및 오디오 전화 번호가 포함된 전자 메일로 사용자에게 모든 회의 정보를 **보낼 수** 있습니다.
  
**다음 Windows PowerShell**

자세한 내용은 [Microsoft Teams PowerShell 참조를](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) 참조하세요.
    
  
### <a name="to-reset-the-conference-id"></a>회의 ID를 다시 설정

예를 들어 사용자가 잊어버렸다면 사용자의 회의 ID를 다시 설정할 수 있습니다.
  
![Microsoft Teams 로고를 나타내는 아이콘](media/teams-logo-30x30.png) **Microsoft Teams 관리 센터 사용**

1. 왼쪽 탐색 모음에서 **[사용자]를** 클릭한 다음 사용 가능한 사용자 목록에서 사용자를 선택합니다.

2. 페이지 맨 위에 있는 편집을 **클릭합니다.**

3. 오디오 **회의에서** 회의 ID **재설정을 클릭합니다.**

4. 다시 설정 **회의 ID 창에서** 재설정을 **클릭합니다.** 회의 ID가 자동으로 만들어지며 새 회의 ID가 있는 전자 메일이 사용자에게 전송됩니다.
  
**다음 Windows PowerShell**

자세한 내용은 [Microsoft Teams PowerShell 참조를](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) 참조하세요.


## <a name="what-else-should-you-know"></a>알아야 할 다른 것은 무엇입니까?

   > [!IMPORTANT]
   >  새 전화 회의 ID가 만들어지거나 다시 설정되면 발신자에 의해 이전 전화 회의 ID를 사용할 수 없습니다. 새 회의 ID가 초대에 추가될 수 있도록 사용자에게 기존 모임 초대를 다시 계획할지 알려야 합니다. 
  
    
- 회의 ID는 오디오 회의 브리지에 설정된 자릿수 길이를 충족해야 합니다. 회의 신분증에는 사전 또는 특수 문자를 사용할 수 없습니다. 숫자만 사용할 수 있습니다.
   
    
## <a name="want-to-know-more-about-windows-powershell"></a>자세한 내용은 Windows PowerShell?

Windows PowerShell 관리는 사용자 및 사용자가 허용되거나 허용되지 않는 작업을 관리하는 것입니다. 이 Windows PowerShell 여러 작업을 수행할 때 일상적인 작업을 간소화할 수 있는 단일 관리 지점을 사용하여 Microsoft 365 또는 Office 365를 관리할 수 있습니다. 다음 항목을 Windows PowerShell 항목을 참조하세요.
    
  - [Office 365 PowerShell을 사용하는 이유](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Microsoft 365 또는 Office 365를 관리하는 가장 좋은 Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
자세한 내용은 Windows PowerShell [Microsoft Teams PowerShell 참조를](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) 참조하세요.
    
## <a name="related-topics"></a>관련 항목

[Microsoft 365 또는 Office 365에서 오디오 회의 시도 또는 구매](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)
