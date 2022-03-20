---
title: 원격 위치에 대한 긴급 주소
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: roykuntz
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- NOCSH
description: Microsoft가 긴급 통화를 지원하기 위해 디스패치 가능한 위치 정보를 지원하는 방법에 대해 자세히 알아보습니다.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: d80854fc36e6914ba48e8993d298c75b136bd06f
ms.sourcegitcommit: 4af3638637456f21bc97f510ed9d2f7ff2da07e2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2022
ms.locfileid: "63660713"
---
# <a name="emergency-addresses-for-remote-locations"></a>원격 위치에 대한 긴급 주소

이 문서에서는 미국의 911 긴급 통화 위치 정보에 대한 Microsoft의 지원을 설명합니다. 이 지원은 긴급 통화를 하는 사용자에 대해 가능한 가장 정확한 디스패치 가능한 위치 정보를 Teams 보장합니다. 발신자의 위치--onsite 또는 가정에서 작업하는 경우와 관계없이 PSAP(공공 안전 응답 지점)에 전송된 발신자 위치 정보는 정확해야 합니다.

이 문서에는 MLTS(다중 전화 시스템)에 대한 RAY BAUM의 법을 준수하는 Microsoft의 준수에 대한 정보가 포함되어 있습니다. RAY BAUM의 법은 2021년 초에 적용된 Kari의 법률 요구 사항을 확장합니다. RAY BAUM의 법칙 및 Kari의 법칙에 대한 자세한 내용은 [911](https://www.fcc.gov/911-dispatchable-location) 통화 및 다중 전화 시스템의 디스패치 가능한 위치 [– Kari의 법률 및 RAY BAUM의 Act 911](https://www.fcc.gov/mlts-911-requirements) 직접 전화 걸기, 알림 및 디스패치 가능한 위치 요구 사항을 참조하세요. 

이제 집에서 작업하는 사용자는 해당되는 경우 자신의 긴급 주소를 설정할 수 있습니다. 이 문서에서는 최종 사용자가 긴급 주소를 설정할 수 있도록 사용자 정책을 구성하는 방법을 설명합니다.

이 정보는 미국의 긴급 911 호출에 적용하나, 사용자가 입력한 위치도 캐나다의 심사 센터로 전달됩니다.

이 문서에는 다음 섹션이 포함되어 있습니다.

- [긴급 통화 위치 정보 지원](#support-for-emergency-calling-location-information)
- [위치 우선 순위](#location-precedence)
- [긴급 주소 분류 및 라우팅](#emergency-address-classification-and-routing)
- [최종 사용자가 긴급 주소를 구성하도록 설정](#enable-end-users-to-configure-their-emergency-address)
- [참고 사항 및 제한 사항](#notes-and-restrictions)


## <a name="support-for-emergency-calling-location-information"></a>긴급 통화 위치 정보 지원

이러한 요구 사항을 지원하기 위해 Teams 운영 체제에서 제공하는 위치 서비스를 사용하여 주소 제안--관리자 또는 사용자의 권한이 부여된 경우를 제안합니다. 최종 사용자는 제안된 주소의 위치를 확인하거나, 편집하거나, 새 주소를 수동으로 입력할 수 있습니다. 그런 다음 클라이언트가 해당 네트워크에 연결될 때 사용자가 확인한 주소가 자동으로 Teams 클라이언트에 저장됩니다. 사용자 저장 주소는 클라이언트가 Teams 자동으로 지워집니다.


## <a name="location-precedence"></a>위치 우선 순위

응급 주소는 Teams 유형별로 분류할 수 있습니다. 다음 목록은 긴급 번호에 전화를 걸 때 사용되는 위치 우선 순위를 보여줍니다.

1. 테넌트에서 정의된 동적으로 획득된 주소는 위치 정보 서비스에서 관리합니다.

2. 최종 사용자가 확인, 편집 또는 수동으로 입력한 주소입니다. 이 주소는 클라이언트가 Teams 로컬 네트워크에 연결됩니다.

3. 운영 체제에서 자동으로 제안하는 주소입니다.

4. 관리자가 사용자에게 정적으로 할당하는 주소입니다.


## <a name="emergency-address-classification-and-routing"></a>긴급 주소 분류 및 라우팅

다음 표에서는 각 유형에 대한 긴급 주소 및 관련 라우팅 방법의 종류를 보여 주며, 호출이 제공 PSAP로 자동으로 라우팅되거나 정확도를 위해 심사된 후 제공 PSAP로 전송됩니다. 이 라우팅 동작은 모든 호출 계획 사용자, 운영자 커넥트 인증된 긴급 호출 서비스 공급자에 대해 미국에서 지원됩니다.


| 긴급 주소 유형 | 긴급 라우팅 방법 |
| :------------| :-------|
| 관리자가 정의한 동적으로 획득된 긴급 주소입니다. | PSAP로 직접 연결합니다. |
| 사용자가 정확도를 확인하지 않고 운영 체제에서 얻은 **긴급 주소입니다** . | 스크린 및 PSAP로 전송됩니다. |
| 사용자가 정확도를 확인하여 운영 체제에서 얻은 **긴급 주소입니다** .| PSAP로 직접 연결합니다. |
| 운영 체제에서 얻은 긴급 주소로 사용자가 편집하고 확인했습니다. | 스크린 및 PSAP로 전송됩니다. |
| 사용자가 입력하고 확인한 긴급 주소입니다. | 스크린 및 PSAP로 전송됩니다. |
| 사용자/번호에 정적으로 할당된 긴급 주소입니다. | 스크린 및 PSAP로 전송됩니다. |
| Null | 스크린 및 PSAP로 전송됩니다. |


## <a name="enable-end-users-to-configure-their-emergency-address"></a>최종 사용자가 긴급 주소를 구성하도록 설정

최종 사용자에 대해 이 기능을 사용하도록 설정하려면 powerShell cmdlet을 New-CsTeamsEmergencyCallingPolicy 외부LocationLookupMode 매개 변수를 사용하도록 설정합니다. 다음 예제를 참조합니다. 


``` PowerShell
New-CsTeamsEmergencyCallingPolicy -Identity E911WFH -ExternalLocationLookupMode Enabled
```

```PowerShell
Grant-CsTeamsEmergencyCallingPolicy -PolicyName E911WFH -Identity user@contoso.com
```

최종 사용자에게 이 기능을 사용하도록 설정한 후 통화 탭에서 사용자가 긴급 주소를 추가, 편집 또는 확인하여 설정한 후에 주소를 표시할 수 있습니다. 최종 사용자가 위치 서비스를 설정할 수 있는 방법에 대한 자세한 내용은 [Home Emergency 911에서 작업: 위치 서비스 사용 을 참조하세요](https://support.microsoft.com/office/work-from-home-emergency-911-enable-location-services-583dd649-87fc-4b23-aed6-f4e2279297f9?storagetype=live).

이 Windows 경우 그룹 Windows 또는 [MDM](/windows/client-management/mdm/policy-csp-privacy#privacy-letappsaccesslocation)(모바일 디바이스 관리)을 사용하여 애플리케이션이 위치에 액세스할 수 있는지 여부 및 위치 서비스를 관리할 수 있습니다.

위치 서비스에 대한 Windows 자세한 내용은 위치 Windows 개인 정보 보호를 [참조하세요](https://support.microsoft.com/windows/windows-location-service-and-privacy-3a8eee0a-5b0b-dc07-eede-2a5ca1c49088).



## <a name="notes-and-restrictions"></a>참고 사항 및 제한 사항

다음을 염두에 두어야 합니다.

- 설명된 업무 환경은 데스크톱 및 mac의 Teams 데스크톱에 Windows 있습니다.

- Teams 휴대폰은 집에서 작업 환경을 지원하지 않습니다.

- Teams 모바일은 자동 위치 검색을 지원하지만 설명된 사용자가 입력한 환경은 지원하지 않습니다.

- 개인 정보 설정은 자동 위치 감지와 충돌할 수 있습니다. 모바일 디바이스 관리 시스템을 사용할 수 있습니다.


## <a name="related-topics"></a>관련 항목

- [긴급 통화 관리](what-are-emergency-locations-addresses-and-call-routing.md)

- [Home Emergency 911에서 작업: 위치 서비스 사용](https://support.microsoft.com/office/work-from-home-emergency-911-enable-location-services-583dd649-87fc-4b23-aed6-f4e2279297f9?storagetype=live)

