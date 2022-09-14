---
title: 포트 순서
author: CarolynRowe
ms.author: crowe
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
description: 포트 주문의 개요와 서비스 공급자에서 Teams로 전화 번호를 전송하는 방법을 알아 보세요.
ms.collection:
- M365-voice
- m365initiative-voice
ms.openlocfilehash: c5c8b68cfd97c8a39f0b4866fb7670473a9ecef3
ms.sourcegitcommit: 46b5dc0519d487e264b1386e5074085c2d090e9a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/14/2022
ms.locfileid: "67674379"
---
# <a name="whats-a-port-order"></a>포트 순서

현재 전화 서비스 공급자 또는 이동 통신 사업자가 있고 사용자 또는 서비스에 대한 전화 번호가 이미 있는 경우 해당 전화 번호를 Microsoft Teams로 전송하는 "*포트 주문*"을 만들어야 합니다. 번호가 이식되면 오디오 회의(회의 브리지), 자동 전화 교환 및 통화 큐와 같은 사용자 및 서비스에 해당 전화 번호를 할당할 수 있습니다.
  
전화 번호를 Teams로 이식하면 Microsoft가 서비스 공급자가 되고 이전 서비스 공급자 또는 이동 통신 사업자와의 서비스 연결을 끊을 수 있습니다.

이 문서의 정보를 검토하여 번호 포팅에 대해 알아보세요. 그런 다음 포트 주문을 만들고 전화 번호를 전송할 준비가 되어 있어야 합니다. 단계별 지침 [은 Teams로 전화 번호 전송](transfer-phone-numbers-to-teams.md) 을 참조하세요.
  
## <a name="what-countries-or-regions-support-number-porting"></a>번호 포팅을 지원하는 국가 또는 지역은 무엇인가요?

지원되는 모든 국가 또는 지역에서 전화 번호를 이식하거나 전송할 수 있지만, 포트 주문 요청을 제출하는 방법은 전화 번호가 있는 국가 또는 지역에 따라 달라집니다. 번호 포팅을 지원하는 국가 및 지역 목록은 [조직의 전화 번호 관리를 참조하세요](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md).  

현재 Microsoft Teams 관리 센터의 [포팅 마법사](transfer-phone-numbers-to-teams.md)는 영국, 미국 및 캐나다의 전화 번호 가져오기를 지원합니다. 다른 국가 및 지역의 전화 번호를 가져오려면 [포트 주문을 수동으로 제출할](manually-submit-port-order.md) 수 있습니다.
  
## <a name="what-numbers-can-be-transferred"></a>어떤 숫자를 전송할 수 있나요?

 **전송할 수 있습니다.**
  
일반적으로 다음을 포함하여 지원되는 공급자의 전화 번호를 전송할 수 있습니다.
  
- 유선 전화 번호입니다.

- 휴대폰 및 태블릿에 사용되는 전화 번호와 같은 휴대폰 전화 번호입니다.

    > [!NOTE]
    > 휴대폰 번호 전송은 미국 및 푸에르토리코에서만 사용할 수 있습니다.
  
- 유료 전화 번호입니다.

- 무료 전화 번호입니다.

    > [!NOTE]
    > UIFN(유니버설 국제 무료 전화 번호)은 전송할 수 없습니다.
    > 무료 전화 번호의 포팅 가용성은 국가 및 지역에 따라 다를 수 있습니다. 더 많은 정보를 찾으려면 해당 국가 또는 지역별 문서를 참조하여 포팅 서비스에 사용할 수 있는 지원을 확인하세요. 
  
- 전화 회의 브리지, 자동 전화 교환 등에 사용되는 전화 번호와 같은 서비스 전화 번호입니다.

- 팩스 전화 번호는 팩스로 보낼 수 없습니다. 사용자에게 할당해야 합니다.

- Vonage 또는 RingCentral과 같은 전화 공급자의 VoIP 전화 번호입니다.

- 하이브리드 전화 번호(직접 라우팅 또는 운영자 연결에서 통화 플랜으로 마이그레이션)를 포팅하는 경우 [전화 번호 서비스 팀에](../manage-phone-numbers-for-your-organization/contact-tns-service-desk.md) 문의하세요. 하이브리드 전화 번호라는 메모가 포함되어 있는지 확인합니다.

**다음을 전송할 수 없습니다.**
  
> [!NOTE]
> 현재는 VoIP 전화 공급자의 전화 번호를 포함하여 지원되는 국가 또는 지역에서 제공되지 않는 전화 번호 또는 번호를 전송할 수 없습니다. 지원되는 국가/지역 목록은 [오디오 회의 및 통화 플랜에 대한 국가 및 지역 가용성](../country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)을 참조하세요.
  
- DSL 회선 또는 광대역 인터넷 연결과 같은 데이터 연결에 사용되는 전화 번호입니다.

