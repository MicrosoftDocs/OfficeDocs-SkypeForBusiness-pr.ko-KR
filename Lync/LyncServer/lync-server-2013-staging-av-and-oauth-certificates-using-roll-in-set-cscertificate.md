---
title: 설정-Set-cscertificate을 사용 하 여 준비 AV 및 OAuth 인증서
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Staging AV and OAuth certificates using -Roll in Set-CsCertificate
ms:assetid: 22dec3cc-4b6b-4df2-b269-5b35df4731a7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ660292(v=OCS.15)
ms:contentKeyID: 49354387
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ee572bbf115d1e83476194b0e5c92859886da42f
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42208411"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="staging-av-and-oauth-certificates-in-lync-server-2013-using--roll-in-set-cscertificate"></a>Lync Server 2013 using Set-cscertificate in-Roll에서 AV 및 OAuth 인증서 준비

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-11-13_

A/V (오디오/비디오) 통신은 Microsoft Lync Server 2013의 주요 구성 요소입니다. 응용 프로그램 공유 및 오디오 및 비디오 회의와 같은 기능은 A/V에 지 서비스에 할당 된 인증서, 특히 A/V 인증 서비스에 의존 합니다.

<div>


> [!IMPORTANT]
> <OL>
> <LI>
> <P>이 새로운 기능은 A/V에 지 서비스 및 <EM>Oauthtokenissuer</EM> 인증서에 작동 하도록 설계 되었습니다. 다른 인증서 유형은 A/V에 지 서비스 및 OAuth 인증서 유형과 함께 프로 비전 될 수 있지만 A/V에 지 서비스 인증서가 제공 하는 공존 동작은 도움이 되지 않습니다.</P>
> <LI>
> <P>Microsoft Lync Server 2013 인증서를 관리 하는 데 사용 되는 Lync Server 관리 셸 cmdlet은 A/V에 지 서비스 인증서를 <EM>오디오 Videoauthentication</EM> 인증서 유형으로, Oauthtokenissuer 형식 <EM></EM>으로 서는이를 참조 합니다. 이 항목의 나머지 부분에서는 인증서를 고유 하 게 식별 하기 위해 동일한 식별자 유형, <EM>오디오 Videoauthentication</EM> 및 <EM>Oauthtokenissuer</EM>를 참조 합니다.</P></LI></OL>



</div>

A/V 인증 서비스는 클라이언트 및 기타 A/V 소비자가 사용 하는 토큰을 발급 하는 역할을 합니다. 토큰은 인증서의 특성에서 생성 되며 인증서가 만료 되 면 새 인증서에서 생성 된 새 토큰을 사용 하 여 다시 참가 하기 위한 연결 및 요구 사항이 손실 됩니다. Lync Server 2013의 새로운 기능을 통해이 문제를 완화할 수 있으며, 이전 인증서가 만료 되는 시점을 새로운 상태로 유지 하 고 두 인증서를 모두 일정 기간 동안 계속 작동 하도록 허용할 능력이 있습니다. 이 기능은 Set-cscertificate Lync Server Management Shell cmdlet에서 업데이트 된 기능을 사용 합니다. 기존 매개 변수-EffectiveDate를 사용 하는 새 매개 변수-롤은 새 오디오 Videoauthentication 인증서를 인증서 저장소에 배치 합니다. 이전 오디오 Videoauthentication 인증서는 여전히 발급 된 토큰의 유효성을 검사 하기 위해 계속 유지 됩니다. 새 오디오 Videoauthentication 인증서를 현재 위치에 배치 하면 다음과 같은 일련의 이벤트가 발생 합니다.

<div>


