---
title: 긴급 위치, 장소 및 통화 라우팅 이란?
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.assetid: 589bf5f5-490a-4215-8588-99bab7d33e31
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords:
- ms.teamsadmincenter.locations.emergencyaddresses.overview
- ms.lync.lac.AddressAndLocation
ms.custom:
- Calling Plans
description: '응급 위치, 장소, 긴급 통화 라우팅, 그리고 사용자에 게 계획 하 고 할당 하는 방법에 대해 알아봅니다. '
ms.openlocfilehash: a6f3051c4902d9fda2f20ca17e4aa501a8922264
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2019
ms.locfileid: "37568556"
---
# <a name="what-are-emergency-locations-places-and-call-routing"></a>긴급 위치, 장소 및 통화 라우팅 이란?

통화 계획을 구성할 때는 전화 번호를 받을 때 각 전화 번호로 긴급 위치를 할당 하거나 비상 전화를 지원 하기 위해 사용자에 게 할당할 수 있습니다. 전화 번호에 비상 위치를 지정 하려면 먼저 긴급 위치를 추가 하 고 유효성을 검사 해야 합니다. 유효성 검사를 통해 긴급 위치가 인식 되 고 긴급 응답 서비스에서 사용할 수 있는 올바른 형식으로 되어 있는지 확인 합니다. 필요에 따라 긴급 위치 내에 위치를 추가 하 여 사용자에 게 더 구체적인 위치를 제공할 수 있습니다. 예를 들어 위치는 특정 비상 장소에 연결 된 바닥, 날개 또는 사무실 일 수 있습니다. 긴급 위치는 확인 되지 않지만 장소는 그렇지 않습니다.
  
## <a name="what-are-emergency-locations"></a>응급 위치는 무엇 인가요?

비상 위치는 활성 전화 번호에 필요 하며, 필요한 경우에는 국가/지역에 따라 달라 집니다. 미국에서 사용자에 게 번호를 할당 하면 긴급 위치가 필요 합니다. 유럽, 중동, 아프리카 (EMEA) 등의 다른 국가의 경우에는 Office 365에서 전화 번호를 가져오거나 다른 서비스 공급자 또는 통신 업체에서 전송 하는 경우 긴급 위치가 필요 합니다.
  
비상 위치는 도심 주소, 주소 또는 실제 주소 라고 할 수 있습니다. 조직의 비즈니스 장소에 대 한 거리 또는 도심 주소입니다. 예를 들어 주소 *12345 북쪽 주 주소, Redmond, WA 98052* 을 사용 하 여 긴급 통화를 적절 한 디스패치 기관으로 라우팅하고 긴급 전화 발신자를 찾을 수 있습니다. 비즈니스에 둘 이상의 실제 비즈니스 위치가 있는 경우 두 개 이상의 응급 위치가 필요할 수 있습니다.
  
비상 반응 서비스의 유효성을 검사 하는 것은 긴급 하 고 제대로 포맷 되었는지 확인 하는 것과 관련이 있습니다. 유효성이 검사 되지 않은 긴급 위치를 추가 하 고 저장할 수 있지만, 확인 된 위치만 사용자에 게 연결 됩니다. 응급 위치를 확인 하 고 저장 한 후에는 사용자에 게 할당할 수 있습니다. 저장 하 고 유효성을 검사 한 긴급 위치를 변경 하려면 새 항목을 만들어야 합니다.
  
## <a name="what-are-places"></a>위치는 무엇 인가요?

장소는 특정 건물 내에서 더 정확한 위치를 제공 하기 위해 비상 위치와 연결 되어 있습니다. 위치는 일반적으로 바닥, 건물 날개 또는 사용자가 위치한 사무실 번호입니다. 비상 위치에는 무제한으로 장소를 연결할 수 있습니다. 
  
사용자에 게 긴급 위치를 할당 하면 해당 위치를 할당할 때 참조 되는 위치 ID가 실제로 표시 됩니다. 위치 ID에는 참조 된 비상 장소 (거리 또는 도심 주소)가 포함 됩니다. 기본 위치에는 문서 내 위치가 필요 하지 않은 경우 긴급 위치에 포함 됩니다.
  
