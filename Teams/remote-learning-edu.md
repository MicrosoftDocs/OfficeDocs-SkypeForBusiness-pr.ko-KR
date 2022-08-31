---
title: 원격 학습을 위해 Microsoft Teams 시작
author: DaniEASmith
ms.author: danismith
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: karsmith, lakuan
description: EDU용 Microsoft Teams에 대한 원격 학습 시작 지침입니다.
ms.localizationpriority: high
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- remotework
appliesto:
- Microsoft Teams
ms.openlocfilehash: 231007549102b8cddc02a0d2a5d29266662b4b2f
ms.sourcegitcommit: 7a1fb6e15c21368afa34cd212865437781f721e2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/31/2022
ms.locfileid: "67466026"
---
# <a name="get-started-with-microsoft-teams-for-remote-learning"></a>원격 학습을 위해 Microsoft Teams 시작

이 문서에서는 Microsoft Teams를 사용하여 원격 학습을 위해 교육 기관을 설정하기 위한 IT 관리 단계를 설명합니다.

Teams 내에서 **교육자는 다음을** 수행할 수 있습니다.

- 학생들과 빠르게 대화를 나눌 수 있습니다.
- 파일 및 웹 사이트를 공유합니다.
- OneNote 수업용 전자 필기장을 만듭니다.
  - 대화형 단원을 구성합니다.
  - 효과적이고 시기 적절한 피드백을 제공합니다.
- 할당을 배포하고 채점합니다.
- 전문 학습 커뮤니티에서 교육 자료를 공유합니다.

**교육 관리자 및 직원은 다음을** 수행할 수 있습니다.

- 이벤트를 최신 상태로 유지합니다.
- 공지 사항 및 토폴로지 대화를 위해 교직원 Teams를 사용하여 공동 작업합니다.

# <a name="accounts--licenses"></a>[계정 & 라이선스](#tab/accounts)

## <a name="user-accounts-licenses-and-identity-security"></a>사용자 계정, 라이선스 및 ID 보안

Teams는 Microsoft 365를 사용하여 사용자를 인증하고 서비스를 제공합니다. 모든 사용자는 공동 작업을 용이하게 하기 위해 Microsoft 365 ID를 설정해야 합니다.

사용자 ID가 아직 없는 경우 이 프로세스에 따라 설정합니다.

1. [학교 데이터 동기화를 사용하여 사용자를 만듭니다](/microsoft-365/education/deploy/school-data-sync).
2. [사용자에게 라이선스를 할당합니다](teams-edu-licensing.md).
3. [Microsoft 365 그룹을 만듭니다](Office-365-groups.md).
4. [Exchange를 설정합니다](Exchange-Teams-interact.md).
5. [SharePoint 및 OneDrive를 설정합니다](SharePoint-OneDrive-interact.md).
6. [Google 전자 메일이 있는 사용자를 설정합니다](/microsoft-365/education/deploy/enabling-teams-for-education-for-google-users).

Microsoft Teams는 무료 A1 교육 계획을 포함하여 모든 Microsoft 365 플랜에 포함되어 있습니다.

Microsoft 365 배포 및 Teams 설정에 대한 지침은 [Microsoft 365 테넌트 만들기](/microsoft-365/education/deploy/create-your-office-365-tenant)를 확인하세요.

# <a name="set-up-teams"></a>[Teams 설정](#tab/setup)

## <a name="easily-set-up-teams"></a>Teams 간편하게 설정

Teams를 시작하고 실행하기 위해 수행해야 하는 두 가지 작업은 다음과 같습니다.

### <a name="1-allow-users-to-create-teams"></a>1. 사용자가 Teams를 만들 수 있도록 허용

**기본적으로 모든 사용자가 Microsoft 365 그룹 및 Teams를 만들 수** 있지만 이 기능이 항상 적절하지는 않을 수 있습니다.

예를 들어 일부 학교에서는 학생이 감독 없이 Teams를 만들지 못하도록 제한하려고 할 수 있습니다. Microsoft 365 그룹 및 팀 만들기는 [특정 보안 그룹으로 제한](/microsoft-365/admin/create-groups/manage-creation-of-groups)될 수 있습니다.

