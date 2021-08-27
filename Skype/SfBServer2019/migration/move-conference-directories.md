---
title: 회의 디렉터리 이동
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: 풀을 해제하기 전에 레거시 풀의 각 회의 디렉터리에 대해 다음 절차를 수행해야 합니다.
ms.openlocfilehash: 5d4333f74c1d45e57e45c66c8de6f3e279cee01f
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58596152"
---
# <a name="move-conference-directories"></a>회의 디렉터리 이동

풀을 해제하기 전에 레거시 풀의 각 회의 디렉터리에 대해 다음 절차를 수행해야 합니다.
  
### <a name="to-move-a-conference-directory-to-skype-for-business-server-2019"></a>회의 디렉터리를 2019년 비즈니스용 Skype 서버 이동

1. 관리 비즈니스용 Skype 서버 셸을 열 수 있습니다.
    
2. 조직에서 회의의 ID를 얻습니다. 다음 명령을 실행합니다.
    
   ```PowerShell
   Get-CsConferenceDirectory
   ```

    위의 명령은 조직의 모든 회의를 반환합니다. 따라서 해제되는 풀로 결과를 제한할 수 있습니다. 예를 들어 FQDN(FQDN) pool01.contoso.net 풀을 해제하는 경우 이 명령을 사용하여 반환되는 데이터를 해당 풀의 회의 디렉터로 제한합니다.
    
   ```PowerShell
   Get-CsConferenceDirectory | Where-Object {$_.ServiceID -match "pool01.contoso.net"}
   ```

    이 명령은 ServiceID 속성에 FQDN이 포함된 전화 회의 pool01.contoso.net.
    
3. 회의 디렉터리를 이동하기 위해 풀의 각 회의 디렉터리에 대해 다음 명령을 실행합니다.
    
   ```PowerShell
   Move-CsConferenceDirectory -Identity <Numeric identity of conference directory> -TargetPool <FQDN of pool where ownership is to be transitioned>
   ```

    예를 들어 회의 디렉터리 3을 이동하기 위해 다음 명령을 사용하여 비즈니스용 Skype 서버 2019 풀을 TargetPool로 지정합니다.
    
   ```PowerShell
   Move-CsConferenceDirectory -Identity 3 -TargetPool "pool02.contoso.net"
   ```

    풀의 모든 회의 센터를 이동하려는 경우 다음과 같은 명령을 사용 합니다.
    
   ```PowerShell
   Get-CsConferenceDirectory | Where-Object {$_.ServiceID -match "pool01.contoso.net"} | Move-CsConferenceDirectory -TargetPool "pool02.contoso.net"
   ```

[레거시](https://go.microsoft.com/fwlink/p/?linkId=246227) 풀을 해제하는 방법에 대한 포괄적인 단계별 지침을 확인하려면 Microsoft 레거시 제거 및 서버 역할 제거를 다운로드하세요.
  
회의를 이동하는 경우 다음과 같은 오류가 발생할 수 있습니다.
  
```console
WARNING: Move operation failed for conference directory with ID "5". Cannot perform a rollback because data migration might have already started. Retry the operation.
WARNING: Before using the -Force parameter, ensure that you have exported the conference directory data using DBImpExp.exe and imported the data on the target pool. Refer to the DBImpExp-Readme.htm file for more information.
Move-CsConferenceDirectory : Unable to cast COM object of type 'System._ComObject' to interface type 'Microsoft.Rtc.Interop.User.IRtcConfDirManagement'. 
This operation failed because the QueryInterface call on the COM component for the interface with SID '{4262B886-503F-4BEA-868C-04E8DF562CEB}' failed due to the following error: The specified module could not be found.
```

이 오류는 일반적으로 비즈니스용 Skype 서버 관리 셸에서 작업을 완료하기 위해 업데이트된 Active Directory 권한 집합이 필요한 경우 발생합니다. 문제를 해결하려면 관리 셸의 현재 인스턴스를 닫은 다음 새 셸 인스턴스를 열고 명령을 다시 실행하여 회의 디렉터리를 이동합니다.
  

