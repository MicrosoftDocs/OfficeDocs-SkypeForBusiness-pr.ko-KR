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
- m365initiative-voice
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- NOCSH
description: Microsoft가 긴급 통화를 지원하기 위해 디스패치 가능한 위치 정보를 지원하는 방법을 알아봅니다.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 9efa5f6e9ad5b5f2434efb95265f58c9a603fdd5
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/07/2022
ms.locfileid: "67272073"
---
# <a name="emergency-addresses-for-remote-locations"></a>원격 위치에 대한 긴급 주소

이 문서에서는 미국 911 긴급 통화 위치 정보에 대한 Microsoft의 지원에 대해 설명합니다. 이 지원을 통해 Teams 사용자가 긴급 전화를 걸 수 있도록 가능한 가장 정확한 디스패치 가능한 위치 정보가 제공됩니다. 발신자의 위치(현장 또는 집에서 작업)에 관계없이 PSAP(공공 안전 응답 지점)로 전송된 발신자의 위치 정보는 정확해야 합니다.

이 문서에는 MLTS(다중 회선 전화 시스템)에 대한 RAY BAUM의 법 준수에 대한 Microsoft의 정보가 포함되어 있습니다. RAY BAUM의 법은 2021 년 초에 발효 된 카리의 법률 요구 사항을 확장합니다. RAY BAUM의 법과 Kari의 법에 대한 자세한 내용은 911 통화 및 다중 회선 전화 시스템에 [대한 디스패치 가능한 위치](https://www.fcc.gov/911-dispatchable-location) [- Kari의 법률 및 RAY BAUM의 법 911 직접 전화 걸기, 알림 및 디스패치 가능한 위치 요구 사항을 참조하세요](https://www.fcc.gov/mlts-911-requirements). 

집에서 일하는 사용자는 이제 해당하는 경우 자신의 긴급 주소를 설정할 수 있습니다. 이 문서에서는 최종 사용자가 긴급 주소를 설정할 수 있도록 사용자 정책을 구성하는 방법을 설명합니다.

이 정보는 미국 긴급 911 통화에 적용되지만, 사용자가 입력한 위치는 캐나다의 심사 센터로도 전달됩니다.

이 문서에는 다음 섹션이 포함되어 있습니다.

- [긴급 통화 위치 정보 지원](#support-for-emergency-calling-location-information)
- [위치 우선 순위](#location-precedence)
- [긴급 주소 분류 및 라우팅](#emergency-address-classification-and-routing)
- [최종 사용자가 긴급 주소를 구성할 수 있도록 설정](#enable-end-users-to-configure-their-emergency-address)
- [참고 사항 및 제한 사항](#notes-and-restrictions)


## <a name="support-for-emergency-calling-location-information"></a>긴급 통화 위치 정보 지원

이러한 요구 사항을 지원하기 위해 Teams는 각 운영 체제에서 제공하는 위치 서비스를 사용하여 관리자 또는 사용자가 권한을 부여한 경우 주소를 제안합니다. 최종 사용자는 제안된 주소의 위치를 확인하거나 편집하거나 수동으로 새 주소를 입력할 수 있습니다. 그러면 클라이언트가 네트워크에 연결될 때 사용자가 확인한 주소가 자동으로 사용되도록 확인, 편집 또는 수동으로 입력한 주소가 Teams 클라이언트에 저장됩니다. Teams 클라이언트가 로그아웃되면 사용자 저장 주소가 자동으로 지워집니다.


## <a name="location-precedence"></a>위치 우선 순위

Teams의 긴급 주소는 다양한 유형으로 분류할 수 있습니다. 다음 목록에서는 긴급 번호로 전화를 걸 때 사용되는 위치 우선 순위를 보여줍니다.

1. 위치 정보 서비스에서 테넌트가 관리하는 동적으로 획득한 주소입니다.

2. 최종 사용자가 확인, 편집 또는 수동으로 입력한 주소로, Teams 클라이언트가 연결된 로컬 네트워크에 연결됩니다.

3. 운영 체제에서 자동으로 제안하는 주소입니다.

4. 관리자가 정적으로 사용자에게 할당하는 주소입니다.


## <a name="emergency-address-classification-and-routing"></a>긴급 주소 분류 및 라우팅

다음 표에서는 각 유형에 대한 긴급 주소 및 관련 라우팅 방법의 유형을 보여 줍니다. 호출이 서비스 PSAP로 자동으로 라우팅되는지 또는 서비스 PSAP로 전송하기 전에 정확도를 위해 선별되는지 여부를 보여 줍니다. 이 라우팅 동작은 모든 통화 플랜 사용자, 운영자 연결 파트너 및 직접 라우팅 인증 응급 통화 서비스 공급자에 대한 미국 지원됩니다.


| 긴급 주소 유형 | 긴급 라우팅 방법 |
| :------------| :-------|
| 관리자가 정의한 동적으로 획득한 긴급 주소입니다. | PSAP로 직접 연결합니다. |
| 사용자가 **정확도를 확인하지 않고** 운영 체제에서 가져온 긴급 주소입니다. | 스크린되고 PSAP로 전송됩니다. |
| 사용자가 **정확도를 확인** 하여 운영 체제에서 가져온 긴급 주소입니다.| PSAP로 직접 연결합니다. |
| 운영 체제에서 입수하여 사용자가 편집하고 확인한 긴급 주소입니다. | 스크린되고 PSAP로 전송됩니다. |
| 사용자가 입력하고 확인한 긴급 주소입니다. | 스크린되고 PSAP로 전송됩니다. |
| 사용자/번호에 정적으로 할당된 긴급 주소입니다. | 스크린되고 PSAP로 전송됩니다. |
| Null | 스크린되고 PSAP로 전송됩니다. |


## <a name="enable-end-users-to-configure-their-emergency-address"></a>최종 사용자가 긴급 주소를 구성할 수 있도록 설정

### <a name="using-the-microsoft-teams-admin-center"></a>Microsoft Teams 관리 센터 사용

1. Microsoft Teams 관리 센터의 왼쪽 탐색 영역에서 **음성** > **긴급 정책** 으로 이동합니다.
2. **추가** 를 선택합니다.
3. 긴급 통화 정책의 이름(예: "E911WFH")을 입력합니다.
4. **외부 위치 조회 모드를** 켭니다.
5. **적용** 을 선택합니다.

#### <a name="assign-a-custom-emergency-calling-policy-to-users"></a>사용자에게 사용자 지정 긴급 통화 정책 할당

[!INCLUDE [assign-policy](includes/assign-policy.md)]

### <a name="using-powershell"></a>PowerShell 사용

최종 사용자에 대해 이 기능을 사용하도록 설정하려면 New-CsTeamsEmergencyCallingPolicy PowerShell cmdlet을 사용하고 ExternalLocationLookupMode 매개 변수를 Enabled로 설정합니다. 다음 예제를 참조하세요. 


``` PowerShell
New-CsTeamsEmergencyCallingPolicy -Identity E911WFH -ExternalLocationLookupMode Enabled
```

```PowerShell
Grant-CsTeamsEmergencyCallingPolicy -PolicyName E911WFH -Identity user@contoso.com
```

최종 사용자에 대해 이 기능을 사용하도록 설정한 후 통화 탭에서 사용자는 긴급 주소를 추가, 편집 또는 확인하고 설정된 후에 주소를 표시할 수 있습니다. For more information on how end users can set location services, see [Work from Home Emergency 911: enable location services](https://support.microsoft.com/office/work-from-home-emergency-911-enable-location-services-583dd649-87fc-4b23-aed6-f4e2279297f9?storagetype=live).

Windows에서는 그룹 정책을 사용하거나 [MDM(모바일 디바이스 관리)](/windows/client-management/mdm/policy-csp-privacy#privacy-letappsaccesslocation)을 사용하여 Windows 위치 서비스 및 애플리케이션이 위치에 액세스할 수 있는지 여부를 관리할 수 있습니다.

Windows 위치 서비스에 대한 자세한 내용은 [Windows 위치 서비스 및 개인 정보를 참조하세요](https://support.microsoft.com/windows/windows-location-service-and-privacy-3a8eee0a-5b0b-dc07-eede-2a5ca1c49088).



## <a name="notes-and-restrictions"></a>참고 사항 및 제한 사항

다음 사항에 유의하세요.

- 설명된 가정용 업무 환경은 Windows 및 Mac의 Teams 데스크톱용입니다.

- Teams 전화는 집에서 일하는 환경을 지원하지 않습니다.

- Teams 모바일은 자동 위치 검색을 지원하지만 사용자가 입력한 환경은 설명되지 않습니다.

- 개인 정보 설정이 자동 위치 검색과 충돌할 수 있습니다. 모바일 장치 관리 시스템을 사용할 수 있습니다.


## <a name="related-topics"></a>관련 항목

- [긴급 통화 관리](what-are-emergency-locations-addresses-and-call-routing.md)

- [가정 비상 사태 911에서 작업: 위치 서비스 사용](https://support.microsoft.com/office/work-from-home-emergency-911-enable-location-services-583dd649-87fc-4b23-aed6-f4e2279297f9?storagetype=live)

