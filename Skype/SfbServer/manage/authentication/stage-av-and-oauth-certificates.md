---
title: 비즈니스용 Skype Server using-CsCertificate에 대 한 AV 및 OAuth 인증서 스테이지 설정-롤백
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
ms.assetid: 22dec3cc-4b6b-4df2-b269-5b35df4731a7
description: '요약: 비즈니스용 Skype 서버용으로 AV 및 OAuth 인증서를 준비 합니다.'
ms.openlocfilehash: 530e8f603d2c5be368df37354c3974e2b5abeb5a
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818730"
---
# <a name="stage-av-and-oauth-certificates-in-skype-for-business-server-using--roll-in-set-cscertificate"></a>비즈니스용 Skype Server using-CsCertificate에 대 한 AV 및 OAuth 인증서 스테이지 설정-롤백
 
**요약:** 비즈니스용 Skype 서버용으로 AV 및 OAuth 인증서를 준비 합니다.
  
오디오/비디오 (A/V) 통신은 비즈니스용 Skype 서버의 주요 구성 요소입니다. 응용 프로그램 공유 및 오디오, 비디오 회의 등의 기능은 A/V Edge 서비스에 할당 된 인증서, 특히 A/V 인증 서비스에 의존 합니다.
  
> [!IMPORTANT]
> 이 새로운 기능은 A/V Edge 서비스와 OAuthTokenIssuer 인증서에 사용할 수 있도록 설계 되었습니다. 다른 인증서 유형은 A/V Edge 서비스 및 OAuth 인증서 유형과 함께 프로 비전 할 수 있지만, A/V Edge 서비스 인증서가 제공 하는 공존 동작에는 도움이 되지 않습니다.
  
비즈니스용 Skype 서버 인증서를 관리 하는 데 사용 되는 비즈니스용 Skype 서버 관리 셸 PowerShell cmdlet은 A/V Edge 서비스 인증서를 오디오 Videoauthentication 인증서 유형으로, OAuthServer 인증서를 typeOAuthTokenIssuer로 지칭 합니다. 이 항목의 나머지 부분에서 인증서를 고유 하 게 식별 하기 위해 동일한 식별자 형식, 오디오 Videoauthentication andOAuthTokenIssuer를 참조 합니다.
  
A/V 인증 서비스는 클라이언트 및 다른 A/V 소비자가 사용 하는 토큰 발급을 담당 합니다. 토큰이 인증서의 특성 으로부터 생성 되 고, 인증서가 만료 되 면 새 인증서에서 생성 된 새 토큰으로 다시 참가 하는 데 필요한 연결 및 요구 사항이 손실 됩니다. 비즈니스용 Skype Server의 새로운 기능은이 문제를 해결 하는 것으로, 오래 된 인증서가 만료 되는 것을 미리 하 고, 두 인증서가 일정 기간 동안 계속 해 서 작동할 수 있도록 하는 기능입니다. 이 기능은 CsCertificate Skype for Business Server Management Shell cmdlet에서 업데이트 된 기능을 사용 합니다. 기존 매개 변수-EffectiveDate를 사용 하는 새 매개 변수-롤은 새 오디오 Videoauthentication 인증서를 인증서 저장소에 배치 합니다. 이전 오디오 Videoauthentication 인증서는 계속 해 서 발급 된 토큰의 유효성 검사를 위해 유지 됩니다. 새 오디오 Videoauthentication 인증서를 현재 위치에 배치 하는 것부터 다음 일련의 이벤트가 발생 합니다.
  
> [!TIP]
> Skype for Business Server 관리 셸 cmdlet을 사용 하 여 인증서를 관리 하는 경우에는 Edge 서버의 각 용도에 대해 별도의 인증서를 요청할 수 있습니다. 비즈니스용 Skype 서버 배포 마법사에서 인증서 마법사를 사용 하면 인증서를 만드는 데 도움이 되지만, 일반적으로 모든 인증서가 Edge 서버에서 단일 인증서로 사용 하는 couples **기본** 유형이 있습니다. 롤링 인증서 기능을 사용 하는 경우에는 다른 인증서 용도에서 오디오 Videoauthentication 인증서를 분리할 때 권장 되는 방법입니다. 기본 형식의 인증서를 프로 비전 하 고 준비할 수 있지만, 결합 된 인증서의 오디오 Videoauthentication 부분만 스테이징에서 혜택을 받습니다. 인증서가 만료 되 면 인스턴트 메시지 대화와 관련 된 사용자 (예:)가 로그 아웃 하 고 다시 로그인 해야 액세스에 지 서비스와 연결 된 새 인증서를 사용할 수 있습니다. 웹 회의에 참여 하는 사용자에 대 한 유사한 동작이 웹 회의에 지 서비스를 사용 하는 경우 발생 합니다. OAuthTokenIssuer 인증서는 모든 서버에서 공유 되는 특정 유형입니다. 한 곳에서 인증서를 만들고 관리 하며, 인증서는 중앙 관리 저장소에 다른 모든 서버에 대해 저장 됩니다.
  
