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
- m365initiative-voice
ms.reviewer: crowe
search.appverid: MET150
f1.keywords:
- NOCSH
- ms.teamsadmincenter.directrouting.overview
description: 구성, 필수 핵심 배포 결정 및 음성 라우팅 고려 사항과 같은 직접 라우팅에 대해 자세히 설명합니다.
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8c25299a0f0df6863bcb1fbaa4627b891a6e860a
ms.sourcegitcommit: 75adb0cc163974772617c5e78a1678d9dbd9d76f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/22/2021
ms.locfileid: "60536759"
---
# <a name="survivable-branch-appliance-sba-for-direct-routing"></a>직접 라우팅을 위한 SBA(생존 가능한 분기 어플라이언스)


경우에 따라 직접 라우팅을 사용하여 시스템에 연결하기 위해 Microsoft 전화 사이트가 인터넷이 정전될 수 있습니다.

고객 사이트(분기라고도 불리는)는 직접 라우팅을 통해 일시적으로 Microsoft 클라우드에 연결할 수 없다고 가정합니다. 그러나 분기 내부의 인트라넷은 여전히 완벽하게 작동하며 사용자는 PSTN 연결을 제공하는 SBC(세션 테두리 컨트롤러)에 연결할 수 있습니다.

이 문서에서는 SBA(지속 가능한 분기 어플라이언스)를 사용하여 시스템 Microsoft 전화 정전 시 PSTN(공용 전환 전화 네트워크) 호출을 계속하고 받을 수 있도록 하는 방법을 설명합니다.

## <a name="prerequisites"></a>필수 구성 요소

SBA는 SBA가 별도의 VM 또는 하드웨어에서 실행될 수 있도록 해당 펌웨어에 코드를 추가하거나 별도로 배포하는 SBC 공급업체에 Microsoft에서 제공하는 배포 가능한 코드입니다. 

포함된 살아남을 수 있는 분기 어플라이언스를 사용하여 최신 세션 테두리 컨트롤러 펌웨어를 얻었다면 SBC 공급업체에 문의합니다. 또한 다음이 필요합니다.

- 분기 사이트의 클라이언트가 SBC와 직접 Microsoft Teams 수 있도록 미디어 우회를 위해 SBC를 구성해야 합니다. 

- SBA VM OS에서 TLS1.2를 사용하도록 설정해야 합니다.
- 포트 3443, 4444 및 8443은 Microsoft SBA Server에서 클라이언트와 통신하는 데 Teams 방화벽에서 허용해야 합니다. 
- 포트 5061(또는 SBC에서 구성된 포트)은 Microsoft SBA Server에서 SBC와 통신하는 데 사용하며 방화벽에서 허용해야 합니다. 
- UDP 포트 123은 Microsoft SBA Server에서 NTP 서버와 통신하는 데 사용하며 방화벽에서 허용해야 합니다.
- 포트 443은 Microsoft SBA Server에서 포트와 통신하는 데 Microsoft 365 방화벽에서 허용해야 합니다.
- 공용 클라우드에 대한 Azure IP 범위 및 서비스 태그는 다음에 설명된 지침에 따라 정의해야 합니다. https://www.microsoft.com/download/details.aspx?id=56519

## <a name="supported-teams-clients"></a>지원되는 Teams 클라이언트

SBA 기능은 다음 클라이언트에서 Microsoft Teams 지원합니다. 

- Microsoft Teams Windows 데스크톱 

- Microsoft Teams macOS 데스크톱 

## <a name="how-it-works"></a>작동 방식

인터넷이 중단되는 동안 Teams 클라이언트가 자동으로 SBA로 전환해야 합니다. 지속적인 호출은 중단 없이 계속됩니다. 사용자가 아무 작업도 필요하지 않습니다. 클라이언트가 인터넷이 Teams 호출이 완료되면 클라이언트가 정상 작업 모드로 돌아가서 다른 Teams 합니다. SBA는 수집된 통화 데이터 레코드를 클라우드에 업로드하고 테넌트 관리자가 이 정보를 검토할 수 있도록 통화 기록이 업데이트됩니다. 

