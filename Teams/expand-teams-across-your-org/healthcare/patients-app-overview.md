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
description: Teams 관리자를 위한 환자 앱에 대한 자세한 정보
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 24b9813d14654b58018df5d26b94dc5afdaf816725b273c4a18c380bbd03552b
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54308747"
---
# <a name="patients-app-overview"></a>환자 앱 개요

> [!NOTE]
> 2020년 10월 30일부터 환자 앱이 폐기되고 Teams 내 [목록 앱](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db)으로 대체되었습니다. 환자 앱 데이터는 팀을 백업하는 Office 365 그룹의 그룹 사서함에 저장됩니다. 환자 앱과 연결된 모든 데이터는 이 그룹에 보존되지만 사용자 인터페이스를 통해 더 이상 액세스할 수 없습니다. 사용자는 [목록 앱](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db)을 사용하여 목록을 다시 만들 수 있습니다.
>
>목록 기능을 사용하면 의료 조직의 관리 팀은 라운드 및 분야별 팀 모임에서 일반 환자 모니터링에 이르는 다양한 시나리오에 대한 환자 목록을 작성할 수 있습니다. 시작을 위해 목록에서 환자 서식 파일을 체크 아웃합니다. 조직에서 목록 앱을 관리하는 방법에 대한 자세한 내용은 [목록 앱 관리](../../manage-lists-app.md)를 참조하세요.

환자 응용 프로그램은 모든 Teams 사용자가 사용할 수 있는 Microsoft Teams Store 앱입니다. 이 앱을 사용하면 임상 작업자(예: 간호사, 의사, 사회 복지사)로 구성된 환자 의료 팀이 라운드 및 학문 간 팀 모임에서 일반 환자 모니터링에 이르기까지 시나리오에 대한 환자 목록을 큐레이팅하고 검토할 수 있습니다.

앱에는 두 가지 모드가 있습니다.

- FHIR을 통해 EMR에 연결하는 EMR 연결 모드 EMR 연결 모드 앱은 비공개 미리 보기로 유지되며 관심 있는 고객 또는 관리자는 [teamforhealthcare@service.microsoft.com](mailto:teamsforhealthcare@service.microsoft.com)에서 Microsoft 365 조직에 대한 정보가 포함된 전자 메일을 Microsoft에 전달하여 앱에 대한 액세스를 요청할 수 있습니다.
- 의료 팀이 환자 정보를 수동으로 추가/가져올 수 있는 수동 모드 이 응용 프로그램은 Teams 앱 Store에서 사용할 수 있으며 최종 사용자가 비공개 미리 보기로 다운로드할 수 있습니다. 앱은 Teams에서 [앱 설정 정책](../../teams-app-setup-policies.md)을 사용자의 특정 섹션으로 제한할 수 있습니다. 앱에 액세스하려면 테넌트가 탭(Technology Adoption Program)의 일부여야 합니다. 액세스 권한을 요청하는 프로세스를 시작하려면 [teamsforhealthcare@service.microsoft.com](mailto:teamsforhealthcare@service.microsoft.com)로 전자 메일을 보내 주세요.

## <a name="usage-example"></a>사용 예제

의료 병동의 모든 교대 근무에 대한 라운드 세션 동안 임상의는 병동의 환자와 진행 상황에 대한 최신 업데이트를 논의하기 위해 간호소에 모입니다.  주요 지표(반드시 의료적인 것은 아니며 환자의 의료 기록에 명시되지 않을 수 있음)를 강조하고 환자가 진단에 따라 퇴원을 위한 올바른 치유 경로에 있는지 확인합니다. 이러한 환자의 경과를 살펴보기 위해 담당 간호사는 모든 임상의가 추가된 팀에서 환자 앱을 설정하고 환자 목록에 환자를 추가합니다. 라운드 중에 간호사와 환자의 기타 간병인이 모바일 장치에서 Microsoft Teams 및 환자 앱에 액세스하고 장치에서 관련 환자 정보를 업데이트하면 의료 팀의 다른 모든 사람이 해당 업데이트와 메모를보고 계속 확인하고 동기화 상태를 유지할 수 있습니다. 하루에 두 번, 교대 근무가 시작되고 끝날 때 환자 목록을 검토하고 환자 앱을 사용하여 스스로 정보를 파악하고 대형 디스플레이 화면에서 환자 앱을 사용하여 각 환자에 대한 정보를 공유하는 다분야 팀 모임을 진행합니다. 많은 경우, 특정 임상의는 이러한 Teams 회의에 원격으로 전화를 걸어 토론에 계속 참여할 수 있습니다.

