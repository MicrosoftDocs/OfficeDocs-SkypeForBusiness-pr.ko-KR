---
title: 포트 순서
ms.author: v-lanac
author: lanachin
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
description: 포트 주문에 대 한 개요와 서비스 공급자 로부터 팀으로 전화 번호를 전송 하는 방법에 대해 알아봅니다.
ms.openlocfilehash: 0102adfd53dba3ff455ddbdbc3678e625fd978de
ms.sourcegitcommit: 2d44f1a673316daf0aca3149571b24a63ca72772
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/11/2020
ms.locfileid: "43227542"
---
# <a name="whats-a-port-order"></a>포트 순서

현재 전화 서비스 공급자 또는 통신 회사를 보유 하 고 있고 사용자 또는 서비스에 대 한 전화 번호가 이미 있는 경우 "*포트 순서*"를 만들어 해당 전화 번호를 Microsoft 팀으로 전송 해야 합니다. 번호를 받으면 오디오 회의 (회의 브리지 용), 자동 전화 교환, 통화 대기열 등의 사용자 및 서비스에 해당 전화 번호를 할당할 수 있습니다.
  
전화 번호를 팀으로 이식 하면 Microsoft에서 서비스 공급자가 되어 이전 서비스 공급자 또는 통신 회사와 서비스의 연결을 끊을 수 있습니다.

이 문서에 나와 있는 정보를 검토 하 여 번호 포팅에 대해 알아 보세요. 그 후에는 포트 주문을 만들어 전화 번호를 전송할 준비가 되어 있어야 합니다. 단계별 지침은 [팀에 전화 번호 전송을](transfer-phone-numbers-to-teams.md) 참조 하세요.
  
## <a name="what-countries-or-regions-support-number-porting"></a>번호 포팅에 지원 되는 국가 또는 지역

지원 되는 모든 국가 또는 지역에서 전화 번호를 이식 하거나 양도할 수 있지만, 포트 주문 요청을 제출 하는 방법은 전화 번호가 도착 하는 국가 또는 지역에 따라 달라 집니다. 번호 포팅을 지 원하는 국가 및 지역 목록은 [조직의 전화 번호 관리](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)를 참조 하세요.  

현재 Microsoft 팀 관리 센터의 [포팅 마법사는](transfer-phone-numbers-to-teams.md) 영국, 미국 및 캐나다의 전화 번호를 얻을 수 있도록 지원 합니다. 다른 국가 및 지역에 대 한 전화 번호를 얻으려면 [포트 주문을 수동으로 제출할](manually-submit-port-order.md)수 있습니다.
  
## <a name="what-numbers-can-be-transferred"></a>전송할 수 있는 번호는 무엇 인가요?

 **전송할 수 있습니다.**
  
일반적으로 다음을 포함 하 여 지원 되는 공급자의 전화 번호를 전송할 수 있습니다.
  
- 지역 전화 번호입니다.

- 휴대폰 및 태블릿에 사용 되는 모바일 장치 전화 번호입니다.

    > [!NOTE]
    > 휴대폰 번호 전송은 미국 및 푸에르토리코 에서만 사용할 수 있습니다.
  
- 유료 전화 번호.

- 무료 전화 번호.

    > [!NOTE]
    > UIFN (Universal Freephone Number)을 미국에 양도할 수 없습니다. 
  
- 전화 회의 브리지, 자동 전화 교환 등에 사용 되는 서비스 전화 번호입니다.

- 팩스 전화 번호를 사용할 수는 없지만 팩스에는 사용 될 수 없습니다. 사용자에 게 할당 해야 합니다.

- Vonage 또는 RingCentral와 같은 휴대폰 공급자의 VoIP 전화 번호입니다.

- 비즈니스용 Skype 하이브리드 전화 번호. 이러한 번호를 전송 하려면에 <ptn@microsoft.com>전자 메일을 보내 주십시오.

  **다음을 전송할 수 없습니다.**
  
    > [!NOTE]
    > 현재는 VoIP 전화 공급자의 전화 번호를 포함 하 여 지원 되는 국가나 지역 이외의 전화 번호나 번호를 양도할 수 없습니다. 지원 되는 국가/지역 목록은 [오디오 회의 및 통화 요금제의 국가 및 지역 사용 가능성](../country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md) 을 참조 하세요.
  
- DSL 회선 또는 광대역 인터넷 연결과 같은 데이터 연결에 사용 되는 전화 번호입니다.

