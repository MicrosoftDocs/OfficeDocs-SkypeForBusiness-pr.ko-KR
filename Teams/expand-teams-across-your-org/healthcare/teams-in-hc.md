---
title: 의료 조직을 위한 Teams 시작
author: dstrome
ms.author: dstrome
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: MET150
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
appliesto:
- Microsoft Teams
ms.reviewer: ''
description: 주의 조정, 보안 메시징, telehealth, EHR 통합,에서 일선 worker 시스템 통합을 포함 하는 상태 관리 기능에 대해 알아보세요.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: f2654eab71d240a12f544fbee3521dacd2c49a17
ms.sourcegitcommit: f4f5ad1391b472d64390180c81c2680f011a8a10
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2020
ms.locfileid: "48367668"
---
# <a name="get-started-with-teams-for-healthcare-organizations"></a>의료 조직을 위한 Teams 시작

Microsoft 팀은 병원 및 기타 의료 단체에 유용한 다양 한 기능을 제공 합니다. 팀 기능은 다음을 지원 하기 위해 개발 중에 병원.

- 세심 한 조정 및 공동 작업
- 보안 메시지
- Telehealth
- EHR (전자 건강 보험 기록) 통합 
- Firstline Worker 시스템 통합 

이 섹션의 내용은 모임, 통화, 메시징과 같은 팀의 기본 기능을 기반으로 하며 조직에 이미 팀을 배포한 것으로 가정 합니다. 아직 팀을 롤아웃하기 않은 경우 먼저 [Microsoft 팀을 배포 하는 방법을](../../How-to-roll-out-teams.md)읽어 보세요.

## <a name="care-coordination---microsoft-teams-patients-app"></a>의료 협조-Microsoft 팀 환자 앱

> [!IMPORTANT]
> **2020 년 10 월 30 일에는 환자 앱이 더 이상 사용 되지 않으며 사용자는 더 이상 팀 앱 스토어에서 설치할 수 없게 됩니다. 지금 팀에서 [목록 앱](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) 사용을 시작 하는 것이 좋습니다.**
>
>환자 앱 데이터는 팀을 백업 하는 Office 365 그룹의 그룹 사서함에 저장 됩니다. 환자 앱이 종료 되 면 관련 된 모든 데이터는이 그룹에 보존 되지만 사용자 인터페이스를 통해 더 이상 액세스할 수 없습니다. 현재 사용자는 [목록 앱](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db)을 사용 하 여 목록을 다시 만들 수 있습니다.
>
>[목록 앱](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) 은 모든 팀 사용자를 위해 사전 설치 되어 있으며 모든 팀과 채널에서 탭으로 사용할 수 있습니다. 목록에서 기본 제공 환자 서식 파일을 사용 하거나, 처음부터 또는 Excel로 데이터를 가져오면 환자 목록을 만들 수 있습니다. 조직에서 목록 앱을 관리 하는 방법에 대해 자세히 알아보려면 [목록 앱 관리](../../manage-lists-app.md)를 참조 하세요.

[!INCLUDE [preview-feature](../../includes/preview-feature.md)]

