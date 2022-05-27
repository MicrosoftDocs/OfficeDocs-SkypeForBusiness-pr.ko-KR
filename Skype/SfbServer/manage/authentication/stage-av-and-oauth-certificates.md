---
title: Set-CsCertificate -Roll을 사용하여 비즈니스용 Skype 서버 AV 및 OAuth 인증서 스테이징
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
ms.collection: IT_Skype16
ms.assetid: 22dec3cc-4b6b-4df2-b269-5b35df4731a7
description: '요약: 비즈니스용 Skype 서버 대한 AV 및 OAuth 인증서를 스테이징합니다.'
ms.openlocfilehash: fda09cb53b664419d9652a0b663c83adc770c5cf
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/25/2022
ms.locfileid: "65674610"
---
# <a name="stage-av-and-oauth-certificates-in-skype-for-business-server-using--roll-in-set-cscertificate"></a>Set-CsCertificate -Roll을 사용하여 비즈니스용 Skype 서버 AV 및 OAuth 인증서 스테이징

**요약:** 비즈니스용 Skype 서버 대한 AV 및 OAuth 인증서를 스테이징합니다.

오디오/비디오(A/V) 통신은 비즈니스용 Skype 서버 핵심 구성 요소입니다. 애플리케이션 공유, 오디오 및 비디오 회의와 같은 기능은 A/V Edge 서비스, 특히 A/V 인증 서비스에 할당된 인증서를 사용합니다.

> [!IMPORTANT]
> 이 새로운 기능은 A/V Edge 서비스 및 OAuthTokenIssuer 인증서에 대해 작동하도록 설계되었습니다. 다른 인증서 유형은 A/V Edge 서비스 및 OAuth 인증서 유형과 함께 프로비저닝할 수 있지만 A/V Edge 서비스 인증서의 공존 동작을 활용하지는 않습니다.

비즈니스용 Skype 서버 인증서를 관리하는 데 사용되는 비즈니스용 Skype 서버 관리 셸 PowerShell cmdlet은 A/V Edge 서비스 인증서를 AudioVideoAuthentication 인증서 유형으로, OAuthServer 인증서를 typeOAuthTokenIssuer로 참조합니다. 이 항목의 나머지 부분과 인증서를 고유하게 식별하기 위해 동일한 식별자 유형인 AudioVideoAuthentication 및OAuthTokenIssuer로 참조됩니다.

A/V 인증 서비스는 클라이언트 및 기타 A/V 소비자가 사용하는 토큰을 발급하는 역할을 담당합니다. 토큰은 인증서의 특성에서 생성되며 인증서가 만료되면 연결이 끊어지고 새 인증서에서 생성된 새 토큰과 다시 가입해야 하는 요구 사항이 발생합니다. 비즈니스용 Skype 서버 새로운 기능은 이전 인증서가 만료되고 두 인증서가 일정 기간 동안 계속 작동할 수 있도록 하기 전에 새 인증서를 스테이징하는 기능인 이 문제를 완화합니다. 이 기능은 Set-CsCertificate 비즈니스용 Skype 서버 관리 셸 cmdlet에서 업데이트된 기능을 사용합니다. 기존 매개 변수 -EffectiveDate가 있는 새 매개 변수 -Roll은 인증서 저장소에 새 AudioVideoAuthentication 인증서를 배치합니다. 이전 AudioVideoAuthentication 인증서는 발급된 토큰의 유효성을 검사할 수 있도록 계속 유지됩니다. 새 AudioVideoAuthentication 인증서를 배치하는 것부터 다음과 같은 일련의 이벤트가 발생합니다.

> [!TIP]
> 인증서를 관리하기 위해 비즈니스용 Skype 서버 관리 셸 cmdlet을 사용하여 Edge Server의 각 용도에 대해 별도의 고유 인증서를 요청할 수 있습니다. 비즈니스용 Skype 서버 배포 마법사에서 인증서 마법사를 사용하면 인증서를 만드는 데 도움이 되지만 일반적으로 모든 인증서가 Edge Server에 사용하는 모든 인증서를 단일 인증서에 결합하는 **기본** 유형입니다. 롤링 인증서 기능을 사용하려는 경우 권장되는 방법은 AudioVideoAuthentication 인증서를 다른 인증서 목적과 분리하는 것입니다. 기본 형식의 인증서를 프로비전하고 스테이징할 수 있지만 결합된 인증서의 AudioVideoAuthentication 부분만 스테이징의 이점을 누릴 수 있습니다. 예를 들어 인증서가 만료될 때 메신저 대화에 참여하는 사용자는 로그아웃하고 다시 로그인하여 Access Edge 서비스와 연결된 새 인증서를 사용해야 합니다. 웹 회의 Edge 서비스를 사용하여 웹 회의에 참여하는 사용자에게도 비슷한 동작이 발생합니다. OAuthTokenIssuer 인증서는 모든 서버에서 공유되는 특정 형식입니다. 인증서를 한 곳에서 만들고 관리하면 인증서가 다른 모든 서버의 중앙 관리 저장소에 저장됩니다.

