---
title: 비즈니스 Exchange Server 음성 메일에 대한 통합 메시징 구성
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/11/2019
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 1be9c4f4-fd8e-4d64-9798-f8737b12e2ab
description: '요약: Exchange Server 서버 음성 메일에 대해 통합 메시징을 구성합니다.'
ms.openlocfilehash: 68cf4a11deccac9ad71bdb6216c4126362787498
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49834038"
---
# <a name="configure-exchange-server-unified-messaging-for-skype-for-business-server-voice-mail"></a>비즈니스 Exchange Server 음성 메일에 대한 통합 메시징 구성
 
**요약:** 비즈니스 Exchange Server 음성 메일에 대해 통합 메시징을 구성합니다.
  
비즈니스용 Skype 서버를 사용하면 음성 메일 메시지를 Exchange Server 2016 또는 Exchange Server 2013에 저장할 수 있습니다. 이러한 음성 메일 메시지는 사용자의 받은 편지함에서 전자 메일 메시지로 표시됩니다. 

> [!NOTE]
> 이전에 알려진 Exchange 통합 메시징은 Exchange 2019에서 더 이상 사용할 수 없지만 전화 시스템을 사용하여 음성 메일 메시지를 녹음한 다음 사용자의 Exchange 사서함에 기록을 남길 수 있습니다. 자세한 [내용은 클라우드 음성메일 서비스](../../../sfbhybrid/hybrid/plan-cloud-voicemail.md) 계획을 참조하세요.
  
비즈니스용 Skype 서버와 Exchange Server 2016 또는 Exchange Server 2013 간에 서버 간 인증을 이미 구성한 경우 통합 메시징을 사용할 준비가 된 것입니다. 이렇게하려면 먼저 새 통합 메시징 다이얼 플랜을 만들어 새 통합 메시징 다이얼 플랜에 할당해야 Exchange Server. 예를 들어 Exchange 관리 셸 내에서 실행된 다음 두 명령은 Exchange에 대한 새 3자리 다이얼 플랜을 구성합니다.
  
```powershell
New-UMDialPlan -Name "RedmondDialPlan" -VoIPSecurity "Secured" -NumberOfDigitsInExtension 3 -URIType "SipName" -CountryOrRegionCode 1
Set-UMDialPlan "RedmondDialPlan" -ConfiguredInCountryOrRegionGroups "Anywhere,*,*,*" -AllowedInCountryOrRegionGroups "Anywhere"
```

예제의 첫 번째 명령에서 VoIPSecurity 매개 변수와 매개 변수 값 "Secured"는 신호 채널이 TLS(전송 계층 보안)를 사용하여 암호화되어 있는 경우를 나타냅니다. URIType "SipName"은 메시지가 SIP 프로토콜을 사용하여 송/수신됨을 나타내고, CountryOrRegionCode 1은 다이얼 플랜이 미국에 적용됨을 나타냅니다.
  
두 번째 명령에서 ConfiguredInCountryOrRegionGroups 매개 변수로 전달되는 매개 변수 값은 이 다이얼 플랜에 사용할 수 있는 국가 내 그룹을 지정합니다. 매개 변수 값 "Anywhere, \* \* , " \* 는 다음을 설정합니다.
  
- 그룹 이름("Anywhere")
    
- AllowedNumberString( 숫자 문자열이 허용되었음을 나타내는 와일드카드 \* 문자)
    
- DialNumberString( 전화 걸기 번호가 허용되었음을 나타내는 와일드카드 \* 문자)
    
- TextComment( 텍스트 명령이 허용되었음을 나타내는 와일드카드 \* 문자)
    
> [!NOTE]
> 새 다이얼 플랜을 만들면 기본 사서함 정책도 생성됩니다. 
  
새 다이얼 플랜을 만들고 구성한 후 새 다이얼 플랜을 통합 메시징 서버에 추가한 다음 해당 서버의 시작 모드를 수정해야 합니다. 특히 시작 모드를 "이중"으로 설정해야 합니다. Exchange 관리 셸 내에서 다음 두 작업을 모두 수행할 수 있습니다.
  
```powershell
Set-UmService -Identity "atl-exchangeum-001.litwareinc.com" -DialPlans "RedmondDialPlan" -UMStartupMode "Dual"
```

통합 메시징 서버를 구성한 후 exchange 인증서가 통합 메시징 서비스에 Enable-ExchangeCertificate cmdlet을 실행해야 합니다.
  