CsCertificate cmdlet을 사용 하 고 현재 인증서가 만료 되기 전에 인증서를 준비 하는 데 사용 하는 경우 옵션 및 요구 사항을 완전히 이해 하려면 추가 세부 정보가 필요 합니다. -롤 매개 변수는 중요 하지만 단일 용도로만 가능 합니다. 이를 매개 변수로 정의 하는 경우-CsCertificate에 따라 영향을 받을 인증서에 대 한 정보를 제공 하는 것입니다 (예:, 인증서가 표시 되는 경우). EffectiveDate에서 효율적으로 정의 합니다.
  
 **-롤**:-롤 매개 변수는 필수 이며 종속성이 함께 제공 되어야 합니다. 영향을 받을 인증서와 적용 방법을 완전히 정의 하는 데 필요한 매개 변수:
  
 **-EffectiveDate**: EffectiveDate 매개 변수는 새 인증서가 현재 인증서와 공동 활성 상태가 되는 시간을 정의 합니다. -EffectiveDate 현재 인증서의 만료 시간에 가까운 시간 이거나 시간이 길어질 수 있습니다. 오디오 Videoauthentication 인증서에 대 한 권장 최소 EffectiveDate 8 시간이 며,이는 오디오 Videoauthentication 인증서를 사용 하 여 발급 된 AV Edge 서비스 토큰의 기본 토큰 수명입니다.
  
OAuthTokenIssuer 인증서를 준비할 때 선행 시간에 대 한 요구 사항이 서로 다르므로 인증서가 유효 하 게 됩니다. OAuthTokenIssuer 인증서가 선행 시간에 있어야 하는 최소 시간은 현재 인증서의 만료 시간 보다 24 시간입니다. 함께 사용할 경우 인증서 생성 인증 및 암호화 키에 대 한 보존 시간이 오래 걸리는 OAuthTokenIssuer 인증서 (예: Exchange Server)에 종속 된 다른 서버 역할 때문에 겹치는 시간을 연장 합니다. 내용이.
  
 **-지문**: 손도장은 해당 인증서에 고유한 인증서의 특성입니다. -Thumbprint 매개 변수는 CsCertificate cmdlet의 동작에 영향을 받을 인증서를 식별 하는 데 사용 됩니다.
  
 **-Type**:-type 매개 변수는 단일 인증서 사용 유형을 허용 하거나 쉼표로 구분 된 인증서 용도 유형을 나열할 수 있습니다. 인증서 종류는 cmdlet을 식별 하는 파일과 서버에서 인증서의 용도입니다. 예를 들어, A/V Edge 서비스와 AV 인증 서비스에서 사용 하는 e Videoauthentication을 입력 합니다. 다른 유형의 인증서를 준비 하 고 동시에 제공 하기로 결정 한 경우, 인증서에 대해 가장 오래 걸리는 최소 유효 리드 시간을 고려해 야 합니다. 예를 들어, 오디오 Videoauthentication 및 OAuthTokenIssuer 유형의 인증서를 준비 해야 합니다. 최소 EffectiveDate는 두 인증서 중 큰 것 이어야 하며,이 경우에는 최소 소요 시간이 24 시간인 OAuthTokenIssuer입니다. 리드 시간을 24 시간으로 하는 오디오 Videoauthentication 인증서를 준비 하지 않으려면 요구 사항에 더 많은 EffectiveDate을 별도로 처리 합니다.
  
### <a name="to-update-or-renew-an-av-edge-service-certificate-with-a--roll-and--effectivedate-parameters"></a>-롤 및-EffectiveDate 매개 변수를 사용 하 여 A/V Edge 서비스 인증서를 업데이트 하거나 갱신 하려면

1. 로컬 컴퓨터에 관리자 그룹의 구성원으로 로그온 합니다.
    
2. A/V Edge 서비스의 기존 인증서에 대 한 내보낼 수 있는 개인 키를 사용 하 여 갱신 또는 새 오디오 Videoauthentication 인증서를 요청 합니다.
    
3. 새 오디오 Videoauthentication 인증서를 Edge 서버 및 풀의 다른 모든 Edge 서버로 가져옵니다 (풀을 배포한 경우).
    
