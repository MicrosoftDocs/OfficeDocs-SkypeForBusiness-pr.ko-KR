---
title: CQD 개발 샘플
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 8ca9bf7a-2d6f-48d5-a821-531009726525
description: '요약: 통화 품질 대시보드의 자습서 및 개발 샘플을 검토 합니다. 통화 품질 대시보드는 비즈니스용 Skype 서버용 도구입니다.'
ms.openlocfilehash: 4eac679950abdff5041bdfb63b633287d06a11e7
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36186972"
---
# <a name="cqd-development-samples"></a>CQD 개발 샘플

**요약:** 통화 품질 대시보드에 대 한 자습서 및 개발 샘플을 검토 합니다. 통화 품질 대시보드는 비즈니스용 Skype 서버용 도구입니다.

이 문서에서는 CQD (통화 품질 대시보드) 개발에 대 한 자습서 및 샘플을 제공 합니다.

## <a name="call-quality-dashboard-cqd-development-samples"></a>CQD (통화 품질 대시보드) 개발 샘플

자습서: CQD 데이터 서비스 및 리포지토리 서비스 API를 사용 하 여 사용자 지정 된 보고서 프레젠테이션을 작성 합니다.

### <a name="introduction-to-cqd"></a>CQD 소개

CQD는 온-프레미스 비즈니스용 Skype 서버 배포에 대 한 집계 된 통화 품질 정보에 빠르고 쉽게 액세스할 수 있도록 해 주는 기능을 제공 합니다. CQD는 체감 품질 보관 데이터베이스, 큐브 및 포털의 세 가지 구성 요소로 이루어져 있습니다. 포털은 주 프레젠테이션 계층 이며 다음 세 가지 구성 요소로 나눌 수 있습니다.

1. [비즈니스용 Skype 서버에서 CQD (통화 품질 대시보드) 용 데이터 API](data-api.md)를 통해 인증 된 사용자가 액세스할 수 있는 데이터 서비스입니다.

2. [비즈니스용 Skype 서버에서 CQD (통화 품질 대시보드) 용 리포지토리 API](repository-api.md)를 통해 인증 된 사용자가 액세스할 수 있는 저장소 서비스입니다.

3. 웹 포털-CQD 사용자가 보고 상호 작용 하는 HTML5 기반 인터페이스입니다. 인증 된 사용자는 액세스할 수 있습니다.

웹 포털에 표시 되는 보고서는 "보고서 집합"으로 그룹화 됩니다. 다음 그림은 두 개의 보고서가 포함 된 보고서 집합을 보여 줍니다. 아래 대시보드의 각 보고서에는 여러 가지 필터를 적용 하 여 성공한 통화 수, 잘못 된 통화 및 잘못 된 몇 개월 통화 백분율이 표시 됩니다. 

![CQD 샘플 보고서](../../media/9e0723f7-f850-4d11-9ecd-7e8e013a8bed.png)

CQD는 CQM (통화 품질 방법론)에 따라 만들어지므로 기본 보고서 집합은 CQM에서 도입 된 조사 흐름에 맞게 디자인 되었습니다. 사용자는 필요에 맞게 사용자 지정 보고서를 편집 하거나 만들 수 있습니다. 그러나 데이터를 시각화 하는 여러 가지 방법이 있으므로 CQD에서 제공 하는 시각화는 모든 사용자의 요구 사항을 완전히 처리 하지 못할 수 있습니다. 이러한 경우 사용자는 데이터 Api 및 리포지토리 Api를 활용 하 여 사용자 지정 보고서 페이지를 만들 수 있습니다. 이 자습서의 여러 예제를 살펴보겠습니다.

### <a name="how-the-dashboard-consumes-the-data-service"></a>대시보드가 데이터 서비스를 사용 하는 방법