```powershell
Enable-ExchangeCertificate -Server "atl-umserver-001.litwareinc.com" -Thumbprint "EA5A332496CC05DA69B75B66111C0F78A110D22d" -Services "SMTP","IIS","UM"
```

인증서가 올바르게 할당되고 나면 통합 메시징 서버에서 MsExchangeUM 서비스를 중지했다가 다시 시작해야 합니다. 시작 모드를 변경할 때마다 이 서비스를 중지한 후 다시 시작해야 합니다.
  
통합 메시징 서버 구성이 완료되면 UM Call Router를 구성할 수 있습니다.
  
```powershell
Set-UMCallRouterSettings -Server "atl-exchange-001.litwareinc.com" -UMStartupMode "Dual" -DialPlans "RedmondDialPlan" 
Enable-ExchangeCertificate -Server "atl-umserver-001.litwareinc.com" -Thumbprint "45BAA32496CC891169B75B9811320F78A1075DDA" -Services "IIS","UMCallRouter"
```

시작 모드가 변경되었으므로 UM Call Router를 호스팅하는 컴퓨터에서 MsExchangeUMCR 서비스를 중지했다가 다시 시작해야 합니다.
  
통합 메시징 설정을 완료하려면 UM 사서함 정책을 만든 다음 해당 정책을 사용하여 사용자가 통합 메시징을 사용할 수 있도록 설정해야 합니다. 다음과 같은 명령을 사용하여 사서함 정책을 만들 수 있습니다.
  
```powershell
New-UMMailboxPolicy -Name "RedmondMailboxPolicy" -AllowedInCountryOrRegionGroups "Anywhere"
```

그리고 다음과 같은 명령을 사용하면 사용자가 통합 메시징을 사용할 수 있도록 설정할 수 있습니다.
  
```powershell
Enable-UMMailbox -Extensions 100 -SIPResourceIdentifier "kenmyer@litwareinc.com" -Identity "litwareinc\kenmyer" -UMMailboxPolicy "RedmondMailboxPolicy"
```

위의 명령에서 Extensions 매개 변수는 사용자의 전화 내선 번호를 나타냅니다. 이 예에서 사용자의 내선 번호는 100입니다.
  