Set-CsCertificate cmdlet을 사용하고 현재 인증서가 만료되기 전에 인증서를 스테이징하는 데 사용할 때 옵션과 요구 사항을 완전히 이해하려면 추가 세부 정보가 필요합니다. -Roll 매개 변수는 중요하지만 기본적으로 단일 용도입니다. 매개 변수로 정의하는 경우 인증서가 -EffectiveDate에 의해 정의될 때 -Type(예: AudioVideoAuthentication 및 OAuthTokenIssuer)에 의해 정의된 영향을 받는 인증서에 대한 정보를 제공할 것임을 Set-CsCertificate 알려 줍니다.

 **-Roll**: -Roll 매개 변수가 필요하며 함께 제공해야 하는 종속성이 있습니다. 영향을 받을 인증서 및 적용 방법을 완전히 정의하는 데 필요한 매개 변수:

 **-EffectiveDate**: 매개 변수 -EffectiveDate는 새 인증서가 현재 인증서와 함께 활성화되는 시기를 정의합니다. -EffectiveDate는 현재 인증서의 만료 시간에 가깝거나 더 긴 기간이 될 수 있습니다. AudioVideoAuthentication 인증서에 권장되는 최소 -EffectiveDate는 AudioVideoAuthentication 인증서를 사용하여 발급된 AV Edge 서비스 토큰의 기본 토큰 수명인 8시간입니다.

OAuthTokenIssuer 인증서를 스테이징할 때 인증서가 적용되기 전에 리드 타임에 대한 요구 사항이 다릅니다. OAuthTokenIssuer 인증서가 리드 타임에 대해 가져야 하는 최소 시간은 현재 인증서의 만료 시간 24시간 전입니다. 공존에 대한 연장된 리드 타임은 인증서 생성 인증 및 암호화 키 자료에 대한 보존 시간이 더 긴 OAuthTokenIssuer 인증서(예: Exchange Server)에 종속된 다른 서버 역할 때문입니다.

 **-지문**: 지문은 해당 인증서에 고유한 인증서의 특성입니다. -Thumbprint 매개 변수는 Set-CsCertificate cmdlet의 작업의 영향을 받는 인증서를 식별하는 데 사용됩니다.

 **-Type**: -Type 매개 변수는 단일 인증서 사용 유형 또는 쉼표로 구분된 인증서 사용 유형 목록을 허용할 수 있습니다. 인증서 유형은 cmdlet 및 서버에서 인증서의 용도를 식별하는 형식입니다. 예를 들어 AudioVideoAuthentication 유형은 A/V Edge 서비스 및 AV 인증 서비스에서 사용하기 위한 것입니다. 다른 유형의 인증서를 동시에 스테이징하고 프로비전하기로 결정한 경우 인증서에 대해 가장 긴 최소 유효 리드 타임을 고려해야 합니다. 예를 들어 AudioVideoAuthentication 및 OAuthTokenIssuer 형식의 인증서를 스테이징해야 합니다. 최소 -EffectiveDate는 두 인증서 중 더 커야 합니다. 이 경우 최소 리드 타임이 24시간인 OAuthTokenIssuer입니다. 리드 타임이 24시간인 AudioVideoAuthentication 인증서를 스테이징하지 않으려면 요구 사항에 더 많은 EffectiveDate를 사용하여 별도로 스테이징합니다.

## <a name="to-update-or-renew-an-av-edge-service-certificate-with-a--roll-and--effectivedate-parameters"></a>-Roll 및 -EffectiveDate 매개 변수를 사용하여 A/V Edge 서비스 인증서를 업데이트하거나 갱신하려면

1. 관리자 그룹의 구성원으로 로컬 컴퓨터에 로그온합니다.

2. A/V Edge 서비스의 기존 인증서에 대해 내보낼 수 있는 프라이빗 키를 사용하여 갱신 또는 새 AudioVideoAuthentication 인증서를 요청합니다.

3. 풀이 배포된 경우 새 AudioVideoAuthentication 인증서를 에지 서버 및 풀의 다른 모든 에지 서버로 가져옵니다.