- 팩스 전용 전화 번호입니다.

    팩스에 사용되는 기존 전용 전화 번호가 있는 경우 이러한 번호를 Teams로 전송할  *수*  있지만 팩스 서비스는 예상대로 작동하지 않습니다. 전화 시스템, 국내 통화 플랜 또는 국제 통화 플랜에 대한 라이선스가 있더라도 Teams 고객은 팩스 서비스를 사용할 수 없습니다.

    전화 번호를 Teams로 포팅하는 경우 이 전화 번호를 팩스에 사용하는 대신 조직의 사용자에게 할당할 수 있습니다.

> [!NOTE]
> 현재 영국에서는 지역 코드 0843, 0844, 0845, 0870, 0871, 0872에 대한 공유 비용 번호를 포함하여 영국의 비지리 번호 전송을 지원하지 않습니다.
  
## <a name="what-information-do-i-need-to-provide"></a>어떤 정보를 제공해야 하나요?

현재 이동 통신 사업자에 대한 모든 계정 정보가 있어야 합니다. 포트 주문에 입력하는 정보는 대부분 현재 서비스 공급자의 최신 청구서 또는 청구서에서 찾을 수 있습니다. 또한 계정의 이름 및 포트하려는 숫자를 알아야 합니다.
  
## <a name="what-are-full-port-and-partial-port-transfers"></a>전체 포트 및 부분 포트 전송이란?

Teams로 전화 번호를 포팅하는 경우 모든 번호 또는 그 중 일부를 전송할 수 있습니다.
  
- **전체 포트** 현재 서비스 공급자에서 Teams로 모든 번호를 전송하는 경우입니다. 전송하려는 전화 번호를 묻는 메시지가 표시되면 계정의 다른 모든 전화 번호와 함께 BTN(청구 전화 번호)을 *포함해야 합니다* .

    예를 들어 BTN이  *+1 425-555-1234*  이고 25개의 전화 번호(*+1 425-555-1235~1259*)를 모두 이식하려는 경우를 가정해 보겠습니다. 아래 지침에 따라 번호를 전송하면 **+14255551234 - +14255551259** 입력합니다.

- **부분 포트** 현재 서비스 공급자에서 Teams로 전화 번호 중 일부만 전송하는 경우입니다. 동일한 BTN에 연결된 전화 번호 중 일부를 이식하려는 경우 ** 계정의 다른 모든 전화 번호와 함께 ** BTN을 *포함하지 않아야 합니다* .

    예를 들어 BTN이  *+1 425-555-1234*  이고 25개의 전화 번호 중 5개만 이식하려고 합니다(*+1 425-555-1235~1259*). 아래 지침에 따라 번호를 전송하면 **+1 425 555 1235 - +1 425 555 1239** 를 입력합니다.
    
## <a name="can-i-submit-a-single-number-porting-request-for-all-of-my-numbers-at-one-time"></a>한 번에 모든 번호에 대한 단일 번호 포팅 요청을 제출할 수 있나요?
<a name="bkmk_type_1"> </a>

각 이동 통신 사업자 및 이식되는 번호 유형에 대해 고유한 요청이 필요합니다.
  
예를 들어 다음과 같은 각 유형의 숫자에 대해 고유한 번호 포팅 요청을 제출해야 합니다.
  
- 구독자 번호 또는 지리적 번호라고도 하는 지역 통행료 번호

- 지역 번호가 있는 무료 번호: 800, 844, 855, 866, 877 및 888

- 휴대폰 번호

- Microsoft 365 또는 Office 365 오디오 회의에 사용할 수 있는 서비스 번호입니다.

이러한 각 유형의 숫자에 대한 번호 포팅 요청을 제출하는 방법에 대한 자세한 내용은 다음과 같습니다.
  
- 서로 다른 통신 사업자가 제공하는 **전화 번호** 에는 각 운송업체의 번호에 대한 고유한 포팅 요청이 필요합니다.

- 지역 번호(예: 800, 844, 855, 866, 877 및 888)와 같은 **무료 번호** 는 다른 유형의 숫자와 함께 번호 포팅 요청에 포함할 수 없습니다. 이러한 무료 번호를 이식하려면 [포트 주문을 수동으로 제출](manually-submit-port-order.md)해야 합니다. Microsoft Teams 관리 센터에서는 이러한 번호를 이식할 수 없습니다. 자세한 내용은 [조직의 전화 번호 관리를 참조하세요](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md).

    포트하려는 국가 및 전화 번호 유형에 올바른 LOA(승인서)를 사용하는 것이 중요합니다. [여기에서 필요한 LOA를 다운로드할 수 있습니다](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md).

