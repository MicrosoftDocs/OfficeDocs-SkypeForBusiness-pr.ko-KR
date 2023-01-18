---
title: Microsoft Teams 분석 및 보고
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: conceptual
ms.service: msteams
ms.reviewer: svemu
f1.keywords:
- NOCSH
- ms.teamsadmincenter.analyticsandreports.overview
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
- m365initiative-meetings
description: 이 문서에서는 Microsoft Teams 관리 센터에서 사용할 수 있는 Teams 보고서에 대해 알아봅니다.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: e93a34f19ecf53e05a51fe36983a9f46f741e67e
ms.sourcegitcommit: 40cba40b1babdb3fbfc1a416b7eeb0118f8353df
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/18/2023
ms.locfileid: "69820323"
---
# <a name="microsoft-teams-analytics-and-reporting"></a>Microsoft Teams 분석 및 보고

Microsoft Teams에 대한 새로운 분석 및 보고 환경은 Microsoft Teams 관리 센터에서 사용할 수 있습니다. 다양한 보고서를 실행하여 조직의 사용자가 Teams를 사용하는 방법에 대한 인사이트를 얻을 수 있습니다. 예를 들어 채널 및 채팅 메시지를 통해 통신하는 사용자 수와 Teams에 연결하는 데 사용하는 디바이스 종류를 확인할 수 있습니다. 조직은 보고서의 정보를 사용하여 사용 패턴을 더 잘 이해하고, 비즈니스 의사 결정을 내리고, 교육 및 커뮤니케이션 활동을 알릴 수 있습니다.

## <a name="how-to-access-the-reports"></a>보고서에 액세스하는 방법

보고서에 액세스하려면 다음 역할 중 하나를 할당받아야 합니다.

- 전역 관리자.
- Teams 또는 비즈니스용 Skype 관리자.
- 전역 판독기(테넌트 수준 집계만, 사용자 또는 팀 데이터 없음)

Teams 관리자 역할 및 각 관리자 역할이 액세스할 수 있는 보고서에 대한 자세한 내용은 [Teams 관리자 역할을 사용하여 Teams 관리를](../using-admin-roles.md) 참조하세요.

Microsoft Teams 관리 센터로 이동하여 왼쪽 탐색 영역에서 **분석 & 보고서를** 선택한 다음 **보고서 보기** 에서 실행할 보고서를 선택합니다.

> [!NOTE]
> Microsoft Teams 관리 센터의 보고서는 Microsoft 365 관리 센터 Microsoft 365 보고서의 일부인 Teams의 활동 보고서와는 별개입니다. Microsoft 365 관리 센터 활동 보고서에 대한 자세한 내용은 [관리 센터의 Microsoft 365 보고서를 참조하세요](/microsoft-365/admin/activity-reports/activity-reports).

## <a name="teams-reporting-reference"></a>Teams 보고 참조

다음은 다양한 환경의 Microsoft Teams 관리 센터에서 사용할 수 있는 Teams 보고서 목록과 각 보고서에서 사용할 수 있는 일부 정보의 개요입니다.

Teams 보고 환경을 지속적으로 개선하고 기능과 기능을 추가하고 있습니다. 시간이 지남에 따라 보고서에 추가 기능을 빌드하고 Microsoft Teams 관리 센터에서 새 보고서를 추가할 예정입니다.