> [!TIP]
> Lync Server 관리 셸 cmdlet을 사용 하 여 인증서를 관리 하는 경우에 지 서버에서 각 용도 마다 별도의 인증서를 요청할 수 있습니다. Lync Server 배포 마법사에서 인증서 마법사를 사용 하면 인증서를 만들 수 있지만 일반적으로 모든 인증서에 대해에 지 서버에서 단일 인증서로 사용 하는 <STRONG>기본</STRONG> 유형이 couples 됩니다. 롤링 인증서 기능을 사용 하려는 경우에는 다른 인증서 용도 로부터 오디오 Videoauthentication 인증서를 분리 하는 것이 좋습니다. 기본 유형의 인증서를 프로 비전 하 고 준비할 수 있지만 결합 된 인증서의 오디오 Videoauthentication 부분만 준비를 통해 혜택을 받습니다. 인증서가 만료 되는 경우 인스턴트 메시징 대화 (예:)는 액세스에 지 서비스와 연결 된 새 인증서를 사용 하기 위해 로그 아웃 하 고 다시 로그인 해야 하는 사용자입니다. 웹 회의에 지 서비스를 사용 하 여 웹에 관여 하는 사용자에 게 비슷한 동작이 발생 합니다. OAuthTokenIssuer 인증서는 모든 서버에서 공유 되는 특정 유형입니다. 한 위치에서 인증서를 만들고 관리 하 고 인증서가 중앙 관리 저장소에 다른 모든 서버에 대해 저장 됩니다.



</div>

Set-cscertificate cmdlet을 사용 하 고이를 사용 하 여 현재 인증서가 만료 되기 전에 인증서를 준비 하는 경우 옵션 및 요구 사항을 완전히 이해 하려면 추가 정보가 필요 합니다. – Roll 매개 변수는 중요 하지만 기본적으로 단일 용도로만 제공 됩니다. 매개 변수로 정의 하는 경우에는 인증서가 제공 될 때-Type (예: Set-cscertificate Videoauthentication 및 OAuthTokenIssuer)에 의해 정의 되는 영향을 받는 인증서에 대 한 정보를 제공할 것입니다. 라는 메시지가 나타납니다. EffectiveDate에서 정의 하는 유효 수준입니다.

**-롤:** – Roll 매개 변수는 필수 이며 종속성과 함께 함께 제공 해야 합니다. 영향을 받는 인증서와 적용 방법을 완전 하 게 정의 하는 데 필요한 매개 변수:

**-EffectiveDate:** -EffectiveDate 매개 변수는 새 인증서가 현재 인증서를 사용 하 여 공동 활성 상태가 되는 시기를 정의 합니다. – EffectiveDate은 현재 인증서의 만료 시간에 근접 하거나 시간이 길어질 수 있습니다. 오디오 Videoauthentication 인증서에 대 한 권장 최소 – EffectiveDate 8 시간이 며,이는 오디오 Videoauthentication 인증서를 사용 하 여 발급 된 AV에 지 서비스 토큰의 기본 토큰 수명입니다.

OAuthTokenIssuer 인증서를 준비할 때 선행 시간에 대 한 요구 사항에 따라 인증서가 유효 해질 수 있습니다. OAuthTokenIssuer 인증서가 선행 시간에 대해 수행 해야 하는 최소 시간은 현재 인증서의 만료 시간 보다 24 시간이 하입니다. 확장 된 리드 타임 인은 인증서가 생성 된 인증 및 암호화 키에 대 한 보존 시간이 길수록 OAuthTokenIssuer 인증서 (예: Exchange Server)에 종속 된 다른 서버 역할로 인해 발생 합니다. 자료.

**-지문:** 손도장은 해당 인증서에 고유한 인증서의 특성입니다. -Thumbprint 매개 변수는 Set-cscertificate cmdlet의 작업에 영향을 받는 인증서를 식별 하는 데 사용 됩니다.

**-Type:** – Type 매개 변수는 단일 인증서 사용 유형 또는 쉼표로 구분 된 인증서 사용 유형 목록을 사용할 수 있습니다. 인증서 유형은 cmdlet 및 서버에서 인증서의 용도를 식별 하는 유형입니다. 예를 들어 A/V에 지 서비스 및 AV 인증 서비스에서 다음을 사용 합니다. 다른 유형의 인증서를 준비 하 고 동시에 프로 비전 하는 경우에는 인증서에 대해 가장 오래 걸리는 최소 실제 소요 시간을 고려해 야 합니다. 예를 들어,에는 오디오 Videoauthentication 및 OAuthTokenIssuer 유형의 인증서를 준비 해야 합니다. 최소-EffectiveDate은 두 인증서 중 큰 값 이어야 합니다 (이 경우에는 최소 소요 시간이 24 시간인 OAuthTokenIssuer). 리드 인 24 시간 동안 오디오 Videoauthentication 인증서를 준비 하지 않으려면 요구 사항이 더 많은 EffectiveDate와 별도로 준비 합니다.