클라이언트가 Microsoft Teams 모드인 경우 다음 호출 관련 기능을 사용할 수 있습니다. 

- SBC를 통해 미디어가 흐르는 로컬 SBA/SBC를 통해 PSTN 호출을 합니다.

- SBC를 통해 미디어가 흐르는 로컬 SBA/SBC를 통해 PSTN 호출을 수신합니다. 

- PSTN 호출을 보류하고 다시 시작합니다.

## <a name="configuration"></a>구성

SBA 기능이 작동하기 Teams 클라이언트는 각 분기 사이트에서 사용할 수 있는 SBA와 해당 사이트의 사용자에게 할당된 SBA를 알아야 합니다. 구성 단계는 다음과 같습니다.

1. SBAs를 생성합니다.
2. 분기 Teams 정책을 생성합니다.
3. 사용자에게 정책을 할당합니다.
4. SBA에 애플리케이션을 Azure Active Directory.

모든 구성은 비즈니스용 Skype PowerShell cmdlet을 사용하여 수행됩니다. (Teams 관리 센터는 아직 직접 라우팅 SBA 기능을 지원하지 않습니다.) 

(SBC 공급업체 설명서에 대한 링크가 있는 SBC 구성에 대한 자세한 내용은 이 문서의 끝에 있는 세션 테두리 컨트롤러 구성을 참조하세요.)

### <a name="create-the-sbas"></a>SBAs 만들기

SBAs를 만들 때 New-CsTeamsSurvivableBranchAppliance cmdlet을 사용하게 될 것입니다. 이 cmdlet에는 다음과 같은 매개 변수가 있습니다.

| 매개 변수| 설명 |
| :------------|:-------|
| Identity  | SBA의 ID  |
| Fqdn | SBA의 FQDN |
| 사이트 | SBA가 있는 TenantNetworkSite |
| 설명 | 무료 서식 텍스트 |
|||

예를 들면 다음과 같습니다.

``` powershell
C:\> New-CsTeamsSurvivableBranchAppliance  -Fqdn sba1.contoso.com -Description "SBA 1" 
Identity    : sba1.contoso.com 
Fqdn        : sba1.contoso.com 
Site        : 
Description : SBA 1 
```

### <a name="create-the-teams-branch-survivability-policy"></a>분기 Teams 정책 만들기 

정책을 만들 때 New-CsTeamsSurvivableBranchAppliancePolicy cmdlet을 사용할 수 있습니다. 이 cmdlet에는 다음 매개 변수가 있습니다. 정책에 하나 이상의 SBAS가 포함될 수 있습니다.

| 매개 변수| 설명 |
| :------------|:-------|
| Identity | 정책의 ID |
| BranchApplianceFqdns  | 사이트의 SBA의 FQDN |
||

예를 들면 다음과 같습니다.

``` powershell
C:\> new-CsTeamsSurvivableBranchAppliancePolicy -Identity CPH -BranchApplianceFqdns "sba1.contoso.com","sba2.contoso.com" 
Identity             : Tag:CPH 
BranchApplianceFqdns : {sba1.contoso.com, sba2.contoso.com} 
```

Set-CsTeamsSurvivableBranchAppliancePolicy cmdlet을 사용하여 정책에서 SBAs를 추가하거나 제거할 수 있습니다. 예를 들면 다음과 같습니다. 

``` powershell
Set-CsTeamsSurvivableBranchAppliancePolicy -Identity CPH -BranchApplianceFqdns @{remove="sba1.contoso.com"} 
Set-CsTeamsSurvivableBranchAppliancePolicy -Identity CPH -BranchApplianceFqdns @{add="sba1.contoso.com"} 
```

### <a name="assign-a-policy-to-a-user"></a>사용자에게 정책 할당

개별 사용자에게 정책을 할당하기 위해 Grant-CsTeamsSurvivableBranchAppliancePolicy cmdlet을 사용하게 됩니다. 이 cmdlet에는 다음과 같은 매개 변수가 있습니다.

| 매개 변수| 설명 |
| :------------|:-------|
| Identity | 사용자의 ID |
| PolicyName | 정책의 ID |
||

예를 들면 다음과 같습니다.

