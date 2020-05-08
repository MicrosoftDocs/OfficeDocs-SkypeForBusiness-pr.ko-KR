---
title: 비즈니스용 Skype Online에서 오디오 회의를 사용 하도록 설정 된 사용자 목록 보기
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
description: '비즈니스용 Skype 관리 센터에서 전화 접속 회의를 사용 하도록 설정 된 조직의 사용자 목록을 보는 방법에 대해 알아봅니다. '
ms.openlocfilehash: 206bd52d1b2e0cfc1a72bb557c5d5dc4c0162534
ms.sourcegitcommit: 36f7ec432090683aedb77a5bd7856e1b10af2a81
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2020
ms.locfileid: "44163927"
---
# <a name="see-a-list-of-users-that-are-enabled-for-audio-conferencing-in-skype-for-business-online"></a>비즈니스용 Skype Online에서 오디오 회의를 사용 하도록 설정 된 사용자 목록 보기

> [!NOTE]
> Microsoft 팀에서 사용 하도록 설정 된 사용자에 대 한 자세한 내용은 [Microsoft 팀에서 오디오 회의를 사용할 수 있는 사용자 목록 보기](/MicrosoftTeams/see-a-list-of-users-that-are-enabled-for-audio-conferencing-in-teams)를 참고 하세요.

조직에서 오디오 회의에 비즈니스용 Skype 사용자를 설정한 후에는 사용 하도록 설정 된 사용자 목록을 볼 수 있습니다. 목록을 볼 때 목록에서 사용자가 사용 하는 오디오 회의 공급자 유형, 사용자의 기본 전화 접속 전화 번호, 조직에서 구성 하는 오디오 회의 모임에 대 한 정적 전화 회의 Id를 사용 하도록 설정 되어 있지 않은 경우 목록에도 표시 됩니다.

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="viewing-a-list-of-users"></a>사용자 목록 보기

   
- 왼쪽 탐색 창에서 **오디오 회의** > **사용자**로 이동 합니다.

## <a name="what-else-should-i-know"></a>알아야 할 기타 사항

- 사용 하도록 설정 된 사용자 목록을 볼 때 목록에서 사용자를 선택 하 고 작업 창을 사용 하 여 해당 사용자의 오디오 회의 설정을 편집할 수 있습니다.
    
- Microsoft를 오디오 회의 공급자로 사용 하도록 구성 된 단일 사용자를 선택 하면 기본 전화 번호와 조직에서 동적 전화 회의 Id를 사용할 수 있는지 여부를 확인 하 고 사용자가 구성한 모임에 대 한 전화 회의 ID를 다시 설정할 수 있습니다.
    
- 타사 오디오 회의 공급자를 사용 하도록 구성 된 단일 사용자를 선택 하면 오디오 회의 공급자의 이름, 유료 전화 번호 및 무료 전화 번호 (설정 된 경우)를 볼 수 있습니다.
    
- 필터 옵션을 사용 하 여 다음과 같은 사용자를 표시할 수 있습니다.
    
  - **오디오 회의**
    
  - **오디오 회의 끄기**
    
  - **회의 공급자-Microsoft**
    
  - **회의 공급자-기타**
    
- 검색 단추를 사용 하 여 목록에서 개별 사용자를 검색할 수 있습니다.
    
- 두 명 이상의 사용자를 선택 하 고 다음을 수행할 수 있습니다.
    
  - 이러한 사용자에 대해 다른 기본 번호를 선택 합니다.
    
  - 공급자를 **[없음]** 으로 변경 하 여 사용자에 대 한 오디오 회의를 해제 합니다.
    
  - 사용자에 게 **오디오** 회의 라이선스가 할당 된 경우 오디오 회의 공급자로 Microsoft로 전환 합니다.
    
  - 익명 사용자가 선택 된 사용자의 전화 모임을 활성화 하도록 허용/허용 하지 않습니다.
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Windows PowerShell을 사용 하 여 관리 하는 방법을 알고 싶으세요?

- Windows PowerShell은 사용자 및 허용 되지 않거나 수행할 수 있는 사용자를 관리 하는 방법에 대해 설명 합니다. Windows PowerShell을 사용 하면 여러 작업을 수행할 때 일상 업무를 단순화할 수 있는 단일 관리 지점을 사용 하 여 Microsoft 365 또는 Office 365 및 비즈니스용 Skype Online을 관리할 수 있습니다. Windows PowerShell을 시작 하려면 다음 항목을 참조 하세요.
    
  - [Windows PowerShell 및 Lync Online 소개](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Microsoft 365 또는 Office 365 PowerShell을 사용 해야 하는 이유](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell에는 한 번에 여러 사용자의 설정을 변경 하는 경우와 같이 Microsoft 365 관리 센터를 사용 하는 경우에만 속도, 단순성, 생산성 등 다양 한 이점이 있습니다. 다음 항목에서 이러한 이점에 대해 알아보세요.
    
  - [Windows PowerShell을 사용 하 여 Microsoft 365 또는 Office 365을 관리 하는 최상의 방법](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Windows PowerShell을 사용 하 여 비즈니스용 Skype Online 관리](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Windows PowerShell을 사용 하 여 일반적인 비즈니스용 Skype Online 관리 작업 수행](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a>관련 항목

[Microsoft 365 또는 Office 365에서 오디오 회의 체험 또는 구매](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
