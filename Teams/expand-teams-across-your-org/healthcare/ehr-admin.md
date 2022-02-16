---
title: 가상 Teams - Epic EHR에 통합
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
description: 조직에서 의료 서비스 공급자가 Epic EHR Teams 직접 환자 또는 다른 공급자와 가상 방문을 수행하도록 Teams EHR 커넥터를 통합하는 방법을 알아보습니다.
ms.openlocfilehash: 3274ed2c566008dd7474accf159540c96c82b865
ms.sourcegitcommit: 5880de47e986854fca873ae75f76a7ecad194dff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2022
ms.locfileid: "62763323"
---
# <a name="virtual-visits-with-teams---integration-into-epic-ehr"></a>가상 Teams - Epic EHR에 통합

EHR(전자 Microsoft Teams) 커넥터를 사용하면 임상의가 서사시 EHR 시스템에서 직접 가상 환자 방문 또는 상담을 Microsoft Teams 쉽게 사용할 수 있습니다. Microsoft 365 클라우드를 Teams HIPAA, HITECH 인증 준수를 지원하는 단일 허브에서 채팅, 비디오, 음성 및 의료 도구와의 간단하고 안전한 공동 작업 및 통신을 가능하게 합니다.

의사의 통신 및 공동 작업 Teams 쉽게 조각된 시스템의 어지러워진 시스템을 잘라서 최상의 관리에 집중할 수 있습니다. EHR Teams 사용하여 다음을 할 수 있습니다.

- 통합 Teams 임상 워크플로를 사용하여 Epic EHR 시스템에서 가상 방문을 실행합니다.
- 환자가 환자 Teams 또는 SMS를 통해 가상 방문에 참가할 수 있도록 합니다.
- 다중 참가자, 그룹 방문 및 통역 서비스를 비롯한 다른 시나리오를 지원합니다.
- 참석자 연결, 연결 끊기 및 자동 감사 및 레코드 유지를 사용하도록 설정하는 Teams 가상 방문에 대한 메타데이터를 EHR 시스템에 다시 기록합니다.
- EHR에 연결된 방문에 대한 소비 데이터 보고서 및 사용자 지정 가능한 통화 품질 정보를 볼 수 있습니다.

EHR 포털에서 가상 방문을 관리하는 방법에 대한 개요는 이 비디오를 참조하세요.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4HAtn]

이 문서에서는 의료 조직의 Epic 플랫폼과 통합하도록 EHR Teams EHR 커넥터를 설정하고 구성하는 방법을 설명합니다. 또한 Epic EHR 시스템에서 가상 Teams 경험에 대한 개요를 제공합니다.

## <a name="before-you-begin"></a>시작하기 전에

시작하기 전에 통합을 준비하기 위해 몇 가지 작업을 할 수 있습니다.

### <a name="get-familiar-with-the-integration-process"></a>통합 프로세스에 익숙해지기

전체 통합 프로세스를 이해하기 위해 다음 정보를 검토합니다.

:::image type="content" source="media/ehr-connector-epic-flow.png" alt-text="전체 통합 프로세스의 단계를 요약한 이미지입니다.":::

