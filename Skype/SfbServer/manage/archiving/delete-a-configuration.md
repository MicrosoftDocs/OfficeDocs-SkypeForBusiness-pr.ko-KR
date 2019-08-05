---
title: 비즈니스용 Skype 서버에서 보관 구성 삭제
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: fed12cb5-2c80-476a-af3b-d55b450c5fbc
description: '요약: 비즈니스용 Skype 서버에서 보관 구성을 삭제 하는 방법에 대해 알아봅니다.'
ms.openlocfilehash: e2a79949da21c9b3b8e94019375ea0e1f0887353
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36190377"
---
# <a name="delete-an-archiving-configuration-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서 보관 구성 삭제

**요약:** 비즈니스용 Skype 서버에서 보관 구성을 삭제 하는 방법에 대해 알아봅니다.
  
사이트 구성 또는 풀 구성을 삭제할 수 있지만, 전역 구성은 삭제할 수 없습니다. 전역 구성을 삭제 하면 자동으로 기본 값으로 다시 설정 됩니다.
  
## <a name="delete-an-archiving-configuration-by-using-the-control-panel"></a>제어판을 사용 하 여 보관 구성 삭제

제어판을 사용 하 여 보관 구성을 삭제 하려면 다음을 실행 합니다.
  
1. CsArchivingAdministrator 또는 CsAdministrator 역할에 할당 된 사용자 계정에서 내부 배포의 컴퓨터에 로그온 합니다. 
    
2. 브라우저 창을 열고 관리자 URL을 입력 하 여 비즈니스용 Skype 서버 제어판을 엽니다. 
    
3. 왼쪽 탐색 모음에서 **모니터링 및 보관**을 클릭 한 다음 **구성 보관**을 클릭 합니다.
    
4. 보관 구성 목록에서 삭제 하려는 사이트 또는 풀 구성을 클릭 하 고 **편집**을 클릭 한 다음 **삭제**를 클릭 합니다.
    
    > [!NOTE]
    > 전역 구성을 클릭 해도 되지만 전역 구성을 기본값으로 다시 설정 하려는 경우에만이 옵션을 선택 합니다. 
  
5. **커밋**을 클릭합니다.
    
## <a name="delete-an-archiving-configuration-by-using-windows-powershell"></a>Windows PowerShell을 사용 하 여 보관 구성 삭제

**CsArchivingConfiguration** cmdlet을 사용 하 여 보관 구성을 삭제할 수도 있습니다.
  
예를 들어 다음 명령은 Redmond 사이트에 적용 된 보관 구성 설정을 제거 합니다. 사이트 범위에서 구성 된 정책을 삭제 하는 경우 이전에 사이트 정책에서 관리 하는 사용자는 전역 보관 정책에 의해 자동으로 제어 됩니다.
  
```
Remove-CsArchivingConfiguration -Identity "site:Redmond"
```

다음 명령은 서비스 범위에 적용 된 모든 보관 구성 설정을 제거 합니다.
  
```
Get-CsArchivingConfiguration -Filter "site:*" | Remove-CsArchivingConfiguration
```

다음 명령은 Exchange 보관을 사용 하지 않도록 설정한 모든 보관 구성 설정을 제거 합니다.
  
```
Get-CsArchivingConfiguration | Where-Object {$_.EnableExchangeArchiving -eq $False} | Remove-CsArchivingConfiguration
```

또한 **Remove-CsArchivingConfiguration** cmdlet을 사용 하 여 전역 설정을 기본값으로 다시 설정할 수 있습니다. 예를 들어 전역 수준에서 IM 세션 보관을 사용 하도록 설정한 경우 다음 명령은 전역 수준에서 보관을 해제 하는 기본값을 없음 값으로 다시 설정 합니다.
  
```
Remove-CsArchivingConfiguration -Identity global
```

자세한 내용은 [제거 CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csarchivingconfiguration?view=skype-ps) cmdlet에 대 한 도움말 항목을 참조 하세요.
