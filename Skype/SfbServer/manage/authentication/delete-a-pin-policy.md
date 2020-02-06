---
title: 비즈니스용 Skype 서버에서 핀 정책 삭제
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
ms.collection: IT_Skype16
ms.assetid: 7c378927-2e41-418e-9721-327021bd2e45
description: '요약: 비즈니스용 Skype 서버용 사용자의 전화 접속 회의 PIN을 삭제 합니다.'
ms.openlocfilehash: c496c8b1966ad16ba63b3320b373d3c9ca27dd20
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818800"
---
# <a name="delete-a-pin-policy-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서 핀 정책 삭제
 
**요약:** 비즈니스용 Skype 서버용 사용자의 전화 접속 회의 PIN을 삭제 합니다.
  
PIN (개인 식별 번호) 정책을 삭제 하려면 다음 단계를 따르세요.
  
> [!NOTE]
> 글로벌 PIN 정책은 삭제할 수 없습니다. 
  
### <a name="to-delete-a-pin-policy-in-skype-for-business-server-control-panel"></a>비즈니스용 Skype Server 제어판에서 핀 정책을 삭제 하려면

1.  RTCUniversalServerAdmins 그룹의 구성원 이거나 해당 사용자 권한이 있는 사용자 계정에서 또는 CsServerAdministrator 또는 CsAdministrator 역할에 할당 된 경우 비즈니스용 Skype 서버를 배포한 네트워크의 컴퓨터에 로그온 합니다. .
    
2. 브라우저 창을 열고 관리자 URL을 입력 하 여 비즈니스용 Skype 서버 제어판을 엽니다.  
    
3. 왼쪽 탐색 모음에서 **보안** 을 클릭 한 다음 **고정 정책을**클릭 합니다.
    
4. **PIN 정책** 페이지에서 검색 필드에 삭제 하려는 정책의 이름 전체 또는 일부를 입력 합니다.
    
5. 정책 목록에서 원하는 정책을 클릭 하 고 **편집**을 클릭 한 다음 **삭제**를 클릭 합니다.
    
6. **확인**을 클릭합니다.
    
## <a name="removing-pin-policies-by-using-windows-powershell-cmdlets"></a>Windows PowerShell Cmdlet을 사용 하 여 PIN 정책 제거

Windows PowerShell 및 CsPinPolicy cmdlet을 사용 하 여 PIN 정책을 삭제할 수 있습니다. 이 cmdlet은 비즈니스용 Skype 서버 관리 셸에서 또는 Windows PowerShell의 원격 세션에서 실행할 수 있습니다. 원격 Windows PowerShell을 사용 하 여 비즈니스용 Skype Server에 연결 하는 방법에 대 한 자세한 내용은 블로그 문서 ["빠른 시작: 원격 PowerShell을 사용 하 여 Microsoft Lync Server 2010 관리"](https://go.microsoft.com/fwlink/p/?linkId=255876)를 참조 하세요. 이 프로세스는 비즈니스용 Skype 서버에서 동일 합니다.
  
### <a name="to-remove-a-specific-pin-policy"></a>특정 PIN 정책 제거

- 이 명령은 Id RedmondPinPolicy를 사용 하 여 PIN 정책을 제거 합니다.
    
  ```PowerShell
  Remove-CsPinPolicy -Identity "RedmondPinPolicy"
  ```

### <a name="to-remove-all-the-pin-policies-applied-to-the-site-scope"></a>사이트 범위에 적용 된 모든 PIN 정책을 제거 하려면

- 이 명령은 사이트 범위에서 구성 된 PIN 정책을 모두 제거 합니다.
    
  ```PowerShell
  Get-CsPinPolicy -Filter "site:*" | Remove-CsPinPolicy
  ```

### <a name="to-remove-all-the-pin-policies-that-allow-the-use-of-common-patterns"></a>공통 패턴을 사용할 수 있는 PIN 정책을 모두 제거 하려면

- 이 항목은 일반 패턴을 사용할 수 있는 PIN 정책 (: G)을 모두 제거 합니다.
    
  ```PowerShell
  et-CsPinPolicy | Where-Object {$_.AllowCommonPatterns -eq $True} | Remove-CsPinPolicy
  ```

자세한 내용은 [제거 CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/remove-cspinpolicy?view=skype-ps) cmdlet에 대 한 도움말 항목을 참조 하세요.
  

