---
title: Patients App 및 EHR 통합 STU3 인터페이스
author: dstrome
ms.author: dstrome
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: MET150
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
appliesto:
- Microsoft Teams
ms.reviewer: anach
description: Electronic Health Records를 환자 앱과 STU3 인터페이스 Microsoft Teams 통합하는 방법을 알아보고
ms.custom: seo-marvel-apr2020
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 64fc61072510942b67d51542095a927e7e67c697
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58582332"
---
# <a name="stu3-interface-specification"></a>STU3 인터페이스 사양

> [!NOTE]
> 2020년 10월 30일부터 환자 앱이 폐기되고 Teams 내 [목록 앱](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db)으로 대체되었습니다. 환자 앱 데이터는 팀을 백업하는 Office 365 그룹의 그룹 사서함에 저장됩니다. 환자 앱과 연결된 모든 데이터는 이 그룹에 보존되지만 사용자 인터페이스를 통해 더 이상 액세스할 수 없습니다. 사용자는 [목록 앱](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db)을 사용하여 목록을 다시 만들 수 있습니다.
>
>목록 기능을 사용하면 의료 조직의 관리 팀은 라운드 및 분야별 팀 모임에서 일반 환자 모니터링에 이르는 다양한 시나리오에 대한 환자 목록을 작성할 수 있습니다. 시작을 위해 목록에서 환자 서식 파일을 체크 아웃합니다. 조직에서 목록 앱을 관리하는 방법에 대한 자세한 내용은 [목록 앱 관리](../../manage-lists-app.md)를 참조하세요.

환자 앱과 함께 작동하기 위해 FHIR 서버를 설정하거나 Microsoft Teams 앱에 액세스하는 데 필요한 데이터를 이해해야 합니다. FHIR 서버는 다음 리소스에 대한 번들을 사용하여 POST 요청을 지원해야 합니다.

