---
title: 포트 순서
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.voice.phonenumbers.porting.overview
- Calling Plans
description: 포트 주문의 개요와 서비스 공급자에서 전화 번호를 전송하는 방법을 Teams.
ms.openlocfilehash: bb2c81a1c2263e59aee8477679440c7e26748c3a
ms.sourcegitcommit: 32ba2ed0343e19f56e62fb3c507923c95f11b1bd
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/19/2021
ms.locfileid: "61124275"
---
# <a name="whats-a-port-order"></a>포트 순서

현재 전화 서비스 공급자 또는 통신업체가 있으며 사용자 또는 서비스에 대한 전화 번호가 이미 있는 경우 해당 전화 번호를 전송하려면 *"포트* 주문"을 만들어야 Microsoft Teams. 번호가 포터링될 때 사용자 및 서비스에 이러한 전화 번호를 할당할 수 있습니다(컨퍼런스 브리지용), 자동 참석자 및 통화 큐.
  
전화 번호를 이동하여 전화 번호를 Teams Microsoft는 서비스 공급자가 되거나 이전 서비스 공급자 또는 통신사와의 서비스 연결을 끊을 수 있습니다.

번호 이식에 익숙해지기 위해 이 문서의 정보를 검토합니다. 그 후 포트 순서를 만들고 전화 번호를 전송할 준비가 되어 있습니다. 단계별 지침을 [Teams](transfer-phone-numbers-to-teams.md) 전화 번호 전송을 참조하세요.
  
## <a name="what-countries-or-regions-support-number-porting"></a>번호 포터링을 지원하는 국가 또는 지역은 무엇입니까?

지원되는 모든 국가 또는 지역에서 전화 번호를 포트 또는 전송할 수 있지만 포트 주문 요청을 제출하는 방법은 전화 번호가 오는 국가 또는 지역에 따라 달라 습니다. 번호 포터링을 지원하는 국가 및 지역 목록은 조직의 전화 번호 [관리를 참조하세요.](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)  

현재 [관리](transfer-phone-numbers-to-teams.md) 센터의 Microsoft Teams 마법사는 영국, 미국 및 캐나다에 대한 전화 번호를 받고 있습니다. 다른 국가 및 지역에 대한 전화 번호를 얻게하려면 포트 순서를 수동으로 [제출할 수 있습니다.](manually-submit-port-order.md)
  
## <a name="what-numbers-can-be-transferred"></a>전송할 수 있는 숫자는 무엇입니까?

 **전송할 수 있습니다.**
  
일반적으로 지원되는 공급자에서 다음을 포함하여 모든 전화 번호를 전송할 수 있습니다.
  
- 랜드라인 전화 번호입니다.

- 휴대폰 및 태블릿에 사용되는 휴대폰 전화 번호와 같은 휴대폰 전화 번호입니다.

    > [!NOTE]
    > 휴대폰 번호 전송은 미국 및 푸에르토리코에서만 사용할 수 있습니다.
  
- 전화 번호입니다.

- 무료 전화 번호입니다.

    > [!NOTE]
    > UIFN(유니버설 국제 무료 전화 번호)은 우리에게 전송할 수 없습니다. 
  
- 전화 번호(예: 전화 회의 브리지, 자동 참석자 등)입니다.

- 팩스 전화 번호이지만 팩스에 사용할 수 없습니다. 사용자에게 할당해야 합니다.

- Vonage 또는 RingCentral과 같은 전화 공급자의 VoIP 전화 번호입니다.

- 비즈니스용 Skype 전화 번호입니다. 이러한 번호를 전송하려는 경우 에서 이메일을 보내 주시기 <ptn@microsoft.com> 바랍니다.

**다음을 전송할 수 없습니다.**
  
