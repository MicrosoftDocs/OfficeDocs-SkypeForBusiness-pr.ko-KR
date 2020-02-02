---
title: Teams에서 수명 주기 관리 계획 - Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 09/26/2018
ms.topic: reference
ms.service: msteams
ms.reviewer: rowille
audience: admin
description: Teams에서 수명 주기 관리 기능을 구현하는 방법에 대해 알아봅니다.
localization_priority: Priority
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3a0e055305cc994730b22507b5ce0cf1823e43f0
ms.sourcegitcommit: ed3a6789dedf54275e0b1ab41d4a4230eed6eb72
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/30/2020
ms.locfileid: "41628374"
---
# <a name="plan-for-lifecycle-management-in-teams"></a>Teams에서 수명 주기 관리 계획

Teams에서는 조직의 공동 작업 수명 주기 관리 프로세스를 구현하기 위한 다양한 도구 집합을 제공합니다. 이 문서에서는 IT 전문가에게 올바른 질문을 통해 수명 주기 관리를 위한 요구 사항과 이를 충족하는 데 사용하는 도구를 파악하도록 안내합니다. 

수명 주기 관리를 계획하는 것은 작업을 효과적으로 완료할 계획을 세울 수 있기 때문에 중요합니다. 프로젝트는 대부분 시작, 중간 및 끝으로 구성됩니다. Teams도 마찬가지이지만, 이러한 도구는 다양한 방식으로 구성 및 사용할 수 있으므로 수명 주기의 어느 단계에 있는지 항상 명확하지는 않습니다. 수명 주기 관리 계획을 세우면 조직의 프로젝트가 이러한 단계를 거치는 과정에서 이를 추적하는 데 도움이 됩니다.

