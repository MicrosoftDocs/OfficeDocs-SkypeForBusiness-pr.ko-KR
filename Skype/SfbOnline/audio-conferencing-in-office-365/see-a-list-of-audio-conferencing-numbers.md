---
title: 비즈니스용 Skype Online에서 오디오 회의 번호 목록 보기
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 2d6b4ed4-e12b-4691-8405-fae720d69425
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
description: '비즈니스용 Skype Online 내에서 전화 접속 회의 번호를 검색하는 방법을 배워야 합니다. '
ms.openlocfilehash: 48cca375f2039a1cebbd07100a8bcd8d275f55f0
ms.sourcegitcommit: 36f7ec432090683aedb77a5bd7856e1b10af2a81
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2020
ms.locfileid: "44164687"
---
# <a name="see-a-list-of-audio-conferencing-numbers-in-skype-for-business-online"></a>비즈니스용 Skype Online에서 오디오 회의 번호 목록 보기

> [!NOTE]
> Microsoft Teams의 오디오 회의 번호에 대한 자세한 내용은 Microsoft Teams의 오디오 회의 번호 목록을 [참조하세요.](/MicrosoftTeams/see-a-list-of-audio-conferencing-numbers-in-teams)

비즈니스용 Skype 사용자에 대한 오디오 회의를 설정할 때 오디오 회의에 사용할 수 있는 전화 번호를 볼 수 있습니다. 이 목록에는 조직에서 사용할 수 있는 모든 오디오 회의 전화 번호가 있습니다.
  
 **가격을 찾고 있나요?** 오디오 회의에 대한 가격 [책정을 참조합니다.](https://products.office.com/skype-for-business/audio-conferencing#Requirements)
  
> [!IMPORTANT]
> **오디오 회의에 대한 모든 전화 접속 번호 목록을 포함하는 리소스는 없습니다.** 해당 지역 또는 국가/지역에서 사용할 수 있는 전화 접속 전화 번호가 있는 경우 **비즈니스용 Skype** 관리 센터 음성 전화 번호로 이동하여 추가를 클릭한 다음 새 서비스 번호를  >    >   **클릭합니다.**  **국가/지역**, **시/지역** 및 **도시** 목록을 사용하여 검색을 필터링합니다. 또한 무료 서비스 번호를 찾고 있는 경우 **주/지역** 목록에서 무료 서비스를 선택합니다. 
  
조직에서 사용할 수 있는 전화 번호가 하나뿐인 경우 모든 사용자의 기본 번호로 사용됩니다. 여러 전화 번호를 사용할 수 있는 경우 각 사용자의 기본 전화 번호를 선택할 수 있습니다. 이 기본 번호는 비즈니스용 Skype 모임 초대에 포함됩니다.
  
초대에 [](set-the-phone-numbers-included-on-invites.md) 포함된 전화 번호를 설정하여 단일 사용자의 전화 접속 전화 번호를 변경할 수 있습니다.
  
> [!NOTE]
> 국내 전화 접속 번호는 조직 전용으로, 기본 전화 번호로 설정할 수 있는 유일한 전화 번호입니다. 그러나 국제 전화 접속 번호는 여러 조직에서 공유할 수 있습니다. 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="to-view-your-audio-conferencing-phone-numbers"></a>오디오 회의 전화 번호를 확인

1. 직장 또는 학교 계정으로 로그인합니다.
    
2. 비즈니스용 Skype의 > **관리 센터로 이동하세요.**
    
3. 비즈니스용 Skype 관리 **센터의** 왼쪽 탐색 모음에서 **오디오** 회의 Microsoft 브리지로 이동한  >  다음,
    
   - 오디오 회의에 사용할 수 있는 전화 번호를 볼 수 있습니다.
    
   - 오디오 회의 자동 연결에서 사용할 위치 및 기본 및 보조 언어를 볼 수도 있습니다.
    
> [!NOTE]
> 오디오 회의 사용자로 이동하여 사용자의 속성을 선택하여 조직의 사용 가능한 번호 목록에서 새 번호를 선택하여 기본 번호를 변경할  >   수 있습니다. 초대에 [포함된 전화 번호](set-the-phone-numbers-included-on-invites.md)설정 참조 

  
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>사용자 계정으로 관리하는 방법을 알고 Windows PowerShell?

- 시간을 절약하거나 이 작업을 자동화하기 위해 [Get-CsOnlineDialInConferencingServiceNumber](https://go.microsoft.com/fwlink/?LinkId=617691) cmdlet을 사용할 수 있습니다.
    
- Windows PowerShell 관리는 사용자 및 사용자가 허용되거나 허용되지 않는 작업을 관리하는 것입니다. 이 Windows PowerShell 여러 작업을 수행할 때 일상적인 작업을 간소화할 수 있는 단일 관리 지점을 사용하여 Microsoft 365 또는 Office 365를 관리할 수 있습니다. 다음 항목을 Windows PowerShell 항목을 참조하세요.
    
  - [Microsoft 365 또는 Office 365 PowerShell을 사용하는 이유](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Microsoft 365 또는 Office 365를 관리하는 가장 좋은 Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell Microsoft 365 관리 센터를 사용하는 것 이상으로 속도, 단순성 및 생산성에 많은 이점이 있습니다. 예를 들어 한 번으로 많은 사용자를 위한 설정을 변경할 때도 있습니다. 다음 항목에서 이러한 이점에 대해 자세히 배워야 합니다.
    
  - [Windows PowerShell 및 Lync Online 소개](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [비즈니스 Windows PowerShell 사용하여 비즈니스용 Skype Online 관리](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [비즈니스용 Windows PowerShell Skype Online 관리 작업을 수행하는 데 사용할 수 있습니다.](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > 비즈니스 Windows PowerShell용 Skype Online 모듈을 사용하면 비즈니스용 Skype Online에 Windows PowerShell 원격 세션을 만들 수 있습니다. 64비트 컴퓨터에서만 지원되는 이 모듈은 비즈니스용 [Skype Online용](https://go.microsoft.com/fwlink/?LinkId=294688) Windows PowerShell 모듈의 Microsoft 다운로드 센터에서 다운로드할 수 있습니다.
  
## <a name="related-topics"></a>관련 항목

[Microsoft 365 또는 Office 365에서 오디오 회의 시도 또는 구매](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
  