Microsoft 팀에는 이제 건강 보험 조직과 관련 된 의료 협조 솔루션을 포함 하 고 있으며,이를 통해 가장 좋은 환자를 제공할 수 있습니다. 의료 코디 네이션 솔루션의 crux (Microsoft 팀 환자 앱)는 빠른 의료 상호 운용성 리소스 ([Fto r](https://www.hl7.org/fhir/)) 인터페이스를 사용 하 여 microsoft 팀에 연결 되어 있으며, 임상 공동 작업 및 의사 소통을 가능 하 게 하는 유용한 의료 정보를 컨텍스트로 통합 하는 제 1 자 탭 앱입니다.  

의료 코디 네이션 솔루션은 HL7v2 및 FA r과 같은 기존 상태 데이터 표준을 사용 하 여 환자 앱을 EHR 시스템에 연결할 수 있는 선두 독립 소프트웨어 공급 업체 (Isv)와 인터페이스 할 수 있습니다. Microsoft는 다음 업계 리더와 협력 하 여 팀과 전자 상태 레코드 통합을 설정 합니다.

- Datica ( [CMI](https://datica.com/compliant-managed-integration/) 제공)
- Cloverleaf ( [INFOR FA r 브리지](https://pages.infor.com/hcl-infor-fhir-bridge-brochure.html)를 통해)
- Redox ( [r ^ FA r 서버](https://www.redoxengine.com/fhir/)통과)
- Dapasoft ( [FA r의 Corolar](https://www.dapasoft.com/corolar-fhir-server-for-microsoft-teams/))

건강 관리 기관에 대 한 Microsoft 팀을 구현 하는 EHR 통합 및 interop 파트너는 환자 앱에 의료 공급자 조직의 EHR 시스템에 대 한 보안 및 인증 된 연결을 제공 해야 합니다. 이렇게 하면 관련 환자 레코드의 단방향 (읽기 전용) 흐름을 환자 앱으로 이동할 수 있습니다. 환자 앱은 f r 형식을 인식 하므로, 파트너는 HL7v2 등의 다양 한 다른 형식에서 집계 된 데이터를 FTO r DSTU2 또는 STU3으로 변환 하는 역할도 담당 합니다.

<br>

![신중 하 게 조정 및 공동 작업을 보여 주는 그림](../../media/ehr-1.png)

<br>

환자 앱은 EHR (전자 상태 레코드) 시스템과 통합 되며 의사 공급자가 팀의 보안 플랫폼 내에서 실시간으로 환자를 처리할 수 있도록 지원 합니다. 환자 앱은 다음과 같은 문제를 해결 하기 위해 주의 조정 영역에서 첫 번째 주요 투자입니다.

- 환자 경험을 통한 저렴 하 고 중요 한 의사 소통으로 인 한 효율성 향상
- Siloed 관리 burdens를 생성 하는 정보
- 복잡 하 고 단편화 된 공동 작업 도구로 clinicians 간의 불만
- 너무 많은 비 리소스 임상 시간을 구울 수 있는 비효율적인 개인 관리 지원 조정

Microsoft 팀은 의사, clinicians, nurses, 기타 직원이 다음과 같이 효율적으로 공동 작업을 수행할 수 있도록 합니다.

- Office 문서에서 작동 하 고 공동 작업 하는 단일 가상화 된 팀의 일부
- 다른 환자에 대 한 지속적인 대화를 통해 주의가 필요 합니다.
- 탭에서 채널을 사용 하 여 작업을 구조화 하는 방법으로, 정보 원본을 고정 하는 탭의 추가 도움말을 사용할 수 있습니다.
- 팀의 오디오, 비디오, 화면 공유, 기록, 내용 기능을 통해 채널 모임을 사용 하 여 일일 모임 관리
- 환자 앱을 사용 하 여 모니터링 해야 하는 위험성이 높은 환자 목록을 만들고 EHR 시스템에서 최신 정보를 가져옵니다. 환자 앱 자체는 Microsoft 팀에 다음 기능을 추가 합니다.

    - 단일 채널 내에서 여러 환자 목록을 만들 수 있습니다.
    - 구성 가능한 열을 통해 환자에 대해 표시 되는 정보를 보고 정렬 하는 기능.
    - 팀 템플릿을 통해 앱을 자동으로 프로 비전 할 수 있습니다.
    - IOS 및 Android 용 팀 앱에서 모바일 최초의 의료 근로자와 Microsoft 팀 웹 및 데스크톱 클라이언트에 사용할 수 있습니다.
    - 준수 문의 구문 분석을 통해 FDSTU2 및 STU3 버전에 대 한 지원.
    - 모든 보기 및 검색 작업에 대 한 감사 로그를 사용 하 여 HIPAA의 모든 사용자 인터페이스를 보호 합니다.

환자 앱은 팀 확장성 플랫폼을 기반으로 하며, 탭 프레임 워크를 활용 하 여 채널 내에서 다양 한 환자 콘텐츠를 표시 합니다. 다른 팀 앱과 플랫폼 자체에 대해 자세히 알아보려면 [Microsoft 팀 용 앱](/microsoftteams/platform/concepts/apps/apps-overview)을 참조 하세요.  

> [!NOTE]
> 환자 앱은 비공개 preview이 고 FTO r 인터페이스는 beta입니다. 릴리스 버전은 이전 버전과 호환 되지 않을 것으로 예상 됩니다.

![데스크톱 및 모바일 장치에서 환자 앱 스크린샷](../../media/ehr-2.png)

구현 세부 정보는 [Microsoft 팀에 전자 의료 기록 통합](patients-app.md) 을 참조 하세요.

## <a name="teams-templates"></a>팀 서식 파일

팀을 만들기 위한 새 템플릿이 병원 설정에 적용 되도록 개발 되었고 더 많은 내용이 곧 제공 될 예정입니다. 이를 통해 의료 근로자가 다양 한 부서나 wards의 환자을 조정 하는 데 사용 하는 팀을 쉽게 만들 수 있습니다. [의료 조직의 팀 서식 파일 시작을](healthcare-templates.md)참조 하세요. 팀은 cardiology 등의 내부 부서를 위해 시작 하거나 주의를 wards 하 고 더 많은 서식 파일을 개발할 수 있습니다.

## <a name="lists-app"></a>목록 앱

[!INCLUDE [preview-feature](../../includes/preview-feature.md)]

팀의 목록 앱은 팀에서 정보를 추적 하 고 작업을 구성 하는 데 도움이 됩니다. 앱은 모든 팀 사용자를 위해 사전 설치 되어 있으며 모든 팀과 채널에서 탭으로 사용할 수 있습니다. 목록은 미리 정의 된 서식 파일에서 만들거나 Excel로 데이터를 가져와 처음부터 만들 수 있습니다.

관리 팀에서 환자 서식 파일을 사용 하 여 시작 하세요. 환자의 요구 및 상태를 추적 하는 목록을 만들 수 있습니다. 팀에서 Excel 스프레드시트의 기존 환자 데이터를 가져와 목록을 만들 수 있습니다. 이러한 목록은 라운드 및 환자 모니터링과 같은 시나리오에 사용 하 여 주의를 조정할 수 있습니다.

예를 들어, 청구 nurse는 모든 의료 팀 구성원을 포함 하는 환자 목록을 팀에 만듭니다. 라운드 하는 동안 의료 팀은 모바일 장치에서 팀에 액세스 하 고 목록에서 환자 정보를 업데이트 하 여 팀의 모든 구성원이 동기화 상태를 유지할 수 있습니다. 관리 팀에서 주요 상태 성과 지표에 대해 논의 하 고 평가 하는 데 사용 되는 반올림 세션에서는 대규모 디스플레이 화면에서 팀을 사용 하 여이 정보를 공유할 수 있습니다. 사이트를가지고 있지 않은 팀 구성원은 원격으로 참가할 수 있습니다.

다음은 환자 반올림을 위해 설정 된 예제 목록입니다.

:::image type="content" source="../../media/lists-patients-example.png" alt-text="환자 반올림에 대 한 예제 목록 스크린샷":::

자세히 알아보려면 [팀에서 조직의 목록 앱 관리](../../manage-lists-app.md)를 참조 하세요.

## <a name="secure-messaging"></a>보안 메시지

안전한 메시징은 새로운 여러 기능을 포함 하 여 주의 팀 내에서 공동 작업을 지원 합니다.

- 메시지 보낸 사람이 메시지에 대 한 특별 한 우선 순위를 설정할 수 있으므로 메시지를 읽을 때까지 받는 사람이 반복적으로 알림을 받습니다.
- 메시지 보낸 사람은 읽음 확인을 요청할 수 있으므로 메시지를 받는 사람이 보낸 메시지를 읽었을 때 알림을 받습니다.


이러한 기능을 함께 사용 하면 긴급 메시지를 더욱 쉽게 확인 하 고 메시지를 받아서 읽음을 확신할 수 있습니다. 이러한 기능을 사용 하는 새로운 의료 팀은 환자 기준으로 만들 수 있습니다. 이러한 기능은 정책 기반 이며, 개인 또는 전체 팀에 게 할당 될 수 있습니다.

자세한 내용은 [의료 기관에 대 한 보안 메시징 정책 시작](messaging-policies-hc.md) 을 참조 하세요.

보안 메시징과 관련 하 여 의료 기관에서 다른 테 넌 트를 페더레이션 하 여 더 다양 한 테 넌 트 간 통신을 허용 하는 기능도 있습니다. ( [Microsoft 팀에서 외부 액세스 (페더레이션) 관리](../../manage-external-access.md)를 참조 하세요.)

## <a name="firstline-worker-integration"></a>Firstline Worker 통합

Microsoft 팀은 Firstline Worker와 통합 되어 교대 근무 인력 기능을 조정 하는 데 사용할 수 있습니다. [Microsoft 팀에서 조직의 교대 근무 앱 관리](../shifts/manage-the-shifts-app-for-your-organization-in-teams.md)를 참조 하세요.
