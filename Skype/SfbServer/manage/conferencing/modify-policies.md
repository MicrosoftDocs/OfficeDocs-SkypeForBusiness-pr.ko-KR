---
title: 비즈니스용 Skype 서버에서 회의 정책 수정
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b40ba905-e74a-4456-ac94-65471bc2d66d
description: '요약: 비즈니스용 Skype 서버에서 회의 정책을 수정 하는 방법에 대해 알아봅니다.'
ms.openlocfilehash: 9cfb13436a01439a8d5ea152ca1d8ac543bc0e88
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991813"
---
# <a name="modify-conferencing-policies-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서 회의 정책 수정
 
**요약:** 비즈니스용 Skype 서버에서 회의 정책을 수정 하는 방법에 대해 알아봅니다.
  
Skype for Business Server 제어판을 사용 하거나 비즈니스용 Skype 서버 관리 셸을 사용 하 여 회의 정책을 수정할 수 있습니다.
  
## <a name="modify-conferencing-policies-by-using-skype-for-business-server-control-panel"></a>비즈니스용 Skype Server 제어판을 사용 하 여 회의 정책 수정

1. CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당 된 사용자 계정에서 내부 배포의 컴퓨터에 로그온 합니다.
    
2.  비즈니스용 Skype Server 제어판을 엽니다.
    
3. 왼쪽 탐색 모음에서 **회의**를 클릭 한 다음 **회의 정책을**클릭 합니다.
    
4. 회의 정책 목록에서 변경 하려는 정책을 클릭 하 고 **편집**을 클릭 한 다음 **세부 정보 표시**를 클릭 합니다.
    
5. **회의 편집 정책**에서 수정할 수 없는 정책 이름을 제외한 모든 정책 설정을 수정 합니다.
    
6. **커밋**을 클릭합니다.
    
## <a name="modify-conferencing-policies-by-using-skype-for-business-server-management-shell"></a>비즈니스용 Skype Server Management Shell을 사용 하 여 회의 정책 수정

회의 정책을 수정 하려면 **Set-CsConferencingPolicy** cmdlet을 사용 합니다.
  
다음 예제에서는 회의 정책 SalesConferencingPolicy의 속성 값을 수정 합니다. 명령에서 AllowConferenceRecording 속성 값을 False로 설정 합니다.
  
```PowerShell
Set-CsConferencingPolicy -Identity SalesConferencingPolicy -AllowConferenceRecording $False
```

전체 구문 및 매개 변수 목록을 비롯 한 자세한 내용은 [Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps)를 참조 하세요.
  