- 팩스 전용 전화 번호입니다.

    팩스에 사용 되는 기존 전용 전화 번호가 있는 경우 이러한 번호를 팀으로 전송할 *수* 있지만, 팩스 서비스는 예상 대로 작동 하지 않습니다. 전화 시스템, 국내 통화 요금제 또는 국제 통화 요금제에 대 한 라이선스를 보유 하 고 있는 경우에도 팀 고객은 팩스 서비스를 사용할 수 없습니다.

    전화 번호를 팀으로 이식 하는 경우 팩스를 사용 하는 대신 조직의 사용자에 게이 전화 번호를 할당할 수 있습니다.

    > [!NOTE]
    > 영국의 경우 현재 지역 코드 0843, 0844, 0845, 0870, 0871, 0872의 공유 비용 번호를 포함 하 여 영국에 거주 하지 않는 번호의 양도 지원 하지 않습니다.
  
## <a name="what-information-do-i-need-to-provide"></a>어떤 정보를 제공 해야 하나요?

현재 통신 업체에 대 한 모든 계정 정보가 필요 합니다. 포트 주문에 입력 하는 정보는 대부분 현재 서비스 공급자의 최신 청구서 또는 송장에 나와 있습니다. 계정에 해당 하는 이름 및 포트를 원하는 번호를 알아야 할 수도 있습니다.
  
## <a name="what-are-full-port-and-partial-port-transfers"></a>전체 포트 및 부분 포트 전송 이란?

전화 번호를 팀으로 포팅 하는 경우 모든 번호 또는 일부를 이전 하는 옵션이 있습니다.
  
- **전체 포트** 이는 모든 번호를 현재 서비스 공급자에서 팀으로 전송 하는 경우입니다. 전송할 전화 번호를 묻는 메시지가 표시 되 면 계정에 있는 다른 모든 전화 번호와 함께 BTN (대금 청구 전화 번호)를 *포함 해야 합니다* .

    예를 들어 BTN가 *+ 1 425-555-1234* 이 고 모든 25 개의 전화 번호 (*+ 1 425-555-1235 ~ 1259*)를 이식 하려고 한다고 가정해 보겠습니다. 다음 지침에 따라 번호를 전송 하면 **+ 14255551234-+ 14255551259**을 입력 합니다.

- **부분 포트** 현재 서비스 공급자의 일부 전화 번호만 팀으로 전송 하는 경우입니다. 같은 BTN에 연결 된 일부 전화 번호를 이식 하려는 경우 * *는 귀하의 계정에 있는 다른 모든 전화번호와 함께 * * BTN를 *포함 하지 않아야 합니다* .

    예를 들어, BTN가 *+ 1 425-555-1234* 이 고 25 개의 전화 번호를 5 개 (*+ 1 425-555-1235 ~ 1259*)로만 이식 하려고 한다고 가정해 보겠습니다. 다음 지침에 따라 번호를 전송 하면 **+ 1 425 555 1235-+ 1 425 555 1239**을 입력 합니다.
    
## <a name="can-i-submit-a-single-number-porting-request-for-all-of-my-numbers-at-one-time"></a>한 번에 모든 번호에 대 한 단일 번호 포팅 요청을 제출할 수 있나요?
<a name="bkmk_type_1"> </a>

이식 하는 각 통신 업체와 번호 유형에 고유한 요청이 필요 합니다.
  
예를 들어 다음의 각 숫자 형식에 대해 고유한 번호 포팅 요청을 제출 해야 합니다.
  
- 로컬 유료 전화 번호 (가입자 번호 또는 지리 번호 라고도 함)

- 800, 844, 855, 866, 877, 888 등의 지역 번호를 사용 하 여 무료 통화를 받으세요.

- 휴대폰 번호

- Office 365에서 오디오 회의에 사용할 수 있는 서비스 번호입니다.

각 숫자 형식에 대해 번호 포팅 요청을 제출 하는 방법에 대 한 자세한 내용은 다음을 참조 하세요.
  
- 다른 통신 업체에서 제공 하는 **전화 번호** 를 사용 하려면 각 반송파와 함께 숫자에 대 한 고유한 포팅 요청이 필요 합니다.