고등 교육 기관의 경우 학생을 포함한 모든 사람이 수업, 연구, 그룹 프로젝트 및 연구 그룹을 위한 팀을 만들 수 있도록 허용하는 것이 좋습니다.

Teams를 만드는 방법에 대한 연습은 [Microsoft Teams에서 수업 팀 만들기를 참조하세요](https://support.office.com/article/create-a-class-team-in-microsoft-teams-preview-fae422eb-58b7-4431-9ff2-a4b9b6ae7c5b).

### <a name="2-configure-user-experiences-using-policies"></a>2. 정책을 사용하여 사용자 환경 구성

[!INCLUDE [policy-wizard-edu](includes/policy-wizard-edu.md)]

> [!NOTE]
> [원거리 학습을 위해 Teams에서 학생들을 안전하게 보호](https://support.office.com/article/f00fa399-0473-4d31-ab72-644c137e11c8)하세요.
>
> EDU 정책 권장 사항을 보려면 [교육용 Teams 정책 및 정책 패키지를](policy-packages-edu.md) 참조하세요.

Teams 정책은 특정 사용자 또는 그룹에 사용할 수 있는 기능을 제어합니다. 정책은 비공개 채팅, 비공개 통화, 모임 예약, 공유할 수 있는 콘텐츠 형식 등을 사용할 수 있는 사용자를 정의할 수 있습니다.

**고등 교육 직원, 교육자 및 학생은** 기본(글로벌) 정책을 사용할 수 있습니다. [번역 기능](messaging-policies-in-teams.md#messaging-policy-settings) 및 [자동 모임 기록](meetings-policies-recording-and-transcription.md#transcription) 등 Teams에 더 많은 기능을 추가하도록 정책을 조정할 수 있습니다.

**초등 중등학생은** 제한된 기능이 필요할 수 있습니다. 학생 정책은 '전역(조직 전체 기본값)' 정책을 변경하는 것이 좋습니다.

**초등학교 교직원 및 교육자는 비공개 채팅 허용 및** 모임 일정 예약과 같은 주요 기능을 부여하는 정책을 할당받아야 합니다. [직원과 교육자에게 이 정책을 대량으로 할당합니다](batch-group-policy-assignment-edu.md).

> [!IMPORTANT]
> 사용자에게 할당된 모임 정책의 경우 자동으로 **사용자 설정을** **조직의 모든** 사람에게 설정하는 것이 좋습니다. 이렇게 하면 인증되지 않은 사용자가 Teams 모임에 참가하기 전에 로비에서 입장해야 합니다.
>
> 자세한 내용은 [Teams에서 모임 정책 관리](meeting-policies-participants-and-guests.md#automatically-admit-people)를 참조하세요.

# <a name="class-teams"></a>[수업 팀](#tab/class-teams)

## <a name="create-class-teams-for-secure-classroom-use"></a>안전한 교실 사용을 위한 수업 팀 만들기

교육용 Microsoft Teams는 교육용 [특별 팀 유형](https://support.office.com/article/choose-a-team-type-to-collaborate-in-microsoft-teams-0a971053-d640-4555-9fd7-f785c2b99e67)을 제공합니다. [수업 팀 유형](https://support.office.com/article/create-a-class-team-in-microsoft-teams-fae422eb-58b7-4431-9ff2-a4b9b6ae7c5b)은 교실용으로 설계되었으며, 다음을 포함한 교실 요구 사항을 지원하는 특정 기능을 제공합니다.

- 할당.
- 성적.
- OneNote 교실 전자 필기장.
- 학생용 읽기 전용 콘텐츠를 보호하기 위한 [수업 자료 폴더](https://support.office.com/article/Use-folders-to-create-read-only-files-for-students-or-other-team-members-0e7791d7-8c9c-4749-9bca-984289477988)입니다.
- [Insights](./class-insights.md)에서는 학생의 참여, 과제 및 각 교실의 복지에 대한 실시간 데이터를 제공합니다.
- 학생이 추가되기 전에 수업을 설정하기 위한 [초기 교육자 액세스](https://support.microsoft.com/article/activate-early-access-class-teams-created-with-school-data-sync-0d154696-66ab-4fcf-b22f-c3d9a82aaf78) 권한입니다.
- 파괴적인 학생 및 기타 특수 권한을 음소거하는 기능입니다.

클래스 팀은 다음을 통해 만들 수 있습니다.

- [학교 데이터 동기화(SDS)](#automatic-team-creation-using-sds).
- [Microsoft 365 클래스 그룹을 사용하여 교육자 주도 만들기](#educator-led-team-creation-from-microsoft-365-class-groups)
- [Graph API를 사용하는 PowerShell 스크립트](#powershell-script-using-graph-apis)입니다.
- [수동 팀 만들기](#manual-team-creation).

요구 사항에 가장 잘 맞는 올바른 배포 경로를 선택 하는 데 도움이 되는 다양한 옵션에 대해 단계별로 살펴봅니다.

### <a name="automatic-team-creation-using-sds"></a>SDS를 사용하여 자동 팀 만들기

[SDS(학교 데이터 동기화)](/SchoolDataSync) 는 SIS(학생 정보 시스템) 또는 LMS(학습 관리 시스템)와 같은 기관의 레코드 시스템에서 데이터를 읽습니다.

SDS는 모든 레코드 시스템에서 데이터를 가져올 수 있으며 많은 SIS 공급업체에 대한 기본 제공 커넥터 [가 있습니다](/schooldatasync/frequently-asked-questions#what-sismis-vendors-does-school-data-sync-support).  

#### <a name="benefits-of-sds"></a>SDS의 이점

- 사용자를 자동으로 만들고 라이선스를 적용합니다.
- 수업 팀을 자동으로 만들고 유지 관리합니다.
- SIS/LMS와 동기화하여 학생 구성원 자격 변경을 유지합니다.
- [교육자가 학생을 추가하기 전에 수업을 준비할 수 있습니다](https://support.office.com/article/activate-early-access-class-teams-created-with-school-data-sync-0d154696-66ab-4fcf-b22f-c3d9a82aaf78).
- 보안 그룹을 자동으로 만들 수 있습니다.
- 범위가 지정된 관리 위임에 대한 관리 단위를 만듭니다.
- [교육자 암호 재설정을 허용합니다](/schooldatasync/how-to-enable-teacher-password-reset).
- 그룹 및 팀의 이름을 바꾸고 보관하는 기본 제공 정리 기능이 있습니다.
- [Teams에서 SIS로 성적을 동기화합니다](/schooldatasync/grade-sync).
- [학생 개인 데이터를 보호합니다](/schooldatasync/protecting-student-personal-data).
- 보호자 동의를 추적하고 관리합니다.
- 더 나은 교육 Insights 데이터를 제공합니다.

#### <a name="considerations-for-sds"></a>SDS에 대한 고려 사항

SDS는 다음 두 단계로 팀을 만듭니다.

1. SDS는 Azure Active Directory(Azure AD)에 Microsoft 365 그룹을 만듭니다.
2. SDS는 자동으로 해당 그룹을 팀으로 바꿉니다.

팀 만들기의 두 번째 단계는 SDS에서 선택 사항입니다. 배포 시간 및 발생할 수 있는 사용하지 않은 팀 수에 따라 관리자는 자동으로 팀을 만들려고 하지 않을 수 있습니다. 대신 [교육자 주도 팀 만들기 방법을 참조하세요](#educator-led-team-creation-from-microsoft-365-class-groups).  

#### <a name="get-started-with-sds"></a>SDS 시작

시작하려면 [SDS(School Data Sync)](/SchoolDataSync) 로 이동하여 무료 배포 지원을 받으려면 문의 [https://aka.ms/sdssupport](https://aka.ms/sdssupport) 하세요.  

### <a name="educator-led-team-creation-from-microsoft-365-class-groups"></a>Microsoft 365 클래스 그룹에서 교육자 주도 팀 만들기

교육자 주도 팀 만들기를 통해 교육자는 필요한 수업을 쉽게 만들 수 있습니다.  

이 방법을 사용하면 SDS를 사용하여 각 클래스에 대한 그룹을 만들거나(권장) [Graph API](/graph/api/educationroot-post-classes) 사용하여 직접 만들 수 있습니다.

수업 그룹이 준비되면 교육자는 그룹을 팀으로 변환할 수 있습니다.

1. Teams에서 Teams 탭을 선택합니다.
2. 클라이언트 맨 위에서 **제안된 클래스 아이콘을** 선택합니다.

#### <a name="benefits-of-educator-led-team-creation"></a>교육자 주도 팀 만들기의 이점

- 수업은 준비되고 제안되지만 교육자에서 사용하려는 경우가 아니면 만들어지지 않습니다.
- 500,000개 이상의 팀이 있는 기관의 경우 이 방법을 사용하면 불필요한 팀 수가 줄어듭니다.
- [SDS 혜택](#benefits-of-sds).
- Graph API 이점.
  - 교육자는 클래스를 만들 수 있도록 제어할 수 있습니다.
  - SDS와의 통합이 필요하지 않습니다.

#### <a name="considerations-for-educator-led-team-creation"></a>교육자 주도 팀 만들기에 대한 고려 사항

- 완전히 자동화되지 않으며 몇 가지 강사 작업이 필요합니다.
- 팀을 만들 수 있는 권한이 없는 교육자는 [기존 그룹에서 팀을 만들](https://support.office.com/article/create-a-class-team-in-microsoft-teams-preview-fae422eb-58b7-4431-9ff2-a4b9b6ae7c5b) 수 있습니다.
- Graph API 높은 수준의 기술 전문 지식, 스크립트를 만들고 실행하는 시간 및 문제를 해결하는 시간이 필요합니다.

#### <a name="get-started-with-educator-led-team-creation"></a>교육자 주도 팀 만들기 시작

SDS 방법을 시작하려면 [SDS(School Data Sync)](/SchoolDataSync) 로 이동하여 무료 배포 지원을 받으려면 문의 [https://aka.ms/sdssupport](https://aka.ms/sdssupport) 하세요.

- SDS 프로필에서 자동 팀 만들기 토글을 해제해야 합니다.
- 두 개의 SDS 프로필을 사용하여 수업 팀에 대해 자동 및 교육자 주도 팀 만들기의 조합을 사용할 수 있습니다.

그래프 API 방법을 사용하려면 [그래프 API](/graph/api/educationroot-post-classes?tabs=http&view=graph-rest-1.0&preserve-view=true) 및 [수업 팀 만들기](/graph/api/educationroot-post-classes?tabs=http&view=graph-rest-beta&preserve-view=true)를 참조하세요.  

### <a name="powershell-script-using-graph-apis"></a>그래프 API를 사용하는 PowerShell 스크립트

PowerShell을 사용하면 스크립트를 작성하여 팀과 채널을 만들고 설정을 자동으로 구성할 수 있습니다.

이 방법을 사용하려면 관리자가 [먼저 그룹을 만들고, 교육자와 학생을 추가한 다음, 팀을 만들어야 합니다](/graph/teams-create-group-and-team).

[Microsoft Graph API 사용하여 팀을 만들고, 구성하고, 복제하고, 보관할](/graph/api/resources/teams-api-overview) 수도 있습니다.

#### <a name="benefits-of-powershell-scripts"></a>PowerShell 스크립트의 이점

- IT 관리자가 클래스 만들기를 제어할 수 있게 합니다.
- 사전 강사 액세스 팀 또는 팀에 즉각적인 학생 액세스를 만들기 위한 옵션
- [학생 구성원 자격 변경 내용을 Azure AD 그룹에 동기화합니다](/graph/api/team-post?tabs=http&view=graph-rest-beta#example-4-create-a-team-from-group&preserve-view=true).

#### <a name="considerations-for-powershell-scripts"></a>PowerShell 스크립트에 대한 고려 사항

- 스크립트를 만들어 실행하고 수업 그룹을 만들 때 발생하는 문제를 해결하기 위한 기술 관련 전문 지식과 시간이 많이 필요합니다.
- 기본 제공 오류 처리 또는 다시 시도 논리가 없습니다.
- 멤버 자격 변경은 SIS와 동기화되지 않습니다.

> [!NOTE]
> 수업 팀에는 숨겨진 그룹 구성원이 필요하므로 수업 내에 있는 강사와 학생만이 해당 수업의 멤버를 볼 수 있습니다. Microsoft 365 클래스 그룹을 만들려면 개인 정보 요구 사항을 충족하는 [수업 팀 만들기](/graph/api/educationroot-post-classes?tabs=http&view=graph-rest-beta&preserve-view=true) 를 참조하세요.

### <a name="manual-team-creation"></a>수동 팀 만들기

사용자는 자신의 팀을 만들 수 있는 기능을 통해 Teams 환경을 조정할 수 있습니다.

사용자의 권한에 따라 다음을 수행할 수 있습니다.

- [자신의 팀을 설정하고 학생을 포함한 사용자를 초대](https://support.microsoft.com/article/create-a-class-team-in-microsoft-teams-fae422eb-58b7-4431-9ff2-a4b9b6ae7c5b#ID0EADAAA=Create_a_team_from_scratch)합니다.
- [수동으로 팀에 사용자를 추가합니다](https://support.office.com/article/add-a-student-to-a-class-team-b88263bb-ace1-4702-8a48-f8a2cf4af954).
- [조인 코드를 공유합니다](https://support.office.com/article/Create-a-link-or-a-code-for-joining-a-team-11b0de3b-9288-4cb4-bc49-795e7028296f).
- [팀에 대한 링크를 공유합니다](https://support.office.com/article/Create-a-link-or-a-code-for-joining-a-team-11b0de3b-9288-4cb4-bc49-795e7028296f).

교육자는 학생을 팀에 추가하여 학생들이 액세스할 수 있도록 하고 추가되었다는 알림을 받는 것이 가장 좋습니다.

#### <a name="benefits-of-manual-team-creation"></a>수동 팀 만들기의 이점

- 교육자에게 수업 생성을 완전히 제어할 수 있습니다.
- 수업 팀은 즉시 만들어집니다.

#### <a name="considerations-for-manual-team-creation"></a>수동 팀 만들기에 대한 고려 사항

- 강사 작업과 시간이 필요합니다.
- 학생 구성원 자격은 SIS와 동기화되지 않으며 수동 관리가 필요합니다.
- 학생들은 수업 팀에 즉시 액세스할 수 있습니다.

### <a name="recommended-best-practices"></a>권장 모범 사례

- 조기 배포하여 개학 날을 위해 모든 작업이 안정적으로 준비되었는지 확인합니다.

- SDS 자동 팀 만들기와 관련된 문제의 경우 교육자는 [교육자 주도 팀 만들기 방법을](#educator-led-team-creation-from-microsoft-365-class-groups) 사용하여 다시 시도할 수 있습니다. [수동 팀 만들기](#manual-team-creation) 는 또 다른 솔루션이지만 클래스는 SIS와 동기화되지 않습니다.

- 테넌트 팀 제한은 50만 개입니다. 따라서 관리자는 이러한 제한에 도달하지 않도록 사용하지 않는 팀의 수를 줄여야 합니다. 자세한 내용은 [Microsoft Teams의 제한 및 사양을 참조하세요](limits-specifications-teams.md).  

# <a name="educator-early-access"></a>[교육자 조기 액세스](#tab/early-access)

## <a name="early-access-to-class-teams"></a>수업 팀에 빠르게 액세스

조기 액세스 수업 팀은 학생들이 볼 수 있기 전에 교육자가 수업 팀에 액세스할 수 있도록 허용합니다. 교육자는 학생에게 액세스 권한을 부여하기 전에 파일을 설정하고, 추가하고, 구성할 시간을 갖게 됩니다.

학생들이 팀에 액세스할 준비가 되면 [수업을 활성화할](https://support.office.com/article/activate-early-access-class-teams-created-with-school-data-sync-0d154696-66ab-4fcf-b22f-c3d9a82aaf78) 수 있습니다.

### <a name="how-do-i-create-class-teams-that-allow-educators-early-access-to-set-up-a-team-before-admitting-students"></a>강사가 학생을 입학하기 전에 팀을 구성할 수 있도록 조기에 액세스 할 수 있는 수업 팀을 만들려면 어떻게 해야 하나요?

그룹(SDS, 강사 주도 또는 그래프 API를 통해)에서 생성된 Teams는 기본적으로 조기 액세스 팀을 자동으로 생성합니다.

Graph API를 사용하여 자신만의 조기 액세스 팀을 만들려면 [클래스를 만들고](/graph/api/educationroot-post-classes?tabs=http&view=graph-rest-beta&preserve-view=true) [그룹에서 팀을 만들어야](/graph/api/team-post?tabs=http&view=graph-rest-beta#example-4-create-a-team-from-group&preserve-view=true) 합니다.

### <a name="how-do-i-check-if-a-class-is-activated"></a>클래스가 인증되는지 확인하려면 어떻게 해야 하나요?

[팀 리소스 유형](/graph/api/resources/team?view=graph-rest-beta&preserve-view=true)에서 [isMembershipLimitedToOwners](/graph/api/resources/team?view=graph-rest-beta#properties&preserve-view=true) 속성을 확인하여 클래스가 활성화되었는지 확인합니다.

[Get Team API](/graph/api/team-get?tabs=http&view=graph-rest-beta&preserve-view=true)를 사용하여 특정 클래스에 대한 ```isMembershipLimitedToOwners``` 속성을 쿼리합니다. 팀이 활성화되면 false 값이 반환됩니다. 팀이 활성화되지 않은 경우 true 값을 반환합니다.

### <a name="how-do-i-activate-a-class-for-an-educator"></a>강사 수업을 활성화하려면 어떻게 해야 하나요?

[업데이트 팀 API](/graph/api/team-update?tabs=http&view=graph-rest-beta&preserve-view=true)를 사용하고 속성을 false로 설정 ```isMembershipLimitedToOwners``` 하여 교육자를 대신하여 팀을 활성화합니다. 팀이 활성화된 후에는 되돌릴 수 없습니다.

### <a name="create-staff-teams-for-staff-communication-and-collaboration"></a>직원 커뮤니케이션 및 공동 작업을 위한 직원 팀 만들기

[교직원 유형 팀은](https://support.office.com/article/create-a-staff-team-in-microsoft-teams-314ac9d5-36a9-408e-8ae4-7ef20e9f1ddf) 교육 관리자와 직원이 정보를 공유하고 기관 차원의 이니셔티브에서 함께 작업할 수 있도록 합니다.

교육 관리자는 팀 만들기 마법사를 사용하여 팀에 직원을 추가하거나, [팀을 만든 후 구성원을 추가](https://support.office.com/article/add-members-to-a-team-in-teams-aff2249d-b456-4bc3-81e7-52327b6b38e9)하거나, [팀에 대한 참가 코드 또는 링크를 공유하여 팀에](https://support.office.com/article/create-a-link-or-a-code-for-joining-a-team-11b0de3b-9288-4cb4-bc49-795e7028296f) 직원을 추가할 수 있습니다.

# <a name="meeting-scenarios"></a>[모임 시나리오](#tab/scenarios)

## <a name="teams-meeting-scenarios"></a>Teams 모임 시나리오

### <a name="collaborative-meetings-for-virtual-classes"></a>가상 수업을 위한 공동 작업 모임

[Microsoft Teams 모임](./tutorial-meetings-in-teams.yml)은 오디오, 비디오, [콘텐츠 공유](https://support.office.com/article/show-your-screen-during-a-meeting-90c84e5a-b6fe-4ed4-9687-5923d230d3a7), 화이트보드 및 공유 노트를 사용할 수 있는 기능을 포함하여 최대 250명의 동시 참석자를 지원합니다.

모임은 다음과 같습니다.

- [Teams 클라이언트 내에서 예약됩니다](./tutorial-meetings-in-teams.yml).
- 참석자가 나중에 검토할 수 있도록 기록되고 저장됩니다.
- [콘텐츠를 쉽게 찾을 수 있도록 전사](https://support.office.com/article/Microsoft-Stream-automatically-creates-closed-captions-for-videos-8d6ac353-9ff2-4e2b-bca1-329499455308)되었습니다.
- 노트북 또는 휴대폰 웹캠, 마이크 및 스피커를 사용하여 액세스합니다.
- [특정 디바이스에 최적화되었습니다](https://products.office.com/microsoft-teams/across-devices/devices).
- 모든 참가자가 학생이 감독 없이 모임에 참가하지 않도록 하기 위해 종료되었습니다.

### <a name="districtuniversity-events-or-updates"></a>학군/대학 이벤트 또는 업데이트

일부 모임에는 많은 청중과 추가 프로덕션 요구 사항이 있습니다. 이러한 모임은 발표자, 제작자 및 중재 Q&A를 정의했습니다.

Teams는 [Microsoft Teams 라이브 이벤트](teams-live-events/what-are-teams-live-events.md)를 사용하여 이러한 세션을 지원합니다.

라이브 이벤트는 다음과 같은 시나리오에 사용할 수 있습니다.

- 지구 또는 대학 차원의 업데이트.
- 리더십 주소.
- 대규모 수업 또는 학생 그룹에 대한 지침입니다.
- 커뮤니티로 확장.

다음에서 라이브 세션을 수행하는 방법에 대해 알아봅니다.

- [라이브 이벤트를 계획하고 예약합니다](https://support.office.com/article/video-plan-and-schedule-a-live-event-f92363a0-6d98-46d2-bdd9-f2248075e502).
- [라이브 이벤트를 생성합니다](https://support.office.com/article/video-produce-a-live-event-34c89e79-ffd4-4a6a-baf6-77055e0709cb).
- [라이브 이벤트에 참석](https://support.office.com/article/video-attend-a-live-event-d837ad8d-ce34-44d0-9744-9beb50e943ac)합니다.
- [Q&A 조정](https://support.office.com/article/video-moderating-a-q-a-4984e582-8c66-4ea3-aaaf-d93cf62e1b76)

# <a name="resources"></a>[리소스](#tab/resources)

## <a name="support-resources"></a>지원 리소스

원격 학습으로의 전환에 대한 일반적인 개요는 [여기에서 시작하세요](https://www.microsoft.com/education/remote-learning).

IT 관리자, 교육자, 학생 또는 보호자인 경우 이러한 리소스를 통해 Teams를 사용하는 데 도움이 될 수 있습니다.

- **IT 관리자**
  - [플랫폼별 Teams 기능](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3).
  - [Teams 클라이언트를 다운로드하고 배포합니다](get-clients.md).
  - [Teams 문제 해결](/MicrosoftTeams/troubleshoot/teams).
  - [가상화된 데스크톱 인프라용 Teams](./teams-for-vdi.md).
  - [통화 품질을 모니터링하고 관리합니다](monitor-call-quality-qos.md).
  - [Teams의 서비스 상태를 확인합니다](service-health.md).
  - [원격 직원에 대한 Microsoft 365 트래픽을 최적화](https://techcommunity.microsoft.com/t5/office-365-blog/how-to-quickly-optimize-office-365-traffic-for-remote-staff-amp/ba-p/1214571)합니다.
  - [Teams에 대한 연락처를 지원합니다](/microsoft-365/admin/contact-support-for-business-products).
  - [교육용 Teams 웨비나](https://aka.ms/TeamsEDUWebinars).

- **교육자**
  - [교육자를 위한 도움말 센터입니다](https://support.office.com/article/microsoft-teams-5aa4431a-8a3c-4aa5-87a6-b6401abea114).
  - [원격 학습 도움말](https://aka.ms/RemoteLearningHelp).
  - [Teams를 다운로드합니다](get-clients.md).
  - [교육용 Teams 웨비나](https://aka.ms/TeamsEDUWebinars).
  - [Teams를 사용하는 교육자를 위한 온라인 과정](https://education.microsoft.com/course/9c9f5c11/overview)입니다.
  - [Teams와 공동 작업 학습 환경을 만드는 온라인 과정](https://education.microsoft.com/course/b1e15cfc/overview)입니다.
  - [지원 티켓을 제출합니다](https://www.microsoft.com/microsoft-teams/download-app).

- **학생**
  - [학생을 위한 도움말 센터](https://support.office.com/article/student-help-center-395ab230-55bf-44c6-b265-e832d729b694)입니다.
  - [원격 학습 도움말](https://aka.ms/RemoteLearningHelp).
  - [Teams를 다운로드합니다](https://www.microsoft.com/microsoft-teams/download-app).

- **보호자**
  - [원격 학습 도움말](https://aka.ms/RemoteLearningHelp).
  - [Teams를 다운로드합니다](https://www.microsoft.com/microsoft-teams/download-app).

---
