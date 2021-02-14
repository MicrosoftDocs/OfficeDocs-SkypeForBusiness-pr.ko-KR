---
title: 'Teams 관리자를 위한 환자 앱 '
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
MS.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
appliesto:
- Microsoft Teams
ms.reviewer: anach
description: Teams 관리자를 위한 환자 앱에 대해 자세히 알아보기
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 92bc7581610abf1dc8baab17d2e9d23abb6c6fd3
ms.sourcegitcommit: beaaee10019f4eda746f348888a4a3c2aaa6f196
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2020
ms.locfileid: "48803506"
---
# <a name="patients-app-overview"></a>환자 앱 개요

> [!NOTE]
> 2020년 10월 30일부로 환자 앱은 사용 중지되고 Teams의 [목록](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) 앱으로 대체됩니다. 환자 앱 데이터는 팀을 백업하는 Office 365 그룹의 그룹 사서함에 저장됩니다. 환자 앱과 연결된 모든 데이터는 이 그룹에 유지되지만 사용자 인터페이스를 통해 더 이상 액세스할 수 없습니다. 사용자는 목록 앱을 사용하여 목록을 다시 [만들 수 있습니다.](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db)
>
>목록을 사용하여 의료 조직의 관리 팀은 라운드 및학 간 팀 모임에서 일반 환자 모니터링에 이르는 시나리오에 대한 환자 목록을 만들 수 있습니다. 시작을 위해 목록에서 환자 서식 파일을 확인해 하세요. 조직에서 목록 앱을 관리하는 방법에 대한 자세한 내용은 목록 앱 [관리를 참조하세요.](../../manage-lists-app.md)

환자 애플리케이션은 모든 Teams 사용자가 사용할 수 있는 Microsoft Teams 스토어 앱입니다. 이 앱을 사용하면 의료 근로자(예: 간호사, 의사, 사회복지사)로 구성된 환자 의료 팀이 라운드 및 전문 간호사 팀 회의에서 일반 환자 모니터링에 이르는 시나리오에 대한 환자 목록을 큐레이터하고 검토할 수 있습니다.

앱에는 다음 두 가지 모드가 있습니다.

- FHIR을 통해 EMR에 연결하는 EMR 연결 모드입니다. EMR 연결 모드 앱은 비공개 [미리](mailto:teamsforhealthcare@service.microsoft.com) 보기로 유지되고 관심 있는 고객 또는 관리자는 Microsoft 365 조직에 대한 정보가 있는 teamsforhealthcare@service.microsoft.com Microsoft에 전자 메일을 삭제하여 앱에 대한 액세스를 요청할 수 있습니다.
- 의료 팀이 환자 정보를 수동으로 추가/가져올 수 있는 수동 모드입니다. 이 애플리케이션은 최종 사용자가 비공개 미리 보기로 다운로드할 수 있도록 Teams 앱 스토어에서 사용할 수 있습니다. Teams에서 앱 설정 정책을 사용하여 사용자의 특정 섹션으로 [앱을 제한할](../../teams-app-setup-policies.md) 수 있습니다. 앱에 액세스하려면 테넌트가 TAP(기술 채택 프로그램)에 참여해야 합니다. 액세스 권한을 요청하는 [](mailto:teamsforhealthcare@service.microsoft.com) 프로세스를 teamsforhealthcare@service.microsoft.com 전자 메일을 보내 주세요.

## <a name="usage-example"></a>사용 예

의료 와드의 모든 교대 근무에 대해 반올라 세션을 진행하는 동안 의료진은 간호소에 모인 후 환자와 진행 상황을 논의합니다.  주요 중요한 메트릭(반드시 의료 또는 환자의 의료 기록에 명시적이지 않은 것)을 강조 표시하고 환자가 진단에 따라 퇴원할 올바른 경로에 있도록 합니다. 이러한 환자를 반올려하기 위해 담당 간호사는 모든 의사가 추가되는 팀에서 환자 앱을 설정하고 환자를 환자 목록에 추가합니다. 라운드 중에 간호사 및 환자를 위한 다른 진료 제공자는 모바일 장치에서 Microsoft Teams 및 환자 앱에 액세스하고 해당 장치에서 관련 환자 정보를 업데이트한 다음 의료 팀의 다른 모든 사람이 해당 업데이트와 메모를 보고 동기화된 상태일 수 있습니다. 교대 근무가 시작 및 종료될 때도 매일 두 번 다학제 팀 모임을 통해 환자 목록을 이동하고 환자 앱을 사용하여 환자 앱을 직접 접지하고 큰 디스플레이 화면에서 환자 앱을 사용하여 각 환자에 대한 정보를 공유할 수 있습니다. 종종 특정 의료진이 원격으로 이러한 Teams 모임에 전화를 걸 수도 있으며 여전히 토론에 참여할 수 있습니다.

