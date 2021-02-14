---
title: 환자 앱 및 EHR 통합 DSTU2 인터페이스
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
description: Microsoft Teams Patients 앱에서 작동하기 위해 FHIR 서버 설정 또는 재구성 등 Teams의 DSTU2 인터페이스 사양에 대해 자세히 배워 보십시오.
ms.custom: seo-marvel-mar2020
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 12833ea55977cf7e8d18ee5c10b1f17d898b27b3
ms.sourcegitcommit: beaaee10019f4eda746f348888a4a3c2aaa6f196
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2020
ms.locfileid: "48803486"
---
# <a name="dstu2-interface-specification"></a>DSTU2 인터페이스 사양

> [!NOTE]
> 2020년 10월 30일부로 환자 앱은 사용 중지되고 Teams의 [목록](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) 앱으로 대체됩니다. 환자 앱 데이터는 팀을 백업하는 Office 365 그룹의 그룹 사서함에 저장됩니다. 환자 앱과 연결된 모든 데이터는 이 그룹에 유지되지만 사용자 인터페이스를 통해 더 이상 액세스할 수 없습니다. 사용자는 목록 앱을 사용하여 목록을 다시 [만들 수 있습니다.](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db)
>
>목록을 사용하여 의료 조직의 관리 팀은 라운드 및학 간 팀 모임에서 일반 환자 모니터링에 이르는 시나리오에 대한 환자 목록을 만들 수 있습니다. 시작을 위해 목록에서 환자 서식 파일을 확인해 하세요. 조직에서 목록 앱을 관리하는 방법에 대한 자세한 내용은 목록 앱 [관리를 참조하세요.](../../manage-lists-app.md)

Microsoft Teams Patients 앱에서 작동하기 위해 FHIR 서버를 설정하거나 다시 구성하려면 앱이 액세스해야 하는 데이터를 이해해야 합니다. FHIR 서버는 다음 리소스에 번들을 사용하여 POST 요청을 지원해야 합니다.

