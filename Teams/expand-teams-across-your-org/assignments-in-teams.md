---
title: Teams 과제
author: DaniEASmith
ms.author: danismith
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
search.appverid: MET150
ms.reviewer: jastark
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.assignments.overview
- ms.teamsadmincenter.assignments.tooltip.emaildigest
- ms.teamsadmincenter.assignments.tooltip.makecode
- ms.teamsadmincenter.assignments.tooltip.turnitin
description: 교육용 Teams Microsoft Teams 관리 센터에서 과제를 관리하는 방법을 알아봅니다.
ms.localizationpriority: medium
appliesto:
- Microsoft Teams
ms.openlocfilehash: 91afcd8036cddfae2550aaddad776958ca413a78
ms.sourcegitcommit: 8b33cc2c2e8f43e6ab4b17715d6a42692351ccad
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/08/2022
ms.locfileid: "67624298"
---
# <a name="assignments-in-teams-for-education"></a>교육용 Teams의 과제

교육용 Teams 과제 및 성적 기능을 통해 교육자는 학생에게 작업, 작업 또는 퀴즈를 할당할 수 있습니다. 교육자는 과제 타임라인, 지침을 관리하고, 전환할 리소스를 추가하고, 루브릭으로 등급을 매기는 등의 작업을 수행할 수 있습니다. 성적 탭에서 수업 및 개별 학생 진도를 추적할 수도 있습니다.