- 800, 844, 855, 866, 877, 888 등의 지역 코드를 사용 하는 무료 **번호** 는 다른 유형의 번호를 사용 하는 번호 포팅 요청에 포함 될 수 없습니다. 이러한 무료 전화 번호를 이식 하려면 [포트 순서를 수동으로 제출](manually-submit-port-order.md)해야 합니다. Microsoft 팀 관리 센터에서 이러한 번호를 이식 할 수 없습니다. 자세한 내용은 [조직의 전화 번호 관리](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)를 참조 하세요.

    사용 하는 국가 및 전화 번호 형식에 대 한 올바른 인증 문자 (LOA)와 포트를 지정할 수 있는 것이 중요 합니다. [필요한 LOA를 다운로드할](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)수 있습니다.

- 전송에 권한을 부여 하려면 **휴대폰 번호** 에 PIN 코드가 필요 합니다. 따라서 별도의 번호 포팅 요청이 필요 합니다.

- **서비스 번호** 포팅 요청이 자체적으로 제출 되어야 합니다. 다른 유형의 번호로 제출할 수 없습니다.

## <a name="how-long-does-it-take-to-port-numbers"></a>포트 번호로 걸리는 시간은 얼마나 되나요?
<a name="bkmk_type_1"> </a>

포트 주문 요청을 완료 한 후에는 7-14 일이 처리 되어야 합니다. 그러나 서비스 공급자에 따라 최대 30 일이 걸릴 수 있습니다. 전화 번호가 전달 된 후에는 전자 메일을 받게 되며,이를 통해 연락이 완료 됩니다.
  
포트 순서의 상태를 확인 하려면 Microsoft 팀 관리 센터의 왼쪽 탐색 창에서 **음성** > **전화 번호로**이동한 다음 **주문 기록을**클릭 합니다. 각 포트 주문 상태가 **상태** 열에 나열 됩니다.
  
## <a name="can-user-subscriber-phone-numbers-be-converted-to-service-numbers"></a>사용자 (구독자) 전화 번호를 서비스 번호로 변환할 수 있나요?
<a name="bkmk_type_1"> </a>

예를 들어, 조직의 테 넌 트 GUID와 변환할 전화 번호를 포함 하는 서비스 요청을 제출 하기만 하면 됩니다. 이렇게 하려면 [조직의 전화 번호 관리](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)를 참조 하세요.

## <a name="common-mistakes-to-watch-out-for"></a>조사에 대 한 일반적인 실수
<a name="bkmk_type_1"> </a>

번호 포팅 작업은 쉽습니다. 고객님의 주문은 messed을 받을 수 있지만, 휴대폰 서비스 공급자에 문제가 있는 경우 주문이 불완전 하 고 정보가 누락 되었거나 오타가 있습니다.
  
다음은 고객이 번호를 입력 했을 때 표시 되는 가장 일반적인 실수입니다. 고객 지원에 대 한 통화를 직접 저장 하 고 이러한 오류를 한 번 더 확인 합니다.
  
- 제공 하는 계정 정보가 전화 통신 회사에서 기록 하는 내용과 정확히 일치 하는지 확인 합니다. 일치 하지 않는 정보는 오류의 가장 일반적인 원인이 며 포트 순서를 지연 합니다. 다음이 참인 지 확인 합니다.

  - 계정 변경 권한이 있는 이름이 나 사람이 올바른지 확인 합니다.

  - 주소가 올바릅니다.

  - 계정 번호가 올바릅니다.

  - BTN가 올바릅니다.

- 이러한 전화 번호에 사용 되는 통화 헌트, 특수 링 등의 고급 통화 제어 기능은 없는지 확인 합니다.

- 새로운 서비스를 주문 하거나 현재 서비스 공급자와의 연결을 해제 하지 않았는지 확인 합니다.

- 모든 숫자가 같은 통신 회사 및 동일한 계정에서 사용 중인지 확인 합니다.

- 서비스가 활성 상태 인지 확인 합니다. 계정을 고정 시키면 계정에 있는 캐리어가 변경 되지 않습니다. 계정을 변경할 권한이 있는 사람은 현재 통신 업체에 주문을 제출 해야 고정을 제거할 수 있습니다. 이 프로세스는 캐리어에 따라 1 ~ 3 주가 걸릴 수 있습니다.

## <a name="related-topics"></a>관련 항목

- [포트 주문의 상태 확인](port-order-status.md)
- [통화 요금제에 사용 되는 다른 종류의 전화 번호](../different-kinds-of-phone-numbers-used-for-calling-plans.md)
- [조직의 전화 번호 관리](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)
- [긴급 통화 사용 약관](../emergency-calling-terms-and-conditions.md)
- [비상 전화 고 지 사항 레이블](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)