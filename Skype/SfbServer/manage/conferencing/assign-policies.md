---
title: 비즈니스용 Skype 서버에서 회의 정책 지정
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: f384d19b-0950-4ec6-9d93-2c5958b83e71
description: '요약: 비즈니스용 Skype 서버에서 회의 정책을 할당 하는 방법에 대해 알아보세요.'
ms.openlocfilehash: c5dfb9c2aa186bf199a066c82e3687aade564905
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818660"
---
# <a name="assign-conferencing-policies-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서 회의 정책 지정
 
**요약:** 비즈니스용 Skype 서버에서 회의 정책을 할당 하는 방법에 대해 알아봅니다.
  
비즈니스용 Skype Server Management Shell 및 **CsConferencingPolicy** cmdlet을 사용 하 여 사용자에 게 회의 정책을 할당할 수 있습니다.
  
## <a name="assign-conferencing-policies-by-using-skype-for-business-server-management-shell"></a>비즈니스용 Skype Server Management Shell을 사용 하 여 회의 정책 지정

다음 예제에서는 ": 진구 Myer" Id를 사용 하 여 정책 SalesConferencingPolicy 사용자에 게 할당 됩니다.
  
```PowerShell
Grant-CsConferencingPolicy -identity "Ken Myer" -PolicyName SalesConferencingPolicy
```

다음 예제에서는 회의 정책 FinanceConferencingPolicy 재무 조직 단위에 계정이 있는 모든 사용자에 게 할당 됩니다. 지정 된 OU (조직 구성 단위)의 모든 사용자에 게 동일한 정책을 할당 하려면 Get-CsUser cmdlet을 사용 하 여 해당 OU의 모든 계정을 검색 합니다. 사용자 계정이 검색 된 후에는 해당 정보를 CsConferencingPolicy cmdlet에 파이프 하 여 컬렉션의 각 사용자에 게 FinanceConferencingPolicy 정책을 할당 합니다.
  
```PowerShell
Get-CsUser -OU "ou=Finance,dc=litwareinc,dc=com" | Grant-CsConferencingPolicy -PolicyName FinanceConferencingPolicy
```

전체 구문 및 매개 변수 목록을 비롯 한 자세한 내용은 [CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csconferencingpolicy?view=skype-ps)를 참조 하세요.
  

