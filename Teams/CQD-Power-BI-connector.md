---
title: CQD 쿼리 템플릿을 사용하는 Power BI 커넥터 설치
ms.author: serdars
author: SerdarSoysal
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
localization_priority: Normal
description: CQD(호출 품질 대시보드) 쿼리 템플릿을 사용하는 Power BI Connector 설치
ms.openlocfilehash: c3812032f385a3428feec7f1126663e815af1b52
ms.sourcegitcommit: 4386f4b89331112e0d54943dc3133791d5dca3fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/09/2020
ms.locfileid: "49611582"
---
# <a name="install-power-bi-connector-to-use-cqd-query-templates"></a>CQD 쿼리 템플릿을 사용하는 Power BI 커넥터 설치

Microsoft Teams CQD(통화 품질 대시보드)에 대한 Power BI 쿼리 템플릿(PBIX 파일)을 사용하려면 먼저 다운로드에 포함된 *MicrosoftCallQuality.pqx* 파일을 사용하여 Microsoft CQD용 Power BI 커넥터를 설치해야 [합니다.](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true)

Power [BI를 사용하여 Teams에 대한 CQD 데이터를](CQD-Power-BI-query-templates.md) 분석하여 이러한 템플릿에 대해 자세히 알아보는 방법을 읽어 읽습니다.

