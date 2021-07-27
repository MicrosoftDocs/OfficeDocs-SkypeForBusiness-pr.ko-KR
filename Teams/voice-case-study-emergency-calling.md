---
title: 'Teams Contoso 사례 연구: 긴급 통화'
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
description: 'Teams 기업에 대한 음성 사례 연구 : 긴급 통화'
appliesto:
- Microsoft Teams
ms.openlocfilehash: 69231adb4588039012cceec1063571ddc201c2bb
ms.sourcegitcommit: b387296c043fcf10fba7b9ef416328383e54a565
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/26/2021
ms.locfileid: "53587477"
---
# <a name="contoso-case-study-emergency-calling"></a>Contoso 사례 연구: 긴급 통화

긴급 통화 주소, 장소, 긴급 위치 및 등록된 주소와 관련된 긴급 통화 및 용어의 가용성을 이해하기 위해 Contoso는 긴급 통화 관리 및 계획 및 동적 긴급 통화 구성을 &mdash; &mdash; [검토했습니다.](configure-dynamic-emergency-calling.md) [](what-are-emergency-locations-addresses-and-call-routing.md)

Office 365 계획 사용자가 긴급 통화에 대해 자동으로 사용하도록 설정됩니다. 그러나 미국 내 통화 계획 사용자만 긴급 통화 라우팅에 동적 위치를 사용할 수 있습니다. 

직접 라우팅의 경우 Contoso는 긴급 호출을 라우팅하고 파트너 연결을 위해 추가 구성이 필요하다는 것을 배웠습니다. 관리자는 ERSP(긴급 라우팅 서비스 공급자)에 대한 연결을 구성하거나 ELIN(긴급 위치 식별 번호) 애플리케이션에 대해 SBC(세션 경계 컨트롤러)를 구성해야 합니다.

Contoso에는 미국 및 미국 외부에 사무실이 있습니다.

- 미국의 Contoso Calling Plan 사용자는 동적 위치를 사용하여 긴급 통화를 라우팅할 수 있습니다. 

- 미국 외의 Contoso에는 통화 요금제를 사용하는 사이트와 직접 라우팅을 통해 전화 시스템 사이트가 있습니다.

## <a name="emergency-calling-use-cases"></a>긴급 통화 사용 사례

Contoso가 시스템에 연결하는 방법을 결정한 전화 Contoso는 다음 긴급 호출 사용 사례를 식별했습니다. 