4. Set-CsCertificate cmdlet을 사용하여 가져온 인증서를 구성하고 -EffectiveDate 매개 변수와 함께 -Roll 매개 변수를 사용합니다. 유효 날짜는 현재 인증서 만료 시간(14:00:00 또는 오후 2:00:00)에서 토큰 수명(기본적으로 8시간)을 뺀 것으로 정의되어야 합니다. 이렇게 하면 인증서를 활성으로 설정해야 하는 시간이 제공되고 -EffectiveDate \<string\>: "2015년 7월 22일 오전 6:00:00"입니다.

   > [!IMPORTANT]
   > Edge 풀의 경우 모든 클라이언트 및 소비자 토큰이 새 인증서를 사용하여 갱신되기 전에 이전 인증서 만료로 인한 가능한 A/V 통신 중단을 방지하기 위해 배포된 첫 번째 인증서의 -EffectiveDate 매개 변수로 정의된 날짜 및 시간으로 모든 AudioVideoAuthentication 인증서를 배포하고 프로비전해야 합니다.

   -Roll 및 -EffectiveTime 매개 변수가 있는 Set-CsCertificate 명령:

   ```PowerShell
   Set-CsCertificate -Type AudioVideoAuthentication -Thumbprint <thumb print of new certificate> -Roll -EffectiveDate <date and time for certificate to become active>
   ```

   예제 Set-CsCertificate 명령:

   ```PowerShell
   Set-CsCertificate -Type AudioVideoAuthentication -Thumbprint "B142918E463981A76503828BB1278391B716280987B" -Roll -EffectiveDate "7/22/2015 6:00:00 AM"
   ```

    > [!IMPORTANT]
    > EffectiveDate는 서버의 지역 및 언어 설정과 일치하도록 형식이 지정되어야 합니다. 이 예제에서는 미국 영어 지역 및 언어 설정을 사용합니다.

Set-CsCertificate, -Roll 및 -EffectiveDate가 새 AudioVideoAuthentication 토큰을 발급하기 위한 새 인증서를 스테이징하는 데 사용하는 프로세스를 자세히 이해하려면 기존 인증서를 사용하여 소비자가 사용하고 있는 AudioVideoAuthentication의 유효성을 검사하는 동시에 시각적 타임라인은 프로세스를 이해하는 효과적인 수단입니다. 다음 예제에서 관리자는 A/V Edge 서비스 인증서가 2015년 7월 22일 오후 2:00:00에 만료되도록 결정합니다. 새 인증서를 요청하고 받아 풀의 각 Edge Server로 가져옵니다. 2015년 7월 22일 오전 2시에 -Roll, -Thumbprint가 새 인증서의 지문 문자열과 같고 -EffectiveTime이 2015년 7월 22일 오전 6:00:00으로 설정된 Get-CsCertificate 실행하기 시작합니다. 각 Edge 서버에서 이 명령을 실행합니다.

![Roll 및 EffectiveDate 매개 변수 사용](../../media/Ops_Certificate_Set_Roll_EffectiveTime_Timeline.jpg)

|설명선|단계|
|:-----|:-----|
|1|시작 날짜: 2015년 7월 22일 오전 12:00:00  <br/> 현재 AudioVideoAuthentication 인증서는 2015년 7월 22일 오후 2:00:00에 만료됩니다. 인증서의 만료 타임스탬프를 통해 결정됩니다. 기존 인증서가 만료 시간에 도달하기 전에 8시간 겹침(기본 토큰 수명)을 고려하도록 인증서 교체 및 롤오버를 계획합니다. 이 예제에서는 2:00:00 AM 리드 타임을 사용하여 관리자가 6:00:00 AM 유효 시간 전에 새 인증서를 배치하고 프로비전할 수 있는 적절한 시간을 허용합니다.|
|2|7/22/2015 2:00:00 AM - 7/22/2015 5:59:59 AM  <br/> -Type \<certificate usage type\> -Thumbprint \<thumbprint of new certificate\> -Roll -EffectiveDate를 Set-CsCertificate 사용하여 6:00:00 AM의 유효 시간(이 예제에서는 4시간 리드 타임이지만 더 길어질 수 있음)으로 Edge 서버에서 인증서를 설정합니다. \<datetime string of the effective time for new certificate\>|
|3|7/22/2015 6:00 AM - 7/22/2015 2:00 PM  <br/> 토큰의 유효성을 검사하기 위해 새 인증서가 먼저 시도되고 새 인증서가 토큰의 유효성을 검사하지 못하면 이전 인증서가 시도됩니다. 이 프로세스는 8시간(기본 토큰 수명) 겹침 기간 동안 모든 토큰에 사용됩니다.|
|4|종료: 2015년 7월 22일 오후 2:00:01  <br/> 이전 인증서가 만료되었으며 새 인증서가 인수되었습니다. Remove-CsCertificate -Type \<certificate usage type\> -Previous를 사용하여 이전 인증서를 안전하게 제거할 수 있습니다.|

