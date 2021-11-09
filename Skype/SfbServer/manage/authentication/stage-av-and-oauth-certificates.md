---
title: 3단계에서 -Roll을 비즈니스용 Skype 서버 AV 및 OAuth 인증서를 Set-CsCertificate
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
ms.assetid: 22dec3cc-4b6b-4df2-b269-5b35df4731a7
description: '요약: AV 및 OAuth 인증서를 단계적으로 비즈니스용 Skype 서버.'
ms.openlocfilehash: 7eeac29ba322d40d8ab8f70712ecfca5ead5c97d
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60832112"
---
# <a name="stage-av-and-oauth-certificates-in-skype-for-business-server-using--roll-in-set-cscertificate"></a>3단계에서 -Roll을 비즈니스용 Skype 서버 AV 및 OAuth 인증서를 Set-CsCertificate
 
**요약:** 단계 AV 및 OAuth 인증서를 비즈니스용 Skype 서버.
  
A/V(오디오/비디오) 통신은 A/V의 핵심 구성 비즈니스용 Skype 서버. 응용 프로그램 공유 및 오디오 및 비디오 회의와 같은 기능은 A/V 에지 서비스, 특히 A/V 인증 서비스에 할당된 인증서를 사용 합니다.
  
> [!IMPORTANT]
> 이 새로운 기능은 A/V 에지 서비스 및 OAuthTokenIssuer 인증서에 대해 작동하도록 디자인됩니다. 다른 인증서 유형은 A/V 에지 서비스 및 OAuth 인증서 유형과 함께 프로비전할 수 있지만 A/V 에지 서비스 인증서가 제공하는 동시 사용 동작의 이점은 없습니다.
  
비즈니스용 Skype 서버 인증서를 관리하는 데 사용되는 비즈니스용 Skype 서버 관리 셸 PowerShell cmd 비즈니스용 Skype 서버let은 A/V 에지 서비스 인증서를 AudioVideoAuthentication 인증서 유형으로, OAuthServer 인증서는 typeOAuthTokenIssuer로 지 지어지며, 이 항목의 나머지와 인증서를 고유하게 식별하기 위해 동일한 식별자 유형인 AudioVideoAuthentication 및OAuthTokenIssuer로 참조됩니다.
  
A/V 인증 서비스는 클라이언트 및 기타 A/V 소비자가 사용하는 토큰을 발행합니다. 토큰은 인증서의 특성에서 생성되고 인증서가 만료되면 연결이 끊어지며 새 인증서에 의해 생성된 새 토큰과 다시 연결해야 하는 요구 사항이 생성됩니다. 비즈니스용 Skype 서버 새로운 기능은 이 문제를 해결합니다. 즉, 이전 인증서가 만료되고 두 인증서가 한 기간 동안 계속 작동할 수 있도록 새 인증서를 준비할 수 있습니다. 이 기능은 Set-CsCertificate 비즈니스용 Skype 서버 관리 셸 cmdlet의 업데이트된 기능을 사용 합니다. 새 매개 변수 -Roll은 기존 매개 변수 -EffectiveDate를 사용하여 새 AudioVideoAuthentication 인증서를 인증서 저장소에 저장합니다. 이전 AudioVideoAuthentication 인증서는 발급된 토큰에 대해 유효성을 검사할 수 있는 상태로 유지됩니다. 새 AudioVideoAuthentication 인증서를 추가하는 것부터 다음과 같은 일련의 이벤트가 발생합니다.
  
> [!TIP]
> 인증서 비즈니스용 Skype 서버 관리 셸 cmdlet을 사용하여 에지 서버의 각 용도에 대해 별도의 인증서를 요청할 수 있습니다. 비즈니스용 Skype 서버 배포 마법사에서 인증서 마법사를 사용하면 인증서를 만들 수 있지만 일반적으로  모든 인증서가 에지 서버에 사용하는 모든 인증서를 단일 인증서에 결합하는 기본 형식입니다. 롤링 인증서 기능을 사용하게 될 경우 AudioVideoAuthentication 인증서를 다른 인증서와 분리하는 것이 좋습니다. Default 유형의 인증서를 프로비전하고 준비할 수 있지만 결합된 인증서의 AudioVideoAuthentication 부분만 준비를 통해 이점을 제공합니다. 인증서가 만료될 때 인스턴트 메시징 대화에 참여한 사용자는 액세스 에지 서비스에 연결된 새 인증서를 사용하기 위해 로그아웃했다가 다시 로그인해야 합니다. 웹 회의 에지 서비스를 사용하여 웹 회의에 참여한 사용자에 대해 유사한 동작이 발생합니다. OAuthTokenIssuer 인증서는 모든 서버에서 공유되는 특정 유형입니다. 인증서를 한 장소에서 만들고 관리하면 인증서가 다른 모든 서버의 중앙 관리 저장소에 저장됩니다.
  