``` powershell
C:\> Grant-CsTeamsSurvivableBranchAppliancePolicy -PolicyName CPH -Identity user@contoso.com 
```

다음 예제에 표시된 $Null 정책을 부여하여 사용자에서 정책을 제거할 수 있습니다.

``` powershell
C:\> Grant-CsTeamsSurvivableBranchAppliancePolicy -PolicyName $Null -Identity user@contoso.com 
```

### <a name="register-an-application-for-the-sba-with-azure-active-directory"></a>SBA에 애플리케이션을 Azure Active Directory

테넌트 내에서 사용되는 다양한 SBA를 사용하여 SBA에서 필요한 데이터를 Microsoft 365 허용하려면 SBA에 애플리케이션을 Azure Active Directory. 

애플리케이션 등록에 대한 자세한 내용은 다음을 참조하세요.

- [비즈니스용 앱 개발 Azure Active Directory](/azure/active-directory/manage-apps/developer-guidance-for-integrating-applications)

- [애플리케이션을](/azure/active-directory/develop/quickstart-register-app)Microsoft ID 플랫폼.  

테넌트의 모든 SBAs에서 사용하기 위해 하나의 애플리케이션만 등록하면 됩니다. 

SBA 등록의 경우 등록에서 만든 다음 값이 필요합니다. 

- 애플리케이션(클라이언트) ID 
- 클라이언트 비밀 

SBA 애플리케이션의 경우 다음을 염두에 두어야 합니다. 

- 이름은 원하는대로 될 수 있습니다.  
- 지원되는 계정 유형 = 이 조직 디렉터리의 계정만 해당됩니다. 
- 웹 리디렉션 Uri = https://login.microsoftonline.com/common/oauth2/nativeclient .
- 암시적 부여 토큰 = 액세스 토큰 및 ID 토큰. 
- API 권한 = Skype Teams 관리 액세스 -> 애플리케이션 권한 -> application_access_custom_sba_appliance.
- 클라이언트 비밀: 설명 및 만료를 사용할 수 있습니다. 
- 클라이언트 비밀을 만드는 즉시 복사해야 합니다. 
- 애플리케이션(클라이언트) ID는 개요 탭에 표시됩니다.

그런 다음 다음 단계를 수행합니다.

1. 애플리케이션을 등록합니다.
2. 암시적 부여 토큰을 설정합니다.
3. API 권한을 설정합니다.
4. 클라이언트 비밀을 생성합니다.


## <a name="session-border-controller-configuration"></a>세션 테두리 컨트롤러 구성 

포함된 Survivable 분기 어플라이언스로 세션 테두리 컨트롤러를 구성하는 방법에 대한 단계별 지침은 SBC 공급업체에서 제공하는 설명서를 참조하세요. 

- [AudioCodes](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-survivable-branch-appliances)

- [리본 메뉴](https://support.sonus.net/pages/viewpage.action?pageId=248644034)

- [Oracle](https://www.oracle.com/technical-resources/documentation/acme-packet.html#Link-MicrosoftTeams) 

- [TE-Systems](https://www.anynode.de/microsoft-teams-sba/)

## <a name="reporting-issues"></a>보고 문제

SBC 공급업체의 지원 조직에 문제를 보고합니다. 문제를 보고할 때 살아남을 수 있는 분기 어플라이언스가 구성된 것을 나타냅니다.

## <a name="known-issues"></a>알려진 문제

- 새 Survivable 분기 어플라이언스를 추가하는 경우 생존 가능한 분기 어플라이언스 정책에서 사용할 수 있는 데 다소 시간이 걸릴 수 있습니다.

- 사용자에게 생존 가능한 분기 어플라이언스 정책을 할당하는 경우 Get-CsOnlineUser의 출력에 SBA가 표시되기까지 다소 시간이 걸릴 수 있습니다. 

- Azure AD 연락처에 대한 역방향 번호 보기는 수행되지 않습니다. 

- SBA는 통화 전달 설정을 지원하지 않습니다. 

- 동적 긴급 호출(E911)에 대해 구성된 긴급 번호에 대한 긴급 호출은 지원되지 않습니다.