4. Set-CsCertificate cmdlet을 사용 하 여 가져온 인증서를 구성 하 고-Roll 매개 변수를-EffectiveDate 매개 변수와 함께 사용 합니다. 유효 날짜는 현재 인증서 만료 시간 (14:00:00 또는 2:00:00 PM)에서 토큰 수명 (기본적으로 8 시간)을 뺀 값으로 정의 되어야 합니다. 이렇게 하면 인증서를 활성으로 설정 해야 하 고-EffectiveDate \<문자열\>: "7/22/2015 6:00:00 AM"이 됩니다. 
    
    > [!IMPORTANT]
    > Edge 풀의 경우, 새 인증서를 사용 하 여 모든 클라이언트 및 소비자 토큰이 갱신 되기 전에 오래 된 인증서가 만료 되는 것을 방지 하기 위해 배포 되는 첫 번째 인증서의-EffectiveDate 매개 변수를 통해 배포 및 프로 비전 된 모든 오디오 Videoauthentication 인증서가 있어야 합니다. 
  
    CsCertificate 명령은-롤 및-EffectiveTime 매개 변수를 사용 합니다.
    
   ```PowerShell
   Set-CsCertificate -Type AudioVideoAuthentication -Thumbprint
          <thumb print of new certificate> -Roll -EffectiveDate <date and time
          for certificate to become active>
   ```

    CsCertificate 명령 예:
    
   ```PowerShell
   Set-CsCertificate -Type AudioVideoAuthentication -Thumbprint
          "B142918E463981A76503828BB1278391B716280987B" -Roll -EffectiveDate "7/22/2015
          6:00:00 AM"
   ```

    > [!IMPORTANT]
    > EffectiveDate는 서버의 국가 및 언어 설정에 맞게 형식이 지정 되어야 합니다. 이 예제에서는 미국 영어 국가 및 언어 설정을 사용 합니다. 
  
CsCertificate,-롤 및-EffectiveDate에서 사용 중인 추가 기능을 확인 하기 위해 기존 인증서를 사용 하는 동안 새 오디오 Videoauthentication 토큰을 발급 하는 데 사용 되는 새 인증서를 준비 하는 프로세스에 대해 자세히 알아보려면 소비자에 따라 시각적 시간 표시 막대는 프로세스를 이해 하는 효과적인 방법입니다. 다음 예제에서 관리자는 A/V Edge 서비스 인증서가 07/22/2015에서 2:00:00 PM에 만료 되는 것으로 판단 합니다. 새 인증서를 요청 하 고 해당 풀의 각 Edge 서버로 가져옵니다. 2 07/22/2015 AM에는 CsCertificate with-롤,-지문을 새 인증서의 손도장 문자열과 동일 하 게,-EffectiveTime를 07/22/2015 6:00:00 AM으로 설정 하는 작업이 시작 됩니다. 각 Edge 서버에서이 명령을 실행 합니다.
  
![Roll 및 EffectiveDate 매개 변수 사용.](../../media/Ops_Certificate_Set_Roll_EffectiveTime_Timeline.jpg)
  
|**호출**|**단계별**|
|:-----|:-----|
|1  <br/> |시작: 7/22/2015 12:00:00 오전  <br/> 현재 오디오 Videoauthentication 인증서는 7/22/2015의 2:00:00 PM에 만료 되기 때문입니다. 이는 인증서의 만료 된 타임 스탬프에 따라 결정 됩니다. 기존 인증서가 만료 시간에 도달 하기 전에 8 시간의 겹치기 (기본 토큰 수명)을 고려 하 여 인증서를 대체 하 고 롤오버를 계획 합니다. 이 예제에서는 관리자가 6:00:00 AM 유효 시간 이전에 새 인증서를 배치 하 고 프로 비전 하는 데 적절 한 시간을 허용 하기 위해 2:00:00 AM 시간을 사용 합니다.  <br/> |
|2  <br/> |7/22/2015 2:00:00 AM-7/22/2015 5:59:59 AM  <br/> 유효 시간이 6:00:00 AM 인 Edge 서버의 인증서 설정 (4 시간 리드 타임은이 예제의 경우 \<) CsCertificate 인증서 사용 형식\> -지문 \<지문 (새 인증서의 유효 시간\> -롤-EffectiveDate \<datetime 문자열 사용)\>  <br/> |
|3  <br/> |7/22/2015 6:00 AM-7/22/2015 2:00 PM  <br/> 토큰의 유효성을 검사 하려면 새 인증서가 먼저 시도 되 고 새 인증서가 토큰의 유효성을 검사 하지 못하면 이전 인증서가 시도 됩니다. 이 프로세스는 8 시간 (기본 토큰 수명) 기간 동안 모든 토큰에 사용 됩니다.  <br/> |
|4(tcp/ipv4)  <br/> |종료: 7/22/2015 2:00:01 PM  <br/> 오래 된 인증서가 만료 되 고 새 인증서가 걸렸습니다. CsCertificate \<인증서 용도 유형을\> 제거 하 여 이전 인증서를 안전 하 게 제거할 수 있습니다.  <br/> |
   