||||||
|---------|---------|---------|---------|---------|
|**작업**: [앱에 대한 Teams 요청합니다](#request-access-to-the-teams-app). <br> **결과**: 조직에 테스트 권한을 제공합니다.|**작업**: 공용 및 개인 키 인증서를 만들고 이를 Epic에 업로드합니다. <br> **결과**: 에픽은 공용 키 인증서를 동기화합니다.|**작업**: EHR 커넥터 구성 포털에서 구성 단계를 완료합니다. <br> **결과**: Epic 구성에 대한 FDI 레코드를 수신합니다.| **작업**: 에픽 기술 전문가와 함께 에픽에서 FDI 레코드를 구성합니다.<br> **결과**: 구성이 완료되었습니다. 테스트할 준비가 완료되었습니다.|**작업**: 테스트 환경에서 테스트를 완료합니다.<br> **결과**: 흐름의 전체 유효성 검사 및 프로덕션으로 이동하기 위한 결정입니다.|

### <a name="request-access-to-the-teams-app"></a>앱에 대한 Teams 요청

앱에 대한 액세스를 요청해야 Teams 합니다.

1. 에픽 앱 Teams 마켓플레이스에서 앱 다운로드를 [요청합니다](https://apporchard.epic.com/Gallery?id=6153). 이렇게 하면 Microsoft EHR 커넥터 팀에 대한 에픽의 요청이 트리거됩니다.
1. 요청을 한 후 조직 [이름, TeamsForHealthcare@service.microsoft.com](mailto:teamsforhealthcare@service.microsoft.com) 및 Epic 기술 담당자의 전자 메일 주소가 있는 전자 메일을 전송합니다.
1. Microsoft EHR 커넥터 팀은 사용 확인을 통해 전자 메일에 응답합니다.

### <a name="review-the-epic-microsoft-teams-telehealth-integration-guide"></a>Telehealth Epic-Microsoft Teams 가이드 검토

Epic 기술 전문가와 함께 [Epic-Microsoft 팀 원격 상태 통합 가이드](https://galaxy.epic.com/Search/GetFile?Url=1!68!100!100100357)를 검토해 보세요. 모든 반드시 충족해야 합니다.

## <a name="prerequisites"></a>필수 구성 요소

- EHR 의료 조직을 위한 Microsoft Cloud 독립 실행형 Microsoft Teams 구독 또는 구독에 대한 활성 구독입니다(프로덕션 EHR 환경에서 테스트할 때만 적용).
- 에픽 버전 2018년 11월 이상
- 사용자는 모임을 포함하는 Microsoft 365 Office 365 라이선스를 Teams 있습니다.
- Teams 의료 조직에서 채택 및 사용됩니다.
- 시스템은 모든 소프트웨어 및 [](../../hardware-requirements-for-the-teams-app.md) 브라우저 요구 사항을 Teams.

> [!IMPORTANT]
> 통합을 진행하기 전에 사전 통합 단계를 완료하고 모든 구성 구성이 충족될 수 있는지 확인하세요.

통합 단계는 조직의 다음 사용자에 의해 수행됩니다.

- **Microsoft 365 관리자**: 통합을 담당하는 주 사용자입니다. 관리자는 커넥터를 구성하고, SMS를 사용하도록 설정하고(필요한 경우) 구성을 인증할 에픽 고객 분석가를 추가합니다.
- **에픽 고객 분석가**: 에픽에 로그인 자격 증명이 있는 조직의 사람입니다. 관리자는 관리자가 입력한 구성 설정을 승인하고 에픽에 구성 레코드를 제공합니다.

관리자 Microsoft 365 에픽 고객 분석가는 동일한 사람이 될 수 있습니다.

## <a name="set-up-the-teams-ehr-connector"></a>EHR Teams 설정

커넥터를 설정하려면 다음이 필요합니다.

- [EHR 커넥터 구성 포털 시작](#launch-the-ehr-connector-configuration-portal)
- [구성 정보 입력](#enter-configuration-information)
- [SMS 알림 사용(선택 사항)](#enable-sms-notifications-optional)
- [구성 승인 또는 보기](#approve-or-view-the-configuration)
- [구성 검토 및 완료](#review-and-finish-the-configuration)

### <a name="launch-the-ehr-connector-configuration-portal"></a>EHR 커넥터 구성 포털 시작

시작하려면 Microsoft 365 [관리자가 EHR](https://ehrconnector.teams.microsoft.com) 커넥터 구성 포털을 시작하고 전자 Microsoft 365 로그인합니다.

사용자 Microsoft 365 단일 조직 또는 여러 조직을 구성하여 통합을 테스트할 수 있습니다. 구성 포털에서 테스트 및 프로덕션 URL을 구성합니다. 프로덕션으로 이동하기 전에 Epic 테스트 환경에서 통합을 테스트해야 합니다.

> [!NOTE]
> 사용자 Microsoft 365 및 에픽 고객 분석가가 구성 포털의 통합 단계를 완료해야 합니다. 에픽 구성 단계의 경우 조직에 할당된 에픽 기술 전문가에게 문의하세요.

### <a name="enter-configuration-information"></a>구성 정보 입력

다음으로 통합을 설정하려면 Microsoft 365 관리자가 다음을 합니다.

1. 에픽 기술 전문가의 FHIR(빠른 상태 상호 운영성 리소스) 기본 URL을 추가하고 환경을 지정합니다. 조직의 요구와 테스트하려는 환경에 따라 필요한 수의 FHIR 기본 URL을 구성합니다.

    - FHIR 기본 URL은 서버 FHIR API 엔드포인트에 해당하는 정적 주소입니다. 예제 URL은 `https://lamnahealthcare.org/fihr/auth/connect-ocurprd-oauth/api/FHDST`입니다.

    - 테스트 및 프로덕션 환경에 대한 통합을 설정할 수 있습니다. 초기 설정의 경우 프로덕션으로 이동하기 전에 테스트 환경에서 커넥터를 구성하는 것이 좋습니다.

1. 이후 단계에서 구성을 사용할 에픽 고객 분석가의 사용자 이름을 추가합니다.

    :::image type="content" source="media/ehr-connector-epic-configure.png" alt-text="추가될 승인자가 표시되어 있는 구성 페이지의 스크린샷입니다." lightbox="media/ehr-connector-epic-configure.png":::

### <a name="enable-sms-notifications-optional"></a>SMS 알림 사용(선택 사항)

> [!NOTE]
> SMS 알림은 현재 미국에서만 사용할 수 있습니다. 향후 릴리스에서 다른 지역에서 이 기능을 사용할 수 있도록 Teams 이 문서를 업데이트할 예정입니다.

조직에서 Microsoft가 환자에 대한 SMS 알림을 관리하려는 경우 이 단계를 완료합니다. SMS 알림을 사용하도록 설정하면 환자는 예약된 방문에 대한 확인 및 미리 알림 메시지를 받게 됩니다.

SMS 알림을 사용하도록 설정하려면 Microsoft 365 관리자가 다음을 합니다.

1. SMS 알림 페이지에서 다음에 대한 동의 확인란을 모두 선택합니다.

    - Microsoft가 조직을 대신하여 환자에게 SMS 알림을 보낼 수 있도록 허용합니다.
    - 참석자들이 SMS 메시지를 보내고 받는 데 동의하는지 확인하도록 합니다.
    
    :::image type="content" source="media/ehr-connector-epic-sms-notifications.png" alt-text="동의 확인란 및 전화 번호를 생성하는 옵션을 보여 주며 SMS 알림 페이지의 스크린샷입니다." lightbox="media/ehr-connector-epic-sms-notifications.png":::

1. 전화 **번호 아래****에서 새 전화** 번호 생성을 선택하여 조직에 대한 전화 번호를 생성합니다. 이렇게 하면 새 전화 번호를 요청하고 생성하는 프로세스가 시작됩니다. 이 프로세스를 완료하는 데 최대 2분이 걸릴 수 있습니다.

    전화 번호가 생성되면 화면에 표시됩니다. 이 번호는 환자에게 SMS 확인 및 미리 알림을 보내는 데 사용됩니다. 이 숫자는 프로비전되어 있지만 FHIR 기본 URL에 아직 연결되지 않았습니다. 다음 단계에서 이 작업을 합니다.

    :::image type="content" source="media/ehr-connector-epic-phone-number.png" alt-text="생성된 전화 번호의 예제를 보여주는 스크린샷입니다." lightbox="media/ehr-connector-epic-phone-number.png":::

    완료 **를** 선택한 다음 다음을 **선택합니다**.

1. 전화 번호를 FHIR 기본 URL에 연결하려면 **SMS** **전화** 번호 아래에서 번호를 선택합니다. SMS 알림을 사용하도록 설정하려는 각 FHIR 기본 URL에 대해 이 작업을 합니다.

    :::image type="content" source="media/ehr-connector-epic-link-phone-number.png" alt-text="FHIR 기본 URL에 전화 번호를 연결하는 방법을 보여주는 스크린샷입니다." lightbox="media/ehr-connector-epic-link-phone-number.png":::

    커넥터를 처음 구성하는 경우 이전 단계에서 입력한 FHIR 기본 URL이 표시됩니다. 동일한 전화 번호는 여러 FHIR 기본 URL에 연결할 수 있습니다. 즉, 환자는 다른 조직 및/또는 부서에 대해 동일한 전화 번호에서 SMS 알림을 받게 됩니다.

1. 각 **FHIR** 기본 URL 옆에 있는 SMS 설정을 선택하여 환자에게 보낼 SMS 알림 유형을 설정합니다.

    :::image type="content" source="media/ehr-connector-epic-sms-setup.png" alt-text="SMS 설정 설정을 보여주는 스크린샷입니다." lightbox="media/ehr-connector-epic-sms-setup.png":::

    - **확인 SMS**: EHR 시스템에서 방문이 예약, 업데이트 또는 취소될 때 알림이 환자에게 전송됩니다.
    - **미리 알림 SMS**: 지정한 시간 간격과 방문의 예약된 시간에 따라 환자에게 알림이 전송됩니다.

    저장 **을 선택 합니다**.

1. 공용 **업로드 인증서** 를 업로드하려면 인증서를 선택합니다. 각 환경에 대해 Base64 인코딩(공개 키만 해당) .cer 인증서를 업로드해야 합니다.

    SMS 알림을 보내기 위한 약속 정보를 수신하려면 공용 키 인증서가 필요합니다. 들어오는 정보가 유효한 원본에서 제공된지 확인하려면 인증서가 필요합니다.

    커넥터가 SMS 미리 알림을 보내는 데 사용되는 경우 에픽에서 약속을 만들 때 환자의 전화 번호는 HL7v2 페이로드에 에픽에서 전송됩니다. 이러한 숫자는 조직의 지리에 있는 각 약속에 대해 저장되고 약속이 진행될 때까지 유지됩니다. HL7v2 메시지를 구성하는 방법에 대한 자세한 내용은 [Epic-Microsoft Teams](https://galaxy.epic.com/Search/GetFile?Url=1!68!100!100100357) 통합 가이드를 참조하세요.

    다음 **을 선택합니다**.

> [!NOTE]
> 사용자 관리자의 Microsoft 365 SMS 설정을 업데이트할 수 있습니다. 설정을 변경하면 SMS 서비스가 중지될 수 있습니다. SMS 보고서를 보는 방법에 대한 [자세한 내용은 EHR 커넥터 관리 Teams 참조하세요](ehr-admin-reports.md).

### <a name="approve-or-view-the-configuration"></a>구성 승인 또는 보기

승인자로 추가된 조직의 에픽 고객 분석가가 [EH Microsoft 365 R](https://ehrconnector.teams.microsoft.com) 커넥터 구성 포털을 시작하고 해당 자격 증명을 사용하여 로그인합니다. 유효성 검사가 성공하면 승인자가 Epic 자격 증명을 사용하여 에픽 조직의 유효성을 검사하기 위해 로그인해야 합니다.

> [!Note]
> 관리자와 Microsoft 365 에픽 고객 분석가가 동일한 사람인 경우 여전히 에픽에 로그인하여 액세스의 유효성을 검사해야 합니다. 에픽 로그인은 FHIR 기본 URL의 유효성을 검사하는 데만 사용됩니다. Microsoft는 이 로그인을 사용하여 자격 증명을 저장하거나 EHR 데이터에 액세스하지 않습니다.

:::image type="content" source="media/ehr-connector-epic-login-approve.png" alt-text="로그인 및 승인 옵션을 보여 주며 구성 승인 또는 보기 페이지의 스크린샷입니다." lightbox="media/ehr-connector-epic-login-approve.png":::

Epic에 성공적으로 로그인한 후 에픽 고객 분석가가 **구성** 을 승인해야 합니다. 구성이 올치 않은 경우 Microsoft 365 관리자가 구성 포털에 로그인하고 설정을 변경할 수 있습니다.

:::image type="content" source="media/ehr-connector-epic-approve.png" alt-text="승인 옵션을 보여 주며 구성 승인 또는 보기 페이지의 스크린샷입니다." lightbox="media/ehr-connector-epic-approve.png":::

### <a name="review-and-finish-the-configuration"></a>구성 검토 및 완료

Epic 관리자가 구성 정보를 승인하면 환자 및 공급자 출시에 대한 통합 레코드가 표시됩니다. 통합 레코드에는 다음이 포함됩니다.

- 환자 및 공급자 레코드
- 직접 SMS 레코드
- SMS 구성 레코드
- 디바이스 테스트 구성 레코드

에픽 고객 분석가는 이러한 레코드를 에픽에 제공해야 에픽에서 Virtual Visits 구성을 완료해야 합니다. 자세한 내용은 [Epic-Microsoft Teams Telehealth 통합 가이드를 참조하세요](https://galaxy.epic.com/Search/GetFile?Url=1!68!100!100100357).

> [!Note]  
> 사용자 또는 Microsoft 365 고객 분석가가 구성 포털에 로그인하여 필요한 경우 통합 레코드를 보고 조직 구성을 변경할 수 있습니다.

:::image type="content" source="media/ehr-connector-epic-finish.png" alt-text="통합 정보를 보여 주며 검토 및 완료 페이지의 스크린샷입니다." lightbox="media/ehr-connector-epic-finish.png":::

> [!Note]
> 에픽 고객 분석가는 관리자 관리자에 의해 구성된 각 FHIR 기본 URL에 대한 승인 Microsoft 365 완료해야 합니다.

## <a name="launch-teams-virtual-visits"></a>가상 Teams 시작

EHR 커넥터 단계 및 에픽 구성을 완료한 후 조직에서 비디오 방문을 지원할 준비가 Teams.

### <a name="virtual-visits-prerequisites"></a>가상 방문의 전제

- 시스템은 모든 소프트웨어 및 브라우저 [](../../hardware-requirements-for-the-teams-app.md) 요구 사항을 충족해야 Teams.

- Epic 조직과 사용자 조직 간의 통합 Microsoft 365 완료했습니다.

### <a name="provider-experience"></a>공급자 환경

조직의 의료 서비스 공급자는 해당 Teams(Hyperspace, Haiku, Canto)의 앱을 사용하여 방문에 참가할 수 있습니다. **가상 방문 시작** 단추는 공급자 흐름에 포함되어 있습니다.

공급자 환경의 주요 기능:

- 공급자는 지원되는 브라우저 또는 웹앱을 사용하여 방문에 Teams 있습니다.

- 공급자는 처음으로 방문에 참가할 때 Microsoft 365 계정으로 일회성 로그인을 해야 합니다.

- 일회성 로그인 후 공급자는 가상 약속으로 Teams. (공급자는 로그인하여 로그인해야 Teams.

- 공급자는 주어진 약속에 대한 연결 및 연결을 끊는 참가자의 실시간 업데이트를 볼 수 있습니다. 공급자는 환자가 방문에 연결되는 경우를 볼 수 있습니다.

  ![환자와의 방문의 공급자 경험.](media/ehc-provider-experience-6.png)

> [!NOTE]
> 의료 기록 연속성 또는 보존 목적에 필요한 모임 채팅에 입력된 모든 정보는 의료 공급자가 다운로드, 복사 및 기록해야 합니다. 채팅은 법적 의료 기록 또는 지정된 레코드 집합을 구성하지 않습니다. 채팅의 메시지는 관리자 관리자가 만든 설정에 Microsoft Teams 저장됩니다.

### <a name="patient-experience"></a>환자 환경

커넥터는 MyChart 웹 및 모바일을 통해 방문에 참가하는 환자를 지원합니다. 약속 시 환자는 가상 방문 시작 단추를 사용하여 MyChart에서 방문 **을 시작할 수** 있습니다.

환자 환경의 주요 기능:

- 환자는 앱을 설치하지 않고도 데스크톱 및 모바일의 최신 [웹 브라우저에서 방문에 참가할 Teams 있습니다](../mobile-browser-join.md).

- 환자는 클릭 한 번으로 방문에 참가할 수 있으며 다른 계정이나 로그인이 필요하지 않습니다.

- 환자는 Microsoft 계정을 만들거나 방문을 시작하기 위해 로그인할 필요는 없습니다.

- 환자는 공급자가 가입하고 인정할 때까지 로비에 배치됩니다.

- 환자는 방문에 참가하기 전에 로비에서 비디오 및 마이크를 테스트할 수 있습니다.

  ![방문의 환자 경험.](media/ehc-virtual-visit-5.png)

> [!Note]
> Epic, MyChart, Haiku 및 Canto는 Epic Systems Corporation의 상표입니다.

### <a name="privacy-and-location-of-data"></a>개인 정보 및 데이터의 위치

Teams EHR 시스템에 통합하면 통합 및 가상 방문 흐름 중에 사용 및 저장되는 데이터의 양이 최적화됩니다. 이 솔루션은 전체 Teams 개인 정보 보호 및 데이터 관리 원칙과 Teams 개인 정보에 설명된 지침을 따릅니다.

EHR Teams EHR 커넥터는 EHR 시스템에서 환자 또는 의료 공급자의 식별 가능한 개인 데이터 또는 의료 공급자의 건강 기록을 저장하거나 전송하지 않습니다. EHR 커넥터에 의해 저장되는 데이터는 팀 모임 설정 중에 사용되는 EHR 사용자의 고유 ID뿐입니다.

EHR 사용자의 고유 ID는 [Microsoft 365 고객 데이터가 저장되는 위치](/microsoft-365/enterprise/o365-data-locations)에 설명된 세 가지 지역 중 하나에 저장됩니다. 모임 참가자가 공유하는 모든 채팅, Teams 및 기타 데이터는 기존 저장소 정책에 따라 저장됩니다. 데이터 위치에 대한 자세한 내용은 Teams 데이터 위치를 [Teams 참조하세요](../../location-of-data-in-teams.md).

## <a name="related-articles"></a>관련 기사

- [Teams EHR 커넥터 관리자 보고서](ehr-admin-reports.md)
- [의료 조직을 위한 Teams 시작](teams-in-hc.md)
