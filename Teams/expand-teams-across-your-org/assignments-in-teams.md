---
title: Teams에 대한 과제
author: cichur
ms.author: v-cichur
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
description: 교육용 Teams의 Microsoft Teams 관리 센터에서 과제를 관리하는 방법에 대해 자세히 알아보습니다.
localization_priority: Normal
appliesto:
- Microsoft Teams
ms.openlocfilehash: 410f5d32dd8af4775639a080725cd5680b6a70c2
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51121376"
---
# <a name="assignments-in-teams-for-education"></a>교육용 Teams의 과제

교육용 Teams의 과제 및 성적 기능을 통해 교사는 학생에게 작업, 작업 또는 퀴즈를 할당할 수 있습니다. 교육자는 과제 일정, 지침, 전환할 리소스를 추가하고, 루브릭을 사용하여 채점할 수 있습니다. 성적 탭에서 수업 및 개별 학생 진행률을 추적할 수도 있습니다.

교육용 Teams의 과제 및 [성적에 대해 자세히 알아보습니다.](https://support.office.com/article/microsoft-teams-5aa4431a-8a3c-4aa5-87a6-b6401abea114?ui=en-US&rs=en-IE&ad=IE#ID0EAABAAA=Assignments)

> [!Note]
> 다른 플랫폼에서 Teams 할당에 대한 자세한 내용은 플랫폼에 따라 [Teams 기능을 참조하세요.](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3)

## <a name="assignments-integrations-in-the-microsoft-teams-admin-center"></a>Microsoft Teams 관리 센터의 과제 통합

Microsoft Teams 관리 센터의 관리자 설정을 사용하여 조직 및 해당 학생의 교육자에 대한 기능을 켜거나 해제할 수 있습니다. 과제와 관련된 설정은 다음과 같습니다.

<a name="#bkemaildigest"> </a>
### <a name="weekly-guardian-email-digest"></a>주간 보호자 전자 메일 다이제스트


보호자 전자 메일은 주말마다 부모 또는 보호자에게 전송됩니다. 전자 메일에는 이전 주 및 다가오는 주에 대한 과제에 대한 정보가 포함되어 있습니다. 학교 데이터 동기화를 사용하여 부모 및 보호자 [동기화를 설정할 수 있습니다.](/schooldatasync/parent-contact-sync)

1. SDS에서 부모 및 보호자 동기화를 통해 부모 연락처 정보를 가져올 수 있습니다. 부모 및 보호자 동기화를 사용하도록 설정하는 방법에 대한 지침은 부모 및 보호자 동기화 사용 [을 참조하세요.](/schooldatasync/parent-contact-sync#enabling-parent-and-guardian-sync)

2. 설정이 기본적으로 꺼져 있는 경우 Microsoft Teams 관리 센터에서 보호자 설정을 켜면 됩니다. 이렇게 하면 교사가 매주 다이제스트를 보낼 수 있습니다.

   > [!NOTE]
   > 교사는 자신의 개인 수업 팀 내에서 설정을 선택 해제하여 다이제스트를 옵트아웃할 수 **있습니다(학부모/보호자**> 할당 설정).

부모가 전자 메일을 받을지 확인하려면 다음 세 항목이 true가 되어야 합니다.

 - SDS의 학생 프로필에 첨부되어 부모 또는 보호자로 _태그가_ 지정된 전자 메일 _주소입니다._ 자세한 내용은 부모 및 [보호자 동기화 파일 형식 을 참조합니다.](/schooldatasync/parent-contact-sync-file-format)

 - 학생은 과제 설정에서 교사가 전자 메일을 사용하지 않도록 설정하지 않는 하나 이상의 [수업에 속합니다.](https://support.microsoft.com/office/adjust-assignment-settings-in-your-class-team-05bb3b89-1cdf-415a-b6c7-44add0376a77)

 - 전자 메일에는 지난 주 또는 예정된 주에 기한이 있는 할당에 대한 정보가 포함되어 있습니다.

이 기능에 대한 기본 설정은 - **끄기입니다.**


<a name="bkmakecode"> </a>
### <a name="makecode"></a>MakeCode
Microsoft MakeCode는 모든 학생에게 컴퓨터 과학을 생명으로 만드는 블록 기반 코딩 플랫폼입니다. 

MakeCode는 Microsoft 사용 약관 및 개인 정보 취급 방침이 적용된 [Microsoft](https://go.microsoft.com/fwlink/?LinkID=206977) [제품입니다.](https://go.microsoft.com/fwlink/?LinkId=521839)

이 기능에 대한 기본 설정은 - **끄기입니다.**

Teams에서 MakeCode 할당을 사용하도록 설정하려면 **Teams 관리** 센터로 이동하고 과제 섹션으로 이동한 다음 MakeCode 토글 옵션을 **켜기로 설정합니다.**  **저장** 을 클릭합니다. 이러한 설정이 적용되는 데 몇 시간을 허용합니다.

이 기능의 작동 방식에 대한 자세한 내용은 이 비디오 데모 [를 참조하세요.](https://makecode.com/blog/teams/teams-assignments)

[MakeCode 에 대해 자세히 알아보자.](https://aka.ms/makecode)

<a name="#turnitin"> </a>
### <a name="turnitin"></a>Turnitin

[Turnitin은](https://www.turnitin.com/) 학업 무결성 서비스입니다. 자체 약관 및 개인 정보 취급 방침이 적용된 타사 제품 또는 서비스입니다. 귀하는 타사 제품 및 서비스를 사용할 책임이 있습니다.

이 기능에 대한 기본 설정은 - **끄기입니다.**

조직에 대해 Turnitin을 사용하도록 설정하려면 Turnitin 구독이 필요합니다. 그런 다음 Turnitin 관리 콘솔에서 찾을 수 있는 다음 정보를 입력할 수 있습니다.

  * **TurnitinApiKey:** 통합 아래 관리 콘솔에서 찾을 수 있는 32자 GUID입니다.
  * **TurnitinApiUrl**: Turnitin 관리 콘솔의 HTTPS URL입니다.

이 정보를 얻는 데 도움이 되는 몇 가지 지침은 다음과 같습니다.

**TurnitinApiUrl은** 관리자 콘솔의 호스트 주소입니다.
예: `https://your-tenant-name.turnitin.com`

관리 콘솔은 통합과 연결된 통합 및 API 키를 만들 수 있는 위치입니다.

사이드 **메뉴에서** 통합을 선택한  다음 통합 추가를 선택하고 통합 이름을 지정합니다.

![새 통합 추가를 보여주는 스크린샷](./educationImages/Assignments_mopo_turnitin2.png)

**프롬프트에 따라 TurnitinApiKey가** 제공됩니다. API 키를 복사하여 Microsoft Teams 관리 센터에 붙여넣습니다.  키를 볼 수 있는 유일한 시간입니다.

![API 키 복사를 보여주는 스크린샷](./educationImages/Assignments_mopo_turnitin3.png)

이 설정에  대한 관리 센터에서 저장 단추를 클릭하면 이러한 설정이 적용되는 데 몇 시간이 걸릴 수 있습니다.