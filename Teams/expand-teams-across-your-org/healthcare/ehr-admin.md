---
title: Teams 가상 약속 - Epic EHR에 통합
author: LanaChin
ms.author: v-lanachin
manager: samanro
audience: ITPro
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
- microsoftcloud-healthcare
- m365solution-healthcare
- m365solution-scenario
appliesto:
- Microsoft Teams
ms.reviewer: ansantam
description: Teams EHR 커넥터를 통합하여 조직의 의료 공급자가 Epic EHR 시스템에서 직접 Teams 환자 또는 다른 공급자와 가상 약속을 수행할 수 있도록 하는 방법을 알아봅니다.
ms.openlocfilehash: baef8aeda05413ce2f307a4bbea7259490ecfb83
ms.sourcegitcommit: 68162a8c9dee9a27af596353baabeda9b8fa64f3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2022
ms.locfileid: "64853059"
---
# <a name="virtual-appointments-with-teams---integration-into-epic-ehr"></a>Teams 가상 약속 - Epic EHR에 통합

Microsoft Teams EHR(전자 건강 기록) 커넥터를 사용하면 임상의가 에픽 EHR 시스템에서 직접 Microsoft Teams 있는 다른 공급자와 가상 환자 약속 또는 상담을 쉽게 시작할 수 있습니다. Microsoft 365 클라우드에서 구축된 Teams HIPAA, HITECH 인증 등을 준수하는 단일 허브에서 채팅, 비디오, 음성 및 의료 도구와의 간단하고 안전한 공동 작업 및 통신을 지원합니다.

Teams 통신 및 공동 작업 플랫폼을 사용하면 임상의가 조각난 시스템의 혼란을 쉽게 끊어 최상의 치료를 제공하는 데 집중할 수 있습니다. Teams EHR 커넥터를 사용하면 다음을 수행할 수 있습니다.

- 통합 임상 워크플로를 사용하여 Epic EHR 시스템에서 Teams 가상 약속을 시작합니다.
- 환자가 환자 포털 내에서 또는 SMS를 통해 Teams 가상 약속에 참여할 수 있도록 합니다.
- 다중 참가자, 그룹 방문 및 인터프리터 서비스를 비롯한 다른 시나리오를 지원합니다.
- 참석자가 연결하고, 연결을 끊고, 자동 감사 및 레코드 유지를 사용하도록 설정할 때 기록할 Teams 가상 약속에 대한 메타데이터를 EHR 시스템에 다시 씁니다.
- EHR 연결 약속에 대한 사용량 데이터 보고서 및 사용자 지정 가능한 통화 품질 정보를 봅니다.

EHR 포털에서 가상 약속을 관리하는 방법에 대한 개요는 이 비디오를 확인하세요.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4HAtn]

이 문서에서는 의료 조직의 Epic 플랫폼과 통합하도록 Teams EHR 커넥터를 설정하고 구성하는 방법을 설명합니다. 또한 Epic EHR 시스템의 Teams 가상 약속 환경에 대한 개요를 제공합니다.

## <a name="before-you-begin"></a>시작하기 전에

시작하기 전에 통합을 준비하기 위해 몇 가지 작업을 수행해야 합니다.

### <a name="get-familiar-with-the-integration-process"></a>통합 프로세스 숙지

전체 통합 프로세스를 이해하려면 다음 정보를 검토합니다.

:::image type="content" source="media/ehr-connector-epic-flow.png" alt-text="전체 통합 프로세스의 단계를 요약한 이미지입니다.":::

