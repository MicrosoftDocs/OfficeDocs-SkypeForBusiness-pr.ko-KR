---
title: 정책에서 PIN 정책 비즈니스용 Skype 서버
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 7c378927-2e41-418e-9721-327021bd2e45
description: '요약: 사용자 전화 접속 회의 PIN을 비즈니스용 Skype 서버.'
ms.openlocfilehash: 61bd6aabf823ab73f26832b1494bf625d3ea641c
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60847431"
---
# <a name="delete-a-pin-policy-in-skype-for-business-server"></a>정책에서 PIN 정책 비즈니스용 Skype 서버
 
**요약:** 사용자 전화 접속 회의 PIN을 삭제하여 비즈니스용 Skype 서버.
  
PIN(개인 식별 번호) 정책을 삭제하려면 다음 단계를 수행합니다.
  
> [!NOTE]
> 전역 PIN 정책은 삭제할 수 없습니다. 
  
### <a name="to-delete-a-pin-policy-in-skype-for-business-server-control-panel"></a>제어판에서 PIN 비즈니스용 Skype 서버 삭제하려면

1.  RTCUniversalServerAdmins 그룹의 구성원(또는 이와 동등한 사용자 권한)의 사용자 계정 또는 CsServerAdministrator 또는 CsAdministrator 역할에 할당된 사용자 계정에서 배포한 네트워크의 컴퓨터에 비즈니스용 Skype 서버.
    
2. 브라우저 창을 열고 관리 URL을 입력하여 관리 비즈니스용 Skype 서버 열 수 있습니다.  
    
3. 왼쪽 탐색 모음에서 **보안** 을 클릭하고 **PIN 정책** 을 클릭합니다.
    
4. **PIN 정책** 페이지의 검색 필드에 삭제할 정책의 이름 전부 또는 일부를 입력합니다.
    
5. 정책 목록에서 원하는 정책을 클릭하고 **편집** 을 클릭한 다음 **삭제** 를 클릭합니다.
    
6. **확인** 을 클릭합니다.
    
## <a name="removing-pin-policies-by-using-windows-powershell-cmdlets"></a>cmdlet을 사용하여 PIN Windows PowerShell 제거

PIN 정책은 Windows PowerShell cmdlet을 사용하여 삭제할 Remove-CsPinPolicy 있습니다. 이 cmdlet은 관리 셸 또는 비즈니스용 Skype 서버 세션에서 실행할 수 Windows PowerShell. 원격 응용 Windows PowerShell 연결에 대한 자세한 비즈니스용 Skype 서버 [Microsoft Lync Remote PowerShell Administration 을 참조합니다.](https://blog.insideo365.com/2011/08/remote-lync-powershell-administration/) 프로세스는 동일한 비즈니스용 Skype 서버.
  
### <a name="to-remove-a-specific-pin-policy"></a>특정 PIN 정책을 제거하려면

- 이 명령은 ID RedmondPinPolicy가 포함된 PIN 정책을 제거합니다.
    
  ```PowerShell
  Remove-CsPinPolicy -Identity "RedmondPinPolicy"
  ```

### <a name="to-remove-all-the-pin-policies-applied-to-the-site-scope"></a>사이트 범위에 적용된 모든 PIN 정책을 제거하려면

- 이 명령은 사이트 범위에 구성된 모든 PIN 정책을 제거합니다.
    
  ```PowerShell
  Get-CsPinPolicy -Filter "site:*" | Remove-CsPinPolicy
  ```

### <a name="to-remove-all-the-pin-policies-that-allow-the-use-of-common-patterns"></a>공통 패턴 사용을 허용하는 모든 PIN 정책을 제거하려면

- 그리고 이 명령은 공통 패턴 사용을 허용하는 모든 PIN 정책을 제거합니다.
    
  ```PowerShell
  et-CsPinPolicy | Where-Object {$_.AllowCommonPatterns -eq $True} | Remove-CsPinPolicy
  ```

자세한 내용은 [Remove-CsPinPolicy](/powershell/module/skype/remove-cspinpolicy?view=skype-ps) cmdlet에 대한 도움말 항목을 참조하십시오.