해당 사서함을 사용하도록 설정하고 나면 kenmyer@litwareinc.com 사용자가 Exchange 통합 메시징을 사용할 수 있게 됩니다. 사용자가 비즈니스용 Skype 서버 관리 셸에서 [Test-CsExUMConnectivity](https://docs.microsoft.com/powershell/module/skype/test-csexumconnectivity?view=skype-ps) cmdlet을 실행하여 Exchange UM에 연결할 수 있는지 확인할 수 있습니다.
  
```powershell
$credential = Get-Credential "litwareinc\kenmyer"
Test-CsExUMConnectivity -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential
```

통합 메시징을 사용할 수 있도록 설정된 두 번째 사용자가 있는 경우 [Test-CsExUMVoiceMail](https://docs.microsoft.com/powershell/module/skype/test-csexumvoicemail?view=skype-ps) cmdlet을 사용하여 두 번째 사용자가 첫 번째 사용자에게 음성 메일 메시지를 남길 수 있는지 확인할 수 있습니다.
  
```powershell
$credential = Get-Credential "litwareinc\pilar"
Test-CsExUMVoiceMail -TargetFqdn "atl-cs-001.litwareinc.com" -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -SenderSipAddress "sip:pilar@litwareinc.com" -SenderCredential $credential
```



## <a name="configuring-unified-messaging-on-microsoft-exchange-server"></a>2013에서 통합 메시징 Microsoft Exchange Server 
> [!IMPORTANT]
> Exchange UM(통합 메시징)을 사용하여 Enterprise Voice 사용자에 대해 전화 응답, Outlook Voice Access 또는 자동 전화 교환 서비스를 제공하려는 경우 비즈니스용 [Skype에서 Exchange](../../plan-your-deployment/integrate-with-exchange/unified-messaging.md)통합 메시징 통합 계획을 읽은 다음 이 섹션의 지침을 따릅니다. 

Exchange UM(통합 메시징)이 사용되지 Enterprise Voice 구성하려면 다음 작업을 수행해야 합니다.

- Exchange UM(통합 메시징) 서비스를 실행하는 서버에서 인증서 구성
  > [!NOTE]
  > 모든 클라이언트 액세스 및 사서함 서버를 모든 UM SIP URI 다이얼 플랜에 추가합니다. 그렇지 않은 경우 아웃바운드 통화 라우팅이 예상대로 작동하지 않습니다. 
- 필요한 경우 구독자 액세스 전화 번호와 함께 하나 이상의 UM SIP URI 다이얼 플랜을 만든 다음 해당 L 다이얼 플랜을 만드시다.

- 다음 exchucutil.ps1 스크립트를 사용하여 다음을 실행합니다.
    - UM IP 게이트웨이 만들기
    - UM 헌트 그룹 만들기
    - 비즈니스용 Skype 서버에 UM Active Directory 도메인 서비스 개체를 읽을 수 있는 권한을 부여합니다.
- UM 자동 회의 개체를 만듭니다.
- 구독자 액세스 개체를 만듭니다.
- 각 사용자에 대해 SIP URI를 만들고 사용자를 UM SIP URI 다이얼 플랜과 연결합니다.

### <a name="requirements-and-recommendations"></a>요구 사항 및 권장 사항

시작하기 전에 이 섹션의 설명서에서는 클라이언트 액세스 및 사서함과 같은 Exchange 역할을 배포했다고 가정합니다. 이 Microsoft Exchange Server Exchange UM은 이러한 서버에서 서비스로 실행됩니다.

또한 다음에 주의하십시오.
- Exchange UM이 여러 포리스트에 설치되어 있는 경우 Exchange Server UM 포리스트에 대해 통합 단계를 수행해야 합니다. 또한 비즈니스용 Skype 서버가 배포된 포리스트를 신뢰하도록 각 UM 포리스트를 구성해야 합니다. 또한 각 UM 포리스트를 신뢰하도록 비즈니스용 Skype 서버가 배포된 포리스트를 구성해야 합니다.
- 통합 단계는 통합 메시징 서비스가 실행되는 Exchange Server 역할과 비즈니스용 Skype 서버를 실행하는 서버에서 모두 수행됩니다. Lync Server 2013 Exchange Server 전에 통합 메시징 통합 단계를 수행해야 합니다.
  > [!NOTE]
  > 서버에서 수행되는 통합 단계와 관리자 역할에 대한 자세한 내용은 배포 프로세스 개요를 [참조하십시오.](../../plan-your-deployment/integrate-with-exchange/deployment-overview.md) 

Exchange UM을 실행하는 각 서버에서 다음 도구를 사용할 수 있어야 합니다.
- Exchange 관리 셸
- 다음 작업을 수행하는 스크립트 exchucutil.ps1
    - 각 비즈니스용 Skype 서버에 대해 UM IP 게이트웨이를 만듭니다.
    - 각 게이트웨이에 대한 헌트 그룹 만들기. 각 헌트 그룹의 파일럿 식별자는 게이트웨이와 연결된 프런트 엔드 풀 또는 Standard Edition 서버에서 사용하는 UM SIP URI 다이얼 플랜을 지정합니다.
    - 비즈니스용 Skype 서버에 Active Directory 도메인 서비스에서 Exchange UM 개체를 읽을 수 있는 권한을 부여합니다.



### <a name="configure-unified-messaging-on-microsoft-exchange-with-exchucutilps1"></a>통합 메시징을 사용하여 Microsoft Exchange에서 ExchUCUtil.ps1 

Microsoft 비즈니스용 Skype 서버를 Exchange UM(통합 메시징)에 통합하는 경우 셸에서 ExchUcUtil.ps1 스크립트를 실행해야 합니다. ExchUcUtil.ps1 스크립트는 다음을 수행합니다.

- 각 비즈니스용 Skype 서버 풀에 대해 UM IP 게이트웨이를 만듭니다.

> [!IMPORTANT]
> ExchUcUtil.ps1 스크립트는 UM IP 게이트웨이를 하나 이상 만듭니다. 스크립트가 만들어진 한 게이트웨이를 제외한 모든 UM IP 게이트웨이에서 발신 전화를 사용하지 않도록 설정해야 합니다. 또한 스크립트를 실행하기 전에 만들어진 UM IP 게이트웨이에서도 발신 전화를 사용하지 않도록 설정합니다. 

- 각 UM IP 게이트웨이에 대해 UM 헌트 그룹을 만듭니다. 각 헌트 그룹의 파일럿 식별자는 UM IP 게이트웨이와 연결된 비즈니스용 Skype 서버 프런트 엔드 풀 또는 Standard Edition 서버에서 사용하는 UM SIP URI 다이얼 플랜을 지정합니다.
- 비즈니스용 Skype 서버에 UM 다이얼 플랜, 자동 전화 걸기, UM IP 게이트웨이 및 UM 헌트 그룹과 같은 Active Directory UM 컨테이너 개체를 읽을 수 있는 권한을 부여합니다.
  > [!IMPORTANT]
  > 각 UM 포리스트는 비즈니스용 Skype 서버가 배포된 포리스트를 신뢰하도록 구성해야 합니다. 또한 각 UM 포리스트를 신뢰하도록 비즈니스용 Skype 서버 2013이 배포된 포리스트를 구성해야 합니다. Exchange UM이 여러 포리스트에 설치된 경우 Exchange Server UM 포리스트에 대해 통합 단계를 수행하거나 비즈니스용 Skype 서버 도메인을 지정해야 합니다. 예를 들어 ExchUcUtil.ps1 -Forest:<-domain-controller-fqdn을>. 

### <a name="use-the-shell-to-run-the-exchucutilps1-script"></a>셸을 사용하여 ExchUcUtil.ps1 스크립트 실행

조직의 ExchUcUtil.ps1 비즈니스용 Skype 서버와 동일한 토폴로지에 있는 모든 Exchange 서버에서 ExchUcUtil.ps1 스크립트를 실행합니다. 셸을 사용하여 사서함 서버에서 스크립트를 실행하거나, 클라이언트 액세스 서버에서 원격 Windows PowerShell을 사용하여 스크립트를 실행할 수 있습니다. 조직의 클라이언트 액세스 서버에서 스크립트를 실행하면 클라이언트 액세스 서버가 원격 Windows PowerShell 세션을 조직에 있는 사서함 서버로 프록시합니다.
> [!IMPORTANT]
> ExchUcUtil.ps1 스크립트는 UM IP 게이트웨이를 하나 이상 만듭니다. 스크립트가 만들어진 한 게이트웨이를 제외한 모든 UM IP 게이트웨이에서 발신 전화를 사용하지 않도록 설정해야 합니다. 또한 스크립트를 실행하기 전에 만들어진 UM IP 게이트웨이에서도 발신 전화를 사용하지 않도록 설정합니다. UM IP 게이트웨이에서 발신 전화를 사용하지 않도록 설정하려면 UM IP 게이트웨이에서 거는 전화를 사용 하지 않도록 설정을 참조하세요. 
> [!IMPORTANT]
> 사용자는 Exchange 조직 관리 역할의 사용 권한이 있거나, 스크립트를 실행할 수 있는 Exchange 조직 관리 보안 그룹의 구성원이어야 합니다. 

1. Exchange 관리 셸을 엽니다.
2. C:\Windows\System32 프롬프트에 **cd \<drive letter> :\Program Files\Microsoft\Exchange Server\V15\Scripts>.ExchUcUtil.ps1** 입력한 다음 Enter를 누르고 있습니다.

#### <a name="how-do-you-know-this-worked"></a>작동 여부를 확인하는 방법

ExchUcUtul.ps1 스크립트가 완료되었는지 확인하려면 다음을 수행합니다.
- Get-UMIPGateway cmdlet 또는 EAC를 사용하여 새로운 UM IP 게이트웨이 또는 만들어진 게이트웨이를 확인합니다.
- Get-UMHuntGroup cmdlet 또는 EAC를 사용하여 새로운 UM 헌트 그룹 또는 만들어진 그룹을 확인합니다.

### <a name="configure-certificates-on-the-server-running-exchange-server-unified-messaging"></a>통합 메시징을 실행하는 서버에서 Exchange Server 구성
 
계획 설명서에서 비즈니스용 Skype 서버의 Exchange 통합 메시징 통합 계획에 설명된 바와 같이 Exchange UM(통합 메시징)을 배포한 경우 조직의 Enterprise Voice 사용자에게 Exchange UM 기능을 제공하려는 경우 다음 절차에 따라 Exchange UM을 실행하는 서버에서 인증서를 구성할 수 있습니다.

> [!IMPORTANT]
> 내부 인증서의 경우 비즈니스용 Skype 서버를 실행하는 서버와 Microsoft Exchange를 실행하는 서버에는 함께 신뢰할 수 있는 신뢰할 수 있는 루트 기관 인증서가 있어야 합니다. 서버에 신뢰할 수 있는 루트 기관 인증서 저장소에 인증 기관의 루트 인증서가 등록되어 있는 경우 CA(인증 기관)는 동일하거나 다른 인증 기관일 수 있습니다. 

비즈니스 Exchange Server 연결하려면 서버 인증서를 사용하여 구성해야 합니다.
1. Exchange Server에 대한 CA 인증서를 다운로드합니다.
2. Exchange Server에 대한 CA 인증서를 설치합니다.
3. Exchange Server의 신뢰할 수 있는 루트 CA 목록에 해당 CA가 있는지 확인합니다.
4. Exchange Server에 대한 인증서 요청을 만들고 인증서를 설치합니다. 
5. Exchange Server에 대한 인증서를 할당합니다.


**CA 인증서를 다운로드하려면**

1. Exchange UM을 실행하는 서버에서 **시작,** 실행을 클릭하고 **http:// \<name of your Issuing CA Server> /certsrv를** 입력한 다음 확인을 **클릭합니다.** 
2. 작업 선택에서 CA 인증서, 인증서 체인 **또는 CRL 다운로드를 클릭합니다.**
3. CA 인증서, 인증서 체인 또는 **CRL** 다운로드 아래에서 기본 **64로** 인코딩 방법을 선택한 다음 CA 인증서 **다운로드를 클릭합니다.**
   > [!NOTE]
   > 이 단계에서 DER(Distinguished Encoding Rules) 인코딩을 지정할 수 있습니다. DER 인코딩을 선택하는 경우 이 절차 다음 단계와 **CA 인증서를 설치하려면** 의 10단계에서 파일 형식은 .cer이 아닌 .p7b입니다. 
4. **파일 다운로드** 대화 상자에서 **저장** 을 클릭한 다음 파일을 서버의 하드 디스크에 저장합니다. 이전 단계에서 선택한 인코딩에 따라 파일의 확장명은 .cer 또는 .p7b가 됩니다.

**CA 인증서를 설치하려면**

1. Exchange UM을 실행하는 서버에서 시작, **실행,** 열기 상자에 **mmc** 입력, 확인을 클릭하여 MMC(Microsoft Management Console)를 **런타이저합니다.** 
2. **파일** 메뉴에서 **스냅인 추가/제거** 를 클릭한 다음 **추가** 를 클릭합니다.
3. **독립 실행형 스냅인 추가** 상자에서 **인증서** 를 클릭한 다음 **추가** 를 클릭합니다.
4. **인증서 스냅인** 대화 상자에서 **컴퓨터 계정** 을 클릭한 다음 **다음** 을 클릭합니다.
5. 컴퓨터 **선택** 대화 상자에서 로컬 **컴퓨터: (이** 콘솔이 실행되고 있는 컴퓨터) 확인란이 선택되어 있는지 확인한 후 마침을 **클릭합니다.**
6. **닫기** 를 클릭한 다음 **확인** 을 클릭합니다. 
7. 콘솔 트리에서 **인증서(로컬 컴퓨터)**, **신뢰할 수 있는 루트 인증 기관** 을 차례로 확장한 다음 **인증서** 를 클릭합니다.
8. **인증서** 를 마우스 오른쪽 단추로 클릭하고 **모든 작업** 을 클릭하고 **가져오기** 를 클릭합니다.
9. **다음** 을 클릭합니다. 
10. **찾아보기** 를 클릭하여 파일을 찾은 다음 **다음** 을 클릭합니다. **CA 인증서를 다운로드하려면** 의 3단계에서 선택한 인코딩에 따라 파일의 확장명은 .cer 또는 .p7b가 됩니다.
11. 다음 **저장소에 모든 인증서를** 저장합니다.
12. **찾아보기** 를 클릭한 다음 **신뢰할 수 있는 루트 인증 기관** 을 선택합니다. 
13. **다음** 을 클릭하여 설정을 확인한 다음 **마침** 을 클릭합니다. 


**CA가 신뢰할 수 있는 루트 CA 목록에 있는지 확인:**

1. Exchange UM을 실행하는 서버의 MMC 확장 인증서(로컬 컴퓨터)에서 신뢰할 수 있는 루트 인증 기관을 확장한 다음 인증서를 클릭합니다.
2. 세부 정보 창에서 해당 CA가 신뢰할 수 있는 CA 목록에 있는지 확인합니다.


