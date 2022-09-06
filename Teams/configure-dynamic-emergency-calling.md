---
title: 동적인 긴급 전화 구성
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
- m365initiative-voice
ms.reviewer: roykuntz
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- NOCSH
description: Microsoft 통화 플랜 및 전화 시스템 직접 라우팅 동적 긴급 통화 기능을 구성하는 방법을 알아봅니다.
ms.custom: seo-marvel-mar2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9109f26abc953fd131e96440bd62d147cac8114f
ms.sourcegitcommit: 75dfc3cd9b59282d68e35e4d7185da572eb3795c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/06/2022
ms.locfileid: "67606037"
---
# <a name="plan-and-configure-dynamic-emergency-calling"></a>동적인 긴급 전화 계획 및 구성 

Microsoft 통화 플랜, 운영자 연결, 운영자 연결 모바일(공개 미리 보기 릴리스) 및 직접 라우팅에 대한 동적 긴급 호출은 긴급 통화를 구성 및 라우팅하고 Teams 클라이언트의 현재 위치에 따라 보안 담당자에게 알리는 기능을 제공합니다.  

테넌트 관리자가 정의하는 네트워크 토폴로지(긴급 주소와 연결된 네트워크 요소)에 따라 Teams 클라이언트는 LIS(위치 정보 서비스)에 대한 요청에서 네트워크 연결 정보를 제공합니다. 일치하는 항목이 있으면 LIS는 클라이언트에 위치를 반환합니다.

Teams 클라이언트에는 긴급 통화의 일부로 위치 데이터가 포함됩니다. 그런 다음 응급 서비스 공급자가 이 데이터를 사용하여 적절한 PSAP(공공 안전 응답 지점)를 확인하고 해당 PSAP로 통화를 라우팅하여 PSAP 디스패처가 호출자의 위치를 가져올 수 있도록 합니다.  

동적 긴급 호출의 경우 다음이 발생해야 합니다.

1. 네트워크 관리자는 네트워크 설정 및 LIS를 구성하여 네트워크/긴급 위치 맵을 만듭니다.

