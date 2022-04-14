---
title: Teams 가상 방문 - Cerner EHR에 통합
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
description: 조직의 의료 공급자가 Cerner EHR 시스템에서 직접 Teams 환자 또는 다른 공급자와 가상 방문을 수행할 수 있도록 Teams EHR 커넥터를 통합하는 방법을 알아봅니다.
ms.openlocfilehash: b5a5a860036b3b561d5a6e18a13b71e072998aa4
ms.sourcegitcommit: 480046a53dfb6e6cf867e1920f8fb43dda9d3774
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2022
ms.locfileid: "64703694"
---
# <a name="virtual-visits-with-teams---integration-into-cerner-ehr"></a>Teams 가상 방문 - Cerner EHR에 통합

Microsoft Teams EHR(전자 건강 기록) 커넥터를 사용하면 임상의가 가상 환자 방문을 시작하거나 Cerner EHR 시스템에서 직접 Microsoft Teams 다른 공급자와 상담할 수 있습니다. Microsoft 365 클라우드에서 구축된 Teams HIPAA, HITECH 인증 등을 준수하는 단일 허브에서 채팅, 비디오, 음성 및 의료 도구와의 간단하고 안전한 공동 작업 및 통신을 지원합니다.

Teams 통신 및 공동 작업 플랫폼을 사용하면 임상의가 조각난 시스템의 혼란을 쉽게 끊어 최상의 치료를 제공하는 데 집중할 수 있습니다. Teams EHR 커넥터를 사용하면 다음을 수행할 수 있습니다.

- 통합 임상 워크플로를 사용하여 Cerner EHR 시스템에서 Teams 가상 방문을 수행합니다.
- 환자가 이메일 또는 SMS 알림에서 Teams 가상 방문에 참여할 수 있도록 합니다.
- EHR 연결 방문에 대한 사용량 데이터 보고서 및 사용자 지정 가능한 통화 품질 정보를 봅니다.

이 문서에서는 Cerner 플랫폼과 통합하도록 Teams EHR 커넥터를 설정하고 구성하는 방법을 설명합니다. 또한 Cerner EHR 시스템의 Teams 가상 방문 환경에 대한 개요를 제공합니다.

## <a name="before-you-begin"></a>시작하기 전에

> [!NOTE]
> 통합을 사용하도록 설정하기 전에 Cerner 담당자에게 문의하고 Cerner 통합 가이드를 검토하세요.

### <a name="prerequisites"></a>필수 구성 요소

의료 기관에서 Teams EHR 커넥터를 통합하기 전에 다음이 있어야 합니다.

- Microsoft Teams EHR 커넥터 독립 실행형 제품에 대한 활성 구독입니다(프로덕션 EHR 환경에서 테스트하는 동안에만 적용됨).
- 사용자에게는 Teams 모임을 포함하는 적절한 Microsoft 365 또는 Office 365 라이선스가 있습니다.
- Teams 의료 조직에서 채택되고 사용됩니다.
- 시스템은 Teams 대한 모든 [소프트웨어 및 브라우저 요구 사항을 충족합니다](../../hardware-requirements-for-the-teams-app.md).
- Cerner 버전 2018년 11월 이상

## <a name="set-up-the-teams-ehr-connector"></a>Teams EHR 커넥터 설정

커넥터를 설정하려면 다음이 필요합니다.

