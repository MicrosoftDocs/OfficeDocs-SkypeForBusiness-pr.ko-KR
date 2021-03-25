---
title: 비즈니스용 Skype 서버에서 PIN 정책 정보 보기
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
ms.collection: IT_Skype16
ms.assetid: 1d48b060-d77f-44ee-b70f-3ce128aedac4
description: '요약: 비즈니스용 Skype 서버에 대한 사용자의 PIN 정책 정보를 시청합니다.'
ms.openlocfilehash: 80383ce7e78ba8806119121f8c27c6e469363003
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119537"
---
# <a name="view-pin-policy-information-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서 PIN 정책 정보 보기
 
**요약:** 비즈니스용 Skype 서버에 대한 사용자의 PIN 정책 정보를 하세요.
  
**PIN** 정책 탭을 사용하여 IP 전화를 사용하여 비즈니스용 Skype에 연결하는 사용자의 PIN(개인 식별 번호) 인증을 볼 수 있습니다. PIN 인증을 사용하려면 웹 서비스 설정에서 **PIN 인증 사용** 이 선택되어 있는지 확인합니다.
  
사용자 수준 또는 사이트 수준 PIN 정책을 수정하려면 다음 단계를 수행합니다. 
  
### <a name="to-view-information-about-a-pin-policy-in-skype-for-business-server-control-panel"></a>비즈니스용 Skype 서버 제어판에서 PIN 정책에 대한 정보를 보기 위해

1.  RTCUniversalServerAdmins 그룹의 구성원(또는 이와 동등한 사용자 권한)의 사용자 계정 또는 CsServerAdministrator 또는 CsAdministrator 역할에 할당된 사용자 계정에서 비즈니스용 Skype 서버를 배포한 네트워크에 있는 컴퓨터에 로그온합니다.
    
2. 브라우저 창을 열고 관리 URL을 입력하여 비즈니스용 Skype 서버 제어판을 니다.  
    
3. 왼쪽 탐색 모음에서 **보안** 을 클릭하고 **PIN 정책** 을 클릭합니다.
    
4. **PIN 정책** 페이지에서 정책을 클릭하고 **편집** 을 클릭한 후에 **자세한 정보 표시** 를 클릭합니다.
    
## <a name="viewing-pin-policies-by-using-windows-powershell-cmdlets"></a>cmdlet을 사용하여 PIN Windows PowerShell 보기

또한 CMDLET 및 cmdlet을 사용하여 PIN 정책을 Windows PowerShell Get-CsPinPolicy 있습니다. 이 cmdlet은 비즈니스용 Skype 서버 관리 셸 또는 비즈니스용 Skype 서버 관리 셸에서 실행할 수 Windows PowerShell. 원격 Windows PowerShell 사용하여 비즈니스용 Skype 서버에 연결하는 데 대한 자세한 내용은 [블로그 문서 "빠른 시작: 원격 PowerShell을 사용하여 Microsoft Lync Server 2010 관리"를 참조하세요.](https://go.microsoft.com/fwlink/p/?linkId=255876) 이 프로세스는 비즈니스용 Skype 서버에서 동일합니다.
  
### <a name="to-view-pin-policies"></a>PIN 정책을 보기 위해

모든 PIN 정책에 대한 정보를 보시다시피 비즈니스용 Skype 서버 관리 셸에 다음 명령을 입력한 다음 Enter를 누르고 있습니다.
    
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

[비즈니스용 Skype 서버에서 새 PIN 정책 만들기](create-a-new-pin-policy.md)