[교육용 Teams 과제 및 성적에 대해 자세히 알아보세요](https://support.office.com/article/microsoft-teams-5aa4431a-8a3c-4aa5-87a6-b6401abea114?ui=en-US&rs=en-IE&ad=IE#ID0EAABAAA=Assignments).

> [!Note]
> 다양한 플랫폼의 Teams 할당에 대한 자세한 내용은 [플랫폼별 Teams 기능을](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3) 참조하세요.

## <a name="assignments-integrations-in-the-microsoft-teams-admin-center"></a>Microsoft Teams 관리 센터의 과제 통합

Microsoft Teams 관리 센터의 관리자 설정을 사용하여 조직 내의 교육자와 학생에 대한 기능을 켜거나 끌 수 있습니다. 다음은 할당과 관련된 설정입니다.

<a name="#bkemaildigest"> </a>

### <a name="weekly-guardian-email-digest"></a>주간 보호자 전자 메일 다이제스트

보호자 이메일은 매주 주말마다 부모 또는 보호자에게 전송됩니다. 전자 메일에는 이전 주 및 다음 주의 과제에 대한 정보가 포함되어 있습니다. [학교 데이터](/schooldatasync/parent-contact-sync) 동기화를 사용하여 부모 및 보호자 동기화를 설정할 수 있습니다.

1. SDS에서 부모 및 보호자 동기화를 통해 부모 연락처 정보를 가져옵니다. 부모 및 보호자 동기화를 사용하도록 설정하는 방법에 대한 지침은 [부모 및 보호자 동기화를 사용하도록 설정하는 방법을](/schooldatasync/parent-contact-sync#enabling-parent-and-guardian-sync) 참조하세요.

2. 설정이 기본적으로 꺼져 있으므로 Microsoft Teams 관리 센터에서 보호자 설정을 켭니다. 이를 통해 교사는 주간 다이제스트를 보낼 수 있습니다.

   > [!NOTE]
   > 교사는 자신의 개인 수업 팀 내에서 설정을 선택 취소하여 다이제스트를 옵트아웃할 수 있습니다(**과제 설정 > 부모/보호자 이메일**).

부모가 전자 메일을 받는지 확인하려면 다음 세 가지 항목이 true여야 합니다.

- Email 주소는 SDS에서 학생 프로필에 연결되고 _부모_ 또는 _보호자_ 로 태그가 지정됩니다. 자세한 내용은 [부모 및 보호자 동기화 파일 형식](/schooldatasync/parent-contact-sync-file-format)을 참조하세요.

- 학생은 [과제 설정](https://support.microsoft.com/office/adjust-assignment-settings-in-your-class-team-05bb3b89-1cdf-415a-b6c7-44add0376a77)에서 교사가 전자 메일을 사용하지 않도록 설정하지 않은 하나 이상의 수업에 속합니다.

- 전자 메일에는 이전 주 또는 다음 주의 기한이 있는 과제에 대한 정보가 포함됩니다.

이 기능에 대한 기본 설정은 - **Off** 입니다.

<a name="bkmakecode"> </a>

### <a name="makecode"></a>MakeCode

Microsoft MakeCode는 모든 학생에게 컴퓨터 과학을 실현하는 블록 기반 코딩 플랫폼입니다.

MakeCode는 Microsoft [사용 약관](https://go.microsoft.com/fwlink/?LinkID=206977) 및 [개인 정보 취급 방](https://go.microsoft.com/fwlink/?LinkId=521839) 침의 적용을 받는 Microsoft 제품입니다.

이 기능에 대한 기본 설정은 - **Off** 입니다.

Teams에서 MakeCode 할당을 사용하도록 설정하려면 **Teams 관리 센터로** 이동하여 **과제** 섹션으로 이동한 다음 MakeCode 토글 옵션을 **켜** 기로 설정합니다. **저장** 을 선택합니다. 이러한 설정이 적용되는 데 몇 시간 정도 걸릴 수 있습니다.

이 기능의 작동 방식에 대한 자세한 내용은 이 [비디오 데모](https://makecode.com/blog/teams/teams-assignments)를 시청하세요.

[MakeCode에 대해 자세히 알아보세요](https://aka.ms/makecode).

<a name="#turnitin"> </a>

### <a name="turnitin"></a>Turnitin

[Turnitin](https://www.turnitin.com/) 은 교육 무결성 서비스입니다. 이는 자체 약관 및 개인 정보 취급 방침의 적용을 받는 타사 서비스입니다. 타사 제품 및 서비스의 사용에 대한 책임은 귀하에게 있습니다.

이 기능에 대한 기본 설정은 - **Off** 입니다.

조직에 대해 Turnitin을 사용하도록 설정하려면 Turnitin 구독이 필요합니다. 그런 다음 Turnitin 관리 콘솔에서 찾을 수 있는 다음 정보를 입력할 수 있습니다.

- **TurnitinApiKey**: 통합 아래의 관리 콘솔에 있는 32자 GUID입니다.
- **TurnitinApiUrl**: Turnitin 관리 콘솔의 HTTPS URL입니다.

이 정보를 얻는 데 도움이 되는 몇 가지 지침은 다음과 같습니다.

**TurnitinApiUrl** 은 관리 콘솔의 호스트 주소입니다.
예: `https://your-tenant-name.turnitin.com`

관리 콘솔에서는 통합 및 통합과 연결된 API 키를 만들 수 있습니다.

사이드 메뉴에서 통합을 선택한 다음 통합 추가를 선택하고 **통합** 에 이름을 지정 **합니다**.

![새 통합 추가를 보여 주는 스크린샷](./educationImages/Assignments_mopo_turnitin2.png)

메시지가 표시되면 **TurnitinApiKey** 가 제공됩니다.
API 키를 복사하여 Microsoft Teams 관리 센터에 붙여넣습니다.  키를 볼 수 있는 유일한 시간입니다.

![API 키 복사를 보여 주는 스크린샷](./educationImages/Assignments_mopo_turnitin3.png)

이 설정에 대한 관리 센터에서 **저장** 단추를 클릭하면 이러한 설정이 적용되는 데 몇 시간이 걸릴 수 있습니다.

## <a name="assignments-data"></a>할당 데이터

과제는 교사와 학생 모두에 의해 생성된 정보를 저장합니다. 모든 데이터는 수업에서 정보가 의도된 교사와 특정 학생 간에 공동으로 공유됩니다. 이 데이터에는 SharePoint와 SharePoint 외부의 두 저장소가 있습니다.

>[!NOTE]
>읽기 진행률과 같은 자사 통합에도 동일한 규칙이 적용됩니다.

### <a name="assignments-data-in-sharepoint-document-libraries"></a>SharePoint 문서 라이브러리의 할당 데이터

과제 제출과 연결된 학생의 파일은 문서 라이브러리(이름: *Student Work*)에 저장됩니다. 교사가 만들고 학생이 액세스할 수 있는 과제와 연결된 파일은 해당 수업 팀 SharePoint 사이트의 다른 문서 라이브러리(이름: *수업 파일*)에 저장됩니다. 자사 통합은 동일한 클래스 팀 SharePoint 사이트(이름: *과제 제목 + 타임스탬프를*)에 할당 데이터를 저장할 수도 있습니다.

#### <a name="files-associated-with-the-student"></a>학생과 연결된 파일

IT 관리자는 콘텐츠 검색 도구를 사용하여 과제 제출 및 과제와 관련된 파일과 관련된 학생 파일(*학생 작업*, *수업 파일* 또는 기타 자사 통합 파일)을 검색할 수 있습니다. 예를 들어 관리자는 조직의 모든 SharePoint 사이트를 검색하고 검색 쿼리에서 학생의 이름과 수업 또는 과제 이름을 사용하여 DSR(데이터 주체 요청)과 관련된 데이터를 찾을 수 있습니다.

#### <a name="files-associated-with-the-teacher"></a>교사와 연결된 파일

IT 관리자는 콘텐츠 검색 도구를 사용하여 과제에 대한 수업 내에서 교사가 학생에게 배포한 과제 및 파일과 관련된 교사 파일(*학생 작업*, *수업 파일* 또는 기타 자사 통합 파일)을 검색할 수 있습니다. 예를 들어 관리자는 조직의 모든 SharePoint 사이트를 검색하고 검색 쿼리에서 교사의 이름과 수업 또는 과제 이름을 사용하여 DSR과 관련된 데이터를 찾을 수 있습니다.

### <a name="assignments-data-outside-of-sharepoint-document-libraries"></a>SharePoint 문서 라이브러리 외부의 할당 데이터

과제와 관련된 일부 데이터는 수업 팀 SharePoint 사이트에 저장되지 않으므로 콘텐츠 검색을 통해 검색할 수 없습니다. 여기에는 다음이 포함됩니다.

- 교사의 학생 성적 및 피드백
- 각 학생이 과제에 대해 제출한 문서 목록
- 기한 등과 같은 배정 세부 정보
- 진행률 읽기 구절 또는 학생 발음 데이터와 같은 자사 통합 데이터

이러한 유형의 데이터의 경우 IT 관리자 또는 교사와 같은 데이터 소유자는 DSR과 관련된 데이터를 찾기 위해 수업 팀의 과제로 이동해야 할 수 있습니다. 관리자는 자신을 수업에 소유자로 추가하고 해당 수업 팀의 모든 과제를 볼 수 있습니다.

>[!NOTE]
>학생이 더 이상 수업에 참여하지 않는 경우 해당 데이터는 *더 이상 등록되지 않은* 상태로 수업에 계속 있을 수 있습니다. 학생은 테넌트 관리자에게 자신이 속한 클래스 목록을 제공해야 합니다.

### <a name="bulk-export-assignment-data-outside-of-sharepoint-document-libraries"></a>SharePoint 문서 라이브러리 외부에서 할당 데이터 대량 내보내기

#### <a name="for-a-student"></a>학생용

단일 학생의 데이터를 대량으로 내보내려면 해당 학생이 속한 수업에서 학생을 제거하기 전에 [스크립트를 실행하고](/microsoft-365/education/deploy/configure-assignments-for-teams) 입력합니다 ``userId``. 학생이 사이트에서 제거된 경우 관리자는 스크립트를 실행하기 전에 학생을 수업에 다시 추가하거나, 관리자가 학생이 속한 학생과 ``classId`` 학생을 제공할 ``userId`` 수 있습니다.

학생 제출에 대한 데이터를 내보냅니다.

#### <a name="for-a-teacher"></a>교사용

대량 내보내기 과제 데이터는 학생과 동일한 방식으로 작동하지만 교사가 액세스할 수 있는 모든 제출이 내보내질 것입니다.

### <a name="bulk-delete-assignment-data-outside-of-sharepoint-document-libraries"></a>SharePoint 문서 라이브러리 외부의 할당 데이터 대량 삭제

#### <a name="for-a-student"></a>학생용

단일 학생의 데이터를 대량으로 삭제하려면 해당 학생이 속한 수업에서 학생을 제거하기 전에 [스크립트를 실행하고](/microsoft-365/education/deploy/configure-assignments-for-teams) 입력합니다 ``userId``. 학생이 사이트에서 제거된 경우 관리자는 스크립트를 실행하기 전에 학생을 수업에 다시 추가하거나, 관리자가 학생이 속한 학생과 ``classId`` 학생을 제공할 ``userId`` 수 있습니다.

``ClassId`` 을 제공하면 관리자는 특정 수업에서 학생에 대한 정보만 삭제할 수 있습니다.

#### <a name="for-a-teacher"></a>교사용

교사에 대한 과제의 데이터는 수업 전체에서 공유되므로 대량 삭제 옵션이 없습니다. 대신 관리자는 클래스에 자신을 추가하고 앱으로 이동하여 할당을 삭제할 수 있습니다.

자세한 내용은 [Teams에 대한 할당 구성을 참조하세요](/microsoft-365/education/deploy/configure-assignments-for-teams).

## <a name="removing-assignments-and-grades"></a>과제 및 성적 제거

Teams 정책을 사용하여 특정 사용자 또는 전체 테넌트에 대한 과제 및 성적을 제거할 수도 있습니다.

개별 사용자의 과제 및 성적을 제거하려면 **Teams 관리 센터로** 이동하여 **Teams 앱 > 사용 권한 정책** 으로 이동하여 새 앱 사용 권한 정책 정의를 만듭니다.  새 정책 정의를 만들 때 **Microsoft 앱** 정책을 설정하여 _특정 앱을 차단하고 다른 모든 앱을 허용_ 하고 **차단** 된 애플리케이션 목록에 과제 및 **성적을** 추가합니다. 새 정책 정의가 저장되면 적절한 사용자에게 할당합니다.

전체 테넌트에 대한 과제 및 성적을 제거하려면 **Teams 관리 센터로** 이동하여 **Teams 앱 > 앱 관리** 로 이동한 후 애플리케이션 목록에서 **과제** 및 **성적을** 검색하여 선택합니다. 애플리케이션의 설정 페이지 내 상태 설정을 _차단됨_ 으로 변경합니다.

## <a name="assignments-diagnostic-tool-for-users"></a>사용자를 위한 할당 진단 도구

Microsoft 지원 Microsoft 엔지니어링 팀이 과제 기능과 관련된 문제를 조사하기 위해 진단 데이터를 수집하는 도구를 만들었습니다.

이 도구는 사용자가 문제가 발생하는 모든 화면에서 할당 내에서 액세스할 수 있습니다.

Teams에서 진단 도구를 끌어오려면 다음을 수행할 수 있습니다.

- **데스크톱 및 웹에서:**
  - Ctrl+/를 선택합니다.
- **모바일 디바이스에서:**
  - 두 손가락으로 화면을 터치하고 손가락을 45도 회전하거나
  - 15초 동안 세 손가락으로 화면을 탭합니다.

진단 도구가 나타나면 Microsoft 기술 지원에 필요할 수 있는 데이터 목록이 사용자에게 표시됩니다.

끌어온 데이터에는 다음이 포함될 수 있습니다.

- 그룹 ID
- 테넌트 ID
- 세션 ID
- 할당 ID
- 제출 ID
- 사용자 ID

이 데이터는 Microsoft에 자동으로 전송되지 않습니다. 사용자는 지원 티켓과 관련하여 데이터를 복사하여 Microsoft 지원 에이전트에 붙여넣어야 합니다.

사용자가 진단 도구를 끌어온 다음 닫으면 데이터가 전송되지 않습니다.

데이터가 Microsoft 지원 에이전트로 전송되면 조직의 Microsoft 365 서비스 계약에 따라 지원 데이터로 처리됩니다.

교육자 및 학생과 공유할 수 있는 이 진단 도구를 사용하는 방법에 대한 지침은 [진단 데이터 가져오기를 참조하여 과제 문제를 해결합니다](https://support.microsoft.com/topic/b40793f5-dbae-4c8a-841a-6baa7f232e2e).