> [!Tip]
> Microsoft Teams의 수명 주기에 대해 자세히 알아보려면 다음 세션을 시청하세요. [Microsoft Teams에서 거버넌스, 관리 및 수명 주기](https://aka.ms/teams-governance)


## <a name="lifecycle-concepts"></a>수명 주기 개념

다음 개념과 정의는 모두 수명 주기 관리에 대한 의사 결정에 영향을 줍니다.

**Teams**

_팀_은 공동 작업을 지원하는 사용자, 콘텐츠 및 도구의 컬렉션입니다. 팀은 구성원을 정의하고 해당 구성원에게 적용되는 사용 권한 및 정책을 정의합니다. Teams는 Office 365 그룹에 기반하며 Office 365 그룹 멤버 자격 동기화에 대한 변경 사항이 소속 팀에 동기화됩니다. 다른 Office 365 그룹과 마찬가지로 Teams는 Exchange 사서함, SharePoint 사이트, OneNote 전자 필기장 및 Office 365 내의 다른 자산으로 자동 프로 비전을 제공합니다. [Office 365 그룹에 대해 자세히 알아보세요](https://support.office.com/article/Learn-about-Office-365-groups-b565caa1-5c40-40ef-9915-60fdb2d97fa2).

**채널**

채널은 실제 작업이 수행되는 팀 내의 공동 작업 공간입니다. 각 채널은 전체 팀 내의 다른 주제 또는 작업 흐름을 나타냅니다. 각 채널에서 폴더는 해당 채널에 공유된 모든 파일을 저장할 수 있도록 SharePoint 사이트에 자동 생성되어 사용자가 관심 있는 문서를 쉽게 찾고 작업할 수 있습니다. 특정 작업 흐름에 관련된 앱을 사용하여 채널을 확장할 수도 있습니다. 예를 들어 채널에 Power BI 대시보드를 추가하여 프로젝트의 한 측면에 대한 성공 여부를 추적할 수 있습니다.

**팀 액세스 유형**

팀에 참가할 수 있는 사용자를 결정합니다.

-   _비공개_ 팀은 팀 소유자가 승인한 팀 구성원에게 제한됩니다. 이는 대규모 조직에서 프로젝트 팀과 가상 팀에 대한 일반적인 설정입니다.
-   _공개_ 팀은 조직의 모든 사용자가 직접 참가할 수 있도록 열려 있습니다. 이 기능은 서로 다른 프로젝트에서 작업하는 다양한 부서 사용자의 일반 관심 영역의 주제에 대한 공동 작업에 유용합니다. 이는 소규모 조직에 적합한 기본 설정입니다.

**팀 사용자 유형 및 관리자 역할** 

팀 사용자 유형은 팀 구성원이 가진 제어 수준을 결정합니다.

-   _팀 생성자_는 디렉터리에서 그룹 또는 팀을 만들 수 있는 권한을 가집니다. 관리자는 이 사용자 유형을 관리자 또는 사용자의 하위 집합으로 제한할 수 있습니다. 자세한 내용은 [Office 365 그룹을 만들 수 있는 사용자 관리](https://support.office.com/article/Manage-who-can-create-Office-365-Groups-4c46c8cb-17d0-44b5-9776-005fced8e618)를 참조하세요. 
-   _팀 소유자_는 팀에 대한 멤버 자격과 설정을 관리합니다. 팀마다 최대 100명의 팀 소유자가 있을 수 있습니다.
-   _팀 구성원_은 팀에 참가하는 조직의 구성원입니다.
-   _게스트_는 조직 외부의 사용자입니다. 조직에서 [게스트 액세스](guest-access.md)를 사용하도록 설정한 경우 전자 메일 주소를 가진 모든 사용자를 게스트로 초대할 수 있습니다.

> [!Note]
> [Microsoft Teams에서 역할 및 사용 권한 할당](assign-roles-permissions.md) 문서에서 팀 소유자와 팀 구성원 기능에 대한 자세한 내용을 확인할 수 있습니다.

Teams 관리자 역할이 각 관리자 역할 보유자의 기능을 결정합니다. 다음 표에서 이에 대해 설명합니다.

<table>
 <thead>
  <tr>
    <th width="0.5%"></th>
    <th width="15.5%">역할&nbsp;&nbsp;</th>
    <th width="25%">설명</th>
    <th width="60%">설명한 대로 도구를 사용하여 수행할 수 있는 작업:</th>
  </tr>
</thead>
<tbody>
   <tr>
    <td valign="top" colspan="2">Teams 서비스 관리자</td>
    <td valign="top">Teams 서비스를 관리하며 Office 365 그룹을 만들고 관리</td>
    <td valign="top">모임 정책, 구성 및 회의 브리지 등의 모임을 관리<sup>1</sup><br><br>통화 정책, 전화번호 인벤토리 및 과제, 전화 큐 및 자동 전화 교환 등의 음성을 관리<sup>1</sup><br><br>메시지 정책 등의 메시지를 관리<sup>1</sup><br><br>페더레이션, Teams 업그레이드, Teams 클라이언트 설정을 포함하여 조직 전체 설정을 모두 관리<sup>1</sup><br><br>멤버 자격을 포함하여 조직의 팀과 관련 설정을 관리<sup>2</sup><br><br>고급 문제 해결 도구 집합을 사용하여 사용자 프로필 페이지를 확인하고 사용자 통화 품질 문제를 해결<sup>3</sup></td>
</tr>
<tr>
<td valign="top" colspan="2">Teams 커뮤니케이션 관리자</td>
<td valign="top">Microsoft Teams 서비스 내의 호출 및 모임 기능을 관리</td>
<td valign="top">모임 정책, 구성 및 회의 브리지 등의 모임을 관리<sup>1</sup><br><br>통화 정책, 전화번호 인벤토리 및 과제, 전화 큐 및 자동 전화 교환 등의 음성을 관리<sup>1</sup><br><br>고급 문제 해결 도구 집합을 사용하여 사용자 프로필 페이지를 확인하고 사용자 통화 품질 문제를 해결<sup>1</sup></td>
</tr>
<tr>
<td valign="top" colspan="2">Teams 커뮤니케이션 전문가</td>
<td valign="top">기본 도구를 사용하여 Teams 내의 커뮤니케이션 문제를 해결</td>
<td valign="top">사용자 프로필 페이지에 액세스하여 통화 분석에서 통화 문제를 해결할 수 있습니다. 검색하는 특정 사용자에 대한 사용자 정보만 볼 수 있습니다.<sup>3</sup></td>
</tr>
<tr>
<td valign="top" colspan="2">Teams 커뮤니케이션 지원 엔지니어</td>
<td valign="top">고급 도구를 사용하여 Teams 내의 커뮤니케이션 문제를 해결</td>
<td valign="top">사용자 프로필 페이지에 액세스하여 통화 분석에서 통화 문제를 해결할 수 있습니다. 전체 통화 레코드 정보를 볼 수 있습니다.<sup>3</sup></td>
</tr>
<tr>
</tbody>
<tfoot>
<tr><td align="right"><sup>1</sup></td><td colspan="3"><a href="https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell
">PowerShell - 비즈니스용 Skype 모듈</a> 또는 <a href="https://docs.microsoft.com/microsoftteams/manage-teams-skypeforbusiness-admin-center">Microsoft Teams 관리 센터</a></td></tr>
<tr><td align="right"><sup>2</sup></td><td colspan="3"><a href="https://www.powershellgallery.com/packages/MicrosoftTeams/0.9.3">PowerShell - Microsoft Teams 모듈</a> 또는 <a href="https://docs.microsoft.com/microsoftteams/manage-teams-skypeforbusiness-admin-center">Microsoft Teams 관리 센터</a></td></tr>
<tr><td align="right"><sup>3</sup></td><td colspan="3"><a href="https://docs.microsoft.com/microsoftteams/manage-teams-skypeforbusiness-admin-center">Microsoft Teams 관리 센터</a> 전용</td>
</tr>
</tfoot>
</table>


## <a name="it-decisions-to-make-before-getting-started"></a>시작하기 전에 해야 할 IT 의사 결정

Teams를 조직에서 시작하기 전에 조직에서 결정한 모든 필수 거버넌스 정책을 구현합니다. 여기에는 명명 규칙, 만료 정책, 보존 정책 등의 항목이 포함될 수 있습니다. 일반적으로 조직 전체에서 배포를 확장하기 전에 이러한 요구 사항을 구현하는 것이 훨씬 쉽습니다.

자세한 내용은 [Teams에서의 거버넌스 계획](plan-teams-governance.md)을 참조하세요.

## <a name="teams-lifecycle-stages"></a>Teams 수명 주기 단계

일반적으로 팀에는 프로젝트에 부합하거나 목표를 달성하는 목적이 있습니다. 팀이 공통 관심사를 기반으로 형성된 경우에도 팀 멤버 자격이 시간이 지나면서 변하고 토론이 부실해질 수 있으므로 결국 다른 팀에서 약간 다른 방식으로 다시 참가만 하게 됩니다.

팀을 만들고 채널을 설정하면 각 팀이 시작됩니다. 중간에는 팀을 사용해서 공동 작업을 진행하여 워크플로의 리듬을 일치시킵니다. 일부 경우에는 결국 팀이 목적을 이루고 해당 유효 수명이 종료됩니다. 

자세한 내용은 [Microsoft Teams 관리 센터에서 Teams 관리](manage-teams-in-modern-portal.md)를 참조하세요.

### <a name="stage-1-beginning"></a>1단계: 시작

#### <a name="create-the-team"></a>팀 만들기

첫 번째 단계는 팀의 목표를 정의하는 것입니다(목표는 비즈니스 프로세스에서 조직 구조 및 프로젝트에 이르는 범위를 다루거나, 단순히 비구조적 공동 작업 허브를 만드는 것일 수 있음). 팀 목표를 정의하면 올바른 사용자를 식별하는 데 도움이 됩니다. 실행 가능한 최대로 광범위한 멤버 자격을 목표로 공개 공동 작업을 권장하는 것이 좋습니다. 

팀 소유자는 팀 구성원을 초대하고 팀 그림 및 설명을 설정하며, 개별 구성원에 대한 사용 권한을 설정할 수 있습니다. 

> [!Tip]
>  결근 또는 재배정을 고려하여 2명 이상의 팀 소유자를 식별하는 것이 가장 좋습니다.

#### <a name="team-origins"></a>팀 원본

Teams는 다음과 같은 다양한 방법으로 시작할 수 있습니다.

-   처음부터 팀 만들기 개별 전자 메일 별칭 또는 사용자 이름을 사용하여 구성원을 추가하거나 배포 목록을 확장합니다.
-   기존 팀에서 팀을 만들고 해당 채널 구성과 앱 구성을 템플릿으로 사용합니다. 원하는 경우 해당 멤버 자격 목록을 사용할 수도 있습니다.
-   팀에 사서함과 SharePoint 사이트에 대한 액세스도 제공하는 기존 Office 365 그룹에 팀을 추가합니다.
-   Microsoft Graph Teams API 또는 PowerShell Cmdlet을 사용하여 팀을 만듭니다. API는 전체 주소록 특성(예: 영역 또는 부서) 또는 비즈니스 프로세스(예: 클라이언트 계약 또는 교실 명단)에 기반하여 프로그래밍 방식으로 팀을 만들 수 있습니다.

팀 구성에 대한 자세한 내용을 알아보려면 다음 링크를 사용하세요.

-   [Teams에서의 팀 구성에 대한 모범 사례](best-practices-organizing.md)
-   [채팅, 팀, 채널 및 앱 배포](deploy-chat-teams-channels-microsoft-teams-landing-page.md)
-   [모임 및 회의 배포](deploy-meetings-microsoft-teams-landing-page.md)
-   [클라우드 음성 배포](cloud-voice-landing-page.md)


|    |     |
|-----------|------------|
| ![의사 결정 지점을 묘사하는 아이콘](media/audio_conferencing_image7.png) <br/>의사 결정 지점|<ul><li>팀의 목적은 무엇인가요?</li><li>누가 팀에 속해 있나요?</li><li>팀이 개인적 혹은 공공 팀이 될 것인가요?</li><li>새 구성원이 자신을 추가하거나 팀 소유자가 추가할 수 있나요?</li><li>채널을 만들거나 탭, 봇 및 커넥터를 추가하는 권한은 누가 가질 것인가요?</li></ul> |
| ![다음 단계를 묘사하는 아이콘](media/audio_conferencing_image9.png)<br/>다음 단계|<ul><li>팀을 만듭니다.</li><li>채널을 계획합니다.</li></ul>|


#### <a name="set-up-channels"></a>채널 설정

팀 소유자나 적절한 사용 권한을 가진 구성원은 팀에서 채널을 만들 수 있습니다. 각 채널의 목표를 고려하는 것이 중요합니다. 프로젝트에 대한 공동 작업, 주제에 대한 토론 또는 공통 관심 영역을 예로 들 수 있습니다. 기본적으로 모든 팀에는 일반 채널이 포함되지만, 대부분의 팀은 보다 더 많은 채널을 원하므로 구성원이 추가 채널을 만들게 됩니다. 새 주제나 프로젝트가 발생하면 해당 채널 집합이 유기적으로 커지고 시작된 채널보다 토론 횟수가 많아질 수 있습니다.

흥미를 유발하기 위해 채널 소유자가 환영 메시지를 게시하거나 관련 문서를 **파일** 탭에 업로드하거나 탭 또는 커넥터를 채널에 추가할 수 있습니다. 또한 소유자는 채널 설명을 설정하고, 모든 팀 구성원에게 기본적으로 표시되도록 중요한 채널을 “자동 즐겨찾기 추가”할 수 있습니다.

|    |     |
|-----------|------------|
| ![의사 결정 지점을 묘사하는 아이콘](media/audio_conferencing_image7.png) <br/>의사 결정 지점|<ul><li>팀에 어떤 초기 채널이 추가될 예정인가요?</li><li>새 채널을 추가하기 위해 어떤 지침이 제공되나요(있는 경우)? (프로젝트, 주제 또는 ...별로 설정되나요?)</li></ul> |
| ![다음 단계를 묘사하는 아이콘](media/audio_conferencing_image9.png)<br/>다음 단계|<ul><li>초기 채널을 만듭니다.</li><li>환영 메시지를 게시합니다.</li><li>공동 작업을 시작합니다.</li></ul>|

### <a name="stage-2-middle"></a>2단계: 중간

팀워크가 시작되면 팀 멤버 자격이 채널 계층과 함께 변화하기 시작할 수 있습니다. 팀을 엄격하게 제어 및 차단할 필요가 없다면 검색 결과가 표시되지 않더라도 탐색을 권장하는 것이 좋습니다. 사용자가 익숙해질수록 \@팀 멘션을 실험하여 채널을 즐겨찾기로 표시하고, 일반 채널을 사용하여 편리하게 게시할 수 있습니다. 팀마다 다르므로 사용량에 따라 디자인을 개선합니다. Teams 보고 기능을 통해 팀의 사용 현황 및 상태를 모니터링합니다.

주요 그룹 커뮤니케이션이 Teams에서 시작되고 유지되므로 신뢰, 허용 범위 및 협업 정신이 유기적으로 증가합니다. 팀 구성원은 일대일 채팅을 통해 그룹 대화의 유용성을 알게 됩니다. 개별 팀에서는 Giphy 및 스티커와 같은 흥미로운 기능을 통해 자신의 퍼스낼리티를 개발하는 경향이 있습니다. 이와 동시에 독자적이거나 무례한 행동이 발생할 때마다 막는 것이 중요합니다.

팀은 유기적인 조직이므로 때때로 확인하고 신경써야 합니다. 다음은 몇 가지 모범 사례입니다.

-   챔피언을 사용하여 사용률이 떨어지기 시작할 때 이를 유지하고 창의적인 새로운 행동을 발견하고 전파합니다. 
-   게스트를 신중하게 관리하여 비즈니스를 끝내야 할 때 게스트의 액세스를 종료했는지 확인합니다.
-   필요에 따라 새로운 채널을 추가하고 기존 채널이 투명해지도록 비즈니스 요구 사항에 따라 채널을 발전시키세요. 또는 중요 또는 사용 후 삭제 데이터가 포함된 경우 보존 요구 사항에 따라 이를 보관하거나 삭제할 것을 고려합니다.
-   대규모 그룹이나 관심 기반 영역이 등장하면 새 팀을 만듭니다.
-   채널 모임 또는 문서에 대한 탭 대화와 같은 다른 채널 공동 작업을 시도합니다.

팀이 침체되기 시작하면 다음을 고려하세요.

-   커뮤니케이션을 전자 메일이 아니라 팀에 집중시킵니다.
-   모바일 앱을 사용하여 참여를 높입니다.
-   채널 수를 정리합니다.

|    |     |
|-----------|------------|
| ![의사 결정 지점을 묘사하는 아이콘](media/audio_conferencing_image7.png) <br/>의사 결정 지점|<ul><li>누가 사용률을 모니터링하여 문제를 식별할 것인가요?</li><li>어떤 수치를 사용하여 팀 상태가 정상인지 여부를 확인할 것인가요?</li><li>유효 수명이 종료된 팀을 식별합니다.</li><li>아직 목적을 수행하고 있으나 활성화가 필요한 비정상 팀을 식별합니다.</li></ul> |
| ![다음 단계를 묘사하는 아이콘](media/audio_conferencing_image9.png)<br/>다음 단계|<ul><li>개별 팀 상태를 모니터링하는 프로세스를 구현합니다.</li></ul>|

### <a name="stage-3-end"></a>3단계: 끝

팀의 작업 과정이 모두 실행되었으면 작업이 종료되었음을 공식적으로 승인하는 것이 중요합니다. 그러면 팀 구성원은 종료를 인식하고, 다른 사용자가 오래된 부실 정보에 액세스하지 못하도록 차단할 수 있습니다. 팀만을 사용하여 사후 분석과 개요서와 같은 종료 절차를 수행할 수 있습니다.

필요 없는 팀(예: 테스트전용으로 만든 팀 또는 중요한 데이터가 포함된 팀)을 삭제할 수 있습니다. IT에서 최대 21일(Office 365 그룹의 경우 30일) 동안 복구할 수 있는 "일시 삭제"를 사용하여 팀을 정말로 삭제할 수 있습니다. 팀 삭제는 준수 정책에 따라 유지되는 채팅 또는 콘텐츠에 영향을 주지 않습니다. 채널에는 "일시 삭제"가 있으며 삭제 후 최대 21일 동안 복구할 수 있습니다.

보관 기능 외에도 만료 및 보존 정책을 사용하여 더 이상 활동하지 않거나 소유자가 조직을 떠난 팀의 노출을 줄일 수 있습니다.

만료 및 보존 정책 설정에 대한 자세한 내용은 [Microsoft Teams의 보안 및 규정 준수 개요](security-compliance-overview.md)를 참조하세요.

|    |     |
|-----------|------------|
| ![의사 결정 지점을 묘사하는 아이콘](media/audio_conferencing_image7.png) <br/>의사 결정 지점|<ul><li>팀 수명 종료 시점의 징후를 정의합니다.</li><li>팀 콘텐츠의 사용 가능 여부와 해당 기간을 결정합니다.</li></ul> |
| ![다음 단계를 묘사하는 아이콘](media/audio_conferencing_image9.png)<br/>다음 단계|<ul><li>모범 사례 및 진행 중 얻은 개선 사항을 문서화합니다.</li><li>필요한 경우 데이터를 보관합니다.</li></ul>|

## <a name="related-topics"></a>관련 주제

[Teams에 대한 거버넌스 빠른 시작](teams-adoption-governance-quick-start.md)
