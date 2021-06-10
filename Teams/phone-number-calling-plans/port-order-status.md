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
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Calling Plans
description: '포트 주문의 상태 및 수행할 수 있는 다양한 작업을 얻을 수 있는 방법에 대해 자세히 알아보습니다. '
ms.openlocfilehash: 8290ffba7be56f3ede0e275c801110f8c9d9539e
ms.sourcegitcommit: 693205da865111380b55c514955ac264031eb2fd
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/02/2020
ms.locfileid: "44205689"
---
# <a name="whats-the-status-of-your-port-orders"></a>포트 주문의 상태 확인

포트 순서 상태를 보려면 관리 센터의 왼쪽 탐색에서 Microsoft Teams 음성 포트 > 순서로 이동한 다음 **주문** 기록 을  >   **클릭합니다.** 각 포트 주문 상태는 상태 **열에 나열됩니다.** 주문 [프로세스에](../phone-number-calling-plans/port-order-overview.md#how-long-does-it-take-to-port-numbers) 대해 알아보는 데 포트 번호가 얼마나 오래 걸릴지 참조합니다. 

다음 표에는 필요한 경우 수행할 수 있는 작업뿐만 아니라 포트 순서 상태도 나열되어 있습니다.

|**상태**|**주문을 볼 수 있나요?**|**주문을 편집할 수 있나요?**|**주문을 취소할 수 있나요?**|**주문을 삭제할 수 있나요?**|**설명**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|**처리** <br/> |예  <br/> |아니요  <br/> |예  <br/> |아니요  <br/> |관리자가 주문을 만들어 Microsoft에서 수신합니다.  <br/> |
|**통신사에 문의** <br/> |예  <br/> |아니요  <br/> |예  <br/> |아니요  <br/> |주문은 Microsoft에서 수신 및 승인을 받았고, 잃은 통신사와 협력하여 승인을 받고 있습니다.  <br/> |
|**전송 승인됨** <br/> |예  <br/> |아니요  <br/> |예  <br/> |아니요  <br/> |주문은 패소한 통신사에 의해 수락되고 FOC(Firm Order Commitment) 날짜가 설정되어 있습니다.  <br/> |
|**전송 보류 중** <br/> |예  <br/> |아니요  <br/> |아니요  <br/> |아니요  <br/> |전송은 24시간 미만이기 때문에 주문을 더 이상 편집하거나 취소할 수 없습니다.  <br/> |
|**오류** <br/> |아니요  <br/> |예  <br/> |예  <br/> |예(현재는 오류가 있는 경우 포트 순서를 삭제할 수 없습니다. 포트 순서를 다시 만들어야 합니다. 또는 PSTN 서비스 데스크 도움말에 [문의해야 합니다.](../manage-phone-numbers-for-your-organization/contact-pstn-service-desk.md)  <br/> |패한 캐리어는 주문을 거부했습니다.  <br/> |
|**완료되었습니다.** <br/> |예  <br/> |아니요  <br/> |아니요  <br/> |아니요  <br/> |숫자가 성공적으로 전송됩니다.  <br/> |
|**취소** <br/> |아니요  <br/> |예  <br/> |아니요  <br/> |아니요  <br/> |관리자가 주문을 취소합니다.  <br/> |

전체 단계별 지침은 전화 [번호 전송을](transfer-phone-numbers-to-teams.md)Teams.

도움이 필요하거나 전화 번호를 더 많이 제공해야 하는 경우 [PSTN 서비스 데스크에 문의합니다.](../manage-phone-numbers-for-your-organization/contact-pstn-service-desk.md)

## <a name="related-topics"></a>관련 항목

- [포트 순서](port-order-overview.md)
- [통화 계획에 사용되는 다양한 종류의 전화 번호](../different-kinds-of-phone-numbers-used-for-calling-plans.md)
- [조직의 전화 번호 관리](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)
- [긴급 통화 사용 약관](../emergency-calling-terms-and-conditions.md)
- [긴급 통화 고지 레이블](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)