유효 시간에 도달하면(2015년 7월 22일 오전 6:00:00) 모든 새 토큰이 새 인증서에서 발급됩니다. 토큰의 유효성을 검사할 때 토큰은 먼저 새 인증서에 대해 유효성을 검사합니다. 유효성 검사에 실패하면 이전 인증서가 시도됩니다. 새 인증서를 시도하고 이전 인증서로 되돌리는 프로세스는 이전 인증서의 만료 시간까지 계속됩니다. 이전 인증서가 만료되면(2015년 7월 22일 오후 2:00:00) 토큰은 새 인증서에서만 유효성을 검사합니다. 이전 매개 변수와 함께 Remove-CsCertificate cmdlet을 사용하여 이전 인증서를 안전하게 제거할 수 있습니다.

```PowerShell
Remove-CsCertificate -Type AudioVideoAuthentication -Previous
```

## <a name="to-update-or-renew-an-oauthtokenissuer-certificate-with-a--roll-and--effectivedate-parameters"></a>-Roll 및 -EffectiveDate 매개 변수를 사용하여 OAuthTokenIssuer 인증서를 업데이트하거나 갱신하려면

1. 관리자 그룹의 구성원으로 로컬 컴퓨터에 로그온합니다.

2. 프런트 엔드 서버의 기존 인증서에 대해 내보낼 수 있는 프라이빗 키가 있는 갱신 또는 새 OAuthTokenIssuer 인증서를 요청합니다.

3. 풀이 배포된 경우 새 OAuthTokenIssuer 인증서를 풀의 프런트 엔드 서버로 가져옵니다. OAuthTokenIssuer 인증서는 전역적으로 복제되며 배포의 모든 서버에서만 업데이트 및 갱신해야 합니다. 프런트 엔드 서버가 예로 사용됩니다.

4. Set-CsCertificate cmdlet을 사용하여 가져온 인증서를 구성하고 -EffectiveDate 매개 변수와 함께 -Roll 매개 변수를 사용합니다. 유효 날짜는 현재 인증서 만료 시간(14:00:00 또는 오후 2:00:00)에서 최소 24시간을 뺀 값으로 정의되어야 합니다.

    -Roll 및 -EffectiveTime 매개 변수가 있는 Set-CsCertificate 명령:

   ```PowerShell
   Set-CsCertificate -Type OAuthTokenIssuer -Thumbprint <thumbprint of new certificate> -Roll -EffectiveDate <date and time for certificate to become active> -identity Global
   ```

예제 Set-CsCertificate 명령:

  ```PowerShell
  Set-CsCertificate -Type OAuthTokenIssuer -Thumbprint "B142918E463981A76503828BB1278391B716280987B" -Roll -EffectiveDate "7/21/2015 1:00:00 PM"
  ```

> [!IMPORTANT]
> EffectiveDate는 서버의 지역 및 언어 설정과 일치하도록 형식이 지정되어야 합니다. 이 예제에서는 미국 영어 지역 및 언어 설정을 사용합니다.

유효 시간에 도달하면(2015년 7월 21일 오전 1:00:00) 모든 새 토큰이 새 인증서에서 발급됩니다. 토큰의 유효성을 검사할 때 토큰은 먼저 새 인증서에 대해 유효성을 검사합니다. 유효성 검사에 실패하면 이전 인증서가 시도됩니다. 새 인증서를 시도하고 이전 인증서로 되돌리는 프로세스는 이전 인증서의 만료 시간까지 계속됩니다. 이전 인증서가 만료되면(2015년 7월 22일 오후 2:00:00) 토큰은 새 인증서에서만 유효성을 검사합니다. 이전 매개 변수와 함께 Remove-CsCertificate cmdlet을 사용하여 이전 인증서를 안전하게 제거할 수 있습니다.

```PowerShell
Remove-CsCertificate -Type OAuthTokenIssuer -Previous
```

## <a name="see-also"></a>참고 항목

[비즈니스용 Skype 서버 서버-서버 인증(OAuth) 및 파트너 애플리케이션 관리](server-to-server-and-partner-applications.md)

[Set-CsCertificate](/powershell/module/skype/set-cscertificate)

[Remove-CsCertificate](/powershell/module/skype/remove-cscertificate)
