---
title: 포트 주문의 상태는 무엇 인가요?
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
f1keywords: ''
ms.custom:
- Calling Plans
description: '포트 주문 상태를 확인 하는 방법과 해당 사용자가 사용할 수 있는 다양 한 작업을 확인 하는 방법에 대해 알아봅니다. '
ms.openlocfilehash: 7c7b0c745ac4af01b58771463f348f5ac0f3dac7
ms.sourcegitcommit: 100ba1409bf0af58e4430877c1d29622d793d23f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/01/2019
ms.locfileid: "37925687"
---
# <a name="whats-the-status-of-your-port-orders"></a>포트 주문의 상태는 무엇 인가요?

포트 순서의 상태를 확인 하려면 Microsoft 팀 관리 센터의 왼쪽 탐색 창에서 > **음성** > **포트 주문**으로 이동한 다음 **주문 기록을**클릭 합니다. 각 포트 주문 상태가 **상태** 열에 나열 됩니다.

다음 표에서는 포트 순서 상태 및 필요한 경우 수행할 수 있는 작업을 보여 줍니다.

|**상태**|**주문을 볼 수 있나요?**|**주문을 편집할 수 있나요?**|**주문을 취소할 수 있나요?**|**주문을 삭제할 수 있습니까?**|**설명**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|**워드프로세싱** <br/> |예  <br/> |아니요  <br/> |예  <br/> |아니요  <br/> |관리자가 주문을 만들었고 Microsoft에서 수신 했습니다.  <br/> |
|**통신 회사 접속 하기** <br/> |예  <br/> |아니요  <br/> |예  <br/> |아니요  <br/> |Microsoft에 의해 주문이 접수 되 고 승인 되었으며, 손실 된 반송파로 작업 하 여 승인을 받습니다.  <br/> |
|**전송 승인 됨** <br/> |예  <br/> |FOC (기업 주문 약정)  <br/> |예  <br/> |아니요  <br/> |손실 된 반송파에 의해 주문이 수락 되었고 FOC 날짜가 설정 되었습니다.  <br/> |
|**전송 보류 중** <br/> |예  <br/> |아니요  <br/> |아니요  <br/> |아니요  <br/> |24 시간 이내에 전송이 더 이상 편집 되거나 취소 될 수 없습니다.  <br/> |
|**오류** <br/> |아니요  <br/> |예  <br/> |예  <br/> |예 (현재 오류가 있는 경우 포트 순서를 삭제할 수 없습니다. 포트 순서를 다시 만들거나 [PSTN 서비스 데스크 도움말](../manage-phone-numbers-for-your-organization/contact-pstn-service-desk.md)에 문의 해야 합니다.  <br/> |손실 된 반송파가 주문을 거부 했습니다.  <br/> |
|**완료** <br/> |예  <br/> |아니요  <br/> |아니요  <br/> |아니요  <br/> |숫자가 성공적으로 전송 되었습니다.  <br/> |
|**되었습니다** <br/> |아니요  <br/> |예  <br/> |아니요  <br/> |아니요  <br/> |관리자가 주문을 취소 했습니다.  <br/> |

자세한 단계별 지침은 [팀에 전화 번호 이전](transfer-phone-numbers-to-teams.md)을 참조 하세요.

도움이 필요 하거나 전화 번호를 더 확보 해야 하는 경우 [PSTN 서비스 데스크 도움말을 참조](../manage-phone-numbers-for-your-organization/contact-pstn-service-desk.md)하세요.

## <a name="related-topics"></a>관련 항목

- [포트 순서는 무엇 인가요?](port-order-overview.md)
- [통화 요금제에 사용 되는 다른 종류의 전화 번호](../different-kinds-of-phone-numbers-used-for-calling-plans.md)
- [Manage phone numbers for your organization](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)(조직의 전화 번호 관리)
- [긴급 통화 사용 약관](../emergency-calling-terms-and-conditions.md)
- [비상 전화 고 지 사항 레이블](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)
