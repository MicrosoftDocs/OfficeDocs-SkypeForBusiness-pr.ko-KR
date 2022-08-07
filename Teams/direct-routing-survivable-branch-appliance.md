---
title: 직접 라우팅 SBA
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 12/08/2020
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
ms.reviewer: crowe
search.appverid: MET150
f1.keywords:
- NOCSH
- ms.teamsadmincenter.directrouting.overview
description: 구성, 필요한 핵심 배포 결정 및 음성 라우팅 고려 사항과 같은 직접 라우팅에 대해 자세히 알아봅니다.
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: cc250b0506614ef658ade9a491c5561a65b98800
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/07/2022
ms.locfileid: "67269673"
---
# <a name="survivable-branch-appliance-sba-for-direct-routing"></a>직접 라우팅을 위한 SBA(Survivable Branch Appliance)


경우에 따라 직접 라우팅을 사용하여 Microsoft Phone 시스템에 연결하는 고객 사이트에서 인터넷 중단이 발생할 수 있습니다.

분기라고 하는 고객 사이트가 직접 라우팅을 통해 일시적으로 Microsoft 클라우드에 연결할 수 없다고 가정합니다. 그러나 분기 내의 인트라넷은 여전히 완벽하게 작동하며 사용자는 PSTN 연결을 제공하는 SBC(세션 테두리 컨트롤러)에 연결할 수 있습니다.

이 문서에서는 SBA(Survivable Branch Appliance)를 사용하여 가동 중단 시 Microsoft Phone System이 PSTN(공중 전화망) 통화를 계속 만들고 받을 수 있도록 하는 방법을 설명합니다.

## <a name="prerequisites"></a>필수 구성 요소

SBA는 Microsoft에서 SBC 공급업체에 제공한 배포 가능 코드로, 펌웨어에 코드를 포함하거나 별도로 배포하여 별도의 VM 또는 하드웨어에서 SBA를 실행하도록 합니다. 

포함된 Survivable Branch Appliance를 사용하여 최신 세션 테두리 컨트롤러 펌웨어를 얻으려면 SBC 공급업체에 문의하세요. 또한 다음이 필요합니다.

- SBC는 분기 사이트의 Microsoft Teams 클라이언트가 SBC를 통해 직접 미디어가 흐르도록 미디어 바이패스용으로 구성해야 합니다. 

- SBA VM OS에서 TLS1.2를 사용하도록 설정해야 합니다.
- 포트 3443, 4444 및 8443은 Microsoft SBA 서버에서 Teams 클라이언트와 통신하는 데 사용되며 방화벽에서 허용되어야 합니다. 
- 포트 5061(또는 SBC에 구성된 포트)은 Microsoft SBA 서버에서 SBC와 통신하는 데 사용되며 방화벽에서 허용되어야 합니다. 
- UDP 포트 123은 Microsoft SBA 서버에서 NTP 서버와 통신하는 데 사용되며 방화벽에서 허용되어야 합니다.
- 포트 443은 Microsoft SBA 서버에서 Microsoft 365와 통신하는 데 사용되며 방화벽에서 허용되어야 합니다.
- 퍼블릭 클라우드에 대한 Azure IP 범위 및 서비스 태그는 다음에 설명된 지침에 따라 정의되어야 합니다. https://www.microsoft.com/download/details.aspx?id=56519

## <a name="supported-teams-clients"></a>지원되는 Teams 클라이언트

SBA 기능은 다음 Microsoft Teams 클라이언트에서 지원됩니다. 

- Microsoft Teams Windows 데스크톱 

- Microsoft Teams macOS 데스크톱
- 모바일용 Teams 
- Teams 휴대폰

## <a name="how-it-works"></a>작동 방식

인터넷 중단 시 Teams 클라이언트는 자동으로 SBA로 전환해야 하며 지속적인 통화는 중단 없이 계속되어야 합니다. 사용자로부터 아무 작업도 필요하지 않습니다. Teams 클라이언트가 인터넷이 작동 중이고 발신 통화가 완료된 것을 감지하는 즉시 클라이언트는 정상 작동 모드로 대체되고 다른 Teams 서비스에 연결됩니다. SBA는 수집된 통화 데이터 레코드를 클라우드에 업로드하고, 테넌트 관리자가 이 정보를 검토할 수 있도록 통화 기록이 업데이트됩니다. 

