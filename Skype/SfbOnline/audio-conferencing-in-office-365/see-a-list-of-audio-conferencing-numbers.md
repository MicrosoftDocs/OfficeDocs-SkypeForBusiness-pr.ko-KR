---
title: 비즈니스용 Skype Online의 오디오 회의 번호 목록 보기
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
description: '비즈니스용 Skype Online에서 전화 접속 회의 번호를 찾는 방법을 알아보세요. '
ms.openlocfilehash: 6c9c9633f99edf42c3016b90f3b52c6c4c54b0d6
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42011021"
---
# <a name="see-a-list-of-audio-conferencing-numbers-in-skype-for-business-online"></a>비즈니스용 Skype Online의 오디오 회의 번호 목록 보기

> [!NOTE]
> Microsoft 팀의 오디오 회의 번호에 대 한 자세한 내용은 [Microsoft 팀의 오디오 회의 번호 목록을](/MicrosoftTeams/see-a-list-of-audio-conferencing-numbers-in-teams)참조 하세요.

비즈니스용 Skype 사용자를 위해 오디오 회의를 설정할 때 오디오 회의에 사용할 수 있는 전화 번호를 볼 수 있습니다. 이 목록에는 조직에서 사용할 수 있는 모든 오디오 회의 전화 번호가 포함 됩니다.
  
 **가격을 찾으십니까?** [오디오 회의에 대 한 가격 산정을](https://products.office.com/skype-for-business/audio-conferencing#Requirements)참조 하세요.
  
> [!IMPORTANT]
> **오디오 회의에 대 한 모든 전화 접속 번호 목록이 포함 된 리소스가 없습니다.** 해당 지역 또는 국가/지역에서 전화 접속 전화 번호를 사용할 수 있는지 확인 하려면 **비즈니스용 Skype 관리 센터** > **음성** > **전화 번호로**이동 하 고 **추가**를 클릭 한 다음 **새 서비스 번호**를 클릭 합니다. **국가/지역**, **시/지역**, **구/군/시** 목록을 사용 하 여 검색을 필터링 합니다. 또한 무료 서비스 번호를 찾고 있는 경우에는 **상태/지역** 목록에서 무료 **통화** 를 선택 합니다.
  
조직에서 사용할 수 있는 전화 번호가 하나뿐인 경우 모든 사용자의 기본 번호로 사용 됩니다. 여러 개의 전화 번호를 사용할 수 있는 경우 각 사용자의 기본 전화 번호를 선택할 수 있습니다. 이 기본 번호는 비즈니스용 Skype 모임 초대에 포함 됩니다.
  
[초대에 포함 된 전화 번호를 설정](set-the-phone-numbers-included-on-invites.md) 하 여 단일 사용자의 전화 접속 전화 번호를 변경 하는 방법을 알아봅니다.
  
> [!NOTE]
> 국내 전화 접속 번호는 조직 전용 이므로 기본 전화 번호로 설정할 수 있습니다. 그러나 국제 전화 접속 번호는 여러 조직에서 공유 될 수 있습니다. 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="to-view-your-audio-conferencing-phone-numbers"></a>오디오 회의 전화 번호를 보려면

1. 회사 또는 학교 계정으로 Office 365에 로그인 합니다.
    
2. **비즈니스용 Skype**> 관리 센터로 이동 합니다.
    
3. **비즈니스용 Skype 관리 센터**의 왼쪽 탐색 창에서 **오디오 회의** > **Microsoft bridge**로 이동한 후 다음을 수행 합니다.
    
   - 오디오 회의에 사용할 수 있는 전화 번호를 볼 수 있습니다.
    
   - 오디오 회의 자동 전화 교환에 사용 될 위치 및 기본 및 보조 언어만 볼 수도 있습니다.
    
> [!NOTE]
> 조직의 사용 가능한 번호 목록에서 새 번호를 선택 하 여 **오디오 회의** > **사용자** 로 이동 하 고 사용자의 속성을 선택 하 여 기본 번호를 변경할 수 있습니다. [초대에 포함 된 전화 번호 설정을](set-the-phone-numbers-included-on-invites.md)참조 하세요. 

  
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Windows PowerShell을 사용 하 여 관리 하는 방법을 알고 싶으세요?

- 시간을 절약 하거나이를 자동화 하려면 [CsOnlineDialInConferencingServiceNumber](https://go.microsoft.com/fwlink/?LinkId=617691) cmdlet을 사용 하면 됩니다.
    
- Windows PowerShell은 사용자 및 허용 되지 않거나 수행할 수 있는 사용자를 관리 하는 방법에 대해 설명 합니다. Windows PowerShell을 사용 하면 여러 작업을 수행할 때 일상 업무를 단순화할 수 있는 단일 관리 지점을 사용 하 여 Office 365를 관리할 수 있습니다. Windows PowerShell을 시작 하려면 다음 항목을 참조 하세요.
    
  - [Office 365 PowerShell을 사용 해야 하는 이유](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Windows PowerShell을 사용 하 여 Office 365를 관리 하는 가장 좋은 방법](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell에는 한 번에 여러 사용자의 설정을 변경 하는 경우와 같이 Microsoft 365 관리 센터를 사용 하는 경우에만 속도, 단순성, 생산성 등 다양 한 이점이 있습니다. 다음 항목에서 이러한 이점에 대해 알아보세요.
    
  - [Windows PowerShell 및 Lync Online 소개](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Windows PowerShell을 사용 하 여 비즈니스용 Skype Online 관리](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Windows PowerShell을 사용 하 여 일반적인 비즈니스용 Skype Online 관리 작업 수행](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > 비즈니스용 Skype Online 용 Windows PowerShell 모듈을 사용 하면 비즈니스용 Skype Online에 연결 하는 원격 Windows PowerShell 세션을 만들 수 있습니다. 이 모듈은 64 비트 컴퓨터 에서만 지원 되며 비즈니스용 [Skype Online 용 Windows PowerShell 모듈](https://go.microsoft.com/fwlink/?LinkId=294688) 의 Microsoft 다운로드 센터에서 다운로드할 수 있습니다.
  
## <a name="related-topics"></a>관련 항목

[Office 365에서 오디오 회의 체험 또는 구매](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
  
