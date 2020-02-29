---
title: Microsoft Teams를 사용하여 원격 작업자 지원
author: LolaJacobsen
ms.author: lolaj
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
ms.reviewer: dansteve
localization_priority: Priority
search.appverid: MET150
description: >
  조직의 원격 작업자가 특히 COVID-19(코로나 바이러스) 발생에 대응하여 재택 근무(WFH)를 하는 경우 이 가이드를 읽고 Microsoft Teams를 사용하여 생산성을 높일 수 있습니다.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4fbdb875896ca07402d699f1ca2a28770cb46ee2
ms.sourcegitcommit: ae65fb089d98665c4b26e0345bb96241fb893f0b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/29/2020
ms.locfileid: "42342905"
---
# <a name="support-remote-workers-using-microsoft-teams"></a>Microsoft Teams를 사용하여 원격 작업자 지원

이 문서의 모범 사례를 사용하여 원격으로 또는 집에서 일하는 사용자를 지원하세요.

## <a name="technical"></a>기술 관련

1.  [모든 사용자에 대해 Teams가 설정](assign-teams-licenses.md)되어 있는지 확인하세요.
    
      - [Teams Exploratory](teams-exploratory.md) 또는 [Teams 무료](https://support.office.com/article/Welcome-to-Microsoft-Teams-free-6d79a648-6913-4696-9237-ed13de64ae3c)를 살펴보고 회사의 모든 사람이 Teams를 사용할 수 있도록 하세요.

      - 원격 직원은 모임 및 오디오 회의에 더 의존합니다. 아직 이 작업을 롤아웃하지 않은 경우 [Teams에서 모임 및 회의](deploy-meetings-microsoft-teams-landing-page.md)를 확인하세요.

2.  사용자에게 Teams에 대해 알립니다. [Teams 고객 성공 키트](https://download.microsoft.com/download/A/E/9/AE984CD4-CF4B-41E7-9ABD-6735E3F01897/MicrosoftTeamsCustomerSuccessKit.zip)를 다운로드하여 프레젠테이션, 샘플 전자 메일, 포스터, 시작 가이드를 얻어 보세요.


5.  직원들이 Teams에 적합한 인터넷 액세스와 대역폭을 보유하고 있는지 확인합니다. [Teams에 대한 조직의 네트워크 준비](prepare-network.md)의 지침을 사용하여 이 작업을 수행하는 방법을 알아보세요.
    - 제한된 대역폭은 Teams 모임의 오디오 품질에 영향을 미칠 수 있습니다. 저대역폭 조건을 사용하여 최고의 모임을 경험하기 위해 사용자에 게 비디오를 제한하고 통화 및 모임 오디오에 PSTN을 사용하도록 장려합니다. 

    - 통화 또는 모임 품질 문제를 해결하는 데 도움이 필요한 경우에는 이 문서의 맨 아래에 있는 [알려진 문제: 비즈니스용 Skype/Teams 회의에 전화 걸기](#known-issue-dialing-into-skype-for-business-or-teams-conference-ids)에 관한 지침을 따르세요.

2.  직원들이 Teams를 최대한 활용할 수 있도록 [교육 링크를 보내세요](enduser-training.md).
    
3. 원격 작업에 대한 새로운 내용을 읽고 사용자와 공유하세요.
        
      - Teams 블로그 (2020년 2월 28일): [Microsoft Teams로 집에서 작업하는 4 개의 팁](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/4-tips-for-working-from-home-with-microsoft-teams-by-lola/ba-p/1202083)

      - [Office 365로 공동 작업](https://support.office.com/article/Collaborate-with-Office-365-ac05a41e-0b49-4420-9ebc-190ee4e744f4)

      - [Teams과 Office 365로 원격 작업](https://support.microsoft.com/help/4549995/working-remotely-with-teams-and-office-365)

3.  모든 사람이 모바일 앱을 [설치](get-clients.md#mobile-clients)하고 사용하도록 장려: [iOS](https://go.microsoft.com/fwlink/?LinkId=835758)   [Android](https://go.microsoft.com/fwlink/p/?linkid=2102168)

    > [!NOTE]
    > 중국에 있는 경우, 여기에 있는 [중국에서 Android용 Teams 받기](get-teams-android-in-china.md)로 이동하세요.

4.  사용자 문의를 처리하기 위해 [헬프데스크](troubleshoot-installation.md) 직원을 고용하세요.


## <a name="communications"></a>커뮤니케이션

Teams를 사용하여 직원들과 지속적으로 소통하세요.
- [조직 전체 팀](create-an-org-wide-team.md) 및 [회사 커뮤니케이터](https://docs.microsoft.com/microsoftteams/platform/samples/app-templates#company-communicator) 앱 서식 파일
    
- 조직의 재택 근무 및 건강 및 안전 정책에 대한 정보를 보내세요.
    
- 회사 전체의 모임 및 지원 활동에 [라이브 이벤트](teams-live-events/what-are-teams-live-events.md)를 사용하세요. 250명 이상의 참석자가 있는 모든 모임을 라이브 이벤트로 만듭니다. 

## <a name="personal-considerations"></a>개인적 고려 사항

다음은 집에서 효과적으로 작업하기 위한 몇 가지 팁입니다.

- 좋은 조명과 적절히 인체 공학적으로 구성된 물리적 작업 공간을 확보하세요.

- 근무 시간과 작업에 명확한 경계를 설정하고, 자리에 없는 경우 Teams의 [현재 상태](https://support.office.com/article/change-your-status-in-teams-ce36ed14-6bc9-4775-a33e-6629ba4ff78e)를 사용하여 이를 표시하세요.

- 의도적으로 재택 근무 사무실로 “출퇴근”하세요. 재택 근무(work-from-home)를 집에서도 근무(home-equals-work)로 오해하지 마세요.

- 수시로 일어나 휴식을 취하세요. 걷거나 스트레칭하고 차를 한 잔 마시세요.

## <a name="known-issue-dialing-into-skype-for-business-or-teams-conference-ids"></a>알려진 문제: 비즈니스용 Skype 또는 Teams 회의 ID에 전화 걸기

다음은 2020년 2월 7일 메시지 센터 게시물(MC203397)에 대한 요약입니다.

Microsoft는 중국 지역의 일부 사용자가 비즈니스용 Skype 또는 Teams 회의 ID로 전화를 거는 데 문제가 있음을 알고 있습니다. 대부분의 경우 이러한 문제는 당사가 제어하는 시스템의 외부에 있습니다. 종종 로컬 모바일 및 전화 통신 사업자에 문제가 있습니다. 

오디오 회의를 하는 데 문제가 있는 경우 다음을 수행하는 것이 좋습니다.

- 호출자 또는 모임 이끌이에게 PSTN 또는 휴대폰 번호로 전화하도록 요청합니다.
- VoIP를 사용하여 데스크톱 또는 모바일 클라이언트에서 통화 또는 모임에 참가합니다.

지원 티켓을 기록해야 하는 경우 다음을 포함하세요.
    
- 정확한 통화 시간
- 전화를 건 전화 회의 브리지 번호
- 호출자 전화 네트워크
- 호출자 전화 번호
