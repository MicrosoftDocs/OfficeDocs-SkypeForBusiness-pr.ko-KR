---
title: 팀 음성 Contoso 사례 연구
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 06/17/2020
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
ms.reviewer: jowrig
search.appverid: MET150
f1.keywords:
- NOCSH
description: 여러 국가의 기업에 대 한 팀 음성 사례 연구
appliesto:
- Microsoft Teams
ms.openlocfilehash: e4503576df8d8e9f3d332cda45eb235d8162cf53
ms.sourcegitcommit: af15d99837a389b6b26952211e65cd68c4b7f46e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/18/2020
ms.locfileid: "44786102"
---
# <a name="contoso-case-study-emergency-calling"></a>Contoso 사례 연구: 비상 전화

비상 전화 긴급 주소, 장소, 긴급 위치, 등록 주소와 관련 된 비상 전화 및 용어에 대 한 가용성을 이해 하기 위해 &mdash; &mdash; Contoso는 긴급 통화 [관리](what-are-emergency-locations-addresses-and-call-routing.md) 를 검토 하 고 [동적 비상 전화를 계획 하 고 구성](configure-dynamic-emergency-calling.md)합니다.

Office 365에서 통화 요금제 사용자는 자동으로 비상 전화를 걸 수 있습니다. 하지만 미국 내 에서만 계획 사용자가 동적 위치를 사용 하 여 비상 전화를 라우팅할 수 있습니다. 

직접적인 라우팅의 경우 Contoso는 비상 전화 라우팅과 파트너 연결에 대 한 추가 구성이 필요 하다 고 배웠습니다. 관리자는 비상 연락망 (비상 라우팅 서비스 공급자)에 대 한 연결을 구성 하거나 (미국) 긴급 위치 Id 번호 (ELIN) 응용 프로그램에 대 한 SBC (세션 경계 컨트롤러)를 구성 해야 합니다.

Contoso는 미국 이외의 지역에 거주 하는 사무실을 보유 하 고 있습니다.

- 미국에서 Contoso 통화 계획 사용자는 동적 위치를 사용 하 여 비상 전화를 라우팅할 수 있습니다. 

- 미국 외의 Contoso에는 통화 계획을 사용 하는 일부 사이트와 직접 라우팅을 통해 전화 시스템에 연결 된 일부 사이트가 있습니다.

## <a name="emergency-calling-use-cases"></a>비상 전화 사용 사례

Contoso에서 전화 시스템에 연결 하는 방법을 결정 한 후에는 Contoso가 다음과 같은 긴급 통화 사용 사례를 확인 했습니다. 