Power BI 보고서에 액세스할 수 있는 [올바른 CQD](https://docs.microsoft.com/microsoftteams/turning-on-and-using-call-quality-dashboard#assign-roles-for-accessing-cqd) 액세스 역할이 있는지 확인

> [!NOTE]
> CQD Power BI 커넥터는 Power BI에서 DirectQuery만 지원합니다. 가져오기 모드는 지원되지 않습니다. 

## <a name="installation"></a>설치

커넥터를 사용할 수 있도록 사용자 지정 커넥터를 설치하고 보안을 조정하는 프로세스는 Power BI 설명서에 [자세히 설명되어 있습니다.](https://docs.microsoft.com/power-bi/desktop-connector-extensibility) 간단한 설명을 위해 다음과 같습니다.

1. 컴퓨터에 문서 Power BI Desktop 사용자 지정 커넥터 폴더가 이미 *\[ \] \\ \\ 있는지* 확인합니다. 그렇지 않은 경우 이 폴더를 만드면 됩니다. <sup>1</sup>

2. *\* 커넥터 파일(.mez* 또는 *\* .pqx* 파일)을 다운로드하고 *Custom Connectors 디렉터리에 저장합니다.*

3. **커넥터 파일이 *\* .mez*** 파일인 경우 사용자 지정 커넥터 설정 설명서에 설명된 보안 [설정도 조정해야 합니다.](https://docs.microsoft.com/power-bi/desktop-connector-extensibility#data-extension-security)

이 Microsoft Teams용 Power BI 커넥터의 새 버전이 릴리스된 경우 *Custom Connectors* 디렉터리의 이전 커넥터 파일을 새 파일로 바꾸기만 합니다.

## <a name="setup"></a>설정

보고서를 빌드하고 쿼리를 실행하려면 먼저 CQD 데이터 원본에 연결해야 합니다. 연결하기 위해 아래 단계를 수행합니다.

1. Power BI Desktop의 홈 탭에서 데이터 *다운로드를 클릭합니다.*

    ![스크린샷: Power BI 커넥터](media/CQD-power-bi-connector1-resize.png)

2. 이 *시점에* 데이터 저장 창이 나타납니다. Online *Services로 이동한* 다음 Microsoft 통화 품질(베타)을 선택하고 *Connect를 적중합니다.* 

    ![스크린샷: Power BI 커넥터](media/CQD-power-bi-connector2-resize.png)

3. 다음에 로그인하라는 메시지가 표시될 것입니다. CQD에 사용하는 동일한 자격 증명을 사용 합니다. <sup>2</sup>

4. 다음 프롬프트는 두 데이터 연결 모드 간의 *옵션을 제공합니다.* *DirectQuery를 선택하고* 확인을 *클릭합니다.*

5. 마지막으로, CQD에 대한 전체 데이터 모델을 보여 주어 최종 프롬프트가 표시될 것입니다. 이 시점에는 데이터가 표시되지 않습니다. CQD에 대한 데이터 모델만 표시됩니다. *[로드]를* 선택하여 설치 프로세스를 완료합니다.

6. 이 시점에서 Power BI는 창의 오른쪽에 데이터 모델을 로드합니다. 그렇지 않으면 페이지가 비어 있으며 기본적으로 쿼리가 로드되지 않습니다. 쿼리를 **작성하고** 데이터를 반환하기 위해 아래에서 쿼리 작성을 진행합니다.

이 설치 프로세스 중 단계가 완전히 명확하지 않은 경우 빠른 [시작: Power BI Desktop에서](https://docs.microsoft.com/power-bi/desktop-quickstart-connect-to-data)데이터에 연결하여 프로세스에 대한 자세한 설명을 찾을 수 있습니다.

## <a name="building-queries"></a>쿼리 구축

설정이 완료되면 필드 창에 수백 개의 차원 및 측정값의 이름이 *표시됩니다.* 여기에서 실제 쿼리를 생성하는 것은 간단합니다. 쿼리에 대해 원하는 차원 및 측정값을 선택한 다음 페이지로 끌어서 놓습니다. 다음은 간단한 예제를 통해 보다 자세한 설명입니다.

1. 시각화 창에서 사용할 *시각화를* 선택합니다. 해당 시각화의 빈 버전이 페이지에 표시됩니다. 이 예제에서는 테이블 시각화를 *사용하게* 됩니다.

    ![스크린샷: Power BI 커넥터](media/CQD-power-bi-connector3-resize.png)

2. 쿼리에 사용할 크기 및 측정값(해당 이름으로 집계 기호로 표시)을 결정한 다음 수동으로 선택하고 검은색 시각화로 끌어다 놓습니다. 또는 시각화 옵션 아래의 *값* 필드로 끌어다 놓습니다.

    ![스크린샷: Power BI 커넥터](media/CQD-power-bi-connector4-resize2.png)

    > [!IMPORTANT]
    > 호출 품질 대시보드를 실행하려면 모든 쿼리에 대한 측정값이 필요합니다. 쿼리에 측정값을 추가하지 못하면 해당 쿼리가 실패합니다.

3. 다음으로 필터링할 차원을 선택하고 필터 창의  이 시각적 필드에 있는 필터로 *끌어다* 놓습니다. CQD Power BI 커넥터는  현재 기본 필터링(가능한 차원 값 목록에서 값 선택), *고급* 필터링(고급 CQD와 유사하게 필터링할 값 및 피연산자  지정)  및 상대 날짜 필터링(종료 시간 및 시작 시간 차원에만 사용 가능)을 제공합니다.  상위 N에 따라 *필터링은* CQD에서 지원되지 않습니다.

    ![스크린샷: Power BI 커넥터](media/CQD-power-bi-connector5-resize.png)

4. 마지막으로 시각화 *창* 내에서 서식  탭을 선택하여 쿼리의 스타일을 지정하고 서식을 지정합니다.

    > [!NOTE]
    > CQD 쿼리를 실행하려면 하나 이상의 측정값이 필요 합니다. 쿼리가 로드되지 않는 경우 쿼리에 측정값이 포함되어 있지 않은지 다시 한 번 검사합니다.

## <a name="creating-a-drillthrough-report"></a>드릴스루 보고서 만들기

[Power BI의](https://docs.microsoft.com/power-bi/desktop-drillthrough) 드릴스루를 사용하면 다른 보고서의 값을 컨텍스트로 사용하여 빠르게 필터링할 수 있는 포커스가 있는 보고서를 만들 수 있습니다. CQD 커넥터를 사용하여 첫 번째 쿼리를 만드는 방법을 알고 나면 드릴스루를 만드는 것이 더 간단합니다.

1. 포커스가 있는 보고서에 대한 다른 페이지를 만든 다음 해당 페이지에 쿼리를 추가합니다.

2. 드릴스루 필터로 사용할 차원을 선택하고 시각화 창의 *드릴스루* 필드로 *끌어다* 놓습니다.

    ![스크린샷: Power BI 커넥터](media/CQD-power-bi-connector6-resize.png)

3. **그거에요\!** 해당 차원을 사용하는 다른 페이지의 다른 쿼리는 이제 해당 페이지로 드릴스루하여 드릴스루 차원 값을 필터로 자동으로 적용합니다.

    ![스크린샷: Power BI 커넥터](media/CQD-power-bi-connector7-resize.png)

고급 CQD와 달리 Power BI는 비차원 드릴스루를 지원합니다. 쿼리에 필요한 차원이 포함되어 있는 한 다른 페이지로 드릴스루할 수 있습니다.

### <a name="best-practice"></a>모범 사례

호출 품질 커넥터 쿼리는 드릴스루 기능을 염두에 두어 설계해야 합니다. 모든 데이터를 한 번 로드한 다음 필터를 사용하여 아래로 스크롤하는 대신 더 광범위한 카디널리티 쿼리로 시작하고 높은 카디널리티 쿼리로 드릴다운합니다. 예를 들어 품질 문제에 가장 많이 기여하는 서브넷을 진단하려는 경우 먼저 문제에 영향을 주는 해당 지역 및 국가를 식별한 다음 해당 지역 또는 국가의 서브넷으로 드릴다운하는 것이 유용합니다. 호출 품질 커넥터 템플릿은 예제 역할을 하도록 이러한 방식으로 디자인되었습니다.

## <a name="limitations"></a>제한 사항

Power BI를 사용하겠지만 CQD 데이터 모델 또는 일반적으로 DirectQuery 커넥터에 대한 제한 사항으로 인해 CQD 커넥터에서 모든 Power BI 기능이 지원되지는 않습니다. 아래 목록은 커넥터의 몇 가지 주목할 만한 제한 사항을 설명하지만 이 목록은 철저히 고려하지 말아야 합니다.

1. **계산된 열 –** 일반적으로 DirectQuery 커넥터는 Power BI에서 계산된 열을 제한적으로 지원합니다. 일부 계산된 열은 커넥터와 함께 작동할 수 있는 반면 예외로 간주해야 합니다. 일반적으로 계산된 열은 작동하지 않습니다.

2. **집계 –** CQD 데이터 모델은 큐브 모델을 토대합니다. 즉, 집계가 측정값 형태로 이미 지원됩니다. 다른 차원에 집계를 수동으로 추가하려고 시도하거나 측정값의 집계 유형을 변경하려고 하면 커넥터에서 작동하지 않습니다. 일반적으로 오류가 발생합니다.

3. **사용자 지정 시각적 개체 –** CQD 커넥터는 다양한 사용자 지정 시각적 개체와 작동하지만 모든 사용자 지정 시각적 개체와의 호환성을 보장할 수 없습니다. 많은 사용자 지정 시각적 개체는 DirectQuery 커넥터에서 지원하지 않는 계산된 열 또는 가져온 데이터의 사용에 의존합니다.

4. **캐시된 데이터 참조 –** Power BI는 현재 DirectQuery 커넥터에서 캐시된 데이터를 참조하는 방법을 지원하지 않습니다. 쿼리 결과를 참조하려고 하면 새 쿼리가 수행됩니다.

5. **상대 데이터 필터링 –** CQD 커넥터에서 지원되지만 시작 시간  및 종료 시간 *차원에서만* 지원됩니다. 날짜 *차원은* 상대 날짜 필터링을 위한 명백한 선택일 수 있습니다. *날짜는* 날짜 시간 개체로 저장되지 않습니다. 따라서 Power BI에서 상대 날짜 필터링을 지원하지 않습니다.

6. **정부 GCC(커뮤니티 클라우드) 지원 –** GCC 환경의 고객의 경우 Power BI Desktop을 사용할 때 CQD Power BI 커넥터가 작동됩니다. CQD Power BI 커넥터는 현재 GCC 고객을 위한 Power BI 서비스와 호환되지 않습니다.

이러한 문제는 대부분 Power BI의 DirectQuery 커넥터 디자인에 대한 제한 사항 또는 CQD 데이터 모델의 디자인에 대한 기본 사항입니다.

## <a name="troubleshooting"></a>문제 해결

### <a name="im-trying-to-use-the-date-column-as-a-date-slicer-as-soon-as-i-convert-the-data-type-of-this-column-to-date-i-get-this-error"></a>날짜 열을 날짜 슬라이서로 사용하려고 합니다. 이 열의 데이터 형식을 날짜로 변환하는 즉시 이 오류가 발생합니다.

> **이 시각적 개체에** 대한 데이터를 로드할 수 없습니다. OLE DB 또는 ODBC 오류: [Expression.Error] 식을 데이터 원본에 접을 수 없습니다. 더 간단한 식을 사용해 주세요.

날짜 슬라이서는 Power BI 커넥터에서 지원되지 않습니다. 날짜 범위를 지정하기 위해 날짜보다 작고 큰 필터를 지정하여 보고서에 두 개의 필터를 적용합니다.

또는 보아야 할 날짜가 최근인 경우 상대 날짜 필터를 적용하여 지난 N일/주/월의 데이터만 보여 줄 수 있습니다.

## <a name="error-codes"></a>오류 코드

CQD Power BI 커넥터는 구성할 수 있는 쿼리 종류 측면에서 브라우저 앱보다 제한이 적기 때문에 쿼리를 구축하는 동안 종종 많은 오류가 발생할 수 있습니다. "CQDError" 형식의 오류 메시지가 수신되는 경우 RunQuery – 쿼리 실행 오류"를 참조하고, 아래 목록을 ErrorType 번호와 함께 참조하여 쿼리와 관련한 가능한 문제를 해결합니다. 다음은 CQD Power BI 커넥터에서 발생할 수 있는 가장 일반적인 오류 유형 코드입니다.

- **ErrorType 1 - 쿼리 구조 오류:** 쿼리 구조 오류는 일반적으로 커넥터가 올바르게 형식이 지정된 쿼리를 빌드하지 못하여 발생합니다. 이 문제는 위의 제한 사항에서 지정한 대로 지원되지 않는 기능을 사용하는 경우 가장 자주 발생합니다. 해당 쿼리에 대해 계산된 열 또는 사용자 지정 시각적 개체가 사용되지 않는지 다시 한 번 확인해 집니다.

  - **ErrorType 2 - 쿼리 작성 오류:** 쿼리 작성 오류는 CQD 커넥터가 빌드하려는 쿼리를 올바르게 구문 분석할 수 없는 경우 발생합니다. 이 문제는 위의 제한 사항에서 지정한 대로 지원되지 않는 기능을 사용하는 경우 가장 자주 발생합니다. 해당 쿼리에 대해 계산된 열 또는 사용자 지정 시각적 개체가 사용되지 않는지 다시 한 번 확인해 집니다.

  - **ErrorType 5 - 실행 시간 제한:** 쿼리가 시간 초과 전에 가능한 최대 런타임에 도달했습니다. 쿼리에 필터를 더 추가하여 범위를 제한합니다. 데이터 범위를 좁히는 것이 이를 달성하는 가장 효과적인 방법인 경우가 종종 있습니다.

  - **ErrorType 7 - 측정 오류 없음:** CQD 쿼리는 작동하기 위해 측정값이 요구됩니다. 쿼리에 측정값이 포함되어 있는지 다시 한 번 검사합니다. CQD 커넥터의 측정값은 이름 앞에 집계(합계) 기호로 표시됩니다.

이 범위를 벗어난 추가 오류가 발생하는 경우 문제를 해결하고 설명서를 적절하게 업데이트할 수 있도록 CQD 팀에 알려 주세요.

## <a name="footnotes"></a>각주

**<sup>1</sup>** 특정 프로세스 및 앱(예: OneDrive)으로 인해 문서 루트 폴더가 변경될 수 있습니다. Power BI *Desktop \\ 사용자* 지정 커넥터 디렉터리가 현재 루트 폴더 문서 폴더 안에 있는지 확인합니다.

**<sup>2</sup>** CQD에 사용하는 로그인  자격 증명은 Power BI Desktop 앱 자체에 로그인하는 데 사용하는 자격 증명과 같을 필요가 없습니다.

## <a name="frequently-asked-questions"></a>자주 묻는 질문

### <a name="when-will-the-power-bi-connector-be-updated-from-beta-status"></a>Power BI 커넥터는 언제 "베타" 상태에서 업데이트될 예정

베타 태그에도 불구하고 Power BI용 호출 품질 커넥터는 커넥터의 릴리스 버전이며 이를 반영하기 위해 Power BI 팀에서 공식적으로 보안에 서명했습니다. 베타 태그를 제거하는 인증 프로세스는 광범위한 프로세스이며 커넥터에 직접 지원을 제공하려면 Power BI 팀의 약속이 필요합니다. 시간 제약으로 인해 Power BI 팀은 현재 지원 및 광범위한 인증을 제공할 수 없지만 Microsoft 통화 품질 커넥터의 보안, 인증 및 일반 기능을 증명할 준비가 된 것입니다.

### <a name="why-does-the-connector-seem-slower-compared-to-advanced-cqd-in-the-browser-what-can-i-do-to-improve-performance"></a>브라우저에서 고급 CQD에 비해 커넥터가 느려 보이는 이유는 무엇입니까? 성능을 개선하기 위해 무엇을 할 수 있는가

다양한 템플릿에 대한 쿼리 성능은 실제로 브라우저와 커넥터에서 동일합니다.  다른 독립 실행형 앱과 마찬가지로 Power BI는 성능에 인증 및 렌더링 시간을 추가합니다. 또한 차이점은 실행되는 동시 쿼리 수에 있습니다. 브라우저의 CQD 버전에는 덜 잘 개발되고 정보 밀도가 높은 시각화 옵션이 있기 때문에 대부분의 보고서는 한에 2-3개 쿼리를 로드하는 것으로 제한되었습니다. 반면에 커넥터 템플릿은 종종 20개 이상의 동시 쿼리를 표시합니다. 이전처럼 응답성이 뛰어난 보고서를 빌드하려는 경우 탭당 쿼리가 2~3개가 넘지 않습니다.

자세한 내용은 다음 문서를 참조하세요.

- [Power BI에 대한 최적화 가이드](https://docs.microsoft.com/power-bi/guidance/power-bi-optimization)
- [DirectQuery 모델 지침](https://docs.microsoft.com/power-bi/guidance/directquery-model-guidance)

### <a name="i-find-that-i-routinely-run-into-the-10000-row-limit-when-running-queries-how-can-i-get-the-connector-to-return-more-than-10000-rows"></a>쿼리를 실행할 때 10,000행 제한이 일상적으로 실행됩니다. 10,000개가 넘는 행을 반환하는 커넥터를 어떻게 얻을 수 있습니다.

10,000행 제한은 실제로 API 끝에 지정되어 있으며 성능을 크게 개선하고 메모리 부족으로 인한 쿼리 실행 오류의 위험을 줄일 수 있도록 디자인되었습니다.

결과 행 수를 늘리는 대신 커넥터 모범 사례에 따라 보고서를 재구성하는 것이 가장 좋습니다. 포함된 템플릿은 이러한 모범 사례를 보여 주기 위해 디자인됩니다. 가능한 경우 월, 연도, 날짜, 지역, 국가 등 더 넓은 카디널리티 차원을 사용하여 KP를 확인하여 시작하세요. 거기에서 점점 더 높은 카디널리티 차원으로 드릴다운할 수 있습니다. Helpdesk 및 Location-Enhanced 보고서는 모두 이 드릴다운 워크플로의 좋은 예를 제공합니다.



## <a name="related-topics"></a>관련 항목

[Power BI를 사용하여 Teams에 대한 CQD 데이터 분석](CQD-Power-BI-query-templates.md)
