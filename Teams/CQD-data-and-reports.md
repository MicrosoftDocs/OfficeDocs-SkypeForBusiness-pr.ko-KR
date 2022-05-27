---
title: CQD(통화 품질 대시보드)의 데이터 및 보고서
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.reviewer: mikedav, siunies, gageames
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
search.appverid: MET150
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Reporting
- ms.lync.lac.ToolsCallQualityDashboard
- seo-marvel-apr2020
description: Microsoft CQD(통화 품질 대시보드)에서 사용할 수 있는 데이터 및 보고서에 대해 알아봅니다.
ms.openlocfilehash: c30840ea4bf1de02572300044964211c5668056f
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/25/2022
ms.locfileid: "65675010"
---
# <a name="data-and-reports-in-call-quality-dashboard-cqd"></a>CQD(통화 품질 대시보드)의 데이터 및 보고서

Microsoft CQD(통화 품질 대시보드)는 NRT(거의 실시간) 데이터 피드를 사용합니다. 통화 레코드는 통화 종료 후 30분 이내에 CQD에서 사용할 수 있습니다. NRT 파이프라인의 호출 레코드는 데이터 세트에서 제거되기 전에 몇 달 동안만 사용할 수 있습니다.

## <a name="many-ways-to-access-cqd-data"></a>CQD 데이터에 액세스하는 여러 가지 방법

여러 가지 방법을 통해 CQD 데이터에 액세스할 수 있습니다. 요구 사항을 가장 잘 충족하는 것을 선택합니다.

