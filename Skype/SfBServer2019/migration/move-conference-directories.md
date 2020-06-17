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
localization_priority: Normal
description: 풀을 해제 하기 전에 레거시 풀의 각 전화 회의 디렉터리에 대해 다음 절차를 수행 해야 합니다.
ms.openlocfilehash: 8a25b955ae769a712750ff08325b3fa29538be8a
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752500"
---
# <a name="move-conference-directories"></a>회의 디렉터리 이동

풀을 해제 하기 전에 레거시 풀의 각 전화 회의 디렉터리에 대해 다음 절차를 수행 해야 합니다.
  
### <a name="to-move-a-conference-directory-to-skype-for-business-server-2019"></a>회의 디렉터리를 비즈니스용 Skype 서버 2019로 이동 하려면

1. 비즈니스용 Skype 서버 관리 셸을 엽니다.
    
2. 조직에서 회의 디렉터리의 id를 가져오려면 다음 명령을 실행 합니다.
    
   ```PowerShell
   Get-CsConferenceDirectory
   ```

    위의 명령은 조직의 모든 전화 회의 디렉터리를 반환 합니다. 따라서 역할을 해제 하는 풀로 결과를 제한할 수 있습니다. 예를 들어 FQDN (정규화 된 도메인 이름) pool01.contoso.net을 사용 하 여 풀을 제거 하는 경우이 명령을 사용 하 여 반환 되는 데이터를 해당 풀의 전화 회의 디렉터리로 제한 합니다.
    
   ```PowerShell
   Get-CsConferenceDirectory | Where-Object {$_.ServiceID -match "pool01.contoso.net"}
   ```

    이 명령은 ServiceID 속성에 FQDN pool01.contoso.net가 포함 된 전화 회의 디렉터리만 반환 합니다.
    
3. 전화 회의 디렉터리를 이동 하려면 풀의 각 전화 회의 디렉터리에 대해 다음 명령을 실행 합니다.
    
   ```PowerShell
   Move-CsConferenceDirectory -Identity <Numeric identity of conference directory> -TargetPool <FQDN of pool where ownership is to be transitioned>
   ```

    예를 들어 전화 회의 디렉터리 3을 이동 하려면 다음 명령을 사용 하 여 비즈니스용 Skype 서버 2019 풀을 TargetPool로 지정 합니다.
    
   ```PowerShell
   Move-CsConferenceDirectory -Identity 3 -TargetPool "pool02.contoso.net"
   ```

    풀의 모든 전화 회의 디렉터리를 이동 하려면 다음과 같은 명령을 사용 합니다.
    
   ```PowerShell
   Get-CsConferenceDirectory | Where-Object {$_.ServiceID -match "pool01.contoso.net"} | Move-CsConferenceDirectory -TargetPool "pool02.contoso.net"
   ```

레거시 풀을 제거 하는 방법에 대 한 포괄적인 단계별 지침을 제공 [하는 Microsoft legacy을 다운로드 하 고 서버 역할을 제거](https://go.microsoft.com/fwlink/p/?linkId=246227) 합니다.
  
전화 회의 디렉터리를 이동할 때 다음과 같은 오류가 발생할 수 있습니다.
  
```console
WARNING: Move operation failed for conference directory with ID "5". Cannot perform a rollback because data migration might have already started. Retry the operation.
WARNING: Before using the -Force parameter, ensure that you have exported the conference directory data using DBImpExp.exe and imported the data on the target pool. Refer to the DBImpExp-Readme.htm file for more information.
Move-CsConferenceDirectory : Unable to cast COM object of type 'System._ComObject' to interface type 'Microsoft.Rtc.Interop.User.IRtcConfDirManagement'. 
This operation failed because the QueryInterface call on the COM component for the interface with SID '{4262B886-503F-4BEA-868C-04E8DF562CEB}' failed due to the following error: The specified module could not be found.
```

이 오류는 일반적으로 비즈니스용 Skype 서버 관리 셸에서 작업을 완료 하기 위해 업데이트 된 Active Directory 사용 권한 집합이 필요한 경우 발생 합니다. 이 문제를 해결 하려면 관리 셸의 현재 인스턴스를 닫은 다음 셸의 새 인스턴스를 열고 명령을 다시 실행 하 여 전화 회의 디렉터리를 이동 합니다.
  

