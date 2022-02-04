---
title: 할당에 Teams
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
description: 관리 센터의 Microsoft Teams 관리 교육용 Teams.
ms.localizationpriority: medium
appliesto:
- Microsoft Teams
ms.openlocfilehash: 88414131b5ba8fee750efef8d0b6f6f5313e13fd
ms.sourcegitcommit: 1129841e68e927fe7cc31de3ad63a3e9247253cd
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/03/2022
ms.locfileid: "62363144"
---
# <a name="assignments-in-teams-for-education"></a>교육용 Teams의 과제

과제 및 성적 기능은 교육용 Teams 학생에게 작업, 작업 또는 퀴즈를 할당할 수 있도록 합니다. 교육자는 과제 일정, 지침, 전환할 리소스를 추가하고, 루브릭을 사용하여 채점할 수 있습니다. 성적 탭에서 수업 및 개별 학생 진행률을 추적할 수도 있습니다.

[과제 및](https://support.office.com/article/microsoft-teams-5aa4431a-8a3c-4aa5-87a6-b6401abea114?ui=en-US&rs=en-IE&ad=IE#ID0EAABAAA=Assignments) 성적에 대해 교육용 Teams.

> [!Note]
> 다른 플랫폼에서 Teams 할당에 대한 자세한 내용은 플랫폼 Teams [기능을 참조하세요](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3).

## <a name="assignments-integrations-in-the-microsoft-teams-admin-center"></a>관리 센터의 할당 Microsoft Teams 통합

관리 센터의 관리자 Microsoft Teams 사용하여 조직 및 해당 학생의 교육자에 대한 기능을 켜거나 해제할 수 있습니다. 과제와 관련된 설정은 다음과 같습니다.

<a name="#bkemaildigest"> </a>

### <a name="weekly-guardian-email-digest"></a>주간 보호자 전자 메일 다이제스트

보호자 전자 메일은 주말마다 부모 또는 보호자에게 전송됩니다. 전자 메일에는 이전 주 및 다가오는 주에 대한 과제에 대한 정보가 포함되어 있습니다. 부모 및 보호자 동기화는 [학교 데이터 동기화.](/schooldatasync/parent-contact-sync)

1. SDS에서 부모 및 보호자 동기화를 통해 부모 연락처 정보를 가져올 수 있습니다. 부모 및 보호자 동기화를 사용하도록 설정하는 방법에 대한 지침은 부모 및 보호자 동기화 [사용 을 참조하세요](/schooldatasync/parent-contact-sync#enabling-parent-and-guardian-sync).

2. 설정이 기본적으로 꺼져 Microsoft Teams 관리 센터에서 보호자 설정을  켜면 됩니다. 이렇게 하면 교사가 매주 다이제스트를 보낼 수 있습니다.

   > [!NOTE]
   > 교사는 자신의 개인 수업 팀 내에서 설정을 선택 해제하여 다이제스트를 옵트아웃할 수 있습니다 **(학부모/** 보호자 설정 > 할당).

부모가 전자 메일을 받을지 확인하려면 다음 세 항목이 true가 되어야 합니다.

- SDS의 학생 프로필에 첨부되어 부모 또는 보호자로 _태그가 지정_ 된 전자 메일 _주소입니다_. 자세한 내용은 [부모 및 보호자 동기화 파일 형식을 참조합니다](/schooldatasync/parent-contact-sync-file-format).

- 학생은 과제 설정에서 교사가 전자 메일을 사용하지 않도록 설정하지 않는 하나 이상의 수업 [에 속합니다](https://support.microsoft.com/office/adjust-assignment-settings-in-your-class-team-05bb3b89-1cdf-415a-b6c7-44add0376a77).

- 전자 메일에는 이전 주 또는 다가오는 주에 기한이 있는 할당에 대한 정보가 포함되어 있습니다.

이 기능에 대한 기본 설정은 - **꺼집니다**.

<a name="bkmakecode"> </a>

### <a name="makecode"></a>MakeCode

Microsoft MakeCode는 모든 학생에게 컴퓨터 과학을 생명으로 만드는 블록 기반 코딩 플랫폼입니다.

MakeCode는 Microsoft 사용 약관 및 개인 정보 취급 방침이 적용 [된 Microsoft](https://go.microsoft.com/fwlink/?LinkID=206977) [제품](https://go.microsoft.com/fwlink/?LinkId=521839) 입니다.

이 기능에 대한 기본 설정은 - **꺼집니다**.

MakeCode 할당을 Teams 관리 센터로 Teams 관리 센터로 이동 **하고 과제 섹션** 으로 이동한 다음 MakeCode 토글 옵션을  켜기로 **설정합니다**. **저장** 을 클릭합니다. 이러한 설정이 적용되는 데 몇 시간을 허용합니다.

이 기능의 작동 방식에 대한 자세한 내용은 이 비디오 데모 [를 시청하세요](https://makecode.com/blog/teams/teams-assignments).

[MakeCode에 대해 자세히 알아보자](https://aka.ms/makecode).

<a name="#turnitin"> </a>

### <a name="turnitin"></a>Turnitin

[Turnitin](https://www.turnitin.com/) 은 학업 무결성 서비스입니다. 이 서비스는 자체 약관 및 개인 정보 취급 방침을 적용하는 타사 서비스입니다. 귀하는 타사 제품 및 서비스를 사용할 책임이 있습니다.

이 기능에 대한 기본 설정은 - **Off**.입니다.

조직에 대해 Turnitin을 사용하도록 설정하려면 Turnitin 구독이 필요합니다. 그런 다음 Turnitin 관리 콘솔에서 찾을 수 있는 다음 정보를 입력할 수 있습니다.

- **TurnitinApiKey**: 통합 아래 관리 콘솔에서 찾을 수 있는 32자 GUID입니다.
- **TurnitinApiUrl**: Turnitin 관리 콘솔의 HTTPS URL입니다.

이 정보를 얻는 데 도움이 되는 몇 가지 지침은 다음과 같습니다.

**TurnitinApiUrl** 은 관리자 콘솔의 호스트 주소입니다.
예: `https://your-tenant-name.turnitin.com`

관리 콘솔은 통합과 연결된 통합 및 API 키를 만들 수 있는 위치입니다.

사이 **드 메뉴에서** 통합을 선택한 다음 통합 추가  를 선택하고 통합 이름을 지정합니다.

![새 통합을 추가하는 스크린샷.](./educationImages/Assignments_mopo_turnitin2.png)

**프롬프트에 따라 TurnitinApiKey** 가 제공됩니다.
API 키를 복사하여 관리 센터에 Microsoft Teams 붙여넣습니다.  키를 볼 수 있는 유일한 시간입니다.

![API 키를 복사하는 스크린샷.](./educationImages/Assignments_mopo_turnitin3.png)

이 설정에 대한  관리 센터에서 저장 단추를 클릭하면 이러한 설정이 적용되는 데 몇 시간이 걸릴 수 있습니다.

## <a name="assignments-data"></a>할당 데이터

과제는 교사와 학생이 모두 생성한 정보를 저장합니다. 모든 데이터는 교사와 수업에서 정보가 의도된 특정 학생 간에 공유됩니다. 이 두 개의 저장소가 있으며, SharePoint 외부에 SharePoint.

>[!NOTE]
>진행률 읽기와 같은 제1자 통합에도 동일한 규칙이 적용됩니다.

### <a name="assignments-data-in-sharepoint-document-libraries"></a>문서 라이브러리의 SharePoint 할당

과제 제출과 연결된 학생의 파일은 문서 라이브러리에 저장됩니다(명명: *Student Work).* 교사가 생성하고 학생이 액세스할 수 있는 과제와 연결된 파일은 해당 수업 팀 웹 사이트의 다른 문서 라이브러리(클래스 파일SharePoint 저장됩니다. 또한 과제 데이터를 동일한 클래스 팀 SharePoint 사이트에 저장할 수도 있습니다(명명: 과제 제목 + 타임스탬 *프).*

#### <a name="files-associated-with-the-student"></a>학생과 연결된 파일

IT 관리자는 콘텐츠 검색 도구를 사용하여 과제 제출 및 과제와 관련된 파일과 관련된 학생 파일(*학생* *작업, 수업* 파일 또는 기타 제1자 통합 파일)을 검색할 수 있습니다. 예를 들어 관리자는 조직의 모든 SharePoint 검색하고 검색 쿼리에서 학생의 이름 및 수업 또는 과제 이름을 사용하여 DSR(데이터 주체 요청)과 관련된 데이터를 찾을 수 있습니다.

#### <a name="files-associated-with-the-teacher"></a>교사와 연결된 파일

IT 관리자는 콘텐츠 검색 도구를 사용하여 과제와 관련된 교사 파일(*학생* *작업, 수업* 파일 또는 기타 제1자 통합 파일)을 검색할 수 있습니다. 예를 들어 관리자는 조직의 모든 SharePoint 검색하고 검색 쿼리에서 교사의 이름 및 수업 또는 과제 이름을 사용하여 DSR과 관련된 데이터를 찾을 수 있습니다.

### <a name="assignments-data-outside-of-sharepoint-document-libraries"></a>문서 라이브러리 외부의 SharePoint 할당

할당과 관련된 일부 데이터는 클래스 팀 SharePoint 사이트에 저장되지 않습니다. 즉, Content Search에서 검색할 수 없습니다. 여기에는 다음이 포함됩니다.

- 교사의 학생 성적 및 피드백
- 각 학생이 과제에 제출한 문서 목록
- 기한 등 할당 세부 정보
- 진행률 구절 읽기 또는 학생 발음 데이터와 같은 자사 통합 데이터

이러한 유형의 데이터의 경우 IT 관리자 또는 데이터 소유자(예: 교사)가 수업 팀의 과제로 이동하여 DSR과 관련된 데이터를 찾아야 할 수 있습니다. 관리자는 클래스에 소유자로 자신을 추가하고 해당 클래스 팀에 대한 모든 과제를 볼 수 있습니다.

>[!NOTE]
>학생이 수업에 더 이상 참여하지 않은 경우 더 이상 등록되지 않은 경우 해당 데이터가 수업에 계속 존재할 *수 있습니다*. 학생은 테넌트 관리자에게 해당 클래스의 목록을 제공해야 합니다.

### <a name="bulk-export-assignment-data-outside-of-sharepoint-document-libraries"></a>문서 라이브러리 외부의 대량 내보내기 SharePoint 데이터

#### <a name="for-a-student"></a>학생용

단일 학생의 데이터를 대량으로 내보내기 위해 학생이 참여하는 수업에서 학생을 제거하기 전에 스크립트를 실행 [](/microsoft-365/education/deploy/configure-assignments-for-teams)하고 을 제공합니다``userId``. 학생이 ``userId`` ``classId`` 사이트에서 제거된 경우 관리자는 스크립트를 실행하기 전에 학생을 다시 수업에 추가할 수 있습니다. 또는 관리자가 학생의 일부인 학생을 제공할 수 있습니다.

학생 제출에 대한 데이터는 내보낼 것입니다.

#### <a name="for-a-teacher"></a>교사의 경우

대량 내보내기 과제 데이터는 학생에게 동일한 방식으로 작동하지만 교사가 액세스할 수 있는 모든 제출은 내보낼 수 있습니다.

### <a name="bulk-delete-assignment-data-outside-of-sharepoint-document-libraries"></a>문서 라이브러리 외부에서 할당 SharePoint 대량 삭제

#### <a name="for-a-student"></a>학생용

단일 학생의 데이터를 대량으로 삭제하려면 학생이 참여하는 수업에서 학생을 제거하기 전에 스크립트를 실행하고 [](/microsoft-365/education/deploy/configure-assignments-for-teams) 을 제공합니다``userId``. 학생이 ``userId`` ``classId`` 사이트에서 제거된 경우 관리자는 스크립트를 실행하기 전에 학생을 다시 수업에 추가할 수 있습니다. 또는 관리자가 학생의 일부인 학생을 제공할 수 있습니다.

a를 ``ClassId`` 제공하면 관리자가 특정 수업에서 학생에 대한 정보만 삭제할 수 있습니다.

#### <a name="for-a-teacher"></a>교사의 경우

교사에 대한 과제의 데이터는 수업에서 공유하기 때문에 일괄 삭제 옵션이 없습니다. 대신 관리자는 수업에 자신을 추가하고, 앱으로 이동한 다음 과제를 삭제할 수 있습니다.

자세한 내용은 에 대한  [할당](/microsoft-365/education/deploy/configure-assignments-for-teams) 구성을 Teams.

## <a name="removing-assignments-and-grades"></a>과제 및 성적 제거

또한 특정 사용자 또는 Teams 할당 및 성적을 제거할 수 있습니다.

개별 사용자에 대한 할당 및 성적을 제거하려면 관리 센터로 Teams  관리 센터로 이동하여 Teams > 정책으로 이동하여 새 앱 사용 **권한** 정책 정의를 만들 수 있습니다.  새 정책 정의를 만들 때 Microsoft 앱 정책을 **특정** 앱 차단으로  설정하고 다른 모든 앱을 허용하고 할당을  차단된 애플리케이션 목록에 추가합니다. 새 정책 정의가 저장되고 나면 해당 사용자에게 할당합니다.

전체 **테** 넌트에 대한 할당 및 성적을 제거하려면 관리 센터로 Teams 관리 센터로 이동하여 앱 관리 Teams > 앱으로 이동한 다음, 애플리케이션 목록에서 **과제** 를 검색하고 선택합니다. 할당 애플리케이션 설정 페이지에서 상태 설정을 차단으로 _변경합니다_.
