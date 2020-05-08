---
title: 비즈니스용 Skype Online에서 오디오 회의를 위한 자동 전화 교환 언어 설정
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 26d73dda-ab26-4af4-8aec-d17f3479ae50
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
description: 비즈니스용 Skype Online에서 오디오 회의 번호에 대 한 오디오 회의 자동 전화 교환 언어를 선택 하는 방법에 대해 알아봅니다.
ms.openlocfilehash: 93b6ea917c7f79747273366893efc47a22b89bb2
ms.sourcegitcommit: 36f7ec432090683aedb77a5bd7856e1b10af2a81
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2020
ms.locfileid: "44163909"
---
# <a name="set-auto-attendant-languages-for-audio-conferencing-in-skype-for-business-online"></a>비즈니스용 Skype Online에서 오디오 회의를 위한 자동 전화 교환 언어 설정

> [!Note]
> Microsoft 팀에서 자동 전화 교환 언어를 설정 하는 방법에 대 한 자세한 내용은 [Microsoft 팀에서 오디오 회의를 위한 자동 전화 교환 언어](/MicrosoftTeams/set-auto-attendant-languages-for-audio-conferencing-in-teams)설정을 참조 하세요.

비즈니스용 Skype의 오디오 회의 자동 전화 교환은 모임에 참가할 때 다양 한 언어로 오디오 발신자를 인사 합니다.
  
하나의 기본 언어와 최대 4 개의 보조 언어를 선택 합니다. 설정한 기본 언어가 먼저 사용 되며, 선택 하는 대로 보조 언어가 자동 전화 교환에 사용 됩니다. 
  
> [!NOTE]
>  전용 범주에 해당 하는 오디오 회의 번호의 언어만 변경할 수 있습니다. 공유 오디오 회의 번호의 언어는 변경할 수 없습니다.

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="set-the-conferencing-auto-attendant-languages"></a>회의 자동 전화 교환 언어 설정

이 단계를 수행 하려면 [전역 관리자](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) 또는 [비즈니스용 Skype 관리자](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) 여야 합니다.
    
1. **비즈니스용 Skype 관리 센터**의 왼쪽 탐색에서 **레거시 포털로**이동 합니다. 레거시 포털에서 **오디오 회의**를 선택한 다음 **Microsoft bridge**를 클릭 합니다.
    
2. 목록에서 오디오 회의 전화 번호를 선택 하 고 작업 창에서 **언어 설정을**클릭 합니다. 전용 오디오 회의 번호의 언어만 변경할 수 있습니다.  
    
3. **언어 설정** 페이지에서 **기본 언어** 목록을 클릭 하 여 사용 가능한 언어의 전체 목록을 봅니다. 필요한 경우 각 **보조 언어** 목록을 클릭 하 여 보조 언어를 선택 합니다.
    
    > [!NOTE]
    > 지원 되는 기본 및 보조 언어가 나열 됩니다. 목록에서 해당 항목을 선택 하는 순서는 호출자에 게 표시 되는 언어의 순서입니다. 
  
4. **저장**을 클릭합니다.
    
## <a name="want-else-should-i-know"></a>기타 알아야 할 것

- 오디오 회의에 지원 되는 언어 목록을 보려면 [오디오 회의 지원 언어](/MicrosoftTeams/audio-conferencing-supported-languages)를 참조 하세요.
    
- 공유 전화 번호에 대해서만 언어를 설정할 수 있습니다.
    
- Microsoft에서 제공 하는 공급자를 사용 하는 Office 365 365의 오디오 회의를 사용할 수 있는 국가/지역 목록을 보려면 [오디오 회의의 전화 번호](phone-numbers-for-audio-conferencing.md)를 참조 하세요.
    
## <a name="want-to-use-windows-powershell"></a>Windows PowerShell을 사용 하 고 싶으신가요?

이 단계를 자동화 하기 위해 [CsOnlineDialInConferencingServiceNumber](https://go.microsoft.com/fwlink/?LinkId=617689) 및 [Get-CsOnlineDialInConferencingLanguagesSupported](https://go.microsoft.com/fwlink/?LinkId=617684) cmdlet을 사용할 수 있습니다.
  
자세히 알아보려면 [Windows PowerShell을 사용 하 여 일반적인 비즈니스용 Skype Online 관리 작업](https://go.microsoft.com/fwlink/?LinkId=525038) 을 참조 하세요.
  
## <a name="related-topics"></a>관련 항목

[Microsoft 365 또는 Office 365에서 오디오 회의 체험 또는 구매](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