Microsoft Teams 클라이언트가 오프라인 모드인 경우 다음과 같은 통화 관련 기능을 사용할 수 있습니다. 

- SBC를 통해 미디어가 흐르는 로컬 SBA/SBC를 통해 PSTN을 호출합니다.

- SBC를 통해 미디어가 흐르는 로컬 SBA/SBC를 통해 PSTN 호출을 수신합니다. 

- PSTN 호출을 보류하고 다시 시작합니다.

## <a name="configuration"></a>구성

SBA 기능이 작동하려면 Teams 클라이언트는 각 분기 사이트에서 사용할 수 있는 SBA와 해당 사이트의 사용자에게 할당된 SBA를 알고 있어야 합니다. 구성 단계는 다음과 같습니다.

1. SBA를 만듭니다.
2. Teams 분기 생존 정책을 만듭니다.
3. 사용자에게 정책을 할당합니다.
4. Azure Active Directory에 SBA에 대한 애플리케이션을 등록합니다.

모든 구성은 비즈니스용 Skype Online PowerShell cmdlet을 사용하여 수행됩니다. (Teams 관리 센터는 아직 직접 라우팅 SBA 기능을 지원하지 않습니다.) 

(SBC 공급업체 설명서에 대한 링크가 포함된 SBC 구성에 대한 자세한 내용은 이 문서의 끝에 있는 세션 테두리 컨트롤러 구성을 참조하세요.)

### <a name="create-the-sbas"></a>SBA 만들기

SBA를 만들려면 New-CsTeamsSurvivableBranchAppliance cmdlet을 사용합니다. 이 cmdlet에는 다음과 같은 매개 변수가 있습니다.

| 매개 변수| 설명 |
| :------------|:-------|
| Identity  | SBA의 ID  |
| Fqdn | SBA의 FQDN |
| 사이트 | SBA가 있는 TenantNetworkSite |
| 설명 | 자유 서식 텍스트 |
|||

예를 들면 다음과 같습니다.

``` powershell
C:\> New-CsTeamsSurvivableBranchAppliance  -Fqdn sba1.contoso.com -Description "SBA 1" 
Identity    : sba1.contoso.com 
Fqdn        : sba1.contoso.com 
Site        : 
Description : SBA 1 
```

### <a name="create-the-teams-branch-survivability-policy"></a>Teams 분기 생존 정책 만들기 

정책을 만들려면 New-CsTeamsSurvivableBranchAppliancePolicy cmdlet을 사용합니다. 이 cmdlet에는 다음과 같은 매개 변수가 있습니다. 정책에 하나 이상의 SBA가 포함될 수 있습니다.

| 매개 변수| 설명 |
| :------------|:-------|
| Identity | 정책의 ID |
| BranchApplianceFqdns  | 사이트의 SBA FQDN |
||

예를 들면 다음과 같습니다.

``` powershell
C:\> new-CsTeamsSurvivableBranchAppliancePolicy -Identity CPH -BranchApplianceFqdns "sba1.contoso.com","sba2.contoso.com" 
Identity             : Tag:CPH 
BranchApplianceFqdns : {sba1.contoso.com, sba2.contoso.com} 
```

Set-CsTeamsSurvivableBranchAppliancePolicy cmdlet을 사용하여 정책에서 SBA를 추가하거나 제거할 수 있습니다. 예를 들면 다음과 같습니다. 

``` powershell
Set-CsTeamsSurvivableBranchAppliancePolicy -Identity CPH -BranchApplianceFqdns @{remove="sba1.contoso.com"} 
Set-CsTeamsSurvivableBranchAppliancePolicy -Identity CPH -BranchApplianceFqdns @{add="sba1.contoso.com"} 
```

### <a name="assign-a-policy-to-a-user"></a>사용자에게 정책 할당

개별 사용자에게 정책을 할당하려면 Grant-CsTeamsSurvivableBranchAppliancePolicy cmdlet을 사용합니다. 이 cmdlet에는 다음과 같은 매개 변수가 있습니다.

| 매개 변수| 설명 |
| :------------|:-------|
| Identity | 사용자의 ID |
| PolicyName | 정책의 ID |
||

