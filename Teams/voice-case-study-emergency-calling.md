---
title: Teams 음성 Contoso 사례 연구
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
description: 다국적 기업에 대한 Teams 음성 사례 연구
appliesto:
- Microsoft Teams
ms.openlocfilehash: e4503576df8d8e9f3d332cda45eb235d8162cf53
ms.sourcegitcommit: af15d99837a389b6b26952211e65cd68c4b7f46e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/18/2020
ms.locfileid: "44786102"
---
# <a name="contoso-case-study-emergency-calling"></a>Contoso 사례 연구: 긴급 통화

긴급 통화, 장소, 긴급 위치 및 등록된 주소와 관련된 긴급 통화 및 용어의 가용성을 이해하기 위해 &mdash; &mdash; Contoso는 [](what-are-emergency-locations-addresses-and-call-routing.md) [](configure-dynamic-emergency-calling.md)긴급 통화 관리 및 계획 및 동적 긴급 통화 구성을 검토했습니다.

Office 365에서는 통화 요금제 사용자가 긴급 통화를 자동으로 사용하도록 설정됩니다. 하지만 미국 내 통화 요금제 사용자만 긴급 통화를 라우팅하는 데 동적 위치를 사용할 수 있습니다. 

직접 라우팅의 경우 Contoso는 긴급 통화 라우팅 및 파트너 연결에 추가 구성이 필요하다는 것을 배웠습니다. 관리자는 ERSP(긴급 라우팅 서비스 공급자)에 대한 연결을 구성하거나 ELIN(긴급 위치 식별 번호) 애플리케이션에 대해 SBC(세션 테두리 컨트롤러)를 구성해야 합니다.

Contoso에는 미국 및 미국 외부에 사무실이 있습니다.

- 미국의 Contoso 통화 요금제 사용자는 동적 위치를 사용하여 긴급 통화를 라우팅할 수 있습니다. 

- Contoso에는 미국 이외에는 통화 요금제를 사용하는 사이트와 직접 라우팅을 통해 전화 시스템에 연결된 일부 사이트가 있습니다.

## <a name="emergency-calling-use-cases"></a>긴급 통화 사용 사례

Contoso가 전화 시스템에 연결하는 방법을 결정한 후 Contoso는 다음과 같은 긴급 통화 사용 사례를 확인했습니다. 

