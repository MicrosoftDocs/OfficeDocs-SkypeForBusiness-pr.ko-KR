---
title: 온라인에서 사용자에 대한 비즈니스용 Skype 다시 설정
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 6e12242c-55f7-4bf4-90d7-0f36c0326b8e
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
description: '온라인에서 사용자의 모임 모임 ID를 다시 설정하고 비즈니스용 Skype 업데이트 및 마이그레이션 도구에 대한 링크를 얻을 수 있는 단계에 대해 알아보십시오. '
ms.openlocfilehash: 57523cfc0186120c42fffe01961cd71f623bfa964ecf0c8251a26e518a31abd4
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54310267"
---
# <a name="reset-a-conference-id-for-a-user-in-skype-for-business-online"></a>온라인에서 사용자에 대한 비즈니스용 Skype 다시 설정

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

> [!NOTE]
> 에서 회의 ID를 다시 설정하는 Microsoft Teams 의 사용자에 대한 회의 [ID 재설정을 Microsoft Teams.](/MicrosoftTeams/reset-a-conference-id-for-a-user-in-teams)

동적 회의 ID는 전화 접속 전화 번호와 함께 모임 초대 맨 아래에 포함되어 있습니다. 사용자가 전화 번호에 전화를 걸면 모임의 자동 참석자가 전화 회의에 참석할 수 있도록 발신자에게 이 회의 ID를 입력하도록 요청합니다.
  
> [!NOTE]
> 회의 공급자가 Microsoft인 경우 사용자의 회의 신분은 동적 전용으로 설정됩니다. 변경할 수 없습니다. 컨퍼런스 신분은 오디오 회의에 사용하도록 설정된 비즈니스용 Skype 사용자에 대해 자동으로 설정됩니다. 

## <a name="resetting-the-conference-id-for-a-user"></a>사용자에 대한 회의 ID 재설정
   
1. 비즈니스용 Skype 관리 센터에서 오디오 회의 사용자를 클릭하고 사용자를 선택한 다음 회의 ID 아래의 작업 창에서 다시  >  설정 **을 클릭합니다.** 
    
2. 회의 **ID 재설정 창에서** 예 **를 클릭합니다.** 회의 ID가 자동으로 생성되고 새 회의 ID가 있는 사용자에게 전자 메일이 전송됩니다. 기본적으로 전자 메일은 사용자에게 전송되지만 해제할 수 있습니다.
    
> [!NOTE]
> 회의 ID를 다시 설정하면 새 회의 ID가 있는 전자 메일이 사용자에게 전송됩니다. 이 전자 메일은 기본 전자 메일 주소로 전송됩니다. 대부분의 경우 해당 전자 메일 Microsoft 365 Office 365 합니다. 전자 메일에는 새 회의 ID, 기본 전화 접속 전화 번호 및 모임 업데이트 도구를 사용하여 기존 모임을 비즈니스용 Skype 지침이 포함되어 있습니다. 
  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="what-else-should-i-know"></a>다른 무엇을 알아야 하나요?

- 작업 창의 사용자에 대한 전자 메일을 통해 회의 정보 보내기를 클릭하여 회의 ID 및 전화  접속 전화 번호가 포함된 전자 메일에서 사용자에게 모든 회의 정보를 보낼 수 있습니다. PIN을 보내지 않습니다.
    
- 회의 ID에는 7자리 숫자가 포함되어 있으며 관리 센터에서 또는 비즈니스용 Skype 사용하여 해당 길이를 변경할 수 Windows PowerShell.
    
- 다시 설정한 후 회의 ID 에 나열된 새 회의 **ID를 볼 수 있습니다.**
    
- 오디오 회의용 사용자의 회의 ID는 사용자 페이지에서 사용자를 선택할 때 오디오 회의  아래 작업 창 아래쪽에서 볼 **수** 있습니다.
    
- 새 회의 ID를 만든 후 이전 회의 ID는 발신자에서 사용할 수 없습니다. 새 회의 ID가 초대에 추가될 수 있도록 기존 모임 초대를 다시 계획할 수 있도록 사용자에게 알려야 합니다. 사용자는 모임 도구를 사용하여 비즈니스용 Skype 업데이트할 수 있습니다. 모임 업데이트 도구를 다운로드, 설치 및 비즈니스용 Skype 방법을 참조하려면 다음을 참조하세요.
    
  - [모임 업데이트 도구 비즈니스용 Skype 및 Lync](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4)
    
  - [비즈니스용 Skype 온라인, 모임 마이그레이션 도구(64비트)](https://go.microsoft.com/fwlink/?LinkID=626047)
    
  - [비즈니스용 Skype 온라인, 모임 마이그레이션 도구(32비트)](https://www.microsoft.com/download/details.aspx?id=54079)
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>사용자와 함께 관리하는 방법을 알고 Windows PowerShell?

- 사용자 관리에 Windows PowerShell 사용자가 허용되거나 허용되지 않는 작업을 모두 관리하는 것입니다. 이 Windows PowerShell 여러 작업을 수행할 때 일상적인 작업을 단순화할 수 있는 단일 관리 Microsoft 365 Office 365 비즈니스용 Skype 온라인에서 관리하거나 온라인을 관리할 수 있습니다. 다음 항목을 Windows PowerShell 다음 항목을 참조하세요.
    
  - [Windows PowerShell 및 비즈니스용 Skype Online 소개](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [PowerShell 또는 Microsoft 365 Office 365 이유](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
 
- Windows PowerShell 많은 사용자에 대해 설정을 한 Microsoft 365 관리 센터 설정하는 경우와 같이 데이터만 사용하여 속도, 단순성 및 생산성에 많은 이점이 있습니다. 다음 항목에서 이러한 이점에 대해 자세히 알아보습니다.
    
  - [사용자와 함께 Microsoft 365 또는 Office 365 가장 Windows PowerShell](/previous-versions//dn568025(v=technet.10))
    
  - [온라인 Windows PowerShell 관리하기 위해 비즈니스용 Skype 사용](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [일반적인 Windows PowerShell 관리 작업을 수행하는 데 비즈니스용 Skype 사용](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
## <a name="related-topics"></a>관련 항목

[오디오 회의 PIN 재설정](reset-the-audio-conferencing-pin.md)
