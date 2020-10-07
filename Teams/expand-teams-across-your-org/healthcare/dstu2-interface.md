---
title: 환자 App 및 EHR integration DSTU2 인터페이스
author: dstrome
ms.author: dstrome
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: MET150
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
appliesto:
- Microsoft Teams
ms.reviewer: anach
description: Microsoft 팀 환자 앱을 사용 하도록 FTO r 서버를 설정 하거나 다시 구성 하는 등 팀의 DSTU2 인터페이스 사양에 대해 알아봅니다.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: ab502f66785af7947185fb0fbee0d3a55dd70c67
ms.sourcegitcommit: f4f5ad1391b472d64390180c81c2680f011a8a10
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2020
ms.locfileid: "48367608"
---
# <a name="dstu2-interface-specification"></a>DSTU2 인터페이스 사양

> [!IMPORTANT]
> **2020 년 10 월 30 일에는 환자 앱이 더 이상 사용 되지 않으며 사용자는 더 이상 팀 앱 스토어에서 설치할 수 없게 됩니다. 지금 팀에서 [목록 앱](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) 사용을 시작 하는 것이 좋습니다.**
>
>환자 앱 데이터는 팀을 백업 하는 Office 365 그룹의 그룹 사서함에 저장 됩니다. 환자 앱이 종료 되 면 관련 된 모든 데이터는이 그룹에 보존 되지만 사용자 인터페이스를 통해 더 이상 액세스할 수 없습니다. 현재 사용자는 [목록 앱](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db)을 사용 하 여 목록을 다시 만들 수 있습니다.
>
>[목록 앱](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) 은 모든 팀 사용자를 위해 사전 설치 되어 있으며 모든 팀과 채널에서 탭으로 사용할 수 있습니다. 목록에서 기본 제공 환자 서식 파일을 사용 하거나, 처음부터 또는 Excel로 데이터를 가져오면 환자 목록을 만들 수 있습니다. 조직에서 목록 앱을 관리 하는 방법에 대해 자세히 알아보려면 [목록 앱 관리](../../manage-lists-app.md)를 참조 하세요.

[!INCLUDE [preview-feature](../../includes/preview-feature.md)]

Microsoft 팀 환자 앱을 사용 하도록 FTO r 서버를 설정 또는 재구성 하려면 앱이 액세스 해야 하는 데이터에 대 한 이해가 필요 합니다. FHIR 서버는 다음 리소스에 대해 번들을 사용 하 여 POST 요청을 지원 해야 합니다.