- [환자](#patient)
- [관찰](#observation)
- [조건](#condition)
- [인게이트](#encounter)
- [내성성 발화](#allergyintolerance)
- [적용 범위](#coverage)
- [품사 주문](#medication-order)
- [위치](#location)

> [!NOTE]
> 환자 리소스는 앱이 로드되지 않는 유일한 필수 리소스입니다. 그러나 파트너는 Microsoft Teams Patients 앱의 최상의 최종 사용자 환경을 위해 아래 제공된 사양에 따라 위에서 언급한 모든 리소스에 대한 지원을 구현하는 것이 좋습니다.

Microsoft Teams Patients 앱에서 두 개 이상의 리소스에 대한 쿼리는 FHIR 서버의 URL에 요청 번들(BATCH)을 게시합니다. 서버는 각 요청을 처리하고 각 요청과 일치하는 리소스 번들을 반환합니다. 자세한 정보 및 예제는 [https://www.hl7.org/fhir/DSTU2/http.html#transaction](https://www.hl7.org/fhir/DSTU2/http.html#transaction) 다음을 참조하세요.

다음 모든 FHIR 리소스는 직접 리소스 참조를 통해 액세스할 수 있습니다.

## <a name="conformance-minimum-required-field-set"></a>준수 최소 필수 필드 집합

 FHIR 서버는 해당 기능에 대한 사실적 요약을 가지기 위해 준수 문을 구현해야 합니다. DSTU2 FHIR 서버에서 아래 매개 변수가 필요합니다.

 - REST

    - 모드
    - 상호 작용
    - 리소스: 형식
    - 보안: [OAuth URIS 확장](https://hl7.org/fhir/extension-oauth-uris.html)
   
 - FhirVersion(이 코드는 여러 버전을 지원할 때 피벗해야 하는 버전을 이해해야 합니다.)

이 [https://www.hl7.org/fhir/dstu2/conformance.html](https://www.hl7.org/fhir/dstu2/conformance.html) 필드 집합에 대한 기타 세부 정보를 참조합니다.

## <a name="patient"></a>환자

다음은 [Argonaut](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html) 환자 프로필 필드의 하위 집합인 최소 필수 필드입니다.

 - Name.Family
 - Name.Given
 - Gender
 - BirthDate
 - MRN(식별자)

Argonaut 필드 외에도, 환자 앱이 훌륭한 사용자 환경을 위해 다음 필드를 읽습니다.

 - Name.Use
 - Name.Prefix
 - CareProvider(환자 리소스에 대한 이 참조에는 다음 예제에 표시된 표시 필드가 포함되어야 합니다.)

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

리소스 검색은 /Patient/_search POST 메서드와 다음 매개 변수를 사용합니다.

 - id
 - family:contains=(가족 이름에 값이 포함된 모든 환자를 검색합니다.)
 - given=\<substring>
 - name=\<substring>
 - birthdate=(exact match)
 - \_count(반환해야 하는 결과의 최대 수) <br> 응답은 검색 결과로 반환된 총 레코드 수를 포함해야 합니다. 이 개수는 PatientsApp에서 반환되는 레코드 수를 제한하는 데 \_ 사용됩니다.
 - identifier=\<mrn>

목표는 다음을 통해 환자를 검색하고 필터링할 수 있는 것입니다.

- ID: FHIR의 모든 리소스에 있는 리소스 ID입니다.
- MRN: 이는 의료진이 알 수 있는 환자에 대한 실제 식별자입니다. 이 MRN은 FHIR의 식별자 리소스 내 식별자 유형을 기반으로 합니다.
- 이름
- 생년월일

이 호출의 다음 예제를 참조합니다.

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

이 [https://www.hl7.org/fhir/DSTU2/Patient.html](https://www.hl7.org/fhir/DSTU2/Patient.html) 필드 집합에 대한 기타 세부 정보를 참조합니다.

## <a name="observation"></a>관찰

다음은 Argonaut 중요 기호 프로필의 하위 집합인 최소 필수 필드입니다.

 - 유효(날짜 시간 또는 기간)
 - Code.Coding.Code
 - ValueQuantity.Value

Argonaut 필드 외에도, 환자 앱이 훌륭한 사용자 환경을 위해 다음 필드를 읽습니다.

 - Code.Coding.Display
 - ValueQuantity.Unit

구성 요소 관찰을 사용하는 경우 각 구성 요소 관찰에 동일한 논리가 적용됩니다.

리소스 검색은 GET 메서드 및 다음 매개 변수를 사용합니다.

 - patient=\<patient id\>
 - sort:desc=\<field ex. date\>

목표는 환자에 대한 최신 중요 기호인 [VitalSigns.DSTU.saz](관찰?)를 검색할 수 있는 것입니다.

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

이 [https://www.hl7.org/fhir/DSTU2/Observation.html](https://www.hl7.org/fhir/DSTU2/Observation.html) 필드 집합에 대한 기타 세부 정보를 참조합니다.

## <a name="condition"></a>조건

다음은 [Argonaut](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html)조건 프로필의 하위 집합인 최소 필수 필드입니다.

1. Code.Coding[0]. 디스플레이

Argonaut 필드 외에도 환자 앱이 훌륭한 사용자 환경을 위해 다음 필드를 읽을 수 있습니다.

 - 기록된 날짜
 - 심각도

리소스 검색은 GET 메서드 및 다음 매개 변수를 사용합니다.

 - patient=\<patient id>
 - _count=\<max results>

이 호출의 다음 예제를 참조합니다.

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

이 [https://www.hl7.org/fhir/DSTU2/Condition.html](https://www.hl7.org/fhir/DSTU2/Condition.html) 필드 집합에 대한 기타 세부 정보를 참조합니다.

## <a name="encounter"></a>인게이트

다음은 미국 핵심 인시던트 프로필의 하위 집합인 최소 필수 필드입니다.

 - 상태
 - [0]을 입력합니다. 코딩[0]. 디스플레이

또한 US Core Encounter 프로필의 "반드시 지원해야 하는" 필드의 다음 필드도 있습니다.

 - Period.Start
 - Location[0]. Location.Display

리소스 검색은 GET 메서드 및 다음 매개 변수를 사용합니다.

 - patient=\<patient id>
 - _sort:desc=\<field ex. date>
 - _count=\<max results>

목표는 환자의 마지막으로 알려진 위치를 검색할 수 있는 것입니다. 각 만남은 위치 리소스를 참조합니다. 참조에는 위치의 표시 필드도 포함되어야 합니다. 이 호출의 다음 예제를 참조합니다.

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

이 [https://www.hl7.org/fhir/DSTU2/Encounter.htm](https://www.hl7.org/fhir/DSTU2/Encounter.htm) 필드 집합에 대한 기타 세부 정보를 참조합니다.

## <a name="allergyintolerance"></a>2010-02-02

다음은 Argonaut일자세한Intolerance 프로필의 하위 집합인 최소 필수 필드입니다.

 - Code.Text
 - Code.Coding[0]. 디스플레이
 - 상태

Argonaut 필드 외에도, 환자 앱이 훌륭한 사용자 환경을 위해 다음 필드를 읽습니다.

 - RecordedDate
 - Note.Text
 - 반응[..]. 질.Text
 - 반응[..]. Manifestation[..]. 텍스트
 - Text.Div

리소스 검색은 GET 메서드 및 다음 매개 변수를 사용합니다.

 - Patient =  \<patient id>

이 호출의 다음 예제를 참조합니다.

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

이 [https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html](https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html) 필드 집합에 대한 기타 세부 정보를 참조합니다.

## <a name="medication-order"></a>품사 주문

다음은 Argonaut에이지이루터 프로필의 하위 집합인 최소 필수 필드입니다.

 - DateWritten
 - Prescriber.Display
 - 표시할 수 있습니다(참조하는 경우)
 - 표시기.Text(개념인 경우)

Argonaut 필드 외에도 환자 앱이 훌륭한 사용자 환경을 위해 다음 필드를 읽을 수 있습니다.

 - DateEnded
 - 1000000000000000000
 - Text.Div

리소스 검색은 GET 메서드 및 다음 매개 변수를 사용합니다.

 - patient=\<patient id>
 - _count=\<max results>

이 호출의 다음 예제를 참조합니다.

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

이 [https://www.hl7.org/fhir/DSTU2/MedicationOrder.html](https://www.hl7.org/fhir/DSTU2/MedicationOrder.html) 필드 집합에 대한 기타 세부 정보를 참조합니다.

## <a name="coverage"></a>적용 범위

다음은 미국 코어 또는 Argonaut 프로필에서 다루지 않는 최소 필수 필드입니다.

 - 지급자

리소스 검색은 GET 메서드 및 다음 매개 변수를 사용합니다.

 - patient=\<patient id>

이 호출의 다음 예제를 참조합니다.

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
    
이 [https://www.hl7.org/fhir/DSTU2/Coverage.html](https://www.hl7.org/fhir/DSTU2/Coverage.html) 필드 집합에 대한 기타 세부 정보를 참조합니다.

## <a name="location"></a>위치

이 리소스는 Encounter 리소스에 대한 [참조로만 사용됩니다.](#encounter)

이 [https://www.hl7.org/fhir/DSTU2/Location.html](https://www.hl7.org/fhir/DSTU2/Location.html) 필드 집합에 대한 기타 세부 정보를 참조합니다.
