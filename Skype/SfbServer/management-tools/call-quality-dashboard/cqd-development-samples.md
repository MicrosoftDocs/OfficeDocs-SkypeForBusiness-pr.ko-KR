---
title: CQD 개발 샘플
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 8ca9bf7a-2d6f-48d5-a821-531009726525
description: '요약: 통화 품질 대시보드에 대한 자습서 및 개발 샘플을 검토합니다. 통화 품질 대시보드는 통화 품질 대시보드를 위한 비즈니스용 Skype 서버.'
ms.openlocfilehash: b0b4811e38d50f871e023757220a2a3f0108be349c55eaf78e39ab243954c5dd
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54331296"
---
# <a name="cqd-development-samples"></a>CQD 개발 샘플

**요약:** 통화 품질 대시보드에 대한 자습서 및 개발 샘플을 검토합니다. 통화 품질 대시보드는 통화 품질 대시보드를 위한 비즈니스용 Skype 서버.

이 문서에서는 CQD(통화 품질 대시보드)에 대한 개발에 대한 자습서 및 예제를 제공합니다.

## <a name="call-quality-dashboard-cqd-development-samples"></a>CQD(통화 품질 대시보드) 개발 샘플

자습서: CQD 데이터 서비스 및 리포지토리 서비스 API를 사용하여 사용자 지정된 보고서 프레젠테이션을 구축합니다.

### <a name="introduction-to-cqd"></a>CQD 소개

CQD는 모든 배포에 대해 집계된 통화 품질 정보에 빠르고 쉽게 액세스할 비즈니스용 Skype 서버 있습니다. CQD는 QoE 보관 데이터베이스, 큐브 및 포털의 세 가지 구성 요소로 구성됩니다. 포털은 기본 프레젠테이션 계층으로, 다음 세 가지 구성 요소로 추가로 나눌 수 있습니다.

1. 데이터 서비스는 의 [CQD(통화](data-api.md)품질 대시보드)를 통해 인증된 사용자가 액세스할 수 비즈니스용 Skype 서버.

2. 리포지토리 서비스는 에서 CQD(통화 품질 대시보드용 리포지토리 [API)를](repository-api.md)통해 인증된 사용자가 액세스할 수 비즈니스용 Skype 서버.

3. 웹 포털 - CQD 사용자가 보고 상호 작용하는 HTML5 기반 인터페이스입니다. 이 액세스는 인증된 사용자가 액세스할 수 있습니다.

웹 포털에 표시된 보고서는 "보고서 집합"으로 그룹화됩니다. 그림에는 두 개의 보고서가 있는 보고서 집합이 표시되어 있습니다. 아래 대시보드의 각 보고서에는 다양한 필터가 적용된 양호한 통화 수, 불량 통화 및 몇 개월 동안의 불량 통화 비율에 대한 쿼리 결과가 표시됩니다. 

![CQD 샘플 보고서](../../media/9e0723f7-f850-4d11-9ecd-7e8e013a8bed.png)

CQD는 CQM(통화 품질 방법론)에 따라 만들어지기 때문에 기본 보고서 집합은 CQM에서 도입된 조사 흐름에 맞게 디자인됩니다. 또한 사용자는 자신의 요구에 따라 사용자 지정 보고서를 편집하거나 만들 수 있습니다. 그러나 데이터를 시각화하는 방법이 여러 가지이기 때문에 CQD에서 제공하는 시각화는 모든 사용자의 요구를 완전히 충족하지 않을 수 있습니다. 이러한 경우 사용자는 데이터 API 및 리포지토리 API를 활용하여 사용자 지정 보고서 페이지를 만들 수 있습니다. 이 자습서에서는 일련의 예제를 진행합니다.

### <a name="how-the-dashboard-consumes-the-data-service"></a>대시보드에서 데이터 서비스를 사용하는 방법

