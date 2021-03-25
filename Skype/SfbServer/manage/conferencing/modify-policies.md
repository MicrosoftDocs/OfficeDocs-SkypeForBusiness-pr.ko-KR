---
title: 비즈니스용 Skype 서버에서 회의 정책 수정
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b40ba905-e74a-4456-ac94-65471bc2d66d
description: '요약: 비즈니스용 Skype 서버에서 회의 정책을 수정하는 방법을 설명하는 정보를 제공합니다.'
ms.openlocfilehash: 6bbba82c9785e074da492eb66cbdd943dc0cea35
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119427"
---
# <a name="modify-conferencing-policies-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서 회의 정책 수정
 
**요약:** 비즈니스용 Skype 서버에서 회의 정책을 수정하는 방법에 대해 자세히 알아보습니다.
  
비즈니스용 Skype 서버 제어판 또는 비즈니스용 Skype 서버 관리 셸을 사용하여 회의 정책을 수정할 수 있습니다.
  
## <a name="modify-conferencing-policies-by-using-skype-for-business-server-control-panel"></a>비즈니스용 Skype 서버 제어판을 사용하여 회의 정책 수정

1. CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.
    
2.  비즈니스용 Skype 서버 제어판을 니다.
    
3. 왼쪽 탐색 모음에서 회의 를 클릭한 다음 회의 정책을 **클릭합니다.**
    
4. 회의 정책 목록에서 변경할 정책을 클릭하고 **편집** 을 클릭한 다음 **자세한 정보 표시** 를 클릭합니다.
    
5. **회의 정책 편집** 에서 수정이 불가능한 정책 이름을 제외한 정책 설정을 수정합니다.
    
6. **커밋** 을 클릭합니다.
    
## <a name="modify-conferencing-policies-by-using-skype-for-business-server-management-shell"></a>비즈니스용 Skype 서버 관리 셸을 사용하여 회의 정책 수정

회의 정책을 수정하려면 **Set-CsConferencingPolicy** cmdlet을 사용 합니다.
  
다음 예에서는 회의 정책 SalesConferencingPolicy의 속성 값을 수정합니다. 이 명령은 AllowConferenceRecording 속성 값을 False로 설정합니다.
  
```PowerShell
Set-CsConferencingPolicy -Identity SalesConferencingPolicy -AllowConferenceRecording $False
```

전체 구문과 매개 변수 목록을 비롯한 자세한 내용은 [Set-CsConferencingPolicy 를 참조하십시오.](/powershell/module/skype/set-csconferencingpolicy?view=skype-ps)
