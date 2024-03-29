---
title: 전화 번호 서비스 팀에 문의
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: conceptual
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.voice.tnsservicedesk
- ms.teamsadmincenter.voice.contacttnssupport
- Calling Plans
ROBOTS: NOINDEX, NOFOLLOW
description: 조직의 전화 번호 또는 포트(전송) 번호를 받으면 TNS 서비스 데스크에서 도움과 지원을 받아야 할 수 있습니다.
ms.openlocfilehash: 9984775a05458592fe1789c0dd8b173a08783220
ms.sourcegitcommit: fd56fb16ed60b027d3f8de96711d143825f9c184
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/20/2023
ms.locfileid: "69835561"
---
# <a name="telephone-number-services-tns---service-desk"></a>TNS(전화 번호 서비스) - Service Desk

> [!NOTE]
> 2021년 7월 22일부터 TNS 서비스 데스크에 연결할 이전 전자 메일 시스템이 사용 중지되었습니다.

새로운 전화 번호 서비스 **[센터에서](https://pstnsd.powerappsportals.com)** TNS(전화 번호 서비스) 서비스 데스크와 상호 작용하는 새로운 프로세스가 있습니다. 이제 Teams 관리 센터와 통합된 단일 위치에서 티켓을 열고 티켓을 보고 통신을 추적할 수 있습니다. 해당 작업은 다음 섹션에서 자세히 설명합니다.


- **[새 사례 만들기](#create-a-new-case)** – 새 요청 또는 일반 문의를 제출합니다.

- **[기존 사례 보기](#view-and-manage-existing-cases)** – 기존 사례를 추적하고 모니터링합니다.

- **[내 회사 사례 보기](#view-and-manage-existing-cases)** – 회사의 기존 사례를 추적하고 모니터링합니다. 동료가 사례를 연 경우 이 보기에서 해당 사례를 찾아볼 수 있습니다.

- **[피드백 제공](#view-and-manage-existing-cases)** – 피드백을 당사와 공유하세요.

## <a name="create-a-new-case"></a>새 사례 만들기

> [!NOTE]
> 동일한 테넌트에서만 사례를 만들 수 있습니다. 예를 들어 @fabrikam.com 사용자는 @contoso.com 대신 사례를 만들 수 없습니다.

새 사례를 만들려면 다음 단계를 수행합니다.

1. 다음 위치 중 하나에서 **새 사례 만들기** 를 선택합니다.

   - **전화 번호 서비스 센터** 홈페이지의 페이지 위쪽 또는 아래쪽 타일에 있습니다.

   - **내 기존 사례 보기** 페이지에서

   - **내 회사 사례 보기** 페이지에서

2. [다음 섹션](#provide-case-details)에 설명된 대로 사례 세부 정보를 제공합니다.

3. 모든 값을 입력한 후 **제출** 을 선택합니다. 사례 번호를 볼 수 있는 새 화면이 표시됩니다.

### <a name="provide-case-details"></a>사례 세부 정보 제공

사례 세부 정보를 이해하려면 Microsoft에 다음 정보가 필요합니다.

- [사례 범주](#case-category)
- [국가 또는 지역](#country-or-region)
- [사례 유형](#case-type)
- [사례 유형](#case-title)
- [알림에 대한 추가 연락처](#additional-contacts-for-notifications)
- [설명](#description)
- [추가 지원 문서](#additional-supporting-documents)

#### <a name="case-category"></a>사례 범주

사례에는 다음 두 가지 범주 중 하나가 있을 수 있습니다.

- **새 요청 제출**- 새 요청을 제출하려면 이 옵션을 선택합니다. 예를 들어 포트 요청을 제출하거나 Microsoft에서 전화 번호를 구입하려고 합니다.

- **일반 문의** - 요청을 결정하는 데 도움이 되는 질문이 있는 경우 이 옵션을 선택합니다. 예를 들어 무선 번호를 Microsoft에 포팅할 수 있는지, Microsoft에서 수신자 부담 번호를 지원하는지 여부를 알아야 합니다.

#### <a name="country-or-region"></a>국가 또는 지역

이 사례를 제출하는 국가/지역을 선택합니다. 여러 국가에 대한 요청이 있는 경우 국가/지역당 하나의 사례를 열어야 합니다.

#### <a name="case-type"></a>사례 유형

사례 유형은 다음 항목 중 하나일 수 있습니다.

- **사용자 지정 통화 이름(미국만 해당)** - Microsoft 전화 번호에 사용자 지정 통화 이름을 설정합니다. 미국 전화 번호에만 적용됩니다.

  - **설정할 사용자 지정 호출 이름(15자만 해당)** - 설정하려는 사용자 지정 호출 이름입니다. 이름은 최대 15자로 제한됩니다.

  - **전화 번호 목록** - 사용자 지정 통화 이름 값을 설정할 전화 번호 목록입니다. 전화 번호 목록을 사용하여 csv 파일을 업로드합니다.

- **내부 테넌트 포트** – 한 테넌트에서 다른 테넌트로 전화 번호를 이동합니다. 예를 들어 Microsoft 내에 서로 다른 두 테넌트가 있고 전화 번호를 한 테넌트에서 다른 테넌트로 이동하려고 합니다.

  - **원본 테넌트 도메인 이름** - 전화 번호를 다른 테넌트로 이동하려는 테넌트입니다.

  - **원본테넌트 고유 식별자** - 원본 테넌트용 테넌트 ID입니다. 이 필드는 선택 사항입니다.

  - **대상 테넌트 도메인 이름** - 전화 번호를 이동할 테넌트입니다.

  - **대상 테넌트 고유 식별자** - 대상 테넌트용 테넌트 ID입니다. 이 필드는 선택 사항입니다.

  - **요청된 날짜 시간*** - 번호를 원본 테넌트에서 대상 테넌트로 이동하려는 날짜 및 시간입니다. 날짜 및 시간을 참조하세요.

  - **전화 번호 목록** - 원본 테넌트에서 대상 테넌트로 이동하려는 전화 번호 목록입니다. 전화 번호 목록을 사용하여 csv 파일을 업로드합니다.

- **인벤토리 형식 변경** – 전화 번호 유형을 변경합니다. 예를 들어 Microsoft 구독자 번호를 서비스 번호로 변경하려고 합니다. Microsoft에서 지원하는 전화 번호 유형에 대한 자세한 내용은 [전화 번호 유형](../different-kinds-of-phone-numbers-used-for-calling-plans.md)을 참조하세요.

  - **변환 대상** - 번호를 사용자 번호 또는 서비스 번호로 변환하려면 선택합니다.

  - **기본 날짜/시간*** - 숫자의 인벤토리 유형을 변경할 날짜 및 시간입니다. 자세한 내용은 날짜 및 시간을 참조하세요.

  - **확인란 – 인벤토리 유형을 업데이트하려면 내 전화 번호를 할당 취소해야 한다는 것을 이해합니다** . Microsoft는 테넌트 내 전화 번호가 할당되지 않은 한 전화 번호 유형 변경 요청을 처리할 수 없습니다. 이후 날짜에 대해 이 변경을 요청하는 경우 요청된 날짜 및 시간 전에 번호 할당을 취소해야 합니다.

  - **전화 번호 목록** - 유형을 변경할 전화 번호 목록입니다. 전화 번호 목록을 사용하여 csv 파일을 업로드합니다.

- **새 TN 취득** – Microsoft에서 새 전화 번호를 구입하세요.

  - **번호 유형** - 숫자의 유형을 선택합니다. [전화 번호 유형](../different-kinds-of-phone-numbers-used-for-calling-plans.md)을 참조하세요.

  - **Teams 관리 센터 포털에서 전화 번호를 구하려고** 했습니다. Microsoft Teams 관리 센터에서 이러한 전화 번호를 구입하려고 했나요?

  - **필요한 전화 번호 수량** - 구입하려는 전화 번호 수입니다.

  - **시/도** - 원하는 전화 번호의 국가/지역 내의 시/도입니다.

  - **시** - 원하는 전화 번호의 시/도 내 도시입니다.

  - **사무실 주소** - 특정 국가에만 해당됩니다. 사무실의 사이트 주소입니다.

  - **디렉터리 목록** - 특정 국가에만 해당됩니다. 전화 번호로 회사 정보를 게시하시겠습니까?

- **포트 인** – 현재 서비스 공급자의 기존 전화 번호를 Microsoft로 포팅합니다.

  - **포트 순서 이름 지정** - 포트 요청에 대해 기억하기 쉬운 이름을 제공합니다.

  - **요청된 포팅 날짜/시간*** - 번호를 Microsoft로 포팅하려는 날짜/시간입니다. 현재 번호 소유자가 먼저 포트 요청을 승인해야 하기 때문에 이는 보장된 포팅 날짜가 아닙니다. 날짜 및 시간을 참조하세요.

  - **포팅 번호 목록** - Microsoft로 포팅하려는 전화 번호 목록입니다. 전화 번호 목록을 사용하여 csv 파일을 업로드합니다.

  - **LOA(권한 부여)** - 여기에 서명되고 입력된 LOA를 첨부합니다. Microsoft는 LOA 없이 포트 요청을 처리할 수 없습니다.

    > [!NOTE]
    > 기존 전화 번호 및 추가 설명서 요구 사항을 포팅/전송하는 LOA에 대한 자세한 내용은 [통화 플랜에 대한 전화 번호 관리를 참조하세요](/microsoftteams/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization).
    >
    >사용자를 위해 999개 이하의 전화 번호를 포트/전송하려면 추가 처리를 위해 완료되고 서명된 LOA를 Microsoft Teams 관리 센터에 업로드합니다.
    >
    > 999개 이상의 전화 번호를 포팅/전송하거나 Microsoft Teams 관리 센터에서 포팅 프로세스에 문제가 발생하는 경우 해당 지역의 TNS 서비스 데스크에 [포트 주문을 수동으로 제출할](/microsoftteams/phone-number-calling-plans/manually-submit-port-order) 수 있습니다.

- **주소 업데이트** – 긴급 전화 주소를 업데이트합니다. 이 필드는 선택한 국가에만 적용됩니다.

  - **위치 ID** - 긴급 주소의 위치 ID입니다.

  - **전화 번호 목록** - 긴급 주소를 변경할 전화 번호 목록입니다(설명 필드에 원하는 주소를 입력). 전화 번호 목록을 사용하여 csv 파일을 업로드합니다.

**날짜 및 시간** 국가: 프랑스, 날짜: 2021/8/14, 시간: 오전 10시를 선택하면 요청이 2021/8/14 오전 10시에 실행됩니다. 프랑스 시간

#### <a name="case-title"></a>사례 제목

질문을 요약한 제목을 입력합니다.

#### <a name="additional-contacts-for-notifications"></a>알림에 대한 추가 연락처

Microsoft로부터 자동 상태 통지를 받을 사용자 목록을 입력합니다.
예를 들어, 포트인 순서를 지정하려는 경우 자신과 다른 두 명의 동료가 자동 상태 통지를 받도록 할 수 있습니다. **알림 전자 메일** 섹션에서 동료의 전자 메일 주소를 제공합니다. 이 정보는 선택 사항입니다.

#### <a name="description"></a>설명

달성하려는 작업을 설명하고 Microsoft TNS(전화 번호 서비스) 서비스 데스크에 대한 질문을 나열합니다.

#### <a name="additional-supporting-documents"></a>추가 지원 문서

사례에 대한 추가 문서를 업로드합니다.

## <a name="view-and-manage-existing-cases"></a>기존 사례 보기 및 관리

**기존 사례 보기** 를 선택하고 사례 번호를 선택하여 사례를 볼 수 있습니다. 사례 번호를 선택하면 사례 세부 정보로 리디렉션됩니다. (**회사 사례 보기** 를 선택하여 회사 사례를 볼 수 있습니다.)  또는 다음 방법으로 확인할 수 있습니다.

- **사례 열기**, **모든 사례** 또는 **종료된 사례** 를 선택하여 **사례를 필터링** 합니다.

- 기존 케이스를 열고 아래로 스크롤한 다음 **메모 추가** 를 선택하여 사례와 관련하여 **TNS 서비스 데스크와 통신** 합니다. 새 창이 나타납니다. 메모 상자에 메시지를 입력합니다. 지원 문서를 첨부한 다음(사용 가능한 경우) **제출** 을 선택합니다.

  **TNS 서비스 데스크** 의 응답은 동일한 타임라인 아래에 표시됩니다. 사례에 업데이트가 있으면 업데이트에 대한 자동 전자 메일 알림을 받게 됩니다.

- 기존 사례로 이동하여 아래로 스크롤하고 **사례 취소** 를 선택하여 **사례를 취소합니다**. 드롭다운 목록에서 취소 이유를 선택한 다음 **취소** 를 선택합니다.

- **사례 해결** - 요청이 완료된 경우, 기존 사례로 이동하여 아래로 스크롤한 후 **사례 해결** 을 선택하여 사례를 해결할 수 있습니다. 이제 사례가 **해결됨 – 문제 해결됨** 으로 표시될 **종료** 를 선택합니다.

## <a name="related-topics-and-additional-resources"></a>관련 항목 및 추가 리소스

- 번호 설정 및 구성, 라이선스, 수수료 또는 청구와 관련된 지원은 [비즈니스 제품 지원 연락처 - 관리 도움말](/microsoft-365/admin/contact-support-for-business-products?tabs=online)을 참조하세요.

- 국가/지역에서 사용할 수 있는 통화 요금제에 대한 자세한 내용은 [오디오 회의 및 통화 요금제에 사용할 수 있는 국가 및 지역](../country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)을 참조하세요.

- 조직에 적합한 전화 번호 유형에 대한 자세한 내용은 [다양한 종류의 전화 번호를 참조하세요](../different-kinds-of-phone-numbers-used-for-calling-plans.md).

- 조직의 전화 번호 관리에 대한 자세한 내용은 [조직의 전화 번호 관리](manage-phone-numbers-for-your-organization.md)를 참조하세요.

- 비상 통화 약관에 대한 자세한 내용은 [비상 통화 약관](../emergency-calling-terms-and-conditions.md)을 참조하세요.
