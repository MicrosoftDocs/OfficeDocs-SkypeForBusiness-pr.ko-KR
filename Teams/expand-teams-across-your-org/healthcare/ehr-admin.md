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
ms.openlocfilehash: 37b93533aeff6b519b1f5a65cf49211464b41388
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51096282"
---
# <a name="virtual-visits-with-teams---integration-into-ehr"></a>Teams를 사용하여 가상 방문 - EHR에 통

Microsoft Teams EHR(전자 건강 기록) 커넥터를 사용하면 의료자가 EHR 시스템에서 직접 Teams의 다른 공급자와 가상 환자 방문 또는 상담을 쉽게 시작할 수 있습니다. Microsoft 365 클라우드를 기반으로 구축된 Microsoft Teams는 HIPAA, HITECH 인증 준수를 지원하는 단일 허브에서 채팅, 비디오, 음성, 의료 도구를 사용하여 간단하고 안전하게 공동 작업 및 커뮤니케이션을 수행할 수 있도록 지원합니다.
Teams의 통신 및 공동 작업 플랫폼을 사용하면 임상의들이 파편화된 시스템의 어수선한 작업을 손쉽게 제거하여 최상의 서비스를 제공하는 데 시간을 투자할 수 있습니다. Microsoft Teams EHR(전자 건강 기록) 커넥터는 다음과 같은 기능을 제공합니다.

- 공급자 및 환자 포털에서 Teams 가상 방문을 시작합니다.
- 이벤트 연결 및 연결 해제 시에 EHR 메타데이터에 다시 기록하여 자동 감사 및 레코드 유지를 지원합니다.
- 기존 병원 및 환자 워크플로에 통합되어 Microsoft Teams를 동시에 사용할 수 있습니다.

  EHR 포털에서 가상 방문을 관리하는 방법에 대한 비디오를 시청해 보세요.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4HAtn]

## <a name="before-you-begin"></a>시작하기 전에

EHR 커넥터를 통합하기 전에 다음과 같은 필수 구성 요소가 갖춰져 있는지 확인해야 합니다.

