---
title: 팀에 대 한 배정
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
search.appverid: MET150
ms.reviewer: jastark
f1keywords:
- ms.teamsadmincenter.assignments.overview
- ms.teamsadmincenter.assignments.tooltip.emaildigest
- ms.teamsadmincenter.assignments.tooltip.makecode
- ms.teamsadmincenter.assignments.tooltip.turnitin
description: 교육 팀의 Microsoft 팀 관리 센터에서 과제를 관리 하는 방법에 대해 알아봅니다.
localization_priority: Normal
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0eaaa4782ac1c0f5fa8d1618f89c05d3ffd58e57
ms.sourcegitcommit: d4e69d46de564c445feb855cbee55954a7063bba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/21/2019
ms.locfileid: "36483982"
---
# <a name="assignments-in-teams-for-education"></a>교육용 팀의 과제

과제는 수업에서 학생 또는 팀 구성원에 게 배정 된 작업 또는 작업 단위를 연구의 일부로 하는 것입니다. 팀 클래스 내에서 과제를 만들 수 있습니다.

[과제에 대 한 자세한 정보](https://support.office.com/article/microsoft-teams-5aa4431a-8a3c-4aa5-87a6-b6401abea114?ui=en-US&rs=en-IE&ad=IE#ID0EAABAAA=Assignments)

## <a name="assignments-in-the-microsoft-teams-admin-center"></a>Microsoft 팀 관리 센터의 과제

Microsoft 팀 관리 센터의 관리 설정에서 다음 기능을 설정 하거나 해제 하 여 조직 내 학생 및 교사에 게 사용할 수 있습니다. 과제와 관련 된 설정은 다음과 같습니다.

<a name="#bkemaildigest"> </a>
### <a name="weekly-guardian-email-digest"></a>주간 보호자 이메일 요약
[!INCLUDE [preview-feature](../includes/preview-feature.md)]

보호자 이메일은 학생의 부모나 보호자에 게 전송 되는 주간 전자 메일입니다. 전자 메일에는 이전 주의 과제 및 다음 주에 대 한 정보가 포함 되며 주말에 발송 됩니다. 전자 메일은 학교 데이터 동기화 기능을 사용 하 여 관리자가 업데이트 해야 합니다.

이 설정은 기본적으로 해제 되어 있습니다.

<a name="bkmakecode"> </a>
### <a name="makecode"></a>MakeCode
MakeCode는 모든 학생에 게 컴퓨터 과학을 수명으로 제공 하는 블록 기반 코딩 플랫폼입니다. 

귀하의 약관 및 개인정보 보호 정책에 적용 되는 타사 제품이 나 서비스입니다. 귀하는 타사 제품 및 서비스를 사용 해야 합니다.

이 설정은 기본적으로 해제 되어 있습니다.

[MakeCode에 대 한 자세한 정보](https://www.microsoft.com/makecode)

<a name="#turnitin"> </a>
### <a name="turnitin"></a>Turnitin
[!INCLUDE [preview-feature](../includes/preview-feature.md)]

Turnitin는 plagiarism 검색 서비스입니다. 귀하의 약관 및 개인정보 보호 정책에 적용 되는 타사 제품이 나 서비스입니다. 귀하는 타사 제품 및 서비스를 사용 해야 합니다.

이 설정은 기본적으로 해제 되어 있습니다.

조직에 대 한 Turnitin을 사용 하도록 설정 하려면 이미 Turnitin 구독이 있어야 합니다. Turnitin 관리 콘솔에서 찾을 수 있는 다음과 같은 추가 정보를 입력 해야 합니다.

  * _TurnitinApiKey_: 관리자 콘솔의 통합에서 찾은 32 문자 GUID입니다.
  * _TurnitinApiUrl_: Turnitin 관리 콘솔의 HTTPS URL입니다.

이 정보를 구하는 데 도움이 되는 몇 가지 지침입니다.

TurnitinApiUrl는 관리 콘솔의 호스트 주소입니다.
예. `https://your-tenant-name.turnitin.com`

관리 콘솔에서 통합과 통합에 연결 된 API 키를 만들 수 있습니다.

측면 **** 메뉴에서 통합을 선택한 다음 **통합 추가** 를 선택 하 고 통합에 이름을 지정 합니다.
![새 통합 추가를 보여주는 스크린샷](./educationImages/Assignments_mopo_turnitin2.png)

메시지를 팔 로우 하는 경우 TurnitinApiKey이 사용자에 게 제공 됩니다. API 키를 복사 하 여 Microsoft 팀 관리 센터에 붙여넣습니다.  이 시점 에서만 키를 볼 수 있습니다.
![API 키 복사를 보여 주는 스크린샷](./educationImages/Assignments_mopo_turnitin3.png)

이 설정에 대 한 관리 센터에서 **저장** 단추를 클릭 하면 이러한 설정을 적용 하는 데 최대 24 시간이 소요 될 수 있습니다.

[Turnitin 및 Microsoft 팀 간 통합에 대해 자세히 알아보기](https://www.turnitin.com/products/feedback-studio/microsoft-teams-integration)

[Turnitin에 대 한 자세한 정보](https://www.turnitin.com/)