## <a name="configure-patients-app"></a>환자 앱 구성

EMR 모드 Patients 앱을 사용하기 위해 환경을 준비하는 방법에 대한 자세한 내용은 [Microsoft Teams에 Electronic Healthcare 레코드](patients-app.md)통합을 참조하세요. 또한 조직에 환자 앱을 사용하도록 [설정하려면 Microsoft Teams에서](../../teams-app-setup-policies.md) 앱 설정 정책 관리도 참조해야 합니다.

최종 사용자가 환자 앱을 소유하거나 관리하는 팀에 액세스하고 설치하는 방법에 대한 자세한 내용은 Microsoft Teams 환자 시작을 [참조하세요.](https://support.office.com/article/get-started-with-microsoft-teams-patients-aa7daebe-706a-4a65-8ce9-b9b79233f393)

<!-- add link out to client doc, doesn't seem to be available yet, Grant is finalizing -->

## <a name="frequently-asked-questions-faq"></a>FAQ(질문과 대답)

**환자 앱 데이터는 어디에 저장하나요?**

열/필드 스마마, 목록 및 목록 항목(예: 환자)에 입력된 실제 데이터를 포함하여 최종 사용자가 환자 앱에 입력한 모든 데이터는 안전하고 호환되는 Exchange Online 인프라에 저장됩니다. 모든 데이터는 팀과 연결된 그룹 사서함에 저장됩니다. 이 아키텍처를 통해 환자 앱은 데이터 레지던시, 정부 클라우드 지원(향후 제공) 및 eDiscovery 지원과 같은 기타 규정 준수/정보 보호 기능을 쉽게 이행할 수 있습니다. 환자 앱은 팀 범위에서 운영됩니다. 팀당 앱의 인스턴스를 설치해야 합니다.

<!-- add link to eDiscovery article for the Patients app, Mark Johnson will finalize soon -->

**환자 앱을 어디에서 획득할 수 있나요?**

관리자가 환자 앱을 사용하도록 설정한 경우 모든 최종 사용자는 Teams 앱 스토어로 이동하여 구성원인 팀에 환자 앱을 추가할 수 있습니다. 자세한 내용은 [Microsoft Teams에서 앱 설정 정책 관리를 참조하세요.](../../teams-app-setup-policies.md)

**와드/단위가 작동하는 방식이기 때문에 환자 앱의 여러 인스턴스가 팀에 있을 수 있나요?**

현재는 특정 팀에 대해 환자 앱의 인스턴스를 하나만 설치할 수 있으며 일반 채널에만 설치할 수 있습니다. 그러나 앱 내에서 다중 채널 또는 분리/분리 시나리오를 해결하기 위해 여러 목록을 만들 수 있습니다. 기본적으로 팀의 모든 구성원은 일반 채널의 환자 탭에 액세스할 수 있습니다. 

**Patients 앱에서 모든 데이터를 내보낼 수 있나요?**
지금은 그렇지 않지만 이 기능은 곧 출시될 예정입니다. 

**이 앱은 PHI를 수용하기 때문에 무단 액세스 또는 규정 준수를 방지하기 위한 감사가 있나요?**

예, 있습니다. Patients 앱의 Microsoft Teams 사용자가 수행한 모든 단일 UI 작업은 보안 및 규정 준수 센터에서 감사 및 사용할 수 있습니다. 자세한 내용은 환자 앱의 감사 [로그에 설명됩니다.](patients-audit.md)

## <a name="related-topics"></a>관련 항목

[Microsoft Teams에 전자 의료 레코드 통합](patients-app.md)
