---
title: 사용자의 전화 회의 ID 보기, 변경, 다시 설정
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
- seo-marvel-mar2020
description: Microsoft 팀에서 사용자에 게 전화 회의 ID를 할당 하는 방법 및 회의 id 매개 변수를 지정 하는 방법을 알아봅니다.
ms.openlocfilehash: 7c4b9614843f353438630892574c25576913d24b
ms.sourcegitcommit: cddaacf1e8dbcdfd3f94deee7057c89cee0e5699
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/03/2020
ms.locfileid: "43140941"
---
# <a name="view-and-reset-a-conference-id-assigned-to-a-user-in-microsoft-teams"></a>Microsoft 팀에서 사용자에 게 할당 된 회의 ID 보기 및 다시 설정

전화 회의 ID가 Office 365에서 오디오 회의를 위해 설정 되 고 Microsoft를 오디오 회의 공급자로 사용 하는 경우 Microsoft 팀 사용자에 게 자동으로 할당 됩니다. 모임이 예정 되 면 모임 초대에 할당 된 전화 회의 ID가 전송 됩니다. 사용자가 예약 하는 각 모임에는 고유한 전화 번호를 할당 받게 됩니다. 
  
전화 회의 ID는 사용자에 게 자동으로 만들어지고 할당 되지만, 사용자가이를 사용 하지 않고 특정 번호로 설정 하려는 경우 또는 사용자가 자신의 전화 회의 ID를 분실 하거나 손실 하지 않았을 때가 있을 수 있습니다. Microsoft 팀 관리 센터 또는 Windows PowerShell을 사용 하 여 전화 회의 ID를 보고 변경 하 고 다시 설정할 수 있습니다.
  
전화 회의 ID와 기본 오디오 회의 전화 번호로 사용자에 게 전자 메일이 전송 되거나, 전화 회의 id를 다시 설정 하는 경우에는 전화 회의 ID만 포함 하 고 PIN이 아닌 다른 전자 메일을 보낼 수 있습니다. 회의 이끌이의 PIN을 다시 설정 하는 방법에 대 한 자세한 내용은 [여기](reset-a-conference-id-for-a-user-in-teams.md)를 참조 하세요. 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="view-and-reset-conference-ids"></a>회의 Id 보기 및 재설정

### <a name="to-view-the-conference-id"></a>전화 회의 ID를 보려면

![Microsoft Teams 로고를 나타내는 아이콘](media/teams-logo-30x30.png) **Microsoft Teams 관리 센터 사용**

1. 왼쪽 탐색 창에서 **사용자**를 클릭 한 다음 사용 가능한 사용자 목록에서 사용자를 선택 합니다.

2. 페이지 맨 위에서 **편집**을 클릭 합니다.

3. **오디오 회의**에서 **전화 회의 ID**를 확인 합니다.

    > [!TIP]
    > **전자 메일로 회의 정보 보내기** 링크를 클릭 하 여 전화 회의 ID 및 오디오 전화 번호가 포함 된 전자 메일로 모든 회의 정보를 사용자에 게 보낼 수 있습니다.
  
**Windows PowerShell 사용**

자세한 내용은 [Microsoft 팀 PowerShell 참조](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) 를 참조 하세요.
    
  
### <a name="to-reset-the-conference-id"></a>전화 회의 ID를 다시 설정 하려면

예를 들어 사용자가 잊어버린 경우 전화 회의 ID를 다시 설정할 수 있습니다.
  
![Microsoft Teams 로고를 나타내는 아이콘](media/teams-logo-30x30.png) **Microsoft Teams 관리 센터 사용**

1. 왼쪽 탐색 창에서 **사용자**를 클릭 한 다음 사용 가능한 사용자 목록에서 사용자를 선택 합니다.

2. 페이지 맨 위에서 **편집**을 클릭 합니다.

3. **오디오 회의**에서 **전화 회의 ID 재설정**을 클릭 합니다.

4. **전화 회의 ID 다시 설정** 창에서 **원래 대로**를 클릭 합니다. 전화 회의 ID가 자동으로 만들어지고 새 전화 회의 ID를 사용 하 여 사용자에 게 전자 메일이 전송 됩니다.
  
**Windows PowerShell 사용**

자세한 내용은 [Microsoft 팀 PowerShell 참조](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) 를 참조 하세요.


## <a name="what-else-should-you-know"></a>알아야 할 기타 사항

   > [!IMPORTANT]
   >  새 전화 회의 ID가 만들어지거나 하나는 다시 설정 된 후에는 발신자가 이전 전화 회의 ID를 사용할 수 없습니다. 사용자에 게 기존 모임 초대를 다시 예약 하 여 새 회의 ID가 초대에 추가 되었는지 알려 주어 야 합니다. 
  
    
- 전화 회의 ID는 오디오 회의 브리지에 설정 된 길이의 자릿수를 충족 해야 합니다. 전화 회의 Id에는 영문자 또는 특수 문자를 사용할 수 없습니다. 숫자만 사용할 수 있습니다.
   
    
## <a name="want-to-know-more-about-windows-powershell"></a>Windows PowerShell에 대 한 자세한 정보를 확인 하 고 싶으신가요?

Windows PowerShell은 사용자 및 허용 되지 않거나 수행할 수 있는 사용자를 관리 하는 방법에 대해 설명 합니다. Windows PowerShell을 사용 하면 여러 작업을 수행할 때 일상 업무를 단순화할 수 있는 단일 관리 지점을 사용 하 여 Office 365를 관리할 수 있습니다. Windows PowerShell을 시작 하려면 다음 항목을 참조 하세요.
    
  - [Office 365 PowerShell을 사용 해야 하는 이유](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Windows PowerShell을 사용 하 여 Office 365를 관리 하는 가장 좋은 방법](https://go.microsoft.com/fwlink/?LinkId=525142)
    
Windows PowerShell에 대 한 자세한 내용은 [Microsoft 팀 PowerShell 참조](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) 에서 자세한 내용을 참조 하세요.
    
## <a name="related-topics"></a>관련 항목

[Office 365에서 오디오 회의 체험 또는 구매](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)

