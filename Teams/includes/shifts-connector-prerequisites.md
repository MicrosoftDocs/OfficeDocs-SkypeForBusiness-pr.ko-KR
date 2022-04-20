---
author: LanaChin
ms.author: v-lanachin
ms.date: 03/31/2022
ms.topic: include
audience: admin
ms.service: msteams
ms.openlocfilehash: ab375a876eb62e5f41e5dd7cda3743d4010b95ff
ms.sourcegitcommit: bf0071417188b33fc23e2a420187da5024d4bd40
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/20/2022
ms.locfileid: "64593694"
---
시작하기 전에 다음 필수 구성 요소가 있는지 확인합니다.

- Blue Yonder WFM 버전 2020.3, 2021.1 또는 2021.2.

    > [!NOTE]
    > Blue Yonder WFM 2020.3 또는 2021.1이 있는 경우 2020.3.0.4 또는 2021.1.0.3 패치를 적용합니다. 이 패치는 사용자가 Shifts에서 영구 오류 메시지를 받는 문제를 해결합니다. 또한 사용자가 Shifts에서 가용성을 업데이트하지 못하게 하는 문제를 해결합니다.

- Blue Yonder WFM 서비스 계정 이름 및 암호 및 서비스 URL:

    - 페더레이션 인증 URL
    - 쿠키 인증 URL
    - 직원 셀프 서비스 URL
    - 소매 웹 API URL
    - 사이트 관리자 API URL
    - 관리 API URL

    이 정보가 없는 경우 Blue Yonder 지원에 문의하세요. 계정은 Blue Yonder 엔터프라이즈 관리자가 루트 엔터프라이즈 수준에서 만듭니다. API 액세스, 클라이언트 관리자 및 스토어 관리자 액세스 권한이 있어야 합니다. 연결을 만들려면 계정 및 암호가 필요합니다.
- 페더레이션된 SSO 인증은 Blue Yonder WFM 환경에서 사용하도록 설정됩니다. 페더레이션된 SSO를 사용하도록 설정하려면 Blue Yonder 지원에 문의하세요. 다음 정보가 필요합니다.

    - federatedSSOValidationService: `https://wfmconnector.teams.microsoft.com/api/v1/fedauth/{tenantId}/6A51B888-FF44-4FEA-82E1-839401E9CD74/authorize` 여기서 {tenantId}는 tenantId입니다.
     - proxyHeader: X-MS-AuthToken

- Teams 하나 이상의 팀이 설정되었습니다.
- 매핑하려는 모든 팀에 팀 소유자로 Microsoft 365 시스템 계정을 추가했습니다.</br> [Microsoft 365 이 계정을 만들고](/microsoft-365/admin/add-users/add-users) Microsoft 365 라이선스를 할당합니다. 그런 다음, 매핑하려는 모든 팀에 계정을 팀 소유자로 추가합니다. Shifts 커넥터는 Blue Yonder WFM에서 Shifts 변경 내용을 동기화할 때 이 계정을 사용합니다.

    이 용도로 특별히 계정을 만들고 사용자 계정을 사용하지 않는 것이 좋습니다.