예를 들면 다음과 같습니다.

``` powershell
C:\> Grant-CsTeamsSurvivableBranchAppliancePolicy -PolicyName CPH -Identity user@contoso.com 
```

다음 예제와 같이 $Null 정책을 부여하여 사용자로부터 정책을 제거할 수 있습니다.

``` powershell
C:\> Grant-CsTeamsSurvivableBranchAppliancePolicy -PolicyName $Null -Identity user@contoso.com 
```

### <a name="register-an-application-for-the-sba-with-azure-active-directory"></a>Azure Active Directory를 사용하여 SBA에 대한 애플리케이션 등록

테넌트 내에서 사용되는 여러 SBA가 Microsoft 365에서 필요한 데이터를 읽을 수 있도록 하려면 Azure Active Directory에 SBA에 대한 애플리케이션을 등록해야 합니다. 

애플리케이션 등록에 대한 자세한 내용은 다음을 참조하세요.

- [Azure Active Directory용 기간 업무 앱 개발](/azure/active-directory/manage-apps/developer-guidance-for-integrating-applications)

- [Microsoft ID 플랫폼 애플리케이션을 등록](/azure/active-directory/develop/quickstart-register-app)합니다.  

테넌트의 모든 SBA에서 사용할 애플리케이션을 하나만 등록하면 됩니다. 

SBA 등록의 경우 등록에서 만든 다음 값이 필요합니다. 

- 애플리케이션(클라이언트) ID 
- 클라이언트 암호 

SBA 애플리케이션의 경우 다음 사항에 유의하세요. 

- 이름은 사용자가 결정하는 것이 무엇이든 될 수 있습니다.  
- 지원되는 계정 유형 = 이 조직 디렉터리에만 있는 계정입니다. 
- 웹 리디렉션 Uri = https://login.microsoftonline.com/common/oauth2/nativeclient.
- 암시적 권한 부여 토큰 = 액세스 토큰 및 ID 토큰. 
- API 권한 = Skype 및 Teams 테넌트 관리 Access -> 애플리케이션 권한 -> application_access_custom_sba_appliance.
- 클라이언트 암호: 설명 및 만료를 사용할 수 있습니다. 
- 클라이언트 암호를 만든 직후에 복사해야 합니다. 
- 애플리케이션(클라이언트) ID가 개요 탭에 표시됩니다.

그런 다음, 다음 단계를 수행합니다.

1. 애플리케이션을 등록합니다.
2. 암시적 권한 부여 토큰을 설정합니다.
3. API 권한을 설정합니다.
4. 클라이언트 암호를 만듭니다.


## <a name="session-border-controller-configuration"></a>세션 테두리 컨트롤러 구성 

포함된 Survivable Branch Appliance를 사용하여 세션 테두리 컨트롤러를 구성하는 방법에 대한 단계별 지침은 SBC 공급업체에서 제공하는 설명서를 참조하세요. 

- [AudioCodes](https://www.audiocodes.com/library/technical-documents?query=sba)

- [리본 메뉴](https://support.sonus.net/pages/viewpage.action?pageId=248644034)

- [Oracle](https://www.oracle.com/technical-resources/documentation/acme-packet.html#Link-MicrosoftTeams) 

- [TE-Systems](https://www.anynode.de/microsoft-teams-sba/)

## <a name="reporting-issues"></a>보고 문제

SBC 공급업체의 지원 조직에 문제를 보고합니다. 문제를 보고할 때 Survivable Branch Appliance가 구성되어 있음을 나타냅니다.

## <a name="known-issues"></a>알려진 문제

- 새 Survivable Branch Appliance를 추가하는 경우 Survivable Branch Appliance 정책에서 사용하기까지 다소 시간이 걸릴 수 있습니다.

- 사용자에게 Survivable Branch Appliance 정책을 할당하는 경우 Get-CsOnlineUser의 출력에 SBA가 표시되기까지 다소 시간이 걸릴 수 있습니다. 

- Azure AD 연락처에 대한 역방향 번호 조회가 수행되지 않습니다. 

- SBA는 착신 전환 설정을 지원하지 않습니다. 

- 동적 긴급 통화(E911)를 위해 구성된 긴급 번호에 대한 긴급 전화 걸기는 지원되지 않습니다.