||||||
|---------|---------|---------|---------|---------|
|**작업**: [Teams 앱에 대한 액세스를 요청합니다](#request-access-to-the-teams-app). <br> **결과**: 테스트에 대한 권한을 조직에 부여합니다.|**작업**: 퍼블릭 및 프라이빗 키 인증서를 만들고 Epic에 업로드합니다. <br> **결과**: 에픽은 공개 키 인증서를 동기화합니다.|**작업**: EHR 커넥터 구성 포털에서 구성 단계를 완료합니다. <br> **결과**: 에픽 구성에 대한 FDI 레코드를 받습니다.| **작업**: Epic 기술 전문가와 협력하여 에픽에서 FDI 레코드를 구성합니다.<br> **결과**: 구성이 완료되었습니다. 테스트할 준비가 완료되었습니다.|**작업**: 테스트 환경에서 테스트를 완료합니다.<br> **결과**: 흐름의 전체 유효성 검사 및 프로덕션으로 전환 결정.|

### <a name="request-access-to-the-teams-app"></a>Teams 앱에 대한 액세스 요청

Teams 앱에 대한 액세스를 요청해야 합니다.

1. [에픽 앱 오차드 마켓플레이스에서 Teams 앱을](https://apporchard.epic.com/Gallery?id=6153) 다운로드하도록 요청합니다. 이렇게 하면 Epic에서 Microsoft EHR 커넥터 팀에 대한 요청이 트리거됩니다.
1. 요청을 수행한 후 에픽 기술 담당자의 조직 이름, 테넌트 ID 및 전자 메일 주소를 사용하여 [TeamsForHealthcare@service.microsoft.com](mailto:teamsforhealthcare@service.microsoft.com) 이메일을 보냅니다.
1. Microsoft EHR 커넥터 팀은 사용 확인을 통해 전자 메일에 응답합니다.

### <a name="review-the-epic-microsoft-teams-telehealth-integration-guide"></a>Epic-Microsoft Teams Telehealth 통합 가이드 검토

Epic 기술 전문가와 함께 [Epic-Microsoft 팀 원격 상태 통합 가이드](https://galaxy.epic.com/Search/GetFile?Url=1!68!100!100100357)를 검토해 보세요. 모든 필수 구성 요소가 충족되는지 확인합니다.

## <a name="prerequisites"></a>필수 구성 요소

- Microsoft Cloud for Healthcare 대한 활성 구독 또는 Microsoft Teams EHR 커넥터 독립 실행형 제품에 대한 구독(프로덕션 EHR 환경에서 테스트할 때만 적용됨).
- 에픽 버전 2018년 11월 이상
- 사용자에게는 Teams 모임을 포함하는 적절한 Microsoft 365 또는 Office 365 라이선스가 있습니다.
- Teams 의료 조직에서 채택되고 사용됩니다.
- 시스템은 Teams 대한 모든 [소프트웨어 및 브라우저 요구 사항을 충족합니다](../../hardware-requirements-for-the-teams-app.md).

> [!IMPORTANT]
> 통합을 진행하기 전에 사전 통합 단계를 완료하고 모든 필수 구성 요소가 충족되는지 확인합니다.

통합 단계는 조직의 다음 사용자가 수행합니다.

- **Microsoft 365 전역 관리자**: 통합을 담당하는 주 사용자입니다. 관리자는 커넥터를 구성하고, SMS(필요한 경우)를 사용하도록 설정하고, 구성을 승인할 Epic 고객 분석가를 추가합니다.
- **Epic 고객 분석가**: Epic에 로그인 자격 증명이 있는 조직의 사용자입니다. 관리자가 입력한 구성 설정을 승인하고 구성 레코드를 Epic에 제공합니다.

Microsoft 365 관리자와 에픽 고객 분석가도 같은 사람이 될 수 있습니다.

## <a name="set-up-the-teams-ehr-connector"></a>Teams EHR 커넥터 설정

커넥터를 설정하려면 다음이 필요합니다.

- [EHR 커넥터 구성 포털 시작](#launch-the-ehr-connector-configuration-portal)
- [구성 정보 입력](#enter-configuration-information)
- [SMS 알림 사용(선택 사항)](#enable-sms-notifications-optional)
- [구성 승인 또는 보기](#approve-or-view-the-configuration)
- [구성 검토 및 완료](#review-and-finish-the-configuration)

### <a name="launch-the-ehr-connector-configuration-portal"></a>EHR 커넥터 구성 포털 시작

시작하려면 Microsoft 365 관리자가 [EHR 커넥터 구성 포털](https://ehrconnector.teams.microsoft.com)을 시작하고 Microsoft 365 자격 증명을 사용하여 로그인합니다.

Microsoft 365 관리자는 통합을 테스트하도록 단일 조직 또는 여러 조직을 구성할 수 있습니다. 구성 포털에서 테스트 및 프로덕션 URL을 구성합니다. 프로덕션으로 이동하기 전에 Epic 테스트 환경에서 통합을 테스트해야 합니다.

> [!NOTE]
> Microsoft 365 관리자 및 Epic 고객 분석가는 구성 포털에서 통합 단계를 완료해야 합니다. 에픽 구성 단계는 조직에 할당된 에픽 기술 전문가에게 문의하세요.

### <a name="enter-configuration-information"></a>구성 정보 입력

다음으로 통합을 설정하기 위해 Microsoft 365 관리자는 다음을 수행합니다.

1. Epic 기술 전문가의 FHIR(Fast Health 상호 운용성 리소스) 기본 URL을 추가하고 환경을 지정합니다. 조직의 요구 사항 및 테스트하려는 환경에 따라 필요한 만큼의 FHIR 기본 URL을 구성합니다.

    - FHIR 기본 URL은 서버 FHIR API 엔드포인트에 해당하는 정적 주소입니다. 예제 URL은 `https://lamnahealthcare.org/fihr/auth/connect-ocurprd-oauth/api/FHDST`입니다.

    - 테스트 및 프로덕션 환경에 대한 통합을 설정할 수 있습니다. 초기 설정의 경우 프로덕션 환경으로 이동하기 전에 테스트 환경에서 커넥터를 구성하는 것이 좋습니다.

1. 이후 단계에서 구성을 승인할 Epic 고객 분석가의 사용자 이름을 추가합니다.

    :::image type="content" source="media/ehr-connector-epic-configure.png" alt-text="추가되는 승인자를 보여 주는 구성 페이지의 스크린샷." lightbox="media/ehr-connector-epic-configure.png":::

### <a name="enable-sms-notifications-optional"></a>SMS 알림 사용(선택 사항)

> [!NOTE]
> SMS 알림은 현재 미국만 사용할 수 있습니다. 향후 Teams 릴리스의 다른 지역에서 이 기능을 사용할 수 있도록 노력하고 있으며 사용 가능한 경우 이 문서를 업데이트할 예정입니다.

조직에서 Microsoft가 환자에 대한 SMS 알림을 관리하도록 하려는 경우 이 단계를 완료합니다. SMS 알림을 사용하도록 설정하면 환자는 예약된 약속에 대한 확인 및 미리 알림 메시지를 받게 됩니다.

SMS 알림을 사용하도록 설정하기 위해 Microsoft 365 관리자는 다음을 수행합니다.

1. SMS 알림 페이지에서 다음을 수행할 두 동의 확인란을 모두 선택합니다.

    - Microsoft가 조직을 대신하여 환자에게 SMS 알림을 보낼 수 있도록 허용합니다.
    - 참석자가 SMS 메시지를 보내고 받는 데 동의했는지 확인합니다.
    
    :::image type="content" source="media/ehr-connector-epic-sms-notifications.png" alt-text="동의 확인란과 전화 번호를 생성하는 옵션을 보여 주는 SMS 알림 페이지의 스크린샷." lightbox="media/ehr-connector-epic-sms-notifications.png":::

1. **전화 번호** 아래에서 **새 전화 번호 생성을** 선택하여 조직의 전화 번호를 생성합니다. 이렇게 하면 새 전화 번호를 요청하고 생성하는 프로세스가 시작됩니다. 이 프로세스를 완료하는 데 최대 2분이 걸릴 수 있습니다.

    전화 번호가 생성되면 화면에 표시됩니다. 이 번호는 환자에게 SMS 확인 및 미리 알림을 보내는 데 사용됩니다. 숫자가 프로비전되었지만 아직 FHIR 기본 URL에 연결되지 않았습니다. 다음 단계에서 이 작업을 수행합니다.

    :::image type="content" source="media/ehr-connector-epic-phone-number.png" alt-text="생성된 전화 번호의 예를 보여 주는 스크린샷." lightbox="media/ehr-connector-epic-phone-number.png":::

    **완료****를 선택한 다음** 다음을 선택합니다.

1. 전화 번호를 FHIR 기본 URL에 연결하려면 **SMS 구성** 섹션의 **전화 번호** 아래에서 번호를 선택합니다. SMS 알림을 사용하도록 설정하려는 각 FHIR 기본 URL에 대해 이 작업을 수행합니다.

    :::image type="content" source="media/ehr-connector-epic-link-phone-number.png" alt-text="전화 번호를 FHIR 기본 URL에 연결하는 방법을 보여 주는 스크린샷" lightbox="media/ehr-connector-epic-link-phone-number.png":::

    커넥터를 처음 구성하는 경우 이전 단계에서 입력한 FHIR 기본 URL이 표시됩니다. 동일한 전화 번호를 여러 FHIR 기본 URL에 연결할 수 있습니다. 즉, 환자는 다른 조직 및/또는 부서에 대해 동일한 전화 번호에서 SMS 알림을 받습니다.

1. 각 FHIR 기본 URL 옆에 있는 **SMS 설정을** 선택하여 환자에게 보낼 SMS 알림 유형을 설정합니다.

    :::image type="content" source="media/ehr-connector-epic-sms-setup.png" alt-text="SMS 설정 설정을 보여 주는 스크린샷." lightbox="media/ehr-connector-epic-sms-setup.png":::

    - **확인 SMS**: EHR 시스템에서 약속이 예약, 업데이트 또는 취소될 때 환자에게 알림이 전송됩니다.
    - **미리 알림 SMS**: 지정한 시간 간격 및 예약된 시간에 따라 환자에게 알림이 전송됩니다.

    **저장** 을 선택합니다.

1. **업로드 인증서** 를 선택하여 공개 키 인증서를 업로드합니다. 각 환경에 대해 Base64로 인코딩된(공개 키에만 해당) .cer 인증서를 업로드해야 합니다.

    SMS 알림을 보내기 위한 약속 정보를 받으려면 공개 키 인증서가 필요합니다. 들어오는 정보가 유효한 원본에서 온 것인지 확인하려면 인증서가 필요합니다.

    커넥터를 사용하여 SMS 미리 알림을 보내면 Epic에서 약속을 만들 때 Epic에서 HL7v2 페이로드로 환자의 전화 번호를 보냅니다. 이러한 숫자는 조직의 지리에 있는 각 약속에 대해 저장되며 약속이 이루어질 때까지 유지됩니다. HL7v2 메시지를 구성하는 방법에 대한 자세한 내용은 [Epic-Microsoft Teams Telehealth 통합 가이드](https://galaxy.epic.com/Search/GetFile?Url=1!68!100!100100357)를 참조하세요.

    **다음** 을 선택합니다.

> [!NOTE]
> 언제든지 Microsoft 365 관리자가 SMS 설정을 업데이트할 수 있습니다. 설정을 변경하면 SMS 서비스가 중단될 수 있습니다. SMS 보고서를 보는 방법에 대한 자세한 내용은 [Teams EHR 커넥터 관리자 보고서를 참조하세요](ehr-admin-reports.md).

### <a name="approve-or-view-the-configuration"></a>구성 승인 또는 보기

승인자로 추가된 조직의 Epic 고객 분석가가 [EHR 커넥터 구성 포털](https://ehrconnector.teams.microsoft.com)을 시작하고 Microsoft 365 자격 증명을 사용하여 로그인합니다. 유효성 검사가 성공하면 승인자에게 Epic 자격 증명을 사용하여 로그인하여 Epic 조직의 유효성을 검사하라는 메시지가 표시됩니다.

> [!Note]
> Microsoft 365 관리자와 에픽 고객 분석가가 동일한 사용자인 경우 액세스의 유효성을 검사하려면 여전히 Epic에 로그인해야 합니다. Epic 로그인은 FHIR 기본 URL의 유효성을 검사하는 데만 사용됩니다. Microsoft는 이 로그인을 사용하여 자격 증명을 저장하거나 EHR 데이터에 액세스하지 않습니다.

:::image type="content" source="media/ehr-connector-epic-login-approve.png" alt-text="로그인 및 승인 옵션을 보여 주는 구성 승인 또는 보기 페이지의 스크린샷." lightbox="media/ehr-connector-epic-login-approve.png":::

Epic에 성공적으로 로그인한 후 Epic 고객 분석가가 구성을 승인 **해야 합니다** . 구성이 올바르지 않으면 Microsoft 365 관리자가 구성 포털에 로그인하고 설정을 변경할 수 있습니다.

:::image type="content" source="media/ehr-connector-epic-approve.png" alt-text="승인 옵션을 보여 주는 구성 승인 또는 보기 페이지의 스크린샷." lightbox="media/ehr-connector-epic-approve.png":::

### <a name="review-and-finish-the-configuration"></a>구성 검토 및 완료

Epic 관리자가 구성 정보를 승인하면 환자 및 공급자 출시에 대한 통합 레코드가 표시됩니다. 통합 레코드는 다음과 같습니다.

- 환자 및 공급자 레코드
- 직접 SMS 레코드
- SMS 구성 레코드
- 디바이스 테스트 구성 레코드

Epic 고객 분석가는 Epic에서 가상 약속 구성을 완료하려면 이러한 레코드를 Epic에 제공해야 합니다. 자세한 내용은 [Epic-Microsoft Teams Telehealth 통합 가이드](https://galaxy.epic.com/Search/GetFile?Url=1!68!100!100100357)를 참조하세요.

> [!Note]  
> 언제든지 Microsoft 365 또는 Epic 고객 분석가가 구성 포털에 로그인하여 통합 레코드를 보고 필요에 따라 조직 구성을 변경할 수 있습니다.

:::image type="content" source="media/ehr-connector-epic-finish.png" alt-text="통합 정보를 보여 주는 검토 및 완료 페이지의 스크린샷." lightbox="media/ehr-connector-epic-finish.png":::

> [!Note]
> Epic 고객 분석가는 Microsoft 365 관리자가 구성한 각 FHIR 기본 URL에 대한 승인 프로세스를 완료해야 합니다.

## <a name="launch-teams-virtual-appointments"></a>Teams 가상 약속 시작

EHR 커넥터 단계 및 에픽 구성을 완료하면 조직에서 Teams 비디오 약속을 지원할 준비가 된 것입니다.

### <a name="virtual-appointments-prerequisites"></a>가상 약속 필수 구성 요소

- 시스템은 Teams 대한 모든 [소프트웨어 및 브라우저 요구 사항을](../../hardware-requirements-for-the-teams-app.md) 충족해야 합니다.

- Epic 조직과 Microsoft 365 조직 간의 통합 설정을 완료했습니다.

### <a name="provider-experience"></a>공급자 환경

조직의 의료 공급자는 Epic 공급자 앱(하이퍼스페이스, Haiku, Canto)의 Teams 사용하여 약속에 참여할 수 있습니다. **가상 방문 시작** 단추는 공급자 흐름에 포함되어 있습니다.

공급자 환경의 주요 기능:

- 공급자는 지원되는 브라우저 또는 Teams 앱을 사용하여 약속을 조인할 수 있습니다.

- 공급자는 약속에 처음 가입할 때 Microsoft 365 계정으로 일회성 로그인을 수행해야 합니다.

- 일회성 로그인 후 공급자는 Teams 가상 약속으로 직접 이동됩니다. (공급자는 Teams 로그인해야 합니다).

- 공급자는 지정된 약속에 대한 연결 및 연결 해제 참가자의 실시간 업데이트를 볼 수 있습니다. 공급자는 환자가 약속에 연결된 때를 볼 수 있습니다.

  ![환자와 약속의 공급자 경험.](media/ehc-provider-experience-6.png)

> [!NOTE]
> 의료 기록 연속성 또는 보존 목적에 필요한 모임 채팅에 입력된 모든 정보는 의료 공급자가 다운로드, 복사 및 알려야 합니다. 채팅은 법적 의료 기록 또는 지정된 레코드 집합을 구성하지 않습니다. 채팅의 메시지는 Microsoft Teams 관리자가 만든 설정에 따라 저장됩니다.

### <a name="patient-experience"></a>환자 환경

커넥터는 MyChart 웹 및 모바일을 통해 약속에 가입하는 환자를 지원합니다. 약속 시 환자는 **가상 방문** 시작 단추를 사용하여 MyChart에서 약속을 시작할 수 있습니다.

환자 환경의 주요 기능:

- 환자는 [Teams 앱을 설치하지 않고도 데스크톱 및 모바일의 최신 웹 브라우저](../browser-join.md)에서 약속을 조인할 수 있습니다.

- 환자는 한 번의 클릭으로 약속에 참여할 수 있으며 다른 계정이나 로그인이 필요하지 않습니다.

- 환자는 Microsoft 계정을 만들거나 약속을 시작하기 위해 로그인할 필요가 없습니다.

- 환자는 공급자가 가입하고 그(것)들을 인정할 때까지 로비에 배치됩니다.

- 환자는 약속에 참여하기 전에 로비에서 비디오와 마이크를 테스트 할 수 있습니다.

  ![약속의 환자 경험.](media/ehc-virtual-visit-5.png)

> [!Note]
> Epic, MyChart, Haiku 및 Canto는 Epic Systems Corporation의 상표입니다.

## <a name="get-insight-into-virtual-appointments-usage"></a>가상 약속 사용에 대한 인사이트 가져오기

Microsoft Teams 관리 센터의 [가상 방문 사용 현황 보고서는](../../teams-analytics-and-reports/virtual-visits-usage-report.md) 관리자에게 조직의 Teams 가상 약속 활동에 대한 개요를 제공합니다. 이 보고서는 EHR 시스템에서 수행된 Teams EHR 통합 모임을 포함하여 가상 약속에 대한 자세한 분석을 보여 줍니다.

로비 대기 시간 및 약속 기간과 같은 주요 메트릭을 볼 수 있습니다. 이 정보를 사용하여 사용량 추세에 대한 인사이트를 확보하여 더 나은 비즈니스 결과를 제공하기 위해 가상 약속을 최적화할 수 있습니다.

### <a name="privacy-and-location-of-data"></a>개인 정보 및 데이터의 위치

EHR 시스템에 Teams 통합은 통합 및 가상 약속 흐름 중에 사용되고 저장되는 데이터의 양을 최적화합니다. 이 솔루션은 전체 Teams 개인 정보 보호 및 데이터 관리 원칙과 Teams 개인 정보에 설명된 지침을 따릅니다.

Teams EHR 커넥터는 식별 가능한 개인 데이터 또는 EHR 시스템에서 환자 또는 의료 제공자의 건강 기록을 저장하거나 전송하지 않습니다. EHR 커넥터에 의해 저장되는 데이터는 팀 모임 설정 중에 사용되는 EHR 사용자의 고유 ID뿐입니다.

EHR 사용자의 고유 ID는 [Microsoft 365 고객 데이터가 저장되는 위치](/microsoft-365/enterprise/o365-data-locations)에 설명된 세 가지 지역 중 하나에 저장됩니다. 모임 참가자가 Teams 공유한 모든 채팅, 녹음/녹화 및 기타 데이터는 기존 스토리지 정책에 따라 저장됩니다. Teams 데이터의 위치에 대한 자세한 내용은 [Teams 데이터 위치를](../../location-of-data-in-teams.md) 참조하세요.

## <a name="related-articles"></a>관련 기사

- [가상 방문 사용 현황 보고서 Teams](../../teams-analytics-and-reports/virtual-visits-usage-report.md)
- [EHR 커넥터 관리자 보고서 Teams](ehr-admin-reports.md)
- [의료 기관을 위한 Teams 시작](teams-in-hc.md)
