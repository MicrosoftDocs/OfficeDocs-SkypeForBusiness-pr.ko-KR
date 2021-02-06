---
title: 가상 방문을 위한 Teams
author: cichur
ms.author: v-cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
- microsoftcloud-healthcare
- m365solution-healthcare
- m365solution-scenario
appliesto:
- Microsoft Teams
ms.reviewer: ''
description: Microsoft Teams를 사용하여 가상 방문 시스템 설정
ms.openlocfilehash: 2d2be135668bcc45f0054e987a23845e3245c38e
ms.sourcegitcommit: 1b11a2b74b8db6ed9e5da9b04cf3ed9c02a1d892
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "50125781"
---
# <a name="virtual-visits-with-teams---integration-into-ehr"></a>Teams를 통해 가상 방문 - EHR에 통합

Microsoft Teams EHR(Electronic Health Record) 커넥터를 사용하면 의료진이 EHR 시스템에서 직접 Teams의 다른 공급자와 가상 환자 방문 또는 상담을 쉽게 할 수 있습니다. Microsoft 365 클라우드에서 구축된 Microsoft Teams는 HIPAA, HITECH 인증 준수를 지원하는 단일 허브에서 채팅, 비디오, 음성 및 의료 도구를 사용하여 간단하고 안전한 공동 작업 및 통신을 가능하게 합니다.
Teams의 통신 및 공동 작업 플랫폼을 사용하면 의료진이 가장 좋은 진료를 제공하는 데 시간을 할애할 수 있도록 조각난 시스템의 어수선한 결과를 쉽게 끊을 수 있습니다. Microsoft Teams EHR(Electronic Health Record) 커넥터는 다음을 할 수 있습니다.
- 공급자 및 환자 포털에서 Teams 가상 방문을 실행합니다.
- 연결 및 연결 해제 이벤트에 대한 EHR 메타데이터에 다시 작성하여 자동 감사 및 레코드 유지를 활성화합니다.
- 기존 의사 및 환자 워크플로에 통합하면서 Microsoft Teams를 사용할 수 있습니다.

  EHR 포털에서 가상 방문을 관리하는 방법에 대한 비디오를 시청합니다.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4HAtn]

## <a name="before-you-begin"></a>시작하기 전에

EHR 커넥터를 통합하려면 먼저 다음의 전제가 있는지 확인해야 합니다.

