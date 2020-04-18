---
title: Microsoft Teams의 알려진 문제
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: troubleshooting
ms.service: msteams
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
ms.reviewer: marcl
audience: admin
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- NOCSH
description: Microsoft Teams 클라이언트 앱 및 관리자 환경에 대해 현재 알려진 문제 목록입니다.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4d6e2a03b7d0ab5b09a71bc7b7a8a944740f223c
ms.sourcegitcommit: c40a7ada120180cd39f18b2e37f23223075abbf4
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2020
ms.locfileid: "43535533"
---
# <a name="known-issues-for-microsoft-teams"></a>Microsoft Teams의 알려진 문제

이 문서에는 Microsoft Teams의 알려진 문제점이 기능 영역별로 나열되어 있습니다.

## <a name="common-issues-and-resolutions"></a>공통적인 문제 및 해결 방법

> [!NOTE]
> COVID-19로 인해 원격 작업자(WFH)를 지원하도록 Teams를 배포하는 데 도움이 필요한 경우 [Microsoft Teams를 사용하여 원격 작업자 지원](support-remote-work-with-teams.md)을 검토하세요. 또한 Microsoft 365 FastTrack 프로그램에서 배포 지원을 받을 수 있습니다. [FastTrack Center](https://www.microsoft.com/fasttrack)를 방문하여 요청을 제출하세요.

### <a name="for-all-teams-customers"></a>모든 Teams 고객에게 해당

| |  |
|---------|---------|
|**Teams를 처음 사용하시나요?**    |[Microsoft Teams 시작](get-started-with-teams-quick-start.md)을 확인하세요.         |
|**Teams 게스트 액세스 사용**     |[Teams 게스트 액세스 검사 목록](guest-access-checklist.md)을 검토하고 모든 단계를 완료합니다. 참조해야 하는 추가 리소스:<ul><li>[Microsoft Teams에서 게스트 액세스 이해](guest-access.md)</li>[게스트가 팀에 참여하는 방법](guest-joins.md) <li>[설정 – Microsoft Teams 게스트 액세스 검사 목록](guest-access-checklist.md)</li></ul>|
|**Teams 모임 및 전화 접속**    |Microsoft Teams에서 오디오 회의를 켜거나 설정하는 데 도움이 필요한가요? 이 사용자가 최근에 생성되었나요? 이 경우 **설정이 적용되기까지** 2~24시간이 걸립니다.<br>사용자에게 오디오 회의를 사용할 수 있는 라이선스가 부여되었는지와 기본 유료 전화 번호가 있는지 확인하려면 다음을 수행합니다.<br><ol><li>Microsoft 365 관리 센터에서 **활성 사용자**로 이동한 다음 문제의 사용자를 선택합니다.</li><li> 관리 센터 버전에 따라, **라이선스 및 앱**을 선택하거나 **제품 라이선스**에서 **편집**을 클릭합니다.</li><li> 사용자에게 오디오 회의, Microsoft Teams 및 비즈니스용 Skype(플랜 2)를 사용할 수 있도록 선택된 라이선스가 있는지 확인합니다.</li><li>**관리 센터**에서 **모두 표시**와 **Teams**를 차례로 클릭합니다.</li><li>Microsoft Teams 관리 센터에서 **레거시 포털**을 클릭합니다.</li><li>비즈니스용 Skype 관리 센터에서 **오디오 회의**를 클릭한 다음, **사용자**를 클릭합니다.</li><li>해당 사용자를 선택하고 사용자에게 기본 유료 전화 번호가 있는지 확인합니다.</li> </ol> 자세한 내용은 [Office 365의 통화 요금제](calling-plans-for-office-365.md)를 참조하거나 라이선스 관련 질문에 대한 도움말을 보려면 Microsoft 상거래 청구 팀에 문의하세요. <br><br>추가 리소스:<ul><li>[Microsoft Teams에서의 모임 및 회의](deploy-meetings-microsoft-teams-landing-page.md)</li><li>[Microsoft Office 365의 오디오 회의](audio-conferencing-in-office-365.md)</li></ul>       |
|**Teams 예비 라이선스**     |Microsoft Teams 예비 환경을 통해 조직에서 AAD (Azure Active Directory)를 사용하고 Teams 라이선스가 없는 사용자는 Teams의 예비 환경을 시작할 수 있습니다. 관리자는 조직의 사용자에 대해 이 기능을 설정 하거나 해제할 수 있습니다. 이전의 [Microsoft 상용 클라우드 평가판](iw-trial-teams.md)은 이제 Teams 예비 환경으로 대체되었습니다. <br><br>추가 리소스:<ul><li>[Teams 예비 환경에 등록하는 방법](teams-exploratory.md#how-users-sign-up-for-the-teams-exploratory-experience)</li><li>[Teams 예비 환경 관리](teams-exploratory.md#manage-the-teams-exploratory-experience)</li></ul>|
|**비공개 채널**    |Microsoft Teams의 비공개 채널은 팀 내 공동 작업을 위한 집중적인 공간을 만들어 줍니다. 비공개 채널의 소유자나 구성원인 팀 사용자만 채널에 액세스할 수 있습니다. 이미 팀 구성원인 경우 게스트를 포함한 모든 사용자가 비공개 채널의 구성원으로 추가될 수 있습니다.<br><br>관리할 추가 팀을 따로 만들 필요 없이 정보를 알아야 하는 사람에게만 공동 작업을 제한하려거나 특정 프로젝트에 할당된 그룹 간의 커뮤니케이션을 용이하게 하려는 경우 비공개 채널을 사용하는 것이 좋습니다.<br><br>추가 리소스:<ul><li>[Teams 예비 환경에 등록하는 방법](teams-exploratory.md#how-users-sign-up-for-the-teams-exploratory-experience)</li><li>[Teams 예비 환경 관리](teams-exploratory.md#manage-the-teams-exploratory-experience)</li><ul>        |
|**모임 정책**|[모임 정책](meeting-policies-in-teams.md)은 조직에서 사용자가 예약한 모임 참가자가 사용할 수 있는 기능을 제어하는 데 사용됩니다. 정책을 만들고 변경한 후에 사용자를 정책에 할당할 수 있습니다.         |
||**모임 정책 변경 또는 만들기**<br><br>모임 정책을 변경하거나 만들려면 Microsoft Teams 관리 센터 > **모임** > **모임 정책**으로 이동합니다. 목록에서 정책을 선택하거나 **추가**를 선택합니다. 새 정책을 만들려면 이름과 설명을 추가합니다. 이름은 특수 문자가 포함될 수 없으며 64자를 초과할 수 없습니다. 설정을 선택한 다음 **저장**을 클릭합니다. 예를 들어, 사용자 수가 많은데 모임에 필요한 대역폭의 양을 제한하려고 한다고 가정해 보겠습니다. "제한된 대역폭"이라는 새 사용자 지정 정책을 만들고 다음 설정을 사용하지 않도록 설정합니다.<br><br>**오디오 및 비디오**에서:<ul><li>클라우드 녹음/녹화 허용을 끕니다.</li><li>IP 비디오 허용을 끕니다.</li></ul>**콘텐츠 공유**에서:<ul><li>화면 공유 모드를 사용하지 않도록 설정합니다.</li><li>화이트보드 허용을 끕니다.</li><li>공유 노트 허용을 끕니다.</li></ul>그 다음 사용자에게 정책을 할당합니다.         |
| |**사용자에게 모임 정책 할당**<br><br><ol><li>Microsoft Teams 관리 센터의 왼쪽 탐색 창에서 **사용자**로 이동한 후 해당 사용자를 클릭합니다.</li><li>사용자 이름의 왼쪽을 클릭하여 사용자를 선택한 후 **설정 편집**을 클릭합니다.</li><li>**모임 정책**에서 할당하려는 정책을 선택한 후 **적용**을 클릭합니다.</li></ol>한 번에 여러 사용자에게 정책을 할당하려면 [Teams 사용자 설정을 일괄 편집](edit-user-settings-in-bulk.md)을 참조하세요. 또는 다음 작업을 수행할 수 있습니다.<ol><li>Microsoft Teams 관리 센터의 왼쪽 탐색 창에서 **모임 > 모임 정책**으로 이동합니다.</li><li>정책 이름의 왼쪽을 클릭하여 정책을 선택합니다.</li><li>**사용자 관리**를 선택합니다.</li><li>**사용자 관리** 창에서 표시 이름 또는 사용자 이름으로 사용자를 검색하고 이름을 선택한 후 **추가**를 클릭합니다. 추가할 각 사용자에 대해 이 단계를 반복합니다.</li><li>사용자 추가를 마쳤으면 **저장**을 클릭합니다.</li>         |
|**다이얼 패드 누락 문제 해결**     |다음을 수행합니다. <ul><li>사용자에게 [Teams 라이선스](assign-teams-licenses.md)가 할당되어 있는지 확인합니다.</li><li>사용자에게 [통화 요금제](calling-plan-landing-page.md)가 할당되었는지 확인합니다.</li><li>사용자가 [Enterprise Voice](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/enable-users-for-enterprise-voice-online-and-phone-system-voicemail#to-enable-your-users-for-phone-system-in-office-365-voice-and-voicemail)를 사용할 수 있도록 설정합니다.</li></ul>      |
|**Teams 로그인 문제 해결**   |먼저 [Microsoft Teams 서비스가 정상인지](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/servicehealth) 확인합니다. 그런 다음, 자주 발생하는 오류 코드를 확인하고 [Microsoft Teams에 로그인하는 데 문제가 있는 이유](https://support.office.com/article/a02f683b-61a3-4008-9447-ee60c5593b0f)를 검토하세요.  [Microsoft Teams의 ID 모델 및 인증](identify-models-authentication.md)을 검토해야 할 수도 있습니다.         |

### <a name="for-education-customers"></a>교육용 고객의 경우

|||
|---------|---------|
|사용자에게 "기회를 놓치고 있습니다" 메시지가 표시됩니다.   |[학교에서 Microsoft Teams를 사용하도록 설정](https://docs.microsoft.com/microsoft-365/education/intune-edu-trial/enable-microsoft-teams)해야 합니다. EDU 테넌트에서 Microsoft Teams는 기본적으로 사용하도록 설정되어 있지 않습니다. 먼저 이 기능을 사용하도록 설정해야 합니다. <br><br>다음으로, [Microsoft Office 365 교육 에디션에서 원격 교육 및 학습](https://support.office.com/article/remote-teaching-and-learning-in-office-365-education-f651ccae-7b65-478b-8366-51bb884025c4)을 참조하여 학교 설정, 수업 계획, 가상 모임 및 학생들과 콘텐츠 공유에 대한 최신 지침을 알아보세요.<br><br>마지막으로 [Teams 관리자 교육](itadmin-readiness.md)에서 Microsoft Teams IT 관리자 교육 비디오, 데크, 그리고 그 밖의 다양한 콘텐츠를 확인하세요.        |

Microsoft Teams로 문제를 해결하는 방법에 대 한 자세한 내용은 [Teams 문제 해결](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)을 참조하세요.