- [환자가](#patient)
- [탑](#observation)
- [조건](#condition)
- [문제가](#encounter)
- [Allergy intolerance](#allergyintolerance)
- [통신이](#coverage)
- [투약 주문](#medication-order)
- [위치](#location)

> [!NOTE]
> 환자 리소스는 유일한 필수 리소스 이며 앱이 전혀 로드 되지 않습니다. 그러나 Microsoft 팀 환자 앱을 사용 하 여 최상의 최종 사용자 환경을 제공 하기 위해 파트너는 위에서 설명한 모든 사양에 대 한 지원을 구현 하는 것이 좋습니다.

Microsoft 팀 환자 앱에서 두 개 이상의 리소스에 대 한 쿼리는 요청에 대 한 번들 (일괄)을 FHIR 서버의 URL에 게시 합니다. 서버는 각 요청을 처리 하 고 각 요청과 일치 하는 리소스의 번들을 반환 합니다. 자세한 내용 및 예제는를 참조 하세요 [https://www.hl7.org/fhir/DSTU2/http.html#transaction](https://www.hl7.org/fhir/DSTU2/http.html#transaction) .

다음의 모든 팔 로우 리소스는 직접 리소스 참조를 통해 액세스할 수 있어야 합니다.

## <a name="conformance-minimum-required-field-set"></a>준수 최소 필수 필드 집합

 FA r 서버는 기능에 대 한 factual 요약을 제공 하기 위해 준수 문을 구현 해야 합니다. DSTU2 FA r 서버에서 다음 매개 변수가 예상 됩니다.

1. 받침대
   1. 모드
   2. 개입
   3. 자원: 종류
   4. 보안: [OAuth uri 용 확장](https://hl7.org/fhir/extension-oauth-uris.html)
2. Fto Rversion (코드에는 여러 버전을 지원할 때 피벗할 버전을 파악 하기 위해 필요 합니다.)

[https://www.hl7.org/fhir/dstu2/conformance.html](https://www.hl7.org/fhir/dstu2/conformance.html)이 필드 집합에 대 한 자세한 내용은을 참조 하세요.

## <a name="patient"></a>환자가

다음은 [Argonaut 환자 프로필](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html) 필드의 하위 집합인 최소 필수 필드입니다.

1. 패밀리 이름
2. Name. 지정 된
3. 성별을
4. 생년월일
5. MRN (Identifier)

Argonaut 필드 외에도 멋진 사용자 환경을 위해 환자 앱은 다음 필드도 읽습니다.

1. 이름을 사용 합니다.
2. Name. 접두사
3. CareProvider (환자 리소스에 대 한이 참조에는 다음 예제에 표시 된 표시 필드가 포함 되어야 합니다.)

* * *

    요청: <fa r-server>/Patient/<환자 번호>
    
    응답: {"resourceType": "환자", "id": "<환자 id>",.
      .
      .
      "name": [{"사용": "공식", "전위": ["Mr"], "family": ["Chau"], "지정": ["Hugh"]}], "식별자": [{"사용": "공식", "유형": {"코딩": [{"시스템": "" https://hl7.org/fhir/v2/0203 , "코드": "MR"}]}, "값": "1234567": "성별": "남성", "careProvider": [{"표시": "홍 길동"}],} 1957-06-05

* * *

리소스 검색에서는/Patient/_search 및 다음 매개 변수에 POST 메서드를 사용 합니다.

1. i
2. 패밀리: contains = (가족 이름에 값이 포함 되어 있는 모든 환자를 검색 합니다.)
3. 지정 =\<substring>
4. name =\<substring>
5. 생년월일 = (정확한 일치)
6. \_count (반환 해야 하는 최대 결과 수) <br> 응답에는 검색 결과로 반환 되는 레코드의 총 개수가 포함 되어야 하 고, \_ PatientsApp에서 반환 되는 레코드 수를 제한 하기 위해 count가 사용 됩니다.
7. identifier =\<mrn>

목표는 다음을 수행 하 여 환자를 검색 하 고 필터링 할 수 있다는 것입니다.

- ID:이는 모든 자원의 모든 리소스에 있는 자원 ID입니다.
- MRN이는 임상 직원이 알고 있는 환자에 대 한 실제 식별자입니다. 이 MRN는 FA r의 식별자 리소스 내에 있는 식별자 유형을 기반으로 한다는 것을 이해 합니다.
- 이름
- 생년월일

이 통화의 다음 예제를 참조 하세요.

* * *

    요청: POST <fa r-서버>/Patient/_search 요청 본문: 지정 = hugh&family = chau
    
    응답: {"resourceType": "번들", "id": "<번들 id>",.
      .
      .
      "항목": [{"리소스": {"resourceType": "환자", "id": "<환자 id>", "name": [{"텍스트": "Hugh Chau", "가족": ["Chau"], "지정": ["Hugh"]}], "성별": "1957-06-05"}, "검색": {"mode": "match"}}]}

* * *

[https://www.hl7.org/fhir/DSTU2/Patient.html](https://www.hl7.org/fhir/DSTU2/Patient.html)이 필드 집합에 대 한 자세한 내용은을 참조 하세요.

## <a name="observation"></a>탑

다음은 Argonaut 필수 기호 프로필의 하위 집합인 필요한 최소 필드입니다.

 1. 유효 (날짜 시간 또는 기간)
 2. 코드. 코딩 코드
 3. 값

Argonaut 필드 외에도 멋진 사용자 환경을 위해 환자 앱은 다음 필드도 읽습니다.

 1. 코드. 표시
 2. 단위

구성 요소 관찰을 사용 하는 경우 각 구성 요소 관찰에 대해 동일한 논리가 적용 됩니다.

리소스 검색에서 GET 메서드 및 다음 매개 변수를 사용 합니다.

1. 환자 =\<patient id\>
2. sort: desc =\<field ex. date\>

목표는 환자, [VitalSigns] (관람?)에 대 한 최신 필수 서명을 검색할 수 있다는 것입니다.

* * *

    요청: <fa r-서버>/관찰? 환자 =<환자 id>&_sort:d esc = 날짜&category = 필수-기호
    
    응답: {"resourceType": "번들", "id": "<번들 id>", "": "searchset", "total": 20, "entry": [{"리소스": {"resourceType": "관찰", "id": "<resource-id>", "category": {"코딩": [{code]: "필수-기호"}],}, "코드": {"코딩": [{"시스템": " http://loinc.org ", "코드": "39156-5", "display": "bmi"}],}, "effectiveDateTime": "2009-12-01", "": {"값": 34.4, "단위": "kg/m2", "시스템": " http://unitsofmeasure.org ", "코드": "kg/m2"}},},.
        .
        .
      ] }

* * *

[https://www.hl7.org/fhir/DSTU2/Observation.html](https://www.hl7.org/fhir/DSTU2/Observation.html)이 필드 집합에 대 한 자세한 내용은을 참조 하세요.

## <a name="condition"></a>조건

다음은 [Argonaut condition 프로필](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html)의 하위 집합인 최소 필수 필드입니다.

1. 코드. 코딩 [0]. 표시

Argonaut 필드 외에도 멋진 사용자 환경을 위해 환자 앱에서는 다음 필드도 읽을 수 있습니다.

1. 기록 된 날짜
2. 문제의

리소스 검색에서 GET 메서드 및 다음 매개 변수를 사용 합니다.

1. 환자 =\<patient id>
2. _count =\<max results>

이 통화의 다음 예제를 참조 하세요.

* * *

    요청: <fa r-server>/Condition? 환자 =<환자-id>&_count = 10
    
    응답: {"resourceType": "번들", "id": "<번들 id>" "," 유형 ":" searchset "," "resourceType": "": "id": "<리소스 id>", "코드": {"코딩": [{"시스템": " http://snomed.info/sct ", "코드": "386033004", "display": "Neuropathy (nerve 손상)"}]}, "dateRecorded": "2018-09-17", "심각도": {"코딩": [{"시스템": " http://snomed.info/sct ", "코드": "24484000", "display": "심각한"}]}},}]}

* * *

[https://www.hl7.org/fhir/DSTU2/Condition.html](https://www.hl7.org/fhir/DSTU2/Condition.html)이 필드 집합에 대 한 자세한 내용은을 참조 하세요.

## <a name="encounter"></a>문제가

미국 핵심 발생 프로필 "있어야 하는" 필드의 하위 집합인 최소 필수 필드는 다음과 같습니다.

1. 상태
2. [0]을 입력 합니다. 코딩 [0]. 표시

또한 미국 Core 발생 프로필의 "지원 해야 하는" 필드는 다음과 같습니다.

1. 기간. 시작
2. 위치 [0]. 위치. 표시

리소스 검색에서 GET 메서드 및 다음 매개 변수를 사용 합니다.

1. 환자 =\<patient id>
2. _sort: desc =\<field ex. date>
3. _count =\<max results>

목표는 환자 마지막으로 알려진 위치를 검색할 수 있다는 것입니다. 각 발생은 위치 리소스를 참조 합니다. 또한 참조에는 위치의 표시 필드도 포함 됩니다. 이 통화의 다음 예제를 참조 하세요.
* * *

    요청: <fa r-서버>/발생? 환자 =<환자-id>&_sort:d esc = date&_count = 1
    
    응답: {"resourceType": "번들", "유형": "searchset", "total": 1 "항목": [{"resource": {"resourceType": "발생", "id": "<리소스-id>", "식별자": [{"사용": "공식", "value": " <id> "}], "status": "도착", "유형": [{"코딩": [{"표시": "약속"}],}], "환자": {"참조": "환자/<환자 번호>"}, "기간": {"시작": "09/17/2018 1:00:00 PM"}, "위치": [{"위치": {"display": "클리닉"}

* * *

[https://www.hl7.org/fhir/DSTU2/Encounter.htm](https://www.hl7.org/fhir/DSTU2/Encounter.htm)이 필드 집합에 대 한 자세한 내용은을 참조 하세요.

## <a name="allergyintolerance"></a>AllergyIntolerance

다음은 Argonaut AllergyIntolerance 프로필의 하위 집합인 최소 필수 필드입니다.

1. 코드. 텍스트
2. 코드. 코딩 [0]. 표시
3. 상태

Argonaut 필드 외에도 멋진 사용자 환경을 위해 환자 앱은 다음 필드도 읽습니다.

1. RecordedDate
2. 참고. 텍스트
3. [...]에 반응 합니다. 물질. 텍스트
4. [...]에 반응 합니다. Manifestation[..]. 본문
5. 텍스트. i v

리소스 검색에서 GET 메서드 및 다음 매개 변수를 사용 합니다.

1. 환자 =  \<patient id>

이 통화의 다음 예제를 참조 하세요.

* * *

    요청: <fa r-server>/AllergyIntolerance? 환자 =<환자 id>
    
    응답: {"resourceType": "번들", "id": "<번들 id>", "유형": "searchset", "recordedDate", "total": "" entry ":" resourceType ":" AllergyIntolerance "," id ":" <리소스 id> "," ":" 2018 년 9-17T07:00:00.000 Z "," 물질 ": {" 텍스트 ":" Cas히 고 "" "status": "확인", "반응": [{"물질": {"text": "cas히 고 너트 allergenic Injectable Product"}, "manifestation": [{"텍스트": "Anaphylactic 반응"}]}

* * *

[https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html](https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html)이 필드 집합에 대 한 자세한 내용은을 참조 하세요.

## <a name="medication-order"></a>투약 주문

다음은 Argonaut MedicationOrder 프로필의 하위 집합인 최소 필수 필드입니다.

1. 기록 된 날짜
2. Prescriber
3. 투약. 표시 (참조 하는 경우)
4. 투약. 텍스트 (if 개념)

Argonaut 필드 외에도 멋진 사용자 환경을 위해 환자 앱에서는 다음 필드도 읽을 수 있습니다.

1. 날짜 종료
2. DosageInstruction
3. 텍스트. i v

리소스 검색에서 GET 메서드 및 다음 매개 변수를 사용 합니다.

1. 환자 =\<patient id>
2. _count =\<max results>

이 통화의 다음 예제를 참조 하세요.

* * *

    요청: <fa r-서버>/MedicationOrder? 환자 =<환자 id>&_count = 10
    
    응답: {"resourceType": "번들", "id": "<번들 id>", "유형": "searchset", "total": "entry": [{"리소스": {"resourceType": "MedicationOrder", "id": "<리소스 id>" 날짜 기록 ":" 2018-09-17 "," medicationCodeableConcept ": {" text ":" Lisinopril 20 MG Oral 태블릿 "}," prescriber ": {" display ":" "dosageInstruction": [{"text"}

* * *  

[https://www.hl7.org/fhir/DSTU2/MedicationOrder.html](https://www.hl7.org/fhir/DSTU2/MedicationOrder.html)이 필드 집합에 대 한 자세한 내용은을 참조 하세요.

## <a name="coverage"></a>통신이

미국 Core 또는 Argonaut 프로필에서 다루지 않는 최소 필수 필드는 다음과 같습니다.

1. Payor

리소스 검색에서 GET 메서드 및 다음 매개 변수를 사용 합니다.

1. 환자 =\<patient id>

이 통화의 다음 예제를 참조 하세요.

* * *

    요청: <fa r-server>/Coverage? 환자 =<환자 id>
    
    응답: {"resourceType": "번들", "유형": "searchset", "total": 1, "entry": {"리소스": "resourceType": "커버리지" "," id ":" <자원 id> "," 요금제 ":" 기본 보험 없음 "," 구독자 ": {" 참조 ":" 환자/<환자>

* * *

[https://www.hl7.org/fhir/DSTU2/Coverage.html](https://www.hl7.org/fhir/DSTU2/Coverage.html)이 필드 집합에 대 한 자세한 내용은을 참조 하세요.

## <a name="location"></a>위치

이 리소스는 [발생](#encounter) 리소스에 대 한 참조로만 사용 됩니다.

[https://www.hl7.org/fhir/DSTU2/Location.html](https://www.hl7.org/fhir/DSTU2/Location.html)이 필드 집합에 대 한 자세한 내용은을 참조 하세요.