- [Epic의 App Orchard 마켓 플레이스](https://apporchard.epic.com/Gallery?id=6153)의 Microsoft Teams 앱에 대한 액세스.

- 의료용 Microsoft 클라우드에 대한 활성 가입 또는 Microsoft Teams EHR 커넥터 독립 실행형 제품 구독(제품 테스트 중에는 강제 실행만 가능).

- 사용자에게 Microsoft Teams 모임을 포함하는 적절한 Microsoft 365 또는 Office 365 라이선스가 있어야 합니다.

- 조직 내부에서 Microsoft Teams를 채택하고 사용해야 합니다.

- 조직에 2018년 11월 버전 이상이 설치되어 있어야 합니다.

- 시스템이 모든 [소프트웨어 및 브라우저 필수 요구 사항](../../hardware-requirements-for-the-teams-app.md)을 충족해야 합니다.

또한 조직의 다음 사용자로부터 정보를 제공 받아야 합니다.

- Microsoft 365 관리자

- Epic 고객 분석가

> [!Note]
> [Epic-Microsoft Teams Telehealth 통합](https://galaxy.epic.com/Search/GetFile?Url=1!68!100!100100357) 가이드를 에픽 기술 전문가와 함께 검토합니다. 모든 전제가 완료된지 확인 합니다. 

## <a name="connector-setup"></a>커넥터 설정

커넥터를 설정하려면 다음이 필요합니다.

- [EHR Connector 구성 포털 시작](ehr-admin.md#launch-the-ehr-connector-configuration-portal)
- [구성 정보](ehr-admin.md#configuration-information)
- [구성 승인 또는 보기](ehr-admin.md#approve-or-view-configuration)
- [구성 검토 및 완료](ehr-admin.md#review-and-finish-the-configuration)

### <a name="launch-the-ehr-connector-configuration-portal"></a>[EHR Connector 구성 포털 시작](#launch-the-ehr-connector-configuration-portal)

의료 조직이 Microsoft Teams로 가상 방문을 시작하도록 구성하려면 먼저 의료 조직이 EHR 커넥터 구성 포털을 시작합니다. 단일 조직 또는 여러 조직을 구성하여 통합을 테스트합니다. 구성 포털에서 테스트 및 프로덕션 URL을 구성합니다. 프로덕션 환경으로 이동하기 전에, Epic의 테스트 환경에서의 통합을 테스트하세요.
  
- EHR 커넥터 구성 URL: [https://ehrconnector.teams.microsoft.com](https://ehrconnector.teams.microsoft.com)

조직의 Microsoft 365 관리자 및 Epic 고객 관리 분석가가 구성 포털의 정보 및 통합 단계를 완료해야 합니다. Epic 구성 단계에 대한 자세한 내용은 조직에 할당된 Epic 기술 전문가 리소스에 문의하세요.

### <a name="configuration-information"></a>[구성 정보](#configuration-information)

이 단계는 **Microsoft 365 관리자** 가 완료해야 합니다. Microsoft 365 관리자는 커넥터 구성 포털을 시작하고 Microsoft 자격 증명으로 로그인하여 구성 프로세스를 시작해야 합니다.

이 단계를 완료하려면 Microsoft 365 관리자가 사용자의 사이트에 있는 Epic 기술 전문가로부터 유효한 FHIR(전자 의료 기록 교환) 기본 URL과 구성을 승인할 Epic 고객 분석가의 사용자 이름을 제공 받아야 합니다. Microsoft 365 관리자는 커넥터 구성 페이지를 시작하고 Microsoft 자격 증명으로 로그인하여 구성 프로세스를 시작해야 합니다.

- FHIR 기본 URL은 서버 FHIR API 끝점에 해당하는 정적 주소입니다. 예제 URL은 `https://lamnahealthcare.org/fihr/auth/connect-ocurprd-oauth/api/FHDST`입니다.

- 구성 승인자 이름은 다음 단계에서 구성 승인을 담당할 Epic 고객 분석가의 이름입니다. Epic 고객 분석가는 Epic에 대한 로그인 권한이 있는 조직 내 사용자입니다.

  ![구성 승인자의 이름이 EHR 커넥터의 목록에서 선택됩니다.](../../media/teams-ehr-connector.png)

### <a name="approve-or-view-configuration"></a>[구성 승인 또는 보기](#approve-or-view-configuration)

승인자로 추가된 의료 조직에 대한 Epic 고객 분석가는 이제 이전 단계와 동일한 EHR 커넥터 URL을 사용하여 Microsoft 365 자격 증명을 사용하여 로그인해야 합니다. 유효성 검사가 완료되면, 승인자는 Epic 자격 증명을 사용하여 로그인하여 Epic 조직의 유효성을 검사하라는 요청을 받게 됩니다.

> [!Note]
> 조직의 Microsoft 365 관리자 및 Epic 고객 관리 분석가가 같은 사람일 수 있습니다. 이 경우 사용자 이름을 승인자로 추가합니다. 액세스의 유효성을 검사하려면 여전히 Epic에 로그인해야 합니다. Epic 로그인은 FHIR 기본 URL의 유효성을 검사하는 데만 사용됩니다. Microsoft는 이 로그인을 통해 자격 증명을 저장하거나 EHR 데이터에 액세스하지 않습니다.

  ![자격 증명 구성을 확인하고 승인합니다.](../../media/approve-view-configuration.png)

로그인이 성공적으로 완료된 후에는 Epic 고객 분석가가 **반드시** 구성을 승인해야 합니다. 구성이 올바르지 않은 경우 Microsoft 365 관리자는 Microsoft EHR 커넥터 포털에 다시 로그인하여 원래 구성을 수정할 수 있습니다. 

![EHR 커넥터가 구성되어 있는지 확인하고 구성을 변경하는 옵션을 선택합니다.](../../media/ehc-approve-3.png)

### <a name="review-and-finish-the-configuration"></a>[구성 검토 및 완료](#review-and-finish-the-configuration)

Epic 관리자가 구성 정보를 승인하면 환자 및 공급자 출시에 대한 통합 레코드가 표시됩니다. 이러한 레코드는 Epic의 가상 방문 구성을 완료하는 데 필요합니다. 자세한 내용은 Microsoft Teams 원격의료 통합 가이드를 참조하세요.

> [!Note]  
> 필요한 경우 Microsoft 365 또는 Epic 고객 관리 분석가가 구성 포털에 로그인하여 통합 레코드를 보고 조직 구성을 수정할 수 있습니다.

![통합 정보가 표시됩니다.](../../media/finish-configuration.png)

> [!Note]
> 앞의 Microsoft 관리자가 구성한 모든 FHIR URL에 대해 Epic 고객 관리 분석가가 승인 프로세스를 완료해야 합니다.

![구성 정보가 승인됩니다.](../../media/approve-configuration-2.png)

## <a name="launch-teams-virtual-visits"></a>Teams 가상 방문 시작

EHR 커넥터 단계와 Epic 구성을 완료했다면, 조직에서 Microsoft Teams를 통해 비디오 방문을 지원할 준비가 된 것입니다.

### <a name="virtual-visit-prerequisites"></a>가상 방문 필수 구성 요소

- 시스템이 모든 [소프트웨어 및 브라우저 필수 요구 사항](../../hardware-requirements-for-the-teams-app.md)을 충족해야 합니다.

- 의료 조직은 Epic 조직과 Microsoft 365 조직 간의 설정을 완료해야 합니다.

### <a name="provider-experience"></a>공급자 환경

조직의 의료 공급자는 Epic 공급자 응용 프로그램 (Hyperspace, Haiku, Canto)에서 Microsoft Teams와 함께 가상 방문에 참여할 수도 있습니다. **가상 방문 시작** 단추는 공급자 흐름에 포함되어 있습니다.

공급자 환경의 주요 기능:

- 공급자는 지원되는 브라우저 또는 Microsoft Teams 응용 프로그램을 사용하여 가상 방문에 참여할 수 있습니다.

- 공급자는 가상 방문에 처음 참여할 때 Microsoft 365 계정으로 1회 로그인해야 합니다.

- 1회 로그인 후 공급자는 Microsoft Teams의 가상 약속으로 바로 이동합니다. (공급자는 반드시 Microsoft Teams에 로그인해야 합니다.)

- 공급자는 주어진 약속에 대한 참가자의 연결 및 연결 해제 실시간 업데이트를 확인할 수 있습니다. 공급자는 환자가 가상 방문에 연결된 시점을 확인할 수 있습니다.

  ![환자가 가상으로 방문하는 공급자 환경](../../media/ehc-provider-experience-6.png)

### <a name="patient-experience"></a>환자 환경

커넥터는 MyChart 웹 및 모바일을 통해 가상 방문에 참여하는 환자를 지원합니다. 약속 시점에 환자는 **가상 방문 시작** 단추를 사용하여 MyChart에서 가상 방문을 시작할 있습니다.

환자 환경의 주요 기능:

- 환자는 앱을 설치하지 않고도 데스크톱 및 모바일의 최신 웹 브라우저에서 가상 방문에 참여할 수 있습니다.

- 환자는 클릭 한 번으로 가상 방문에 참여할 수 있으며 다른 계정이나 로그인이 필요하지 않습니다.

- 환자는 Microsoft 계정을 만들거나 가상 방문을 시작하기 위해 로그인할 필요가 없습니다.

- 의료 공급자가 약속에 참여하고 가상 방문을 인정할 때까지 환자는 대기실에 있습니다.

- 가상 방문에 참가하기 전에 대기실에서 비디오와 마이크를 테스트할 수 있습니다.

  ![가상 방문의 환자 환경](../../media/ehc-virtual-visit-5.png)

> [!Note]
> Epic, MyChart, Haiku 및 Canto는 Epic Systems Corporation의 상표입니다.

### <a name="privacy-and-location-of-data"></a>개인 정보 및 데이터의 위치

Teams와 EHR 시스템의 통합은 통합 및 가상 방문 흐름 중에 사용 및 저장되는 데이터의 양을 최적화합니다. 이 솔루션은 전체 Teams 개인 정보 보호 및 데이터 관리 원칙과 Teams 개인 정보에 설명된 지침을 따릅니다.

Microsoft Teams EHR 커넥터는 EHR 시스템에서 식별할 수 있는 개인 데이터나 환자 또는 의료 공급자의 건강 기록을 저장하거나 전송하지 않습니다. EHR 커넥터에 의해 저장되는 데이터는 팀 모임 설정 중에 사용되는 EHR 사용자의 고유 ID뿐입니다. EHR 사용자의 고유 ID는 [Microsoft 365 고객 데이터가 저장되는 위치](/microsoft-365/enterprise/o365-data-locations?view=o365-worldwide#data-center-geographies)에 설명된 세 가지 지역 중 하나에 저장됩니다. 모임 참가자가 Teams에 입력한 모든 채팅, 녹음/녹화 및 기타 데이터는 기존 저장소 정책에 따라 저장됩니다. Microsoft Teams의 데이터 위치에 대해 자세히 알아보려면 [Teams의 데이터 위치](../../location-of-data-in-teams.md)를 방문하세요.