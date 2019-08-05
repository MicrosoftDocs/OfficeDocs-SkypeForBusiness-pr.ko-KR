---
title: 비즈니스용 Skype 서버 2015 음성 사서함에 대해 Exchange Server 2013 통합 메시징 구성
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/11/2019
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 1be9c4f4-fd8e-4d64-9798-f8737b12e2ab
description: '요약: 비즈니스용 Skype 서버 음성 메일에 대 한 Exchange Server 통합 메시징을 구성 합니다.'
ms.openlocfilehash: a1c83b4ec92e6e3b3d678d2d7e0a65f58fc9d6ce
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36188148"
---
# <a name="configure-exchange-server-unified-messaging-for-skype-for-business-server-voice-mail"></a>비즈니스용 Skype 서버 2015 음성 사서함에 대해 Exchange Server 2013 통합 메시징 구성
 
**요약:** 비즈니스용 Skype 서버 음성 메일에 대 한 Exchange Server 통합 메시징을 구성 합니다.
  
비즈니스용 Skype Server를 사용 하 여 Exchange Server 2016 또는 Exchange Server 2013에 저장 된 보이스 메일 메시지를 할 수 있습니다. 그러면 해당 보이스 메일 메시지가 사용자의 받은 편지함에 전자 메일 메시지로 표시 됩니다. 

> [!NOTE]
> 이전에는 알려진 exchange 통합 메시징 기능을 Exchange 2019에서 더 이상 사용할 수 없지만, 전화 시스템을 사용 하 여 음성 메일 메시지를 기록한 다음 사용자의 Exchange 사서함에 녹음/녹화 된 상태로 남겨둘 수도 있습니다. 자세한 내용은 [클라우드 보이스 메일 서비스 계획](../../../sfbhybrid/hybrid/plan-cloud-voicemail.md) 을 참조 하세요.
  
비즈니스용 Skype 서버와 Exchange Server 2016 또는 Exchange Server 2013 간에 서버 간 인증을 이미 구성한 경우에는 통합 메시징을 설정할 준비가 된 것입니다. 이렇게 하려면 먼저 Exchange Server에서 새 통합 메시징 다이얼 플랜을 만들고 할당 해야 합니다. 예를 들어 Exchange 관리 셸에서 실행 되는 다음 두 명령은 Exchange에 대 한 새로운 3 자리 다이얼 플랜을 구성 합니다.
  
```
New-UMDialPlan -Name "RedmondDialPlan" -VoIPSecurity "Secured" -NumberOfDigitsInExtension 3 -URIType "SipName" -CountryOrRegionCode 1
Set-UMDialPlan "RedmondDialPlan" -ConfiguredInCountryOrRegionGroups "Anywhere,*,*,*" -AllowedInCountryOrRegionGroups "Anywhere"
```

이 예제에서는 VoIPSecurity 매개 변수를 사용 하 고 매개 변수 값이 "보안"으로 표시 되는 첫 번째 명령은 신호 채널이 TLS (전송 계층 보안)를 통해 암호화 됨을 나타냅니다. URIType는 SIP 프로토콜을 사용 하 여 메시지를 보내고 받을 수 있으며, CountryOrRegionCode는 다이얼 플랜이 미국에 적용 됨을 나타냅니다.
  
두 번째 명령에서 ConfiguredInCountryOrRegionGroups 매개 변수에 전달 된 매개 변수 값은이 다이얼 플랜에 사용할 수 있는 국내 그룹을 지정 합니다. 매개 변수 값 "임의의 위치\*,\*,\*"는 다음을 설정 합니다.
  
- 그룹 이름 ("어디서")
    
- Allowed번호 문자열 (\*즉, 숫자 문자열이 허용 됨을 나타내는 와일드 카드 문자)
    
- DialNumberString (\*즉, 전화 번호가 허용 됨을 나타내는 와일드 카드 문자)
    
- TextComment (\*즉, 모든 텍스트 명령이 허용 됨을 나타내는 와일드 카드 문자)
    
> [!NOTE]
> 새 다이얼 플랜을 만들면 기본 사서함 정책만 생성 됩니다. 
  
새 다이얼 플랜을 만들고 구성한 후에는 통합 메시징 서버에 새 다이얼 플랜을 추가 하 고 해당 서버의 시작 모드를 수정 해야 합니다. 특히 시작 모드를 "이중"으로 설정 해야 합니다. Exchange 관리 셸에서는 다음 두 작업을 모두 수행할 수 있습니다.
  
```
Set-UmService -Identity "atl-exchangeum-001.litwareinc.com" -DialPlans "RedmondDialPlan" -UMStartupMode "Dual"
```

