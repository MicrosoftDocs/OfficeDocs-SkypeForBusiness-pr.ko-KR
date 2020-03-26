---
title: CQD 데이터를 사용 하 여 Power BI에서 Microsoft 팀 사용률 보기
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.reviewer: siunies
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
- Teams_ITAdmin_RemoteWorkers
search.appverid: MET150
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
description: 팀 활용 Power BI 보고서를 사용 하 여 조직의 Microsoft 팀 사용량을 추적 합니다.
ms.openlocfilehash: efca39a89eecdf9d603a81a07d8529147f87698a
ms.sourcegitcommit: 4d376449a75928282373598647f2b82127909c4f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/26/2020
ms.locfileid: "42978557"
---
# <a name="view-microsoft-teams-utilization-in-power-bi-using-cqd-data"></a>CQD 데이터를 사용 하 여 Power BI에서 Microsoft 팀 사용률 보기

2020 년 3 월에 새로 추가 된, [CQD 용으로 다운로드할 수 있는 POWER BI 쿼리 서식 파일](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true)에 팀 사용률 보고서가 추가 되었습니다. 

이 새로운 팀 사용률 보고서를 사용 하 여 사용자가 Microsoft 팀을 사용 하는 방법과 그 정도를 확인할 수 있습니다. 이러한 보고서는 관리자와 비즈니스 리더가 모두이 데이터로 빠르게 이동할 수 있는 중앙 집중화 된 위치를 대상으로 합니다.