- [EHR 커넥터 구성 포털 시작](#launch-the-ehr-connector-configuration-portal)
- [구성 정보 입력](#enter-configuration-information)
- [SMS 알림 사용(선택 사항)](#enable-sms-notifications-optional)
- [구성 검토 및 완료](ehr-admin-cerner.md#review-and-finish-the-configuration)

> [!IMPORTANT]
> 이러한 단계는 조직의 Microsoft 365 전역 관리자가 완료해야 합니다.  

### <a name="launch-the-ehr-connector-configuration-portal"></a>EHR 커넥터 구성 포털 시작

시작하려면 Microsoft 365 관리자가 [EHR 커넥터 구성 포털](https://ehrconnector.teams.microsoft.com)을 시작하고 Microsoft 자격 증명을 사용하여 로그인합니다.

Microsoft 365 관리자는 통합을 테스트하도록 단일 부서 또는 여러 부서를 구성할 수 있습니다. 구성 포털에서 테스트 및 프로덕션 URL을 구성합니다. 프로덕션으로 이동하기 전에 Cerner 테스트 환경에서 통합을 테스트해야 합니다.

### <a name="enter-configuration-information"></a>구성 정보 입력

다음으로 통합을 설정하기 위해 Microsoft 365 관리자는 Cerner의 FHIR(Fast Health Interoperability Resources) 기본 URL을 추가하고 환경을 지정합니다. 조직의 요구 사항 및 테스트하려는 환경에 따라 필요한 만큼의 FHIR 기본 URL을 구성합니다.

:::image type="content" source="media/ehr-admin-cerner-configuration.png" alt-text="Teams EHR 커넥터 구성 포털의 구성 정보 페이지 스크린샷" lightbox="media/ehr-admin-cerner-configuration.png":::

- FHIR 기본 URL은 서버 FHIR API 엔드포인트에 해당하는 정적 주소입니다. 예제 URL은 `https://lamnahealthcare.org/fihr/auth/connect-ocurprd-oauth/api/FHDST`입니다.

- 테스트 및 프로덕션 환경에 대한 통합을 설정할 수 있습니다. 초기 설정의 경우 프로덕션 환경으로 이동하기 전에 테스트 환경에서 커넥터를 구성하는 것이 좋습니다.

FHIR 기본 URL의 유효성을 검사하고 환경을 선택한 후 **완료** 를 선택합니다. 그런 다음 필요에 따라 다른 환경에 대한 FHIR 기본 URL을 더 추가합니다.

**다음** 을 선택하여 다음 단계로 이동합니다.

### <a name="enable-sms-notifications-optional"></a>SMS 알림 사용(선택 사항)

조직에서 Microsoft가 환자에 대한 SMS 알림을 관리하도록 하려는 경우 이 단계를 완료합니다. SMS 알림을 사용하도록 설정하면 환자는 예약된 방문에 대한 확인 및 미리 알림 메시지를 받게 됩니다.

SMS 알림을 사용하도록 설정하기 위해 Microsoft 365 관리자는 다음을 수행합니다.

1. SMS 알림 페이지에서 다음을 수행할 두 동의 확인란을 모두 선택합니다.

    - Microsoft가 조직을 대신하여 환자에게 SMS 알림을 보낼 수 있도록 허용합니다.
    - 참석자가 SMS 메시지를 보내고 받는 데 동의했는지 확인합니다.

    :::image type="content" source="media/ehr-admin-cerner-sms-notifications.png" alt-text="동의 확인란과 전화 번호를 생성하는 옵션을 보여 주는 SMS 알림 페이지의 스크린샷." lightbox="media/ehr-admin-cerner-sms-notifications.png":::

1. **전화 번호** 아래에서 **새 전화 번호 생성을** 선택하여 조직의 전화 번호를 생성합니다. 이렇게 하면 새 전화 번호를 요청하고 생성하는 프로세스가 시작됩니다. 이 프로세스를 완료하는 데 최대 2분이 걸릴 수 있습니다.

    전화 번호가 생성되면 화면에 표시됩니다. 이 번호는 환자에게 SMS 확인 및 미리 알림을 보내는 데 사용됩니다. 숫자가 프로비전되었지만 아직 FHIR 기본 URL에 연결되지 않았습니다. 다음 단계에서 이 작업을 수행합니다.

    :::image type="content" source="media/ehr-admin-cerner-phone-number.png" alt-text="생성된 전화 번호의 예를 보여 주는 스크린샷." lightbox="media/ehr-admin-cerner-phone-number.png":::

    **완료****를 선택한 다음** 다음을 선택합니다.

1. 전화 번호를 FHIR 기본 URL에 연결하려면 **SMS 구성** 섹션의 **전화 번호** 아래에서 번호를 선택합니다. SMS 알림을 사용하도록 설정하려는 각 FHIR 기본 URL에 대해 이 작업을 수행합니다.

    :::image type="content" source="media/ehr-admin-cerner-link-phone-number.png" alt-text="전화 번호를 FHIR 기본 URL에 연결하는 방법을 보여 주는 스크린샷" lightbox="media/ehr-admin-cerner-link-phone-number.png":::

    커넥터를 처음 구성하는 경우 이전 단계에서 입력한 FHIR 기본 URL이 표시됩니다. 동일한 전화 번호를 여러 FHIR 기본 URL에 연결할 수 있습니다. 즉, 환자는 다른 조직 및/또는 부서에 대해 동일한 전화 번호에서 SMS 알림을 받습니다.

     **다음** 을 선택합니다.

### <a name="review-and-finish-the-configuration"></a>구성 검토 및 완료

환자 및 공급자 시작에 대한 통합 레코드가 표시됩니다. 이러한 레코드는 Cerner에서 가상 방문 구성을 완료하는 데 필요합니다. 자세한 내용은 Cerner-Microsoft Teams Telehealth 통합 가이드를 참조하세요.

> [!NOTE]
> 언제든지 Microsoft 365 관리자가 구성 포털에 로그인하여 통합 레코드를 보고 필요한 경우 구성 설정을 변경할 수 있습니다.

## <a name="launch-teams-virtual-visits"></a>가상 방문 Teams 시작

EHR 커넥터 단계 및 Cerner 구성 단계를 완료한 후 조직은 Teams 비디오 방문을 지원할 준비가 된 것입니다.

### <a name="virtual-visits-prerequisites"></a>가상 방문 필수 구성 요소

- 시스템은 Teams 대한 모든 [소프트웨어 및 브라우저 요구 사항을](../../hardware-requirements-for-the-teams-app.md) 충족해야 합니다.
- Cerner 조직과 Microsoft 365 조직 간의 통합 설정을 완료했습니다.

### <a name="provider-experience"></a>공급자 환경

조직의 의료 공급자는 PowerChart 포털의 Teams 사용하여 방문에 참여할 수 있습니다. 공급자는 Teams 옵션을 사용할 수 있는 환자 보드로 이동해야 합니다.

여기에서 공급자는 방문 정보를 보고, 방문에 참여하고, 모임 링크를 보낼 수 있습니다. 일회성 로그인 후 공급자는 Teams 가상 약속으로 직접 이동됩니다.

공급자 환경의 주요 기능:

- 공급자는 지원되는 브라우저 또는 Teams 앱을 사용하여 방문에 참여할 수 있습니다.
- 공급자는 화면 공유, 사용자 지정 배경 및 녹음/녹화를 포함하여 지원되는 모든 Teams 모임 기능을 사용할 수 있습니다.
- 공급자는 PowerChart에서 지정된 약속을 위해 방문에 연결하는 환자의 실시간 업데이트를 볼 수 있습니다.
- 공급자 정보는 방문하는 동안 환자에게 표시되지 않습니다.

> [!NOTE]
> 의료 기록 연속성 또는 보존 목적에 필요한 모임 채팅에 입력된 모든 정보는 의료 공급자가 다운로드, 복사 및 알려야 합니다. 채팅은 법적 의료 기록 또는 지정된 레코드 집합을 구성하지 않습니다. 채팅의 메시지는 Microsoft Teams 관리자가 만든 설정에 따라 저장됩니다.

### <a name="patient-experience"></a>환자 환경

커넥터는 SMS 문자 메시지의 링크를 통해 방문에 참여하는 환자를 지원합니다. 약속 시 환자는 SMS 문자 메시지의 링크를 탭하여 방문을 시작할 수 있습니다.

환자 환경의 주요 기능

- 환자는 [Teams 앱을 설치하지 않고도 데스크톱 및 모바일의 최신 웹 브라우저](../browser-join.md)에서 방문에 참여할 수 있습니다.
- 환자는 한 번의 클릭으로 방문에 참여할 수 있으며 다른 계정이나 로그인이 필요하지 않습니다.
- 환자는 Microsoft 계정을 만들거나 로그인하여 방문을 시작할 필요가 없습니다.
- 환자는 공급자가 가입하고 그(것)들을 인정할 때까지 로비에 배치됩니다.
- 환자는 방문에 참여하기 전에 로비에서 비디오와 마이크를 테스트 할 수 있습니다.

## <a name="get-insight-into-virtual-visits-usage"></a>가상 방문 사용 현황에 대한 인사이트 얻기

Microsoft Teams 관리 센터의 [가상 방문 사용 현황 보고서는](../../teams-analytics-and-reports/virtual-visits-usage-report.md) 관리자에게 조직의 Teams Virtual Visits 활동에 대한 개요를 제공합니다. 이 보고서는 EHR 시스템에서 수행된 Teams EHR 통합 모임을 포함하여 가상 약속에 대한 자세한 분석을 보여 줍니다.

로비 대기 시간 및 방문 기간과 같은 주요 메트릭을 볼 수 있습니다. 이 정보를 사용하여 더 나은 비즈니스 결과를 제공하기 위해 가상 방문을 최적화하는 데 도움이 되는 사용량 추세에 대한 인사이트를 얻을 수 있습니다.

## <a name="privacy-and-location-of-data"></a>개인 정보 및 데이터의 위치

EHR 시스템에 Teams 통합은 통합 및 가상 방문 흐름 중에 사용되고 저장되는 데이터의 양을 최적화합니다. 이 솔루션은 전체 Teams 개인 정보 보호 및 데이터 관리 원칙과 Teams 개인 정보에 설명된 지침을 따릅니다.

Teams EHR 커넥터는 식별 가능한 개인 데이터 또는 EHR 시스템에서 환자 또는 의료 제공자의 건강 기록을 저장하거나 전송하지 않습니다. EHR 커넥터가 저장하는 유일한 데이터는 Teams 모임 설정 중에 사용되는 EHR 사용자의 고유 ID입니다.

EHR 사용자의 고유 ID는 [Microsoft 365 고객 데이터가 저장되는 위치](/microsoft-365/enterprise/o365-data-locations)에 설명된 세 가지 지역 중 하나에 저장됩니다. 모임 참가자가 Teams 공유한 모든 채팅, 녹음/녹화 및 기타 데이터는 기존 스토리지 정책에 따라 저장됩니다. Teams 데이터의 위치에 대한 자세한 내용은 [Teams 데이터 위치를](../../location-of-data-in-teams.md) 참조하세요.

## <a name="related-articles"></a>관련 기사

- [가상 방문 사용 현황 보고서 Teams](../../teams-analytics-and-reports/virtual-visits-usage-report.md)
- [EHR 커넥터 관리자 보고서 Teams](ehr-admin-reports.md)
- [의료 기관을 위한 Teams 시작](teams-in-hc.md)
