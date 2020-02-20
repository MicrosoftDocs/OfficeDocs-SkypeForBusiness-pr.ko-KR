---
title: '팀 용 환자 앱 관리자 '
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
description: 팀 용 환자 앱 관리자
ms.openlocfilehash: 4c4eaced1b7e3c328d589906ac50cfb8ac805ea3
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42153790"
---
# <a name="patients-app-overview"></a>환자 앱 개요

환자 응용 프로그램은 모든 팀 사용자가 사용할 수 있는 Microsoft 팀 스토어 앱입니다. 앱은 임상 팀 (예: Nurses, 의사, 사교 작업자)으로 구성 되는 환자 팀에서 환자 목록을 반올림 및 검토 하 여 라운드 및 interdisciplinary 팀 모임에서 일반 환자 모니터링에 이르기까지 다양 한 시나리오를 만들 수 있습니다.

앱에는 두 가지 모드가 있습니다.

- Emr를 통해 FA r을 통해 연결 하는 EMR 연결 모드입니다. EMR 연결 모드 앱은 비공개 미리 보기에서 유지 되며, 관련 고객 또는 관리자가 Office 365 테 넌 트에 대 한 정보로 [teamsforhealthcare@service.microsoft.com](mailto:teamsforhealthcare@service.microsoft.com) 에서 Microsoft 전자 메일을 삭제 하 여 앱에 대 한 액세스를 요청할 수 있습니다.
- 주의 팀이 환자 정보를 수동으로 추가/지참물 할 수 있도록 해 주는 수동 모드입니다. 이 응용 프로그램은 최종 사용자가 비공개 미리 보기에서 다운로드할 수 있는 팀 앱 스토어에서 제공 됩니다. 팀에서 [앱 설치 정책을](../../teams-app-setup-policies.md) 사용 하 여 특정 사용자 섹션으로 앱을 제한할 수 있습니다. 앱에 대 한 액세스 권한을 얻으려면 테 넌 트가 기술 채택 프로그램에 포함 되어 있어야 합니다 (탭). [Teamsforhealthcare@service.microsoft.com](mailto:teamsforhealthcare@service.microsoft.com) 에서 전자 메일을 삭제 하 여 액세스 요청 프로세스를 시작 하세요.

## <a name="usage-example"></a>사용 예제

의료 wards의 모든 교대 근무에 대 한 세션을 반올림 하는 동안 nursing 스테이션에서 clinicians를 수집 하 여 진행 중인 환자에 대 한 최신 업데이트를 논의 합니다.  중요 한 주요 메트릭 (반드시 의료이 아닌 환자의 의료 기록)을 강조 표시 하 고 해당 진단을 기반으로 방전 시킬 수 있는 적절 한 glide 경로에 환자를 사용 하 고 있는지 확인 합니다. 이러한 환자를 반올림 하기 위해, 무료 nurse는 모든 clinicians이 추가 된 팀에 환자 앱을 설정 하 고 환자 목록에 환자를 추가 합니다. 라운드를 진행 하는 동안 환자에 대 한 nurses 및 기타 주의 givers는 모바일 장치에서 Microsoft 팀과 환자 앱에 액세스 하 고, 해당 장치에서 관련 환자 정보를 업데이트 하 고, 의료 팀의 다른 사용자가 해당 업데이트 및 메모를 볼 수 있습니다. 동기화 상태를 유지 합니다. 교대 근무의 시작 및 끝 부분에는 여러 disciplinary 팀 모임이 있어 환자 목록을 통해 환자 앱을 사용 하 고, 큰 디스플레이 화면에서 환자 앱을 사용 하 여 각 환자에 대 한 정보를 공유할 수 있습니다. 일부 경우에 따라 일부 clinicians는 이러한 팀 모임에 원격으로 전화를 걸 수 있으며 여전히 토론에 포함 될 수도 있습니다.

## <a name="configure-patients-app"></a>환자 앱 구성

EMR 모드 환자 앱을 사용 하기 위해 환경을 준비 하는 방법에 대 한 자세한 내용은 [Microsoft 팀에 전자 의료 기록 통합](patients-app.md)을 참조 하세요. 또한 조직에 대해 환자 앱을 사용 하도록 설정 하려면 [Microsoft 팀에서 앱 설정 관리 정책도](../../teams-app-setup-policies.md) 참조 해야 합니다.

최종 사용자가 자신이 소유 하거나 관리 하는 팀에 환자 앱에 액세스 하 여 설치 하는 방법에 대 한 자세한 내용은 [Microsoft 팀 시작](https://support.office.com/article/get-started-with-microsoft-teams-patients-aa7daebe-706a-4a65-8ce9-b9b79233f393) 을 참조 하세요 환자 

<!-- add link out to client doc, doesn't seem to be available yet, Grant is finalizing -->

## <a name="frequently-asked-questions-faq"></a>자주 묻는 질문 (FAQ)

**환자 앱 데이터는 어디에 저장 되나요?**

최종 사용자가 열/필드 스키마를 포함 하 여 환자 앱에 입력 한 모든 데이터는 목록 및 목록 항목에 입력 한 실제 데이터 (즉, 환자)가 보안 및 준수 Exchange Online 인프라에 저장 됩니다. 모든 데이터는 팀과 연결 된 그룹 사서함에 저장 됩니다. 이 아키텍처는 환자 앱에서 데이터 영주권, 정부 구름 지원 (향후 출시 예정) 및 eDiscovery 지원 등의 기타 규정 준수/정보 보호 기능을 쉽게 처리할 수 있도록 합니다. 환자 앱은 팀 범위에서 작동 합니다. 팀 당 앱의 인스턴스를 설치 해야 합니다.

<!-- add link to eDiscovery article for the Patients app, Mark Johnson will finalize soon -->

**환자 앱은 어디에서 받을 수 있나요?**

관리자가 조직에 환자 앱을 사용 하도록 설정한 경우, 최종 사용자는 팀 app store로 이동 하 여 환자 앱을 구성원으로 속해 있는 팀에 추가할 수 있습니다. 자세한 내용은 [Microsoft 팀에서 앱 설정 정책 관리](../../teams-app-setup-policies.md)를 참조 하세요.

**팀에서 환자 앱의 여러 인스턴스를 사용할 수 있나요?이는 내 말/단위가 작동 하는 방식입니다.**

현재는 주어진 팀에 대 한 환자 앱의 인스턴스 중 하나만 설치 하 고 일반 채널에만 설치할 수 있습니다. 그러나 앱 내에서 여러 목록을 만들어 다중 채널 또는 격리/구분 시나리오를 처리할 수 있습니다. 기본적으로 팀의 모든 구성원은 일반 채널의 환자 탭에 액세스할 수 있습니다. 

**환자 앱에서 모든 데이터를 내보낼 수 있나요?**
지금 당장,이 기능은 곧 제공 될 예정입니다. 

**이 앱은 매우 유용 하 게 사용할 수 있으므로 승인 되지 않은 액세스 또는 규정 준수를 방지 하는 감사가 있나요?**

예. 환자 앱의 Microsoft 팀 사용자가 수행한 모든 단일 UI 동작은 감사 되 고 보안 및 준수 센터에서 사용할 수 있습니다. 세부 정보는 [여기](patients-audit.md) 문서에 설명 되어 있습니다.

## <a name="related-topics"></a>관련 주제

[Microsoft Teams에 전자 의료 레코드 통합](patients-app.md)
