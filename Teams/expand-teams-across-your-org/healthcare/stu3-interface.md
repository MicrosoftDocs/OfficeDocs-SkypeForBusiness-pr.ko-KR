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
description: Microsoft 팀 환자 앱 및 STU3 인터페이스 사양에 전자 상태 레코드를 통합 하는 방법에 대해 자세히 알아보세요.
ms.custom: seo-marvel-apr2020
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: a36c6176b4873dd41d654493bd36e9a3dbbfd49a
ms.sourcegitcommit: 18b5e3487ba1350c5d2e6d676a4ab582b5b638d4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2020
ms.locfileid: "48772269"
---
# <a name="stu3-interface-specification"></a>STU3 인터페이스 사양

> [!NOTE]
> 2020 년 10 월 30 일에 효력을 환자 앱이 만료 되어 팀의 [목록 앱](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) 으로 대체 되었습니다. 목록을 사용 하는 경우 의료 기관에서 팀은 팀 모임에서 일반 환자 모니터링과의 interdisciplinary에 이르기까지 시나리오에 대 한 환자 목록을 만들 수 있습니다. 목록에서 환자 서식 파일을 확인 하 여 시작 하세요. 조직에서 목록 앱을 관리 하는 방법에 대해 자세히 알아보려면 [목록 앱 관리](../../manage-lists-app.md)를 참조 하세요.

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