## <a name="what-is-emergency-call-routing"></a>긴급 통화 라우팅 이란?

비상 전화를 적절 한 디스패치 센터로 라우팅하는 프로세스 중에는 비상 연락망과 장소를 사용 하 여 긴급 첫 번째 응답자를 발송 합니다. 팀 사용자가 긴급 전화 번호로 전화를 걸면 전화를 처리 하는 방법은 국가 및 지역에 따라 달라 집니다 (PSAP). 미국 및 영국 등 일부 국가에서는 통화를 적절 한 디스패치 센터에 연결 하기 전에 사용자의 현재 위치를 확인 하기 위해 먼저 통화를 차단 합니다. 다른 국가와 지역에서 통화는 긴급 발신자와 관련 된 전화 번호를 처리 하는 디스패치 센터로 직접 라우팅됩니다.
  
## <a name="create-add-and-assign-emergency-locations-and-places-to-your-users"></a>사용자에 게 긴급 위치 및 장소 만들기, 추가, 할당

1. **응급 위치 계획**. 첫 번째 단계는 비상 위치를 계획 하는 것입니다. 모든 실제 주소를 나열 합니다. 그 다음에 따라 긴급 위치에 대 한 장소가 필요한 지 여부를 결정 합니다. 예를 들어 회사에 각각 4 개의 층이 있는 세 개의 office 건물이 있는 경우 세 가지 긴급 위치, 즉 각각에 대 한 층이 4 개에 나열 되어야 합니다.
    
2. **비상 위치를 추가**합니다. 다음 단계는 비상 위치를 추가 하는 것입니다. 자세한 내용은 [조직의 긴급 위치 추가, 변경 또는 제거](add-change-remove-emergency-location-organization.md)를 참조 하세요.
    
    > [!IMPORTANT]
    > 주소 또는 도심 주소의 유효성을 검사 하는 경우 정확 하 게 서식이 지정 되었는지 확인 해야 합니다. 구/군/시의 잘못 된 이름 등 부분적으로 올바른 긴급 주소를 입력 해도 여전히 유효성 검사를 통과할 수 있습니다. 유효성 검사 프로세스는 지정 된 주소의 모든 부분을 사용 하 여 통화를 적절 한 긴급 파견 센터로 라우팅할 수 있는 충분 한 정보가 있는지 확인 합니다. 그렇다면 유효성이 검사 된 것으로 반환 되 고 전화 번호에 할당 될 수 있습니다.
  
3. **전화 번호를 가져옵니다**. 다음 단계는 사용자의 전화 번호를 가져오는 것입니다. Office 365에서 새 전화 번호를 가져오거나 "포팅" 하거나 기존 전화 번호를 Office 365으로 전송 하 여이 작업을 수행할 수 있습니다. 전체 단계를 보려면 [전화 번호를 Office 365으로 전송](transfer-phone-numbers-to-office-365.md)을 참조 하세요.
    
4. **전화 번호를 할당**합니다. 마지막 단계는 사용자가 전화를 걸고 받을 수 있도록 하는 것입니다. 이렇게 하려면 각 사용자에 게 전화 번호를 할당 해야 합니다. [사용자의 전화 번호 지정, 변경 또는 제거](/microsoftteams/assign-change-or-remove-a-phone-number-for-a-user) 를 참조 하 여 전화 번호를 할당 합니다.

> [!NOTE]
> 이 보다 더 많은 전화 번호를 받으려면 [PSTN 서비스 데스크에 문의 하세요](manage-phone-numbers-for-your-organization/contact-pstn-service-desk.md).

    
## <a name="related-topics"></a>관련 항목

[통화 요금제에 사용 되는 다른 종류의 전화 번호](different-kinds-of-phone-numbers-used-for-calling-plans.md)

[비상 통화 약관](emergency-calling-terms-and-conditions.md)