- **휴대폰 번호에는** 전송 권한을 부여하는 PIN 코드가 필요합니다. 따라서 별도의 번호 포팅 요청이 필요합니다.

- **서비스 번호** 포팅 요청은 스스로 제출해야 합니다. 다른 유형의 숫자로 제출할 수 없습니다.

## <a name="how-long-does-it-take-to-port-numbers"></a>포트 번호에 얼마나 걸리나요?
<a name="bkmk_type_1"> </a>

포트 주문 요청을 완료한 후 처리되는 데 7~14일이 걸립니다. 그러나 서비스 공급자에 따라 최대 30일이 걸릴 수 있습니다. 전화 번호가 이식된 후에는 이동이 좋다는 것을 알려주는 이메일을 받게 됩니다.
  
포트 주문 상태를 확인하려면 Microsoft Teams 관리 센터의 왼쪽 탐색에서 **음성** > **전화 번호** 로 이동한 다음 **주문 기록을** 클릭합니다. 각 포트 순서 상태는 **상태** 열에 나열됩니다.
  
## <a name="can-user-subscriber-phone-numbers-be-converted-to-service-numbers"></a>사용자(구독자) 전화 번호를 서비스 번호로 변환할 수 있나요?
<a name="bkmk_type_1"> </a>

예, 그들은 할 수 있습니다. 이렇게 하려면 [전화 번호 사용 관리를 참조하세요](../manage-the-usage-of-a-phone-number.md).

## <a name="can-i-port-out-my-numbers-from-teams-to-a-different-phone-service-provider-or-carrier"></a>Teams에서 다른 전화 서비스 공급자 또는 이동 통신 사업자로 내 번호를 이식할 수 있나요?

Teams에서 다른 이동 통신 사업자로 번호를 이식하려면 새 운송업체에 요청을 제출해야 합니다. 또한 Microsoft Teams 관리 센터에서 포팅 PIN을 설정해야 합니다.

포팅 PIN을 정의하려면 Microsoft Teams 관리 센터의 왼쪽 탐색에서 **음성** > **전화 번호** 로 이동하고 페이지의 오른쪽 위 모서리에서 **포팅 PIN 관리를** 선택한 다음 10자리 PIN을 입력합니다.

새 이동 통신 사업자가 포팅 요청으로 문의하면 사용자가 정의한 PIN을 제공하도록 요청합니다.

PIN을 추가로 설정해야 하는 경우 [전화 번호 서비스 팀에](../manage-phone-numbers-for-your-organization/contact-tns-service-desk.md) 문의하세요.

## <a name="common-mistakes-to-watch-out-for"></a>주의해야 할 일반적인 실수
<a name="bkmk_type_1"> </a>

번호 포팅은 쉽게 수행할 수 있습니다. 그러나 전화 서비스 공급자에 문제가 있거나 주문이 불완전하고 누락된 정보가 있거나 오타가 있는 경우 주문이 엉망이 될 수 있습니다.
  
다음은 고객이 번호를 이식할 때 발생하는 가장 일반적인 실수입니다. 고객 지원에 대한 호출을 저장하고 이러한 오류를 다시 확인합니다.
  
- 제공하는 계정 정보가 휴대폰 통신 사업자의 기록과 정확히 일치하는지 확인합니다. 일치하지 않는 정보는 오류의 가장 일반적인 원인이며 포트 순서를 지연합니다. 다음이 true인지 확인합니다.

  - 계정을 변경할 수 있는 권한이 있는 이름 또는 사람이 올바르습니다.

  - 주소가 올바르습니다.

  - 계정 번호가 올바르습니다.

  - BTN이 맞습니다.

- 이러한 전화 번호에서 사용할 수 있는 고급 통화 제어 기능(예: 통화 사냥, 고유 링)이 없는지 확인합니다.

- 현재 서비스 공급자와 새 서비스 주문을 하거나 연결을 끊지 않았는지 확인합니다.

- 모든 숫자가 동일한 운송업체와 동일한 계정에서 온 것인지 확인합니다.

- 서비스가 활성 상태인지 확인합니다. 계정을 동결하면 계정에서 이동 통신 사업자가 변경되지 않습니다. 계정을 변경할 수 있는 권한이 있는 사람은 현재 운송업체에 주문을 제출하여 동결을 제거해야 합니다. 이 프로세스는 운송업체에 따라 1~3주가 걸릴 수 있습니다.

## <a name="related-topics"></a>관련 주제

- [포트 주문의 상태 확인](port-order-status.md)
- [통화 플랜에 사용되는 다양한 종류의 전화 번호](../different-kinds-of-phone-numbers-used-for-calling-plans.md)
- [조직의 전화 번호 관리](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)
- [긴급 통화 사용 약관](../emergency-calling-terms-and-conditions.md)
- [긴급 통화 고지 사항 레이블](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)