현재 인증서 만료 전에 Set-CsCertificate cmdlet을 사용하여 인증서를 단계화할 때 옵션 및 요구 사항을 완전히 이해하려면 추가 세부 정보가 필요합니다. -Roll 매개 변수는 중요하지만 기본적으로 단일 용도입니다. 매개 변수로 정의하는 경우 인증서가 -EffectiveDate에 의해 정의될 때 -type(예: AudioVideoAuthentication 및 OAuthTokenIssuer)에 의해 정의될 인증서에 대한 정보를 제공하게 될 것임이 알려야 Set-CsCertificate 합니다.
  
 **-Roll**: -Roll 매개 변수가 필요하며 함께 제공해야 하는 종속성도 있습니다. 영향을 받을 인증서와 인증서 적용 방법을 완전히 정의하는 데 필요한 매개 변수:
  
 **-EffectiveDate**: 매개 변수 -EffectiveDate는 새 인증서가 현재 인증서와 함께 활성화될 때를 정의합니다. -EffectiveDate는 현재 인증서의 만료 기간에 가까워지거나 더 긴 기간이 될 수 있습니다. AudioVideoAuthentication 인증서에 권장되는 최소 -EffectiveDate는 8시간으로, AudioVideoAuthentication 인증서를 사용하여 발급된 AV 에지 서비스 토큰의 기본 토큰 수명입니다.
  
OAuthTokenIssuer 인증서를 준비할 때 인증서가 유효해지기 전까지는 리드 타임에 대한 요구 사항이 다릅니다. OAuthTokenIssuer 인증서의 리드 타임에 대한 최소 시간은 현재 인증서의 만료 시간 24시간 전입니다. 공존에 대한 연장된 리드 타임은 인증서를 만든 인증 및 암호화 키 자료에 대한 보존 시간이 더 긴 OAuthTokenIssuer 인증서(예: Exchange Server)에 종속된 다른 서버 역할 때문에 사용됩니다.
  
 **-Thumbprint**: 지문은 해당 인증서에 고유한 인증서의 특성입니다. -Thumbprint 매개 변수는 cmdlet의 작업으로 영향을 받을 인증서를 식별하는 Set-CsCertificate 사용됩니다.
  
 **-Type**: -Type 매개 변수는 단일 인증서 사용 유형 또는 인증서 사용 유형에 대한 MA로 구분된 목록을 허용할 수 있습니다. 인증서 유형은 cmdlet 및 인증서의 용도를 서버에 식별하는 유형입니다. 예를 들어 AudioVideoAuthentication은 A/V 에지 서비스 및 AV 인증 서비스에서 사용하기 위한 것입니다.를 입력합니다. 서로 다른 유형의 인증서를 동시에 준비하고 프로비전하기로 결정한 경우 인증서에 대해 가장 긴 최소 유효 리드 타임을 고려해야 합니다. 예를 들어 AudioVideoAuthentication 및 OAuthTokenIssuer 유형의 인증서를 준비해야 합니다. 최소 -EffectiveDate는 최소 24시간의 리드 타임인 OAuthTokenIssuer와 같은 두 인증서보다 커야 합니다. 24시간의 리드 타임으로 AudioVideoAuthentication 인증서를 단계별로 설정하지 않을 경우 요구 사항에 더 많은 EffectiveDate를 통해 별도로 단계별로 수록합니다.
  
### <a name="to-update-or-renew-an-av-edge-service-certificate-with-a--roll-and--effectivedate-parameters"></a>-Roll 및 -EffectiveDate 매개 변수를 사용하여 A/V 에지 서비스 인증서를 업데이트하거나 갱신

1. Administrators 그룹의 구성원으로 로컬 컴퓨터에 로그온합니다.
    
2. A/V 에지 서비스의 기존 인증서에 대해 내보낼 수 있는 개인 키가 있는 갱신 또는 새 AudioVideoAuthentication 인증서를 요청합니다.
    
3. 풀이 배포된 경우 새 AudioVideoAuthentication 인증서를 에지 서버 및 풀의 다른 모든 에지 서버로 가져올 수 있습니다.
    
