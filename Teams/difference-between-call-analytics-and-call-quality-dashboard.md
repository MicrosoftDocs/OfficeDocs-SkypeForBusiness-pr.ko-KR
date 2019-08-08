---
title: 통화 분석 및 통화 품질 대시보드
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.reviewer: mikedav, wlooney, gageames
ms.topic: conceptual
ms.assetid: 4cd5fe35-8463-4996-a252-086cd3ca2d9a
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
search.appverid: MET150
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Reporting
description: 통화 분석 및 통화 품질 대시보드 및이를 사용 하 여 통화 품질 문제를 모니터링 하 고 해결 하는 시기에 대해 알아봅니다.
ms.openlocfilehash: 1130e901ca8c7103c9dd73990c4c0af47898203d
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36237520"
---
# <a name="call-analytics-and-call-quality-dashboard"></a>통화 분석 및 통화 품질 대시보드

Microsoft 팀과 비즈니스용 Skype는 통화 품질 문제를 모니터링 하 고 문제를 해결 하는 두 가지 방법, 즉, Call Analytics 및 통화 품질 대시보드 (CQD)를 제공 합니다. 이 문서에서는 이러한 두 가지 방법에 대해 설명 하 고 각 항목을 사용 하는 방법을 알려줍니다.

통화 분석 및 CQD는 병렬로 실행 되며 독립적으로 또는 함께 사용할 수 있습니다. 예를 들어 통신 지원 전문가에 게 전화 문제 해결에 대 한 추가 도움이 필요 하다 고 판단 합니다. 커뮤니케이션 지원 전문가는 커뮤니케이션 지원 엔지니어에 게 통화를 전달 하 고,이는 통화 분석에서 통신 지원 전문가 보다 더 많은 정보에 액세스할 수 있습니다. 통신 지원 엔지니어가 네트워크 엔지니어에 게 문제를 알릴 수 있습니다. 네트워크 엔지니어가 전체 사이트 관련 문제가 통화 문제의 원인이 될 수 있는지를 확인 하기 위해 CQD를 확인할 수 있습니다.

## <a name="whats-call-analytics-and-when-should-i-use-it"></a>통화 분석의 정의 및 사용 해야 하는 경우

