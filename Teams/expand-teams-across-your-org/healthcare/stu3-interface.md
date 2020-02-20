---
title: 환자 App 및 EHR integration STU3 인터페이스
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
description: Microsoft 팀 환자 앱 EHR 통합
ms.openlocfilehash: d718f3d3772a08ecfa57e418a4f4fc2e22fe7172
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42147701"
---
# <a name="stu3-interface-specification"></a>STU3 인터페이스 사양

[!INCLUDE [preview-feature](../../includes/preview-feature.md)]

Microsoft 팀 환자 앱을 사용 하도록 FTO r 서버를 설정 또는 재구성 하려면 앱이 액세스 해야 하는 데이터에 대 한 이해가 필요 합니다. FHIR 서버는 다음 리소스에 대해 번들을 사용 하 여 POST 요청을 지원 해야 합니다.

- [환자가](#patient)
- [탑](#observation)
- [조건](#condition)
- [문제가](#encounter)
- [Allergy Intolerance](#allergyintolerance)
- [통신이](#coverage)
- [투약 문](#medication-request) (DSTU2 버전의 PatientsApp에서 MedicationOrder를 대체 합니다.)
- 위치 (이 리소스에서 필요로 하는 정보가 발생할 수 있음)

> [!NOTE]
> 환자 리소스는 유일한 필수 리소스 (앱이 전혀 로드 되지 않는)에만 사용 됩니다. 그러나 Microsoft 팀 환자 앱을 사용 하 여 최상의 최종 사용자 환경을 제공 하기 위해 파트너는 위에서 설명한 모든 사양에 대 한 지원을 구현 하는 것이 좋습니다.

두 개 이상의 리소스에 대 한 Microsoft 팀 환자 앱의 쿼리는 요청에 대 한 번들 (일괄 처리)을 FTO r 서버의 URL에 게시 해야 합니다. 서버는 각 요청을 처리 하 고 각 요청과 일치 하는 리소스의 번들을 반환 합니다. 자세한 내용 및 예제는를 참조 [https://www.hl7.org/fhir/STU3/http.html#transaction](https://www.hl7.org/fhir/STU3/http.html#transaction)하세요.

## <a name="capability-statement"></a>역량 명세서

최소 필수 필드는 다음과 같습니다.

1. 받침대
   1. 모드
   2. 개입
   3. 자원: 종류
   4. 보안: [OAuth uri 용 확장](https://hl7.org/fhir/extension-oauth-uris.html)
2. Fto Rversion (코드에는 어떤 버전을 피벗할 것인지 이해 하기 위해 필요 합니다.)

이 [https://www.hl7.org/fhir/stu3/capabilitystatement.html](https://www.hl7.org/fhir/stu3/capabilitystatement.html) 필드 집합에 대 한 자세한 내용은을 참조 하세요.

## <a name="patient"></a>환자가

다음은 Argonaut 환자 프로필 필드의 하위 집합인 최소 필수 필드입니다.

1. Name. 지정 된
2. 패밀리 이름
3. 성별을
4. 생년월일
5. MRN (Identifier)

[Argonaut 필드](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html)외에도 멋진 사용자 환경을 위해 환자 앱에서는 다음 필드도 읽을 수 있습니다.

1. 이름을 사용 합니다.
2. Name. 접두사
3. [GeneralPractitioner]-GeneralPractitioner 참조는 환자 리소스 (표시 필드에만 해당)에 포함 되어야 합니다.

리소스 검색에서는/Patient/_search 및 다음 매개 변수에 POST 메서드를 사용 합니다.

1. i
2. family = (가족 이름에 값이 포함 되어 있는 모든 환자 검색)
3. 지정 된\<= 하위 문자열>
4. 생년월일 = (정확한 일치)
5. 성별 = (관리자 성별 중 하나에 해당 하는 값)
6. \_count (반환 해야 하는 최대 결과 수) <br> 응답에는 검색 \_결과에 따라 반환 되는 레코드의 총 개수가 포함 되어야 하며 반환 되는 레코드 수를 제한 하기 위해 PatientsApp에서 사용 됩니다.
7. 식별자 =\<mrn

목표는 다음을 수행 하 여 환자를 검색 하 고 필터링 할 수 있다는 것입니다.

- ID:이는 모든 자원의 모든 리소스에 있는 자원 ID입니다.
- MRN이는 임상 직원이 알고 있는 환자에 대 한 실제 식별자입니다. 이 MRN는 FA r의 식별자 리소스 내에 있는 식별자 유형을 기반으로 이해 합니다.
- 이름
- 생년월일

통화에 대 한 다음 예제를 참조 하세요.

* * *

    요청: POST <fa r-서버>/Patient/_search 요청 본문: 지정 = ruth&family = black
    
    응답: {"resourceType": "번들", "id": "<번들 id>", "meta": {"lastUpdated": "2019-01-14T23:44:45.052 + 00:00"}, "type": "searchset", "/patient/", "total": "" 링크 ": [{" relation ":" self "," url ":" "항목": _search> <[{"fullUrl": <fa r-server>/Patient/<환자> "," resource ": {" resourceType ":" 환자 "," id ":" <환자 id> "," meta ": {" 37.000 ":" 1 "," lastUpdated ":" 2017-10-18T18:32: + 00:00 "}," 텍스트 ": {" status ":" 생성 됨 "," div ":"<div>\n        <p>Ruth 블랙</p>\n      </div>"}," 식별자 ": [{" 사용 ":" 일반 "," 유형 ": {" 코딩 ": [{" 시스템 ":"https://hl7.org/fhir/v2/0203"," 코드 ":" MR "," 표시 ":" 의료 레코드 번호 "," userselected ": false}]," text ":" 의료 레코드 번호 "}," 시스템 ":"http://hospital.smarthealthit.org"," system "을" 1234567 ")]," 활성 ": true," name ": [{" 사용 ":" 공식 "," 가족 ":" Black "," 제공 됨 ": [" Ruth "," C "
    ]}], "텔레콤": [{"시스템": "전화", "값": "800-599-2739", "사용": "home"}, {"system": "phone", "값": "800-808-7785", "사용": "모바일"}, {"시스템": "전자 메일", "값": "ruth.black@example.com"}], "성별": "여성", "생년월일": "1951-08-23", "주소": [{"사용": "집", "줄": ["26 남 RdApt 22"], "도시": "Sapulpa" "state": "OK", "postalCode": "74066", "국가": "USA"}]}, "검색": {"mode": "match"}}]}

* * *

    요청: <fa r-server>/Patient/<환자 번호>
    
    응답: {"resourceType": "환자", "id": "<환자 id>", "식별자": [{"사용": "일반", "유형": {"코딩": [{"시스템": "https://hl7.org/fhir/v2/0203", "코드": "MR",}], "text": "의료 레코드 번호"}, "값": "1234567"}], "family": "씨", "다니엘", "지정 된 이름", "X": " ]}], "성별": "남성", "생년월일": "1925-12-23",}

* * *

이 [https://hl7.org/fhir/stu3/patient.html](https://hl7.org/fhir/stu3/patient.html) 필드 집합에 대 한 자세한 내용은을 참조 하세요.

## <a name="observation"></a>탑

다음은 Argonaut 필수 입력 [프로필](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-vitalsigns.html)의 하위 집합인 필요한 최소 필드입니다.

1. 유효 (날짜 시간 또는 기간)
2. 코드. 코딩 코드
3. 값

Argonaut 필드 외에도 멋진 사용자 환경을 위해 환자 앱에서는 다음 필드도 읽을 수 있습니다.

1. 코드. 표시
2. 단위

리소스 검색에서 GET 메서드 및 다음 매개 변수를 사용 합니다.

1. 환자 =\<환자 id>
2. _sort =-날짜
3. 범주 ("category = 필수-서명")에서 중요 한 서명 목록을 검색 하는 방법을 쿼리 합니다.

통화에 대 한 다음 예제를 참조 하세요.

* * *

    요청: <fa r-서버>/관찰? 환자 =<환자 번호>&category = 필수-기호
    
    응답: {"resourceType": "번들", "id": "<번들 id>", "유형": "searchset", "total": 20, "진입": {"리소스": "resourceType": "관찰" "이" <"-id": ": 리소스 id>", "category": "" 시스템 ":"https://hl7.org/fhir/observation-category"," 코드 ":" 필수-기호 "}],}]," code ": {" 코딩 ": [{" 시스템 ":"http://loinc.org"," 코드 ":" 8867-4 "," display ":" heart_rate "}]}," effectiveDateTime ":" 2009-04-08t00:00:00-06:00 ","/분 ": {" 값 ": 72.0," 단위 ":" {티 티} "," system ":"http://unitsofmeasure.org",}}},.
        .
        .
      ] }

* * *

이 [https://www.hl7.org/fhir/stu3/observation.html](https://www.hl7.org/fhir/stu3/observation.html) 필드 집합에 대 한 자세한 내용은을 참조 하세요.

## <a name="condition"></a>조건

다음은 [Argonaut condition 프로필](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html)의 하위 집합인 필요한 최소 필드입니다.

1. 코드. 코딩 [0]. 표시

Argonaut 필드 외에도 멋진 사용자 환경을 위해 환자 앱에서는 다음 필드도 읽을 수 있습니다.

1. AssertedDate
2. 문제의

리소스 검색에서 GET 메서드 및 다음 매개 변수를 사용 합니다.

1. 환자 =\<환자 id>
2. _count =\<최대 결과>

이 통화의 다음 예제를 참조 하세요.

* * *

    요청: <fa r-server>/Condition? 환자 =<환자-id>&_count = 10
    
    응답: {"resourceType": "번들", "id": "<번들 id>", "유형": "searchset", "total": "#" resourceType ":" Condition "," id ":" <리소스 id> "," 코드 ": {" 코딩 ": [{" 시스템 ":" "http://snomed.info/sct," 코드 ":" 185903001 "," display ":"에는 influenza immunization ",}]}," 심각도 ": {" 코딩 ": [{" 시스템 ":" "http://snomed.info/sct", "display": "" assertedDate ":" 2018-04-04 "}},. 24484000
        .
        .
      ] }

* * *
이 [https://hl7.org/fhir/stu3/condition.html](https://hl7.org/fhir/stu3/condition.html) 필드 집합에 대 한 자세한 내용은을 참조 하세요.

## <a name="encounter"></a>문제가

[미국 핵심 발생 프로필](https://hl7.org/fhir/us/core/2018Jan/StructureDefinition-us-core-encounter.html) 의 하위 집합인 최소 필수 필드는 "필드에" 필드가 있어야 합니다. "

1. 상태
2. [0]을 입력 합니다. 코딩 [0]. 표시

또한 미국 Core 발생 프로필의 "지원 해야 하는" 필드에는 다음과 같은 필드가 있습니다.

1. 기간. 시작
2. 위치 [0]. 위치. 표시

리소스 검색에서 GET 메서드 및 다음 매개 변수를 사용 합니다.

1. 환자 =\<환자 id>
2. _sort: desc =\<field ex 날짜>
3. _count =\<최대 결과>

목표는 환자 마지막으로 알려진 위치를 검색할 수 있다는 것입니다. 각 발생은 위치 리소스를 참조 합니다. 또한 참조에는 위치의 표시 필드도 포함 됩니다.

이 [https://hl7.org/fhir/stu3/encounter.html](https://hl7.org/fhir/stu3/encounter.html) 필드 집합에 대 한 자세한 내용은을 참조 하세요.

## <a name="allergyintolerance"></a>AllergyIntolerance

다음은 [Argonaut AllergyIntolerance](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-allergyintolerance.html) 프로필의 하위 집합인 최소 필수 필드입니다.

1. 코드. 텍스트
2. 코드. 코딩 [0]. 표시
3. ClinicalStatus/VerificationStatus (두 가지 모두 읽었습니다)

Argonaut 필드 외에도 멋진 사용자 환경을 위해 환자 앱에서 다음 필드도 읽을 수 있습니다.

1. AssertedDate
2. 참고. 텍스트
3. 반응은
    1. 물질 (1 개의 코딩 요소)
    2. Manifestation (1 코딩 요소)

리소스 검색에서 GET 메서드 및 다음 매개 변수를 사용 합니다.

1. 환자 = \<환자 id>

통화에 대 한 다음 예제를 참조 하세요. 

* * *

    요청: <fa r-server>/AllergyIntolerance? 환자 =<환자 id>
    
    응답: {"resourceType": "번들", "id": "<번들 id>" "," 유형 ":" searchset "," total ":" entry ": [{" 리소스 ": {" resourceType ":" AllergyIntolerance "," id ":" <resource-id> "," clinicalStatus ":" active "," verificationStatus ":" 확인 됨 "," ":"http://rxnav.nlm.nih.gov/REST/Ndfrt"" "시스템": "", "" display ":" sulfonamide antibacterial ",}]," 텍스트 ":" sulfonamide ant ibacterial "}," assertedDate ":" 2018-01-01T00:00:00-07:00 "," 반응 ": [{" manifestation ": [{" 코딩 ": [{" 시스템 ":"http://snomed.info/sct"" 코드 ":" 271807003 "," display ":" skin rash ",}]," text ":" skin rash "}]}

* * *

이 [https://hl7.org/fhir/stu3/allergyintolerance.html](https://hl7.org/fhir/stu3/allergyintolerance.html) 필드 집합에 대 한 자세한 내용은을 참조 하세요.

## <a name="medication-request"></a>투약 요청

[미국 Core 투약 요청 프로필](http://www.hl7.org/fhir/us/core/StructureDefinition-us-core-medicationrequest.html)의 하위 집합인 최소 필수 필드는 다음과 같습니다.

1. 투약. 표시 (참조 하는 경우)
2. 투약 (if CodableConcept)
3. 기관 Edon
4. 요청자. 에이전트 디스플레이

멋진 사용자 환경을 위해 미국 Core 필드 외에도 환자 앱에서 다음 필드를 읽을 수 있습니다.

1. DosageInstruction[..]. 본문
2. 본문

리소스 검색에서 GET 메서드 및 다음 매개 변수를 사용 합니다.

1. 환자 =\<환자 id>
2. _count =\<최대 결과>

이 [https://www.hl7.org/fhir/medicationrequest.html](https://www.hl7.org/fhir/medicationrequest.html) 필드 집합에 대 한 자세한 내용은을 참조 하세요.

## <a name="coverage"></a>통신이

미국 Core 또는 Argonaut 프로필에서 다루지 않는 최소 필수 필드는 다음과 같습니다.

1. 그룹화에서 하나 이상의 요소를 사용 하 여
    1. GroupDisplay
    2. 계획 표시
2. 안에
3. SubscriberId

리소스 검색에서 GET 메서드 및 다음 매개 변수를 사용 합니다.

1. 환자 = \<환자 id>

이 [https://hl7.org/fhir/stu3/coverage.html](https://www.hl7.org/fhir/medicationrequest.html) 필드 집합에 대 한 자세한 내용은을 참조 하세요.
