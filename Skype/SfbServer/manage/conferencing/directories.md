---
title: 비즈니스용 Skype 서버에서 전화 회의렉터 만들기
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
ms.assetid: b124b229-7df5-4b7e-8c11-6661c8c8c051
description: '요약: 비즈니스용 Skype 서버에서 전화 회의를 만드는 방법을 설명하는 문서입니다.'
ms.openlocfilehash: 6a7b8d110f06b089f166fc6ff2eb35ae35632370
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828138"
---
# <a name="create-conference-directories-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서 전화 회의렉터 만들기
 
**요약:** 비즈니스용 Skype 서버에서 전화 회의를 만드는 방법을 배워야 합니다.
  
전화 회의는 참가자가 비즈니스용 Skype를 사용할 때 전화 회의에 참가하는 데 사용하는 영수 모임 ID와 전화 접속 회의 참가자가 전화 회의에 참가하는 데 사용하는 숫자 전용 회의 ID 간의 매핑을 유지 관리합니다. 
  
## <a name="create-a-conference-directory"></a>회의 디렉터리 만들기

전화 회의 디렉터리를 여러 개 만들면 상당히 많은 수의 전화 회의가 만들어질 때까지 전화 회의 ID가 짧게 유지될 수 있습니다. 
  
전화 회의 ID를 약 6자리로 유지하려면 사용자당 전화 회의 수가 보편적인 조직의 경우 풀의 사용자 999명당 하나의 전화 회의 디렉터리를 만드는 것이 좋습니다. 이 지침에 따라 일반적으로 회의 ID는 작게 유지될 수 있습니다. 그러나 풀 전체의 전화 회의 센터 수가 9를 초과하면 추가 전화 회의를 지원하기 위해 전화 회의 ID 길이가 늘어나게 됩니다.
  
회의 ID 형식은 다음과 같습니다. 
  
```console
  <housekeeping digit (1 digit)><conference directory (usually 1-2 digits> 
  <conference number (variable number of digits><check digit (1 digit)>
```

회의 디렉터리를 만들 경우 **New-CsConferenceDirectory** cmdlet을 사용 합니다. 예를 들어 다음 명령은 ID가 42인 전화 회의 디렉터리를 만듭니다. 이 디렉터리는 풀에서 atl-cs-001.litwareinc.com.
  
```PowerShell
New-CsConferenceDirectory -Identity 42 -HomePool "atl-cs-001.litwareinc.com"
```

자세한 내용은 [New-CsConferenceDirectory를 참조하십시오.](https://docs.microsoft.com/powershell/module/skype/new-csconferencedirectory?view=skype-ps)
  

