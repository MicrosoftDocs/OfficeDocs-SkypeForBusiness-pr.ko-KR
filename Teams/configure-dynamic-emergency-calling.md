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
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
description: Microsoft 통화 계획 및 전화 시스템 다이렉트 라우팅 동적 긴급 통화 기능을 구성하는 방법에 대해 자세히 알아보도록 합니다.
ms.custom: seo-marvel-mar2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: ca2fb94ff67f2efa874e670926330f8f3630cbe2
ms.sourcegitcommit: 74f12ed15e1aa1106fa47b95597bde451b0b37f4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2021
ms.locfileid: "50741889"
---
# <a name="plan-and-configure-dynamic-emergency-calling"></a>동적인 긴급 전화 계획 및 구성 

Microsoft 통화 계획 및 전화 시스템 직접 라우팅에 대한 동적 긴급 호출은 Teams 클라이언트의 현재 위치에 따라 긴급 통화를 구성하고 라우팅하고 보안 담당자에게 알릴 수 있는 기능을 제공합니다.  

테넌트 관리자가 정의하는 네트워크 토폴로지에 따라 Teams 클라이언트는 LIS(위치 정보 서비스)에 대한 요청에서 네트워크 연결 정보를 제공합니다. 일치가 있는 경우 LIS는 클라이언트에 위치를 반환합니다. 이 위치 데이터는 클라이언트로 다시 전송됩니다.  

Teams 클라이언트에는 긴급 호출의 일부로 위치 데이터가 포함됩니다. 그런 다음, 이 데이터는 응급 서비스 공급자가 적절한 PSAP(공용 안전 응답 지점)를 결정하고 해당 PSAP로 호출을 라우팅하는 데 사용됩니다. 이는 PSAP 디스패치가 발신자 위치를 얻을 수 있도록 합니다.  

동적 긴급 호출의 경우 다음이 발생해야 합니다.

1. 네트워크 관리자는 네트워크 설정 및 LIS를 구성하여 네트워크/긴급 위치 맵을 생성합니다.

   직접 라우팅의 경우 긴급 호출을 라우팅하고 파트너 연결을 위해 추가 구성이 필요합니다. 관리자는 ERS(긴급 라우팅 **서비스)** 공급자(미국)에 대한 연결을 구성하거나 ELIN(긴급 위치 식별 번호) 애플리케이션에 대한 세션 경계 컨트롤러(SBC)를 구성해야 합니다.