|&nbsp;|&nbsp;|
|---|---|
|Teams 관리 센터[(https://admin.teams.microsoft.com)](https://admin.teams.microsoft.com)|CQD 데이터는 읽기 쉬운 형식으로 필요한 가장 일반적인 데이터를 보여 주는 Teams 관리 센터의 **사용자** 페이지에 포함됩니다. **사용자** 아래에 있는 CQD 데이터는 사용자 지정할 수 없습니다.|
|CQD 포털 [(https://cqd.teams.microsoft.com)](https://cqd.teams.microsoft.com)|드릴스루 필터링을 통해 대부분의 요구 사항을 충족하는 강력한 요약 및 자세한 보고서입니다. CQD 포털에서 보고서를 사용자 지정할 수도 있습니다. <br><br>[CQD](#import-the-cqd-report-templates) 포털에서 데이터를 분석하는 데 도움이 되는 두 개의 CQD 보고서 템플릿을 가져옵니다.|
|Power BI|직접 쿼리를 사용하여 [사용자 지정 가능한 Power BI 템플릿](CQD-Power-BI-query-templates.md)을 사용하여 Power BI CQD 데이터를 볼 수 있습니다. [CQD에 대한 Power BI 쿼리 템플릿을 다운로드합니다](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true).<br><br>[REST API를 사용하여 Power BI 통해 CQD 데이터에 액세스할](/skypeforbusiness/management-tools/call-quality-dashboard/data-api) 수도 있습니다. 오프라인으로 작업할 수 있도록 CQD 데이터를 다운로드하려는 경우 이 메서드를 사용합니다. 이 메서드를 사용하면 성능이 향상됩니다. 특히 온라인 상태에서 Power BI 수렁에 빠져 있는 큰 데이터 집합에 유용합니다.|
|그래프 API|[Graph API](/graph/api/resources/callrecords-api-overview) 사용하여 통화 품질 데이터에 직접 액세스합니다. 가장 복잡한 방법이지만 통화 품질 데이터를 분석할 때 가장 제어하고 유연하게 제어할 수 있습니다. 예를 들어 조직의 다른 데이터와 조인해야 하는 경우 Graph API 사용하여 데이터 모델을 만들고 통화 품질 데이터를 통합할 수 있습니다.|

## <a name="import-the-cqd-report-templates"></a>CQD 보고서 템플릿 가져오기

[큐레이팅된 두 개의 CQD 보고서 템플릿](https://aka.ms/qertemplates)(모든 네트워크 및 관리형 네트워크)을 다운로드하여 CQD를 사용하여 빠르게 속도를 높일 수 있습니다. 모든 네트워크 템플릿은 빌드 데이터 파일로 작동하도록 최적화되었지만 다음 섹션에 설명된 대로 빌드 정보를 수집하고 CQD에 업로드하는 동안 사용할 수 있습니다.

**템플릿을 가져오려면(. CQDX)를 CQD로 변환** 합니다.

1. CQD의 페이지 맨 위에 있는 메뉴에서 **자세한 보고서를** 선택합니다.

2. 왼쪽 패널에서 **가져오기** 를 선택합니다. 첫 번째 CQDX 템플릿으로 이동하고 **열기** 를 선택합니다.

3. 템플릿이 업로드되면 팝업 창에 "보고서 가져오기가 성공했습니다."라는 메시지가 표시됩니다.

4. 두 번째 CQD 템플릿에 대해 2단계와 3단계를 반복합니다.

   > [!NOTE]
   > 각 사용자는 CQD 템플릿을 CQD 인스턴스로 가져와야 합니다.

## <a name="euii-data"></a>EUII 데이터

규정 준수를 위해 최종 사용자 식별 정보(EUII) 데이터(개인 식별 정보 또는 PII라고도 함)는 28일 동안만 유지됩니다. NRT 데이터가 28일 표시를 초과하면 EUII가 포함된 필드가 지워지고 EUII가 없는 NRT 데이터가 생성됩니다. EUII 데이터를 포함하는 필드는 다음과 같습니다.

- 전체 IP 주소
- MAC(미디어 Access Control) 주소
- BSSID(기본 서비스 집합 식별자)
- SIP(세션 시작 프로토콜) URI(비즈니스용 Skype만 해당)
- UPN(사용자 계정 이름)
- 컴퓨터 엔드포인트 이름
- 사용자 축자 피드백
- 개체 ID(엔드포인트 사용자의 Active Directory 개체 ID)
- 전화 번호

### <a name="admin-roles-with-and-without-euii-access"></a>EUII 액세스 권한이 있고 없는 역할 관리

이러한 [RBAC](/azure/role-based-access-control/overview) 역할에는 EUII 액세스 권한이 **있습니다** .

- 전역 관리
- Teams Service 관리
- Teams Communications 관리
- Teams 커뮤니케이션 지원 엔지니어
- 전역 읽기 권한자
- 비즈니스용 Skype 관리

이러한 RBAC 역할에는 EUII 액세스 권한이 **없습니다** .

- 보고서 읽기 권한자
- Teams 통신 지원 전문가

## <a name="date-controls"></a>날짜 컨트롤

CQD는 다음과 같은 롤링 추세 형식을 지원합니다.

- 5일
- 7일
- 30일
- 60일
- 90일

URL Date 매개 변수는 Day 필드를 허용합니다. 롤링 데이 보고서는 추세의 마지막 날로 YYYY-MM-DD 형식으로 지정된 날짜를 사용합니다. URL Date 매개 변수 "00"은 "today"를 나타냅니다.

|URL|롤링 데이 추세 종료 날짜|
|:---|:---|
|<span>\<cqdv3>https:///spd/#/Dashboard//\<reportid>/2019-02/</span>|2019년 2월의 현재 날짜|
|<span>\<cqdv3>https:///spd/#/Dashboard//\<reportid>/2019-02-15/</span>|2019년 2월 15일|
|<span>\<cqdv3>https:///spd/#/Dashboard//\<reportid>00/</span>|현재 날짜|

기본적으로 해당 월의 현재 날짜는 롤링 데이 추세 마지막 날로 사용됩니다.

## <a name="data-available-in-cqd-reports"></a>CQD 보고서에서 사용할 수 있는 데이터

기본 요약 및 자세한 CQD 보고서는 조직의 통화 품질을 관리하는 데 필요한 모든 것일 수 있습니다. 필요한 경우 [사용자 지정 보고서를 만들](#create-custom-detailed-reports) 수 있습니다.

Power BI 사용하여 CQD 데이터를 분석하려면 [Power BI 사용하여 Teams 대한 CQD 데이터를 분석](CQD-Power-BI-query-templates.md)합니다.

|기능|요약 보고서|자세한 보고서|
|:---|:---|:---|
|애플리케이션 공유 메트릭|아니요|예|
|고객 빌드 정보 지원|예|예|
|고객 엔드포인트 정보 지원|<span>cqd.teams.microsoft.com<span/>|<span>cqd.teams.microsoft.com<span/>|
|드릴다운 분석 지원|아니요|예|
|미디어 안정성 메트릭|아니요|예|
|기본 제공 보고서|예|예|
|개요 보고서|예|예|
|사용자별 보고서 집합|아니요|예|
|보고서 집합 사용자 지정(보고서 추가, 삭제, 수정)|아니요|예|
|비디오 기반 화면 공유 메트릭|아니요|예|
|비디오 메트릭|아니요|예|
|사용 가능한 데이터 양|지난 12개월|지난 12개월|
|데이터 Microsoft Teams|예|예|

### <a name="select-product-data-to-see-in-reports"></a>보고서에 표시할 제품 데이터 선택

요약 및 Location-Enhanced 보고서에서 **제품 필터** 드롭다운을 사용하여 모든 제품 데이터, Microsoft Teams 데이터만 표시하거나 온라인 데이터만 비즈니스용 Skype 수 있습니다.

> [!div class="mx-imgBorder"]
> ![스크린샷: 제품 필터 컨트롤 옵션을 보여줍니다.](media/206ad818-0f72-4c8e-b25e-3cc8fcfbef05.png)

자세한 보고서에서 **Is Teams** 차원을 사용하여 데이터를 필터링하여 온라인 데이터를 Microsoft Teams 또는 비즈니스용 Skype 수 있습니다.

## <a name="summary-reports"></a>요약 보고서

CQD에 처음 로그인할 때 CQD 대시보드에 표시되는 보고서입니다. 품질이 좋지 않은 서브넷을 식별하는 데 도움이 되는 일별, 월별 및 테이블 보고서를 통해 품질 추세를 한눈에 볼 수 있습니다.

|탭|설명|
|---|---|
|전체 통화 품질|다른 3개의 탭을 집계합니다.|
|서버 - 클라이언트|서버와 클라이언트 엔드포인트 간의 스트림에 대한 세부 정보입니다.|
|클라이언트 - 클라이언트|두 클라이언트 엔드포인트 간의 스트림에 대한 세부 정보입니다.|
|음성 품질 SLA|비즈니스용 Skype 음성 품질 [SLA](https://go.microsoft.com/fwlink/p/?linkid=846252)에 포함된 통화에 대한 정보입니다.|

### <a name="overall-call-quality-tab"></a>전체 통화 품질 탭

이 탭의 데이터를 사용하여 스트림 수 및 낮은 비율에 따라 통화 품질 상태 및 추세를 평가합니다. 오른쪽 위 모서리의 범례는 이러한 메트릭을 나타내는 색 및 시각적 요소를 보여 줍니다.

> [!div class="mx-imgBorder"]
> ![스크린샷: 통화 품질 탭을 표시합니다.](media/c8d183b1-6592-49b0-a81d-35cc0568d5f0.png)

스트림 Good, Poor 및 Unclassified의 세 그룹으로 분류됩니다. 또한 가난한 것으로 분류된 스트림의 비율을 총 분류된 스트림 수에 대해 계산된 *가난한* *%* 값이 있습니다. *불량 % = 불량 스트림/(잘못된 스트림+ 양호한 스트림) \* 100* 이므로 가난한 *%* 는 여러 *미분류* 스트림의 존재에 영향을 받지 않습니다. 스트림을 불량 또는 양수로 분류하는 항목을 확인하려면 [통화 품질 대시보드의 스트림 분류를 참조하세요](stream-classification-in-call-quality-dashboard.md).

왼쪽의 배율을 사용하여 스트림 개수 값을 측정합니다.

> [!div class="mx-imgBorder"]
> ![스크린샷: 스트림 개수 값을 보여줍니다.](media/850bd25d-d9b2-4df4-8ca6-526a528897c2.png)

오른쪽의 배율을 사용하여 불량 % 값을 측정합니다.

> [!div class="mx-imgBorder"]
> ![스크린샷: 잘못된 % 값을 보여줍니다.](media/29795f71-ca96-4763-a76c-b4bb7c0e5828.png)

막대 위로 마우스를 가져가 실제 숫자 값을 가져올 수도 있습니다.

> [!NOTE]
> 다음 예제는 매우 작은 샘플 데이터 집합에서 온 것이며 실제 배포에서는 값이 현실적이지 않습니다.

> [!div class="mx-imgBorder"]
> ![스크린샷: 데이터에 액세스하는 데 사용되는 마우스를 보여줍니다.](media/8724b016-1a50-4d19-b48a-3b1aae4eb895.png)

전체 스트림 볼륨은 계산된 불량 백분율의 관련성을 결정하는 데 도움이 됩니다. 전체 스트림의 볼륨이 작을수록 보고된 낮은 백분율 값의 신뢰성이 떨어집니다.

### <a name="server-client-tab-and-client-client-tabs"></a>Server-Client 탭 및 Client-Client 탭

이 두 탭은 엔드포인트 간 시나리오에서 발생한 스트림에 대한 세부 정보를 제공합니다. Server-Client 탭에는 미디어 스트림이 흐르는 네 가지 시나리오를 나타내는 4개의 축소 가능한 섹션이 있습니다.

- 내부에 유선
- 외부 유선
- Wi-Fi 내부
- Wi-Fi 외부

마찬가지로 Client-Client 탭에는 접을 수 있는 5개의 섹션이 있습니다.

- Wired Inside — Wired Inside
- 유선 내부 - 외부 유선
- 외부 유선 - 외부 유선
- 유선 내부 - WiFi Inside
- 유선 내부 - Wi-Fi 외부

#### <a name="inside-versus-outside"></a>내부 및 외부

CQD는 존재하는 경우 빌드 정보를 사용하여 스트림을  *내부*  또는 *외부*  로 분류합니다. 각 스트림의 엔드포인트는 서브넷 주소와 연결됩니다. 서브넷이 업로드된 건물 정보에서 InsideCorp로 표시된 서브넷 목록에 있는 경우 *내부* 로 간주됩니다. 빌드 정보가 아직 업로드되지 않은 경우 내부 테스트는 항상 스트림을 *외부* 로 분류합니다.

Server-Client 시나리오에 대한 내부 테스트는 클라이언트 엔드포인트만 고려합니다. 서버는 항상 사용자의 관점에서 외부에 있기 때문에 테스트에서는 고려하지 않습니다.

#### <a name="wired-versus-wifi"></a>유선 및 WiFi

이름에서 알 수 있듯이 분류 조건은 클라이언트 연결의 형식을 기반으로 합니다. 서버는 항상 유선이며 계산에 포함되지 않습니다. 지정된 스트림에서 두 엔드포인트 중 하나가 WiFi 네트워크에 연결된 경우 CQD는 WiFi로 분류합니다.

> [!NOTE]
> 스트림이 지정된 경우 두 엔드포인트 중 하나가 WiFi 네트워크에 연결된 경우 CQD에서 WiFi로 분류됩니다.

## <a name="tenant-data-information"></a>테넌트 데이터 정보

CQD 요약 보고서 대시보드에는 오른쪽 위 모서리의 설정 메뉴에서 **테넌트 데이터 업로드** 선택하여 액세스하는 **테넌트 데이터 업로드** 페이지가 포함되어 있습니다. 이 페이지는 관리자가 다음과 같은 자체 정보를 업로드하는 데 사용됩니다.

- IP 주소 및 지리적 정보의 맵입니다.
- 각 무선 AP 및 해당 MAC 주소의 지도입니다.
- 엔드포인트 메이크/모델/형식에 대한 엔드포인트의 맵입니다.

CQD가 보고서에 이 정보를 포함할 수 있도록 테넌트, 빌드 및 위치 데이터를 업로드하는 것이 좋습니다. 이 데이터를 아직 업로드하지 않은 경우 [업로드 테넌트 및 빌드 데이터를](CQD-upload-tenant-building-data.md) 읽습니다.

## <a name="detailed-reports"></a>자세한 보고서

|이름|설명|
|---|---|
|Location-Enhanced 보고서|위치 정보를 기반으로 품질 추세를 표시합니다. 이 보고서는 [테넌트 데이터를 업로드한](CQD-upload-tenant-building-data.md) 경우에만 표시됩니다.|
|안정성 보고서|오디오, 비디오, VBSS(비디오 기반 화면 공유) 및 앱 공유 보고서를 포함합니다.|
|환경 보고서 품질|회의실을 비롯한 모든 클라이언트 및 디바이스에 대한 오디오 품질 및 안정성. 이러한 보고서는 다운로드 가능한 [CQD 템플릿](https://aka.ms/QERtemplates)의 "슬림다운" 버전으로, 오디오 품질 및 안정성을 분석하기 위한 주요 영역에 중점을 두고 있습니다.|
|품질 드릴다운 보고서|드릴다운: 지역, 위치, 서브넷, 시간 및 사용자별 날짜입니다.|
|오류 드릴다운 보고서|드릴다운: 지역, 위치, 서브넷, 시간 및 사용자별 날짜입니다.|
|내 통화 보고서 평가|지역, 위치 또는 사용자별 사용자 통화 등급을 분석합니다. 축자 피드백을 포함합니다.|
|지원 센터 보고서|기술 지원 센터 보고서는 개별 사용자, 사용자 그룹 또는 모든 사용자의 통화 및 모임 데이터를 살펴봅니다. 이러한 보고서는 건물 및 EUII 데이터를 통합하여 네트워크 위치, 회의 세부 정보, 디바이스 또는 펌웨어에 따라 가능한 시스템 문제를 식별하는 데 도움이 될 수 있습니다.|
|클라이언트 버전 보고서|클라이언트 버전 요약: 각 클라이언트 앱 버전에 대한 세션 및 사용자 수 보기<br><br>사용자별 클라이언트 버전: 각 클라이언트 앱 버전의 사용자 이름 보기 <br><br>제품 및 클라이언트 유형에 대한 미리 빌드된 필터는 버전을 특정 클라이언트에 집중하는 데 도움이 됩니다.|
|엔드포인트 보고서|컴퓨터 엔드포인트(컴퓨터 만들기 및 모델)별로 통화 품질을 표시합니다. 이러한 보고서에는 업로드한 경우 데이터 빌드가 포함됩니다.|

## <a name="create-custom-detailed-reports"></a>사용자 지정 상세 보고서 만들기

기본 CQD 보고서가 요구 사항을 충족하지 않는 경우 다음 지침을 사용하여 사용자 지정 보고서를 만듭니다. 또는(2020년 1월 현재) [대신 CQD 보고서에 Power BI 사용합니다](cqd-power-bi-query-templates.md).

로그인 \(에 표시되는 화면 맨 위에 있는 보고서 풀다운 목록에서 **[요약 보고서** ] 화면에서\) **[세부 보고서**  ]를 **선택한 다음 새로** 만들기를 선택합니다. 보고서에서 **편집** 을 클릭하여 쿼리 편집기 확인합니다. 각 보고서는 쿼리를 통해 큐브로 지원됩니다. 보고서는 쿼리에서 반환된 데이터의 시각화입니다. 이 쿼리 편집기 이러한 쿼리 및 보고서의 표시 옵션을 편집하는 데 도움이 됩니다.

> [!IMPORTANT]
> 네트워크 범위를 사용하여 슈퍼넷(단일 라우팅 접두사로 여러 서브넷의 조합)을 나타낼 수 있습니다. 모든 새 건물 업로드는 겹치는 범위에 대해 확인됩니다. 이전에 건물 파일을 업로드한 경우 현재 파일을 다운로드하고 다시 업로드하여 겹침을 식별하고 문제를 해결한 후 다시 업로드해야 합니다. 이전에 업로드한 파일이 겹치면 보고서의 건물에 서브넷이 잘못 매핑될 수 있습니다. 특정 VPN 구현은 서브넷 정보를 정확하게 보고하지 않습니다. 서브넷에 대한 하나의 항목 대신 빌드 파일에 VPN 서브넷을 추가할 때 VPN 서브넷의 각 주소에 대해 별도의 항목이 별도의 32비트 네트워크로 추가되는 것이 좋습니다. 각 행에는 동일한 빌드 메타데이터가 있을 수 있습니다. 예를 들어 172.16.18.0/24에 대해 한 행 대신 256개의 행이 있어야 하며, 각 주소의 행은 172.16.18.0/32에서 172.16.18.255/32 사이여야 합니다.
>
> VPN 열은 선택 사항이며 기본값은 0입니다.  VPN 열의 값을 1로 설정하면 해당 행으로 표시되는 서브넷이 서브넷 내의 모든 IP 주소와 일치하도록 완전히 확장됩니다.  이러한 서브넷을 완전히 확장하면 데이터 빌드와 관련된 쿼리 시간에 부정적인 영향을 주기 때문에 VPN 서브넷에만 이 작업을 아끼고 사용해야 합니다.

보고서의 가로 막대형 차트와 추세선을 가리키면 자세한 값이 표시됩니다. 포커스가 있는 보고서에는 작업 메뉴인 **편집**, **복제**, **삭제**, **다운로드** 및 **내보내기 보고서 트리** 가 표시됩니다.

## <a name="query-filters"></a>쿼리 필터

쿼리 필터는 CQD의 쿼리 편집기 사용하여 구현됩니다. 이러한 필터는 CQD에서 반환되는 레코드 수를 줄여 보고서의 전체 크기 및 쿼리 시간을 최소화하는 데 사용됩니다. 이는 관리되지 않는 네트워크를 필터링하는 데 특히 유용합니다. 다음 표에 나열된 필터는 정규식(RegEx)을 사용합니다.

|Filter|설명|CQD 쿼리 필터 예제|
|---|---|---|
|빈 값 없음|일부 필터에는 빈 값을 필터링할 수 있는 옵션이 없습니다. 빈 값을 수동으로 필터링하려면 빈 식을 사용하고 필요에 따라 필터를 Equals 또는 Not Equals로 설정합니다.|두 번째 건물 이름 \<\> \^\\\*\$|
|공통 서브넷 제외|관리되지 않는 네트워크와 분리할 유효한 건물 파일이 없으면 홈 네트워크가 보고서에 포함됩니다. 이러한 홈 서브넷은 IT에서 제어할 수 없는 범위이며 보고서에서 신속하게 제외될 수 있습니다. 이 가이드에 정의된 일반적인 서브넷은 10.0.0.0, 192.168.1.0 및 192.168.0.0입니다.|두 번째 서브넷 \<\> 10.0.0.0 \|192.168.0.0 \|192.168.1.0|
|내부만 보기|관리(내부) 또는 관리되지 않는(외부)에 대한 보고서를 필터링하는 데 사용됩니다. 관리되는 CQD 템플릿은 이미 이러한 필터로 미리 구성되어 있습니다.|Second Inside Corp = Inside|

## <a name="report-filters"></a>보고서 필터

CQD 보고서 필터를 사용하여 조사의 초점을 좁힐 수 있습니다. 쿼리 편집기 또는 보고서에서 직접 렌더링된 보고서에 필터를 추가하여 보고서 필터를 사용합니다. 다음 보고서 필터는 [CQD 템플릿](https://aka.ms/QERtemplates) 전체에서 사용됩니다.

|Filter|설명|CQD 보고서 필터 예제|
|---|---|---|
|달|첫 번째 연도, 월로 시작합니다.|2017-10|
|알파벳|모든 알파벳 문자에 대한 필터입니다.|[a-z]|
|숫자|모든 숫자 문자에 대한 필터입니다.|[0-9]|
|비율|백분율에 대한 필터입니다.|([3-9]\\.)\| ([3-9])\| ([1-9][0-9])|

### <a name="drill-down-filters"></a>드릴다운 필터

CQD 보고서에는 통화 품질 조사의 초점을 좁히기 위한 강력한 도구인 몇 가지 드릴다운 필터가 있습니다. 드릴다운 필드를 선택하면 보고서가 자동으로 적절한 탭을 열고 선택한 값을 필터링합니다. 해당 탭에 자체 드릴다운 필드가 있고 하나의 필드가 선택된 경우 두 필터 집합이 모두 적용되어 결과 데이터 집합의 범위를 점진적으로 좁힐 수 있습니다.

![드릴다운 보고서 흐름을 보여 주는 다이어그램](media/qerguide-image-drillthrureportflow.png)

#### <a name="adding-and-editing-drill-down-fields"></a>드릴다운 필드 추가 및 편집

보고서를 편집할 때 쿼리 편집기 사용하여 고유한 드릴다운 필드를 지정하는 옵션이 있습니다.

편집하려는 보고서에 대해 **...** 를 클릭하여 시작한 다음 **편집** 을 선택합니다.

![드릴다운 필드를 편집하는 스크린샷](media/qerguide-image-addeditdrilldownfields.png)

쿼리 편집기 왼쪽에 있는 목록에서 차원을 선택합니다. 그런 다음 **탐색** 레이블 아래의 드롭다운을 클릭하고 해당 차원을 드릴스루할 탭 및 확장기 그룹을 선택합니다. 참고: 현재 드릴다운 기능은 다른 탭으로 이동해야만 작동합니다. 특정 확장기 드릴스루에 대한 지원은 나중에 추가됩니다. 마지막으로 **닫** 기를 클릭하여 차원에 변경 내용을 저장한 다음 **저장** 을 클릭하여 쿼리 편집기 저장하고 닫습니다.

![쿼리 편집기 차원을 선택하는 스크린샷](media/qerguide-image-selectquerydimension.png)

### <a name="multi-select-filters"></a>다중 선택 필터

CQD는 드릴다운 기능 외에도 여러 값(OR 필터)을 사용하여 필터 지정을 지원합니다.

여러 필터 값을 선택하려면 먼저 보고서에 새 필터를 추가합니다. **필터** 레이블 옆을 클릭하고 **+** 사용할 차원의 이름을 입력한 다음 **추가** 를 클릭합니다.

![다중 선택 필터를 추가하는 스크린샷](media/qerguide-image-addmultiselectfilter.png)

그런 다음 **검색** (새 필터 옆에 있는 돋보기 아이콘)을 클릭합니다. 텍스트 필드와 [ **모두 선택** ] 및 [ **반전**]을 비롯한 다양한 옵션이 표시됩니다. 값을 입력하고 해당 필드 옆에 있는 **검색** 을 클릭하여 검색합니다. 또는 텍스트 필드를 비워 두고 **검색** 을 클릭하여 처음 100개 옵션까지 봅니다.

```powershell
/filter/[AllStreams].[Second Tenant Id]\|[YOUR TENANT ID HERE]
```

예제:

![쿼리 필터를 추가하는 스크린샷](media/qerguide-image-addfilter.png)

### <a name="dashboard-level-filters"></a>대시보드 수준 필터

특정 CQD 보고서에는 대시보드 수준 필터가 추가되어 공통 매개 변수로 쉽게 필터링할 수 있습니다. 이러한 필터는 일반 보고서 탭 외부와 제품 필터 바로 아래에 표시되며 대시보드의 모든 필터에 적용됩니다.

![대시보드 필터의 스크린샷.](media/qerguide-image-dashboardfilters.png)

```powershell
/filter/[AllStreams].[Is Teams]|[TRUE | FALSE]
```

### <a name="url-filters"></a>URL 필터

CQD는 URL에 필터 추가를 지원합니다. 이렇게 하면 CQD 쿼리를 쉽게 공유하거나 책갈피를 만들 수 있습니다. 추세 월, 테넌트 ID 또는 언어와 같은 매개 변수를 URL에 정의할 수 있습니다. 제품 또는 대시보드 수준 필터를 URL에 추가할 수도 있습니다.
페더레이션된 엔드포인트가 보고서에 영향을 줄 수 있는 관리형 건물 또는 네트워크를 수정할 때 CQD 보고서에서 페더레이션된 데이터를 제외하면 유용합니다.

필터를 추가하려면 URL 끝에 다음을 추가합니다.

```console
/filter/[AllStreams].[Second Tenant Id]\|[YOUR TENANT ID HERE]
```

예제:

`https://cqd.teams.microsoft.com/cqd/#/1234567/2018-08/filter/[AllStreams].[Second Tenant Id]|[TENANTID]`

URL에 대시보드 수준 필터를 추가하려면 해당 필터가 CQD에 제품 또는 대시보드 수준 필터로 있어야 합니다. 추세 월 뒤와 URL 매개 변수 앞의 URL에 다음 필터를 추가합니다.

`filter/DATA_MODEL_NAME|VALUE`

예를 들어 Microsoft Teams 제품 필터 값을 적용하려면 다음을 추가합니다.

`filter/[AllStreams].[Is%20Teams]|[True]`

전체 URL은 다음과 같습니다.

`https://cqd.teams.microsoft.com/spd/#/Dashboard/2624085/2018-9/filter/[AllStreams].[Is%20Teams]|[True]`

다중 선택 값으로 URL 필터를 적용하려면 각 값을 파이프(|) 문자로 구분합니다. 예를 들면 다음과 같습니다.

`filter/[AllStreams].[Media%20Type]|[Video]|[Audio]|[VBSS]`

잘못된 이름 또는 값을 지정하면 URL 필터가 적용되지 않습니다.

URL 필터를 사용하여 특정 차원에 대한 모든 보고서를 필터링할 수 있습니다. 가장 일반적인 URL 필터는 페더레이션된 참가자 원격 분석을 제외하거나 Teams 또는 비즈니스용 Skype Online에만 집중하도록 보고서를 필터링하는 데 사용됩니다. 페더레이션된 엔드포인트가 보고서에 영향을 줄 수 있는 관리형 건물 또는 네트워크를 수정할 때 CQD 보고서에서 페더레이션된 데이터를 제외하면 유용합니다.

|Filter|설명|CQD 쿼리 필터 예제|
|---|---|---|
|빈 값 없음|일부 필터에는 빈 값을 필터링할 수 있는 옵션이 없습니다. 빈 값을 수동으로 필터링하려면 빈 식을 사용하고 필요에 따라 필터를 Equals 또는 Not Equals로 설정합니다.|두 번째 건물 이름 \<\> \^\\\*\$|
|공통 서브넷 제외|관리되지 않는 네트워크와 분리할 유효한 건물 파일이 없으면 홈 네트워크가 보고서에 포함됩니다. 이러한 홈 서브넷은 IT에서 제어할 수 없는 범위이며 보고서에서 신속하게 제외될 수 있습니다. 이 문서에 정의된 일반적인 서브넷은 10.0.0.0, 192.168.1.0 및 192.168.0.0입니다.|두 번째 서브넷 \<\> 10.0.0.0 \|192.168.0.0 \|192.168.1.0|
|내부만 보기|관리(내부) 또는 관리되지 않는(외부)에 대한 보고서를 필터링하는 데 사용됩니다. 관리되는 CQD 템플릿은 이미 이러한 필터로 미리 구성되어 있습니다.|Second Inside Corp = Inside|

#### <a name="how-to-find-your-tenant-id"></a>테넌트 ID를 찾는 방법

CQD의 테넌트 ID는 Azure의 디렉터리 ID에 해당합니다. 디렉터리 ID를 모르는 경우 Azure Portal 찾을 수 있습니다.

1. Microsoft Azure 포털에 로그인합니다.<https://portal.azure.com>

2. **Azure Active Directory** 선택합니다.

3. **관리** 에서 **속성을** 선택합니다. 테넌트 ID는 **디렉터리 ID** 상자에 있습니다.

PowerShell을 사용하여 테넌트 ID를 찾을 수도 있습니다.

```powershell
Login-AzureRmAccount
```

## <a name="comparing-teams-and-skype-for-business-cqd-data"></a>Teams 및 비즈니스용 Skype CQD 데이터 비교

데이터를 검토할 때 Teams 및 비즈니스용 Skype 간의 데이터 차이를 볼 수 있습니다. 몇 가지 이유는 다음과 같습니다.

- 성능 및 안정성을 보장하기 위한 메커니즘의 차이점:
  - Teams 자동 다시 연결 및 빠른 로밍이 있습니다. 비즈니스용 Skype 않습니다.
  - Teams 동적 대역폭 관리가 있습니다. 비즈니스용 Skype 않습니다.
- TEAMS 및 비즈니스용 Skype 간의 [IP 주소 범위](Office-365-URLs-IP-address-ranges.md) 차이입니다. Teams IP 범위가 최신이므로 방화벽에서 연결 문제가 발생할 수 있습니다.

## <a name="related-topics"></a>관련 항목

[Teams 대한 통화 품질 개선 및 모니터링](monitor-call-quality-qos.md)

[CQD란?](CQD-what-is-call-quality-dashboard.md)

[CQD(통화 품질 대시보드) 설정](turning-on-and-using-call-quality-dashboard.md)

[테넌트 업로드 및 데이터 빌드](CQD-upload-tenant-building-data.md)

[CQD를 사용하여 통화 및 모임 품질 관리](quality-of-experience-review-guide.md)

[CQD에서 사용할 수 있는 차원 및 측정값](dimensions-and-measures-available-in-call-quality-dashboard.md)

[CQD의 스트림 분류](stream-classification-in-call-quality-dashboard.md)

[Power BI 사용하여 CQD 데이터 분석](CQD-Power-BI-query-templates.md)
