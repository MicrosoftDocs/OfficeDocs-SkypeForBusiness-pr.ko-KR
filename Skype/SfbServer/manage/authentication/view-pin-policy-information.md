---
title: PIN 정책 정보 보기 비즈니스용 Skype 서버
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 1d48b060-d77f-44ee-b70f-3ce128aedac4
description: '요약: 사용자 PIN 정책 정보를 비즈니스용 Skype 서버.'
ms.openlocfilehash: fca606d00507f199e09d84604d60cc8004ad9a9b
ms.sourcegitcommit: efd56988b22189dface73c156f6f8738f273fa61
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/30/2021
ms.locfileid: "60013732"
---
# <a name="view-pin-policy-information-in-skype-for-business-server"></a>PIN 정책 정보 보기 비즈니스용 Skype 서버
 
**요약:** 사용자 PIN 정책 정보를 비즈니스용 Skype 서버.
  
**PIN** 정책 탭을 사용하여 IP 전화를 사용하여 PIN에 연결하는 사용자의 개인식별번호(PIN) 인증을 비즈니스용 Skype 수 있습니다. PIN 인증을 사용하려면 웹 서비스 설정에서 **PIN 인증 사용** 이 선택되어 있는지 확인합니다.
  
사용자 수준 또는 사이트 수준 PIN 정책을 수정하려면 다음 단계를 수행합니다. 
  
### <a name="to-view-information-about-a-pin-policy-in-skype-for-business-server-control-panel"></a>제어판에서 PIN 정책에 대한 비즈니스용 Skype 서버 보기

1.  RTCUniversalServerAdmins 그룹의 구성원(또는 이와 동등한 사용자 권한)의 사용자 계정 또는 CsServerAdministrator 또는 CsAdministrator 역할에 할당된 사용자 계정에서 배포한 네트워크의 컴퓨터에 비즈니스용 Skype 서버.
    
2. 브라우저 창을 열고 관리 URL을 입력하여 관리 비즈니스용 Skype 서버 열 수 있습니다.  
    
3. 왼쪽 탐색 모음에서 **보안** 을 클릭하고 **PIN 정책** 을 클릭합니다.
    
4. **PIN 정책** 페이지에서 정책을 클릭하고 **편집** 을 클릭한 후에 **자세한 정보 표시** 를 클릭합니다.
    
## <a name="viewing-pin-policies-by-using-windows-powershell-cmdlets"></a>cmdlet을 사용하여 PIN Windows PowerShell 보기

또한 CMDLET 및 cmdlet을 사용하여 PIN 정책을 Windows PowerShell Get-CsPinPolicy 있습니다. 이 cmdlet은 관리 셸 또는 비즈니스용 Skype 서버 원격 세션에서 실행할 수 Windows PowerShell. 원격 응용 Windows PowerShell 연결에 대한 자세한 비즈니스용 Skype 서버 [Microsoft Lync Remote PowerShell Administration 을 참조합니다.](https://blog.insideo365.com/2011/08/remote-lync-powershell-administration/) 프로세스는 동일한 비즈니스용 Skype 서버.
  
### <a name="to-view-pin-policies"></a>PIN 정책을 보기 위해

모든 PIN 정책에 대한 정보를 보시다시피 비즈니스용 Skype 서버 관리 셸에서 다음 명령을 입력한 다음 Enter를 눌러야 합니다.
    
  ```PowerShell
  Get-CsPinPolicy
  ```

그러면 다음과 같은 정보가 반환됩니다.

<pre>
Identity             : Global
Description          :
MinPasswordLength    : 5
PINHistoryCount      : 0
AllowCommonPatterns  : False
PINLifetime          : 0
MaximumLogonAttempts :
</pre>

자세한 내용은 [Get-CsPinPolicy](/powershell/module/skype/get-cspinpolicy?view=skype-ps) cmdlet에 대한 도움말 항목을 참조하십시오.
  
## <a name="see-also"></a>참고 항목

[새 PIN 정책을 비즈니스용 Skype 서버](create-a-new-pin-policy.md)