두 개 이상의 리소스에 대 한 Microsoft 팀 환자 앱의 쿼리는 요청에 대 한 번들 (일괄 처리)을 FTO r 서버의 URL에 게시 해야 합니다. 서버는 각 요청을 처리 하 고 각 요청과 일치 하는 리소스의 번들을 반환 합니다. 자세한 내용 및 예제는를 참조 하세요 [https://www.hl7.org/fhir/STU3/http.html#transaction](https://www.hl7.org/fhir/STU3/http.html#transaction) .

## <a name="capability-statement"></a>역량 명세서

최소 필수 필드는 다음과 같습니다.

 - 받침대

    - 모드
    - 개입
    - 자원: 종류
    - 보안: [OAuth uri 용 확장](https://hl7.org/fhir/extension-oauth-uris.html)
    
 - Fto Rversion (코드에는 어떤 버전을 피벗할 것인지 이해 하기 위해 필요 합니다.)

[https://www.hl7.org/fhir/stu3/capabilitystatement.html](https://www.hl7.org/fhir/stu3/capabilitystatement.html)이 필드 집합에 대 한 자세한 내용은을 참조 하세요.

## <a name="patient"></a>환자가

다음은 Argonaut 환자 프로필 필드의 하위 집합인 최소 필수 필드입니다.

 - Name. 지정 된
 - 패밀리 이름
 - 성별을
 - 생년월일
 - MRN (Identifier)

[Argonaut 필드](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html)외에도 멋진 사용자 환경을 위해 환자 앱에서는 다음 필드도 읽을 수 있습니다.

 - 이름을 사용 합니다.
 - Name. 접두사
 - [GeneralPractitioner]-GeneralPractitioner 참조는 환자 리소스 (표시 필드에만 해당)에 포함 되어야 합니다.

리소스 검색에서는/Patient/_search 및 다음 매개 변수에 POST 메서드를 사용 합니다.

 - i
 - family = (가족 이름에 값이 포함 되어 있는 모든 환자 검색)
 - 지정 =\<substring>
 - 생년월일 = (정확한 일치)
 - 성별 = (관리자 성별 중 하나에 해당 하는 값)
 - \_count (반환 해야 하는 최대 결과 수) <br> 응답에는 검색 결과에 따라 반환 되는 레코드의 총 개수가 포함 되어야 하며 \_ 반환 되는 레코드 수를 제한 하기 위해 PatientsApp에서 사용 됩니다.
 - identifier =\<mrn>

목표는 다음을 수행 하 여 환자를 검색 하 고 필터링 할 수 있다는 것입니다.

- ID:이는 모든 자원의 모든 리소스에 있는 자원 ID입니다.
- MRN이는 임상 직원이 알고 있는 환자에 대 한 실제 식별자입니다. 이 MRN는 FA r의 식별자 리소스 내에 있는 식별자 유형을 기반으로 이해 합니다.
- 이름
- 생년월일

통화에 대 한 다음 예제를 참조 하세요.

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

[https://hl7.org/fhir/stu3/patient.html](https://hl7.org/fhir/stu3/patient.html)이 필드 집합에 대 한 자세한 내용은을 참조 하세요.

## <a name="observation"></a>탑

[Argonaut Vital-Signs 프로필](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-vitalsigns.html)의 하위 집합인 최소 필수 필드입니다.

 - 유효 (날짜 시간 또는 기간)
 - 코드. 코딩 코드
 - 값

Argonaut 필드 외에도 멋진 사용자 환경을 위해 환자 앱에서는 다음 필드도 읽을 수 있습니다.

 - 코드. 표시
 - 단위

리소스 검색에서 GET 메서드 및 다음 매개 변수를 사용 합니다.

 - 환자 =\<patient id>
 - _sort =-날짜
 - 범주 ("category = 필수-서명")에서 중요 한 서명 목록을 검색 하는 방법을 쿼리 합니다.

통화에 대 한 다음 예제를 참조 하세요.

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

[https://www.hl7.org/fhir/stu3/observation.html](https://www.hl7.org/fhir/stu3/observation.html)이 필드 집합에 대 한 자세한 내용은을 참조 하세요.

## <a name="condition"></a>조건

다음은 [Argonaut condition 프로필](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html)의 하위 집합인 필요한 최소 필드입니다.

 - 코드. 코딩 [0]. 표시

Argonaut 필드 외에도 멋진 사용자 환경을 위해 환자 앱에서는 다음 필드도 읽을 수 있습니다.

 - AssertedDate
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

[https://hl7.org/fhir/stu3/condition.html](https://hl7.org/fhir/stu3/condition.html)이 필드 집합에 대 한 자세한 내용은을 참조 하세요.

## <a name="encounter"></a>문제가

[미국 핵심 발생 프로필](https://hl7.org/fhir/us/core/2018Jan/StructureDefinition-us-core-encounter.html) 의 하위 집합인 최소 필수 필드는 "필드에" 필드가 있어야 합니다. "

 - 상태
 - [0]을 입력 합니다. 코딩 [0]. 표시

또한 미국 Core 발생 프로필의 "지원 해야 하는" 필드에는 다음과 같은 필드가 있습니다.

 - 기간. 시작
 - 위치 [0]. 위치. 표시

리소스 검색에서 GET 메서드 및 다음 매개 변수를 사용 합니다.

 - 환자 =\<patient id>
 - _sort: desc =\<field ex. date>
 - _count =\<max results>

목표는 환자 마지막으로 알려진 위치를 검색할 수 있다는 것입니다. 각 발생은 위치 리소스를 참조 합니다. 또한 참조에는 위치의 표시 필드도 포함 됩니다.

[https://hl7.org/fhir/stu3/encounter.html](https://hl7.org/fhir/stu3/encounter.html)이 필드 집합에 대 한 자세한 내용은을 참조 하세요.

## <a name="allergyintolerance"></a>AllergyIntolerance

다음은 [Argonaut AllergyIntolerance](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-allergyintolerance.html) 프로필의 하위 집합인 최소 필수 필드입니다.

 - 코드. 텍스트
 - 코드. 코딩 [0]. 표시
 - ClinicalStatus/VerificationStatus (두 가지 모두 읽었습니다)

Argonaut 필드 외에도 멋진 사용자 환경을 위해 환자 앱에서 다음 필드도 읽을 수 있습니다.

 - AssertedDate
 - 참고. 텍스트
 - 반응은
    - 물질 (1 개의 코딩 요소)
    - Manifestation (1 코딩 요소)

리소스 검색에서 GET 메서드 및 다음 매개 변수를 사용 합니다.

 - 환자 =  \<patient id>

통화에 대 한 다음 예제를 참조 하세요. 

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

[https://hl7.org/fhir/stu3/allergyintolerance.html](https://hl7.org/fhir/stu3/allergyintolerance.html)이 필드 집합에 대 한 자세한 내용은을 참조 하세요.

## <a name="medication-request"></a>투약 요청

[미국 Core 투약 요청 프로필](http://www.hl7.org/fhir/us/core/StructureDefinition-us-core-medicationrequest.html)의 하위 집합인 최소 필수 필드는 다음과 같습니다.

 - 투약. 표시 (참조 하는 경우)
 - 투약 (if CodableConcept)
 - 기관 Edon
 - 요청자. 에이전트 디스플레이

멋진 사용자 환경을 위해 미국 Core 필드 외에도 환자 앱에서 다음 필드를 읽을 수 있습니다.

 - DosageInstruction[..]. 본문
 - 본문

리소스 검색에서 GET 메서드 및 다음 매개 변수를 사용 합니다.

 - 환자 =\<patient id>
 - _count =\<max results>

[https://www.hl7.org/fhir/medicationrequest.html](https://www.hl7.org/fhir/medicationrequest.html)이 필드 집합에 대 한 자세한 내용은을 참조 하세요.

## <a name="coverage"></a>통신이

미국 Core 또는 Argonaut 프로필에서 다루지 않는 최소 필수 필드는 다음과 같습니다.

 - 그룹화에서 하나 이상의 요소를 사용 하 여
    - GroupDisplay
    - 계획 표시
 - 안에
 - SubscriberId

리소스 검색에서 GET 메서드 및 다음 매개 변수를 사용 합니다.

 - 환자 = \<patient id>

[https://hl7.org/fhir/stu3/coverage.html](https://www.hl7.org/fhir/medicationrequest.html)이 필드 집합에 대 한 자세한 내용은을 참조 하세요.