팀 활용 Power BI 보고서는 두 가지 기본 보고서 ( **[통화 수 요약](#call-count-summary-report)** 및 **[오디오 시간 요약)](#audio-minutes-summary-report)** 로 구성 됩니다. 사용자가 아래 설명에 명시 된 드릴 다운 보고서를 이용 하는 경우 [일별 사용량](#daily-usage), [지역 오디오 세부 정보](#regional-audio-details), [회의 정보](#conference-details) 및 [사용자 목록](#user-list) 보고서가 재생에 제공 됩니다.

> [!NOTE]
> 지역 및 네트워크 필터링 기능을 제공 하려면 빌드 및 서브넷 데이터를 채워야 합니다.

## <a name="call-count-summary-report"></a>통화 수 요약 보고서

기본 페이지 (통화 수 요약)는 섹션 제목에 명시 된 대로 지난 30 일과 90 일 동안 오디오, 비디오 및 화면 공유 세션의 수를 즉시 제공 합니다. 처음에는 조직에 대 한 데이터가 전체적으로 표시 되며 페이지의 왼쪽에 있는 슬라이서 드롭다운 옵션을 사용 하 여 필터링 할 수 있습니다.

![스크린샷: 팀 이용률 보고서](media/CQD-teams-utilization-report1.png)

1. 슬라이서 드롭다운의 오른쪽에 미디어 유형별 통화 수가 지난 30 일 동안 내부/외부 보기로 분류 됩니다. 현재 전역 환경을 고려 하 여 외부 조직 위치에서 발생 하는 더 많은 호출을 볼 수 있습니다.
  ![스크린샷: 팀 이용률 보고서](media/CQD-teams-utilization-report2.png)

1. 미디어 유형 개수 상자 오른쪽에는 지난 90 일간의 미디어 유형별로 월간 통화 수가 있습니다. 각 열과 미디어 유형을 마우스로 가리키면 사용 추세 정보를 제공 하 여 이전 월 또는 현재 달의 수를 표시할 수 있습니다.
  ![스크린샷: 팀 이용률 보고서](media/CQD-teams-utilization-report3.png)
 

1. 90 일 그래프에서는 가운데 그래프가 작동 하지만 지난 30 일간의 일일 사용량 보기를 제공 하 고 사용자가 특정 날짜에 대 한 세부 정보를 마우스 오른쪽 단추로 클릭 하 고 드릴 다운할 수 있습니다.
  ![스크린샷: 팀 이용률 보고서](media/CQD-teams-utilization-report4.png)

페이지의 왼쪽 아래 섹션에서 지난 해의 각 미디어 유형에 대 한 총 값을 제공 하는 테이블을 찾을 수 있습니다. 
    ![스크린샷: 팀 사용률 보고서](media/CQD-teams-utilization-report5.png) ![스크린샷: 팀 이용률 보고서](media/CQD-teams-utilization-report6.png)   

가로 막대형 차트는 지난 30 일간의 사용 (호출/스트림)이 가장 많은 클라이언트를 표 오른쪽에 표시 합니다.
   ![스크린샷: 팀 이용률 보고서](media/CQD-teams-utilization-report7.png)

이 페이지의 마지막 차트 집합은 각 미디어 유형을 개별적으로 표시 하며, 회의 및 P2P 사용을 보여 주는 분석을 포함 합니다. 아래 차트는 P2P에 비해 회의 사용량 수가 매우 높다는 것을 보여줍니다.
  ![스크린샷: 팀 이용률 보고서](media/CQD-teams-utilization-report8.png)

## <a name="audio-minutes-summary-report"></a>오디오 의사록 요약 보고서

오디오 의사록 사용 보고서에서 몇 가지 다른 보기를 통해 총 통화 시간 사용을 제공 합니다. 

텍스트 상자를 사용 하기 쉽도록 슬라이서 옆에 30 일 사용 현황 요약이 표시 됩니다. 맨 위 번호에는 30 일의 합계가 표시 되 고 그 아래에는 내부 및 외부 분석.

![스크린샷: 팀 이용률 보고서](media/CQD-teams-utilization-report9.png)

오른쪽 위 막대 그래프는 회의 오디오 사용에 대 한 yearlong 보기를 제공 합니다. 월을 마우스로 가리켜 회의 오디오 의사록을 표시 합니다.

P2P 및 컨퍼런스 오디오의 차이를 표시 하기 위해 아래쪽 왼쪽 차트는 지난 해의 모든 오디오를 가져와 두 형식 사이에서 분리 합니다.

![스크린샷: 팀 이용률 보고서](media/CQD-teams-utilization-report10.png)

오디오 의사록 페이지의 마지막 차트에는 전역 지도 오버레이에 대 한 오디오 분 사용량이 표시 됩니다. 이 차트는 빌드 및 서브넷 데이터를 테 넌 트에 업로드 하는 경우에만 적용 됩니다. 지도에 있는 원형 차트 오버레이는 드릴 다운할 수 있으며 그 후에는 국가별 오디오 사용을 제공 합니다.

![스크린샷: 팀 이용률 보고서](media/CQD-teams-utilization-report11.png)


## <a name="drill-through-capabilities"></a>드릴스루 기능

앞에서 언급 한 것 처럼 사용자가 매일 및 지역별 사용 현황 보고서에 드릴스루할 수 있습니다.

### <a name="daily-usage"></a>일일 사용량

일일 사용량 보고서를 사용 하면 관리자가 하루 중의 기간을 통해 피크 사용량을 확인할 수 있습니다. 사용 외에도, 그 날에 대 한 전반적인 사용자 정서 및 피드백을 캡처할 수 있습니다.

![스크린샷: 팀 이용률 보고서](media/CQD-teams-utilization-report12.png)

일일 사용량 보고서에는 선택한 날짜에 대 한 오디오, 비디오 및 화면 공유 수가 내부 및 외부 연결을 구분 하는 추가 기능으로 표시 됩니다. 회의 및 피어 투 피어 분석은 모달의 총계 상자 바로 오른쪽에 있습니다. 보고서의 오른쪽 상단에는 해당 요일의 관련 된 ID 및 참가자와의 회의 목록이 제공 됩니다. 컨퍼런스 목록은 또한 회의 세부 정보 보고서에 대 한 추가 드릴 다운을 제공 합니다. 그래픽 바꾸기

![스크린샷: 팀 이용률 보고서](media/CQD-teams-utilization-report13.png)

가운데 영역의 막대 그래프를 통해 사용자는 하루 중에 최대 소비 기간을 확인할 수 있습니다. 사용자는 그래프에 표시 된 시간으로 드릴 다운 하 여 해당 시간에 대 한 사용자 목록 보고서를 표시할 수 있습니다.

막대 그래프 오른쪽에는 사용자 피드백이 시각적 형식으로 표시 됩니다. 사용자 정서은 주관적인 일 수 있지만 잠재적인 문제를 식별 하는 데 사용할 수 있는 통찰력을 제공 합니다.

아래쪽 표에서는 해당 일에 대 한 메트릭 범위를 제공 합니다. 실패율이 부족 한 경우 관리자에 게 잠재적인 개선 영역을 제공할 수 있습니다. 아래 표시 된 대로 각 시간을 개별적으로 선택할 수도 있습니다.

이 데이터를 사용 하 여 사용량이 많은 시간에 문제가 있는 영역을 확인할 수 있습니다.


해당 날짜의 열을 클릭 하 여 해당 시간에 대 한 메트릭을 표시 합니다.
![스크린샷: 팀 이용률 보고서](media/CQD-teams-utilization-report14.png)
  
  1.  차트 아래 표에 해당 시간에 대 한 메트릭이 표시 됩니다. 열 머리글을 기준으로 정렬할 수 있습니다. 그러나, 문제가 있는 영역을 찾는 데 관심이 있을 것입니다.  
    ![스크린샷: 팀 이용률 보고서](media/CQD-teams-utilization-report15.png)
    
  2.  이 기간 동안에는 해당 IND 지역에서 비디오 성능이 저하 되는 것을 확인할 수 있습니다. 결과적으로, 지역 및 시간 프레임이 식별 됨에 따라 CQD QER Microsoft 보고서를 사용 하 여 문제가 있는 위치를 좁힐 수 있습니다.

### <a name="conference-details"></a>회의 정보

회의 정보 보고서는 참석자 목록에서 세션 중에 사용 되는 미디어 형식에 모임에 대 한 추가 정보를 제공 합니다.

일일 사용량 페이지의 회의 ID 차트에 있는 참가자 표시줄로 회의를 마우스 오른쪽 단추로 클릭 하 여 회의 세부 정보로 드릴 다운 합니다.

![스크린샷: 팀 이용률 보고서](media/CQD-teams-utilization-report24.png)

![스크린샷: 팀 이용률 보고서](media/CQD-teams-utilization-report25.png)
  

아래쪽 표에서 문제 해결을 지원 하기 위해 회의 참가자와 패킷 손실 및 지터까지 관련 된 모든 정보를 볼 수 있습니다.

![스크린샷: 팀 이용률 보고서](media/CQD-teams-utilization-report26.png)


### <a name="regional-audio-details"></a>지역별 오디오 정보

지역 오디오 세부 정보 드릴 다운은 선택 된 지역의 오디오 통화 시간 사용량을 표시 합니다. CQD에 대 한 액세스 권한이 있는 사용자는 선택한 지역 내에서 P2P와 컨퍼런스 오디오 모두에 대 한 사용 추세를 볼 수 있습니다.

1.  호출 횟수 요약 페이지에서 표를 통해 특정 영역으로 드릴 다운 합니다.
  ![스크린샷: 팀 이용률 보고서](media/CQD-teams-utilization-report16.png)

2.  영역이 있는 행을 선택 하면 추가 정보가 필요 합니다.
  ![스크린샷: 팀 이용률 보고서](media/CQD-teams-utilization-report17.png)

3.  데이터 경향에는 현재 네트워크에서 사용 되는 중요 한 분 수가 표시 되며,이는 회의가 surpassing P2P를 사용 하는 것입니다.
  ![스크린샷: 팀 이용률 보고서](media/CQD-teams-utilization-report18.png)

지역 오디오 추세는 전세계의 외부 영향에 따라 사용자에 게 영향을 주는 방식을 표시 하는 데 사용 될 수 있습니다. 특히, 원격으로 작업 해야 하는 사람들을 위해 EMEA 및 APAC 지역에 대 한 외부 사용량을 확인할 것입니다.


### <a name="user-list"></a>사용자 목록

사용자 목록 드릴 다운은 보고서를 보는 사람이 선택한 특정 시간에 대 한 사용자 관련 정보를 예상할 때 제공 됩니다. 일일 사용량 보고서의 시간별 추세 그래프에서 드릴 다운을 통해 사용자 목록 보고서에 액세스할 수 있습니다. 다음과 같이 추가 정보가 필요한 시간을 마우스 오른쪽 단추로 클릭 하 고 드릴스루 및 사용자 목록 선택 합니다.

![스크린샷: 팀 이용률 보고서](media/CQD-teams-utilization-report19.png)

사용자 목록 보고서는 페이지의 위쪽 가운데에 도넛형 차트를 통해 내부/외부 연결을 표시 합니다. 아래 이미지에서 회사 네트워크 외부에서 많은 참여를 하 고 있는 것을 확인할 수 있습니다.

그래프의 오른쪽 위에는 해당 시간 내에 각 사용자가 수행한 통화 수가 표시 됩니다.

![스크린샷: 팀 이용률 보고서](media/CQD-teams-utilization-report20.png)

아래쪽 표에서는 해당 시간 동안 각 사용자에 게 참여 한 세션에 대 한 자세한 정보를 제공 합니다. 오류 유형 열은 drop에 대 한 호출을 발생 시킨 원인을 확인 하는 데 유용 합니다. 캡처 및 렌더링 장치 열은 통화의 품질이 좋지 않다고 보고 한 이유를 식별 하는 데 유용 합니다.


## <a name="related-topics"></a>관련 항목

[통화 품질 대시보드에서 사용할 수 있는 차원 및 측정값](dimensions-and-measures-available-in-call-quality-dashboard.md)

[통화 품질 대시보드의 분류 간소화](stream-classification-in-call-quality-dashboard.md)

[비즈니스용 Skype 통화 분석 설정](set-up-call-analytics.md)

[통화 분석을 사용하여 통화 품질 저하 문제 해결](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[통화 분석 및 통화 품질 대시보드](difference-between-call-analytics-and-call-quality-dashboard.md)
 