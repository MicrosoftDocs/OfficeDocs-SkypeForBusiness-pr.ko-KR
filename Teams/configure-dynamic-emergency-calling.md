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
ms.reviewer: roykuntz
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
description: Microsoft 통화 계획 및 전화 시스템을 구성 하는 방법에 대 한 자세한 내용은 동적 긴급 통화 호출 기능을 라우팅 하세요.
ms.custom: seo-marvel-mar2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 27ee8dd17b3948d373b5a6c13a210d298ee10d8c
ms.sourcegitcommit: a22a7b7e4bf556ee3e5e2e51c6f9f1c865a0724a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/08/2020
ms.locfileid: "45083158"
---
# <a name="plan-and-configure-dynamic-emergency-calling"></a>동적인 긴급 전화 계획 및 구성 

Microsoft 통화 요금제 및 전화 시스템 다이렉트 라우팅을 위한 동적 긴급 통화는 팀 클라이언트의 현재 위치에 따라 긴급 전화를 구성 하 고 라우팅하고 보안 사용자에 게 알릴 수 있는 기능을 제공 합니다.  

테 넌 트 관리자가 정의한 네트워크 토폴로지에 따라 팀 클라이언트는 LIS (위치 정보 서비스)에 대 한 요청에 네트워크 연결 정보를 제공 합니다. 일치 하는 항목이 있으면 LIS가 클라이언트에 대 한 위치를 반환 합니다. 이 위치 데이터는 다시 클라이언트로 전송 됩니다.  

팀 클라이언트는 비상 전화의 일부로 위치 데이터를 포함 합니다. 그런 다음 응급 서비스 공급자가이 데이터를 사용 하 여 적절 한 공공 안전 응답 시점 (PSAP)을 확인 하 고, PSAP 디스패처가 호출자의 위치를 가져올 수 있도록 해당 PSAP에 대 한 통화 경로를 지정 합니다.  

동적 비상 전화의 경우 다음이 발생 해야 합니다.

1. 네트워크 관리자는 네트워크 설정 및 LIS를 구성 하 여 네트워크/비상 위치 맵을 만듭니다.

   직접 라우팅의 경우 비상 전화 라우팅과 파트너 연결에 대 한 추가 구성이 필요 합니다. 관리자는 긴급 한 위치 Id 번호 (ELIN) 응용 프로그램에 대 한 SBC (세션 경계 컨트롤러)를 구성 **하거나** (미국) 긴급 라우팅 서비스 (영어)에 대 한 연결을 구성 해야 합니다.