2. 시작 중 및 이후에 주기적으로 또는 네트워크 연결이 변경될 때 Teams 클라이언트는 네트워크 연결 정보가 포함된 위치 요청을 네트워크 설정 및 LIS로 전송합니다.

   - 네트워크 설정 사이트 일치가 있는 경우 - 긴급 호출 정책은 해당 사이트에서 Teams 클라이언트에 반환됩니다. 정책에 대한 자세한 내용은 긴급 정책 [구성을 참조하세요.](#configure-emergency-policies)

   - LIS 일치가 있는 경우 - Teams 클라이언트가 연결된 네트워크 요소의 긴급 위치는 Teams 클라이언트로 반환됩니다. 일치는 첫 번째 일치 결과가 반환되는 순서대로 수행됩니다.
       - WAP
       - 이더넷 스위치/포트
       - 이더넷 스위치
       - 서브넷

3. Teams 클라이언트가 긴급 호출을 하면 긴급 위치가 PSTN 네트워크로 전달됩니다.

   직접 라우팅의 경우 관리자는 SBC를 구성하여 ERS 공급자에 긴급 호출을 보내거나 SBC ELIN 애플리케이션을 구성해야 합니다.

이 문서에는 다음 섹션이 포함되어 있습니다.

- [긴급 주소 구성](#assign-emergency-addresses)
- [네트워크 설정 구성](#configure-network-settings)
- [위치 정보 서비스 구성](#configure-location-information-service)
- [긴급 정책 구성](#configure-emergency-policies)
- [사용자 및 사이트 사용](#enable-users-and-sites)
- [긴급 호출 테스트](#test-emergency-calling)

적절한 PSAP(공공 안전 응답 지점)에 대한 자동 라우팅을 할 수 있는 능력은 Teams 사용자의 사용 국가에 따라 다릅니다.

응급 주소 및 긴급 통화 라우팅에 대한 정보, 국가별 정보 및 네트워크 설정 및 네트워크 토폴로지에 대한 정보를 비롯한 긴급 통화에 대한 자세한 내용은 다음을 참조하세요.

- [긴급 통화 관리](what-are-emergency-locations-addresses-and-call-routing.md)
- [클라우드 음성 기능에 대한 네트워크 설정 관리](cloud-voice-network-settings.md)
- [클라우드 음성 기능에 대한 네트워크 토폴로지 관리](manage-your-network-topology.md)

정부 클라우드에서 사용할 수 있는 기능에 대한 자세한 내용은 이 문서의 끝부분에 있는 [정부](#government-support) 지원을 참조하세요.


## <a name="supported-clients"></a>지원되는 클라이언트

다음 클라이언트는 현재 지원됩니다.  이 목록에 대한 업데이트를 확인한 후 자주 확인합니다.

- Microsoft Windows용 Teams 데스크톱 클라이언트
- Apple macOS용 Teams 데스크톱 클라이언트
- Apple iOS 클라이언트 버전 1.0.92.2019121004 및 App Store 버전 1.0.92 이상용 Teams 모바일 클라이언트
- Android 클라이언트 및 Google Play 스토어 버전 1416/1.0.0.2019121201 이상용 Teams 모바일 클라이언트
- Teams 전화 버전 1449/1.0.94.2019110802 이상
- Teams Rooms 버전 4.4.25.0 이상

> [!NOTE]
> 보안 데스크 알림을 포함한 동적 긴급 통화는 Teams 웹 클라이언트에서 지원되지 않습니다. 사용자가 Teams 웹 클라이언트를 사용하여 PSTN 번호를 호출하지 못하도록 방지하기 위해 Teams 호출 정책을 설정하고 웹 **PSTN** 호출 허용 설정을 해제할 수 있습니다. 자세한 내용은 [Teams](teams-calling-policy.md) 및 [Set-CsTeamsCallingPolicy의](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps)통화 정책을 참조합니다.

## <a name="assign-emergency-addresses"></a>긴급 주소 할당

호출 계획 사용자와 위치를 동적으로 획득하는 데 필요한 네트워크 식별자 모두에 긴급 주소를 할당할 수 있습니다. (서브넷 및 WiFi AP가 지원됩니다. 이더넷 스위치/포트는 현재 Windows 8.1 이상에서 지원됩니다.

미국 내에서 긴급 통화의 자동화된 라우팅을 지원하려면 네트워크 식별자에 할당된 긴급 위치에 연결된 지역 코드가 포함되어야 합니다. (지역 코드가 없는 긴급 주소는 동적 위치에 필요한 네트워크 식별자에 할당할 수 없습니다.)

Azure Maps는 위치 기반 서비스에 사용됩니다.  Microsoft Teams 관리 센터를 사용하여 긴급 주소를 입력하면 Teams에서 주소에 대한 Azure Maps를 검사합니다.

- 일치가 발견된 경우 지역 코드가 자동으로 포함됩니다.

- 일치를 찾을 수 없는 경우 긴급 주소를 수동으로 만들 수 있습니다. PIN 드롭 기능을 사용하여 이 작업을 할 수 있습니다. 

즉, 호출 계획 사용자에게 할당하기 위해 만들어진 기존 긴급 위치가 동적 위치를 위한 경우 지역 코드를 포함하도록 동일한 주소를 다시 만들어야 합니다. 두 위치를 구분하기 위해 다른 설명을 포함해야 합니다. 새 비상 위치는 이전 위치가 있는 사용자에게 할당할 수 있습니다. 완전히 마이그레이션되면 이전 위치를 삭제할 수 있습니다.

Microsoft Teams 관리 센터 또는 PowerShell을 사용하여 긴급 주소를 추가하고 할당합니다. 자세한 내용은 [조직의](add-change-remove-emergency-location-organization.md) 긴급 위치 추가 및 사용자에 대한 긴급 위치 [할당을 참조하세요.](assign-change-emergency-location-user.md)

## <a name="configure-network-settings"></a>네트워크 설정 구성

네트워크 설정은 Teams 클라이언트의 위치를 결정하고 긴급 호출 정책 및 긴급 위치를 동적으로 얻는 데 사용됩니다. 조직에서 긴급 호출 기능을 원하는 방법에 따라 네트워크 설정을 구성할 수 있습니다.

네트워크 설정에는 서브넷 컬렉션이 포함된 사이트가 포함되어 있으며 이러한 사이트는 사용자에게 동적 정책 할당에 독점적으로 사용됩니다. 예를 들어, 긴급 통화 정책 및 긴급 통화 라우팅 정책은 "Redmond 사이트"에 할당되어 집이나 다른 Microsoft 위치에서 로밍하는 모든 사용자가 Redmond 관련 긴급 번호, 라우팅 및 보안 데스크로 구성됩니다.  

>[!Note]
>또한 서브넷은 LIS에서 정의할 수 있으며 응급 위치와 연결될 수 있습니다.  

다음 정의를 염두에 두어야 합니다. 자세한 내용은 클라우드 음성 기능에 [대한 네트워크 설정을 참조하세요.](cloud-voice-network-settings.md)

- 신뢰할 수 있는 IP 주소는 엔터프라이즈 네트워크의 인터넷 외부 IP 주소 컬렉션을 포함하며 사용자의 엔드포인트가 회사 네트워크 내부에 있는지 확인하는 데 사용됩니다. 동적 정책 또는 위치를 얻기 위한 시도는 사용자의 외부 IP 주소가 신뢰할 수 있는 IP 주소의 IP 주소와 일치하는 경우만 이행됩니다. IPv4 또는 IPv6 IP 주소에 대해 일치할 수 있으며 네트워크 설정으로 전송되는 IP 패킷의 형식에 따라 달라집니다.  공용 IP 주소에 IPv4 및 IPv6이 모두 있는 경우 둘 다 신뢰할 수 있는 IP 주소로 추가해야 합니다.

- 네트워크 지역에는 네트워크 사이트 모음이 포함되어 있습니다. 

- 네트워크 사이트는 조직에 사무실, 건물 집합 또는 캠퍼스와 같은 물리적 값이 있는 위치를 나타내고 있습니다. 이러한 사이트는 IP 서브넷의 컬렉션으로 정의됩니다.

- 네트워크 서브넷을 특정 네트워크 사이트와 연결해야 합니다. 클라이언트의 위치는 네트워크 서브넷 및 연결된 네트워크 사이트에 따라 결정됩니다.  

Microsoft Teams 관리 센터에서 또는 PowerShell을 사용하여 네트워크 설정을 구성합니다. 자세한 내용은 클라우드 음성 기능에 대한 네트워크 [토폴로지 관리를 참조합니다.](manage-your-network-topology.md)

네트워크 설정(예: 새 주소, 네트워크 식별자 등)을 변경하여 Teams 클라이언트에 전파하고 사용할 수 있는 데 다소 시간이 걸릴 수 있습니다(최대 2시간).  

**요금제 사용자를 호출하는 경우:**

- 보안 데스크 알림의 동적 구성이 필요한 경우 신뢰할 수 있는 IP 주소와 네트워크 사이트를 모두 구성해야 합니다.

- 동적 위치만 필요한 경우 신뢰할 수 있는 IP 주소만 구성해야 합니다.

- 둘 다 필요하지 않은 경우 네트워크 설정을 구성할 필요는 없습니다. 

**직접 라우팅 사용자의 경우:**

- 긴급 통화 또는 보안 데스크 알림의 동적 구성이 필요한 경우 신뢰할 수 있는 IP 주소와 네트워크 사이트를 모두 구성해야 합니다.

- 동적 위치만 필요한 경우 신뢰할 수 있는 IP 주소만 구성해야 합니다.

- 둘 다 필요하지 않은 경우 네트워크 설정을 구성할 필요는 없습니다.


## <a name="configure-location-information-service"></a>위치 정보 서비스 구성

Teams 클라이언트는 다른 네트워크 식별자와 연결된 위치에서 긴급 주소를 얻습니다. 서브넷 및 무선 액세스 지점(WAP)이 모두 지원됩니다. 이더넷 스위치/포트는 현재 Windows 8.1 이상에서 지원됩니다.

클라이언트가 위치를 얻게 하려면 LIS를 네트워크 식별자(서브넷, WAP, 스위치, 포트) 및 긴급 위치로 채워야 합니다. Microsoft Teams 관리 센터에서 또는 PowerShell을 사용하여 이 작업을 할 수 있습니다.

### <a name="using-the-microsoft-teams-admin-center"></a>Microsoft Teams 관리 센터 사용

1. 왼쪽 탐색에서 위치 네트워크 &  >  **로 이동합니다.**
2. 추가할 네트워크 식별자를 나타내는 탭을 클릭합니다. 예를 들어 **서브넷,** **Wi-Fi 액세스 포인트,** **스위치** 또는 **포트를 클릭합니다.** 그런 다음 **추가를 클릭합니다.**
3. 필드를 완료하고 긴급 위치를 추가한 다음 적용을 **클릭합니다.**

### <a name="using-powershell"></a>PowerShell 사용

다음 cmdlet을 사용하여 LIS에 포트, 스위치, 서브넷 및 WAP를 추가합니다.

- [Get](https://docs.microsoft.com/powershell/module/skype/get-csonlinelissubnet?view=skype-ps), [Set](https://docs.microsoft.com/powershell/module/skype/set-csonlinelissubnet?view=skype-ps), [Remove](https://docs.microsoft.com/powershell/module/skype/remove-csonlinelissubnet?view=skype-ps) -CsOnlineLisSubnet
- [Get](https://docs.microsoft.com/powershell/module/skype/get-csonlinelisport?view=skype-ps), [Set](https://docs.microsoft.com/powershell/module/skype/set-csonlinelisport?view=skype-ps), [Remove](https://docs.microsoft.com/powershell/module/skype/remove-csonlinelisport?view=skype-ps) -CsOnlineLisPort
- [Get](https://docs.microsoft.com/powershell/module/skype/get-csonlineliswirelessaccesspoint?view=skype-ps), [Set](https://docs.microsoft.com/powershell/module/skype/set-csonlineliswirelessaccesspoint?view=skype-ps), [Remove](https://docs.microsoft.com/powershell/module/skype/remove-csonlineliswirelessaccesspoint?view=skype-ps) -CsOnlineLisWirelessAccessPoint
- [Get](https://docs.microsoft.com/powershell/module/skype/get-csonlinelisswitch?view=skype-ps), [Set](https://docs.microsoft.com/powershell/module/skype/set-csonlinelisswitch?view=skype-ps), [Remove](https://docs.microsoft.com/powershell/module/skype/remove-csonlinelisswitch?view=skype-ps) -CsOnlineLisSwitch

>[!Important]
>서브넷을 네트워크 사이트의 일부로 사용하는 경우 동적 위치를 렌더링하려면 위치 정보 서비스에서 다시 정의해야 합니다.

## <a name="configure-emergency-policies"></a>긴급 정책 구성

다음 정책을 사용하여 긴급 호출을 구성합니다. Microsoft Teams 관리 센터 또는 PowerShell을 사용하여 이러한 정책을 관리할 수 있습니다.

- **긴급 통화 라우팅** 정책 - 직접 라우팅에만 적용됩니다. 이 정책은 긴급 번호, 원하는 경우 숫자당 마스크 및 숫자당 PSTN 경로를 구성합니다.  이 정책을 사용자, 네트워크 사이트 또는 둘 다에 할당할 수 있습니다. (Calling Plans Teams 클라이언트는 해당 Microsoft 365 또는 Office 365 사용 위치에 따라 국가의 긴급 번호로 긴급 통화를 사용할 수 있습니다.)  자세한 내용은 직접 라우팅에 대한 긴급 통화 라우팅 정책 [관리를 참조합니다.](manage-emergency-call-routing-policies.md)

- **긴급 통화 정책** - 통화 계획 및 직접 라우팅에 적용됩니다. 이 정책은 긴급 통화를 할 때 보안 데스크 알림 환경을 구성합니다. 누구에게 알릴지와 알림을 어떻게 알릴지 설정할 수 있습니다. 예를 들어 조직의 보안 데스크에 자동으로 알리고 긴급 통화 시 수신을 듣도록 합니다.  이 정책은 사용자 또는 네트워크 사이트 또는 둘 다에 할당할 수 있습니다. 자세한 내용은 Teams 에서 긴급 [통화 정책 관리를 참조합니다.](manage-emergency-calling-policies.md)

## <a name="enable-users-and-sites"></a>사용자 및 사이트 사용

사용자 및 사이트에 긴급 통화 라우팅 정책 및 긴급 호출 정책을 할당할 수 있습니다. 긴급 통화 라우팅 정책은 Direct 라우팅에만 적용됩니다. (호출 계획 사용자에게 이 정책을 할당할 수 있습니다. 정책은 영향을주지 않습니다.)

Microsoft Teams 관리 센터 또는 PowerShell을 사용하여 정책을 할당합니다. 자세한 내용은 다음을 참조하세요.

- [직접 라우팅에 대한 긴급 통화 라우팅 정책 관리](manage-emergency-call-routing-policies.md)
- [Teams에서 긴급 통화 정책 관리](manage-emergency-calling-policies.md)

다음은 PowerShell 예제입니다.

보안 데스크 알림을 위해 특정 사용자를 사용하도록 설정하려면 다음 명령을 사용 합니다.

```PowerShell
Grant-CsTeamsEmergencyCallingPolicy -Identity user1 -PolicyName SecurityDeskNotification
```

사이트 1에 "Contoso 긴급 통화 정책 1"이라는 정책을 할당하기 위해 다음 명령을 사용하세요.

```PowerShell
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallingPolicy "Contoso Emergency Calling Policy 1"
```

긴급 통화에 대해 특정 Direct 라우팅 사용자를 사용하도록 설정하려면 다음 명령을 사용 합니다.

```PowerShell
Grant-CsTeamsEmergencyCallRoutingPolicy -Identity user1 -PolicyName UnitedStates
```

Site 1에 "Contoso 뉴욕 긴급 통화 라우팅"이라는 정책을 할당하기 위해 다음 명령을 사용하세요.

```PowerShell
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallRoutingPolicy "Contoso New York Emergency Call Routing"
```

네트워크 사이트 및 사용자에게 긴급 호출 정책을 할당하고 해당 사용자가 해당 네트워크 사이트에 있는 경우 네트워크 사이트에 할당된 정책이 사용자에게 할당된 정책을 재지정합니다.

## <a name="test-emergency-calling"></a>긴급 호출 테스트

미국의 ERSP(긴급 라우팅 서비스 공급자)는 긴급 호출 테스트 봇을 제공합니다.

- **미국의 계획** 사용자를 호출하면 미리 정의된 테스트 긴급 번호 933을 사용하여 긴급 호출 구성의 유효성을 검사할 수 있습니다. 이 번호는 봇으로 라우팅됩니다. 그러면 발신자 전화 번호(전화선 ID), 긴급 주소 또는 위치, 호출이 PSAP로 자동으로 라우팅되거나 먼저 화면이 선택될지 여부를 에코합니다.

- **미국의 직접** 라우팅 고객은 테스트 서비스를 위해 ERSP와 조정해야 합니다.

## <a name="government-support"></a>정부 지원

다음 표에서는 정부 클라우드에서 동적 긴급 호출에 대한 지원을 보여줍니다.

| 클라우드 | 가용성 |
| :------------|:-------|
| World Wide Multi 테넌트 | 완전 사용 가능 |
| GCC | Teams IP 휴대폰을 제외한 모든 클라이언트에서 사용할 수 있습니다. |
| GCCH | 보류 중 |
| DoD | 보류 중 |

 ## <a name="related-topics"></a>관련 항목

- [긴급 통화 관리](what-are-emergency-locations-addresses-and-call-routing.md)
- [긴급 전화 정책 관리](manage-emergency-calling-policies.md)
- [긴급 통화 라우팅 정책 관리 ](manage-emergency-call-routing-policies.md)
- [조직의 응급 위치 추가, 변경 또는 제거](add-change-remove-emergency-location-organization.md)
- [사용자에 대한 긴급 위치 할당 또는 변경](assign-change-emergency-location-user.md)
- [클라우드 음성 기능에 대한 네트워크 설정](cloud-voice-network-settings.md)
- [클라우드 음성 기능에 대한 네트워크 토폴로지 관리](manage-your-network-topology.md)
