---
title: 비즈니스용 Skype 서버에서 회의 정책 할당
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
ms.assetid: f384d19b-0950-4ec6-9d93-2c5958b83e71
description: '요약: 비즈니스용 Skype 서버에서 회의 정책을 할당하는 방법을 설명하는 정보를 제공합니다.'
ms.openlocfilehash: 61082a9189b085c852e7593207fc86dcc6509139
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51099164"
---
# <a name="assign-conferencing-policies-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서 회의 정책 할당
 
**요약:** 비즈니스용 Skype 서버에서 회의 정책을 할당하는 방법을 배워야 합니다.
  
비즈니스용 Skype 서버 관리 셸 및 **Grant-CsConferencingPolicy** cmdlet을 사용하여 사용자에게 회의 정책을 할당할 수 있습니다.
  
## <a name="assign-conferencing-policies-by-using-skype-for-business-server-management-shell"></a>비즈니스용 Skype 서버 관리 셸을 사용하여 회의 정책 할당

다음 예제에서는 ID가 "Ken Myer"인 사용자에게 SalesConferencingPolicy 정책이 할당됩니다.
  
```PowerShell
Grant-CsConferencingPolicy -identity "Ken Myer" -PolicyName SalesConferencingPolicy
```

다음 예제에서는 Finance 조직 구성 단위에 계정이 있는 모든 사용자에게 회의 정책 FinanceConferencingPolicy가 할당됩니다. 지정된 OU(조직 구성 단위)의 모든 사용자에게 동일한 정책을 할당하기 위해 Get-CsUser cmdlet을 사용하여 해당 OU의 모든 계정을 검색합니다. 사용자 계정을 검색한 후 해당 정보는 컬렉션의 각 사용자에게 FinanceConferencingPolicy 정책을 할당하는 Grant-CsConferencingPolicy cmdlet에 파이프됩니다.
  
```PowerShell
Get-CsUser -OU "ou=Finance,dc=litwareinc,dc=com" | Grant-CsConferencingPolicy -PolicyName FinanceConferencingPolicy
```

전체 구문과 매개 변수 목록을 비롯한 자세한 내용은 [Grant-CsConferencingPolicy를 참조하십시오.](/powershell/module/skype/grant-csconferencingpolicy?view=skype-ps)