2. 시작 하는 동안 주기적으로 또는 네트워크 연결이 변경 되 면 팀 클라이언트는 네트워크 연결 정보를 포함 하는 위치 요청을 네트워크 설정 및 LIS에 보냅니다.

   - 네트워크 설정 사이트가 일치 하는 경우-긴급 통화 정책이 해당 사이트에서 팀 클라이언트로 반환 됩니다. (정책에 대 한 자세한 내용은 [응급 정책 구성을](#configure-emergency-policies)참조 하세요.)

   - LIS가 일치 하는 경우-팀 클라이언트가 연결 된 네트워크 요소의 긴급 위치가 팀 클라이언트에 반환 됩니다.

3. 팀 클라이언트에서 비상 전화를 받으면 긴급 위치가 PSTN 네트워크로 전달 됩니다.

   직접 라우팅의 경우 관리자는 해당 공급자에 대 한 비상 전화를 보내거나 응용 프로그램에서 SBC ELIN 구성 하도록 SBC를 구성 해야 합니다.

이 문서에는 다음 섹션이 포함 되어 있습니다.

- [긴급 주소 구성](#assign-emergency-addresses)
- [네트워크 설정 구성](#configure-network-settings)
- [위치 정보 서비스 구성](#configure-location-information-service)
- [응급 정책 구성](#configure-emergency-policies)
- [사용자 및 사이트 사용](#enable-users-and-sites)
- [비상 통화 테스트](#test-emergency-calling)

적절 한 공개 안전 응답 시점 (PSAP)으로 자동 라우팅 하는 기능은 팀 사용자의 사용 국가에 따라 달라 집니다.

긴급 주소 및 긴급 통화 라우팅, 국가별 정보, 네트워크 설정 및 네트워크 토폴로지에 대 한 정보를 포함 하 여 긴급 통화에 대 한 자세한 내용은 다음을 참조 하세요.

- [긴급 통화 관리](what-are-emergency-locations-addresses-and-call-routing.md)
- [클라우드 음성 기능에 대 한 네트워크 설정 관리](cloud-voice-network-settings.md)
- [클라우드 음성 기능에 대한 네트워크 토폴로지 관리](manage-your-network-topology.md)

## <a name="supported-clients"></a>지원 되는 클라이언트

현재 지원 되는 클라이언트는 다음과 같습니다.  자주 확인 하 여이 목록에 대 한 업데이트를 확인 하세요.

- Microsoft Windows 용 팀 데스크톱 클라이언트
- Apple macOS 용 팀 데스크톱 클라이언트
- Apple iOS 클라이언트 버전 1.0.92.2019121004 및 App Store 버전 1.0.92 이상에 대 한 팀 모바일 클라이언트
- Android 클라이언트 및 Google Play 스토어 버전 1416/1.0.0.2019121201 이상에 대 한 팀 모바일 클라이언트
- 팀 전화 버전 1449/1.0.94.2019110802 이상
- 팀 대화방 버전 4.4.25.0 이상

## <a name="assign-emergency-addresses"></a>긴급 주소 할당

호출 계획 사용자와 위치를 동적으로 가져오는 데 필요한 네트워크 식별자에 모두 긴급 주소를 할당할 수 있습니다. (서브넷 및 WiFi AP가 지원 됨, 이더넷 스위치/포트에 대 한 지원이 보류 중입니다).

미국 내에서 긴급 통화를 자동으로 라우팅하는 것을 지원 하려면 네트워크 식별자에 할당 된 비상 위치에 연결 된 지역 코드가 포함 되어 있는지 확인 해야 합니다. (지역 코드가 없는 긴급 주소는 동적 위치에 필요한 네트워크 식별자에 할당할 수 없습니다.)

Azure 맵은 위치 기반 서비스에 사용 됩니다.  Microsoft 팀 관리 센터를 사용 하 여 긴급 주소를 입력 하면 팀에서 Azure 지도에서 주소를 확인 합니다.

- 일치 하는 항목이 발견 되 면 지역 코드도 자동으로 포함 됩니다.

- 일치 하는 항목이 없는 경우 긴급 주소를 수동으로 만들 수 있습니다. 핀 드롭 기능을 사용 하 여이 작업을 수행할 수 있습니다. 

즉, 호출 계획 사용자에 게 할당 하기 위해 만든 기존 긴급 위치가 동적 위치를 대상으로 할 경우 지역 코드를 포함 하도록 동일한 주소를 다시 만들어야 합니다. 두 위치를 구분 하려면 다른 설명을 포함 해야 합니다. 새 비상 위치는 이전 위치에 있는 사용자에 게 할당할 수 있습니다. 완전히 마이그레이션된 경우 이전 위치를 삭제할 수 있습니다.

Microsoft 팀 관리 센터에서 또는 PowerShell을 사용 하 여 긴급 주소를 추가 하 고 할당할 수 있습니다. 자세한 내용은 [조직의 긴급 위치 추가](add-change-remove-emergency-location-organization.md) 및 [사용자에 대 한 긴급 위치 지정](assign-change-emergency-location-user.md)을 참조 하세요.

## <a name="configure-network-settings"></a>네트워크 설정 구성

네트워크 설정은 팀 클라이언트의 위치를 결정 하는 데 사용 되며, 긴급 통화 정책 및 긴급 한 위치를 동적으로 얻을 수 있습니다. 조직에서 응급 통화 기능을 원하는 방식에 따라 네트워크 설정을 구성할 수 있습니다.

네트워크 설정에는 서브넷 컬렉션을 포함 하는 사이트가 포함 되며,이는 사용자에 대 한 동적 정책 할당에 독점적으로 사용 됩니다. 예를 들어, 비상 전화 정책 및 긴급 통화 라우팅 정책은 "Redmond 사이트"에 할당 되어 집 또는 다른 Microsoft 위치에서 로밍 하는 모든 사용자가 레드먼드에 대 한 긴급 전화 번호, 라우팅 및 보안 데스크를 사용 하 여 구성 됩니다.  

>[!Note]
>서브넷은 LIS에도 정의할 수 있으며 비상 위치에 연결 될 수 있습니다.  

다음 정의를 염두에 두어야 합니다. 자세한 내용은 [클라우드 음성 기능에 대 한 네트워크 설정을](cloud-voice-network-settings.md)참조 하세요.

- 신뢰할 수 있는 IP 주소에는 엔터프라이즈 네트워크의 인터넷 외부 IP 주소 컬렉션이 포함 되며, 사용자의 끝점이 회사 네트워크 내에 있는지 확인 하는 데 사용 됩니다. 사용자의 외부 IP 주소가 신뢰할 수 있는 IP 주소의 IP 주소와 일치 하는 경우에만 동적 정책 또는 위치를 가져오려고 시도 하는 것이 가능 합니다. IPv4 또는 IPv6 IP 주소에 대해 일치가 이루어질 수 있으며, 네트워크 설정으로 전송 되는 IP 패킷의 형식에 따라 달라 집니다.  공용 IP 주소에 IPv4와 IPv6이 모두 있는 경우에는 둘 다 신뢰할 수 있는 IP 주소로 추가 해야 합니다.

- 네트워크 지역에는 네트워크 사이트 컬렉션이 포함 됩니다. 

- 네트워크 사이트는 사무실, 건물 집합, 캠퍼스 등의 실제 가치를 가진 조직이 있는 위치를 나타냅니다. 이러한 사이트는 IP 서브넷의 모음으로 정의 됩니다.

- 네트워크 서브넷은 특정 네트워크 사이트와 연결 되어 있어야 합니다. 클라이언트의 위치는 네트워크 서브넷 및 연결 된 네트워크 사이트를 기준으로 결정 됩니다.  

Microsoft 팀 관리 센터에서 또는 PowerShell을 사용 하 여 네트워크 설정을 구성 합니다. 자세한 내용은 [클라우드 음성 기능에 대 한 네트워크 토폴로지 관리](manage-your-network-topology.md)를 참조 하세요.

네트워크 설정 (예: 새 주소, 네트워크 식별자 등)에 대 한 일부 변경 사항이 팀 클라이언트에 게 전파 되 고 사용 가능 하도록 하는 데는 몇 시간 정도 걸릴 수 있습니다.  

**통화 요금제 사용자:**

- 보안 데스크 알림의 동적 구성이 필요한 경우에는 신뢰할 수 있는 IP 주소와 네트워크 사이트를 모두 구성 해야 합니다.

- 동적 위치만 필요한 경우에는 신뢰할 수 있는 IP 주소만 구성 해야 합니다.

- 둘 다 필요 하지 않은 경우 네트워크 설정 구성이 필요 하지 않습니다. 

**직접 라우팅 사용자의 경우:**

- 보안 데스크 알림의 긴급 통화 또는 동적 구성을 동적으로 사용할 필요가 있는 경우에는 신뢰할 수 있는 IP 주소와 네트워크 사이트를 모두 구성 해야 합니다.

- 동적 위치만 필요한 경우에는 신뢰할 수 있는 IP 주소만 구성 해야 합니다.

- 둘 다 필요 하지 않은 경우 네트워크 설정 구성이 필요 하지 않습니다.


## <a name="configure-location-information-service"></a>위치 정보 서비스 구성

팀 클라이언트는 여러 네트워크 식별자와 연결 된 위치에서 긴급 주소를 가져옵니다. 서브넷과 WAPs (무선 액세스 지점)가 모두 지원 됩니다. (이더넷 스위치/포트에 대 한 지원이 보류 중입니다.)

클라이언트가 위치를 가져오려면 네트워크 식별자 (서브넷, WAPs, 스위치, 포트), 긴급 위치로 LIS를 채워야 합니다. Microsoft 팀 관리 센터에서 또는 PowerShell을 사용 하 여이 작업을 수행할 수 있습니다.

### <a name="using-the-microsoft-teams-admin-center"></a>Microsoft Teams 관리 센터 사용

1. 왼쪽 탐색 창에서 **지역**  >  **네트워크 & 위치로**이동 합니다.
2. 추가 하려는 네트워크 식별자를 나타내는 탭을 클릭 합니다. 예를 들어 **서브넷**, **wi-fi 액세스 지점**, **스위치**또는 **포트**를 클릭 합니다. 그런 다음 **추가**를 클릭 합니다.
3. 필드를 완성 하 고 긴급 위치를 추가한 다음 **적용**을 클릭 합니다.

### <a name="using-powershell"></a>PowerShell 사용

다음 cmdlet을 사용 하 여 포트, 스위치, 서브넷 및 WAPs를 LIS에 추가 합니다.

- [Get](https://docs.microsoft.com/powershell/module/skype/get-csonlinelissubnet?view=skype-ps), [Set](https://docs.microsoft.com/powershell/module/skype/set-csonlinelissubnet?view=skype-ps), [Remove](https://docs.microsoft.com/powershell/module/skype/remove-csonlinelissubnet?view=skype-ps) -CsOnlineLisSubnet
- [Get](https://docs.microsoft.com/powershell/module/skype/get-csonlinelisport?view=skype-ps), [Set](https://docs.microsoft.com/powershell/module/skype/set-csonlinelisport?view=skype-ps), [Remove](https://docs.microsoft.com/powershell/module/skype/remove-csonlinelisport?view=skype-ps) -CsOnlineLisPort
- [Get](https://docs.microsoft.com/powershell/module/skype/get-csonlineliswirelessaccesspoint?view=skype-ps), [Set](https://docs.microsoft.com/powershell/module/skype/set-csonlineliswirelessaccesspoint?view=skype-ps), [Remove](https://docs.microsoft.com/powershell/module/skype/remove-csonlineliswirelessaccesspoint?view=skype-ps) -CsOnlineLisWirelessAccessPoint
- [Get](https://docs.microsoft.com/powershell/module/skype/get-csonlinelisswitch?view=skype-ps), [Set](https://docs.microsoft.com/powershell/module/skype/set-csonlinelisswitch?view=skype-ps), [Remove](https://docs.microsoft.com/powershell/module/skype/remove-csonlinelisswitch?view=skype-ps) -CsOnlineLisSwitch

>[!Important]
>네트워크 사이트의 일부로 서브넷을 사용 하는 경우 동적 위치를 렌더링 하기 위해 위치 정보 서비스에서 다시 정의 해야 합니다.

## <a name="configure-emergency-policies"></a>응급 정책 구성

다음 정책을 사용 하 여 비상 전화를 구성 합니다. Microsoft 팀 관리 센터에서 또는 PowerShell을 사용 하 여 이러한 정책을 관리할 수 있습니다.

- **긴급 통화 라우팅 정책** – 직접 라우팅에만 적용 됩니다. 이 정책은 긴급 전화 번호, 필요한 경우에는 마스크, 숫자 당 PSTN 경로를 구성 합니다.  이 정책을 사용자, 네트워크 사이트 또는 둘 다에 할당할 수 있습니다. (통화 계획 팀 클라이언트는 Microsoft 365 또는 Office 365 사용 위치를 기반으로 국가의 비상 전화를 사용 하 여 응급 통화로 자동으로 활성화 됩니다.)  자세한 내용은 [직접 라우팅에 대 한 긴급 통화 라우팅 정책 관리](manage-emergency-call-routing-policies.md)를 참조 하세요.

- **비상 통화 정책** -통화 요금제 및 직접 라우팅에 적용 됩니다. 이 정책은 비상 통화가 이루어질 때 보안 데스크 알림 환경을 구성 합니다. 알림을 받을 사람과 알리는 방법을 설정할 수 있습니다. 예를 들어 조직의 보안 지원팀에 자동으로 알리고 긴급 통화를 수신 대기 하도록 할 수 있습니다.  이 정책은 사용자 또는 네트워크 사이트에 할당 하거나 둘 다에 할당할 수 있습니다. 자세히 알아보려면 [팀에서 긴급 통화 정책 관리](manage-emergency-calling-policies.md)를 참조 하세요.

## <a name="enable-users-and-sites"></a>사용자 및 사이트 사용

긴급 통화 라우팅 정책 및 비상 전화 정책을 사용자 및 사이트에 할당할 수 있습니다. 긴급 통화 라우팅 정책은 직접 라우팅에만 적용 된다는 점에 유의 하세요. (이 정책을 호출 계획 사용자에 게 할당 하는 것이 가능 하지만, 정책은 아무런 영향을 주지 않습니다.)

Microsoft 팀 관리 센터에서 또는 PowerShell을 사용 하 여 정책을 할당 합니다. 자세히 알아보려면 다음을 참조 하세요.

- [직접 라우팅에 대 한 긴급 통화 라우팅 정책 관리](manage-emergency-call-routing-policies.md)
- [팀에서 긴급 통화 정책 관리](manage-emergency-calling-policies.md)

다음은 PowerShell의 몇 가지 예입니다.

특정 사용자에 게 보안 데스크 알림을 사용 하도록 설정 하려면 다음 명령을 사용 합니다.

```PowerShell
Grant-CsTeamsEmergencyCallingPolicy -Identity user1 -PolicyName SecurityDeskNotification
```

"Contoso 비상 통화 정책 1" 이라는 정책을 사이트 1에 할당 하려면 다음 명령을 사용 합니다.

```PowerShell
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallingPolicy "Contoso Emergency Calling Policy 1"
```

특정 직접 라우팅 사용자에 게 긴급 통화를 사용 하도록 설정 하려면 다음 명령을 사용 합니다.

```PowerShell
Grant-CsTeamsEmergencyCallRoutingPolicy -Identity user1 -PolicyName UnitedStates
```

사이트 1에 "Contoso 뉴욕 긴급 통화 라우팅" 이라는 정책을 할당 하려면 다음 명령을 사용 합니다.

```PowerShell
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallRoutingPolicy "Contoso New York Emergency Call Routing"
```

긴급 통화 정책을 네트워크 사이트 및 사용자에 게 할당 하 고 해당 사용자가 해당 네트워크 사이트에 있는 경우 네트워크 사이트에 할당 된 정책이 사용자에 게 할당 된 정책 보다 우선 합니다.

## <a name="test-emergency-calling"></a>비상 통화 테스트

미국에서 일부 응급 라우팅 서비스 공급자 (ERSPs)는 비상 전화 테스트 봇을 제공 합니다.

- **통화 요금제 미국 내 사용자** 는 미리 정의 된 긴급 전화 번호 933를 사용 하 여 긴급 통화 구성의 유효성을 검사할 수 있습니다. 이 번호는 봇으로 라우팅되며 다음으로 발신자 전화 번호 (통화 라인 ID), 긴급 주소 또는 위치, 통화가 자동으로 PSAP 또는 차단 됨에 의해 전환 되는지 여부를 알립니다.

- **직접 라우팅 미국 내 고객은** 테스트 서비스를 위해 해당 ersp와 조화 되어야 합니다.

 ## <a name="related-topics"></a>관련 항목

- [긴급 통화 관리](what-are-emergency-locations-addresses-and-call-routing.md)
- [긴급 전화 정책 관리](manage-emergency-calling-policies.md)
- [긴급 통화 라우팅 정책 관리](manage-emergency-call-routing-policies.md)
- [조직의 응급 위치 추가, 변경 또는 제거](add-change-remove-emergency-location-organization.md)
- [사용자의 긴급 위치 지정 또는 변경](assign-change-emergency-location-user.md)
- [클라우드 음성 기능에 대한 네트워크 설정](cloud-voice-network-settings.md)
- [클라우드 음성 기능에 대한 네트워크 토폴로지 관리](manage-your-network-topology.md)
