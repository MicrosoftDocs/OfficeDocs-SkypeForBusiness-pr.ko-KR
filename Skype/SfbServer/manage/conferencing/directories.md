---
title: 비즈니스용 Skype 서버에서 전화 회의 디렉터리 만들기
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b124b229-7df5-4b7e-8c11-6661c8c8c051
description: '요약: 비즈니스용 Skype 서버에서 전화 회의 디렉터리를 만드는 방법에 대해 알아보세요.'
ms.openlocfilehash: d2962e7e01ba5bb73ce82de9b5c0ff85550fbe99
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36197715"
---
# <a name="create-conference-directories-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서 전화 회의 디렉터리 만들기
 
**요약:** 비즈니스용 Skype 서버에서 전화 회의 디렉터리를 만드는 방법에 대해 알아봅니다.
  
회의 디렉터리는 비즈니스용 Skype를 사용할 때 참가자가 전화 회의에 참가 하는 데 사용 하는 영숫자 모임 ID와 전화 접속 회의 참가자가 회의에 참가 하는 데 사용 하는 숫자 전용 회의 ID 간의 매핑을 유지 합니다. 
  
## <a name="create-a-conference-directory"></a>회의 디렉터리 만들기

여러 회의 디렉터리를 만들면 회의 Id가 매우 많은 회의를 만들 때까지 짧은 시간 동안 유지 되도록 할 수 있습니다. 
  
사용자 당 일반적인 회의 수가 있는 조직에서 풀의 모든 999 사용자에 대해 하나의 회의 디렉터리를 만드는 것이 좋습니다. 이 지침을 사용 하 여 회의 Id를 일반적으로 작게 유지할 수 있습니다. 그러나, 풀 전체의 회의 디렉터리 수가 9 개를 초과 하면 추가 회의를 지원 하기 위해 회의 ID 길이가 늘어납니다.
  
전화 회의 ID의 형식은 다음과 같습니다. 
  
```
  <housekeeping digit (1 digit)><conference directory (usually 1-2 digits> 
  <conference number (variable number of digits><check digit (1 digit)>
```

컨퍼런스 디렉터리를 만들려면 **CsConferenceDirectory** cmdlet을 사용 합니다. 예를 들어 다음 명령은 id 42를 사용 하 여 풀 atl-cs-001.litwareinc.com에서 호스트 되는 컨퍼런스 디렉터리를 만듭니다.
  
```
New-CsConferenceDirectory -Identity 42 -HomePool "atl-cs-001.litwareinc.com"
```

자세한 내용은 [New-CsConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/new-csconferencedirectory?view=skype-ps)를 참조 하세요.
  