- [미국의 요금제 사용자 호출](#calling-plan-user-in-the-united-states) 

- [미국 외부의 계획 사용자 호출](#calling-plan-user-outside-of-the-united-states)

- [직접 라우팅을 통해 전화 시스템 사용자](#user-who-connects-to-phone-system-through-direct-routing )


### <a name="calling-plan-user-in-the-united-states"></a>미국의 요금제 사용자 호출  

전화 번호를 긴급 위치와 연결해야 하는 경우의 요구 사항이 있습니다. 이러한 요구 사항을 이해하기 위해 Contoso는 통화 계획에 대한 고려 [사항을 검토했습니다.](what-are-emergency-locations-addresses-and-call-routing.md#considerations-for-calling-plans) 

이러한 요구 사항에 따라 Contoso는 미국의 사용자에게 번호가 할당될 때 위치를 전화 번호와 연결하기로 결정했습니다.

### <a name="calling-plan-user-outside-of-the-united-states"></a>미국 외부의 계획 사용자 호출 

전화 번호를 긴급 위치와 연결해야 하는 경우를 이해하기 위해 Contoso는 통화 계획에 대한 고려 사항을 [검토했습니다.](what-are-emergency-locations-addresses-and-call-routing.md#considerations-for-calling-plans) Contoso는 요구 사항에 따라 다음을 결정했습니다.  

-  Contoso는 캐나다의 사용자에게 번호가 할당될 때 위치를 전화 번호와 연결합니다. 

- Contoso는 전화 번호를 Office 365 다른 서비스 공급자 또는 통신사에서 번호가 전송될 때 긴급 위치를 할당합니다. 

### <a name="user-who-connects-to-phone-system-through-direct-routing"></a>직접 라우팅을 통해 전화 시스템 사용자 

이 사용 사례에 대한 긴급 라우팅을 계획하기 위해 Contoso는 직접 라우팅에 대한 고려 [사항을 검토했습니다.](what-are-emergency-locations-addresses-and-call-routing.md#considerations-for-direct-routing) 직접 라우팅 사용자는 통화 계획 사용자와 동일한 방식으로 긴급 전화를 받지 못하기 때문에 Contoso는 긴급 통화를 제공하는 방법을 결정해야 합니다. ERSP(긴급 라우팅 서비스 공급자)에 직접 라우팅을 연결할 수 있습니다. 직접 라우팅에는 ELIN(긴급 위치 식별 번호)이 포함된 SBC가 있습니다.   

#### <a name="emergency-routing-service-provider-ersp-considerations"></a>ERSP(긴급 라우팅 서비스 공급자) 고려 사항

ERSP(긴급 라우팅 서비스 공급자)는 호출자 위치에 따라 긴급 호출을 자동으로 라우팅할 수 있습니다.  

- 긴급 라우팅 서비스 공급자가 직접 라우팅 배포에 통합된 경우 동적으로 획득된 위치가 있는 긴급 호출은 해당 위치를 제공하는 PSAP(공용 안전 응답 지점)로 자동으로 라우팅됩니다. 

- 동적으로 획득된 위치가 없는 긴급 호출은 먼저 업데이트된 위치에 따라 적절한 디스패치 센터에 호출을 연결하기 전에 사용자의 현재 위치를 확인하도록 심사됩니다. 


#### <a name="elin-considerations"></a>ELIN 고려 사항

SBC ELIN 애플리케이션이 직접 라우팅 배포에 통합된 경우 긴급 주소를 전화 번호와 연결하려면 추가 구성 단계를 수행해야 합니다.  

Contoso는 ELIN(긴급 위치 식별 번호) 애플리케이션이 포함된 세션 테두리 컨트롤러를 사용하기로 결정했습니다.  

## <a name="security-desk-notification"></a>보안 데스크 알림

긴급 통화가 배치된 경우 보안 데스크에 알리는 기능을 Microsoft 통화 요금제 및 직접 라우팅에 전화 시스템 있습니다. Contoso는 보안 데스크 알림의 세부 정보를 검토하여 해당 사무실에서 구성해야 하는지 확인했습니다.  

Contoso는 보안 데스크 알림을 사용하기로 결정했다.

## <a name="configuration"></a>구성 

Contoso는 다음에 대한 동적 긴급 호출 [구성의 단계를](configure-dynamic-emergency-calling.md) 따릅니다. 

- 긴급 주소 할당 

- 네트워크 설정 구성 

- 위치 정보 서비스 구성 

- 긴급 정책 구성 

- 사용자 및 사이트 사용 

- 긴급 호출 테스트 

동적 긴급 호출을 구성한 후 Contoso는 해당 사용자에게 위치를 할당해야 합니다.  

- 조직의 응급 위치를 추가, 변경 또는 제거하려면 Contoso가 조직의 응급 위치 추가, 변경 또는 제거의 단계를 [따릅니다.](add-change-remove-emergency-location-organization.md)

- 건물, 바닥 및 사무실에 대한 장소를 만들기 위해 Contoso는 응급 위치에 대한 장소 추가, 변경 또는 제거의 단계를 [수행했습니다.](add-change-remove-emergency-place-organization.md) 

- Contoso는 긴급 위치를 할당하기 위해 사용자에 대한 긴급 위치를 할당하거나 변경하는 단계를 [따릅니다.](assign-change-emergency-location-user.md) 

 