- [환자](#patient)
- [관찰](#observation)
- [조건](#condition)
- [발생](#encounter)
- [알레르기 내성](#allergyintolerance)
- [적용 범위](#coverage)
- [약물 치료](#medication-request) 문(PatientsApp의 DSTU2 버전에서 MedicationOrder 대체)
- 위치(이 리소스에서 필요한 정보는 발생에 포함될 수 있습니다)

> [!NOTE]
> 환자 리소스는 유일한 필수 리소스입니다(앱이 로드되지 않습니다). 그러나 파트너는 아래 제공된 사양에 따라 위에서 언급한 모든 리소스에 대한 지원을 구현하여 환자 앱의 최상의 최종 사용자 환경을 Microsoft Teams 것이 좋습니다.

두 개 Microsoft Teams 환자 앱의 쿼리는 FHIR 서버의 URL에 요청의 번들(BATCH)을 게시해야 합니다. 서버는 각 요청을 처리하고 각 요청에 일치하는 리소스 번들을 반환해야 합니다. 자세한 정보 및 예제는 [https://www.hl7.org/fhir/STU3/http.html#transaction](https://www.hl7.org/fhir/STU3/http.html#transaction) 를 참조하세요.

## <a name="capability-statement"></a>기능 문

필요한 최소 필드는 다음입니다.

 - REST

    - 모드
    - 상호 작용
    - 리소스: 형식
    - 보안: [OAuth URIS 확장](https://hl7.org/fhir/extension-oauth-uris.html)
    
 - FhirVersion(이 코드에서는 피벗해야 하는 버전을 이해해야 합니다.)

이 [https://www.hl7.org/fhir/stu3/capabilitystatement.html](https://www.hl7.org/fhir/stu3/capabilitystatement.html) 필드 집합에 대한 기타 세부 정보는 를 참조합니다.

## <a name="patient"></a>환자

Argonaut 환자 프로필 필드의 하위 집합인 최소 필수 필드는 다음과 같습니다.

 - Name.Given
 - Name.Family
 - 성별
 - BirthDate
 - MRN(식별자)

[Argonaut](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html)필드 외에도, 훌륭한 사용자 환경을 위해 Patients 앱이 다음 필드를 읽을 수 있습니다.

 - Name.Use
 - Name.Prefix
 - [GeneralPractitioner] - GeneralPractitioner 참조가 환자 리소스에 포함되어야 합니다(표시 필드만 해당)

리소스 검색은 /Patient/_search 및 다음 매개 변수에서 POST 메서드를 사용합니다.

 - id
 - family=(가족 이름이 값을 포함하는 모든 환자를 검색합니다.
 - given=\<substring>
 - birthdate=(정확한 일치)
 - gender=(값이 관리-성별 중 하나인 값)
 - \_count(반환해야 하는 최대 결과 수) <br> 응답에는 검색 결과로 반환된 레코드의 총 수가 포함되어야 합니다. 반환된 레코드 수를 제한하기 위해 PatientsApp에서 사용할 수 \_ 있습니다.
 - 식별자=\<mrn>

목표는 다음을 통해 환자를 검색하고 필터링할 수 있습니다.

- ID: FHIR의 모든 리소스가 있는 리소스 ID입니다.
- MRN: 이것은 임상 직원이 알고 있는 환자의 실제 식별자입니다. 이 MRN은 FHIR의 식별자 리소스 내부 식별자 유형을 기반으로 합니다.
- 이름
- Birthdate

호출의 다음 예제를 참조합니다.

```
Request:
POST <fhir-server>/Patient/_search
Request Body:
given=ruth&family=black

Response:
{
  "resourceType": "Bundle",
  "id": "<bundle-id>",
  "meta": {
    "lastUpdated": "2019-01-14T23:44:45.052+00:00"
  },
  "type": "searchset",
  "total": 1,
  "link": [
    {
      "relation": "self",
      "url": <fhir-server>/Patient/_search"
    }
  ],
  "entry": [
    {
      "fullUrl": <fhir-server>/Patient/<patient-id>",
      "resource": {
        "resourceType": "Patient",
        "id": "<patient-id>",
        "meta": {
          "versionId": "1",
          "lastUpdated": "2017-10-18T18:32:37.000+00:00"
        },
        "text": {
          "status": "generated",
          "div": "<div>\n        <p>Ruth Black</p>\n      </div>"
        },
        "identifier": [
          {
            "use": "usual",
            "type": {
              "coding": [
                {
                  "system": "https://hl7.org/fhir/v2/0203",
                  "code": "MR",
                  "display": "Medical record number",
                  "userSelected": false
                }
              ],
              "text": "Medical record number"
            },
            "system": "http://hospital.smarthealthit.org",
            "value": "1234567"
          }
        ],
        "active": true,
        "name": [
          {
            "use": "official",
            "family": "Black",
            "given": [
              "Ruth",
              "C."
            ]
          }
        ],
        "telecom": [
          {
            "system": "phone",
            "value": "800-599-2739",
            "use": "home"
          },
          {
            "system": "phone",
            "value": "800-808-7785",
            "use": "mobile"
          },
          {
            "system": "email",
            "value": "ruth.black@example.com"
          }
        ],
        "gender": "female",
        "birthDate": "1951-08-23",
        "address": [
          {
            "use": "home",
            "line": [
              "26 South RdApt 22"
            ],
            "city": "Sapulpa",
            "state": "OK",
            "postalCode": "74066",
            "country": "USA"
          }
        ]
      },
      "search": {
        "mode": "match"
      }
    }
  ]
}
```

```
Request:
GET <fhir-server>/Patient/<patient-id>

Response:
{
  "resourceType": "Patient",
  "id": "<patient-id>",
  "identifier": [
    {
      "use": "usual",
      "type": {
        "coding": [
          {
            "system": "https://hl7.org/fhir/v2/0203",
            "code": "MR",
          }
        ],
        "text": "Medical record number"
      },
      "value": "1234567"
    }
  ],
  "name": [
    {
      "use": "official",
      "family": "Adams",
      "given": [ "Daniel", "X." ]
    }
  ],
  "gender": "male",
  "birthDate": "1925-12-23",
}
```

이 [https://hl7.org/fhir/stu3/patient.html](https://hl7.org/fhir/stu3/patient.html) 필드 집합에 대한 기타 세부 정보는 를 참조합니다.

## <a name="observation"></a>관찰

이 필드는 [Argonaut](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-vitalsigns.html)프로필의 하위 집합인 최소 Vital-Signs 있습니다.

 - 유효(날짜 시간 또는 기간)
 - Code.Coding.Code
 - ValueQuantity.Value

Argonaut 필드 외에도, 훌륭한 사용자 환경을 위해 Patients 앱은 다음 필드를 읽을 수 있습니다.

 - Code.Coding.Display
 - ValueQuantity.Unit

리소스 검색은 GET 메서드 및 다음 매개 변수를 사용합니다.

 - patient=\<patient id>
 - _sort=-date
 - 범주("category=vital-signs"를 쿼리하여 중요한 기호 목록을 검색합니다.

호출의 이 예제를 참조합니다.

```
Request:
GET <fhir-server>/Observation?patient=<patient-id>&category=vital-signs

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
        "category": [
          {
            "coding": [
              {
                "system": "https://hl7.org/fhir/observation-category",
                "code": "vital-signs"
              }
            ],
          }
        ],
        "code": {
          "coding": [
            {
              "system": "http://loinc.org",
              "code": "8867-4",
              "display": "heart_rate"
            }
          ]
        },
        "effectiveDateTime": "2009-04-08T00:00:00-06:00",
        "valueQuantity": {
          "value": 72.0,
          "unit": "{beats}/min",
          "system": "http://unitsofmeasure.org",
        }
      }
    },
    .
    .
    .
  ]
}
```

이 [https://www.hl7.org/fhir/stu3/observation.html](https://www.hl7.org/fhir/stu3/observation.html) 필드 집합에 대한 기타 세부 정보는 를 참조합니다.

## <a name="condition"></a>조건

Argonaut 조건 프로필의 하위 집합인 최소 필수 [필드는 다음과 같습니다.](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html)

 - Code.Coding[0]. 표시

Argonaut 필드 외에도, 훌륭한 사용자 환경을 위해 Patients 앱은 다음 필드를 읽을 수 있습니다.

 - AssertedDate
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
  "total": 2,
  "entry": [
    {
      "resource": {
        "resourceType": "Condition",
        "id": "<resource-id>",
        "code": {
          "coding": [
            {
              "system": "http://snomed.info/sct",
              "code": "185903001",
              "display": "Needs influenza immunization",
            }
          ]
        },
        "severity": {
          "coding": [
            {
              "system": "http://snomed.info/sct",
              "code": "24484000",
              "display": "Severe"
            }
          ]
        },
        "assertedDate": "2018-04-04"
      }
    },
    .
    .
    .
  ]
}
```

이 [https://hl7.org/fhir/stu3/condition.html](https://hl7.org/fhir/stu3/condition.html) 필드 집합에 대한 기타 세부 정보는 를 참조합니다.

## <a name="encounter"></a>발생

이는 미국 코어 만남 프로필 "필수" [](https://hl7.org/fhir/us/core/2018Jan/StructureDefinition-us-core-encounter.html) 필드의 하위 집합인 최소 필수 필드입니다.

 - 상태
 - [0]을 입력합니다. 코딩[0]. 표시

또한 US Core Encounter 프로필의 "지원해야 합니다" 필드의 다음 필드는 다음과 같습니다.

 - Period.Start
 - Location[0]. Location.Display

리소스 검색은 GET 메서드 및 다음 매개 변수를 사용합니다.

 - patient=\<patient id>
 - _sort:desc=\<field ex. date>
 - _count=\<max results>

목표는 환자의 마지막 알려진 위치를 검색할 수 있게 하는 것입니다. 각 조우는 위치 리소스를 참조합니다. 참조에는 위치의 표시 필드도 포함됩니다.

이 [https://hl7.org/fhir/stu3/encounter.html](https://hl7.org/fhir/stu3/encounter.html) 필드 집합에 대한 기타 세부 정보는 를 참조합니다.

## <a name="allergyintolerance"></a>AllergyIntolerance

다음은 [Argonaut AllergyIntolerance](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-allergyintolerance.html) 프로필의 하위 집합인 최소 필수 필드입니다.

 - Code.Text
 - Code.Coding[0]. 표시
 - ClinicalStatus/VerificationStatus(둘 다 읽음)

Argonaut 필드 외에도, 훌륭한 사용자 환경을 위해 Patients 앱은 다음 필드를 읽을 수 있습니다.

 - AssertedDate
 - Note.Text
 - 반응
    - 물질(하나의 코딩 요소)
    - 매니페스트(하나의 코딩 요소)

리소스 검색은 GET 메서드 및 다음 매개 변수를 사용합니다.

 - 환자 =  \<patient id>

호출의 다음 예제를 참조합니다. 

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
        "clinicalStatus": "active",
        "verificationStatus": "confirmed",
        "code": {
          "coding": [
            {
              "system": "http://rxnav.nlm.nih.gov/REST/Ndfrt",
              "code": "N0000175503",
              "display": "sulfonamide antibacterial",
            }
          ],
          "text": "sulfonamide antibacterial"
        },
        "assertedDate": "2018-01-01T00:00:00-07:00",
        "reaction": [
          {
            "manifestation": [
              {
                "coding": [
                  {
                    "system": "http://snomed.info/sct",
                    "code": "271807003",
                    "display": "skin rash",
                  }
                ],
                "text": "skin rash"
              }
            ],
          }
        ]
      }
    }
  ]
}
```

이 [https://hl7.org/fhir/stu3/allergyintolerance.html](https://hl7.org/fhir/stu3/allergyintolerance.html) 필드 집합에 대한 기타 세부 정보는 를 참조합니다.

## <a name="medication-request"></a>약물 요청

다음은 미국 핵심 약물 요청 프로필의 하위 집합인 최소 필수 [필드입니다.](http://www.hl7.org/fhir/us/core/StructureDefinition-us-core-medicationrequest.html)

 - Medication.Display(참조인 경우)
 - Medication.Text(CodableConcept인 경우)
 - AuthoredOn
 - Requester.Agent.Display

US Core 필드 외에도, 훌륭한 사용자 환경을 위해 Patients 앱이 다음 필드를 읽을 수 있습니다.

 - 복용량Instruction[...]. 텍스트
 - 텍스트

리소스 검색은 GET 메서드 및 다음 매개 변수를 사용합니다.

 - patient=\<patient id>
 - _count=\<max results>

이 [https://www.hl7.org/fhir/medicationrequest.html](https://www.hl7.org/fhir/medicationrequest.html) 필드 집합에 대한 기타 세부 정보는 를 참조합니다.

## <a name="coverage"></a>적용 범위

다음은 미국 코어 또는 Argonaut 프로필에서 다루지 않는 최소 필수 필드입니다.

 - 그룹화( 하나 이상의 요소와 함께
    - GroupDisplay
    - PlanDisplay
 - 기간
 - SubscriberId

리소스 검색은 GET 메서드 및 다음 매개 변수를 사용합니다.

 - 환자 = \<patient id>

이 [https://hl7.org/fhir/stu3/coverage.html](https://www.hl7.org/fhir/medicationrequest.html) 필드 집합에 대한 기타 세부 정보는 를 참조합니다.