CQD 홈페이지를 탐색 하는 경우 (예 http://localhost/cqd): 보고서 집합 및 인증 되 고 승인 된 사용자에 대 한 해당 보고서는 리포지토리 서비스에서 검색 됩니다. 전체 URL은 보고서-집합 ID와 연도-월 (보고서-집합 ID는 URL의 '/#/' 섹션 뒤에 있는 정수 번호 이며 기본적으로 현재 연도-월은 보고서의 끝에 (슬래시 다음에 표시 됨)로 추가 됩니다. 보고서 정의는 JSON 형식으로 저장 되며 저장소 서비스에서 검색 하면 데이터 서비스에 대 한 입력으로 사용 됩니다. 데이터 서비스는 입력을 기반으로 다차원 식 (MDX) 쿼리를 생성 한 다음 큐브에 대해 이러한 MDX 쿼리를 실행 하 여 각 보고서에 대 한 데이터를 검색 합니다. 

### <a name="building-customized-reports"></a>사용자 지정 보고서 빌드

CQD는 이미 보고서를 사용자 지정 하는 데 유연성이 많지만 사용자가 CQD에서 만든 여러 보고서에서 데이터를 집계할 수 있는 상황이 있을 수 있습니다. 예를 들어 표에 있는 모든 유선 통화 조합의 불량 통화 백분율을 표시 하는 보고서를 만들어야 할 수 있습니다 (그림과 같은 결과).

![CQD 테이블](../../media/ef19d535-5da6-44a9-91f6-1ed3f30b96f1.png)

사용자는 CQD에서 제공 하는 포털을 사용 하 여 여러 보고서로 이동 하 여, 각 항목에 대 한 불량 통화%를 추출 하 고 기록 해야 하며,이 경우 수집 해야 하는 데이터 요소가 많은 경우 복잡할 수 있습니다. 데이터 Api에서는 데이터 서비스에서 데이터를 검색 하 여 (예: AJAX 호출을 통해) 사용자에 게이 작업을 수행할 수 있는 프로그래밍 방식의 방법을 제공 합니다. 

 **예제 1: 간단한 보고서 샘플**

먼저 간단한 예를 살펴보겠습니다. 그림과 같은 HTML 페이지에서 오디오 정상 스트림 및 오디오 불량 스트림 수를 표시 하려면 다음을 수행 합니다. 2015

![CQD 예제 보고서](../../media/f0e4e61f-1fa5-4d69-b192-f19e9612bf1c.png)

필요한 것은 적절 한 매개 변수를 사용 하 여 데이터 서비스에 대 한 호출을 보내고 쿼리 결과를 HTML 표에 표시 하는 것입니다. 다음은 JavaScript 코드의 샘플입니다.

```        
$($.fn.freeFormReport = function (queries, urlApi, presentation) {
            var query = {
                Dimensions: [{ DataModelName: '[StartDate].[Month]' }],
                Filters: [{
                    DataModelName: '[StartDate].[Month]',
                    Value: '[2015-02-01T00:00:00]',
                    Operand: 0
                }],
                Measurements:
                    [{ DataModelName: '[Measures].[Audio Good Streams JPDR Count]' },
                     { DataModelName: '[Measures].[Audio Poor Streams JPDR Count]' },]
            };            

            $.ajax({
                url: 'http://localhost/QoEDataService/RunQuery',
                data: JSON.stringify(query),
                type: 'POST',
                async: true,
                contentType: 'application/json;charset=utf-8',
                success: function (data) {
                    //This is the jQuery syntax for document.GetElementById()
                    $('#AudioGoodStreamsJPDRCount').html(data.DataResult[0][1]);
                    $('#AudioPoorStreamsJPDRCount').html(data.DataResult[0][2]);
                }
                error: function (error) {
                    alert('Error getting data, check that the data service is running and that the URL is correct.');
           }
            });
        });
```

이 예제는 다음 세 단계로 deconstructed 수 있습니다.

1. 쿼리를 생성 합니다 (이 예에서는 변수 ' 쿼리 '에 정의 됨). 쿼리는 JSON 개체로 정의 되며, 다음 데이터를 포함 합니다.

   에서. 0 개 이상의 차원 각 차원은 DataModelName으로 표시 됩니다.

   b. 0 개 이상의 필터 각 필터에는 다음이 포함 됩니다.

   - DataModelName (필터 집합을 포함할 차원).

   - Value (피연산자에 따라 비교 되는 값)

   - 피연산자 (비교 형식, 0은 "같음")입니다.

     c. 하나 이상의 측정값.

2. AJAX 호출을 통해 데이터 서비스에 쿼리를 보냅니다. 다음 요청 매개 변수를 제공 해야 합니다.

   에서. url (http://[ServerName]/QoEDataService/RunQuery)입니다.

   b. data (' query ' 변수에 정의 된 JSON 개체의 문자열 표현). 데이터 서비스에서 성공에 대 한 콜백 함수의 매개 변수로 쿼리 결과를 반환 합니다.

   c. type (QoEDataService의 경우 RunQuery에는 ' 게시 ' 요청만 허용 됩니다.)

   a. async (AJAX 호출이 동기 또는 비동기 인지 여부를 나타내는 플래그)

   z.e.n.works. contentType ("application/json" 이어야 함).

   f. 성공 (AJAX 통화가 성공적으로 완료 되는 경우의 콜백 함수).

   g. 오류 (AJAX 호출이 실패 했을 때의 오류 처리 함수).

3. HTML의 div 요소에 데이터 넣기 (코드의 예제에서는 AJAX 요청이 성공적으로 완료 된 후 무명 함수 호출을 통해이 작업을 수행 합니다.)

JavaScript 코드를 HTML 페이지로 묶어 페이지에 그림에 표시 된 것과 같은 보고서가 표시 됩니다. 전체 html은 다음과 같습니다.

```
<!DOCTYPE html>
<html xmlns="http://www.w3.org/1999/xhtml">
<head>
</head>
<body>
    <script src="OpenSourceSoftware/Scripts/jquery-2.1.1.js"></script>

    <script>
        $($.fn.freeFormReport = function (queries, urlApi, presentation) {

            var query = {
                Dimensions: [{ DataModelName: '[StartDate].[Month]' }],
                Filters: [{
                    DataModelName: '[StartDate].[Month]',
                    Value: '[2015-02-01T00:00:00]',
                    Operand: 0
                }],
                Measurements:
                    [{ DataModelName: '[Measures].[Audio Good Streams JPDR Count]' },
                     { DataModelName: '[Measures].[Audio Poor Streams JPDR Count]' },]
            };            

            $.ajax({
                url: 'http://localhost/QoEDataService/RunQuery',
                data: JSON.stringify(query),
                type: 'POST',
                async: true,
                contentType: 'application/json;charset=utf-8',
                success: function (data) {
                    //This is the jQuery syntax for document.GetElementById()
                    $('#AudioGoodStreamsJPDRCount').html(data.DataResult[0][1]);
                    $('#AudioPoorStreamsJPDRCount').html(data.DataResult[0][2]);
                }
                error: function (error) {
                    alert('Error getting data, check that the data service is running and that the URL is correct.');
           }

            });
        });
    </script>
    <table border="1">
        <tr>
            <td></td>
            <td><div>Audio Good Streams JPDR Count</div></td>
            <td><div>Audio Poor Streams JPDR Count</div></td>
        </tr>
        <tr>
            <td>February</td>
            <td><div id="AudioGoodStreamsJPDRCount"></div></td>
            <td><div id="AudioPoorStreamsJPDRCount"></div></td>
        </tr>
    </table>
</body>
</html>
```

지금 까지는 보고서가 여전히 매우 간단 합니다. 사용자는 측정값, 차원 또는 필터를 추가 하 여 보고서를 사용자 지정할 수 있습니다. 예를 들어 AppSharing 불량 통화 백분율을 표시 하려는 경우 AppSharing에 대 한 새로운 측정이 추가 되어야 합니다. 모든 TCP 호출을 표시 하려는 경우 v.s. UDP 호출에서는 교통 형식에 대 한 새 차원이 추가 되어야 합니다. 특정 건물 내에서 불량 통화 수를 표시 하려는 경우 새 필터를 추가 하 여 해당 빌드에 대 한 통화를 선택 해야 합니다.

 **예제 2: 보고서 정의 샘플**

쿼리를 만들 때 측정값/차원/필터 및 해당 값의 전체 목록을 작성 하는 방법을 누군가가 생각 하는 것은 어려울 수 있습니다. 이 경우 포털로 이동 하 고, 보고서 편집기를 사용 하 여 보고서를 작성 하 고, 보고서 정의의 JSON 문자열을 보고, 정의를 사용자 지정 보고서에 복사할 수 있습니다. 

이 예제에서는 사용자가 기존 보고서 집합 (또는 보고서)의 ID를 입력 하 고 보고서 집합 또는 보고서의 정의를 웹 페이지에 표시할 수 있는 그림에 표시 된 것과 같은 웹 페이지를 만들게 됩니다. 그런 다음 사용자는 각 보고서의 JSON 문자열을 예제 1에 표시 된 것과 비슷한 코드에 연결 하 고 사용자가 원하는 모든 사용자 지정 보고서를 생성할 수 있습니다. 

![CQD 예제](../../media/01c45c23-c4d2-47b8-819f-0888cf71260f.png)

보고서 정의 뷰어 도구를 만들려면 필요한 모든 보고서 집합의 정의에 대 한 JSON 문자열 표현을 검색 하기 위해 리포지토리 서비스에 대 한 호출을 보내야 합니다. 리포지토리 API는 지정 된 보고서 집합 ID에 따라 보고서 집합 정의를 반환 합니다. 

간단한 예제는 다음과 같습니다. 코드에는 리포지토리 서비스에 쿼리를 전송 하 여 해당 식별자를 기반으로 리포지토리 항목의 콘텐츠를 가져오는 간단한 예제 블록이 포함 되어 있습니다. 그리고 다음 코드 (processReportSetData 메서드)는 AJAX 호출을 보내 해당 보고서 집합 내의 각 보고서에 대 한 정의를 가져옵니다. CQD 웹 포털의 ID는 보고서 집합의 ID 이므로 AJAX 통화는 보고서 집합 항목을 반환 합니다. 리포지토리 API 및 특히 GetItems에 대 한 자세한 내용은 [Get 항목](get-items.md)을 참조 하세요. 

```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="utf-8" />
    <meta http-equiv='cache-control' content='no-cache'>
    <meta http-equiv='expires' content='0'>
    <meta http-equiv='pragma' content='no-cache'>
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta http-equiv="x-content-type-options" content="nosniff">
    <title>CQD Report definition viewer</title>
</head>
<body>    
    <div style="font-size:32pt">CQD Report definition viewer</div>
        <p>ReportSet Id: <input id="reportSetId" /></p>
        <button onclick='loadReportSet()'>Load</button>
        <div id="Report"></div>
    <!-- Third party Libraries -->
    <script src="OpenSourceSoftware/Scripts/jquery-2.1.1.js"></script>

    <script>
        var urlRepositoryApi = 'http://localhost/QoERepositoryService/repository/item/';

        var loadReportSet = function ()
        {
            var reportSetId = document.getElementById('reportSetId').value;

            $.ajax({
                url: urlRepositoryApi + reportSetId,
                data: '',
                type: 'GET',
                async: false,
                contentType: 'application/json;charset=utf-8',
                success: function (data) {
                    var reportSetDiv = document.getElementById('Report');
                    reportSetDiv.innerHTML = '';
                    processReportSetData(reportSetDiv, data);
                },
                error: function (error) {
                    alert('Error getting Report, check that the qoe data service is running and url is correct.');
                }
            });
        };

        var processReportSetData = function (divReportSet, reportSetDef) {
             //show the report set definition like Title, Description, etc
            showReportSetDefinition(divReportSet, reportSetDef);

            //for each Report in the Reportset, get the Report definition from the Repository Service
            for (var i = 0; i < reportSetDef.subItemIds.length; i++)
            {
                //the reportId is in the subItemIds array.  This is not shown in the CQD UI at all
                var reportId = reportSetDef.subItemIds[i];

                var divReport = document.createElement('div');
                divReport.style.margin = '12px';                
                divReportSet.appendChild(divReport);

                //retrieve the report definition with the reportId
                $.ajax({
                    url: urlRepositoryApi + reportId,
                    data: '',
                    type: 'GET',
                    async: false,
                    contentType: 'application/json;charset=utf-8',
                    success: function (reportData) {
                        processReportData(divReport, reportData, reportId);
                    },
                    error: function (error) {
                        alert('Error getting Report ' + reportId.toString() + ', check that the qoe data service is running and url is correct.');
                    }
                });
            }
        };

        //helper function to render the ReportSet definition
        var showReportSetDefinition = function (divReportSet, reportSetDef) {
            var div = document.createElement('div');
            ReportSetDefinition = reportSetDef.content;
            txt = document.createTextNode(ReportSetDefinition);
            div.style.margin = '12px';
            div.appendChild(txt);
            divReportSet.appendChild(div);
        };

        //show the report definition
        var processReportData = function (divReport, reportData, itemId) {
            if (divReport != undefined &amp;&amp; reportData.content != undefined) {
                var Report = JSON.parse(reportData.content);

                var divReportId = document.createElement('div');
                var subItemId = reportData.subItemIds.length > 0 ? reportData.subItemIds[0].toString() : 'none';
                divReportId.innerHTML = 'ItemId: ' + itemId.toString() + ' (' + Report.Title + ') [subItemId:' + subItemId + ']';
                divReport.appendChild(divReportId);

                var divReportDef = document.createElement('div');
                txt = document.createTextNode(JSON.stringify(Report));
                divReportDef.style.margin = '12px';
                divReportDef.appendChild(txt);                            
                divReport.appendChild(divReportDef);
            }
        };
    </script>
</body>
</html>
```

위의 방법을 사용 하면 그림에 있는 것과 같은 웹 페이지가 생성 됩니다 (초기 방문 시 보고서 정의 제외). CQD 포털에서 보고서 집합 ID를 가져옵니다 (예: CQD 포털 URL에서 '/#/' 기호 뒤에 있습니다. 첫 번째 그림에서는 보고서 집합 ID가 3024 이며이 보고서 집합 ID를이 웹 페이지의 입력 섹션에 넣습니다. "로드" 단추를 누르고 보고서 집합의 전체 정의 (측정값, 차원, 필터 목록)를 확인 합니다.

요약에서 보고서/보고서 집합의 전체 정의를 빠르게 가져올 수 있습니다. 단계는 다음과 같습니다.

1. 포털로 이동한 다음 쿼리 편집기를 사용 하 여 보고서를 사용자 지정 합니다 (보고서 위의 "편집" 단추를 클릭 하 여 측정/치수/필터를 편집, 추가, 제거, 보고서 저장).

2. URL ('/#/' sign in URL 뒤의 정수)에서 보고서 집합 ID를 가져옵니다.

3. 예제 2에서 만든이 보고서 정의 웹 페이지를 시작 하 고 보고서 집합 ID를 입력 하 고 데이터 API 호출에서 사용할 보고서 집합의 전체 정의를 검색 합니다.

   **예제 3: 성과 기록표 샘플**

더욱 복잡 한 작업을 위한 시간. 그림과 같은 웹 페이지를 만들려는 경우 더 많은 양의 데이터를 처리할 수 있도록 예제 2에서 생성 된 웹 페이지를 사용 하 여 보고서의 전체 정의를 검색 하는 방법 1을 업데이트 해야 합니다.

이 경우에는 측정 및 치수 목록을 업데이트 해야 합니다. 측정값 및/또는 차원을 추가/편집 하는 방법을 알아내는 방법은 예제 2의 지침에 따라 전체 측정값 및 차원 목록을 비롯 한 전체 보고서 정의를 검색 하는 것입니다. 전체 보고서 정의를 샘플 코드에 연결 합니다. 

다음은 예제 1에서 제공 된 샘플의 성과 기록표 페이지에 액세스 하는 자세한 단계입니다.

1. ' 쿼리 ' 변수에서 측정값을 (를 `[Measures].[Audio Good Streams JPDR Count]` ) `[Measures].[Audio Poor Streams JPDR Count]` and `[Measures].[AudioPoorJPDRPercentage]`에서 (으)로 업데이트 합니다. 

2. 필터를 업데이트 합니다. 예제 1의 필터에 대 한 JSON 데이터에는 차원 `[StartDate].[Month]`에 설정 된 하나의 필터가 있습니다. 필터는 JSON 배열 이므로 필터 목록에 추가 차원을 추가할 수 있습니다. 예를 들어 "currentMonth"에 대 한 유선 통화 내에서 서버 클라이언트를 가져오려면 다음 필터를 사용 해야 합니다.

   ```
   Filters: [
     { DataModelName: '[StartDate].[Month]', Value: currentMonth, Operand: 0 },
    {
        "DataModelName": "[Scenarios].[ScenarioPair]",
         "Caption": " Server-Inside-wired,Client-Inside-wired",
         "Value": "[1]&amp;[0]&amp;[1]&amp;[1]&amp;[Wired]&amp;[Wired]",
         "Operand": 0,
         "UnionGroup": ""
     },

     { DataModelName: '[StreamType].[StreamType]', Caption: "Valid", Value: "[False]", Operand: 0, UnionGroup: "" }
   ],
   ```

   여기서 치수 `[Scenarios].[ScenarioPair]` 는 동등 `[1]&amp;[0]&amp;[1]&amp;[1]&amp;[Wired]&amp;[Wired]`하 게 설정 됩니다. 은 `[Scenario.][ScenarioPair]` 보고서 만들기를 간소화 하기 위해 만든 특수 차원입니다. 이에 해당 하 `[FirstIsServer], [SecondIsServer], [FirstInside], [SecondIsServer], [FirstConnectionType], [SecondConnectionType]`는 6 개의 값이 있습니다. 따라서 시나리오를 정의 하기 위해 6 개의 필터 조합을 사용 하는 대신 1 개의 필터를 사용 하기만 하면 됩니다. 이 예제 `[1]&amp;[0]&amp;[1]&amp;[1]&amp;[Wired]&amp;[Wired]` 에서는 다음을 수행 합니다. 첫 번째는 서버이 고, 두 번째는 서버가 아니고, 두 번째는 내부이 고, 첫 번째 연결 유형은 유선 이며, 두 번째 연결 유형은 유선 이며, " 서버-클라이언트-유선-내부

3. 각 시나리오에 대해 하나의 필터 집합을 만듭니다. 그림에서 성과 기록표의 각 행은 다른 필터가 되며 (치수와 단위는 동일 하 게 유지 됨) 다른 시나리오를 나타냅니다. 

4. AJAX 호출의 결과를 구문 분석 하 여 표의 올바른 위치에 배치 합니다. 이는 대부분 HTML 및 JavaScript 조작 이므로 여기에 세부 정보를 입력 하지 않습니다. 대신 코드는 부록 A에 제공 됩니다.

    > [!NOTE]
    >  CORS (교차 원본 리소스 공유)를 사용 하는 경우 사용자는 "' 액세스 제어 허용 안 함-원본 ' 헤더가 요청한 리소스에 존재 하는 등의 오류가 발생할 수 있습니다. ' Null ' 원본에는 액세스가 허용 되지 않습니다. 이 문제를 해결 하려면 포털이 설치 되어 있는 폴더 아래에 HTML 파일을 배치 합니다 (기본적으로이는 이어야 `%SystemDrive%\Program Files\Skype for Business 2015 CQD\CQD)`함). 그런 다음 URL `http://<servername>/cqd/<html_file_name>`을 사용 하 여 브라우저를 통해 html에 액세스 합니다. (로컬 CQD 대시보드의 기본 URL `http://<servername>/cqd.`) 

### <a name="appendix-a"></a>부록 A

예제 3 (성과 기록표 샘플)의 HTML 코드:

```
<!DOCTYPE html>
<html xmlns="http://www.w3.org/1999/xhtml">
<head>
    <meta charset="utf-8" />
    <meta http-equiv='cache-control' content='no-cache'>
    <meta http-equiv='expires' content='0'>
    <meta http-equiv='pragma' content='no-cache'>
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <title>Scoreboard Sample</title>

    <style>
        .row {
            margin-right: -15px;
            margin-left: -15px;
            display: table-row;
        }
        .col-md-3 {
            width: 25%;
            display: table-cell;
        }
        .col-md-2 {
            width: 16.66666667%;
            display: table-cell;
        }
        .col-md-1 {
            width: 8.33333333%;
            display: table-cell;
        }

    </style>
</head>
<body>    

    <!-- Third party Libraries -->
    <script src="OpenSourceSoftware/Scripts/jquery-2.1.1.js"></script>

    <table id="ScoreCardTable" style="margin:100px">
        <tr>
            <td width="250px" style="text-align: center; font-size: 24px; font-family: 'Segoe UI'; font-weight: lighter; color: white; background-color: #505050">
                <div style="margin:10px">Scoreboard Sample</div>
            </td>
            <td width="1200px">
                <div style="margin:10px;background-color:#D9D9D9" >
                    <div class="row" id="Header" style="font-size:24px;font-family:'Segoe UI';font-weight:lighter;color:white;background-color:#505050">
                        <div class="col-md-3">Poor Call %</div>
                        <div class="col-md-1">Month1</div>
                        <div class="col-md-1">Month2</div>
                        <div class="col-md-1">Month3</div>
                        <div class="col-md-1">Month4</div>
                        <div class="col-md-1">Month5</div>
                        <div class="col-md-1">Month6</div>
                    </div>                    
                    <div class="row"><div class="col-md-3" style="font-weight:bold">Wired</div></div>
                    <div class="row" id="SS"><div class="col-md-3">Server-Server</div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div></div>
                    <div class="row" id="SWI"><div class="col-md-3">Server-Client (inside)</div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div></div>
                    <div class="row" id="SWO"><div class="col-md-3">Server-Client (outside)</div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div></div>
                    <div class="row" id="WWI"><div class="col-md-3">Client-Client (inside)</div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div></div>
                    <div class="row" id="WIWO"><div class="col-md-3">Client-Client (outside)</div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div></div>
                    <div class="row"><div class="col-md-3" style="font-weight:bold">Wireless</div></div>
                    <div class="row" id="SWFI"><div class="col-md-3">Server-Client (inside)</div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div></div>
                    <div class="row" id="SWFO"><div class="col-md-3">Server-Client (outside)</div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div></div>
                    <div class="row" id="WFIWFI"><div class="col-md-3">Client-Client (inside)</div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div></div>
                    <div class="row" id="WFOWFO"><div class="col-md-3">Client-Client (outside)</div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div></div>
                    <div class="row"><div class="col-md-3" style="font-weight:bold">Mobile/Broadband</div></div>
                    <div class="row" id="SMP"><div class="col-md-3">Server-MobilePhone</div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div></div>
                    <div class="row" id="SMBB"><div class="col-md-3">Server-MobileBroadBand</div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div></div>
                    <div class="row"><div class="col-md-3" style="font-weight:bold">Lync Web App</div></div>
                    <div class="row" id="SLWA"><div class="col-md-3">Server-Client (inside &amp; outside)</div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div></div>
                </div>
            </td>
        </tr>
        <tr>
            <td><br /></td>
        </tr>
    </table>

    <script>

        $(function () {
            var month_names_short = ['NAM', 'Jan', 'Feb', 'Mar', 'Apr', 'May', 'Jun', 'Jul', 'Aug', 'Sep', 'Oct', 'Nov', 'Dec'];
            var currentMonth = '2015-3';

            //update the header with the month names
            var row = document.getElementById('Header');
            var numMonthsToShow = 6;
            for (var m = numMonthsToShow-1; m >= 0; m--) {
                var dateSplit = currentMonth.split('-');
                var monthInt = parseInt(dateSplit[1]);
                var yearInt = parseInt(dateSplit[0]);
                monthInt = monthInt - m;
                if (monthInt < 1)
                {
                    monthInt += 12;
                    yearInt--;
                }
                row.children[numMonthsToShow-m].innerHTML = month_names_short[monthInt];
            }

            var queries = [
            {
                Label: "Server-Server",
                ID: "SS",
                Query:
                {
                  Dimensions: [{ DataModelName: '[StartDate].[Month]'}],
                  Filters: [
                      {
                          "DataModelName": "[Scenarios].[ScenarioPair]",
                          "Caption": " Server-Inside-wired,Server-Inside-wired",
                          "Value": "[1]&amp;[1]&amp;[1]&amp;[1]&amp;[Wired]&amp;[Wired]",
                          "Operand": 0,
                          "UnionGroup": ""
                      },
                      { DataModelName: '[StartDate].[Month]', Value: currentMonth, Operand: 0 },
                      { DataModelName: '[StreamType].[StreamType]', Caption: "Valid", Value: "[False]", Operand: 0, UnionGroup: ""}
                  ],
                  Measurements: [{ DataModelName: '[Measures].[AudioPoorJPDRPercentage]'}],
                  Trend: { EnableTrend: true, SpanCount: numMonthsToShow, TrendDate: currentMonth, Type: 0 }
                 }
            },
            {
                Label: "Server-Client (inside)",
                ID: "SWI",
                Query:
                {
                  Dimensions: [{ DataModelName: '[StartDate].[Month]' }],
                  Filters: [
                      {
                          "DataModelName": "[Scenarios].[ScenarioPair]",
                          "Caption": " Server-Inside-wired,Client-Inside-wired",
                          "Value": "[1]&amp;[0]&amp;[1]&amp;[1]&amp;[Wired]&amp;[Wired]",
                          "Operand": 0,
                          "UnionGroup": ""
                      },
                      { DataModelName: '[StartDate].[Month]', Value: currentMonth, Operand: 0 },
                      { DataModelName: '[StreamType].[StreamType]', Caption: "Valid", Value: "[False]", Operand: 0, UnionGroup: "" }
                  ],
                  Measurements: [{ DataModelName: '[Measures].[AudioPoorJPDRPercentage]' }],
                  Trend: { EnableTrend: true, SpanCount: numMonthsToShow, TrendDate: currentMonth, Type: 0 }
                }
            },
            {
                Label: "Server-Client (outside)",
                ID: "SWO",
                Query:
                {
                  Dimensions: [{ DataModelName: '[StartDate].[Month]' }],
                  Filters: [
                      {
                          "DataModelName": "[Scenarios].[ScenarioPair]",
                          "Caption": " Server-Inside-wired,Client-Outside-wired",
                          "Value": "[1]&amp;[0]&amp;[1]&amp;[0]&amp;[Wired]&amp;[Wired]",
                          "Operand": 0,
                          "UnionGroup": ""
                      },
                      { DataModelName: '[StartDate].[Month]', Value: currentMonth, Operand: 0 },
                      { DataModelName: '[StreamType].[StreamType]', Caption: "Valid", Value: "[False]", Operand: 0, UnionGroup: "" }
                  ],
                  Measurements: [{ DataModelName: '[Measures].[AudioPoorJPDRPercentage]' }],
                  Trend: { EnableTrend: true, SpanCount: numMonthsToShow, TrendDate: currentMonth, Type: 0 }
                 }
            },
            {
                Label: "Client-Client (inside)",
                ID: "WWI",
                Query:
                {
                    Dimensions: [{ DataModelName: '[StartDate].[Month]' }],
                    Filters: [
                        {
                            "DataModelName": "[Scenarios].[ScenarioPair]",
                            "Caption": " Client-Inside-wired,Client-Inside-wired",
                            "Value": "[0]&amp;[0]&amp;[1]&amp;[1]&amp;[Wired]&amp;[Wired]",
                            "Operand": 0,
                            "UnionGroup": ""
                        },
                        { DataModelName: '[StartDate].[Month]', Value: currentMonth, Operand: 0 },
                        { DataModelName: '[StreamType].[StreamType]', Caption: "Valid", Value: "[False]", Operand: 0, UnionGroup: "" }
                    ],
                    Measurements: [{ DataModelName: '[Measures].[AudioPoorJPDRPercentage]' }],
                    Trend: { EnableTrend: true, SpanCount: numMonthsToShow, TrendDate: currentMonth, Type: 0 }
                }
            }
            ,
            {
                Label: "Client-Client (outside)",
                ID: "WIWO",
                Query:
                {
                    Dimensions: [{ DataModelName: '[StartDate].[Month]' }],
                    Filters: [
                        {
                          "DataModelName": "[Scenarios].[ScenarioPair]",
                          "Caption": "Client-Outside-Wired,Client-Outside-Wired",
                          "Value": "[0]&amp;[0]&amp;[0]&amp;[0]&amp;[Wired]&amp;[Wired]",
                          "Operand": 0,
                          "UnionGroup": ""
                        },
                        { DataModelName: '[StartDate].[Month]', Value: currentMonth, Operand: 0 },
                        { DataModelName: '[StreamType].[StreamType]', Caption: "Valid", Value: "[False]", Operand: 0, UnionGroup: "" }
                    ],
                    Measurements: [{ DataModelName: '[Measures].[AudioPoorJPDRPercentage]' }],
                    Trend: { EnableTrend: true, SpanCount: numMonthsToShow, TrendDate: currentMonth, Type: 0 }
                }
            },
            {
                Label: "Server-Client (inside)",
                ID: "SWFI",
                Query:
                {
                    Dimensions: [{ DataModelName: '[StartDate].[Month]' }],
                    Filters: [
                        {
                            "DataModelName": "[Scenarios].[ScenarioPair]",
                            "Caption": " Server-Inside-wired,Client-Inside-wifi",
                            "Value": "[1]&amp;[0]&amp;[1]&amp;[1]&amp;[Wired]&amp;[Wifi]",
                            "Operand": 0,
                            "UnionGroup": ""
                        },
                        { DataModelName: '[StartDate].[Month]', Value: currentMonth, Operand: 0 },
                        { DataModelName: '[StreamType].[StreamType]', Caption: "Valid", Value: "[False]", Operand: 0, UnionGroup: "" }
                    ],
                    Measurements: [{ DataModelName: '[Measures].[AudioPoorJPDRPercentage]' }],
                    Trend: { EnableTrend: true, SpanCount: numMonthsToShow, TrendDate: currentMonth, Type: 0 }
                }
            },
            {
                Label: "Server-Client (outside)",
                ID: "SWFO",
                Query:
                {
                    Dimensions: [{ DataModelName: '[StartDate].[Month]' }],
                    Filters: [
                         {
                             "DataModelName": "[Scenarios].[ScenarioPair]",
                             "Caption": " Server-Inside-wired,Client-Outside-wifi",
                             "Value": "[1]&amp;[0]&amp;[1]&amp;[0]&amp;[Wired]&amp;[Wifi]",
                             "Operand": 0,
                             "UnionGroup": ""
                         },
                        { DataModelName: '[StartDate].[Month]', Value: currentMonth, Operand: 0 },
                        { DataModelName: '[StreamType].[StreamType]', Caption: "Valid", Value: "[False]", Operand: 0, UnionGroup: "" }
                    ],
                    Measurements: [{ DataModelName: '[Measures].[AudioPoorJPDRPercentage]' }],
                    Trend: { EnableTrend: true, SpanCount: numMonthsToShow, TrendDate: currentMonth, Type: 0 }
                }
            },
            {
                Label: "Client-Client (inside)",
                ID: "WFIWFI",
                Query:
                {
                    Dimensions: [{ DataModelName: '[StartDate].[Month]' }],
                    Filters: [
                        {
                            "DataModelName": "[Scenarios].[ScenarioPair]",
                            "Caption": " Client-Inside-Wifi,Client-Inside-Wifi",
                            "Value": "[0]&amp;[0]&amp;[1]&amp;[1]&amp;[Wifi]&amp;[Wifi]",
                            "Operand": 0,
                            "UnionGroup": ""
                        },
                        { DataModelName: '[StartDate].[Month]', Value: currentMonth, Operand: 0 },
                        { DataModelName: '[StreamType].[StreamType]', Caption: "Valid", Value: "[False]", Operand: 0, UnionGroup: "" }
                    ],
                    Measurements: [{ DataModelName: '[Measures].[AudioPoorJPDRPercentage]' }],
                    Trend: { EnableTrend: true, SpanCount: numMonthsToShow, TrendDate: currentMonth, Type: 0 }
                }
            },
            {
                Label: "Client-Client (outside)",
                ID: "WFOWFO",
                Query:
                {
                    Dimensions: [{ DataModelName: '[StartDate].[Month]' }],
                    Filters: [
                        {
                          "DataModelName": "[Scenarios].[ScenarioPair]",
                          "Caption": "Client-Outside-Wifi,Client-Outside-Wifi",
                          "Value": "[0]&amp;[0]&amp;[0]&amp;[0]&amp;[Wifi]&amp;[Wifi]",
                          "Operand": 0,
                          "UnionGroup": ""
                        },
                        { DataModelName: '[StartDate].[Month]', Value: currentMonth, Operand: 0 },
                        { DataModelName: '[StreamType].[StreamType]', Caption: "Valid", Value: "[False]", Operand: 0, UnionGroup: "" }
                    ],
                    Measurements: [{ DataModelName: '[Measures].[AudioPoorJPDRPercentage]' }],
                    Trend: { EnableTrend: true, SpanCount: numMonthsToShow, TrendDate: currentMonth, Type: 0 }
                }
            },
            {
                Label: "Server-MobilePhone",
                ID: "SMP",
                Query:
                {
                    Dimensions: [{ DataModelName: '[StartDate].[Month]' }],
                    Filters: [
                        {"DataModelName": "[First Is Server].[Agent]","Caption": "Server","Value": "[1]","Operand": 0,"UnionGroup": ""},
                        {"DataModelName": "[Second User Agent].[User Agent Type]","Caption": "AndroidLync | iPhoneLync | WPLync","Value": "[AndroidLync],[iPhoneLync],[WPLync]","Operand": 0,"UnionGroup": ""},
                        { DataModelName: '[StartDate].[Month]', Value: currentMonth, Operand: 0 },
                    ],
                    Measurements: [{ DataModelName: '[Measures].[AudioPoorJPDRPercentage]' }],
                    Trend: { EnableTrend: true, SpanCount: numMonthsToShow, TrendDate: currentMonth, Type: 0 }
                }
            },
            {
                Label: "Server-MobileBroadBand",
                ID: "SMBB",
                Query:
                {
                    Dimensions: [{ DataModelName: '[StartDate].[Month]' }],
                    Filters: [
                        {"DataModelName": "[Second Network Connection Type].[Network Connection Detail]","Caption": "MobileBB","Value": "[MobileBB]","Operand": 0,"UnionGroup": ""},
                        {"DataModelName": "[First Is Server].[Agent]","Caption": "Server","Value": "[1]","Operand": 0,"UnionGroup": ""},
                        {"DataModelName": "[Second Is Server].[Agent]","Caption": "Client ","Value": "[0]","Operand": 0,"UnionGroup": ""},
                        { DataModelName: '[StartDate].[Month]', Value: currentMonth, Operand: 0 }                       
                    ],
                    Measurements: [{ DataModelName: '[Measures].[AudioPoorJPDRPercentage]' }],
                    Trend: { EnableTrend: true, SpanCount: numMonthsToShow, TrendDate: currentMonth, Type: 0 }
                }
            },
            {
                Label: "Server-LWA",
                ID: "SLWA",
                Query:
                {
                    Dimensions: [{ DataModelName: '[StartDate].[Month]' }],
                    Filters: [
                        {"DataModelName": "[First Is Server].[Agent]","Caption": "Server","Value": "[1]","Operand": 0,"UnionGroup": ""},
                        {"DataModelName": "[Second User Agent].[User Agent Type]","Caption": "LWA","Value": "[LWA]","Operand": 0,"UnionGroup": ""},
                        { DataModelName: '[StartDate].[Month]', Value: currentMonth, Operand: 0 }                       
                    ],
                    Measurements: [{ DataModelName: '[Measures].[AudioPoorJPDRPercentage]' }],
                    Trend: { EnableTrend: true, SpanCount: numMonthsToShow, TrendDate: currentMonth, Type: 0 }
                }
            }

            ];

            //get the overall corpnet data
            for (var i = 0; i < queries.length; i++) {
                $.ajax({

                    url: 'http://localhost/QoEDataService/RunQuery',
                    data: JSON.stringify(queries[i].Query),
                    type: 'POST',
                    async: false,
                    withCredentials: true,
                    contentType: 'application/json;charset=utf-8',
                    success: function (data) {

                        //find the table row corresponding to the name of this query
                        var row = document.getElementById(queries[i].ID);

                        //update the values for each month
                        for (var m = 0; m < data.DataResult.length; m++)
                        {
                            row.children[m + 1].innerHTML = data.DataResult[m][1].toFixed(2).toString();
                        }

                    },
                    error: function (error) {
                        var row = document.getElementById(queries[i].ID);
                        row.children[1].innerHTML = 'error';
                    }
                });
            }
        });
    </script>
</body>
</html>
```
