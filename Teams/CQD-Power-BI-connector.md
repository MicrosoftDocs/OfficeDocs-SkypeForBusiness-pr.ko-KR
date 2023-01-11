---
title: CQD 쿼리 템플릿을 사용하도록 Power BI 커넥터 설치
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: siunies
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
search.appverid: MET150
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
description: CQD(통화 품질 대시보드) 쿼리 템플릿을 사용하도록 Power BI 커넥터 설치
ms.openlocfilehash: 534103fc2bec48566a1d0a57eeb390ed6ae0606c
ms.sourcegitcommit: 66d8e3d7a29a03c5deba9780964bc03f6587017f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/11/2023
ms.locfileid: "69774753"
---
# <a name="install-microsoft-call-quality-connector-for-power-bi-to-use-call-quality-dashboard-query-templates"></a>통화 품질 대시보드 쿼리 템플릿을 사용하도록 Power BI용 Microsoft 통화 품질 커넥터 설치

Microsoft Teams CQD(통화 품질 대시보드)용 Power BI 쿼리 템플릿(PBIX 파일)을 사용하려면 [다운로드](https://www.microsoft.com/download/details.aspx?id=102291)에 포함된 *MicrosoftCallQuality.pqx* 파일을 사용하여 Power BI용 Microsoft 통화 품질 커넥터를 설치해야 합니다.

이러한 템플릿에 대해 알아보 [려면 Power BI를 사용하여 Teams용 CQD 데이터 분석을](CQD-Power-BI-query-templates.md) 참조하세요.

Power BI 보고서에 액세스할 수 있는 올바른 [CQD 액세스 역할이](./turning-on-and-using-call-quality-dashboard.md#assign-admin-roles-for-access-to-cqd) 있는지 확인합니다.

> [!NOTE]
> Microsoft Call Quality 커넥터는 Power BI에서 DirectQuery만 지원합니다. 가져오기 모드는 지원되지 않습니다. 

## <a name="installation"></a>설치

사용자 지정 커넥터를 설치하고 커넥터 사용을 사용하도록 보안을 조정하는 프로세스는 [Power BI 설명서](/power-bi/desktop-connector-extensibility)에 자세히 설명되어 있습니다. 간단히 하기 위해 간단한 설명은 다음과 같습니다.

1. 컴퓨터에 *Documents\]\\ Power BI Desktop\\ Custom Connectors 폴더가 이미\[* 있는지 확인합니다. 그렇지 않은 경우 이 폴더를 만듭니다. <sup>1</sup>

2. 커넥터 파일( *\*.mez* 또는 *\*.pqx* 파일)을 다운로드하여 *사용자 지정 커넥터* 디렉터리에 배치합니다.

3. **커넥터 파일이 *\*.mez* 파일인 경우** [사용자 지정 커넥터 설정 설명서](/power-bi/desktop-connector-extensibility#data-extension-security)에 설명된 대로 보안 설정도 조정해야 합니다.

새 버전의 Microsoft Call Quality 커넥터가 릴리스된 경우 *사용자 지정 커넥터* 디렉터리의 이전 커넥터 파일을 새 파일로 바꿉니다.

## <a name="setup"></a>설치

보고서를 작성하고 쿼리를 실행하려면 먼저 CQD 데이터 원본에 연결해야 합니다. 연결하려면 아래 단계를 수행합니다.

1. Power BI Desktop 홈 탭에서 *데이터 가져오기* 를 클릭합니다.

    ![Power BI 커넥터에서 데이터를 가져옵니다.](media/CQD-power-bi-connector1-resize.png)

2. 이 시점에서 *데이터 가져오기* 창이 나타납니다. *온라인 서비스* 로 이동한 다음 *Microsoft 통화 품질(베타)* 을 선택하고 *연결을* 누릅니다.

    ![Power BI 커넥터의 Microsoft 통화 품질입니다.](media/CQD-power-bi-connector2-resize.png)

3. 다음에 로그인하라는 메시지가 표시됩니다. 통화 품질 대시보드에 사용하는 것과 동일한 자격 증명을 사용합니다. <sup>2</sup>

4. 다음 프롬프트는 두 *데이터 연결 모드* 간의 옵션을 제공합니다. *DirectQuery를* 선택하고 *확인을* 누릅니다.

5. 마지막으로 통화 품질 대시보드에 대한 전체 데이터 모델을 보여 주는 최종 프롬프트가 표시됩니다. 이 시점에서는 데이터가 표시되지 않으며 CQD에 대한 데이터 모델만 표시됩니다. *로드* 를 선택하여 설치 프로세스를 완료합니다.

6. 이 시점에서 Power BI는 데이터 모델을 창의 오른쪽에 로드합니다. 그렇지 않으면 페이지는 비어 있으며 기본적으로 쿼리가 로드되지 않습니다. **쿼리를** 빌드하고 데이터를 반환하려면 아래 쿼리 작성을 진행합니다.

이 설정 프로세스 중에 단계가 명확하지 않은 경우 프로세스에 대한 자세한 설명은 [빠른 시작: Power BI Desktop 데이터에 연결에서](/power-bi/desktop-quickstart-connect-to-data) 찾을 수 있습니다.

## <a name="building-queries"></a>쿼리 빌드

설정이 완료되면 *필드* 창에 수백 개의 차원 및 측정값 로드 이름이 표시됩니다. 여기에서 실제 쿼리를 생성하는 것은 간단합니다. 쿼리에 대해 원하는 차원과 측정값을 선택한 다음 끌어서 페이지로 놓습니다. 다음은 간단한 예제와 함께 보다 자세한 설명입니다.

1. 시각화 창에서 사용할 *시각화를* 선택합니다. 해당 시각화의 빈 버전이 페이지에 표시됩니다. 이 예제에서는 *테이블* 시각화를 사용합니다.

    ![Power BI 커넥터의 시각화 창.](media/CQD-power-bi-connector3-resize.png)

2. 쿼리에 사용할 차원 및 측정값(해당 이름으로 집계 기호로 표시됨)을 결정한 다음, 수동으로 선택하고 검은색 시각화로 끌어옵니다. 또는 시각화 옵션 아래의 *값* 필드로 끌어옵니다.

    ! Power BI 커넥터의 시각화 쿼리입니다.] (미디어/CQD-power-bi-connector4-resize2.png)

    > [!IMPORTANT]
    > 호출 품질 대시보드에는 쿼리를 실행하기 위한 측정값이 필요합니다. 쿼리에 측정값을 추가하지 않으면 쿼리가 실패합니다.

3. 다음으로 필터링할 차원을 선택하고 필터 창의 *이 시각적 개체* 필드의 필터로 끌어 *옵니다* . Microsoft Call Quality 커넥터는 현재 *기본 필터링* (가능한 차원 값 목록에서 값 선택), *고급 필터링* (통화 품질 대시보드와 유사하게 필터링할 값 및 피연산자를 수동으로 지정) 및 *상대 날짜 필터링* ( *종료 시간* 및 *시작 시간* 차원에만 사용 가능)을 지원합니다. *상위 N* 에 따른 필터링은 통화 품질 대시보드에서 지원되지 않습니다.

    ![Power BI 커넥터의 시각화 필터입니다.](media/CQD-power-bi-connector5-resize.png)

    > [!IMPORTANT]
    > 필터는 차원에 적용되는 경우에만 지원됩니다. 측정값에 대한 필터링은 통화 품질 대시보드에서 지원되지 않습니다.

4. 마지막으로 *시각화* 창에서 *서식* 탭을 선택하여 쿼리의 스타일을 지정하고 서식을 지정합니다.

    > [!NOTE]
    > 호출 품질 대시보드 쿼리를 실행하려면 하나 이상의 측정값이 필요합니다. 쿼리가 로드되지 않으면 쿼리에 측정값을 포함했는지 다시 확인합니다.

## <a name="creating-a-drillthrough-report"></a>드릴스루 보고서 만들기

[Power BI의 드릴스루](/power-bi/desktop-drillthrough) 를 사용하면 다른 보고서의 값을 컨텍스트로 사용하여 신속하게 필터링할 수 있는 포커스가 있는 보고서를 만들 수 있습니다. Microsoft Call Quality 커넥터를 사용하여 첫 번째 쿼리를 만드는 방법을 알게 되면 드릴스루를 만드는 것이 훨씬 간단합니다.

1. 포커스가 있는 보고서에 대한 다른 페이지를 만든 다음 해당 페이지에 쿼리를 추가합니다.

2. 드릴스루 필터로 사용할 차원을 선택하고 시각화 창의 아래 *드릴스루* 필드로 끌어 *옵니다* .

    ![Power BI 커넥터의 드릴스루.](media/CQD-power-bi-connector6-resize.png)

3. **그거에요\!** 해당 차원을 사용하는 다른 페이지의 다른 쿼리는 이제 해당 페이지로 드릴스루 차원의 값을 필터로 자동으로 적용할 수 있습니다.

    ![Power BI 커넥터의 드릴스루 필터입니다.](media/CQD-power-bi-connector7-resize.png)

통화 품질 대시보드와 달리 Power BI는 비순차적 드릴스루를 지원합니다. 쿼리에 필요한 차원이 포함된 경우 다른 페이지로 드릴스루할 수 있습니다.

### <a name="best-practice"></a>모범 사례

Microsoft Call Quality 커넥터 쿼리는 드릴스루 기능을 염두에 두고 설계해야 합니다. 모든 데이터를 한 번에 로드한 다음 필터를 사용하여 축소하는 대신 더 광범위하고 낮은 카디널리티 쿼리로 시작하고 카디널리티가 높은 쿼리로 드릴다운합니다. 예를 들어 품질 문제에 가장 많이 기여하는 서브넷을 진단하려고 할 때 먼저 문제에 기여하는 해당 지역 및 국가를 식별한 다음 해당 지역 또는 국가의 서브넷으로 드릴다운하는 것이 좋습니다. 호출 품질 커넥터 템플릿은 예제 역할을 하기 위해 이러한 방식으로 설계되었습니다.

## <a name="limitations"></a>제한 사항

Power BI를 사용함에도 불구하고 통화 품질 대시보드의 데이터 모델 또는 일반적으로 DirectQuery 커넥터에 대한 제한으로 인해 모든 Power BI 기능이 Microsoft 통화 품질 커넥터에서 지원되는 것은 아닙니다. 아래 목록에서는 커넥터의 더 주목할 만한 제한 사항 중 일부를 적어 두지만 이 목록은 전체적인 것으로 간주해서는 안 됩니다.

1. **계산 열 –** 일반적으로 DirectQuery 커넥터는 Power BI에서 계산된 열에 대해 제한된 지원을 제공합니다. 일부 계산 열은 커넥터에서 작동할 수 있으며, 이러한 열은 예외입니다. 일반적으로 계산 열은 작동하지 않습니다.

2. **집계–** 호출 품질 대시보드 데이터 모델은 큐브 모델을 기반으로 하므로 집계가 측정값 형태로 이미 지원됩니다. 다른 차원에 집계를 수동으로 추가하거나 측정값의 집계 유형을 변경하려고 하면 커넥터에서 작동하지 않으며 일반적으로 오류가 발생합니다.

3. **사용자 지정 시각적 개체 –** Microsoft Call Quality 커넥터는 다양한 사용자 지정 시각적 개체에서 작동하지만 모든 사용자 지정 시각적 개체와의 호환성을 보장할 수 없습니다. 많은 사용자 지정 시각적 개체는 DirectQuery 커넥터에서 지원되지 않는 계산 열 또는 가져온 데이터의 사용에 의존합니다.

4. **캐시된 데이터 참조 –** Power BI는 현재 DirectQuery 커넥터에서 캐시된 데이터를 어떤 방식으로든 참조하는 것을 지원하지 않습니다. 쿼리 결과를 참조하려고 하면 새 쿼리가 발생합니다.

5. **상대 데이터 필터링 –** Microsoft 통화 품질 커넥터에서 지원되지만 *시작 시간* 및 *종료 시간* 차원에서만 지원됩니다. *Date* 차원은 상대 날짜 필터링에 적합한 선택일 수 있지만 *Date* 는 날짜 시간 개체로 저장되지 않으므로 Power BI에서 상대 날짜 필터링을 지원하지 않습니다.

6. **측정 전용 쿼리 -** 현재 Microsoft Call Quality 커넥터에서는 지원되지 않습니다. 세 개 이상의 측정값과 차원이 없는 시각화를 만들 때 열 데이터가 변환됩니다. 이를 방지하려면 항상 시각화에 하나 이상의 차원(예: 월 연도)을 포함합니다. 이 문제는 Power BI용 Microsoft 통화 품질 커넥터의 향후 릴리스에서 해결될 예정입니다.

7. **GCC(Government Community Cloud) 지원 –** GCC 환경의 고객의 경우 Microsoft Call Quality 커넥터는 Power BI Desktop 사용할 때만 작동합니다. Microsoft Call Quality 커넥터는 현재 GCC 고객을 위한 Power BI 서비스 호환되지 않습니다.

이러한 문제의 대부분은 Power BI의 DirectQuery 커넥터 디자인에 대한 제한 또는 CQD 데이터 모델 설계의 기본 사항입니다.

## <a name="troubleshooting"></a>문제 해결

### <a name="im-trying-to-use-the-date-column-as-a-date-slicer-as-soon-as-i-convert-the-data-type-of-this-column-to-date-i-get-this-error"></a>날짜 열을 날짜 슬라이서로 사용하려고 합니다. 이 열의 데이터 형식을 날짜로 변환하는 즉시 이 오류가 발생합니다.

> **이 시각적 개체에 대한 데이터를 로드할 수 없습니다**. OLE DB 또는 ODBC 오류: [Expression.Error] 식을 데이터 원본으로 접을 수 없습니다. 더 간단한 식을 사용해 보세요.

날짜 슬라이서는 Microsoft 통화 품질 커넥터에서 지원되지 않습니다. 날짜 범위를 지정하려면 보고서에 두 개의 필터를 적용하여 보다 작고 날짜보다 큰 을 지정합니다.

또는 보려는 날짜가 최근인 경우 상대 날짜 필터를 적용하여 지난 N일/주/월의 데이터만 표시합니다.


### <a name="when-i-add-certain-dimensions-to-my-reports-the-visual-immediately-returns-couldnt-load-the-data-for-this-visual-removing-the-dimension-fixes-the-visual----what-is-happening"></a>보고서에 특정 차원을 추가하면 시각적 개체는 즉시 **"이 시각적 개체에 대한 데이터를 로드할 수 없습니다"** 를 반환합니다. 차원을 제거하면 시각적 개체가 수정됩니다. 무슨 일이 일어나고 있나요?

Microsoft 통화 품질 커넥터의 알려진 문제입니다. 정수로 노출되는 모든 차원은 Power BI에 '집계' 열로 표시됩니다. 여기서 Power BI는 기본 요약 작업(일반적으로 'Sum')을 시도합니다. 경우에 따라 이 동작은 두 번째 WiFi 채널과 같은 차원의 'sum'이 의미가 없으므로 결과가 유용하지 않더라도 값을 합산하는 데 성공합니다. 다른 경우에는 이 요약 작업이 실패하고 시각적 개체에 오류가 발생합니다.

이 문제를 해결하려면 먼저 시각적 개체에서 차원을 제거합니다. '필드' 목록에서 차원을 선택하고 리본의 '열 도구' 탭으로 이동하여 '요약' 드롭다운 메뉴를 클릭하고 **요약하지 않음을** 선택합니다. 이제 시각적 개체에 차원을 다시 추가할 수 있습니다.


## <a name="error-codes"></a>오류 코드

Power BI용 Microsoft 통화 품질 커넥터는 구성할 수 있는 쿼리 종류 측면에서 브라우저 앱보다 덜 제한되므로 쿼리를 빌드하는 동안 때때로 여러 오류가 발생할 수 있습니다. "CQDError" 형식의 오류 메시지가 표시되는 경우 RunQuery – 쿼리 실행 오류"는 쿼리와 관련된 가능한 문제를 해결하기 위해 제공된 ErrorType 번호와 함께 아래 목록을 참조합니다. 다음은 CQD Power BI 커넥터에서 발생할 수 있는 가장 일반적인 오류 유형 코드입니다.

- **ErrorType 1 - 쿼리 구조 오류:** 쿼리 구조 오류는 일반적으로 커넥터가 올바르게 형식이 지정된 쿼리를 빌드하지 못하여 발생합니다. 이는 위의 제한 사항에 지정된 대로 지원되지 않는 기능을 사용할 때 가장 자주 발생합니다. 해당 쿼리에 계산 열 또는 사용자 지정 시각적 개체를 사용하지 않는지 다시 확인합니다.

  - **ErrorType 2 - 쿼리 빌드 오류:** 쿼리 빌드 오류는 빌드하려는 쿼리를 제대로 구문 분석할 수 없는 Microsoft Call Quality 커넥터로 인해 발생합니다. 이는 위의 제한 사항에 지정된 대로 지원되지 않는 기능을 사용할 때 가장 자주 발생합니다. 해당 쿼리에 계산 열 또는 사용자 지정 시각적 개체를 사용하지 않는지 다시 확인합니다.

  - **ErrorType 5 - 실행 시간 제한:** 쿼리가 시간 초과되기 전에 가능한 최대 런타임에 도달했습니다. 범위를 제한하기 위해 쿼리에 필터를 더 추가해 보세요. 데이터 범위를 좁히는 것이 가장 효과적인 방법인 경우가 많습니다.

  - **ErrorType 7 - 측정값 없음 오류:** 호출 품질 대시보드 쿼리는 작동하려면 측정값이 필요합니다. 쿼리에 측정값이 포함되어 있는지 다시 확인합니다. Microsoft 통화 품질 커넥터의 측정값은 이름 앞에 집계(합계) 기호로 표시됩니다.

이 범위를 벗어나는 추가 오류가 발생하는 경우 문제 해결 및 설명서를 적절하게 업데이트할 수 있도록 통화 품질 대시보드 팀에 알려주세요.

## <a name="footnotes"></a>각주

**<sup>1</sup>** 특정 프로세스 및 앱(예: OneDrive)으로 인해 문서 루트 폴더가 변경될 수 있습니다. *Power BI Desktop\\사용자 커넥터* 디렉터리가 현재 루트 폴더 Documents 폴더 내에 있는지 확인합니다.

**<sup>2</sup>** 통화 품질 대시보드에 사용하는 로그인 자격 증명은 Power BI Desktop 앱 자체에 로그인하는 데 사용하는 것과 동일한 자격 증명일 필요가 *없습니다*.

## <a name="frequently-asked-questions"></a>자주 묻는 질문

### <a name="when-will-the-power-bi-connector-be-updated-from-beta-status"></a>Power BI 커넥터는 언제 "베타" 상태에서 업데이트되나요?

베타 태그에도 불구하고 Power BI용 Microsoft 통화 품질(베타) 커넥터는 커넥터의 첫 번째 '릴리스' 버전이며 이를 반영하기 위해 Power BI 팀에서 공식적으로 보안 서명했습니다. 커넥터가 처음 릴리스될 당시 Power BI 팀은 지원 및 광범위한 인증을 제공할 수 없었지만 Microsoft Call Quality 커넥터의 보안, 신뢰성 및 일반적인 기능을 증명할 준비가 되어 있었습니다. 조만간 Power BI용 Microsoft 통화 품질 커넥터에 투자할 계획입니다.

### <a name="why-does-the-connector-seem-slower-compared-to-call-quality-dashboard-in-the-browser-what-can-i-do-to-improve-performance"></a>브라우저의 통화 품질 대시보드에 비해 커넥터가 느린 이유는 무엇인가요? 성능을 향상시키기 위해 무엇을 할 수 있나요?

다양한 템플릿에 대한 쿼리 성능은 브라우저와 커넥터 모두에서 실제로 동일합니다.  다른 독립 실행형 앱과 마찬가지로 Power BI는 인증 및 렌더링 시간을 성능에 추가합니다. 또한 실행 중인 동시 쿼리 수에 차이가 있습니다. 브라우저 내 버전의 통화 품질 대시보드에는 잘 개발되지 않고 정보 밀도가 높은 시각화 옵션이 있었기 때문에 대부분의 보고서는 한 번에 2~3개의 쿼리를 로드하는 것으로 제한되었습니다. 반면 커넥터 템플릿은 종종 20개 이상의 동시 쿼리를 표시합니다. 이전 보고서와 마찬가지로 응답성이 뛰어난 보고서를 빌드하려면 탭당 쿼리가 2~3개 이하인 보고서를 만들어 보세요.

자세한 내용은 다음 문서를 참조하세요.

- [Power BI 최적화 가이드](/power-bi/guidance/power-bi-optimization)
- [DirectQuery 모델 지침](/power-bi/guidance/directquery-model-guidance)

### <a name="i-find-that-i-routinely-run-into-the-10000-row-limit-when-running-queries-how-can-i-get-the-connector-to-return-more-than-10000-rows"></a>쿼리를 실행할 때 정기적으로 10,000행 제한에 해당합니다. 커넥터가 10,000개 이상의 행을 반환하도록 하려면 어떻게 해야 하나요?

10,000행 제한은 실제로 API 끝에 지정되며 성능을 크게 향상시키고 메모리 부족 조건으로 인한 쿼리 실행 오류의 위험을 줄이는 데 도움이 되도록 설계되었습니다.

결과 행 수를 늘리는 대신 커넥터 모범 사례에 따라 보고서를 재구성하는 것이 가장 좋습니다. 포함된 템플릿은 이러한 모범 사례를 보여 주도록 설계되었습니다. 가능한 경우 월, 연도, 날짜, 지역, 국가 등과 같은 더 광범위하고 낮은 카디널리티 차원을 사용하여 KPI를 확인합니다. 여기에서 점점 더 높은 카디널리티 차원으로 드릴다운할 수 있습니다. 기술 지원팀과 Location-Enhanced 보고서는 모두 이 드릴다운 워크플로의 좋은 예를 제공합니다.



## <a name="related-topics"></a>관련 주제

[Power BI를 사용하여 Teams용 CQD 데이터 분석](CQD-Power-BI-query-templates.md)
