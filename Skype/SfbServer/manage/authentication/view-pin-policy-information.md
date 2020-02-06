---
title: 비즈니스용 Skype 서버에서 PIN 정책 정보 보기
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
ms.assetid: 1d48b060-d77f-44ee-b70f-3ce128aedac4
description: '요약: 비즈니스용 Skype 서버에 대 한 사용자의 PIN 정책 정보를 봅니다.'
ms.openlocfilehash: 57a54e960a0c89408f173567a78449cad21de9ed
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818700"
---
# <a name="view-pin-policy-information-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서 PIN 정책 정보 보기
 
**요약:** 비즈니스용 Skype 서버에 대 한 사용자의 PIN 정책 정보를 봅니다.
  
**Pin (고정 정책** ) 탭을 사용 하 여 IP 전화기로 비즈니스용 Skype에 연결 하는 사용자의 PIN (개인 식별 번호) 인증을 볼 수 있습니다. PIN 인증을 사용 하려면 웹 서비스 설정에서 **Pin 인증 사용** 이 선택 되어 있는지 확인 합니다.
  
다음 단계에 따라 사용자 수준 또는 사이트 수준 PIN 정책을 수정 합니다. 
  
### <a name="to-view-information-about-a-pin-policy-in-skype-for-business-server-control-panel"></a>비즈니스용 Skype Server 제어판의 PIN 정책에 대 한 정보를 보려면

1.  RTCUniversalServerAdmins 그룹의 구성원 이거나 해당 사용자 권한이 있는 사용자 계정에서 또는 CsServerAdministrator 또는 CsAdministrator 역할에 할당 된 경우 비즈니스용 Skype 서버를 배포한 네트워크의 컴퓨터에 로그온 합니다. .
    
2. 브라우저 창을 열고 관리자 URL을 입력 하 여 비즈니스용 Skype 서버 제어판을 엽니다.  
    
3. 왼쪽 탐색 모음에서 **보안** 을 클릭 한 다음 **고정 정책을**클릭 합니다.
    
4. **고정 정책** 페이지에서 정책을 클릭 하 고 **편집**을 클릭 한 다음 **세부 정보 표시**를 클릭 합니다.
    
## <a name="viewing-pin-policies-by-using-windows-powershell-cmdlets"></a>Windows PowerShell Cmdlet을 사용 하 여 PIN 정책 보기

Windows PowerShell 및 CsPinPolicy cmdlet을 사용 하 여 PIN 정책을 볼 수도 있습니다. 이 cmdlet은 비즈니스용 Skype 서버 관리 셸에서 또는 Windows PowerShell의 원격 세션에서 실행할 수 있습니다. 원격 Windows PowerShell을 사용 하 여 비즈니스용 Skype Server에 연결 하는 방법에 대 한 자세한 내용은 블로그 문서 ["빠른 시작: 원격 PowerShell을 사용 하 여 Microsoft Lync Server 2010 관리"](https://go.microsoft.com/fwlink/p/?linkId=255876)를 참조 하세요. 이 프로세스는 비즈니스용 Skype 서버에서 동일 합니다.
  
### <a name="to-view-pin-policies"></a>핀 정책 보기

모든 PIN 정책에 대 한 정보를 보려면 비즈니스용 Skype 서버 관리 셸에서 다음 명령을 입력 한 다음 enter 키를 누릅니다.
    
  ```PowerShell
  Get-CsPinPolicy
  ```

이는 다음과 같은 정보를 반환 합니다.

<pre>
Identity             : Global
Description          :
MinPasswordLength    : 5
PINHistoryCount      : 0
AllowCommonPatterns  : False
PINLifetime          : 0
MaximumLogonAttempts :
</pre>

자세한 내용은 Get-help cmdlet에 대 한 도움말 항목 [CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/get-cspinpolicy?view=skype-ps) 을 참조 하세요.
  
## <a name="see-also"></a>참고 항목

[비즈니스용 Skype 서버에서 새 PIN 정책 만들기](create-a-new-pin-policy.md)