유효 시간 (7/22/2015 6:00:00 AM)에 도달 하면 새 인증서가 모든 새 토큰을 발급 합니다. 토큰의 유효성을 검사할 때 새 인증서에 대해 토큰의 유효성이 먼저 검사 됩니다. 유효성 검사에 실패 하면 이전 인증서가 시도 됩니다. 이전 인증서로 새 응답을 시도 하는 프로세스는 이전 인증서의 만료 시간까지 계속 됩니다. 이전 인증서가 만료 된 경우 (7/22/2015 2:00:00 PM), 새 인증서로만 토큰의 유효성을 검사할 수 있습니다. 이전 인증서는-Previous 매개 변수와 함께 CsCertificate cmdlet을 사용 하 여 안전 하 게 제거할 수 있습니다.

```PowerShell
Remove-CsCertificate -Type AudioVideoAuthentication -Previous
```

### <a name="to-update-or-renew-an-oauthtokenissuer-certificate-with-a--roll-and--effectivedate-parameters"></a>-롤 및-EffectiveDate 매개 변수를 사용 하 여 OAuthTokenIssuer 인증서를 업데이트 하거나 갱신 하려면

1. 로컬 컴퓨터에 관리자 그룹의 구성원으로 로그온 합니다.
    
2. 프런트 엔드 서버의 기존 인증서에 대 한 내보낼 수 있는 개인 키를 사용 하 여 갱신 또는 새 OAuthTokenIssuer 인증서를 요청 합니다.
    
3. 풀의 프런트 엔드 서버로 새 OAuthTokenIssuer 인증서를 가져옵니다 (풀을 배포한 경우). OAuthTokenIssuer 인증서는 전역적으로 복제 되며 배포의 모든 서버에서 업데이트 되 고 갱신 하기만 하면 됩니다. 프런트 엔드 서버는 예제로 사용 됩니다.
    
4. Set-CsCertificate cmdlet을 사용 하 여 가져온 인증서를 구성 하 고-Roll 매개 변수를-EffectiveDate 매개 변수와 함께 사용 합니다. 유효 날짜는 최소 24 시간을 뺀 현재 인증서 만료 시간 (14:00:00 또는 2:00:00 PM)으로 정의 되어야 합니다. 
    
    CsCertificate 명령은-롤 및-EffectiveTime 매개 변수를 사용 합니다.
    
   ```PowerShell
   Set-CsCertificate -Type OAuthTokenIssuer -Thumbprint <thumb
          print of new certificate> -Roll -EffectiveDate <date and time for
          certificate to become active> -identity Global 
   ```

CsCertificate 명령 예:
    
  ```PowerShell
  Set-CsCertificate -Type OAuthTokenIssuer -Thumbprint
          "B142918E463981A76503828BB1278391B716280987B" -Roll -EffectiveDate "7/21/2015
          1:00:00 PM" 
  ```

> [!IMPORTANT]
> EffectiveDate는 서버의 국가 및 언어 설정에 맞게 형식이 지정 되어야 합니다. 이 예제에서는 미국 영어 국가 및 언어 설정을 사용 합니다. 
  
유효 시간 (7/21/2015 1:00:00 AM)에 도달 하면 새 인증서가 모든 새 토큰을 발급 합니다. 토큰의 유효성을 검사할 때 새 인증서에 대해 토큰의 유효성이 먼저 검사 됩니다. 유효성 검사에 실패 하면 이전 인증서가 시도 됩니다. 이전 인증서로 새 응답을 시도 하는 프로세스는 이전 인증서의 만료 시간까지 계속 됩니다. 이전 인증서가 만료 된 경우 (7/22/2015 2:00:00 PM), 새 인증서로만 토큰의 유효성을 검사할 수 있습니다. 이전 인증서는-Previous 매개 변수와 함께 CsCertificate cmdlet을 사용 하 여 안전 하 게 제거할 수 있습니다.
```PowerShell
Remove-CsCertificate -Type OAuthTokenIssuer -Previous 
```

## <a name="see-also"></a>참고 항목

[비즈니스용 Skype 서버에서 OAuth (서버 간 인증) 및 파트너 응용 프로그램 관리](server-to-server-and-partner-applications.md)

[Set-CsCertificate](https://docs.microsoft.com/powershell/module/skype/set-cscertificate?view=skype-ps)
  
[제거-CsCertificate](https://docs.microsoft.com/powershell/module/skype/remove-cscertificate?view=skype-ps)