> [!NOTE]
> 현재 VoIP 전화 공급자의 전화 번호를 포함하여 지원되는 국가 또는 지역에서 전송되지 않은 전화 번호 또는 번호를 전송할 수 없습니다. 지원되는 국가/지역 목록은 오디오 회의 및 통화 계획에 대한 국가 및 지역 가용성을 [참조하세요.](../country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
  
- DSL 전화 광대역 인터넷 연결과 같은 데이터 연결에 사용되는 숫자입니다.

- 전화 전용 숫자입니다.

    팩스에 사용되는 기존 전용 전화 번호가 있는  경우 이러한 번호를 Teams 팩스 서비스가 예상대로 작동하지 않습니다. 팩스 서비스는 Teams, 국내 통화 계획 또는 국제 통화 요금제에 대한 라이선스가 전화 시스템 고객에게는 사용할 수 없습니다.

    전화 번호를 이동하여 전화 번호를 Teams 팩스에 사용하는 대신 조직의 사용자에게 이 전화 번호를 할당할 수 있습니다.

> [!NOTE]
> 현재 영국에서는 지역 코드 0843, 0844, 0845, 0870, 0871, 0872에 대한 공유 비용 번호를 포함하여 영국 비지리 번호 전송을 지원하지 않습니다.
  
## <a name="what-information-do-i-need-to-provide"></a>어떤 정보를 제공해야 하나요?

현재 통신사에 대한 모든 계정 정보가 필요합니다. 포트 순서로 입력하는 정보는 대부분 현재 서비스 공급자의 가장 최근 청구서 또는 송장에서 찾을 수 있습니다. 또한 계정의 이름과 포트할 숫자를 알아야 합니다.
  
## <a name="what-are-full-port-and-partial-port-transfers"></a>전체 포트 및 부분 포트 전송이란?

전화 번호를 포터링하여 Teams 모든 번호 또는 일부를 전송할 수 있습니다.
  
- **전체 포트** 현재 서비스 공급자에서 모든 번호를 전송하는 Teams. 전송하려는 전화 번호를 묻는 요청이 있는  경우 계정의 다른 모든 전화 번호와 함께 BTN(청구 전화 번호)을 포함해야 합니다.

    예를 들어 BTN이  *+1 425-555-1234이고*  25개 전화 *번호(+1 425-555-1235~1259)를* 모두 이식하려는 경우를 예로 들어 보겠습니다. 아래 지침에 따라 번호를 전송하면 **+14255551234 - +14255551259.**

- **부분 포트** 현재 서비스 공급자에서 일부 전화 번호만 전송하는 경우 Teams. 동일한 BTN에 연결된 전화 번호 중 일부를 이식하려는 경우 **** 계정의 다른 모든 전화 번호와 함께 ** BTN을 포함하지 말아야 합니다.

    예를 들어 BTN이 *+1 425-555-1234이고* 25개 전화 번호 중 5개만 포트하려는 *경우(+1 425-555-1235~1259).* 아래 지침을 따라 번호를 전송하면 **+1 425 555 1235 - +1 425 555 1239** 를 입력합니다.
    
## <a name="can-i-submit-a-single-number-porting-request-for-all-of-my-numbers-at-one-time"></a>모든 번호에 대한 단일 번호 포터링 요청을 한 번씩 제출할 수 있나요?
<a name="bkmk_type_1"> </a>

이식되는 각 캐리어 및 번호 유형에 대해 고유한 요청이 필요합니다.
  
예를 들어 다음 유형의 숫자 각각에 대해 고유 번호 포터링 요청을 제출해야 합니다.
  
- 구독자 번호 또는 지리적 번호라고도 하는 로컬 전화 번호

- 800, 844, 855, 866, 877 및 888과 같은 지역 코드가 있는 무료 전화 번호

- 휴대폰 번호

- 오디오 회의에 사용할 수 있는 서비스 Microsoft 365 Office 365.

이러한 유형의 각 숫자에 대한 번호 이식 요청을 제출하는 방법에 대한 자세한 내용은 다음과 같습니다.
  
- **전화** 통신사에서 제공하는 숫자에는 각 통신사와의 숫자에 대한 고유한 포터링 요청이 요구됩니다.

-  800, 844, 855, 866, 877 및 888과 같은 지역 코드가 있는 무료 번호는 다른 유형의 숫자로 번호 포터링 요청에 포함될 수 없습니다. 이러한 무료 번호를 포트하려면 포트 [순서를 수동으로 제출해야 합니다.](manually-submit-port-order.md) 관리 센터에서 이러한 숫자를 Microsoft Teams 수 없습니다. 자세한 내용은 조직의 [전화 번호 관리를 참조하세요.](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)

    포트하려는 국가 및 전화 번호 유형에 대해 올바른 LOA(인증 편지)를 사용하는 것이 중요합니다. 여기에서 [필요한 LOA를 다운로드할 수 있습니다.](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)

- **휴대폰 번호에는** 전송을 승인하기 위해 PIN 코드가 필요하게 됩니다. 따라서 별도의 번호 포터링 요청이 필요합니다.

- **서비스 번호** 이식 요청은 자체적으로 제출해야 합니다. 다른 유형의 숫자로 제출할 수 없습니다.

## <a name="how-long-does-it-take-to-port-numbers"></a>포트 번호에 얼마나 오래 걸릴까요?
<a name="bkmk_type_1"> </a>

포트 주문 요청을 완료한 후 처리하는 데 7-14일이 걸립니다. 그러나 서비스 공급자에 따라 최대 30일이 걸릴 수 있습니다. 전화 번호가 이식된 후 전자 메일이 전송되어 이동하는 것이 좋다는 것을 알 수 있습니다.
  
포트 순서 상태를 확인하려면 관리 센터의 왼쪽 Microsoft Teams 음성 번호로 이동한 다음 전화 기록을   >   **클릭합니다.** 각 포트 주문 상태는 상태 **열에 나열됩니다.**
  
## <a name="can-user-subscriber-phone-numbers-be-converted-to-service-numbers"></a>사용자(구독자) 전화 번호를 서비스 번호로 변환할 수 있나요?
<a name="bkmk_type_1"> </a>

예. 할 수 있습니다. 조직의 테넌트 GUID 및 변환하려는 전화 번호가 포함된 서비스 요청을 제출하기만하면 됩니다. 이 작업을 위해 조직의 전화 [번호 관리를 참조합니다.](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)

## <a name="can-i-port-out-my-numbers-from-teams-to-a-different-phone-service-provider-or-carrier"></a>다른 전화 서비스 공급자 또는 통신사로 Teams 내 번호를 이식할 수 있나요?

다른 통신사로 번호를 Teams 새 통신사에 요청을 제출해야 합니다. 또한 지원 사례를 열고 포트 PIN을 설정해야 합니다. 지원을 받을 수 있는 방법에 대한 자세한 내용은 지원 [을 참조하세요.](/microsoft-365/business-video/get-help-support) 

새 통신 사업자에서 포터링 요청에 문의하면 사용자가 정의한 PIN을 제공해야 합니다.

## <a name="common-mistakes-to-watch-out-for"></a>조심해야 하는 일반적인 실수
<a name="bkmk_type_1"> </a>

번호 포터링은 쉽게 할 수 있습니다. 주문이 까다로워지지만 전화 서비스 공급자에 문제가 있는 경우 주문이 불완전하고 누락된 정보 또는 오타가 있습니다.
  
다음은 고객이 포트 번호로 표시하는 가장 일반적인 실수입니다. 고객 지원에 대한 전화를 저장하고 이러한 오류를 다시 검사합니다.
  
- 제공한 계정 정보가 휴대폰 통신사가 기록한 정보와 정확히 일치해야 합니다. 불일치 정보는 오류의 가장 일반적인 원인으로 포트 순서를 지연합니다. 다음이 true인지 확인합니다.

  - 계정을 변경할 권한이 있는 이름 또는 사용자가 올바른 것입니다.

  - 주소가 올바른 것입니다.

  - 계정 번호가 올바른 것입니다.

  - BTN이 올바른 것입니다.

- 이러한 전화 번호에서 사용하도록 설정된 호출 사냥, 독특한 링과 같은 고급 통화 제어 기능이 없는지 확인합니다.

- 현재 서비스 공급자와 연결 끊기거나 새 서비스 주문을 배치하지 않은지 확인하십시오.

- 모든 번호가 동일한 통신 사업자 및 동일한 계정의 번호가 있는지 확인하세요.

- 서비스가 활성 상태인지 확인 합니다. 계정을 동결하면 계정의 통신사 변경이 방지됩니다. 계정을 변경할 권한이 있는 사람은 현재 이동통신사에 동결을 제거하기 위해 주문을 제출해야 합니다. 이 프로세스는 캐리어에 따라 1~3주가 걸릴 수 있습니다.

## <a name="related-topics"></a>관련 항목

- [포트 주문의 상태 확인](port-order-status.md)
- [통화 계획에 사용되는 다양한 종류의 전화 번호](../different-kinds-of-phone-numbers-used-for-calling-plans.md)
- [조직의 전화 번호 관리](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)
- [긴급 통화 사용 약관](../emergency-calling-terms-and-conditions.md)
- [긴급 통화 고지 레이블](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)
