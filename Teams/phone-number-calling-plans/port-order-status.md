---
title: 포트 주문의 상태 확인
ms.author: tonysmit
author: tonysmit
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
- Calling Plans
description: 포트 주문의 상태를 가져오는 방법과 해당 주문에 대해 수행할 수 있는 다양한 작업에 대해 알아봅니다.
ms.collection:
- M365-voice
ms.openlocfilehash: 29b12d5ec47625a62314bf601018ef069aec4ddb
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/07/2022
ms.locfileid: "67270423"
---
# <a name="whats-the-status-of-your-port-orders"></a>포트 주문의 상태 확인

포트 주문의 상태를 보려면 Microsoft Teams 관리 센터의 왼쪽 탐색에서 > **음성** > **포트 주문** 으로 이동한 다음 **주문 기록을** 클릭합니다. 각 포트 순서 상태는 **상태** 열에 나열됩니다. 주문 프로세스에 대해 알아보 [기 위해 포트 번호에 걸리는 시간을](../phone-number-calling-plans/port-order-overview.md#how-long-does-it-take-to-port-numbers) 확인합니다. 

다음 표에는 포트 주문 상태와 필요한 경우 수행할 수 있는 작업이 나열되어 있습니다.

|**상태**|**주문을 볼 수 있나요?**|**주문을 편집할 수 있나요?**|**주문을 취소할 수 있나요?**|**주문을 삭제할 수 있나요?**|**설명**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|**처리** <br/> |예  <br/> |아니요  <br/> |예  <br/> |아니요  <br/> |관리자가 주문을 만들었으며 Microsoft에서 주문을 받았습니다.  <br/> |
|**이동 통신 사업자에 문의** <br/> |예  <br/> |아니요  <br/> |예  <br/> |아니요  <br/> |주문은 Microsoft에 의해 접수 및 승인되었으며, 당사는 손실된 운송업체와 협력하여 승인을 받고 있습니다.  <br/> |
|**전송 승인됨** <br/> |예  <br/> |아니요  <br/> |예  <br/> |아니요  <br/> |손실된 운송업체가 주문을 수락했으며 FOC(회사 주문 약정) 날짜가 설정되었습니다.  <br/> |
|**전송 보류 중** <br/> |예  <br/> |아니요  <br/> |아니요  <br/> |아니요  <br/> |전송이 24시간 미만이므로 더 이상 주문을 편집하거나 취소할 수 없습니다.  <br/> |
|**오류** <br/> |아니요  <br/> |예  <br/> |예  <br/> |예(현재 오류가 있는 경우 포트 순서를 삭제할 수 없습니다.) 포트 주문을 다시 만들어야 하거나 [TNS Service Desk](../manage-phone-numbers-for-your-organization/contact-tns-service-desk.md)에 문의해야 합니다.  <br/> |잃어버린 캐리어는 주문을 거부했다.  <br/> |
|**완료** <br/> |예  <br/> |아니요  <br/> |아니요  <br/> |아니요  <br/> |숫자가 성공적으로 전송되었습니다.  <br/> |
|**취소** <br/> |아니요  <br/> |예  <br/> |아니요  <br/> |아니요  <br/> |관리자가 주문을 취소했습니다.  <br/> |

전체 단계별 지침은 [Teams로 전화 번호 전송을 참조하세요](transfer-phone-numbers-to-teams.md).

도움이 필요하거나 더 많은 전화 번호를 받아야 하는 경우 [TNS 서비스 데스크](../manage-phone-numbers-for-your-organization/contact-tns-service-desk.md)에 문의하세요.

## <a name="related-topics"></a>관련 항목

- [포트 순서](port-order-overview.md)
- [통화 플랜에 사용되는 다양한 종류의 전화 번호](../different-kinds-of-phone-numbers-used-for-calling-plans.md)
- [조직의 전화 번호 관리](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)
- [긴급 통화 사용 약관](../emergency-calling-terms-and-conditions.md)
- [긴급 통화 고지 사항 레이블](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)
