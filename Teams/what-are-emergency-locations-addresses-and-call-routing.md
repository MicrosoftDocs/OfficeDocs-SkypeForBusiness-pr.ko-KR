---
title: 긴급 위치, 주소 및 통화 라우팅 이란 무엇 인가요?
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
- Teams_ITAdmin_Help
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords:
- ms.teamsadmincenter.locations.emergencyaddresses.overview
- ms.lync.lac.AddressAndLocation
ms.custom:
- Calling Plans
description: '긴급 한 주소, 위치, 긴급 통화 라우팅, 그리고 사용자에 게 계획 하 고 할당 하는 방법에 대해 알아봅니다. '
ms.openlocfilehash: 979fab1cd099d568278efd61d06a3f8a75b04541
ms.sourcegitcommit: d4e69d46de564c445feb855cbee55954a7063bba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/21/2019
ms.locfileid: "36483870"
---
# <a name="what-are-emergency-locations-addresses-and-call-routing"></a>긴급 위치, 주소 및 통화 라우팅 이란 무엇 인가요?

Office 365에서 통화 계획을 구성할 때는 전화 번호를 받을 때 각 전화 번호에 긴급 주소를 할당 하거나 비상 전화를 지원 하기 위해 사용자에 게 할당할 수 있습니다. 전화 번호에 긴급 주소를 할당 하려면 먼저 긴급 주소를 만들고 확인 해야 합니다. 유효성 검사를 통해 긴급 주소가 인식 되 고 긴급 응답 서비스에서 사용할 수 있는 올바른 형식으로 되어 있는지 확인 합니다. 필요에 따라 긴급 주소 내에 위치를 추가 하 여 사용자에 게 더 구체적인 위치를 제공할 수 있습니다. 예를 들어 비상 위치는 특정 긴급 주소에 연결 된 바닥, 날개 또는 사무실 일 수 있습니다. 긴급 주소의 유효성은 검사 되지만 위치는 그렇지 않습니다.
  
## <a name="what-are-emergency-addresses"></a>긴급 주소는 무엇 인가요?

긴급 주소는 활성 전화 번호에 필요 하지만, 필요한 경우에는 국가/지역에 따라 달라 집니다. 미국에서 사용자에 게 번호를 할당 하면 긴급 주소가 필요 합니다. 유럽, 중동, 아프리카 (EMEA) 등의 다른 국가의 경우에는 Office 365에서 전화 번호를 가져오거나 다른 서비스 공급자 또는 통신 업체에서 전송 하는 경우 긴급 주소가 필요 합니다.
  
비상 주소는 도심 주소, 주소 또는 실제 주소 라고 할 수 있습니다. 조직의 비즈니스 장소에 대 한 거리 또는 도심 주소입니다. 예를 들어 주소 *12345 북쪽 주 주소, Redmond, WA 98052* 을 사용 하 여 긴급 통화를 적절 한 디스패치 기관으로 라우팅하고 긴급 전화 발신자를 찾을 수 있습니다. 비즈니스에 둘 이상의 실제 비즈니스 위치가 있는 경우 긴급 주소가 두 개 이상 필요할 수 있습니다.
  
긴급 주소의 유효성을 검사 하는 작업은 긴급 응답 서비스에 적합 하 고 올바른 형식으로 지정 되어 있는지 확인 해야 합니다. 유효성이 검사 되지 않은 긴급 주소를 만들고 저장할 수 있지만, 검증 된 주소만 사용자에 게 연결 됩니다. 긴급 주소의 유효성을 검사 하 고 저장 한 후에는 사용자에 게 할당할 수 있습니다. 저장 된 유효성을 검사 한 긴급 주소를 변경 해야 하는 경우에는 새 항목을 만들어야 합니다.
  
## <a name="what-are-emergency-locations"></a>응급 위치는 무엇 인가요?

긴급 위치는 긴급 주소와 연결 되어 건물 내에서 더 정확한 위치를 제공 합니다. 비상 위치는 일반적으로 바닥, 건물 날개 또는 사용자가 위치한 사무실 번호입니다. 비상 주소와 연결 된 위치 수에는 제한이 없습니다. 
  
사용자에 게 긴급 주소를 할당 하면 해당 주소를 할당할 때 참조 되는 위치 ID가 실제로 표시 됩니다. 위치 ID에는 참조 된 긴급 주소 (거리 또는 도심 주소)가 포함 됩니다. 기본 긴급 위치는 작성 중 위치가 필요 하지 않은 경우 긴급 주소로 제공 됩니다. 
  
