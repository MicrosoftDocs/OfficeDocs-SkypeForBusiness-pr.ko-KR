---
title: 보관을 사용하도록 설정하거나 사용하지 않도록 비즈니스용 Skype 서버
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
ms.assetid: d5aed328-e89d-4a7b-b603-15ae5c33c5dd
description: '요약: 보관을 사용하도록 설정하거나 사용하지 않도록 설정하는 방법을 비즈니스용 Skype 서버.'
ms.openlocfilehash: 3ed4fd18f6d130bbfa5211b142cc1804c489f37c
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62388186"
---
# <a name="enable-or-disable-archiving-in-skype-for-business-server"></a>보관을 사용하도록 설정하거나 사용하지 않도록 비즈니스용 Skype 서버

**요약:** 보관을 사용하도록 설정하거나 사용하지 않도록 설정하는 방법을 비즈니스용 Skype 서버.
  
## <a name="enable-or-disable-archiving-by-using-the-control-panel"></a>제어판을 사용하여 보관 사용 또는 사용 안 하도록 설정

1. CsArchivingAdministrator 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다. 
    
2. 브라우저 창을 열고 관리 URL을 입력하여 관리 비즈니스용 Skype 서버  열 수 있습니다. 
    
3. 왼쪽 탐색 모음에서 **모니터링 및 보관** 을 클릭하고 **보관 구성** 을 클릭합니다.
    
4. 보관 구성 목록에서 적절한 전역, 사이트 또는 풀 구성을 선택하고 편집을 클릭하고 세부 정보 표시를 클릭한 후 다음을 클릭합니다.
    
   - 메신저 대화 세션에 대해서만 보관을 사용하도록 설정하려면 **메신저 대화 세션 보관** 을 클릭합니다.
    
   - IM 세션과 회의 모두에 대해 보관을 사용하도록 설정하려면 IM 및 회의 세션 보관 **을 클릭합니다**.
    
   - 구성에 대해 보관을 사용하지 않도록 설정하려면 보관 **사용 안 을 클릭합니다**.
    
5. **커밋** 을 클릭합니다.
    
## <a name="enable-or-disable-archiving-by-using-windows-powershell"></a>보관을 사용하여 보관을 사용 또는 사용하지 않도록 Windows PowerShell

**Set-CsArchivingConfiguration** cmdlet을 사용하여 보관을 사용하도록 설정하거나 사용하지 않도록 설정할 수도 있습니다. 예를 들어 다음 명령은 IM 세션만 보관할 수 있도록 모든 보관 구성 설정을 수정합니다. 이 명령은 **Get-CsArchivingConfiguration** cmdlet을 매개 변수 없이 호출하여 조직에서 현재 사용 중인 모든 보관 구성 설정을 반환합니다. 이 컬렉션은 EnableArchiving 속성이 "ImAndWebConf"과 같은(-eq) 설정만 선택하는 **Where-Object** cmdlet에 파이프됩니다. 그런 다음 필터링된 컬렉션은 컬렉션의 각 항목을 사용하여 EnableArchiving의 값을 "ImOnly"로 변경하는 **Set-CsArchivingConfiguration** cmdlet에 파이프됩니다.
  
```PowerShell
Get-CsArchivingConfiguration | Where-Object {$_.EnableArchiving -eq "ImAndWebConf"} | Set-CsArchivingConfiguration -EnableArchiving "ImOnly"
```