<div>

## <a name="to-update-or-renew-an-av-edge-service-certificate-with-a-roll-and--effectivedate-parameters"></a>-Roll 및-EffectiveDate 매개 변수를 사용 하 여 A/V에 지 서비스 인증서를 업데이트 하거나 갱신 하려면

1.  Administrators 그룹의 구성원으로 로컬 컴퓨터에 로그온 합니다.

2.  A/V에 지 서비스에서 기존 인증서에 대해 내보낼 수 있는 개인 키를 사용 하 여 갱신 또는 새 오디오 Videoauthentication 인증서를 요청 합니다.

3.  풀에 있는에 지 서버 및 다른 모든에 지 서버로 새 오디오 Videoauthentication 인증서를 가져옵니다 (풀이 배포 된 경우).

4.  Set-cscertificate cmdlet을 사용 하 여 가져온 인증서를 구성 하 고 – EffectiveDate 매개 변수와 함께 – Roll 매개 변수를 사용 합니다. 유효 날짜는 현재 인증서 만료 시간 (14:00:00 또는 2:00:00 PM)에서 토큰 수명 (기본값 8 시간)을 뺀 값으로 정의 해야 합니다. 이를 통해 인증서를 활성으로 설정 해야 할 시간이 제공 되 고-EffectiveDate \<문자열\>: "7/22/2012 6:00:00 AM"이 됩니다.
    
    <div>
    

    > [!IMPORTANT]
    > 에 지 풀의 경우에는 새 인증서를 사용 하 여 모든 클라이언트 및 소비자 토큰이 갱신 되기 전에 이전 인증서가 만료 될 때까지 가능한 한 A/V 통신 중단을 방지 하기 위해 배포 된 첫 번째 인증서의 – EffectiveDate 매개 변수에서 지정한 날짜 및 시간까지 모든 오디오 Videoauthentication 인증서를 배포 하 고 프로 비전 해야 합니다.

    
    </div>
    
    -Roll 및 – EffectiveTime 매개 변수를 사용 하는 Set-cscertificate 명령은 다음과 같습니다.
    
        Set-CsCertificate -Type AudioVideoAuthentication -Thumbprint <thumb print of new certificate> -Roll -EffectiveDate <date and time for certificate to become active>
    
    Set-cscertificate 명령 예:
    
        Set-CsCertificate -Type AudioVideoAuthentication -Thumbprint "B142918E463981A76503828BB1278391B716280987B" -Roll -EffectiveDate "7/22/2012 6:00:00 AM"
    
    <div>
    

    > [!IMPORTANT]
    > EffectiveDate 서버의 국가 및 언어 설정과 일치 하도록 형식을 지정 해야 합니다. 이 예제에서는 미국 영어 국가 및 언어 설정을 사용 합니다.

    
    </div>

Set-cscertificate,-롤 및-EffectiveDate에서 사용 중인 오디오 Videoauthentication의 유효성을 검사 하기 위해 기존 인증서를 계속 사용 하면서 새 오디오 Videoauthentication 토큰을 발급 하기 위한 새 인증서를 준비 하는 데 사용 되는 프로세스를 자세히 이해 하려면 기본적으로 시각적 시간 표시 막대는 프로세스를 이해 하는 효율적인 방법입니다.

다음 예에서 관리자는 A/V에 지 서비스 인증서가 07/22/2012에서 오후 2:00:00 시에 만료 되는 것으로 확인 합니다. 새 인증서를 요청 하 고 수신 하 여 해당 풀의 각에 지 서버로 가져옵니다. 오전 2 시 07/22/2012에는 Set-cscertificate를 사용 하 여 새 인증서의 지문 문자열과 같은 Get-07/22/2012 6:00:00 EffectiveTime을 실행 하기 시작 하 고,? 각에 지 서버에서이 명령을 실행 합니다.

![롤 및 EffectiveDate 매개 변수 사용](images/JJ660292.21d51a76-0d03-4ed7-a37e-a7c14940265f(OCS.15).jpg "롤 및 EffectiveDate 매개 변수 사용")

