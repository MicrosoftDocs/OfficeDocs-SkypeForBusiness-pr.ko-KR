---
title: 가상 Teams - Cerner EHR에 통합
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
description: 조직에서 의료 서비스 공급자가 Cerner EHR Teams 직접 환자 또는 다른 공급자와 가상 방문을 수행하도록 Teams EHR 커넥터를 통합하는 방법을 알아보습니다.
ms.openlocfilehash: 7329bd0afacfe941746374cc836203f17a9b5e57
ms.sourcegitcommit: 4df3d144296b9b8982109be7edaffd636aabdf29
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/15/2021
ms.locfileid: "60960144"
---
# <a name="virtual-visits-with-teams---integration-into-cerner-ehr"></a>가상 Teams - Cerner EHR에 통합

EHR(전자 Microsoft Teams) 커넥터를 사용하면 임상의가 환자와 가상 방문을 시작하거나 Cerner EHR 시스템에서 직접 Microsoft Teams 다른 공급자와 상담할 수 있습니다. Microsoft 365 클라우드를 Teams HIPAA, HITECH 인증 준수를 지원하는 단일 허브에서 채팅, 비디오, 음성 및 의료 도구와의 간단하고 안전한 공동 작업 및 통신을 가능하게 합니다.

의사의 통신 및 공동 작업 Teams 쉽게 조각된 시스템의 어지러워진 시스템을 잘라서 최상의 관리에 집중할 수 있습니다. EHR Teams 사용하여 다음을 할 수 있습니다.

- 통합된 Teams Cerner EHR 시스템에서 가상 방문을 수행합니다.
- 환자가 전자 메일 또는 SMS Teams 가상 방문에 참가할 수 있도록 합니다.
- EHR에 연결된 방문에 대한 소비 데이터 보고서 및 사용자 지정 가능한 통화 품질 정보를 볼 수 있습니다.

이 문서에서는 Cerner 플랫폼과 통합할 Teams EHR 커넥터를 설정하고 구성하는 방법을 설명합니다. 또한 Cerner EHR 시스템에서 가상 Teams 경험에 대한 개요를 제공합니다.

## <a name="before-you-begin"></a>시작하기 전에

> [!NOTE]
> Cerner 담당자와 대화하고 통합을 사용하도록 설정하기 전에 Cerner 통합 가이드를 검토해야 합니다.

### <a name="prerequisites"></a>필수 구성 요소

의료 조직에서 Teams EHR 커넥터를 통합하기 전에 다음이 있어야 합니다.

- EHR Microsoft Teams 독립 실행형 제품(프로덕션 EHR 환경에서 테스트하는 동안만 적용)에 대한 활성 구독입니다.
- 모임을 Microsoft 365 Office 365 적절한 Teams 라이선스입니다.
- Teams 의료 조직에서 채택 및 사용됩니다.
- 시스템은 모든 [](../../hardware-requirements-for-the-teams-app.md) 소프트웨어 및 브라우저 요구 사항을 Teams.
- Cerner 버전 2018년 11월 이상

## <a name="set-up-the-teams-ehr-connector"></a>EHR Teams 설정

커넥터를 설정하려면 다음이 필요합니다.

