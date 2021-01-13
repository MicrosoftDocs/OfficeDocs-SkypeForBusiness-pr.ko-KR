---
title: 포트 순서
ms.author: v-cichur
author: cichur
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.voice.phonenumbers.porting.overview
- Calling Plans
description: 포트 주문의 개요와 서비스 공급자에서 Teams로 전화 번호를 전송하는 방법에 대해 간략하게 소개합니다.
ms.openlocfilehash: 4f1f8ca843db8c2b27eaa467b0014befe6f2b519
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802508"
---
# <a name="whats-a-port-order"></a>포트 순서

현재 전화 서비스 공급자 또는 통신 사업자가 있으며 사용자 또는 서비스에 대한 전화 번호가 이미 있는 경우 해당 전화 번호를 Microsoft Teams로 전송하려면 *"포트* 주문"을 만들어야 합니다. 번호가 포터링된 경우 해당 전화 번호를 사용자 및 서비스에 할당할 수 있습니다(전화 회의용 전화 회의용), 자동 전화 참석자, 통화 큐.
  
전화 번호를 Teams로 포식하면 Microsoft가 서비스 공급자가 되거나 이전 서비스 공급자 또는 통신사와의 서비스 연결을 끊을 수 있습니다.

번호 포터링에 익숙해지기 위해 이 문서의 정보를 검토하세요. 그런 다음 포트 주문을 만들고 전화 번호를 전송할 준비가 된 것입니다. 단계별 [지침은 Teams로](transfer-phone-numbers-to-teams.md) 전화 번호 이전을 참조하세요.
  
## <a name="what-countries-or-regions-support-number-porting"></a>번호 포터링을 지원하는 국가 또는 지역은 무엇입니까?

지원되는 모든 국가 또는 지역에서 전화 번호를 포트 또는 이전할 수 있지만, 포트 주문 요청을 제출하는 방법은 전화 번호가 들어오는 국가 또는 지역에 따라 다를 수 있습니다. 번호 포터링을 지원하는 국가 및 지역 목록은 조직의 전화 번호 [관리를 참조하세요.](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)  

현재 Microsoft [](transfer-phone-numbers-to-teams.md) Teams 관리 센터의 포터링 마법사는 영국, 미국 및 캐나다의 전화 번호 구하기를 지원하고 있습니다. 다른 국가 및 지역의 전화 번호를 얻습니다. 포트 주문을 수동으로 [제출하면 됩니다.](manually-submit-port-order.md)
  
## <a name="what-numbers-can-be-transferred"></a>어떤 숫자를 전송할 수 있나요?

 **전송할 수 있습니다.**
  
일반적으로 다음을 포함하여 지원되는 공급자로부터 전화 번호를 전송할 수 있습니다.
  
- 유선 전화 번호입니다.

- 휴대폰 및 태블릿에 사용되는 휴대폰 번호와 같은 모바일 장치 전화 번호입니다.

    > [!NOTE]
    > 휴대폰 번호 이전은 미국 및 푸에르토리코에서만 사용할 수 있습니다.
  
- 전화 번호

- 무료 전화 번호입니다.

    > [!NOTE]
    > UIFN(유니버설 국제 무료 전화 번호)은 이체할 수 없습니다. 
  
- 전화 회의 브리지, 자동 전화 회의 등에 사용되는 서비스 전화 번호

- 팩스 전화 번호이지만 팩스에 사용할 수 없습니다. 사용자에게 할당해야 합니다.

- Vonage 또는 RingCentral과 같은 전화 공급자의 VoIP 전화 번호입니다.