유효 시간에 도달 하면 (7/22/2012 6:00:00 AM) 새 인증서에서 모든 새 토큰을 발급 합니다. 토큰의 유효성을 검사 하는 경우 새 인증서에 대해 토큰의 유효성을 먼저 검사 합니다. 유효성 검사가 실패 하면 이전 인증서가 시도 됩니다. 이전 인증서의 만료 시간까지 새로 만들기를 시도 하는 프로세스는 계속 진행 됩니다. 이전 인증서가 만료 된 경우 (7/22/2012 2:00:00 PM), 새 인증서로만 토큰의 유효성을 검사 합니다. 이전 인증서는 – Previous 매개 변수와 함께 Set-cscertificate cmdlet을 사용 하 여 안전 하 게 제거할 수 있습니다.

    Remove-CsCertificate -Type AudioVideoAuthentication -Previous

</div>

<div>

## <a name="to-update-or-renew-an-oauthtokenissuer-certificate-with-a-roll-and--effectivedate-parameters"></a>-Roll 및-EffectiveDate 매개 변수를 사용 하 여 OAuthTokenIssuer 인증서를 업데이트 하거나 갱신 하려면

1.  Administrators 그룹의 구성원으로 로컬 컴퓨터에 로그온 합니다.

2.  A/V에 지 서비스에서 기존 인증서에 대해 내보낼 수 있는 개인 키를 사용 하 여 갱신 또는 새 OAuthTokenIssuer 인증서를 요청 합니다.

3.  풀을 배포한 경우 새 OAuthTokenIssuer 인증서를 해당 풀의 프런트 엔드 서버로 가져옵니다. OAuthTokenIssuer 인증서는 전역적으로 복제 되며, 배포의 모든 서버에서 업데이트 및 갱신 하기만 하면 됩니다. 프런트 엔드 서버는 예제로 사용 됩니다.

4.  Set-cscertificate cmdlet을 사용 하 여 가져온 인증서를 구성 하 고 – EffectiveDate 매개 변수와 함께 – Roll 매개 변수를 사용 합니다. 유효 날짜는 현재 인증서 만료 시간 (14:00:00 또는 2:00:00 PM)에서 최소 24 시간을 뺀 값으로 정의 해야 합니다.
    
    -Roll 및 – EffectiveTime 매개 변수를 사용 하는 Set-cscertificate 명령은 다음과 같습니다.
    
        Set-CsCertificate -Type OAuthTokenIssuer -Thumbprint <thumb print of new certificate> -Roll -EffectiveDate <date and time for certificate to become active>
    
    Set-cscertificate 명령 예:
    
        Set-CsCertificate -Type OAuthTokenIssuer -Thumbprint "B142918E463981A76503828BB1278391B716280987B" -Roll -EffectiveDate "7/21/2012 1:00:00 PM"
    
    <div>
    

    > [!IMPORTANT]
    > EffectiveDate 서버의 국가 및 언어 설정과 일치 하도록 형식을 지정 해야 합니다. 이 예제에서는 미국 영어 국가 및 언어 설정을 사용 합니다.

    
    </div>

유효 시간에 도달 하면 (7/21/2012 1:00:00 AM) 새 인증서에서 모든 새 토큰을 발급 합니다. 토큰의 유효성을 검사 하는 경우 새 인증서에 대해 토큰의 유효성을 먼저 검사 합니다. 유효성 검사가 실패 하면 이전 인증서가 시도 됩니다. 이전 인증서의 만료 시간까지 새로 만들기를 시도 하는 프로세스는 계속 진행 됩니다. 이전 인증서가 만료 된 경우 (7/22/2012 2:00:00 PM), 새 인증서로만 토큰의 유효성을 검사 합니다. 이전 인증서는 – Previous 매개 변수와 함께 Set-cscertificate cmdlet을 사용 하 여 안전 하 게 제거할 수 있습니다.

    Remove-CsCertificate -Type OAuthTokenIssuer -Previous

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013의에 지 서버 인증서 계획](lync-server-2013-plan-for-edge-server-certificates.md)  
[Lync Server 2013에서 서버 간 인증 (OAuth) 및 파트너 응용 프로그램 관리](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md)  


[Lync Server 2013에 대 한에 지 인증서 설정](lync-server-2013-set-up-edge-certificates.md)  
[Set-cscertificate](https://technet.microsoft.com/library/Gg398518(v=OCS.15))  
[Set-cscertificate을 제거 합니다.](https://technet.microsoft.com/library/Gg412895(v=OCS.15))  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