- [미국에서 계획 사용자에 게 전화 걸기](#calling-plan-user-in-the-united-states) 

- [미국 이외의 지역에서 요금제 사용자에 게 전화 걸기](#calling-plan-user-outside-of-the-united-states)

- [직접 라우팅을 통해 전화 시스템에 연결 하는 사용자](#user-who-connects-to-phone-system-through-direct-routing )


### <a name="calling-plan-user-in-the-united-states"></a>미국에서 계획 사용자에 게 전화 걸기  

전화 번호를 비상 위치와 연결 해야 하는 경우에 대 한 요구 사항이 있습니다. 이러한 요구 사항을 이해 하기 위해 Contoso는 [통화 요금제 고려 사항을](what-are-emergency-locations-addresses-and-call-routing.md#considerations-for-calling-plans)검토 했습니다. 

이러한 요구 사항에 따라 미국 내 사용자에 게 숫자가 할당 될 때 Contoso는 해당 위치를 전화 번호와 연결 하기로 결정 했습니다.

### <a name="calling-plan-user-outside-of-the-united-states"></a>미국 이외의 지역에서 요금제 사용자에 게 전화 걸기 

전화 번호를 긴급 위치와 연결 해야 하는 경우를 이해 하려면 Contoso는 [호출 계획에 대 한 고려 사항을](what-are-emergency-locations-addresses-and-call-routing.md#considerations-for-calling-plans)검토 합니다. 요구 사항에 따라 Contoso는 다음을 결정 했습니다.  

-  Contoso는 숫자가 캐나다 사용자에 게 할당 된 경우 해당 위치를 전화 번호와 연결 합니다. 

- Contoso는 Office 365에서 전화 번호를 가져올 때 긴급 위치를 할당 하거나 다른 서비스 공급자 또는 통신 회사에서 번호를 전송 하는 경우 

### <a name="user-who-connects-to-phone-system-through-direct-routing"></a>직접 라우팅을 통해 전화 시스템에 연결 하는 사용자 

이 사용 사례에 대 한 긴급 라우팅에 대 한 계획을 수립 하기 위해 Contoso는 [직접 라우팅 고려 사항을](what-are-emergency-locations-addresses-and-call-routing.md#considerations-for-direct-routing)검토 했습니다. 직접 라우팅 사용자는 통화 계획 사용자와 같은 방식으로 비상 전화를 받을 수 없기 때문에 Contoso는 비상 전화를 제공 하는 방법을 결정 해야 했습니다. 직접 라우팅은 비상 라우팅 서비스 공급자 (ERSP)에 연결 될 수 있습니다. 직접적인 라우팅에는 비상 위치 식별 번호 (ELIN)를 포함 하는 SBC도 있을 수 있습니다.   

#### <a name="emergency-routing-service-provider-ersp-considerations"></a>ERSP (응급 라우팅 서비스 공급자) 고려 사항

ERSPs (응급 라우팅 서비스 공급자)는 발신자의 위치에 따라 긴급 통화를 자동으로 라우팅할 수 있습니다.  

- 긴급 라우팅 서비스 공급자가 직접 라우팅 배포에 통합 되어 있는 경우 동적으로 구입한 위치가 있는 비상 통화가 해당 위치를 처리 하는 PSAP (공개 안전 응답 시점)로 자동으로 라우팅됩니다. 

- 업데이트 된 위치에 따라 적절 한 디스패치 센터에 전화를 연결 하기 전에 동적으로 구입 위치 없이 긴급 통화를 먼저 차단 하 여 사용자의 현재 위치를 결정 합니다. 


#### <a name="elin-considerations"></a>ELIN 고려 사항

응용 프로그램의 SBC ELIN 라우팅 배포에 통합 되어 있는 경우 긴급 주소를 전화 번호와 연결 하려면 추가 구성 단계가 필요 합니다.  

Contoso는 비상 위치 Id 번호 (ELIN) 응용 프로그램을 포함 하는 세션 경계 컨트롤러를 사용 하기로 결정 했습니다.  

## <a name="security-desk-notification"></a>보안 데스크 알림

긴급 통화를 사용 하는 경우 Microsoft 통화 요금제와 전화 시스템 직접 라우팅 모두에서 보안 데스크에 게 알릴 수 있습니다. Contoso는 보안 데스크 알림에서 이러한 세부 정보를 검토 하 여 해당 사무실에서이를 구성 해야 하는지 확인 했습니다.  

Contoso는 보안 데스크 알림을 사용 하기로 결정 했습니다.

## <a name="configuration"></a>구성 

Contoso는 다음에 대 한 [동적 비상 전화 구성](configure-dynamic-emergency-calling.md) 의 단계를 수행 했습니다. 

- 긴급 주소 할당 

- 네트워크 설정 구성 

- 위치 정보 서비스 구성 

- 응급 정책 구성 

- 사용자 및 사이트 사용 

- 비상 통화 테스트 

동적 비상 통화가 구성 되 면 Contoso는 해당 사용자에 게 위치를 할당 해야 합니다.  

- 조직의 긴급 위치를 추가, 변경 또는 제거 하기 위해 Contoso는 [조직의 긴급 위치 추가, 변경 또는 제거](add-change-remove-emergency-location-organization.md) 의 단계를 팔 로우 합니다.

- 건물, 층, 사무실에 대 한 위치를 만들려면 Contoso는 [긴급 위치에 대 한 위치 추가, 변경 또는 제거](add-change-remove-emergency-place-organization.md) 의 단계를 수행 합니다. 

- 긴급 위치를 지정 하기 위해 Contoso는 [사용자에 대 한 긴급 위치 지정 또는 변경](assign-change-emergency-location-user.md)의 단계를 팔 로우 합니다. 

 