## <a name="configure-patients-app"></a>환자 앱 구성

[조직에](../../teams-app-setup-policies.md) 대해 patients 앱을 사용하도록 설정하려면 Microsoft Teams 앱 설정 정책 관리를 참조하세요.

최종 사용자가 소유하거나 관리하는 팀에 대한 환자 앱에 액세스하여 설치하는 방법에 대한 자세한 내용은 [Microsoft Teams 환자 시작하기](https://support.office.com/article/get-started-with-microsoft-teams-patients-aa7daebe-706a-4a65-8ce9-b9b79233f393)를 참조하세요.

<!-- add link out to client doc, doesn't seem to be available yet, Grant is finalizing -->

## <a name="frequently-asked-questions-faq"></a>자주 묻는 질문 (FAQ)

**환자 앱 데이터는 어디에 저장되나요?**

열/필드 스키마, 목록 및 목록 항목(예: 환자)에 입력된 실제 데이터를 포함하여 최종 사용자가 환자 앱에 입력한 모든 데이터는 안전하고 규정을 준수하는 Exchange Online 인프라에 저장됩니다. 모든 데이터는 팀과 연결된 그룹 사서함에 저장됩니다. 이 아키텍처를 통해 환자 앱은 데이터 상주, 정부 클라우드 지원(향후 제공 예정) 및 eDiscovery 지원과 같은 기타 규정 준수/정보 보호 기능을 쉽게 수행할 수 있습니다. 환자 앱은 팀 범위에서 작동합니다. 팀별로 앱 인스턴스를 설치해야 합니다.

<!-- add link to eDiscovery article for the Patients app, Mark Johnson will finalize soon -->

**환자 앱은 어디서 구할 수 있나요?**

관리자가 조직에 환자 앱을 사용하도록 설정한 경우 최종 사용자는 Teams 앱 스토어로 이동하여 구성원인 팀에 환자 앱을 추가할 수 있습니다. 자세한 내용은 [Microsoft Teams에서 앱 설정 정책](../../teams-app-setup-policies.md)을참조하세요.

**병동/병실이 운영되는 방식에 따라 팀에서 환자 앱의 여러 인스턴스를 가질 수 있나요?**

현재는 특정 팀에 대해 환자 앱 인스턴스를 일반 채널에만 한 개 설치할 수 있습니다. 그러나 앱 내에서 다중 채널 또는 격리/분리 시나리오를 해결하기 위해 여러 목록을 만들 수 있습니다. 기본적으로 팀의 모든 구성원은 일반 채널의 환자 탭에 액세스할 수 있습니다. 

**환자 앱에서 모든 데이터를 내보낼 수 있나요?**
지금은 아니지만 이 기능은 곧 제공될 예정입니다. 

**이 앱은 PHI를 수용하기 떄문에 무단 액세스 또는 규정 준수를 방지하기 위한 감사 기능이 있나요?**

네, 있습니다. 환자 앱에서 Microsoft Teams 사용자가 수행하는 모든 단일 UI 작업은 감사를 받으며, 이 기능은 보안 및 규정 준수 센터에서 사용할 수 있습니다. 자세한 내용은 [환자 앱에 대한 감사 로그](patients-audit.md)에 설명되어 있습니다.