- Epic의 앱 [Orchard](https://apporchard.epic.com/Gallery?id=6153)마켓플레이스에서 Microsoft Teams 앱에 액세스할 수 있습니다.

- Microsoft Cloud for Healthcare에 대한 활성 구독 또는 Microsoft Teams EHR Connector 독립 실행형 제품 구독(프로덕션 테스트 중에만 적용).

- 사용자에게는 Microsoft Teams 모임이 포함된 적절한 Microsoft 365 또는 Office 365 라이선스가 있어야 합니다.

- Microsoft Teams는 조직 내에서 채택 및 사용해야 합니다.

- 조직에는 2018년 11월 이후 버전이 있어야 합니다.

- 시스템은 모든 소프트웨어 및 브라우저의 요구 사항을 [충족해야 합니다.](https://docs.microsoft.com/microsoftteams/hardware-requirements-for-the-teams-app)

또한 조직의 다음 사용자로부터 정보를 제공해야 합니다.

- Microsoft 365 관리자

- 엄연한 고객 분석가

> [!Note]
> Epic 기술 전문가에게 모든 Teams Telehealth Epic-Microsoft 제공해달라 요청하세요.

## <a name="connector-setup"></a>커넥터 설정

커넥터 설정에는 다음이 필요합니다.

- [EHR 커넥터 구성 포털 시작](ehr-admin.md#launch-the-ehr-connector-configuration-portal)
- [구성 정보](ehr-admin.md#configuration-information)
- [구성 승인 또는 보기](ehr-admin.md#approve-or-view-configuration)
- [구성 검토 및 완료](ehr-admin.md#review-and-finish-the-configuration)

### <a name="launch-the-ehr-connector-configuration-portal"></a>[EHR 커넥터 구성 포털 시작](#launch-the-ehr-connector-configuration-portal)

Microsoft Teams에서 가상 방문을 시작하려면 EHR 커넥터 구성 포털을 시작하여 의료 조직을 구성합니다. 통합을 테스트하도록 단일 또는 여러 조직을 구성합니다. 구성 포털에서 테스트 및 프로덕션 URL을 구성합니다. 프로덕션 환경으로 이동하기 전에 전적 테스트 환경에서 통합을 테스트합니다.
  
- EHR 커넥터 구성 URL: [https://ehrconnector.teams.microsoft.com](https://ehrconnector.teams.microsoft.com)

조직의 Microsoft 365 관리자 및 Epic 고객 분석가는 구성 포털에서 정보 및 통합 단계를 완료해야 합니다. Epic 구성 단계는 조직에 할당된 기술 전문가 리소스에 문의하세요.

### <a name="configuration-information"></a>[구성 정보](#configuration-information)

이 단계는 **Microsoft 365 관리자가 완료해야 합니다.** Microsoft 365 관리자는 커넥터 구성 포털을 시작하고 Microsoft 자격 증명으로 로그인하여 구성 프로세스를 시작해야 합니다.

이 단계를 완료하려면 Microsoft 365 관리자가 사용자의 전사적 기술 전문가로부터 유효한 FHIR(Fast Health Interoperability Resources) 기본 URL과 구성을 인가할 Epic 고객 분석가의 사용자 이름을 수신해야 합니다. Microsoft 365 관리자는 커넥터 구성 페이지를 시작하고 Microsoft 자격 증명으로 로그인하여 구성 프로세스를 시작해야 합니다.

- FHIR 기본 URL은 서버 FHIR API 엔드포인트에 해당하는 정적 주소입니다. 예제 URL은 `https://lamnahealthcare.org/fihr/auth/connect-ocurprd-oauth/api/FHDST` 다음과 같습니다.

- 구성 승인자 이름은 다음 단계에서 구성을 승인할 책임이 있는 Epic 고객 분석가의 이름입니다. Epic 고객 분석가는 로그인 액세스 권한이 있는 조직의 사람입니다.

  ![EHR 커넥터의 목록에서 구성 승인자 이름이 선택됩니다.](../../media/teams-ehr-connector.png)

### <a name="approve-or-view-configuration"></a>[구성 승인 또는 보기](#approve-or-view-configuration)

승인자로 추가된 의료 조직의 Epic 고객 분석가는 이제 이전 단계와 동일한 EHR 커넥터 URL을 사용하여 Microsoft 365 자격 증명을 사용하여 로그인해야 합니다. 유효성 검사가 성공하면 승인자가 해당 Epic 자격 증명을 사용하여 로그인하여 서사시 조직의 유효성을 검사할지 묻는 메시지가 표시될 것입니다.

> [!Note]
> 조직의 Microsoft 365 관리자 및 Epic 고객 분석가는 같은 사람일 수 있습니다. 이 경우 사용자 이름을 승인자로 추가합니다. 액세스의 유효성을 검사하려면 여전히 Epic에 로그인해야 합니다. 서사시 로그인은 FHIR 기본 URL의 유효성을 검사하는 데만 사용됩니다. Microsoft는 이 로그인을 사용하여 자격 증명을 저장하거나 EHR 데이터에 액세스하지 않습니다.

  ![자격 증명 구성을 확인하고 승인합니다.](../../media/approve-view-configuration.png)

성공적인 성공적인 로그인 후, Epic 고객 분석가는 **구성을** 승인해야 합니다. 구성이 올답지 않은 경우 Microsoft 365 관리자는 Microsoft EHR 커넥터 포털에 다시 로그인하여 원래 구성을 수정할 수 있습니다. 

![EHR 커넥터가 구성되어 있는지 확인하고 구성을 변경하는 옵션을 선택합니다.](../../media/ehc-approve-3.png)

### <a name="review-and-finish-the-configuration"></a>[구성 검토 및 완료](#review-and-finish-the-configuration)

서사시 관리자가 구성 정보를 승인하면 환자 및 공급자 출시를 위한 통합 레코드가 표시됩니다. 이러한 레코드는 Epic에서 가상 방문 구성을 완료하는 데 필요합니다. 자세한 내용은 Epic-Microsoft Teams Telehealth 통합 가이드를 참조하세요.

> [!Note]  
> 필요한 경우 Microsoft 365 또는 Epic 고객 분석가가 구성 포털에 로그인하여 통합 레코드를 보고 조직 구성을 수정할 수 있습니다.

![통합 정보가 표시됩니다.](../../media/finish-configuration.png)

> [!Note]
> 승인 프로세스는 전에 Microsoft 관리자가 구성한 모든 FHIR URL에 대해 Epic 고객 분석가가 완료해야 합니다.

![구성 정보가 승인됩니다.](../../media/approve-configuration-2.png)

## <a name="launch-teams-virtual-visits"></a>Teams 가상 방문 시작

EHR 커넥터 단계 및 전사적 구성을 완료한 후 조직은 Microsoft Teams를 사용하여 비디오 방문을 지원할 준비가 됩니다.

### <a name="virtual-visit-prerequisites"></a>가상 방문 전제

- 시스템은 모든 소프트웨어 및 브라우저의 요구 사항을 [충족해야 합니다.](https://docs.microsoft.com/microsoftteams/hardware-requirements-for-the-teams-app)

- 의료 조직은 서사시 조직과 Microsoft 365 조직 간의 설정을 완료해야 합니다.

### <a name="provider-experience"></a>공급자 환경

조직의 의료 공급자는 또한 대표적인 공급자 애플리케이션(하이퍼스페이스, Haiku, Canto)에서 Microsoft Teams를 통해 가상 방문에 참가할 수 있습니다. 가상 **방문 시작 단추는** 공급자 흐름에 포함되어 있습니다.

공급자 환경의 주요 기능:

- 공급자는 지원되는 브라우저 또는 Microsoft Teams 애플리케이션을 사용하여 가상 방문에 참가할 수 있습니다.

- 공급자는 가상 방문에 처음으로 참가할 때 Microsoft 365 계정으로 일회성 로그인을 해야 합니다.

- 일회성 로그인 후 공급자는 Microsoft Teams의 가상 약속으로 바로 가게 됩니다. (공급자는 Microsoft Teams에 로그인해야 합니다.)

- 공급자는 제공된 약속에 대한 참가자 연결 및 연결 끊기의 실시간 업데이트를 볼 수 있습니다. 공급자는 환자가 가상 방문에 연결된 경우를 볼 수 있습니다.

  ![환자가 있는 가상 방문의 공급자 환경](../../media/ehc-provider-experience-6.png)

### <a name="patient-experience"></a>환자 환경

커넥터는 MyChart 웹 및 모바일을 통해 가상 방문에 참여하는 환자를 지원합니다. 약속 시 환자는 가상 방문 시작 단추를 사용하여 MyChart에서 가상 **방문을 시작할 수** 있습니다.

환자 경험의 주요 기능:

- 환자는 앱 설치 없이 데스크톱 및 모바일의 최신 웹 브라우저에서 가상 방문에 참가할 수 있습니다.

- 환자는 클릭 한 번으로 가상 방문에 참가할 수 있으며 다른 계정이나 로그인이 필요하지 않습니다.

- 환자는 Microsoft 계정을 만들거나 가상 방문을 시작하기 위해 로그인할 필요는 없습니다.

- 환자는 의료 공급자가 약속에 조인하고 가상 방문에 이를 수임할 때까지 대기실에 배치됩니다.

- 가상 방문에 참가하기 전에 로비에서 비디오 및 마이크 테스트를 사용할 수 있습니다.

  ![가상 방문의 환자 경험](../../media/ehc-virtual-visit-5.png)

> [!Note]
> Epic, MyChart, Haiku 및 Canto는 Epic Systems Corporation의 상표입니다.

### <a name="privacy-and-location-of-data"></a>개인 정보 및 데이터의 위치

EHR 시스템에 팀 통합은 통합 및 가상 방문 흐름 중에 사용 및 저장되는 데이터의 양을 최적화합니다. 이 솔루션은 Teams 개인 정보 보호에 설명된 전반적인 Teams 개인 정보 보호 및 데이터 관리 원칙 및 지침을 따릅니다.

Microsoft Teams EHR 커넥터는 식별 가능한 개인 데이터 또는 환자 또는 의료 공급자의 의료 기록을 EHR 시스템에서 저장하거나 전송하지 않습니다. EHR 커넥터에 의해 저장되는 유일한 데이터는 Teams 모임 설정 중에 사용되는 EHR 사용자의 고유 ID입니다. EHR 사용자의 고유 ID는 Microsoft 365 고객 데이터가 저장되는 위치에 설명된 세 가지 지리적 지역 중 [하나에 저장됩니다.](https://docs.microsoft.com/microsoft-365/enterprise/o365-data-locations?view=o365-worldwide#data-center-geographies) 모임 참가자가 Teams에 입력한 모든 채팅, 기록 및 기타 데이터는 기존 저장소 정책에 따라 저장됩니다. Microsoft Teams의 데이터 위치에 대한 자세한 내용은 Teams의 데이터 [위치를 방문하세요.](https://docs.microsoft.com/microsoftteams/location-of-data-in-teams)