4. 가져온 인증서를 Set-CsCertificate -EffectiveDate 매개 변수와 함께 -Roll 매개 변수를 사용합니다. 유효 날짜는 현재 인증서 만료 시간(14:00:00 또는 오후 2:00:00)에서 토큰 수명(기본적으로 8시간)을 밝게 하여 정의해야 합니다. 이 경우 인증서를 활성으로 설정해야 하는 시간이 주어지며 -EffectiveDate \<string\> : "7/22/2015 6:00:00 AM"입니다. 
    
    > [!IMPORTANT]
    > 에지 풀의 경우 모든 클라이언트 및 소비자 토큰이 새 인증서를 사용하여 갱신되기 전에 오래된 인증서 만료로 인한 A/V 통신 중단을 방지하기 위해 배포된 첫 번째 인증서의 -EffectiveDate 매개 변수로 정의된 날짜 및 시간으로 모든 AudioVideoAuthentication 인증서를 배포하고 프로비전해야 합니다. 
  
    -Set-CsCertificate -EffectiveTime 매개 변수를 사용하여 다음 명령을 실행합니다.
    
   ```PowerShell
   Set-CsCertificate -Type AudioVideoAuthentication -Thumbprint
          <thumb print of new certificate> -Roll -EffectiveDate <date and time
          for certificate to become active>
   ```

    명령에 Set-CsCertificate 예제:
    
   ```PowerShell
   Set-CsCertificate -Type AudioVideoAuthentication -Thumbprint
          "B142918E463981A76503828BB1278391B716280987B" -Roll -EffectiveDate "7/22/2015
          6:00:00 AM"
   ```

    > [!IMPORTANT]
    > EffectiveDate는 서버의 지역 및 언어 설정과 일치하게 형식을 지정해야 합니다. 이 예제에서는 영어(미국) 지역 및 언어 설정을 사용합니다. 
  
Set-CsCertificate, -Roll 및 -EffectiveDate가 새 AudioVideoAuthentication 토큰을 발급하기 위해 새 인증서를 준비하는 데 사용하는 프로세스를 더 이해하기 위해 기존 인증서를 사용하여 소비자가 사용 중인 AudioVideoAuthentication의 유효성을 검사하는 데에는 시각적 타임라인이 프로세스를 이해하는 효과적인 수단입니다. 다음 예제에서 관리자는 A/V 에지 서비스 인증서가 2015년 7월 22일 오후 2시에 만료될 예정인지를 파악합니다. 새 인증서를 요청 및 수신하여 풀의 각 에지 서버로 가져와야 합니다. 201 Get-CsCertificate 5년 7월 22일 오전 2시에 -Roll, -Thumbprint는 새 인증서의 지문 문자열과 같고-EffectiveTime은 2015년 7월 22일 오전 6:00:00으로 설정된 -Roll로 실행을 시작했습니다. 이 명령은 각 에지 서버에서 실행됩니다.
  
![Roll 및 EffectiveDate 매개 변수 사용](../../media/Ops_Certificate_Set_Roll_EffectiveTime_Timeline.jpg)
  
|**Callout**|**단계**|
|:-----|:-----|
|1  <br/> |시작: 2015/7/22 오전 12:00:00  <br/> 현재 AudioVideoAuthentication 인증서는 2015년 7월 22일 오후 2시에 만료될 예정입니다. 인증서의 만료된 타임스탬프에 의해 결정됩니다. 기존 인증서가 만료 시간에 도달하기 전에 8시간 동안(기본 토큰 수명) 동안 인증서 교체 및 롤오버를 계획합니다. 이 예에서는 오전 2:00:00 리드 타임을 사용하여 관리자가 새 인증서를 적절한 시간(오전 6시 00:00)에 미리 설정하고 프로비전할 수 있도록 합니다.  <br/> |
|2  <br/> |2015/7/22 오전 2:00:00 - 2015/7/22 오전 5:59:59  <br/> -Type \<certificate usage type\> -Thumbprint -Roll -EffectiveDate를 사용하여 에지 서버에서 인증서를 유효 시간이 오전 6:00:00(이 예에서는 4시간이지만 더 길어도 되지만 더 길 수 있습니다 Set-CsCertificate)으로 설정 \<thumbprint of new certificate\>\<datetime string of the effective time for new certificate\>  <br/> |
|3   <br/> |2015/7/22 오전 6:00 - 2015/7/22 오후 2:00  <br/> 토큰의 유효성을 검사하기 위해 새 인증서를 먼저 시도하고 새 인증서가 토큰의 유효성을 검사하지 못하면 이전 인증서가 시도됩니다. 이 프로세스는 8시간(기본 토큰 수명) 겹치는 기간 동안 모든 토큰에 사용됩니다.  <br/> |
|4  <br/> |종료: 2015/7/22 오후 2:00:01  <br/> 이전 인증서가 만료되고 새 인증서가 인계되었습니다. -Type -Previous을 사용하여 Remove-CsCertificate \<certificate usage type\> 인증서를 안전하게 제거할 수 있습니다.  <br/> |
   
