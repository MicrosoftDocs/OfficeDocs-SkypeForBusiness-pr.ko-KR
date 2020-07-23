---
title: 수업 팀 만들기 권장 방법과 모범 사례
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: lakuan
description: 학교용 수업 팀을 만드는 방법에 대한 권장 방법과 모범 사례에 대해 알아봅니다.
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 3e8b8e8605b5e4f916389109cb611996aa90a895
ms.sourcegitcommit: 34a30c2c9a8e32bfcb382c3e6e7237f277ec361d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/22/2020
ms.locfileid: "45206772"
---
# <a name="recommended-methods-and-best-practices-for-creating-class-teams"></a>수업 팀 만들기 권장 방법과 모범 사례

교육용 Microsoft Teams는 교육용   [특별 팀 유형](https://support.office.com/article/choose-a-team-type-to-collaborate-in-microsoft-teams-0a971053-d640-4555-9fd7-f785c2b99e67) 을 제공합니다. [수업 팀 유형](https://support.office.com/article/create-a-class-team-in-microsoft-teams-fae422eb-58b7-4431-9ff2-a4b9b6ae7c5b)은 교실용으로 설계되었으며, 다음을 포함한 교실 요구 사항을 지원하는 특정 기능을 제공합니다.  

- 과제
- 성적
- OneNote 교실 전자 필기장  
- 학생을 위한 읽기 전용 콘텐츠를 보호하기 위한 [수업 자료 폴더](https://support.office.com/article/Use-folders-to-create-read-only-files-for-students-or-other-team-members-0e7791d7-8c9c-4749-9bca-984289477988) 
- 학생이 추가 되기 전에 수업을 설정하기 위한 [사전 교사 액세스](https://support.microsoft.com/article/activate-early-access-class-teams-created-with-school-data-sync-0d154696-66ab-4fcf-b22f-c3d9a82aaf78)  
- 방해가 되는 학생 음소거 기능 및 기타 특정 권한  

수업 팀을 만드는 몇 가지 방법이 있으며 교육용 Teams에는 이 과정을 최대한 간편하게 해 주는 고유 배포 도구 집합이 있습니다. 요구 사항에 가장 잘 맞는 올바른 배포 경로를 선택 하는 데 도움이 되는 다양한 옵션에 대해 단계별로 살펴봅니다.  

## <a name="automatic-team-creation-using-sds"></a>SDS를 사용하여 자동 팀 만들기

**이 기능은 2020년 7월 말에 제공될 예정입니다.**

팀 만들기 자동화는 IT 관리자와 교사의 시간을 모두 줄여줍니다. 이 기능을 사용해 교사는 모든 수업 팀을 만들고 로그인할 때 설정할 준비가 되었는지 확인할 수 있습니다. [SDS(School Data Sync)](https://docs.microsoft.com/SchoolDataSync)는 교육 기관의 레코드 시스템(예: SIS(학생 정보 시스템) 또는 LMS(학습 관리 시스템))에서 데이터를 읽는 무료 Office 365 Education 도구입니다. SDS는 Office 365 데이터를 사용하여 대량으로 수업 팀 만들기 및 정보 시스템과의 동기화를 포함하여 여러 가지 방법으로 등록 변경에 따른 강사와 학생 구성원을 업데이트합니다. SDS는 모든 시스템 레코드에서 데이터를 가져올 수 있으며, 전 세계의 여러 기존 [SIS 공급 업체](https://docs.microsoft.com/schooldatasync/what-sis-and-mis-vendors-does-school-data-sync-support)에 대한 기본 제공 커넥터가 있습니다. SDS를 사용하는 것은 다음과 같은 이점이 있어 좋습니다.  

### <a name="benefits"></a>이점

- 수업 팀 자동 만들기 및 유지 관리로 교사는 Teams에 로그인하여 즉시 교육을 시작할 수 있습니다.
- SIS/LMS에 대한 구성원 동기화를 통해 학생 구성원 변경 내용을 유지 관리합니다.
- EDU 고객 성공 팀에서 무료 배포 지원을 제공합니다.
- [사전 교사 액세스](https://support.office.com/article/activate-early-access-class-teams-created-with-school-data-sync-0d154696-66ab-4fcf-b22f-c3d9a82aaf78): 교사는 학생을 허용하기 전에 팀을 준비할 수 있는 시간이 있습니다.  
- 필요에 따라 사용자를 만들고 Office 365 라이선스를 적용합니다.
- Teams 정책을 포함하여 Office 365에서 사용할 보안 그룹을 만듭니다.
- 범위가 지정된 관리 위임 및 [교사 암호 재설정](https://docs.microsoft.com/schooldatasync/how-to-enable-teacher-password-reset)에 대한 관리 단위를 만듭니다. 
- 대규모 프로세스의 경우 관리자의 작업을 줄이기 위한 기본 제공 오류 및 재시도 처리, 제한 백오프 및 세션 안정성이 있습니다.  
- 그룹 및 팀이 오래된 경우 이름을 바꾸고 보관할 수 있는 기본 제공 정리 기능이 있습니다.
- [성적 동기화](https://docs.microsoft.com/schooldatasync/grade-sync): 교사는 Teams에서 모든 성적을 매기고 자동으로 다시 Teams에서 SIS 성적표로 성적을 작성할 수 있습니다. 
- [학생 데이터 보호](https://docs.microsoft.com/schooldatasync/protecting-student-personal-data): 학생이 타사 앱을 사용하지 못하도록하며 부모 동의를 추적하고 관리합니다. 
- 가져온 데이터는 사용자 역할, 조직(학교) 및 기타 중요한 데이터로 교육 정보를 보강하는 데 사용됩니다.  

### <a name="considerations"></a>고려 사항

SDS는 2단계로 팀을 만듭니다. 첫 번째 단계에서는 Azure AD(Azure Active Directory)에 Microsoft 365 그룹을 만들고 두 번째 단계에서 자동으로 해당 그룹을 팀으로 변환합니다. 팀 만들기의 두 번째 단계는 SDS에서 선택 사항입니다. 배포 시간 및 발생할 수 있는 사용하지 않은 팀 수에 따라 관리자는 자동으로 팀을 만들려고 하지 않을 수 있습니다. 팀이 50만 개 이상인 기관은 SDS에서 자동 팀 만들기를 해제하고 [교사 주도 팀 만들기 방법](#teacher-led-team-creation-from-office-365-class-groups)을 사용하는 것을 권장합니다.  

### <a name="get-started"></a>시작하기

시작하려면 [SDS(School Data Sync)](https://docs.microsoft.com/SchoolDataSync)로 이동하여 [https://aka.ms/sdssupport](https://aka.ms/sdssupport)배포 지원에 문의하세요.  

## <a name="teacher-led-team-creation-from-office-365-class-groups"></a>Office 365 클래스 그룹에서 교사 주도 팀 만들기

**이 기능은 2020년 8월 말에 제공될 예정입니다.**

교사 주도 팀 만들기는 교사에게 필요한 수업을 신속하게 만들 수 있도록 해주는 훌륭한 배포 옵션입니다. 또한 팀이 50만 개 이상인 기관은 이 방법을 사용하여 관련 없는 팀의 수를 최소화하는 것을 권장합니다.  

이 하이브리드 방법을 통해 SDS를 사용하여 각 수업에 대한 그룹을 만들거나(권장) [그래프 API](https://docs.microsoft.com/graph/api/educationroot-post-classes)를 사용하여 직접 파일을 만들 수 있습니다. 수업 그룹이 준비되면 교사는 **제안된 수업** 아이콘을 사용하여 그룹을 팀으로 변환할 수 있습니다.

:::image type="content" source="media/class-teams-edu-suggested-classes.png" alt-text="제안 된 수업 아이콘을 보여주는 스크린샷":::

### <a name="benefits"></a>이점

- [사전 교사 액세스](https://support.office.com/article/activate-early-access-class-teams-created-with-school-data-sync-0d154696-66ab-4fcf-b22f-c3d9a82aaf78): 교사는 학생을 허용하기 전에 팀을 준비할 수 있는 시간이 있습니다.  
- 사용되지 않는 팀과 불필요한 팀의 수를 줄입니다. 수업은 준비되고 제안되지만 교사가 사용하려고 하기 전까지는 만들어지지 않습니다. 팀이 50만 개 이상인 대규모 기관은 이 옵션을 선택하여 혼란을 줄이는 것을 권장합니다.
- SDS
    - SIS/LMS에 대한 구성원 동기화를 통해 학생 구성원 변경 내용을 유지 관리합니다.
    - EDU 고객 성공 팀에서 무료 배포 지원을 제공합니다.
    - 필요에 따라 사용자를 만들고 Office 365 라이선스를 적용합니다.
    - Teams 정책을 포함하여 Office 365에서 사용할 보안 그룹을 만듭니다.
    - 범위가 지정된 관리 위임 및 [교사 암호 재설정](https://docs.microsoft.com/schooldatasync/how-to-enable-teacher-password-reset)에 대한 관리 단위를 만듭니다.
    - 대규모 프로세스의 경우 관리자의 작업을 줄이기 위한 기본 제공 오류 및 재시도 처리, 제한 백오프 및 세션 안정성이 있습니다. 
    - 그룹 및 팀이 오래된 경우 이름을 바꾸고 보관할 수 있는 기본 제공 정리 기능이 있습니다. 
    - [성적 동기화](https://docs.microsoft.com/schooldatasync/grade-sync): 교사는 Teams에서 모든 성적을 매기고 자동으로 다시 Teams에서 SIS 성적표로 성적을 작성할 수 있습니다. 
    - [학생 데이터 보호](https://docs.microsoft.com/schooldatasync/protecting-student-personal-data): 학생이 타사 앱을 사용하지 못하도록하며 부모 동의를 추적하고 관리합니다. 
    - 가져온 데이터는 사용자 역할, 조직(학교) 및 기타 중요한 데이터로 교육 정보를 보강하는 데 사용됩니다.
- 그래프 API
    - 추가 유연성 및 제어
    - SDS와의 통합이 필요하지 않습니다.

### <a name="considerations"></a>고려 사항

- 완전히 자동화되지 않으며 몇 가지 교사 작업이 필요 합니다.
- 팀을 만들 수 있는 권한이 없는 교사는 [여기](https://support.office.com/article/create-a-class-team-in-microsoft-teams-preview-fae422eb-58b7-4431-9ff2-a4b9b6ae7c5b)에 표시된 것과 같이 기존 그룹에서 계속 팀을 만들 수 있습니다.
- 그래프 API에는 스크립트를 만들어 실행하고 수업 그룹을 만들 때 발생하는 문제를 해결하기 위한 기술 관련 전문 지식과 시간이 많이 필요합니다.

### <a name="get-started"></a>시작하기

SDS 방법을 사용해 시작하려면, [SDS(School Data Sync)](https://docs.microsoft.com/SchoolDataSync)로 이동하여 [https://aka.ms/sdssupport](https://aka.ms/sdssupport)배포 지원에 문의하세요. 

그래프 API 방법을 사용하려면 [그래프 API](https://docs.microsoft.com/graph/api/educationroot-post-classes?view=graph-rest-1.0&tabs=http) 및 [수업 팀 만들기](https://docs.microsoft.com/graph/api/educationroot-post-classes?view=graph-rest-beta&tabs=http)를 참조하세요.  

> [!NOTE]
> SDS에 이 방법을 사용하려면 SDS 프로필에서 자동 팀 만들기를 설정/해제해야 합니다. 2개의 SDS 프로필을 사용하여 필수 및 선택 수업 팀에 대한 자동 및 교사 주도 팀 만들기를 함께 사용할 수도 있습니다.

## <a name="powershell-script-using-graph-apis"></a>그래프 API를 사용하는 PowerShell 스크립트

PowerShell을 사용하여 팀, 채널을 만들고 설정을 자동으로 구성하는 스크립트를 작성할 수 있습니다. 이를 위해서는 관리자가 먼저 그룹을 만들고 교사와 학생을 추가한 다음[여기](https://docs.microsoft.com/graph/teams-create-group-and-team)에 나와 있는 대로 팀을 만들어야 합니다. Microsoft 그래프 API를 사용하여 팀을 만들고, 구성하고, 복제하고, 보관할 수도 있습니다. 자세한 내용은 [Microsoft 그래프 API를 사용하여 Microsoft Teams에서 작업](https://developer.microsoft.com/graph/docs/api-reference/beta/resources/teams_api_overview), [Microsoft Teams PowerShell](https://docs.microsoft.com/powershell/module/teams) 및 [수업 팀 만들기](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta&tabs=http#example-6-create-a-team-with-a-non-standard-base-template-type)를 참조하세요. 그래프 API를 사용하면 더욱더 강력하게 제어하고 유연한 기능을 사용할 수 있으나 기술 전문 지식이 필요하며 초기 설정에 시간이 더 많이 걸립니다.  

### <a name="benefits"></a>이점

- 추가 유연성 및 제어
- 사전 교사 액세스 팀 또는 팀에 즉각적인 학생 액세스를 만들기 위한 옵션  
- [그룹에서 팀을 만들기](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta&tabs=http#example-4-create-a-team-from-group)를 하는 경우, 교사는 사전에 액세스할 수 있으며 Azure AD 그룹에 대한 학생 구성원 변경 내용이 동기화됩니다.

### <a name="considerations"></a>고려 사항

- 스크립트를 만들어 실행하고 수업 그룹을 만들 때 발생하는 문제를 해결하기 위한 기술 관련 전문 지식과 시간이 많이 필요합니다.
- 기본 제공 오류 처리 또는 다시 시도 논리가 없습니다.
- 구성원이 변경되면 SIS와 동기화되지 않습니다. 

> [!NOTE]
> 수업 팀에는 숨겨진 그룹 구성원이 필요하므로 수업 내에 있는 교사와 학생만이 해당 수업의 멤버를 볼 수 있습니다. Office 365 수업 그룹을 만들려면 [수업 팀 만들기](https://docs.microsoft.com/graph/api/educationroot-post-classes?view=graph-rest-beta&tabs=http)를 참조하여 동일한 개인 정보 요구 사항을 충족하세요.

## <a name="manual-team-creation"></a>수동 팀 만들기

학생과 교사는 문제를 최소화하면서 Teams를 사용하고, 필요에 맞게 유연하게 조정할 수 있습니다. Teams 환경을 조정하는 한 가지 방법은 팀을 만들 수 있도록 지원하는 것입니다. 교사는 [여기](https://support.microsoft.com/article/create-a-class-team-in-microsoft-teams-fae422eb-58b7-4431-9ff2-a4b9b6ae7c5b#ID0EADAAA=Create_a_team_from_scratch)에 나와 있는 대로 고유한 수업 유형 팀을 설정하고 학생을 초대합니다. 교사는 [팀에 학생을 추가](https://support.office.com/article/add-a-student-to-a-class-team-b88263bb-ace1-4702-8a48-f8a2cf4af954)하거나, [참가 코드를 공유](https://support.office.com/article/Create-a-link-or-a-code-for-joining-a-team-11b0de3b-9288-4cb4-bc49-795e7028296f)하거나, [팀에 대한 링크를 공유](https://support.office.com/article/Create-a-link-or-a-code-for-joining-a-team-11b0de3b-9288-4cb4-bc49-795e7028296f)하여 학생을 초대할 수 있습니다. 가능한 경우, 교사가 팀에 학생을 추가하여 학생에게 액세스 권한을 부여하고, 팀에 추가되었음을 알리는 것이 좋습니다.

### <a name="benefits"></a>이점

- 교사를 위한 추가 유연성
- 즉시 팀 만들기 및 액세스   

### <a name="considerations"></a>고려 사항

- 교사 작업과 시간이 필요합니다.
- 학생 구성원은 SIS와 동기화되지 않으므로 수동 관리를 해야 합니다.
- 교사에게 팀에 대한 사전 액세스를 제공하지 않습니다. 학생이 즉시 액세스할 수 있습니다.

## <a name="recommended-best-practices"></a>권장 모범 사례

- 조기 배포하세요! 조기 배포하여 개학 날을 위해 모든 작업이 안정적으로 준비되었는지 확인합니다. SDS를 사용하는 경우에는 SDS 배포를 시작하기 위해 전체 학생 등록을 하지 않아도 됩니다. 해당 정보를 SIS에서 사용할 수 있게 되면 학생들이 동기화됩니다.
- 팀이 50만 개 이상인 경우 [교사 주도 팀 만들기 방법](#teacher-led-team-creation-from-office-365-class-groups)을 사용하는 것을 권장합니다. 관련이 있고 필요한 수업 팀만 만들어 사용되지 않는 팀을 줄여 혼란을 방지할 수 있습니다.  
- SDS 자동 팀 만들기 및 교사에게 해당하는 문제가 있을 경우(예: 수업이 누락된 경우) [교사 주도 팀 만들기 방법](#teacher-led-team-creation-from-office-365-class-groups)을 사용하여 다시 시도할 수 있습니다. [수동 팀 만들기](#manual-team-creation)는 또 다른 솔루션이지만 팀 구성원의 업데이트는 유지되지 않습니다.  
- 테넌트 팀 제한은 50만 개입니다. 따라서 관리자는 이러한 제한 팀 수에 도달하지 않고 설정 시간을 연장하지 않도록 사용하지 않는 팀 수를 사전에 줄여야 합니다. 제한에 대한 자세한 내용은 [Microsoft Teams의 제한 사항 및 사양](limits-specifications-teams.md)을 참조하세요.  