CQD 홈페이지(예: 를 검색할 때 인증된 사용자 및 권한이 부여된 사용자에 대한 보고서 집합 및 해당 보고서는 리포지토리 서비스에서 http://localhost/cqd) 검색됩니다. 전체 URL은 보고서 집합 ID와 연도-월에서 생성됩니다. 보고서 집합 ID는 URL에서 '/#/' 섹션 다음에 오는 정수 번호로, 기본적으로 슬래시 후 보고서 집합 ID의 끝에 현재 연도-월이 추가됩니다. 보고서 정의는 JSON 형식으로 저장되고 리포지토리 서비스에서 검색되면 데이터 서비스에 대한 입력으로 사용됩니다. 데이터 서비스는 입력을 기반으로 MDX(Multi-Dimension Expressions) 쿼리를 생성한 다음 큐브에 대해 이러한 MDX 쿼리를 실행하여 각 보고서의 데이터를 검색합니다. 

### <a name="building-customized-reports"></a>사용자 지정된 보고서 작성

CQD는 이미 보고서를 사용자 지정하는 데 많은 유연성이 있지만 사용자가 CQD로 만든 여러 보고서에서 데이터를 집계해야 하는 상황이 있을 수 있습니다. 예를 들어 테이블에서 가능한 모든 유선 통화 조합의 불량 통화 비율(그림과 같은 결과)을 표시하는 보고서를 만들어야 할 수 있습니다.

![CQD 테이블](../../media/ef19d535-5da6-44a9-91f6-1ed3f30b96f1.png)

CQD에서 제공하는 포털을 사용하여 사용자는 여러 보고서로 이동하여 각 보고서에 대해 불량 통화율을 추출하고 기록해야 하며, 수집해야 하는 데이터 포인트가 많은 경우 번거로우면 번거로우게 될 수 있습니다. 데이터 API는 데이터 서비스(예: AJAX 호출을 통해)에서 데이터를 검색하여 프로그래밍 방식으로 이 작업을 수행할 수 있는 방법을 제공합니다. 

 **예제 1: 간단한 보고서 샘플**

먼저 간단한 예를 들어 보겠습니다. 그림과 같이 HTML 페이지에 Audio Good Stream 및 Audio Bad stream count of February 2015를 표시하려면 다음을 참조하세요.

![CQD 예제 보고서](../../media/f0e4e61f-1fa5-4d69-b192-f19e9612bf1c.png)

적절한 매개 변수를 사용하여 데이터 서비스로 호출을 보내고 쿼리 결과를 HTML 테이블에 표시해야 합니다. 다음은 JavaScript 코드의 샘플입니다.

```javascript        
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

이 예제는 다음 세 단계로 추가로 해체할 수 있습니다.

1. 쿼리를 생성합니다(예제에서는 'query' 변수에 정의되어 있습니다. 쿼리는 다음 데이터를 포함하는 JSON 개체로 정의됩니다.

   a. 0개 이상의 차원 각 차원은 DataModelName으로 표시됩니다.

   b. 필터가 0개 이상입니다. 각 필터에는

   - DataModelName(필터 집합을 사용할 차원)

   - 값(피연산자와 비교할 값)입니다.

   - 피연산자(비교 유형, 0은 "같음"을 의미)

     c. 하나 이상의 측정값

2. AJAX 호출을 통해 데이터 서비스로 쿼리를 전송합니다. 다음 요청 매개 변수를 제공해야 합니다.

   a. url([ServerName]/http:///QoEDataService/RunQuery로 설정해야 합니다.

   b. 데이터('query' 변수에 정의된 JSON 개체의 문자열 표현) 데이터 서비스는 쿼리 결과를 성공을 위해 콜백 함수의 매개 변수로 반환합니다.

   c. type(QoEDataService의 경우 RunQuery는 'POST' 요청만 수락합니다.)

   d. async(AJAX 호출이 동기인지 비동기인지를 나타내는 플래그)

   e. contentType("application/json"으로 해야 합니다.)

   f. success(AJAX 호출이 성공적으로 완료된 경우의 콜백 함수)

   g. error(AJAX 호출이 실패할 때의 오류 처리 함수)입니다.

3. 데이터를 HTML의 div 요소에 넣습니다(코드의 예제에서는 AJAX 요청이 성공적으로 완료된 후 익명 함수 호출을 통해 수행).

JavaScript 코드를 HTML 페이지로 묶면 그림에 표시된 보고서와 같은 보고서가 페이지에 표시됩니다. 전체 html은 다음과 같습니다.

```javascript
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

지금까지 보고서는 여전히 매우 간단합니다. 사용자는 측정값, 차원 또는 필터를 더 추가하여 보고서를 사용자 지정할 수 있습니다. 예를 들어 AppSharing 불량 통화 비율을 표시하려는 경우 AppSharing과 관련한 새 측정을 추가해야 합니다. 모든 TCP 호출 v.s를 표시하려는 경우 UDP 통화, 교통 유형에 대한 새 차원을 추가해야 합니다. 특정 건물 내에서 불량 통화 수를 표시하려면 새 필터를 추가하여 해당 건물과의 통화를 선택해야 합니다.

 **예제 2: 보고서 정의 샘플**

쿼리를 작성할 때 측정/차원/필터의 전체 목록과 해당 값을 작성하는 방법을 알아내기 어려울 수 있습니다. 이 경우 포털로 이동하여 보고서 편집기를 사용하여 보고서를 작성한 다음 보고서 정의의 JSON 문자열을 본 다음 정의를 사용자 지정 보고서에 복사할 수 있습니다. 

이 예제에서는 사용자가 기존 보고서 집합(또는 보고서)의 ID를 입력하고 웹 페이지에 보고서 집합 또는 보고서의 정의를 표시하는 그림에 표시된 웹 페이지와 같은 웹 페이지를 작성합니다. 그런 다음 사용자는 예제 1에 표시된 코드와 비슷한 코드에 각 보고서의 JSON 문자열을 연결하고 사용자가 원하는 사용자 지정 보고서를 구성할 수 있습니다. 

![CQD 예제](../../media/01c45c23-c4d2-47b8-819f-0888cf71260f.png)

보고서 정의 뷰어 도구를 만들기 위해 리포지토리 서비스로 호출을 보내 원하는 모든 보고서 집합의 정의에 대한 JSON 문자열 표현을 검색해야 합니다. 리포지토리 API는 주어진 보고서 집합 ID에 따라 보고서 집합 정의를 반환합니다. 

간단한 예는 다음과 같습니다. 코드에는 리포지토리 서비스에 쿼리를 보내 해당 식별자를 기반으로 리포지토리 항목의 내용을 구하는 간단한 예제인 블록이 포함되어 있습니다. 또한 코드의 다음 부분(processReportSetData 메서드)에서는 AJAX 호출을 보내 보고서 집합 내의 각 보고서에 대한 정의를 얻습니다. CQD 웹 포털의 ID는 보고서 집합의 ID이기 때문에 AJAX 호출은 보고서 집합 항목을 반환합니다. 리포지토리 API 및 특히 GetItems에 대한 자세한 내용은 항목 Get 에서 [찾을 수 있습니다.](get-items.md) 

```html
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

위의 결과로 그림에 있는 웹 페이지와 같은 웹 페이지가 표시됩니다(초기 방문 시 보고서 정의가 없는 경우). CQD 포털에서 보고서 집합 ID를 다운로드합니다(예: CQD 포털 URL에 로그인한 후입니다. 첫 번째 그림에서 보고서 집합 ID는 3024입니다. 이 보고서 집합 ID를 이 웹 페이지의 입력 섹션에 넣습니다. "로드" 단추를 누르고 보고서 집합의 전체 정의(측정값, 차원, 필터 목록)를 봐야 합니다.

요약하면 보고서/보고서 집합의 전체 정의를 빠르게 얻을 수 있습니다. 그 단계는 다음과 같습니다.

1. 포털로 이동한 후 쿼리 편집기를 사용하여 보고서를 사용자 지정합니다. 보고서 위에 있는 "편집" 단추를 클릭하여 측정값/차원/필터를 편집, 추가, 제거한 다음 보고서를 저장합니다.

2. URL에서 보고서 집합 ID(URL에 로그인한 후의 정수)를 확인합니다.

3. 예제 2에서 만든 이 보고서 정의 웹 페이지를 시작하고 보고서 집합 ID를 입력하고 데이터 API 호출에 사용할 보고서 집합의 전체 정의를 검색합니다.

   **예제 3: Scorecard sample**

더 복잡한 작업의 시간입니다. 그림과 같은 웹 페이지를 만들면 어떻게 하나요? 많은 양의 데이터를 처리할 수 있도록 예제 1(예제 2에서 생성된 웹 페이지를 사용하여 보고서의 전체 정의를 검색)을 업데이트해야 합니다.

이 경우 측정값 및 차원 목록을 업데이트해야 합니다. 측정값 및/또는 차원을 추가/편집하는 방법을 알아낼 수 있는 방법은 예제 2의 지침을 따르고 전체 측정값 및 차원 목록을 포함하여 전체 보고서 정의를 검색하는 것입니다. 전체 보고서 정의를 예제 코드에 연결합니다. 

다음은 예제 1에 제공된 샘플에서 그림의 점수 기록표 페이지로 이동하는 세부 단계입니다.

1. 'query' 변수의 측정값을 에서 로  `[Measures].[Audio Good Streams JPDR Count]` `[Measures].[Audio Poor Streams JPDR Count]` `[Measures].[AudioPoorJPDRPercentage]` 업데이트합니다. 

2. 필터를 업데이트합니다. 예제 1의 Filters에 대한 JSON 데이터에는 차원 에 설정된 필터가 하나  `[StartDate].[Month]` 있습니다. Filters는 JSON 배열이기 때문에 필터 목록에 차원을 더 추가할 수 있습니다. 예를 들어 "currentMonth"에 대한 유선 호출 내부에서 서버 클라이언트를 얻습니다. 다음과 같은 필터가 필요합니다.

   ```javascript
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

   여기서  `[Scenarios].[ScenarioPair]` 차원은 으로 `[1]&amp;[0]&amp;[1]&amp;[1]&amp;[Wired]&amp;[Wired]` 설정됩니다. 보고서 만들기를 단순화하기 위해 만들어진 특수  `[Scenario.][ScenarioPair]` 차원입니다. 에 해당하는 6개의 값이 `[FirstIsServer], [SecondIsServer], [FirstInside], [SecondIsServer], [FirstConnectionType], [SecondConnectionType]` 있습니다. 따라서 6개 필터를 조합하여 시나리오를 정의하는 대신 필터 1개만 사용하면 됩니다. 이 예제에서 값은 다음과 같은 시나리오로 변환됩니다. 즉, 첫 번째는 서버가 아니고, 두 번째는 서버가 아니고, 두 번째는 내부에, 첫 번째 연결 유형은 유선, 두 번째 연결 유형은  `[1]&amp;[0]&amp;[1]&amp;[1]&amp;[Wired]&amp;[Wired]` "Server-Client-Inside Wired"의 정확한 정의인 유선입니다.

3. 시나리오당 하나의 필터 집합을 만들 수 있습니다. 그림에서 각 행은 다른 필터가 될 다른 시나리오를 나타내며 차원과 측정값은 동일하게 유지됩니다. 

4. AJAX 호출의 결과를 구문 분석하여 테이블의 올바른 위치에 배치합니다. 이는 대부분 HTML 및 JavaScript 조작이기 때문에 여기에서는 세부 정보로 이동하지 않습니다. 대신 부록 A에 코드가 제공됩니다.

    > [!NOTE]
    >  CORS(원본 간 리소스 공유)를 사용하도록 설정하면 요청된 리소스에 '액세스-제어-허용-원점' 헤더가 없음과 같은 오류가 발생할 수 있습니다. 따라서 원점 'null'이(가) 액세스가 허용되지 않습니다." 이 문제를 해결하려면 포털이 설치된 폴더 아래에 HTML 파일을 배치합니다(기본적으로 `%SystemDrive%\Program Files\Skype for Business 2015 CQD\CQD)` 입니다. 그런 다음 URL을 사용하여 브라우저를 통해 html에  `http://<servername>/cqd/<html_file_name>` 액세스합니다. (로컬 CQD 대시보드의 기본 URL은  `http://<servername>/cqd.` ) 

### <a name="appendix-a"></a>부록 A

예제 3에 대한 HTML 코드(Scorecard 샘플):

```html
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