|보고서  |공용 |Gcc |GCCH |국방부 |측정된 항목은 무엇인가요? |
|---------|---------|---------|---------|---------|---------|
|[Teams 사용 현황 보고서](teams-usage-report.md)  |예|예|예|예|  활성 사용자<br/>팀 및 채널의 활성 사용자<br/>활성 채널<br/>메시지<br/>팀의 개인 정보 설정<br/>팀의 활성 게스트  <br/>활성 외부 사용자(공유 채널)<br/>팀 내의 공유 채널별 세부 정보(신규)|
|[Teams 사용자 작업 보고서](user-activity-report.md)  |예|예|예|예|활성 내부 및 외부(공유 채널에서) 사용자<br/> 사용자가 팀 채팅에 게시한 메시지<br/>사용자가 비공개 채팅에 게시한 메시지<br/>  1:1 사용자가 참가한 호출<br/> 사용자가 구성한 모임 수 <br/>사용자가 참가한 모임 수<br/>모임 오디오, 비디오 및 화면 공유 시간<br/>   사용자의 마지막 활동 날짜  <br>사용자의 공유 채널 상호 작용(신규)</br>   |
|[Teams 장치 사용 현황 보고서](device-usage-report.md)   |예|예|예|예|  Windows 사용자<br/>Mac 사용자<br/>iOS 사용자<br/>Android 휴대폰 사용자     |
|[Teams 앱 사용 현황 보고서(신규)](app-usage-report.md)   |예|예|아니요|아니요|  앱의 총 활성 사용자 수<br/>앱을 사용하는 총 활성 팀<br/>설치된 총 앱(신규)<br/>총 비활성 앱 <br/>총 1P 및 3P 및 LoB 앱 사용량(신규)     |
|[Teams 라이브 이벤트 사용 현황 보고서](teams-live-event-usage-report.md)   |예|예|아니요|아니요|  총 뷰 수<br>시작 시간<br>이벤트 상태<br>이끌이<br>발표자<br>프로듀서<br>녹음/녹화 설정<br>프로덕션 유형    |
|[Teams PSTN 차단 사용자 보고서](pstn-blocked-users-report.md)   |예|예|아니요|아니요|  표시 이름<br>전화 번호<br>이유<br>작업 유형<br>작업 날짜 및 시간   |
|[Teams PSTN 분 풀 보고서](pstn-minute-pools-report.md) |예|예|아니요|아니요|  국가 또는 지역<br>기능(라이선스) <br>총 시간(분)<br>사용된 시간(분)<br>사용 가능한 시간(분)|
|[Teams PSTN 사용 현황 보고서 - 통화 플랜](pstn-usage-report.md#calling-plans)|예|예|아니요|아니요|  타임스탬프는<br>사용자 이름<br>전화 번호<br>호출 유형 <br>다음으로 호출<br>국가 또는 지역으로 <br>에서 호출 <br>국가 또는 지역에서<br>충전<br>통화<br>기간<br>국내/국제<br>통화 ID<br>숫자 유형<br>국가 또는 지역<br>회의 ID<br>기능(라이선스)|
|[Teams PSTN 사용 현황 보고서 - 직접 라우팅](pstn-usage-report.md#direct-routing)  |예|예|아니요|아니요|  타임스탬프는<br>표시 이름<br>SIP 주소<br>전화 번호 <br>호출 유형<br>다음으로 호출<br>시작 시간<br>초대 시간<br>실패 시간<br>종료 시간<br>기간<br>숫자 유형<br>미디어 바이패스<br>SBC FQDN<br>Azure 지역<br>이벤트 유형<br>최종 SIP 코드<br>최종 Microsoft 하위 코드<br>최종 SIP 구<br>상관 관계 ID  |
|[Teams 정보 보호 라이선스 보고서](information-protection-license-report.md)  |예|예|아니요|아니요| <br>사용자에게 변경 알림을 통해 메시지를 푸시할 수 있는 유효한 라이선스가 있는지 여부</br><br>사용자가 트리거한 총 변경 알림 이벤트 수<br><br>조직 전체 변경 알림 이벤트를 수신 대기하는 앱<br>|
|[Teams 가상 약속 사용 현황 보고서](/microsoft-365/frontline/virtual-appointments-usage-report?bc=%2fmicrosoftteams%2fbreadcrumb%2ftoc.json&toc=%2fmicrosoftteams%2ftoc.json)|예|예|아니요|아니요| 가상 약속 수<br>예약 예약 수<br>Teams EHR(전자 건강 기록) 통합 약속 수<br>약속의 평균 기간<br>참석자의 평균 로비 대기 시간<br>시작 시간<br>모임 ID<br>로비 대기 시간<br>기간<br>상태<br>제품 유형<br>참석자<br>부서<br>SMS 전송<br>약속이 고급 가상 약속 기능을 사용했는지 여부|
|[Teams 고급 가상 약속 활동 보고서](/microsoft-365/frontline/advanced-virtual-appointments-activity-report?bc=%2fmicrosoftteams%2fbreadcrumb%2ftoc.json&toc=%2fmicrosoftteams%2ftoc.json) |예|예|아니요|아니요|고급 가상 약속 기능을 사용하는 사용자 수<br>SMS 텍스트 알림을 사용하는 사용자 수<br>로비 채팅을 사용하는 사용자 수(출시 예정)<br>주문형 약속을 수행하는 사용자 수|
|[Teams EHR 커넥터 가상 약속 보고서](/microsoft-365/frontline/ehr-connector-report?bc=%2fmicrosoftteams%2fbreadcrumb%2ftoc.json&toc=%2fmicrosoftteams%2ftoc.json) |예|예|아니요|아니요| 시작 시간<br>기간<br>기본(모임 이끌이의 이름)<br>기본 이메일(모임 이끌이의 이메일)<br>부서<br>전화 교환<br>로비 대기 시간<br>약속이 할당 한도 내에 있는지 여부|
[!INCLUDE [teams-reports-definitions](../includes/teams-reports-definitions.md)]

## <a name="make-the-user-specific-data-anonymous"></a>사용자 특정 데이터를 익명으로 만들기

사용 보고서에서 식별 가능한 정보를 익명으로 만들려면 전역 관리자 합니다. 전역 관리자 보고서 및 내보내기에서 표시 이름, 그룹 이름, 전자 메일 및 AAD ID와 같은 식별 가능한 정보(MD5 해시 사용)를 숨길 수 있습니다.

1. Microsoft 365 관리 센터 **설정** \> **조직 설정** 으로 이동하고 **서비스** 탭에서 **보고서를** 선택합니다.
    
2. **보고서를** 선택한 다음 **, 모든 보고서에서 은폐된 사용자, 그룹 및 사이트 이름을 표시** 하도록 선택합니다. 이 설정은 Microsoft 365 관리 센터 사용 현황 보고서와 Teams 관리 센터에 모두 적용됩니다.
  
3. **변경 내용 저장** 을 선택합니다.

> [!NOTE]
> 이 설정을 사용하도록 설정하면 Teams 사용자 활동 보고서, Teams [디바이스 사용](device-usage-report.md) [현황 보고서 및 Teams 사용 보고서에서 사용자](user-activity-report.md), 그룹 및 사이트 이름 정보를 식별할 수 [없습니다](teams-usage-report.md). 2021년 9월 1일부터 이 설정은 중요한 정보를 보호하고 회사가 현지 개인 정보 보호법을 지원할 수 있도록 지속적인 노력의 일환으로 모든 사용자가 기본적으로 사용하도록 설정됩니다. 
>
>이 설정은 Microsoft 365 관리 센터, Microsoft Graph 및 Power BI의 Microsoft 365 사용 보고서에도 적용됩니다.