2. 시작 및 이후에 주기적으로 또는 네트워크 연결이 변경되면 Teams 클라이언트는 네트워크 연결 정보가 포함된 위치 요청을 네트워크 설정 및 LIS로 보냅니다.

   - 네트워크 설정 사이트 일치가 있는 경우 긴급 통화 정책이 해당 사이트에서 Teams 클라이언트로 반환됩니다. (정책에 대한 자세한 내용은 [긴급 정책 구성](#configure-emergency-policies)을 참조하세요).

   - LIS 일치 항목이 있는 경우 Teams 클라이언트가 연결된 네트워크 요소의 긴급 위치가 Teams 클라이언트로 반환됩니다. 일치는 일치하는 첫 번째 결과가 반환되는 순서대로 수행됩니다.
       - Wap
       - 이더넷 스위치/포트
       - 이더넷 스위치
       - 서브넷

3. Teams 클라이언트가 긴급 전화를 걸면 긴급 위치가 PSTN 네트워크로 전달됩니다.

적절한 PSAP(Public Safety Answering Point)로 자동 라우팅하는 기능은 Teams 사용자의 사용 국가에 따라 달라집니다.

Microsoft 통화 플랜, 운영자 연결 파트너 및 운영자 연결 모바일 파트너에는 미국 및 캐나다 사용자에 대한 동적 긴급 라우팅 서비스가 포함됩니다.

그러나 직접 라우팅의 경우 긴급 통화 라우팅 및 파트너 연결에 추가 구성이 필요합니다. 관리자는 온라인 PSTN 게이트웨이 개체에서 PidfloSupported 매개 변수를 True로 설정하여 긴급 호출을 라우팅하는 PSTN 게이트웨이가 나가는 INVITE에 위치 정보를 추가하도록 구성되었는지 확인해야 합니다. 또한 관리자는 ERS(긴급 라우팅 서비스) 공급자(미국 및 캐나다)에 대한 연결을 구성 **하거나** ELIN(긴급 위치 식별 번호) 애플리케이션에 대한 SBC(세션 테두리 컨트롤러)를 구성해야 합니다. ERS 공급자에 대한 자세한 내용은 [직접 라우팅에 대해 인증된 세션 테두리 컨트롤러를 참조하세요](direct-routing-border-controllers.md).

이 문서에는 다음 섹션이 포함되어 있습니다.

- [긴급 주소 할당](#assign-emergency-addresses)
- [네트워크 설정 구성](#configure-network-settings)
- [위치 정보 서비스 구성](#configure-location-information-service)
- [긴급 정책 구성](#configure-emergency-policies)
- [사용자 및 사이트 사용](#enable-users-and-sites)
- [긴급 통화 테스트](#test-emergency-calling)

긴급 주소 및 긴급 통화 라우팅에 대한 정보, 국가별 정보 및 네트워크 설정 및 네트워크 토폴로지 정보를 포함하여 긴급 통화에 대한 자세한 내용은 다음을 참조하세요.

- [긴급 통화 관리](what-are-emergency-locations-addresses-and-call-routing.md)
- [클라우드 음성 기능에 대한 네트워크 설정 관리](cloud-voice-network-settings.md)
- [클라우드 음성 기능에 대한 네트워크 토폴로지 관리](manage-your-network-topology.md)

정부 클라우드에서 사용할 수 있는 기능에 대한 자세한 내용은 이 문서의 끝에 있는 [정부 지원을](#government-support) 참조하세요.


## <a name="supported-clients"></a>지원되는 클라이언트

현재 지원되는 클라이언트는 다음과 같습니다.  이 목록에 대한 업데이트를 보려면 자주 다시 확인하세요.

- Microsoft Windows용 Teams 데스크톱 클라이언트
- Apple macOS용 Teams 데스크톱 클라이언트
- Apple iOS 클라이언트 버전 1.0.92.2019121004 및 App Store 버전 1.0.92 이상용 Teams 모바일 클라이언트
- Android 클라이언트 및 Google Play 스토어 버전 1416/1.0.0.2019121201 이상용 Teams 모바일 클라이언트
- Teams 휴대폰 버전 1449/1.0.94.2019110802 이상
- Teams 룸 버전 4.4.25.0 이상

> [!NOTE]
> 서브넷 및 WiFi 기반 위치는 지원되는 모든 Teams 클라이언트에서 지원됩니다. <br><br>
> LLDP(이더넷/스위치)는 다음에서 지원됩니다.
> - 현재 Windows 버전 10.0 이상.<br>
> - MAC OS- [LLDP 사용 소프트웨어](https://www.microsoft.com/download/details.aspx?id=103383)가 필요합니다.<br>
> - Teams 앱 버전 1449/1.0.94.2021110101 이상이 포함된 Teams 전화.

> [!NOTE]
> 보안 데스크 알림을 포함한 동적 긴급 통화는 Teams 웹 클라이언트에서 지원되지 않습니다. 사용자가 Teams 웹 클라이언트를 사용하여 PSTN 번호를 호출하지 못하도록 하려면 Teams 통화 정책을 설정하고 **웹 PSTN 통화 허용** 설정을 해제할 수 있습니다. 자세한 내용은 Teams 및 [Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps)[의 통화 정책을](teams-calling-policy.md) 참조하세요. 

> [!NOTE]
> 3PIP 전화는 동적 긴급 통화를 지원하지 않습니다. 



## <a name="assign-emergency-addresses"></a>긴급 주소 할당

다음과 같이 긴급 주소를 할당할 수 있습니다.

- 통화 플랜 사용자에게.

- 운영자 연결 및 운영자 연결 모바일 운송업체가 고객의 인벤토리에 업로드할 때 번호에 할당된 기능에 따라 사용자를&mdash;운영자 연결 모바일.

- 위치를 동적으로 가져오는 데 필요한 네트워크 식별자입니다. 

미국 내에서 긴급 통화의 자동 라우팅을 지원하려면 네트워크 식별자에 할당된 긴급 위치에 연결된 지역 코드가 포함되어 있는지 확인해야 합니다. (지역 코드가 없는 긴급 주소는 동적 위치에 필요한 네트워크 식별자에 할당할 수 없습니다.)

Azure Maps 위치 기반 서비스에 사용됩니다. Microsoft Teams 관리 센터를 사용하여 긴급 주소를 입력하면 Teams에서 Azure Maps 주소를 확인합니다.

- 일치하는 항목이 발견되면 지역 코드가 자동으로 포함됩니다.

- 일치하는 항목을 찾을 수 없는 경우 긴급 주소를 수동으로 만들 수 있습니다. PIN 삭제 기능을 사용하여 이 작업을 수행할 수 있습니다. 

> [!NOTE]
> 2년 이상 된 긴급 주소는 네트워크 식별자에 할당할 수 없습니다. 이전 주소를 다시 만들어야 합니다.

Microsoft Teams 관리 센터 또는 PowerShell을 사용하여 긴급 주소를 추가하고 할당합니다. 자세한 내용은 [조직의 긴급 위치 추가](add-change-remove-emergency-location-organization.md) 및 [사용자에 대한 긴급 위치 할당을](assign-change-emergency-location-user.md) 참조하세요.

## <a name="configure-network-settings"></a>네트워크 설정 구성

네트워크 설정은 Teams 클라이언트의 위치를 확인하고 긴급 통화 정책 및 긴급 위치를 동적으로 가져오는 데 사용됩니다. 조직에서 긴급 통화 기능을 원하는 방식에 따라 네트워크 설정을 구성할 수 있습니다.

네트워크 설정에는 서브넷 컬렉션이 포함된 사이트가 포함되며 이러한 사이트는 사용자에게 동적 정책 할당에만 사용됩니다. 예를 들어 긴급 통화 정책 및 긴급 통화 라우팅 정책을 "Redmond 사이트"에 할당하여 집이나 다른 Microsoft 위치에서 로밍하는 모든 사용자가 Redmond에 한정된 긴급 번호, 라우팅 및 보안 데스크로 구성될 수 있습니다.  

신뢰할 수 있는 IP 주소는 엔터프라이즈 네트워크의 인터넷 외부 IP 주소 컬렉션을 포함하며 사용자의 엔드포인트가 회사 네트워크 내에 있는지 확인하는 데 사용됩니다. 동적 정책 또는 위치를 가져오려는 시도는 사용자의 외부 IP 주소가 신뢰할 수 있는 IP 주소의 IP 주소와 일치하는 경우에만 이루어집니다.

IP 주소, 네트워크 지역, 사이트 및 서브넷 주소에 대한 자세한 내용은 [클라우드 음성 기능에 대한 네트워크 설정을](cloud-voice-network-settings.md) 참조하세요.

Microsoft Teams 관리 센터에서 또는 PowerShell을 사용하여 네트워크 설정을 구성합니다. 자세한 내용은 [클라우드 음성 기능에 대한 네트워크 토폴로지 관리를 참조하세요](manage-your-network-topology.md).

네트워크 설정의 일부 변경 내용(예: 새 주소, 네트워크 식별자 등)이 전파되고 Teams 클라이언트에서 사용할 수 있는 데는 몇 시간(최대 몇 시간)이 걸릴 수 있습니다.  

> [!Note]
> 서브넷은 LIS에서 정의할 수도 있으며 긴급 위치와 연결할 수도 있습니다.  LIS 서브넷은 클라이언트에 할당된 서브넷 IP 범위와 일치하는 네트워크 ID로 정의되어야 합니다. 예를 들어 클라이언트 IP/마스크 10.10.10.150/25의 네트워크 ID는 10.10.10.128입니다. 자세한 내용은 [TCP/IP 주소 지정 및 서브넷 기본 사항 이해를 참조하세요](/troubleshoot/windows-client/networking/tcpip-addressing-and-subnetting).

> [!Important]
> Teams 클라이언트에서 원본 IP 주소를 수정하는 클라우드 프록시 서비스 배포에서는 네트워크 구성 설정 조회가 지원되지 않습니다.



**통화 플랜, 운영자 연결 및 운영자 연결 모바일 사용자의 경우:**

- 보안 데스크 알림의 동적 구성이 필요한 경우 신뢰할 수 있는 IP 주소와 네트워크 사이트를 모두 구성해야 합니다.

- 동적 위치만 필요한 경우 신뢰할 수 있는 IP 주소만 구성해야 합니다. 네트워크 설정을 구성할 필요는 없습니다.

- 둘 다 필요하지 않은 경우 네트워크 설정을 구성할 필요가 없습니다. 

**직접 라우팅 사용자의 경우:**

- 긴급 통화의 동적 사용 또는 보안 데스크 알림의 동적 구성이 필요한 경우 신뢰할 수 있는 IP 주소와 네트워크 사이트를 모두 구성해야 합니다.

- 동적 위치만 필요한 경우 신뢰할 수 있는 IP 주소만 구성해야 합니다. 네트워크 설정을 구성할 필요는 없습니다.

- 둘 다 필요하지 않은 경우 네트워크 설정을 구성할 필요가 없습니다.


## <a name="configure-location-information-service"></a>위치 정보 서비스 구성

Teams 클라이언트는 다른 네트워크 식별자와 연결된 위치에서 긴급 주소를 가져옵니다. 

클라이언트가 위치를 가져오려면 네트워크 식별자(서브넷, WAP, 스위치, 포트) 및 긴급 위치로 LIS를 채워야 합니다. Microsoft Teams 관리 센터에서 또는 PowerShell을 사용하여 이 작업을 수행할 수 있습니다.

### <a name="using-the-microsoft-teams-admin-center"></a>Microsoft Teams 관리 센터 사용

1. 왼쪽 탐색 영역에서 **위치** > **네트워크 & 위치** 로 이동합니다.
2. 추가할 네트워크 식별자를 나타내는 탭을 클릭합니다. 예를 들어 **서브넷**, **Wi-Fi 액세스 지점**, 스위치 또는 **포트****를** 클릭합니다. 그런 다음 **추가** 를 클릭합니다.
3. 필드를 완료하고 긴급 위치를 추가한 다음 **적용** 을 클릭합니다.

### <a name="using-powershell"></a>PowerShell 사용

다음 cmdlet을 사용하여 포트, 스위치, 서브넷 및 WAP를 LIS에 추가합니다.

- [가져오기](/powershell/module/skype/get-csonlinelissubnet?view=skype-ps), [설정](/powershell/module/skype/set-csonlinelissubnet?view=skype-ps), [제거](/powershell/module/skype/remove-csonlinelissubnet?view=skype-ps) -CsOnlineLisSubnet
- [Get](/powershell/module/skype/get-csonlinelisport?view=skype-ps), [Set](/powershell/module/skype/set-csonlinelisport?view=skype-ps), [Remove](/powershell/module/skype/remove-csonlinelisport?view=skype-ps) -CsOnlineLisPort
- [Get](/powershell/module/skype/get-csonlineliswirelessaccesspoint?view=skype-ps), [Set](/powershell/module/skype/set-csonlineliswirelessaccesspoint?view=skype-ps), [Remove](/powershell/module/skype/remove-csonlineliswirelessaccesspoint?view=skype-ps) -CsOnlineLisWirelessAccessPoint
- [Get](/powershell/module/skype/get-csonlinelisswitch?view=skype-ps), [Set](/powershell/module/skype/set-csonlinelisswitch?view=skype-ps), [Remove](/powershell/module/skype/remove-csonlinelisswitch?view=skype-ps) -CsOnlineLisSwitch

>[!Important]
>네트워크 사이트의 일부로 서브넷을 사용하는 경우 동적 위치를 렌더링하려면 위치 정보 서비스에서 서브넷을 다시 정의해야 합니다.

## <a name="configure-emergency-policies"></a>긴급 정책 구성

다음 정책을 사용하여 긴급 통화를 구성합니다. Microsoft Teams 관리 센터에서 또는 PowerShell을 사용하여 이러한 정책을 관리할 수 있습니다.

- **긴급 통화 라우팅 정책 – 직접 라우팅에만 적용됩니다**. 이 정책은 긴급 번호, 원하는 경우 숫자당 마스크 및 숫자당 PSTN 경로를 구성합니다. 이 정책을 사용자, 네트워크 사이트 또는 둘 다에 할당할 수 있습니다. 자세한 내용은 [직접 라우팅에 대한 긴급 통화 라우팅 정책 관리를 참조하세요](manage-emergency-call-routing-policies.md).  

   (통화 플랜, 운영자 연결 및 운영자 연결 모바일 사용자는 Microsoft 365 또는 Office 365 사용 위치에 따라 국가의 긴급 번호로 긴급 통화를 자동으로 사용할 수 있습니다.)

- **긴급 통화 정책 - 통화 플랜, 운영자 연결, 운영자 연결 모바일 및 직접 라우팅에 적용됩니다.** 이 정책은 긴급 통화가 수행되면 보안 데스크 알림 환경을 구성합니다. 알릴 사람 및 알림 방법을 설정할 수 있습니다. 예를 들어 조직의 보안 데스크에 자동으로 알리고 긴급 통화에서 수신 대기하도록 합니다.  이 정책은 사용자 또는 네트워크 사이트 또는 둘 다에 할당할 수 있습니다. 자세한 내용은 [Teams에서 긴급 통화 정책 관리를 참조하세요](manage-emergency-calling-policies.md).

## <a name="enable-users-and-sites"></a>사용자 및 사이트 사용

긴급 통화 라우팅 정책 및 긴급 통화 정책을 사용자 및 사이트에 할당할 수 있습니다. 긴급 통화 라우팅 정책은 직접 라우팅에만 적용됩니다. (통화 플랜, 운영자 연결 또는 운영자 연결 모바일 사용자에게 이 정책을 할당할 수 있지만 정책은 적용되지 않습니다.)

Microsoft Teams 관리 센터에서 또는 PowerShell을 사용하여 정책을 할당합니다. 자세한 내용은 다음을 참조하세요.

- [직접 라우팅에 대한 긴급 통화 라우팅 정책 관리](manage-emergency-call-routing-policies.md)
- [Teams에서 긴급 통화 정책 관리](manage-emergency-calling-policies.md)

다음은 PowerShell 예제입니다.

보안 데스크 알림에 특정 사용자를 사용하도록 설정하려면 다음 명령을 사용합니다.

```PowerShell
Grant-CsTeamsEmergencyCallingPolicy -Identity user1 -PolicyName SecurityDeskNotification
```

사이트 1에 "Contoso 긴급 통화 정책 1"이라는 정책을 할당하려면 다음 명령을 사용합니다.

```PowerShell
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallingPolicy "Contoso Emergency Calling Policy 1"
```

긴급 통화에 특정 직접 라우팅 사용자를 사용하도록 설정하려면 다음 명령을 사용합니다.

```PowerShell
Grant-CsTeamsEmergencyCallRoutingPolicy -Identity user1 -PolicyName UnitedStates
```

사이트 1에 "Contoso New York 긴급 통화 라우팅"이라는 정책을 할당하려면 다음 명령을 사용합니다.

```PowerShell
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallRoutingPolicy "Contoso New York Emergency Call Routing"
```

네트워크 사이트 및 사용자에게 긴급 통화 정책을 할당하고 해당 사용자가 해당 네트워크 사이트에 있는 경우 네트워크 사이트에 할당된 정책은 사용자에게 할당된 정책을 재정의합니다.

## <a name="test-emergency-calling"></a>긴급 통화 테스트

미국 일부 ERSP(긴급 라우팅 서비스 공급자)는 긴급 통화 테스트 봇을 제공합니다.

- **미국 또는 캐나다의 통화 플랜, 운영자 연결 및 운영자 연결 모바일 사용자는** 미리 정의된 테스트 긴급 번호 933을 사용하여 긴급 통화 구성의 유효성을 검사할 수 있습니다. 이 번호는 봇으로 라우팅됩니다. 그러면 호출자 전화 번호(통화 회선 ID), 긴급 주소 또는 위치 및 통화가 자동으로 PSAP로 라우팅되는지 또는 먼저 스크린될지 여부를 다시 에코합니다.

- **미국 직접 라우팅 고객은** 테스트 서비스에 대한 ERSP와 조정해야 합니다.

## <a name="government-support"></a>정부 지원

다음 표에서는 정부 클라우드의 동적 긴급 통화에 대한 지원을 보여 줍니다.

| 클라우드 | 가용성 |
| :------------|:-------|
| World Wide 다중 테넌트 | 모든 Teams 클라이언트에서 사용 가능 |
| Gcc | 모든 Teams 클라이언트에서 사용 가능 |
| GCCH | -Teams 데스크톱에서 사용 가능 <br> -Teams 모바일 클라이언트에서 사용 가능 <br> -Teams 휴대폰, 앱 버전에서 사용 가능: 1449/1.0.94.2022061702 |
| 국방부 | 보류 중 |

 ## <a name="related-topics"></a>관련 주제

- [긴급 통화 관리](what-are-emergency-locations-addresses-and-call-routing.md)
- [긴급 전화 정책 관리](manage-emergency-calling-policies.md)
- [긴급 통화 라우팅 정책 관리 ](manage-emergency-call-routing-policies.md)
- [조직의 응급 위치 추가, 변경 또는 제거](add-change-remove-emergency-location-organization.md)
- [사용자의 긴급 위치 할당 또는 변경](assign-change-emergency-location-user.md)
- [클라우드 음성 기능에 대한 네트워크 설정](cloud-voice-network-settings.md)
- [클라우드 음성 기능에 대한 네트워크 토폴로지 관리](manage-your-network-topology.md)
