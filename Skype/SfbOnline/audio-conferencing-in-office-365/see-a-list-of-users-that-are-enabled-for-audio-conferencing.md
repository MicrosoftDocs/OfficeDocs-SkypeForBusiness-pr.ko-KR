---
title: 비즈니스용 Skype Online에서 오디오 회의에 사용할 수 있는 사용자 목록을 참조하세요.
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: bd0cd155-4c6d-424d-a2c9-af7974a2d34c
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: '비즈니스용 Skype 관리 센터 내에서 전화 접속 회의를 사용할 수 있는 조직의 사용자 목록을 보는 방법에 대해 자세히 알아보습니다. '
ms.openlocfilehash: 2cb4481f480f5be9f45064aed1fd48f9f5c28496
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51114134"
---
# <a name="see-a-list-of-users-that-are-enabled-for-audio-conferencing-in-skype-for-business-online"></a>비즈니스용 Skype Online에서 오디오 회의에 사용할 수 있는 사용자 목록을 참조하세요.

> [!NOTE]
> Microsoft Teams에서 사용 가능한 사용자에 대한 자세한 내용은 Microsoft Teams에서 오디오 회의에 사용할 수 있는 사용자 목록을 [참조하세요.](/MicrosoftTeams/see-a-list-of-users-that-are-enabled-for-audio-conferencing-in-teams)

조직에서 비즈니스용 Skype 사용자를 오디오 회의를 사용하도록 설정한 후 사용하도록 설정된 사용자의 목록을 볼 수 있습니다. 목록을 보면 목록에서 각 사용자에 대해 사용하는 오디오 회의 공급자 유형, 사용자의 기본 전화 접속 전화 번호, 동적 회의 ID에 대해 조직이 활성화되지 않은 경우 사용자가 구성하는 오디오 회의 모임에 대한 정적 회의 ID도 표시됩니다.

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="viewing-a-list-of-users"></a>사용자 목록 보기

   
- 왼쪽 탐색에서 **오디오** 회의 사용자로  >  **이동합니다.**

## <a name="what-else-should-i-know"></a>다른 무엇을 알아야 하나요?

- 사용 가능한 사용자 목록을 볼 때 목록에서 사용자를 선택하고 작업 창을 사용하여 해당 사용자의 오디오 회의 설정을 편집할 수 있습니다.
    
- 오디오 회의 공급자로 Microsoft를 사용하도록 구성된 단일 사용자를 선택하면 기본 전화 번호와 조직이 동적 회의 ID에 사용하도록 설정되어 있는지 여부를 볼 수 있으며 사용자가 구성하는 모임에 대한 회의 ID를 다시 설정할 수 있습니다.
    
- 타사 오디오 회의 공급자를 사용하도록 구성된 단일 사용자를 선택하면 오디오 회의 공급자의 이름, 전화 번호 및 무료 전화 번호(설정된 경우)를 볼 수 있습니다.
    
- 필터 옵션을 사용하여 다음과 같은 사용자를 표시할 수 있습니다.
    
  - **의 오디오 회의**
    
  - **오디오 회의 해제**
    
  - **회의 공급자 - Microsoft**
    
  - **회의 공급자 - 기타**
    
- 검색 단추를 사용하여 목록에서 개별 사용자를 검색할 수 있습니다.
    
- 두 개 이상의 사용자를 선택하고 다음을 할 수 있습니다.
    
  - 이러한 사용자에 대해 다른 기본 번호를 선택합니다.
    
  - 공급자를 없음으로 변경하여 사용자에 대한 오디오 회의를 **해제합니다.**
    
  - 사용자가 오디오 회의 라이선스를 할당한 경우 오디오 회의 공급자로 **Microsoft로 전환합니다.**
    
  - 익명 사용자가 선택한 사용자의 전화 모임을 활성화하도록 허용/허용하지 않습니다.
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>사용자와 함께 관리하는 방법을 알고 Windows PowerShell.

- Windows PowerShell 모든 것은 사용자 관리와 사용자가 허용되거나 허용되지 않는 작업을 관리하는 것입니다. 이 Windows PowerShell 여러 작업을 수행할 때 일상적인 작업을 단순화할 수 있는 단일 관리 지점을 사용하여 Microsoft 365 또는 Office 365 및 비즈니스용 Skype Online을 관리할 수 있습니다. 다음 항목을 Windows PowerShell 항목을 참조하세요.
    
  - [Windows PowerShell 및 비즈니스용 Skype Online 소개](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [Microsoft 365 또는 Office 365 PowerShell을 사용해야 하는 이유](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
- Windows PowerShell 사용자에 대한 설정을 한 번씩 변경하는 경우와 같이 Microsoft 365 관리 센터를 사용하는 경우와 같이 Microsoft 365 관리 센터를 사용하는 것 이상으로 속도, 단순성 및 생산성에 많은 이점이 있습니다. 다음 항목에서 이러한 이점에 대해 자세히 알아보습니다.
    
  - [Microsoft 365 또는 Office 365를 관리하는 가장 좋은 Windows PowerShell](/previous-versions//dn568025(v=technet.10))
    
  - [비즈니스용 skype Windows PowerShell 관리하기 위해 사용](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [비즈니스용 Windows PowerShell Skype 온라인 관리 작업을 수행하는 데 사용할 수 있습니다.](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
## <a name="related-topics"></a>관련 항목

[Microsoft 365 또는 Office 365에서 오디오 회의 시도 또는 구매](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)