유효 시간(2015/7/22 오전 6:00:00)에 도달하면 모든 새 토큰이 새 인증서에 의해 발급됩니다. 토큰의 유효성을 검사할 때 먼저 새 인증서에 대해 토큰의 유효성을 검사합니다. 유효성 검사가 실패하면 이전 인증서가 시도됩니다. 새 인증서를 시도하고 이전 인증서로 돌아가는 프로세스는 이전 인증서가 만료될 때까지 계속됩니다. 이전 인증서가 만료되면(2015년 7월 22일 오후 2:00:00) 토큰은 새 인증서로만 유효성을 검사합니다. -Previous 매개 변수와 함께 Remove-CsCertificate 인증서를 사용하여 이전 인증서를 안전하게 제거할 수 있습니다.

```PowerShell
Remove-CsCertificate -Type AudioVideoAuthentication -Previous
```

### <a name="to-update-or-renew-an-oauthtokenissuer-certificate-with-a--roll-and--effectivedate-parameters"></a>-Roll 및 -EffectiveDate 매개 변수를 사용하여 OAuthTokenIssuer 인증서를 업데이트하거나 갱신

1. Administrators 그룹의 구성원으로 로컬 컴퓨터에 로그온합니다.
    
2. 프런트 엔드 서버의 기존 인증서에 대해 내보낼 수 있는 개인 키가 있는 갱신 또는 새 OAuthTokenIssuer 인증서를 요청합니다.
    
3. 풀이 배포된 경우 새 OAuthTokenIssuer 인증서를 풀의 프런트 엔드 서버로 가져올 수 있습니다. OAuthTokenIssuer 인증서는 전역으로 복제되고 배포의 모든 서버에서만 업데이트 및 갱신하면 됩니다. 프런트 엔드 서버가 예로 사용됩니다.
    
4. 가져온 인증서를 Set-CsCertificate -EffectiveDate 매개 변수와 함께 -Roll 매개 변수를 사용합니다. 유효 날짜는 현재 인증서 만료 시간(14:00:00 또는 오후 2:00:00)에서 최소 24시간을 인 것으로 정의해야 합니다. 
    
    -Set-CsCertificate -EffectiveTime 매개 변수를 사용하여 다음 명령을 실행합니다.
    
   ```PowerShell
   Set-CsCertificate -Type OAuthTokenIssuer -Thumbprint <thumb
          print of new certificate> -Roll -EffectiveDate <date and time for
          certificate to become active> -identity Global 
   ```

명령에 Set-CsCertificate 예제:
    
  ```PowerShell
  Set-CsCertificate -Type OAuthTokenIssuer -Thumbprint
          "B142918E463981A76503828BB1278391B716280987B" -Roll -EffectiveDate "7/21/2015
          1:00:00 PM" 
  ```

> [!IMPORTANT]
> EffectiveDate는 서버의 지역 및 언어 설정과 일치하게 형식을 지정해야 합니다. 이 예제에서는 영어(미국) 지역 및 언어 설정을 사용합니다. 
  
유효 시간(2015/7/21 오전 1:00:00)에 도달하면 모든 새 토큰이 새 인증서에 의해 발급됩니다. 토큰의 유효성을 검사할 때 먼저 새 인증서에 대해 토큰의 유효성을 검사합니다. 유효성 검사가 실패하면 이전 인증서가 시도됩니다. 새 인증서를 시도하고 이전 인증서로 돌아가는 프로세스는 이전 인증서가 만료될 때까지 계속됩니다. 이전 인증서가 만료되면(2015년 7월 22일 오후 2:00:00) 토큰은 새 인증서로만 유효성을 검사합니다. -Previous 매개 변수와 함께 Remove-CsCertificate 인증서를 사용하여 이전 인증서를 안전하게 제거할 수 있습니다.
```PowerShell
Remove-CsCertificate -Type OAuthTokenIssuer -Previous 
```

## <a name="see-also"></a>참고 항목

[OAuth(서버 대 서버 인증) 및 파트너 응용 프로그램을 비즈니스용 Skype 서버](server-to-server-and-partner-applications.md)

[Set-CsCertificate](/powershell/module/skype/set-cscertificate?view=skype-ps)
  
[Remove-CsCertificate](/powershell/module/skype/remove-cscertificate?view=skype-ps)