- 비즈니스용 Skype 하이브리드 전화 번호입니다. 이러한 번호를 전송하려는 경우 전자 메일을 보내 주시기 <ptn@microsoft.com> 바랍니다.

  **전송할 수 없습니다.**
  
    > [!NOTE]
    > 현재 VoIP 전화 공급자의 전화 번호를 포함하여 지원되는 국가 또는 지역에서 전송되지 않는 전화 번호 또는 번호를 이전할 수 없습니다. 지원되는 국가/지역 목록은 오디오 회의 및 통화 요금제에 대한 국가 및 지역 가용성을 [참조하세요.](../country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
  
- DSL 줄 또는 광대역 인터넷 연결과 같은 데이터 연결에 사용되는 전화 번호입니다.

- 팩스 전용 전화 번호입니다.

    팩스에 사용되는 기존 전용 전화 번호가 있는  경우 이러한 번호를 Teams로 이전할 수 있지만 팩스 서비스는 예상대로 작동하지 않습니다. 전화 시스템, 국내 통화 요금제 또는 국제 통화 요금제에 대한 라이선스가 있는 경우에도 Teams 고객은 팩스 서비스를 사용할 수 없습니다.

    전화 번호를 Teams로 포터링하는 경우 팩스에 전화 번호를 사용하는 대신 조직의 사용자에게 이 전화 번호를 할당할 수 있습니다.

    > [!NOTE]
    > 현재 영국에서는 지역 번호 0843, 0844, 0845, 0870, 0871, 0872에 대한 공유 비용 번호를 포함하여 영국 비지리적 번호 이전을 지원하지 않습니다.
  
## <a name="what-information-do-i-need-to-provide"></a>어떤 정보를 제공해야 하나요?

현재 통신 사업자에 대한 모든 계정 정보가 필요합니다. 포트 주문에 입력하는 정보는 대부분 현재 서비스 공급자의 가장 최근 청구서 또는 송장에 있습니다. 계정의 이름과 포터를 지정하려는 번호도 알아야 합니다.
  
## <a name="what-are-full-port-and-partial-port-transfers"></a>전체 포트 및 부분 포트 전송이란?

전화 번호를 Teams로 포터링할 때 모든 번호 또는 일부 번호를 이전할 수 있습니다.
  
- **전체 포트** 현재 서비스 공급자에서 Teams로 모든 번호를 이전하는 경우입니다. 이전할 전화 번호를 묻는 경우 계정에 있는  다른 모든 전화 번호와 함께 BTN(청구 전화 번호)을 포함해야 합니다.

    예를 들어 BTN이  *+1 425-555-1234이고*  25개 전화 *번호(+1 425-555-1235~1259)를* 모두 포터를 사용하려는 경우를 예로 들어 보겠습니다. 아래 지침에 따라 번호를 이전하면 **+14255551234 - +14255551259를** 입력합니다.

- **부분 포트** 현재 서비스 공급자에서 Teams로 전화 번호 중 일부만 이전하는 경우입니다. 동일한 BTN에 연결한 전화 번호 중 일부를 포팅하려는 경우 **** 계정에 있는 다른 모든 전화 번호와 함께 ** BTN을 포함하면 안 됩니다.

    예를 들어 BTN이  *+1 425-555-1234인*  경우 25개 전화 *번호(+1 425-555-1235~1259)의* 5개만 포터를 사용하려는 경우를 예로 들어 보겠습니다. 아래 지침에 따라 번호를 전송하면 **+1 425 555 1235 - +1 425 555 1239를** 입력합니다.
    
## <a name="can-i-submit-a-single-number-porting-request-for-all-of-my-numbers-at-one-time"></a>모든 번호에 대해 한 번의 번호 포식 요청을 한 번 제출할 수 있나요?
<a name="bkmk_type_1"> </a>

이식되는 각 운송업체 및 번호 유형에 대해 고유한 요청이 필요합니다.
  
예를 들어 다음 유형의 숫자 각각에 대해 고유한 번호 포터링 요청을 제출해야 합니다.
  
- 구독자 번호 또는 지리적 번호라고도 하는 로컬 전화 번호

- 지역 번호가 있는 무료 번호(예: 800, 844, 855, 866, 877 및 888)

- 휴대폰 번호

- Microsoft 365 또는 Office 365의 오디오 회의에 사용할 수 있는 서비스 번호입니다.

이러한 숫자 유형 각각에 대한 번호 포식 요청을 제출하는 방법에 대한 자세한 내용은 다음과 같습니다.
  
- **서로 다른 통신** 사업자에서 제공하는 전화 번호에는 각 통신 사업자 번호에 대한 고유한 포터링 요청이 있습니다.

-  지역 번호가 있는 무료 번호(예: 800, 844, 855, 866, 877 및 888)는 다른 유형의 숫자로 번호 포식 요청에 포함될 수 없습니다. 이러한 무료 번호로 이식하려면 포트 주문을 수동으로 [제출해야 합니다.](manually-submit-port-order.md) Microsoft Teams 관리 센터에서는 이러한 번호를 포터를 사용할 수 없습니다. 자세한 내용은 조직의 전화 [번호 관리를 참조하세요.](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)

    포트하려는 국가 및 전화 번호 유형에 대해 올바른 LOA(승인 서신)를 사용하는 것이 중요합니다. 여기에서 [필요한 LOA를 다운로드할 수 있습니다.](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)

- **휴대폰 번호에는** 전송 권한을 승인하기 위해 PIN 코드가 필요 합니다. 따라서 별도의 번호 포식 요청이 필요합니다.

- **서비스 번호** 포식 요청은 자체적으로 제출해야 합니다. 다른 유형의 숫자와 함께 제출할 수 없습니다.

## <a name="how-long-does-it-take-to-port-numbers"></a>포트 번호에 얼마나 오래 걸릴까요?
<a name="bkmk_type_1"> </a>

포트 주문 요청을 완료한 후 처리하는 데 7-14일이 걸립니다. 그러나 서비스 공급자에 따라 최대 30일이 걸릴 수 있습니다. 전화 번호가 포식된 후 전자 메일을 통해 연락을 받을 수 있습니다.
  
포트 주문 상태를 확인하려면 Microsoft Teams 관리 센터의 왼쪽 탐색 모음에서 **음성** 전화 번호로 이동한 다음 주문  >   **기록을 클릭합니다.** 각 포트 주문 상태가 상태 **열에 나열됩니다.**
  
## <a name="can-user-subscriber-phone-numbers-be-converted-to-service-numbers"></a>사용자(구독자) 전화 번호를 서비스 번호로 변환할 수 있나요?
<a name="bkmk_type_1"> </a>

예, 할 수 있습니다. 조직의 테넌트 GUID 및 변환할 전화 번호를 포함하는 서비스 요청을 제출하기만하면 됩니다. 이를 위해 조직의 전화 [번호 관리를 참조합니다.](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)

## <a name="can-i-port-out-my-numbers-from-teams-to-a-different-phone-service-provider-or-carrier"></a>내 번호를 Teams에서 다른 전화 서비스 공급자 또는 통신사로 포터 아웃할 수 있나요?

Teams에서 다른 통신사로 번호를 포스아웃하려면 새 통신 사업자에 요청을 제출해야 합니다. 또한 Microsoft Teams 관리 센터에서 포터링 PIN을 설정해야 합니다.

포터링 PIN을 정의하려면 Microsoft Teams 관리 센터의 왼쪽 탐색 모음에서 페이지의 오른쪽 위 모서리에 있는 음성 전화 번호로 이동하고 포링 PIN 관리를 선택한 다음  >  10자리 PIN을 입력합니다. 

새 통신 사업자에서 포터링 요청을 통해 연락하면 사용자가 정의한 PIN을 제공해야 합니다.

## <a name="common-mistakes-to-watch-out-for"></a>유의해야 하는 일반적인 실수
<a name="bkmk_type_1"> </a>

숫자 포터링은 쉽게 할 수 있습니다. 하지만 전화 서비스 공급자에 문제가 있는 경우 주문이 불완전하고 정보가 누락되거나 오타가 있는 경우 주문이 까다로워지지만
  
다음은 고객이 포트 번호에서 저지르는 가장 일반적인 실수입니다. 고객 지원에 대한 통화를 저장하고 이러한 오류를 다시 검사합니다.
  
- 제공한 계정 정보가 통신사에 기록된 정보와 정확히 일치하는지 확인 불일치 정보는 오류의 가장 일반적인 원인으로, 포트 순서가 지연됩니다. 다음이 true인지 확인

  - 계정을 변경할 권한이 있는 이름 또는 사용자가 올바른지 확인합니다.

  - 주소가 올바른지 확인합니다.

  - 계정 번호가 올바른지 확인합니다.

  - BTN이 올바른지 확인합니다.

- 이러한 전화 번호에서 사용할 수 있는 고급 통화 제어 기능(예: 통화 헌트, 링 링)이 없는지 확인합니다.

- 현재 서비스 공급자와의 연결 끊기 또는 새 서비스 주문이 없는지 확인하십시오.

- 모든 번호가 동일한 통신 사업자 및 동일한 계정에서 만들어야 합니다.

- 서비스가 활성 상태인지 확인 계정을 동결하면 계정에서 운송업체가 변경되지 않습니다. 계정을 변경할 권한이 있는 사람은 현재 통신 회사에 주문을 제출하여 동결을 제거해야 합니다. 이 프로세스는 통신 사업자에 따라 1~3주가 걸릴 수 있습니다.

## <a name="related-topics"></a>관련 항목

- [포트 주문의 상태 확인](port-order-status.md)
- [통화 요금제에 사용되는 다양한 종류의 전화 번호](../different-kinds-of-phone-numbers-used-for-calling-plans.md)
- [조직의 전화 번호 관리](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)
- [긴급 통화 사용 약관](../emergency-calling-terms-and-conditions.md)
- [긴급 통화 고지 레이블](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)