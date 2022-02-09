---
title: 2013에서 회의 정책 비즈니스용 Skype 서버
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: f384d19b-0950-4ec6-9d93-2c5958b83e71
description: '요약: 2013에서 회의 정책을 할당하는 비즈니스용 Skype 서버.'
ms.openlocfilehash: fe8483abe2a581668b5f5463f588b051e40c7771
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62399742"
---
# <a name="assign-conferencing-policies-in-skype-for-business-server"></a>2013에서 회의 정책 비즈니스용 Skype 서버
 
**요약:** 2013에서 회의 정책을 할당하는 비즈니스용 Skype 서버.
  
관리 셸 및 **Grant-CsConferencingPolicy** cmdlet을 사용하여 비즈니스용 Skype 서버 정책을 사용자에게 할당할 수 있습니다.
  
## <a name="assign-conferencing-policies-by-using-skype-for-business-server-management-shell"></a>비즈니스용 Skype 서버 관리 셸을 사용하여 회의 정책 할당

다음 예제에서는 ID가 "Ken Myer"인 사용자에게 SalesConferencingPolicy 정책이 할당됩니다.
  
```PowerShell
Grant-CsConferencingPolicy -identity "Ken Myer" -PolicyName SalesConferencingPolicy
```

다음 예제에서는 Finance 조직 구성 단위에 계정이 있는 모든 사용자에게 회의 정책 FinanceConferencingPolicy가 할당됩니다. 지정된 OU(조직 구성 단위)의 모든 사용자에게 동일한 정책을 할당하기 위해 Get-CsUser cmdlet을 사용하여 해당 OU의 모든 계정을 검색합니다. 사용자 계정을 검색한 후 해당 정보는 컬렉션의 각 사용자에게 FinanceConferencingPolicy 정책을 할당하는 Grant-CsConferencingPolicy cmdlet에 파이프됩니다.
  
```PowerShell
Get-CsUser -OU "ou=Finance,dc=litwareinc,dc=com" | Grant-CsConferencingPolicy -PolicyName FinanceConferencingPolicy
```

전체 구문과 매개 변수 목록을 비롯한 자세한 내용은 [Grant-CsConferencingPolicy를 참조하십시오](/powershell/module/skype/grant-csconferencingpolicy?view=skype-ps).