통합 메시징 서버를 구성한 후에는 다음 ExchangeCertificate cmdlet을 실행 하 여 Exchange 인증서가 통합 메시징 서비스에 적용 되었는지 확인 해야 합니다.
  
```
Enable-ExchangeCertificate -Server "atl-umserver-001.litwareinc.com" -Thumbprint "EA5A332496CC05DA69B75B66111C0F78A110D22d" -Services "SMTP","IIS","UM"
```

인증서를 올바르게 할당 한 후에는 통합 메시징 서버에서 MsExchangeUM 서비스를 중지 하 고 다시 시작 해야 합니다. 시작 모드를 변경할 때마다이 서비스를 중지 하 고 다시 시작 해야 합니다.
  
통합 메시징 서버의 구성을 마친 후에는 UM 호출 라우터를 구성할 수 있습니다.
  
```
Set-UMCallRouterSettings -Server "atl-exchange-001.litwareinc.com" -UMStartupMode "Dual" -DialPlans "RedmondDialPlan" 
Enable-ExchangeCertificate -Server "atl-umserver-001.litwareinc.com" -Thumbprint "45BAA32496CC891169B75B9811320F78A1075DDA" -Services "IIS","UMCallRouter"
```

시작 모드가 변경 되었기 때문에 UM 통화 라우터를 호스트 하는 컴퓨터에서 MsExchangeUMCR 서비스를 중지 하 고 다시 시작 해야 합니다.
  
통합 메시징 설정을 완료 하려면 UM 사서함 정책을 만든 다음 해당 정책을 사용 하 여 사용자가 통합 메시징을 사용할 수 있도록 해야 합니다. 다음과 같은 명령을 사용 하 여 사서함 정책을 만들 수 있습니다.
  
```
New-UMMailboxPolicy -Name "RedmondMailboxPolicy" -AllowedInCountryOrRegionGroups "Anywhere"
```

그리고 다음과 같은 명령을 사용 하 여 사용자에 게 통합 메시징을 사용할 수 있습니다.
  
```
Enable-UMMailbox -Extensions 100 -SIPResourceIdentifier "kenmyer@litwareinc.com" -Identity "litwareinc\kenmyer" -UMMailboxPolicy "RedmondMailboxPolicy"
```

앞의 명령에서 Extensions 매개 변수는 사용자의 내선 번호를 나타냅니다. 이 예제에서 사용자는 내선 번호 100를 사용 합니다.
  
