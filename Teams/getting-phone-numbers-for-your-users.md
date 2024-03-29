---
title: 사용자의 전화 번호 가져오기
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.assetid: aa2ec464-3481-4bbb-8c14-e13e18093df5
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
- highpri
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Calling Plans
description: Teams에 대한 새 번호, 포트 또는 이전 번호를 가져오는 방법과 변경 내용을 사용자에게 표시하는 방법을 알아봅니다.
ms.openlocfilehash: d92d48f95e620767148d3917a78d1e72c87f0645
ms.sourcegitcommit: fd56fb16ed60b027d3f8de96711d143825f9c184
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/20/2023
ms.locfileid: "69835491"
---
# <a name="getting-phone-numbers-for-your-users"></a>사용자의 전화 번호 가져오기

조직에서 전화를 걸고 받기 위해 사용자를 설정하려면 먼저 전화 번호를 받아야 합니다.
  
사용자 번호를 가져오는 방법에는 세 가지가 있습니다.

- **Microsoft Teams 관리 센터를 사용합니다.** 일부 국가 및 지역의 경우 Microsoft Teams 관리 센터를 사용하여 사용자의 번호를 가져올 수 있습니다. [사용자의 새 전화 번호 가져오기를 참조하세요](#get-new-phone-numbers-for-your-users).

- **기존 서비스 전화 번호 포팅하기** 현재 서비스 공급자 또는 전화 통신 사업자에서 기존 번호를 포팅하거나 전송할 수 있습니다. 자세한 내용은 [Teams로 전화 번호 전송](./phone-number-calling-plans/transfer-phone-numbers-to-teams.md) 또는 [조직의 전화 번호 관리를 참조하세요](/microsoftteams/manage-phone-numbers-for-your-organization).  
  
- **새 전화 번호를 위한 요청 양식 사용하기** 경우에 따라(국가 또는 지역에 따라) Microsoft Teams 관리 센터를 사용하여 새 전화 번호를 가져올 수 없거나 특정 전화 번호 또는 지역 코드가 필요합니다. 자세한 내용은 [조직의 전화 번호 관리를 참조하세요](/microsoftteams/manage-phone-numbers-for-your-organization).
  
> [!NOTE]
> 조직의 전화 번호를 설정하는 데 도움이 필요한 경우 [비즈니스 제품 지원 연락처 - 관리 도움말에 문의](/microsoft-365/admin/contact-support-for-business-products)하세요.

## <a name="get-new-phone-numbers-for-your-users"></a>사용자의 새 전화 번호 가져오기

**Microsoft Teams 관리 센터 사용**

이러한 정책을 관리하려면 전역 관리자 또는 Teams 서비스 관리자여야 합니다. 관리 역할 및 사용 권한 가져오기에 대한 내용은 [Teams 관리자 역할 사용](./using-admin-roles.md)을 참조하세요.

1. [Microsoft Teams 관리 센터에](https://go.microsoft.com/fwlink/p/?linkid=2066851) 로그인합니다.

2. 왼쪽 탐색 영역에서 **음성** > **전화 번호** 로 이동한 다음 **추가** 를 선택합니다.

3. 주문의 이름을 입력하고 설명을 추가합니다.

4. 위치 및 수량 페이지에서 다음을 수행합니다.
    1. **국가 또는 지역에서** 국가 또는 지역을 선택합니다.
    2. **번호 유형** 에서 **사용자(구독자)** 를 선택합니다.
    3. **위치** 아래에서 위치를 선택합니다. 새 위치를 만들어야 하는 경우 **위치 추가를** 선택합니다.
    4. **영역 코드** 에서 영역 코드를 선택합니다.
    5. **수량** 에서 조직에 대해 원하는 숫자 수를 입력한 다음 **, 다음** 을 선택하여 숫자를 선택합니다.

5. 원하는 숫자를 선택합니다. 전화 번호를 선택하고 주문을 하는 데 10분이 걸립니다. 10분 이상 걸리면 전화 번호가 숫자 풀로 반환됩니다.

6. 주문을 할 준비가 되면 **주문 배치** 를 선택합니다.

    > [!IMPORTANT]
    > 사용자(구독자)의 전화 번호 수는 할당한 **국내 통화 플랜** 및 **국제 통화 플랜** 라이선스의 총 수에 1.1과 10개의 추가 전화 번호를 곱한 것과 같습니다. 예를 들어 국내 통화 플랜 및/또는 국제 통화 플랜을 사용하는 사용자가 총 50명인 경우 **65** 개의 전화 번호 **(50 x 1.1 + 10)** 를 획득할 수 있습니다. 종량제 통화 플랜이 있는 경우 할당된 라이선스당 1 전화 번호만 획득할 수 있습니다.
    >
    > 자세한 내용은 [몇 개의 전화 번호를 받을 수 있나요?](./how-many-phone-numbers-can-you-get.md)를 참조하세요. 이보다 더 많은 전화 번호를 받아야 하는 경우 [비즈니스 제품 지원 담당자 - 관리 도움말에 문의하세요](/microsoft-365/admin/contact-support-for-business-products).
  
## <a name="port-or-transfer-phone-numbers-from-your-service-provider-or-phone-carrier"></a>서비스 공급자 또는 전화 사업자의 전화 번호 포트 또는 전송
  
- 사용자에게 999개 이하의 전화 번호가 필요한 경우 Microsoft Teams 관리 센터에서 포팅 마법사를 사용합니다. [Teams로 전화 번호 전송의](./phone-number-calling-plans/transfer-phone-numbers-to-teams.md) 단계를 수행합니다. 이 프로세스에 대한 지원이 필요한 경우 [포트 주문을 수동으로 제출](phone-number-calling-plans/manually-submit-port-order.md) 하거나 [조직의 전화 번호 관리를](/microsoftteams/manage-phone-numbers-for-your-organization) 참조하여 올바른 LOA(권한 부여 편지)를 다운로드할 수 있습니다.

- 999개 이상의 전화 번호를 이식해야 하는 경우 [포트 주문을 수동으로 제출](phone-number-calling-plans/manually-submit-port-order.md) 하거나 [조직의 전화 번호 관리를](/microsoftteams/manage-phone-numbers-for-your-organization) 참조하여 올바른 LOA(권한 부여서)를 다운로드할 수 있습니다. LOA 문서를 완료하고 서명한 다음 해당 지역의 [TNS 서비스 데스크](manage-phone-numbers-for-your-organization/contact-tns-service-desk.md) 에 문의하세요.

> [!NOTE]
> 기존 전화 번호 및 추가 설명서 요구 사항을 포팅/전송하는 LOA에 대한 자세한 내용은 [통화 플랜에 대한 전화 번호 관리를 참조하세요](/microsoftteams/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization).
>
>사용자를 위해 999개 이하의 전화 번호를 포트/전송하려면 추가 처리를 위해 완료되고 서명된 LOA를 Microsoft Teams 관리 센터에 업로드합니다. 
>
> 999개 이상의 전화 번호를 포팅/전송하거나 Microsoft Teams 관리 센터에서 포팅 프로세스에 문제가 발생하는 경우 해당 지역의 TNS 서비스 데스크에 [포트 주문을 수동으로 제출할](/microsoftteams/phone-number-calling-plans/manually-submit-port-order) 수 있습니다.

## <a name="view-the-phone-numbers-for-your-organization"></a>조직의 전화 번호 보기

**Microsoft Teams 관리 센터 사용**

관리 센터의 왼쪽 탐색 영역에서 **음성** > **전화 번호** 로 이동하여 위치, 번호 유형 및 상태 정보를 포함하여 조직의 번호를 확인합니다.
  
## <a name="assign-phone-numbers-to-users"></a>사용자에게 전화번호 할당

전화 번호를 받은 후에는 각 사용자에게 번호를 할당해야 합니다. 자세한 내용은 [사용자의 전화 번호 할당, 변경 또는 제거를 참조하세요](./assign-change-or-remove-a-phone-number-for-a-user.md).

이 비디오에서는 사용자에게 전화 번호를 할당하는 단계를 보여줍니다.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE54mbS?autoplay=false]

## <a name="related-articles"></a>관련 기사

[전화 번호 전송 자주 묻는 질문](./phone-number-calling-plans/port-order-overview.md)

[통화 플랜에 사용되는 다양한 종류의 전화 번호](./different-kinds-of-phone-numbers-used-for-calling-plans.md)

[조직의 전화 번호 관리](/microsoftteams/manage-phone-numbers-for-your-organization)

[긴급 통화 사용 약관](./emergency-calling-terms-and-conditions.md)

[긴급 통화 고지 사항 레이블](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)