**이제 [Microsoft 팀 관리 센터](https://admin.teams.microsoft.com)에서 통화 분석을 사용할 수 있습니다.** 사용자의 통화 정보와 데이터를 모두 보려면 **통화 기록** 탭을 사용 합니다. 이 작업은 대시보드에서 사용자를 검색 하거나 왼쪽 탐색의 **사용자** 에서 사용자를 찾는 방법으로 사용자의 프로필 페이지를 볼 수 있습니다.

통화 분석에서는 Microsoft 팀 또는 비즈니스용 Skype 계정의 각 사용자에 대 한 특정 통화 및 모임과 관련 된 장치, 네트워크 및 연결에 대 한 자세한 정보를 보여 줍니다. 이 사용자에 게이 오후의 통화가 좋지 않은 이유는 무엇 인가요? 전화 분석을 사용 하 여 Office 365 관리자 또는 교육 된 헬프 데스크 상담원은 Microsoft 팀과 비즈니스용 Skype의 통화 품질 및 연결 문제를 해결 하기 위해 해당 통화와 관련 된 장치, 네트워크, 연결, 기타 요소를 조사할 수 있습니다.

Microsoft 팀 관리 센터에서 사용자에 대 한이 정보를 보려면 사용자 세부 정보 페이지에서 해당 사용자의 **통화 기록** 탭을 클릭 하 여 사용자가 지난 30 일 동안 참가 한 모든 통화와 모임을 표시 합니다.

![모든 분석 사용자 데이터의 스크린샷](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image1.png)

자세한 미디어 및 네트워킹 통계를 포함 하 여 특정 세션에 대 한 추가 정보를 얻으려면 세션을 클릭 하 여 세부 정보를 확인 합니다.

![통화 분석 사용자 세션 데이터의 스크린샷](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image2.png)

외부 공급 업체의 헬프 데스크 에이전트와 같이 관리자가 아닌 사용자가 통화 분석을 사용 하도록 하려면 사용 권한을 할당 하 여 통화 분석을 사용할 수 있지만 나머지 Microsoft 팀 관리 센터에 액세스할 수는 없습니다. 
  
- **통신 지원이 포함 된 헬프데스크 에이전트 전문가 권한**: 상담원은 통화 분석에서 제한 된 데이터 집합과 PII (개인 식별 가능 정보)를 볼 수 있습니다. 통화 문제를 해결할 수 있지만, 커뮤니케이션 지원 엔지니어에 대 한 모임 문제는 발생 하지 않습니다.
    
- **통신 지원 엔지니어가 사용 권한이 있는 헬프데스크 에이전트**: 상담원은 콜 분석에서 사용 가능한 모든 데이터를 확인 하 고 통화와 회의 모두의 문제를 해결 합니다. 콜 로그와 고객 정보에 대 한 모든 권한이 있습니다.

> [!NOTE]
> 통신 지원 전문가 역할은 미리 보기 포털의 계층 1 지원 역할과 같으며 통신 지원 엔지니어 역할은 미리 보기 포털의 계층 2 지원 역할에 해당 합니다.

통신 지원 전문가 및 통신 지원 엔지니어 역할에 대 한 자세한 내용은 [Microsoft 팀 관리자 역할을 사용 하 여 팀 관리를](using-admin-roles.md)참조 하세요.

> [!IMPORTANT]
> Microsoft 팀 관리 센터에서 지원 되는 헬프데스크 에이전트 권한 및 네트워크 토폴로지 업로드를 사용할 수 있습니다. 통신 지원 전문가 및 통신 지원 엔지니어가이 포털을 사용 하 여 통화 분석 및 통화 품질 대시보드에 액세스할 수 있습니다.
    
통화 분석을 설정 하는 방법에 대 한 자세한 내용은 비즈니스용 [Skype 통화 분석 설정](set-up-call-analytics.md)을 참조 하세요. 헬프데스크 에이전트가 통화 분석을 사용 하는 방법에 대 한 자세한 내용은 통화 [분석을 사용 하 여 통화 품질 저하 문제 해결](use-call-analytics-to-troubleshoot-poor-call-quality.md)을 참조 하세요.
  
## <a name="whats-the-call-quality-dashboard-and-when-should-i-use-it"></a>통화 품질 대시보드의 정의 및 사용 해야 하는 경우
  
통화 분석은 관리자와 헬프 데스크의 상담원에 게 특정 전화의 통화 음질 문제를 해결 하는 데 도움이 되도록 설계 된 반면, 통화 품질 대시보드 (CQD)는 팀 관리자, 비즈니스용 Skype 관리자, 네트워크 엔지니어가 네트워크를 최적화 하는 데 도움이 되도록 설계 되었습니다. CQD는 특정 사용자 로부터 포커스를 이동 하 고 대신 전체 팀 또는 비즈니스용 Skype 조 직에 대 한 집계 정보를 봅니다. 자세한 내용은 [팀과 비즈니스용 Skype Online에 대 한 통화 품질 대시보드의 기능](turning-on-and-using-call-quality-dashboard.md#BKMKFeaturesOfTheCQD)을 참조 하세요.
  
사용자의 잘못 된 통화 품질이 다른 많은 사용자에 게 영향을 주는 네트워크 문제로 인 한 것일 수 있습니다. 개인 통화 환경은 CQD에서 볼 수 없지만 Microsoft 팀 또는 비즈니스용 Skype를 사용 하 여 생성 된 전체 통화 품질은 캡처됩니다. CQD를 사용 하는 경우, 네트워크 엔지니어가 통화 음질에 대 한 평가를 할 수 있도록 전체 패턴이 명백 하 게 될 것입니다. CQD는 전체 통화 품질, 서버 클라이언트 스트림, 클라이언트-클라이언트 스트림, 음성 품질 [SLA](https://go.microsoft.com/fwlink/p/?linkid=846252)에 대 한 정보를 제공 하는 통화 품질 메트릭의 보고서를 제공 합니다.
  
![통화 품질 대시보드의 스크린샷](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image3.png)

CQD의 위치 향상 보고서의 도움을 통해 사용자의 건물에 있는 집계 통화 품질 및 안정성을 평가 하 여 문제가 단일 사용자에 게 격리 되었는지 또는 대규모 사용자 세그먼트에 영향을 미치는지 확인할 수 있습니다.

![통화 품질 대시보드의 위치 향상 보고서 스크린샷.](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image4.png)

> [!NOTE]
> CQD에서 빌드 또는 끝점 관련 보기를 사용 하도록 설정 하려면 관리자가 CQD의 테 넌 트 데이터 업로드 페이지에서 [빌드 또는 끝점 정보를 업로드](turning-on-and-using-call-quality-dashboard.md#upload-tenant-data-information) 해야 합니다. 

헬프데스크 등의 관리자가 아닌 사용자가 통화 품질 대시보드를 사용 하도록 하려면 **팀 통신 지원 엔지니어**, **팀 의사 소통 지원 전문가**또는 **보고서 독자** 역할을 할당할 수 있습니다. 다음 역할의 사용자는 통화 품질 대시보드에 액세스할 수 있습니다.

- 전역 관리자
- 전역 읽기 프로그램
- 비즈니스용 Skype 관리자
- 팀 서비스 관리자
- 팀 의사 소통 관리자
- 팀 의사 소통 지원 엔지니어
- 팀 의사 소통 지원 전문가
- 보고서 읽기 프로그램

> [!NOTE]
> 팀 의사 소통 지원 엔지니어, 팀 의사 소통 지원 전문가, 보고서 리더 역할은 CQD의 테 넌 트 데이터 업로드 페이지에서 파일을 수정 하거나 테 넌 트에 대해 CQD를 활성화할 수 없습니다.

이러한 역할에 대 한 자세한 내용은 [Office 365 관리자 역할](/office365/admin/add-users/about-admin-roles)정보를 참조 하세요.

CQD에 대 한 자세한 내용은 microsoft 팀과 비즈니스용 Skype Online 및 [microsoft 비즈니스용 Skype online 용 통화 품질 대시보드에서 제공 되는 크기 및 측정값](dimensions-and-measures-available-in-call-quality-dashboard.md)에 [대 한 통화 품질 대시보드 켜기 및 사용](turning-on-and-using-call-quality-dashboard.md) 을 참조 하세요.
  
## <a name="related-topics"></a>관련 항목

[비디오: 통화 품질 개요](https://aka.ms/teams-quality)

[통화 분석 설정](set-up-call-analytics.md)

[통화 분석을 사용 하 여 통화 품질 저하 문제 해결](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[Microsoft 팀 및 비즈니스용 Skype Online에 대 한 통화 품질 대시보드 켜기 및 사용](turning-on-and-using-call-quality-dashboard.md)