- [EHR 커넥터 구성 포털 시작](#launch-the-ehr-connector-configuration-portal)
- [구성 정보 입력](#enter-configuration-information)
- [SMS 알림 사용(선택 사항)](#enable-sms-notifications-optional)
- [구성 검토 및 완료](ehr-admin-cerner.md#review-and-finish-the-configuration)

> [!IMPORTANT]
> 이러한 단계는 조직의 글로벌 Microsoft 365 완료해야 합니다.  

### <a name="launch-the-ehr-connector-configuration-portal"></a>EHR 커넥터 구성 포털 시작

시작하려면 관리자 Microsoft 365 [EHR](https://ehrconnector.teams.microsoft.com) 커넥터 구성 포털을 시작하고 Microsoft 자격 증명을 사용하여 로그인합니다.

관리자 Microsoft 365 단일 부서 또는 여러 부서를 구성하여 통합을 테스트할 수 있습니다. 구성 포털에서 테스트 및 프로덕션 URL을 구성합니다. 프로덕션으로 이동하기 전에 Cerner 테스트 환경에서 통합을 테스트해야 합니다.

### <a name="enter-configuration-information"></a>구성 정보 입력

다음으로, 통합을 설정하려면 Microsoft 365 관리자가 Cerner에서 FHIR(빠른 상태 상호 운영성 리소스) 기본 URL을 추가하고 환경을 지정합니다. 조직의 요구와 테스트하려는 환경에 따라 필요한 수의 FHIR 기본 URL을 구성합니다.

:::image type="content" source="media/ehr-admin-cerner-configuration.png" alt-text="EHR 커넥터 구성 포털의 구성 Teams 스크린샷입니다." lightbox="media/ehr-admin-cerner-configuration.png":::

- FHIR 기본 URL은 서버 FHIR API 엔드포인트에 해당하는 정적 주소입니다. 예제 URL은 `https://lamnahealthcare.org/fihr/auth/connect-ocurprd-oauth/api/FHDST`입니다.

- 테스트 및 프로덕션 환경에 대한 통합을 설정할 수 있습니다. 초기 설정의 경우 프로덕션으로 이동하기 전에 테스트 환경에서 커넥터를 구성하는 것이 좋습니다.

FHIR 기본 URL의 유효성을 검사하고 환경을 선택한 후 완료 를 **선택하세요.** 그런 다음, 필요한 경우 다른 환경에 대해 FHIR 기본 URL을 더 추가합니다.

**다음을** 선택하여 다음 단계로 이동합니다.

### <a name="enable-sms-notifications-optional"></a>SMS 알림 사용(선택 사항)

조직에서 Microsoft가 환자에 대한 SMS 알림을 관리하려는 경우 이 단계를 완료합니다. SMS 알림을 사용하도록 설정하면 환자는 예약된 가상 방문에 대한 확인 및 미리 알림 메시지를 받게 됩니다.

SMS 알림을 사용하도록 설정하려면 Microsoft 365 관리자가 다음을 합니다.

1. SMS 알림 페이지에서 다음에 대한 동의 확인란을 모두 선택합니다.

    - Microsoft가 조직을 대신하여 환자에게 SMS 알림을 보낼 수 있도록 허용합니다.
    - 참석자들이 SMS 메시지를 보내고 받는 데 동의하는지 확인하도록 합니다.

    :::image type="content" source="media/ehr-admin-cerner-sms-notifications.png" alt-text="동의 확인란 및 전화 번호를 생성하는 옵션을 보여 주며 SMS 알림 페이지의 스크린샷입니다." lightbox="media/ehr-admin-cerner-sms-notifications.png":::

1. 전화 **번호 아래에서** **새** 전화 번호 생성을 선택하여 조직에 대한 전화 번호를 생성합니다. 이렇게 하면 새 전화 번호를 요청하고 생성하는 프로세스가 시작됩니다. 이 프로세스를 완료하는 데 최대 2분이 걸릴 수 있습니다.

    전화 번호가 생성되면 화면에 표시됩니다. 이 번호는 환자에게 SMS 확인 및 미리 알림을 보내는 데 사용됩니다. 이 숫자는 프로비전되어 있지만 FHIR 기본 URL에 아직 연결되지 않았습니다. 다음 단계에서 이 작업을 합니다.

    :::image type="content" source="media/ehr-admin-cerner-phone-number.png" alt-text="생성된 전화 번호의 예제를 보여주는 스크린샷입니다." lightbox="media/ehr-admin-cerner-phone-number.png":::

    완료 **를** 선택한 다음 다음 **을 선택합니다.**

1. 전화 번호를 FHIR 기본 URL에 연결하려면 **SMS** **전화** 번호 아래에서 번호를 선택합니다. SMS 알림을 사용하도록 설정하려는 각 FHIR 기본 URL에 대해 이 작업을 합니다.

    :::image type="content" source="media/ehr-admin-cerner-link-phone-number.png" alt-text="FHIR 기본 URL에 전화 번호를 연결하는 방법을 보여주는 스크린샷입니다." lightbox="media/ehr-admin-cerner-link-phone-number.png":::

    커넥터를 처음 구성하는 경우 이전 단계에서 입력한 FHIR 기본 URL이 표시됩니다. 동일한 전화 번호는 여러 FHIR 기본 URL에 연결할 수 있습니다. 즉, 환자는 다른 조직 및/또는 부서에 대해 동일한 전화 번호에서 SMS 알림을 받게 됩니다.

     다음 **을 선택합니다.**

### <a name="review-and-finish-the-configuration"></a>구성 검토 및 완료

환자 및 공급자 시작에 대한 통합 레코드가 표시됩니다. 이러한 레코드는 Cerner에서 가상 방문 구성을 완료하는 데 필요합니다. 자세한 내용은 Telehealth Cerner-Microsoft Teams 가이드를 참조하세요.

> [!NOTE]
> 사용자 관리자의 Microsoft 365 구성 포털에 로그인하여 필요한 경우 통합 레코드를 보고 구성 설정을 변경할 수 있습니다.

## <a name="launch-teams-virtual-visits"></a>Teams 가상 방문 시작

EHR 커넥터 단계 및 Cerner 구성 단계를 완료한 후 조직에서 비디오 방문을 지원할 준비가 Teams.

### <a name="virtual-visits-prerequisites"></a>가상 방문 전제

- 시스템은 모든 소프트웨어 [](../../hardware-requirements-for-the-teams-app.md) 및 브라우저 요구 사항을 충족해야 Teams.
- Cerner 조직과 사용자 조직 간의 통합 Microsoft 365 완료했습니다.

### <a name="provider-experience"></a>공급자 환경

조직의 의료 서비스 공급자는 PowerChart 포털에서 Teams 가상 방문에 참가할 수 있습니다. 공급자는 환자 보드로 이동해야 합니다. 이 Teams 사용할 수 있습니다.

거기에서 공급자는 가상 방문 정보를 보고, 가상 방문에 참가하고, 모임 링크를 보낼 수 있습니다. 일회성 로그인 후 공급자는 가상 약속으로 Teams.

공급자 환경의 주요 기능:

- 공급자는 지원되는 브라우저 또는 웹앱을 사용하여 가상 Teams 있습니다.
- 공급자는 화면 공유, 사용자 Teams 기록을 포함하여 지원되는 모든 모임 기능을 사용할 수 있습니다.
- 공급자는 PowerChart에서 주어진 약속에 대한 가상 방문에 연결하는 환자의 실시간 업데이트를 볼 수 있습니다.
- 가상 방문 중에 공급자 정보는 환자에게 표시되지 않습니다.

### <a name="patient-experience"></a>환자 환경

커넥터는 SMS 텍스트 메시지의 링크를 통해 가상 방문에 참가하는 환자를 지원합니다. 약속 시 환자는 SMS 문자 메시지의 링크를 탭하여 가상 방문을 시작할 수 있습니다.

환자 경험의 주요 기능

- 환자는 앱 을 설치하지 않고도 데스크톱 및 모바일의 최신 웹 브라우저에서 가상 [Teams 수 있습니다.](../mobile-browser-join.md)
- 환자는 한 번의 클릭으로 가상 방문에 참가할 수 있으며 다른 계정이나 로그인이 필요하지 않습니다.
- 환자는 Microsoft 계정을 만들거나 가상 방문을 시작하기 위해 로그인할 필요가 없습니다.
- 환자는 공급자가 약속에 참가하고 가상 방문에 이를 인정할 때까지 로비에 배치됩니다.
- 환자는 가상 방문에 참가하기 전에 로비에서 비디오 및 마이크를 테스트할 수 있습니다.

## <a name="privacy-and-location-of-data"></a>개인 정보 및 데이터의 위치

Teams EHR 시스템에 통합하면 통합 및 가상 방문 흐름 중에 사용 및 저장되는 데이터의 양이 최적화됩니다. 이 솔루션은 전체 Teams 개인 정보 보호 및 데이터 관리 원칙과 Teams 개인 정보에 설명된 지침을 따릅니다.

EHR Teams EHR 커넥터는 EHR 시스템에서 환자 또는 의료 공급자의 식별 가능한 개인 데이터 또는 의료 공급자의 건강 기록을 저장하거나 전송하지 않습니다. EHR 커넥터가 저장하는 유일한 데이터는 모임 설정 중에 사용되는 EHR 사용자의 고유 ID만 Teams 있습니다.

EHR 사용자의 고유 ID는 [Microsoft 365 고객 데이터가 저장되는 위치](/microsoft-365/enterprise/o365-data-locations)에 설명된 세 가지 지역 중 하나에 저장됩니다. 모임 참가자가 공유하는 모든 채팅, 녹음 Teams 기존 저장소 정책에 따라 저장됩니다. 데이터 위치에 대한 자세한 내용은 Teams 의 데이터 위치를 [Teams.](../../location-of-data-in-teams.md)

## <a name="related-articles"></a>관련 기사

- [Teams EHR 커넥터 관리자 보고서](ehr-admin-reports.md)
- [의료 조직을 위한 Teams 시작](teams-in-hc.md)
