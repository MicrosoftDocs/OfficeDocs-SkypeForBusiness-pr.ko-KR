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
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 15bcc5fcaff50d6d41c45ef2d38e34719ebca999
ms.sourcegitcommit: 18b5e3487ba1350c5d2e6d676a4ab582b5b638d4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2020
ms.locfileid: "48772209"
---
# <a name="dstu2-interface-specification"></a>DSTU2 인터페이스 사양

> [!NOTE]
> 2020 년 10 월 30 일에 효력을 환자 앱이 만료 되어 팀의 [목록 앱](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) 으로 대체 되었습니다. 목록을 사용 하는 경우 의료 기관에서 팀은 팀 모임에서 일반 환자 모니터링과의 interdisciplinary에 이르기까지 시나리오에 대 한 환자 목록을 만들 수 있습니다. 목록에서 환자 서식 파일을 확인 하 여 시작 하세요. 조직에서 목록 앱을 관리 하는 방법에 대해 자세히 알아보려면 [목록 관리 앱](../../manage-lists-app.md) 을 참조 하세요.

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

 - 받침대

    - 모드
    - 개입
    - 자원: 종류
    - 보안: [OAuth uri 용 확장](https://hl7.org/fhir/extension-oauth-uris.html)
   
 - Fto Rversion (코드에는 여러 버전을 지원할 때 피벗할 버전을 파악 하기 위해 필요 합니다.)

[https://www.hl7.org/fhir/dstu2/conformance.html](https://www.hl7.org/fhir/dstu2/conformance.html)이 필드 집합에 대 한 자세한 내용은을 참조 하세요.

## <a name="patient"></a>환자가

다음은 [Argonaut 환자 프로필](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html) 필드의 하위 집합인 최소 필수 필드입니다.

 - 패밀리 이름
 - Name. 지정 된
 - 성별을
 - 생년월일
 - MRN (Identifier)

Argonaut 필드 외에도 멋진 사용자 환경을 위해 환자 앱은 다음 필드도 읽습니다.

 - 이름을 사용 합니다.
 - Name. 접두사
 - CareProvider (환자 리소스에 대 한이 참조에는 다음 예제에 표시 된 표시 필드가 포함 되어야 합니다.)

    ```
    Request:
    GET <fhir-server>/Patient/<patient-id>
    
    Response:
    {
      "resourceType": "Patient",
      "id": "<patient-id>",
      .
      .
      .
      "name": [
        {
          "use": "official",
          "prefix": [ "Mr" ],
          "family": [ "Chau" ],
          "given": [ "Hugh" ]
        }
      ],
      "identifier": [
        {
          "use": "official",
          "type": {
            "coding": [
              {
                "system": "https://hl7.org/fhir/v2/0203",
                "code": "MR"
              }
            ]
          },
          "value": "1234567"
        }
      ],
      "gender": "male",
      "birthDate": "1957-06-05",
      "careProvider": [{ "display": "Jane Doe" }],
    }
    ```

리소스 검색에서는/Patient/_search 및 다음 매개 변수에 POST 메서드를 사용 합니다.

 - i
 - 패밀리: contains = (가족 이름에 값이 포함 되어 있는 모든 환자를 검색 합니다.)
 - 지정 =\<substring>
 - name =\<substring>
 - 생년월일 = (정확한 일치)
 - \_count (반환 해야 하는 최대 결과 수) <br> 응답에는 검색 결과로 반환 되는 레코드의 총 개수가 포함 되어야 하 고, \_ PatientsApp에서 반환 되는 레코드 수를 제한 하기 위해 count가 사용 됩니다.
 - identifier =\<mrn>

목표는 다음을 수행 하 여 환자를 검색 하 고 필터링 할 수 있다는 것입니다.

- ID:이는 모든 자원의 모든 리소스에 있는 자원 ID입니다.
- MRN이는 임상 직원이 알고 있는 환자에 대 한 실제 식별자입니다. 이 MRN는 FA r의 식별자 리소스 내에 있는 식별자 유형을 기반으로 한다는 것을 이해 합니다.
- 이름
- 생년월일

이 통화의 다음 예제를 참조 하세요.

```
Request:
POST <fhir-server>/Patient/_search
Request Body:
given=hugh&family=chau

Response:
{
  "resourceType": "Bundle",
  "id": "<bundle-id>",
  .
  .
  .
  "entry": [
    {
      "resource": {
        "resourceType": "Patient",
        "id": "<patient-id>",
        "name": [
          {
            "text": "Hugh Chau",
            "family": [ "Chau" ],
            "given": [ "Hugh" ]
          }
        ],
        "gender": "male",
        "birthDate": "1957-06-05"
      },
      "search": {
        "mode": "match"
      }
    }
  ]
}
```

[https://www.hl7.org/fhir/DSTU2/Patient.html](https://www.hl7.org/fhir/DSTU2/Patient.html)이 필드 집합에 대 한 자세한 내용은을 참조 하세요.

## <a name="observation"></a>탑

다음은 Argonaut 필수 기호 프로필의 하위 집합인 필요한 최소 필드입니다.

 - 유효 (날짜 시간 또는 기간)
 - 코드. 코딩 코드
 - 값

Argonaut 필드 외에도 멋진 사용자 환경을 위해 환자 앱은 다음 필드도 읽습니다.

 - 코드. 표시
 - 단위

구성 요소 관찰을 사용 하는 경우 각 구성 요소 관찰에 대해 동일한 논리가 적용 됩니다.

리소스 검색에서 GET 메서드 및 다음 매개 변수를 사용 합니다.

 - 환자 =\<patient id\>
 - sort: desc =\<field ex. date\>

목표는 환자, [VitalSigns] (관람?)에 대 한 최신 필수 서명을 검색할 수 있다는 것입니다.

```
Request:
GET <fhir-server>/Observation?patient=<patient-id>&_sort:desc=date&category=vital-signs

Response:
{
  "resourceType": "Bundle",
  "id": "<bundle-id>",
  "type": "searchset",
  "total": 20,
  "entry": [
    {
      "resource": {
        "resourceType": "Observation",
        "id": "<resource-id>",
        "category": {
          "coding": [ { code": "vital-signs" } ],
        },
        "code": {
          "coding": [
            {
              "system": "http://loinc.org",
              "code": "39156-5",
              "display": "bmi"
            }
          ],
        },
        "effectiveDateTime": "2009-12-01",
        "valueQuantity": {
          "value": 34.4,
          "unit": "kg/m2",
          "system": "http://unitsofmeasure.org",
          "code": "kg/m2"
        }
      },
    },
    .
    .
    .
  ]
}
```

[https://www.hl7.org/fhir/DSTU2/Observation.html](https://www.hl7.org/fhir/DSTU2/Observation.html)이 필드 집합에 대 한 자세한 내용은을 참조 하세요.

## <a name="condition"></a>조건

다음은 [Argonaut condition 프로필](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html)의 하위 집합인 최소 필수 필드입니다.

1. 코드. 코딩 [0]. 표시

Argonaut 필드 외에도 멋진 사용자 환경을 위해 환자 앱에서는 다음 필드도 읽을 수 있습니다.

 - 기록 된 날짜
 - 문제의

리소스 검색에서 GET 메서드 및 다음 매개 변수를 사용 합니다.

 - 환자 =\<patient id>
 - _count =\<max results>

이 통화의 다음 예제를 참조 하세요.

```
Request:
GET <fhir-server>/Condition?patient=<patient-id>&_count=10

Response:
{
  "resourceType": "Bundle",
  "id": "<bundle-id>",
  "type": "searchset",
  "total": 1,
  "entry": [
    {
      "resource": {
        "resourceType": "Condition",
        "id": "<resource-id>",
        "code": {
          "coding": [
            {
              "system": "http://snomed.info/sct",
              "code": "386033004",
              "display": "Neuropathy (nerve damage)"
            }
          ]
        },
        "dateRecorded": "2018-09-17",
        "severity": {
          "coding": [
            {
              "system": "http://snomed.info/sct",
              "code": "24484000",
              "display": "Severe"
            }
          ]
        }
      },
    }
  ]
}
```

[https://www.hl7.org/fhir/DSTU2/Condition.html](https://www.hl7.org/fhir/DSTU2/Condition.html)이 필드 집합에 대 한 자세한 내용은을 참조 하세요.

## <a name="encounter"></a>문제가

미국 핵심 발생 프로필 "있어야 하는" 필드의 하위 집합인 최소 필수 필드는 다음과 같습니다.

 - 상태
 - [0]을 입력 합니다. 코딩 [0]. 표시

또한 미국 Core 발생 프로필의 "지원 해야 하는" 필드는 다음과 같습니다.

 - 기간. 시작
 - 위치 [0]. 위치. 표시

리소스 검색에서 GET 메서드 및 다음 매개 변수를 사용 합니다.

 - 환자 =\<patient id>
 - _sort: desc =\<field ex. date>
 - _count =\<max results>

목표는 환자 마지막으로 알려진 위치를 검색할 수 있다는 것입니다. 각 발생은 위치 리소스를 참조 합니다. 또한 참조에는 위치의 표시 필드도 포함 됩니다. 이 통화의 다음 예제를 참조 하세요.

```
Request:
GET <fhir-server>/Encounter?patient=<patient-id>&_sort:desc=date&_count=1

Response:
{
  "resourceType": "Bundle",
  "type": "searchset",
  "total": 1,
  "entry": [
    {
      "resource": {
        "resourceType": "Encounter",
        "id": "<resource-id>",
        "identifier": [{ "use": "official", "value": "<id>" }],
        "status": "arrived",
        "type": [
          {
            "coding": [{ "display": "Appointment" }],
          }
        ],
        "patient": { "reference": "Patient/<patient-id>" },
        "period": { "start": "09/17/2018 1:00:00 PM" },
        "location": [
          {
            "location": { "display": "Clinic - ENT" },
          }
        ]
      }
    }
  ]
}
```

[https://www.hl7.org/fhir/DSTU2/Encounter.htm](https://www.hl7.org/fhir/DSTU2/Encounter.htm)이 필드 집합에 대 한 자세한 내용은을 참조 하세요.

## <a name="allergyintolerance"></a>AllergyIntolerance

다음은 Argonaut AllergyIntolerance 프로필의 하위 집합인 최소 필수 필드입니다.

 - 코드. 텍스트
 - 코드. 코딩 [0]. 표시
 - 상태

Argonaut 필드 외에도 멋진 사용자 환경을 위해 환자 앱은 다음 필드도 읽습니다.

 - RecordedDate
 - 참고. 텍스트
 - [...]에 반응 합니다. 물질. 텍스트
 - [...]에 반응 합니다. Manifestation[..]. 본문
 - 텍스트. i v

리소스 검색에서 GET 메서드 및 다음 매개 변수를 사용 합니다.

 - 환자 =  \<patient id>

이 통화의 다음 예제를 참조 하세요.

```
Request:
GET <fhir-server>/AllergyIntolerance?patient=<patient-id>

Response:
{
  "resourceType": "Bundle",
  "id": "<bundle-id>",
  "type": "searchset",
  "total": 1,
  "entry": [
    {
      "resource": {
        "resourceType": "AllergyIntolerance",
        "id": "<resource-id>",
        "recordedDate": "2018-09-17T07:00:00.000Z",
        "substance": {
          "text": "Cashew nuts"
        },
        "status": "confirmed",
        "reaction": [
          {
            "substance": {
              "text": "cashew nut allergenic extract Injectable Product"
            },
            "manifestation": [
              {
                "text": "Anaphylactic reaction"
              }
            ]
          }
        ]
      }
    }
  ]
}
```

[https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html](https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html)이 필드 집합에 대 한 자세한 내용은을 참조 하세요.

## <a name="medication-order"></a>투약 주문

다음은 Argonaut MedicationOrder 프로필의 하위 집합인 최소 필수 필드입니다.

 - 기록 된 날짜
 - Prescriber
 - 투약. 표시 (참조 하는 경우)
 - 투약. 텍스트 (if 개념)

Argonaut 필드 외에도 멋진 사용자 환경을 위해 환자 앱에서는 다음 필드도 읽을 수 있습니다.

 - 날짜 종료
 - DosageInstruction
 - 텍스트. i v

리소스 검색에서 GET 메서드 및 다음 매개 변수를 사용 합니다.

 - 환자 =\<patient id>
 - _count =\<max results>

이 통화의 다음 예제를 참조 하세요.

```
Request:
GET <fhir-server>/MedicationOrder?patient=<patient-id>&_count=10

Response:
{
  "resourceType": "Bundle",
  "id": "<bundle-id>",
  "type": "searchset",
  "total": 1,
  "entry": [
    {
      "resource": {
        "resourceType": "MedicationOrder",
        "id": "<resource-id>",
        "dateWritten": "2018-09-17",
        "medicationCodeableConcept": {
          "text": "Lisinopril 20 MG Oral Tablet"
        },
        "prescriber": {
          "display": "Jane Doe"
        },
        "dosageInstruction": [
          {
            "text": "1 daily"
          }
        ]
      }
    }
  ]
}
```

[https://www.hl7.org/fhir/DSTU2/MedicationOrder.html](https://www.hl7.org/fhir/DSTU2/MedicationOrder.html)이 필드 집합에 대 한 자세한 내용은을 참조 하세요.

## <a name="coverage"></a>통신이

미국 Core 또는 Argonaut 프로필에서 다루지 않는 최소 필수 필드는 다음과 같습니다.

 - Payor

리소스 검색에서 GET 메서드 및 다음 매개 변수를 사용 합니다.

 - 환자 =\<patient id>

이 통화의 다음 예제를 참조 하세요.

```
Request:
GET <fhir-server>/Coverage?patient=<patient-id>

Response:
{
  "resourceType": "Bundle",
  "type": "searchset",
  "total": 1,
  "entry": [
    {
      "resource": {
        "resourceType": "Coverage",
        "id": "<resource-id>",
        "plan": "No Primary Insurance",
        "subscriber": { "reference": "Patient/<patient-id>" }
      }
    }
  ]
}
```
    
[https://www.hl7.org/fhir/DSTU2/Coverage.html](https://www.hl7.org/fhir/DSTU2/Coverage.html)이 필드 집합에 대 한 자세한 내용은을 참조 하세요.

## <a name="location"></a>위치

이 리소스는 [발생](#encounter) 리소스에 대 한 참조로만 사용 됩니다.

[https://www.hl7.org/fhir/DSTU2/Location.html](https://www.hl7.org/fhir/DSTU2/Location.html)이 필드 집합에 대 한 자세한 내용은을 참조 하세요.