사서함을 사용 하도록 설정한 후에는 사용자 kenmyer@litwareinc.com Exchange 통합 메시징을 사용할 수 있어야 합니다. 비즈니스용 Skype Server Management Shell 내에서 [CsExUMConnectivity](https://docs.microsoft.com/powershell/module/skype/test-csexumconnectivity?view=skype-ps) cmdlet을 실행 하 여 사용자가 Exchange UM에 연결할 수 있는지 확인할 수 있습니다.
  
```
$credential = Get-Credential "litwareinc\kenmyer"
Test-CsExUMConnectivity -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential
```

통합 메시징을 사용 하도록 설정 된 두 번째 사용자가 있는 경우,이 두 번째 사용자 [](https://docs.microsoft.com/powershell/module/skype/test-csexumvoicemail?view=skype-ps) 가 첫 번째 사용자에 대 한 보이스 메일 메시지를 남길 수 있는지 여부를 확인할 수 있습니다.
  
```
$credential = Get-Credential "litwareinc\pilar"
Test-CsExUMVoiceMail -TargetFqdn "atl-cs-001.litwareinc.com" -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -SenderSipAddress "sip:pilar@litwareinc.com" -SenderCredential $credential
```



## <a name="configuring-unified-messaging-on-microsoft-exchange-server"></a>Microsoft Exchange Server에서 통합 메시징 구성 
> [!IMPORTANT]
> UM (통합 메시징)를 사용 하 여 엔터프라이즈 음성 사용자에 대 한 전화 응답, Outlook Voice Access 또는 자동 전화 교환 서비스를 제공 하려는 경우 [비즈니스용 Skype에서 Exchange 통합 메시징 통합에 대 한 계획](../../plan-your-deployment/integrate-with-exchange/unified-messaging.md)을 읽고 다음을 따르세요. 이 섹션에 설명 되어 있습니다. 

엔터프라이즈 음성으로 작업 하도록 Exchange UM (통합 메시징)를 구성 하려면 다음 작업을 수행 해야 합니다.

- Exchange UM (통합 메시징) 서비스를 실행 하는 서버에서 인증서 구성
  > [!NOTE]
  > 모든 클라이언트 액세스 및 사서함 서버를 모든 UM SIP URI 다이얼 플랜에 추가 합니다. 그렇지 않은 경우에는 아웃 바운드 통화 라우팅이 예상 대로 작동 하지 않습니다. 
- 필요에 따라 하나 이상의 UM SIP URI 다이얼 플랜을 구독자 액세스 전화 번호와 함께 만든 다음 해당 하는 L 다이얼 플랜을 만듭니다.

- Exchucutil 스크립트를 사용 하 여 다음을 수행 합니다.
    - UM IP 게이트웨이를 만듭니다.
    - UM 헌트 그룹을 만듭니다.
    - 비즈니스용 Skype Server에서 UM Active Directory 도메인 서비스 개체를 읽을 수 있는 권한을 부여 합니다.
- UM 자동 전화 교환 개체를 만듭니다.
- 구독자 액세스 개체를 만듭니다.
- 각 사용자에 대해 SIP URI를 만들고 사용자를 UM SIP URI 다이얼 플랜에 연결 합니다.

### <a name="requirements-and-recommendations"></a>요구 사항 및 제안

시작 하기 전에이 섹션의 문서에서는 클라이언트 액세스 및 사서함과 같은 Exchange 역할을 배포한 것으로 가정 합니다. Microsoft Exchange Server에서는 Exchange UM을 이러한 서버에서 서비스로 실행 합니다.

또한 다음을 참고 하세요.
- Exchange UM을 여러 포리스트에 설치 하는 경우 각 UM 포리스트에 대해 Exchange Server 통합 단계를 수행 해야 합니다. 또한 각 UM 포리스트는 비즈니스용 Skype 서버를 배포 하는 포리스트를 신뢰 하도록 구성 해야 하며, 비즈니스용 whichSkype Server의 포리스트가 각 UM 포리스트를 신뢰 하도록 구성 해야 합니다.
- 통합 메시징 서비스가 실행 되는 Exchange 서버 역할과 비즈니스용 Skype 서버를 실행 하는 서버에 대 한 통합 단계를 수행 합니다. Lync Server 2013 통합 단계를 수행 하기 전에 Exchange Server 통합 메시징 통합 단계를 수행 해야 합니다.
  > [!NOTE]
  > 어떤 서버와 어떤 관리자 역할에 대해 어떤 통합 단계를 수행 해야 하는지 확인 하려면 [온-프레미스 통합 메시징과 비즈니스용 Skype 통합에 대 한 배포 프로세스 개요](../../plan-your-deployment/integrate-with-exchange/deployment-overview.md)를 참조 하세요. 

Exchange UM을 (를) 실행 하는 각 서버에서 다음 도구를 사용할 수 있어야 합니다.
- Exchange 관리 셸
- 다음 작업을 수행 하는 exchucutil 스크립트.
    - 각 비즈니스용 Skype Server에 대해 UM IP 게이트웨이를 만듭니다.
    - 각 게이트웨이에 대 한 헌트 그룹을 만듭니다. 각 헌트 그룹의 파일럿 식별자는 게이트웨이와 연결 된 프런트 엔드 풀 또는 Standard Edition 서버에서 사용 하는 UM SIP URI 다이얼 플랜을 지정 합니다.
    - Active Directory 도메인 서비스에서 Exchange UM 개체를 읽을 수 있는 비즈니스용 Skype Server 권한을 부여 합니다.



### <a name="configure-unified-messaging-on-microsoft-exchange-with-exchucutilps1"></a>ExchUCUtil를 사용 하 여 Microsoft Exchange에서 통합 메시징 구성 

Exchange UM (통합 메시징)과 함께 Microsoft 비즈니스용 Skype 서버를 통합 하는 경우 셸에서 ExchUcUtil 스크립트를 실행 해야 합니다. ExchUcUtil 스크립트는 다음을 수행 합니다.

- 각 비즈니스용 Skype Server 풀에 대해 UM IP 게이트웨이를 만듭니다.

> [!IMPORTANT]
> ExchUcUtil 스크립트는 하나 이상의 UM IP 게이트웨이를 만듭니다. 스크립트에서 만든 게이트웨이를 제외한 모든 UM IP 게이트웨이에서 나가는 호출을 사용 하지 않도록 설정 해야 합니다. 여기에는 스크립트를 실행 하기 전에 만든 UM IP 게이트웨이에서 나가는 호출을 사용 하지 않도록 설정 하는 것이 포함 됩니다. 

- 각 UM IP 게이트웨이에 대해 UM 헌트 그룹을 만듭니다. 각 헌트 그룹의 파일럿 식별자는 UM IP 게이트웨이와 연결 된 비즈니스용 Skype 서버 프런트 엔드 풀 또는 Standard Edition 서버에서 사용 하는 UM SIP URI 다이얼 플랜을 지정 합니다.
- UM 다이얼 플랜, 자동 전화 교환, UM IP 게이트웨이, UM 헌트 그룹과 같은 Active Directory UM 컨테이너 개체를 읽을 수 있는 비즈니스용 Skype Server 권한을 부여 합니다.
  > [!IMPORTANT]
  > 각 UM 포리스트는 비즈니스용 Skype 서버가 배포 되는 포리스트를 신뢰 하도록 구성 해야 하며, 비즈니스용 Skype 서버 2013이 배포 되는 포리스트를 각 UM 포리스트를 신뢰 하도록 구성 해야 합니다. Exchange UM을 여러 포리스트에 설치 하는 경우 각 UM 포리스트에 대해 Exchange Server 통합 단계를 수행 하거나 비즈니스용 Skype 서버 도메인을 지정 해야 합니다. 예를 들어 ExchUcUtil –. ps1-포리스트: <lync-컨트롤러-fqdn>. 

### <a name="use-the-shell-to-run-the-exchucutilps1-script"></a>Shell을 사용 하 여 ExchUcUtil 스크립트를 실행 합니다.

비즈니스용 Skype 서버와 동일한 토폴로지를가지고 있는 조직의 모든 Exchange 서버에서 ExchUcUtil 스크립트를 실행 합니다. 셸을 사용 하 여 사서함 서버에서 스크립트를 실행 하거나 클라이언트 액세스 서버에서 원격 Windows PowerShell을 사용 하 여 스크립트를 실행할 수 있습니다. 조직의 클라이언트 액세스 서버에서 스크립트를 실행 하는 경우 클라이언트 액세스 서버는 원격 Windows PowerShell 세션을 조직의 사서함 서버에 프록시 하 게 됩니다.
> [!IMPORTANT]
> ExchUcUtil 스크립트는 하나 이상의 UM IP 게이트웨이를 만듭니다. 스크립트에서 만든 게이트웨이를 제외한 모든 UM IP 게이트웨이에서 나가는 호출을 사용 하지 않도록 설정 해야 합니다. 여기에는 스크립트를 실행 하기 전에 만든 UM IP 게이트웨이에서 나가는 호출을 사용 하지 않도록 설정 하는 것이 포함 됩니다. UM IP 게이트웨이에서 나가는 호출을 사용 하지 않도록 설정 하려면 UM IP 게이트웨이에서 발신 전화 사용 안 함을 참조 하세요. 
> [!IMPORTANT]
> 스크립트를 실행 하려면 Exchange 조직 관리 역할의 사용 권한이 나 Exchange 조직 관리자 보안 그룹의 구성원 이어야 합니다. 

1. Exchange 관리 셸을 엽니다.
2. Files\Microsoft\Exchange System32 프롬프트에서 **cd \<드라이브 문자>: a/Server\V15\Scripts>를 입력 합니다. ExchUcUtil**을 입력 한 다음 enter 키를 누릅니다.

#### <a name="how-do-you-know-this-worked"></a>이 작업이 제대로 수행 되었는지 어떻게 알 수 있나요?

ExchUcUtul 스크립트가 성공적으로 완료 되었는지 확인 하려면 다음을 수행 합니다.
- Get-UMIPGateway cmdlet 또는 EAC를 사용 하 여 생성 된 새 UM IP 게이트웨이 또는 게이트웨이를 봅니다.
- UMHuntGroup cmdlet 또는 EAC를 사용 하 여 생성 된 새 UM 헌트 그룹을 봅니다.

### <a name="configure-certificates-on-the-server-running-exchange-server-unified-messaging"></a>Exchange Server 통합 메시징을 실행 하는 서버에서 인증서 구성
 
계획 설명서의 비즈니스용 Skype 서버에서 Exchange 통합 메시징 통합 계획에 설명 된 대로 exchange um (통합 메시징)를 배포한 경우, 사용자의 엔터프라이즈 음성 사용자에 게 Exchange UM 기능을 제공 하려는 경우 조직에서 다음 절차를 사용 하 여 Exchange UM을 실행 하는 서버에서 인증서를 구성할 수 있습니다.

> [!IMPORTANT]
> 내부 인증서의 경우 비즈니스용 Skype Server를 실행 하는 서버와 Microsoft Exchange를 실행 하는 서버에 모두 상호 신뢰 되는 신뢰할 수 있는 루트 인증 기관 인증서가 있어야 합니다. CA (인증 기관)가 신뢰할 수 있는 루트 인증 기관 인증서 저장소에 등록 되어 있는 경우 해당 서버는 동일 하거나 다른 인증 기관 이어야 합니다. 

비즈니스용 Skype 서버에 연결 하기 위해 서버 인증서를 사용 하 여 Exchange 서버를 구성 해야 합니다.
1. Exchange 서버에 대 한 CA 인증서를 다운로드 합니다.
2. Exchange 서버에 대 한 CA 인증서를 설치 합니다.
3. CA가 Exchange Server의 신뢰할 수 있는 루트 Ca 목록에 있는지 확인 합니다.
4. Exchange 서버에 대 한 인증서 요청을 만들고 인증서를 설치 합니다. 
5. Exchange 서버에 대 한 인증서를 할당 합니다.


**CA 인증서를 다운로드 하려면 다음을 수행 합니다.**

1. Exchange UM을 (를) 실행 하는 서버에서 **시작**, **실행**을 차례로 클릭 하 고 **발급 CA\<> 서버의 http://이름을**입력 하 고/certsrv을 클릭 한 다음 **확인**을 클릭 합니다.
2. 작업 선택에서 **CA 인증서, 인증서 체인 또는 CRL 다운로드**를 클릭 합니다.
3. **Ca 인증서, 인증서 체인 또는 CRL 다운로드**에서 **Base 64에 대 한 인코딩 방법을**선택한 다음**CA 인증서 다운로드**를 클릭 합니다.
   > [!NOTE]
   > 이 단계에서 DER (고유 인코딩 규칙) 인코딩을 지정할 수도 있습니다. DER 인코딩을 선택 하는 경우이 절차의 다음 단계인 **CA 인증서를 설치 하** 는 10 단계의 파일 형식은. .cer이 아닌. 
4. **파일 다운로드** 대화 상자에서 **저장**을 클릭 한 다음 서버의 하드 디스크에 파일을 저장 합니다. (이 파일에는 이전 단계에서 선택한 인코딩에 따라 .cer 또는. p7b 확장명 중 하나가 사용 됩니다.)

**CA 인증서를 설치 하려면 다음을 수행 합니다.**

1. Exchange UM을 (를) 실행 하는 서버에서 **시작**을 클릭 하 고 **실행**을 클릭 한 다음 열기 상자에 **Mmc** 를 입력 하 고 **확인**을 클릭 하 여 mmc (Microsoft Management Console)를 엽니다.
2. **파일** 메뉴에서 **스냅인 추가/제거**를 클릭 한 다음 **추가**를 클릭 합니다.
3. **독립 실행형 스냅인 추가** 상자에서 **인증서**를 클릭 한 다음 **추가**를 클릭 합니다.
4. **인증서 스냅인** 대화 상자에서 **컴퓨터 계정을**클릭 하 고 **다음**을 클릭 합니다.
5. **컴퓨터 선택** 대화 상자에서 **로컬 컴퓨터: (이 콘솔이 실행 되 고 있는 컴퓨터)** 확인란이 선택 되어 있는지 확인 한 다음 **마침을**클릭 합니다.
6. **닫기를**클릭 한 다음 **확인**을 클릭 합니다. 
7. 콘솔 트리에서 **인증서 (로컬 컴퓨터)** 를 확장 하 고 **신뢰할 수 있는 루트 인증 기관을**확장 한 다음 **인증서**를 클릭 합니다.
8. **인증서**를 마우스 오른쪽 단추로 클릭 하 고 **모든 작업**을 클릭 한 다음 **가져오기를**클릭 합니다.
9. **다음**을 클릭 합니다. 
10. **찾아보기를** 클릭 하 여 파일을 찾은 후 **다음**을 클릭 합니다. (이 파일은 **CA 인증서를 다운로드 하기 위해**3 단계에서 선택한 인코딩에 따라 .cer 또는. p7b 파일 확장명을 갖습니다.
11. **모든 인증서** 를 다음 저장소에 저장을 클릭 합니다.
12. **찾아보기를**클릭 한 다음 **신뢰할 수 있는 루트 인증 기관을**선택 합니다. 
13. **다음** 을 클릭 하 여 설정을 확인 한 다음 **마침을**클릭 합니다. 


**CA가 신뢰할 수 있는 루트 Ca 목록에 있는지 확인 하려면 다음을 수행 합니다.**

1. Exchange UM을 실행 하는 서버의 MMC에서 인증서 (로컬 컴퓨터)를 확장 하 고 신뢰할 수 있는 루트 인증 기관을 확장 한 다음 인증서를 클릭 합니다.
2. 세부 정보 창에서 CA가 신뢰할 수 있는 Ca 목록에 있는지 확인 합니다.