## <a name="what-is-emergency-call-routing"></a>긴급 통화 라우팅 이란?

긴급 한 긴급 전화를 발송 하는 경우 적절 한 디스패치 센터로 긴급 통화를 라우팅하는 프로세스 중에 비상 주소 및 위치를 사용 합니다. 팀 또는 비즈니스용 Skype 사용자가 긴급 전화 번호로 전화를 걸면 전화를 처리 하는 방법은 국가/지역에 따라 달라 집니다. 미국 및 영국 등 일부 국가에서는 통화를 적절 한 디스패치 센터에 연결 하기 전에 사용자의 현재 위치를 확인 하기 위해 먼저 통화를 차단 합니다. 다른 국가/지역에서 통화는 비상 발신자와 관련 된 전화 번호를 처리 하는 디스패치 센터로 바로 라우팅됩니다.
  
## <a name="create-add-and-assign-emergency-locations-and-addresses-to-your-users"></a>사용자에 게 긴급 위치 및 주소 만들기, 추가, 할당

1. **응급 위치 계획**. 첫 번째 단계는 비상 위치를 계획 하는 것입니다. 모든 실제 주소를 나열 해야 합니다. 그 다음에 따라 긴급 주소에 대 한 위치가 필요한 지 여부를 결정 하 고, 그렇지 않은 경우에는 다음을 수행 합니다. 예를 들어, 회사에 각각 4 개의 층이 있는 3 개의 사무실 건물이 있다면, 각각에 대 한 층 1-4이 각각 표시 되는 3 개의 긴급 주소가 있어야 할 수 있습니다.
    
2. **응급 위치를 만들고 확인**합니다. 다음 단계는 긴급 주소를 만들고 확인 하는 것입니다. 긴급 주소를 만들 때 유효성을 검사할 수 있습니다. 긴급 주소를 만들려면 [조직의 긴급 주소 추가 또는 제거](/SkypeForBusiness/what-are-calling-plans-in-office-365/add-or-remove-an-emergency-address-for-your-organization)를 참조 하세요.
    
    > [!IMPORTANT]
    > 주소 또는 도심 주소의 유효성을 검사 하는 경우 정확 하 게 서식이 지정 된 상태 인지 확인 해야 합니다. 구/군/시의 잘못 된 이름 등 부분적으로 올바른 긴급 주소를 입력 해도 여전히 유효성 검사가 성공 하 게 될 수 있습니다. 유효성 검사 프로세스는 해당 주소의 모든 부분을 사용 하 여 통화를 적절 한 긴급 파견 센터로 라우팅할 수 있는 충분 한 정보가 있는지 확인 합니다. 그렇다면 유효성이 검사 된 것으로 반환 되 고 전화 번호에 할당 될 수 있습니다. 
  
3. **전화 번호를 가져옵니다**. 다음 단계는 사용자의 전화 번호를 가져오는 것입니다. Office 365에서 새 전화 번호를 가져오거나 "포팅" 하거나 기존 전화 번호를 Office 365으로 전송 하 여이 작업을 수행할 수 있습니다. 전체 단계를 보려면 [전화 번호를 Office 365으로 전송](transfer-phone-numbers-to-office-365.md)을 참조 하세요.
    
4. **전화 번호를 할당**합니다. 마지막 단계는 사용자가 전화를 걸고 받을 수 있도록 하는 것입니다. 이렇게 하려면 각 사용자에 게 전화 번호를 할당 해야 합니다. [사용자의 전화 번호 지정, 변경 또는 제거](/microsoftteams/assign-change-or-remove-a-phone-number-for-a-user) 를 참조 하 여 전화 번호를 할당 합니다.

> [!NOTE]
> 이 보다 더 많은 전화 번호를 받으려면 [비즈니스 제품에 대 한 고객 지원에 문의-관리자 도움말](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b) 을 참조 하세요.

    
## <a name="related-topics"></a>관련 항목
[주소 유효성 검사 란?](/SkypeForBusiness/what-are-calling-plans-in-office-365/what-is-address-validation)

[통화 요금제에 사용 되는 다른 종류의 전화 번호](different-kinds-of-phone-numbers-used-for-calling-plans.md)

[비상 통화 약관](emergency-calling-terms-and-conditions.md)

[비즈니스용 Skype Online: 비상 전화 부인 레이블](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

