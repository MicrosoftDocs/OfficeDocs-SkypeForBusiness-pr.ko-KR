---
title: 비즈니스용 Skype Online에서 사용자의 전화 회의 ID 다시 설정
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
description: '비즈니스용 Skype Online에서 사용자의 모임 전화 회의 ID를 다시 설정하는 단계를 알아보고 모임 업데이트 및 마이그레이션 도구에 대한 링크를 얻습니다. '
ms.openlocfilehash: f0bf8a991cfa7c597bb7a0424709e81851291307
ms.sourcegitcommit: 36f7ec432090683aedb77a5bd7856e1b10af2a81
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2020
ms.locfileid: "44164707"
---
# <a name="reset-a-conference-id-for-a-user-in-skype-for-business-online"></a>비즈니스용 Skype Online에서 사용자의 전화 회의 ID 다시 설정

> [!NOTE]
> Microsoft Teams에서 회의 ID를 다시 설정하는 자세한 내용은 Microsoft Teams에서 사용자의 회의 ID 재설정을 [참조하세요.](/MicrosoftTeams/reset-a-conference-id-for-a-user-in-teams)

동적 전화 회의 ID는 발신자에서 모임에 전화 접속하는 데 사용할 수 있는 전화 접속 전화 번호와 함께 모임 초대의 아래쪽에 포함됩니다. 사용자가 전화 번호로 전화를 걸면 모임의 자동 전화 접속자가 발신자가 이 전화 회의 ID를 입력하도록 요청하여 모임에 참석할 수 있습니다.
  
> [!NOTE]
> 회의 공급자가 Microsoft인 경우 사용자의 회의 신분은 동적 전용으로 설정됩니다. 이 변경은 변경할 수 없습니다. 전화 회의는 오디오 회의를 사용하도록 설정된 비즈니스용 Skype 사용자에 대해 자동으로 설정됩니다. 

## <a name="resetting-the-conference-id-for-a-user"></a>사용자의 회의 ID 다시 설정
   
1. 비즈니스용 **Skype** 관리 센터에서 오디오 회의 사용자를 클릭하고 사용자를 선택한 다음 회의 ID 아래의 작업   >   **창에서** 재설정을 **클릭합니다.**
    
2. 회의 **ID 재설정 창에서** **예를 클릭합니다.** 회의 ID가 자동으로 만들어지며 새 회의 ID가 있는 전자 메일이 사용자에게 전송됩니다. 기본적으로 전자 메일은 사용자에게 전송되지만 해제할 수 있습니다.
    
> [!NOTE]
> 회의 ID를 다시 설정하면 새 회의 ID가 있는 전자 메일이 사용자에게 전송됩니다. 이 전자 메일은 대부분의 경우 Microsoft 365 또는 Office 365 사서함의 기본 전자 메일 주소로 전송됩니다. 전자 메일에는 새 전화 회의 ID, 기본 전화 접속 전화 번호 및 비즈니스용 Skype 모임 업데이트 도구를 사용하여 기존 모임을 업데이트하는 지침이 포함되어 있습니다. 
  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="what-else-should-i-know"></a>알아야 할 다른 것은 무엇입니까?

- 작업 창에서 사용자의 전자 메일을 통해 전화 회의 정보 보내기를 클릭하여 전화 회의 ID 및  전화 접속 전화 번호가 포함된 전자 메일로 사용자에게 모든 회의 정보를 보낼 수 있습니다. PIN은 보내지 않습니다.
    
- 전화 회의 ID에는 7자리가 포함되어 있으며 비즈니스용 Skype 관리 센터에서 또는 전화 회의를 사용하여 길이를 변경할 수 Windows PowerShell.
    
- 다시 설정되면 회의 ID 아래에 나열된 새 회의 **ID를 볼 수 있습니다.**
    
- 사용자 페이지에서 사용자를 선택할 때 오디오 회의의 작업 창 아래쪽에서 오디오 회의에  대한 사용자의 회의 ID를 볼 **수** 있습니다.
    
- 새 전화 회의 ID가 생성되면 발신자에 의해 이전 전화 회의 ID를 사용할 수 없습니다. 새 회의 ID가 초대에 추가될 수 있도록 사용자에게 기존 모임 초대를 다시 계획할지 알려야 합니다. 사용자는 비즈니스용 Skype 모임 도구를 사용하여 기존 모임을 업데이트할 수 있습니다. 비즈니스용 Skype 모임 업데이트 도구를 다운로드, 설치 및 실행하는 방법을 참조하려면 다음을 참조하세요.
    
  - [비즈니스용 Skype 및 Lync용 모임 업데이트 도구](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4)
    
  - [비즈니스용 Skype Online, 모임 마이그레이션 도구(64비트)](https://go.microsoft.com/fwlink/?LinkID=626047)
    
  - [비즈니스용 Skype Online, 모임 마이그레이션 도구(32비트)](https://www.microsoft.com/download/details.aspx?id=54079)
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>사용자 계정으로 관리하는 방법을 알고 Windows PowerShell?

- 이 경우 Windows PowerShell 관리에 대한 모든 것 및 사용자가 허용되거나 허용되지 않는 작업을 관리하는 것입니다. 이 Windows PowerShell 여러 작업을 수행할 때 일상적인 작업을 간소화할 수 있는 단일 관리 지점을 사용하여 Microsoft 365 또는 Office 365 및 비즈니스용 Skype Online을 관리할 수 있습니다. 다음 항목을 Windows PowerShell 항목을 참조하세요.
    
  - [Windows PowerShell 및 Lync Online 소개](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Microsoft 365 또는 Office 365 PowerShell을 사용하는 이유](https://go.microsoft.com/fwlink/?LinkId=525041)
 
- Windows PowerShell Microsoft 365 관리 센터를 사용하는 경우와 같이 여러 사용자에 대해 한 번씩 설정을 변경하는 경우와 같이 속도, 단순성 및 생산성에 많은 이점이 있습니다. 다음 항목에서 이러한 이점에 대해 자세히 배워야 합니다.
    
  - [Microsoft 365 또는 Office 365를 관리하는 가장 좋은 Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [비즈니스 Windows PowerShell 사용하여 비즈니스용 Skype Online 관리](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [비즈니스용 Windows PowerShell Skype Online 관리 작업을 수행하는 데 사용할 수 있습니다.](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a>관련 항목

[오디오 회의 PIN 재설정](reset-the-audio-conferencing-pin.md)