- [미국 내 통화 계획 사용자](#calling-plan-user-in-the-united-states) 

- [미국 이외 국가에 있는 요금제 사용자 호출](#calling-plan-user-outside-of-the-united-states)

- [직접 라우팅을 통해 전화 시스템에 연결하는 사용자](#user-who-connects-to-phone-system-through-direct-routing )


### <a name="calling-plan-user-in-the-united-states"></a>미국 내 통화 계획 사용자  

전화 번호를 긴급 위치와 연결해야 하는 경우의 요구 사항이 있습니다. Contoso는 이러한 요구 사항을 이해하기 위해 통화 계획에 [대한 고려 사항을 검토했습니다.](what-are-emergency-locations-addresses-and-call-routing.md#considerations-for-calling-plans) 

Contoso는 이러한 요구 사항에 따라 미국 내 사용자에게 번호가 할당될 때 위치를 전화 번호와 연결하기로 결정했습니다.

### <a name="calling-plan-user-outside-of-the-united-states"></a>미국 이외 국가에 있는 요금제 사용자 호출 

Contoso는 전화 번호를 긴급 위치와 연결해야 하는 경우를 이해하기 위해 통화 요금제에 대한 고려 [사항을 검토했습니다.](what-are-emergency-locations-addresses-and-call-routing.md#considerations-for-calling-plans) Contoso는 요구 사항에 따라 다음을 결정했습니다.  

-  Contoso는 캐나다의 사용자에게 번호가 할당될 때 해당 위치를 전화 번호와 연결합니다. 

- Contoso는 Office 365에서 전화 번호를 획득하거나 다른 서비스 공급자 또는 통신 사업자로부터 번호를 이전할 때 긴급 위치를 할당합니다. 

### <a name="user-who-connects-to-phone-system-through-direct-routing"></a>직접 라우팅을 통해 전화 시스템에 연결하는 사용자 

Contoso는 이 사용 사례에 대한 긴급 라우팅을 계획하기 위해 직접 라우팅에 대한 고려 [사항을 검토했습니다.](what-are-emergency-locations-addresses-and-call-routing.md#considerations-for-direct-routing) 직접 라우팅 사용자는 통화 요금제 사용자와 동일한 방식으로 긴급 통화를 받지 못하기 때문에 Contoso는 긴급 통화를 제공하는 방법을 결정해야 합니다. 직접 라우팅은 ERSP(긴급 라우팅 서비스 공급자)에 연결할 수 있습니다. 직접 라우팅에는 ELIN(긴급 위치 식별 번호)이 포함된 SBC가 있습니다.   

#### <a name="emergency-routing-service-provider-ersp-considerations"></a>ERSP(응급 라우팅 서비스 공급자) 고려 사항

ERSP(긴급 라우팅 서비스 공급자)는 발신자 위치에 따라 긴급 통화를 자동으로 라우팅할 수 있습니다.  

- 응급 라우팅 서비스 공급자가 직접 라우팅 배포에 통합된 경우 동적으로 획득한 위치가 있는 응급 전화는 해당 위치를 제공하는 PSAP(Public Safety Answering Point)로 자동으로 라우팅됩니다. 

- 동적으로 획득한 위치가 없는 긴급 통화는 업데이트된 위치에 따라 적절한 디스패치 센터에 통화를 연결하기 전에 사용자의 현재 위치를 결정하기 위해 먼저 화면이 표시됩니다. 


#### <a name="elin-considerations"></a>ELIN 고려 사항

SBC ELIN 애플리케이션이 직접 라우팅 배포에 통합된 경우 긴급 주소를 전화 번호와 연결하려면 추가 구성 단계를 수행해야 합니다.  

Contoso는 ELIN(긴급 위치 식별 번호) 애플리케이션이 포함된 세션 테두리 컨트롤러를 사용하기로 결정했습니다.  

## <a name="security-desk-notification"></a>보안 데스크 알림

Microsoft 통화 요금제와 전화 시스템 직접 라우팅 모두에서 응급 전화를 걸 때 보안 센터에 알리는 기능을 사용할 수 있습니다. Contoso는 보안 데스크 알림의 세부 정보를 검토하여 사무실에서 구성해야 하는지 여부를 확인했습니다.  

Contoso는 보안 데스크 알림을 사용하기로 결정합니다.

## <a name="configuration"></a>구성 

Contoso는 다음에 대한 동적 긴급 [통화](configure-dynamic-emergency-calling.md) 구성 단계를 따릅니다. 

- 긴급 주소 할당 

- 네트워크 설정 구성 

- 위치 정보 서비스 구성 

- 긴급 정책 구성 

- 사용자 및 사이트 사용 

- 긴급 통화 테스트 

동적 긴급 통화가 구성된 후 Contoso는 적절한 사용자에게 위치를 할당해야 합니다.  

- Contoso는 조직의 긴급 위치를 추가, 변경 또는 제거하기 위해 조직의 긴급 위치 추가, 변경 또는 제거의 단계를 [수행했습니다.](add-change-remove-emergency-location-organization.md)

- Contoso는 건물, 층 및 사무실을 위한 장소를 만들기 위해 긴급 위치에 대한 위치 추가, 변경 또는 제거 단계를 [수행했습니다.](add-change-remove-emergency-place-organization.md) 

- Contoso는 긴급 위치를 할당하기 위해 사용자의 긴급 위치 할당 또는 변경 단계를 [따릅니다.](assign-change-emergency-location-user.md) 

 