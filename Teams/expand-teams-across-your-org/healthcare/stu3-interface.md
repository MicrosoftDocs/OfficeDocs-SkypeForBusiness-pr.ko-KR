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
# <a name="stu3-interface-specification"></a><span data-ttu-id="852d8-103">STU3 인터페이스 사양</span><span class="sxs-lookup"><span data-stu-id="852d8-103">STU3 interface specification</span></span>

> [!NOTE]
> <span data-ttu-id="852d8-104">2020 년 10 월 30 일에 효력을 환자 앱이 만료 되어 팀의 [목록 앱](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) 으로 대체 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="852d8-104">Effective October 30, 2020, the Patients app has been retired and replaced by the [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) in Teams.</span></span> <span data-ttu-id="852d8-105">목록을 사용 하는 경우 의료 기관에서 팀은 팀 모임에서 일반 환자 모니터링과의 interdisciplinary에 이르기까지 시나리오에 대 한 환자 목록을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="852d8-105">With Lists, care teams in your healthcare organization can create patient lists for scenarios ranging from rounds and interdisciplinary team meetings to general patient monitoring.</span></span> <span data-ttu-id="852d8-106">목록에서 환자 서식 파일을 확인 하 여 시작 하세요.</span><span class="sxs-lookup"><span data-stu-id="852d8-106">Check out the Patients template in Lists to get started.</span></span> <span data-ttu-id="852d8-107">조직에서 목록 앱을 관리 하는 방법에 대해 자세히 알아보려면 [목록 앱 관리](../../manage-lists-app.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="852d8-107">To learn more about how to manage the Lists app in your organization, see [Manage the Lists app](../../manage-lists-app.md).</span></span>

<span data-ttu-id="852d8-108">Microsoft 팀 환자 앱을 사용 하도록 FTO r 서버를 설정 또는 재구성 하려면 앱이 액세스 해야 하는 데이터에 대 한 이해가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="852d8-108">Setting up or reconfiguring an FHIR server to work with the Microsoft Teams Patients app requires understanding what data the app needs to access.</span></span> <span data-ttu-id="852d8-109">FHIR 서버는 다음 리소스에 대해 번들을 사용 하 여 POST 요청을 지원 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="852d8-109">The FHIR server must support POST requests using bundles for the following resources:</span></span>

- [<span data-ttu-id="852d8-110">환자가</span><span class="sxs-lookup"><span data-stu-id="852d8-110">Patient</span></span>](#patient)
- [<span data-ttu-id="852d8-111">탑</span><span class="sxs-lookup"><span data-stu-id="852d8-111">Observation</span></span>](#observation)
- [<span data-ttu-id="852d8-112">조건</span><span class="sxs-lookup"><span data-stu-id="852d8-112">Condition</span></span>](#condition)
- [<span data-ttu-id="852d8-113">문제가</span><span class="sxs-lookup"><span data-stu-id="852d8-113">Encounter</span></span>](#encounter)
- [<span data-ttu-id="852d8-114">Allergy Intolerance</span><span class="sxs-lookup"><span data-stu-id="852d8-114">Allergy Intolerance</span></span>](#allergyintolerance)
- [<span data-ttu-id="852d8-115">통신이</span><span class="sxs-lookup"><span data-stu-id="852d8-115">Coverage</span></span>](#coverage)
- <span data-ttu-id="852d8-116">[투약 문](#medication-request) (DSTU2 버전의 PatientsApp에서 MedicationOrder를 대체 합니다.)</span><span class="sxs-lookup"><span data-stu-id="852d8-116">[Medication Statement](#medication-request) (replaces the MedicationOrder in the DSTU2 version of the PatientsApp)</span></span>
- <span data-ttu-id="852d8-117">위치 (이 리소스에서 필요로 하는 정보가 발생할 수 있음)</span><span class="sxs-lookup"><span data-stu-id="852d8-117">Location (the information needed from this resource can be included in Encounter)</span></span>

> [!NOTE]
> <span data-ttu-id="852d8-118">환자 리소스는 유일한 필수 리소스 (앱이 전혀 로드 되지 않는)에만 사용 됩니다. 그러나 Microsoft 팀 환자 앱을 사용 하 여 최상의 최종 사용자 환경을 제공 하기 위해 파트너는 위에서 설명한 모든 사양에 대 한 지원을 구현 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="852d8-118">The Patient resource is the only mandatory resource (without which the app will not load at all); However, it is recommended that the Partner implement support for all the above mentioned resources per specifications provided below for the best end-user experience with the Microsoft Teams Patients App.</span></span>

<span data-ttu-id="852d8-119">두 개 이상의 리소스에 대 한 Microsoft 팀 환자 앱의 쿼리는 요청에 대 한 번들 (일괄 처리)을 FTO r 서버의 URL에 게시 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="852d8-119">Queries from the Microsoft Teams Patients app for more than one resource shall post a bundle (BATCH) of requests to the FHIR server's URL.</span></span> <span data-ttu-id="852d8-120">서버는 각 요청을 처리 하 고 각 요청과 일치 하는 리소스의 번들을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="852d8-120">The server shall process each request and return a bundle of the resources matched by each request.</span></span> <span data-ttu-id="852d8-121">자세한 내용 및 예제는를 참조 하세요 [https://www.hl7.org/fhir/STU3/http.html#transaction](https://www.hl7.org/fhir/STU3/http.html#transaction) .</span><span class="sxs-lookup"><span data-stu-id="852d8-121">For more information and examples, see [https://www.hl7.org/fhir/STU3/http.html#transaction](https://www.hl7.org/fhir/STU3/http.html#transaction).</span></span>

## <a name="capability-statement"></a><span data-ttu-id="852d8-122">역량 명세서</span><span class="sxs-lookup"><span data-stu-id="852d8-122">Capability Statement</span></span>

<span data-ttu-id="852d8-123">최소 필수 필드는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="852d8-123">These are the minimum required fields:</span></span>

 - <span data-ttu-id="852d8-124">받침대</span><span class="sxs-lookup"><span data-stu-id="852d8-124">REST</span></span>

    - <span data-ttu-id="852d8-125">모드</span><span class="sxs-lookup"><span data-stu-id="852d8-125">Mode</span></span>
    - <span data-ttu-id="852d8-126">개입</span><span class="sxs-lookup"><span data-stu-id="852d8-126">Interaction</span></span>
    - <span data-ttu-id="852d8-127">자원: 종류</span><span class="sxs-lookup"><span data-stu-id="852d8-127">Resource: Type</span></span>
    - <span data-ttu-id="852d8-128">보안: [OAuth uri 용 확장](https://hl7.org/fhir/extension-oauth-uris.html)</span><span class="sxs-lookup"><span data-stu-id="852d8-128">Security: [Extension for OAuth URIs](https://hl7.org/fhir/extension-oauth-uris.html)</span></span>
    
 - <span data-ttu-id="852d8-129">Fto Rversion (코드에는 어떤 버전을 피벗할 것인지 이해 하기 위해 필요 합니다.)</span><span class="sxs-lookup"><span data-stu-id="852d8-129">FhirVersion (Our code requires this to understand which version we should pivot to.)</span></span>

<span data-ttu-id="852d8-130">[https://www.hl7.org/fhir/stu3/capabilitystatement.html](https://www.hl7.org/fhir/stu3/capabilitystatement.html)이 필드 집합에 대 한 자세한 내용은을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="852d8-130">See [https://www.hl7.org/fhir/stu3/capabilitystatement.html](https://www.hl7.org/fhir/stu3/capabilitystatement.html) for other details on this field set.</span></span>

## <a name="patient"></a><span data-ttu-id="852d8-131">환자가</span><span class="sxs-lookup"><span data-stu-id="852d8-131">Patient</span></span>

<span data-ttu-id="852d8-132">다음은 Argonaut 환자 프로필 필드의 하위 집합인 최소 필수 필드입니다.</span><span class="sxs-lookup"><span data-stu-id="852d8-132">Here are the minimum required fields, which are a subset of the Argonaut patient profile fields:</span></span>

 - <span data-ttu-id="852d8-133">Name. 지정 된</span><span class="sxs-lookup"><span data-stu-id="852d8-133">Name.Given</span></span>
 - <span data-ttu-id="852d8-134">패밀리 이름</span><span class="sxs-lookup"><span data-stu-id="852d8-134">Name.Family</span></span>
 - <span data-ttu-id="852d8-135">성별을</span><span class="sxs-lookup"><span data-stu-id="852d8-135">Gender</span></span>
 - <span data-ttu-id="852d8-136">생년월일</span><span class="sxs-lookup"><span data-stu-id="852d8-136">BirthDate</span></span>
 - <span data-ttu-id="852d8-137">MRN (Identifier)</span><span class="sxs-lookup"><span data-stu-id="852d8-137">MRN (Identifier)</span></span>

<span data-ttu-id="852d8-138">[Argonaut 필드](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html)외에도 멋진 사용자 환경을 위해 환자 앱에서는 다음 필드도 읽을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="852d8-138">In addition to the [Argonaut fields](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html), for a great user experience the Patients app can also read the following fields:</span></span>

 - <span data-ttu-id="852d8-139">이름을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="852d8-139">Name.Use</span></span>
 - <span data-ttu-id="852d8-140">Name. 접두사</span><span class="sxs-lookup"><span data-stu-id="852d8-140">Name.Prefix</span></span>
 - <span data-ttu-id="852d8-141">[GeneralPractitioner]-GeneralPractitioner 참조는 환자 리소스 (표시 필드에만 해당)에 포함 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="852d8-141">[GeneralPractitioner] - The GeneralPractitioner reference should be included in the Patient resource (display field only)</span></span>

<span data-ttu-id="852d8-142">리소스 검색에서는/Patient/_search 및 다음 매개 변수에 POST 메서드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="852d8-142">A resource search uses the POST method at /Patient/_search and the following parameters:</span></span>

 - <span data-ttu-id="852d8-143">i</span><span class="sxs-lookup"><span data-stu-id="852d8-143">id</span></span>
 - <span data-ttu-id="852d8-144">family = (가족 이름에 값이 포함 되어 있는 모든 환자 검색)</span><span class="sxs-lookup"><span data-stu-id="852d8-144">family=(searches for all patients whose family name contains the value)</span></span>
 - <span data-ttu-id="852d8-145">지정 =\<substring></span><span class="sxs-lookup"><span data-stu-id="852d8-145">given=\<substring></span></span>
 - <span data-ttu-id="852d8-146">생년월일 = (정확한 일치)</span><span class="sxs-lookup"><span data-stu-id="852d8-146">birthdate=(exact match)</span></span>
 - <span data-ttu-id="852d8-147">성별 = (관리자 성별 중 하나에 해당 하는 값)</span><span class="sxs-lookup"><span data-stu-id="852d8-147">gender=(values being one of the administrative-gender)</span></span>
 - <span data-ttu-id="852d8-148">\_count (반환 해야 하는 최대 결과 수)</span><span class="sxs-lookup"><span data-stu-id="852d8-148">\_count (maximum number of results that should be returned)</span></span> <br> <span data-ttu-id="852d8-149">응답에는 검색 결과에 따라 반환 되는 레코드의 총 개수가 포함 되어야 하며 \_ 반환 되는 레코드 수를 제한 하기 위해 PatientsApp에서 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="852d8-149">The response should contain the total count of records returned as a result of the search and \_count will be used by the PatientsApp to limit the number of records returned.</span></span>
 - <span data-ttu-id="852d8-150">identifier =\<mrn></span><span class="sxs-lookup"><span data-stu-id="852d8-150">identifier=\<mrn></span></span>

<span data-ttu-id="852d8-151">목표는 다음을 수행 하 여 환자를 검색 하 고 필터링 할 수 있다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="852d8-151">The goal is to be able to search and filter for a patient by the following:</span></span>

- <span data-ttu-id="852d8-152">ID:이는 모든 자원의 모든 리소스에 있는 자원 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="852d8-152">ID: This is the resource ID that every resource in FHIR has.</span></span>
- <span data-ttu-id="852d8-153">MRN이는 임상 직원이 알고 있는 환자에 대 한 실제 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="852d8-153">MRN: This is the actual identifier for the patient that clinical staff would know.</span></span> <span data-ttu-id="852d8-154">이 MRN는 FA r의 식별자 리소스 내에 있는 식별자 유형을 기반으로 이해 합니다.</span><span class="sxs-lookup"><span data-stu-id="852d8-154">We understand this MRN is based on the type of identifier inside the identifier resource in FHIR.</span></span>
- <span data-ttu-id="852d8-155">이름</span><span class="sxs-lookup"><span data-stu-id="852d8-155">Name</span></span>
- <span data-ttu-id="852d8-156">생년월일</span><span class="sxs-lookup"><span data-stu-id="852d8-156">Birthdate</span></span>

<span data-ttu-id="852d8-157">통화에 대 한 다음 예제를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="852d8-157">See the following example of the call:</span></span>

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

<span data-ttu-id="852d8-158">[https://hl7.org/fhir/stu3/patient.html](https://hl7.org/fhir/stu3/patient.html)이 필드 집합에 대 한 자세한 내용은을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="852d8-158">See [https://hl7.org/fhir/stu3/patient.html](https://hl7.org/fhir/stu3/patient.html) for other details on this field set.</span></span>

## <a name="observation"></a><span data-ttu-id="852d8-159">탑</span><span class="sxs-lookup"><span data-stu-id="852d8-159">Observation</span></span>

<span data-ttu-id="852d8-160">[Argonaut Vital-Signs 프로필](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-vitalsigns.html)의 하위 집합인 최소 필수 필드입니다.</span><span class="sxs-lookup"><span data-stu-id="852d8-160">These are the minimum required fields, which are a subset of the [Argonaut Vital-Signs profile](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-vitalsigns.html).</span></span>

 - <span data-ttu-id="852d8-161">유효 (날짜 시간 또는 기간)</span><span class="sxs-lookup"><span data-stu-id="852d8-161">Effective (date time or period)</span></span>
 - <span data-ttu-id="852d8-162">코드. 코딩 코드</span><span class="sxs-lookup"><span data-stu-id="852d8-162">Code.Coding.Code</span></span>
 - <span data-ttu-id="852d8-163">값</span><span class="sxs-lookup"><span data-stu-id="852d8-163">ValueQuantity.Value</span></span>

<span data-ttu-id="852d8-164">Argonaut 필드 외에도 멋진 사용자 환경을 위해 환자 앱에서는 다음 필드도 읽을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="852d8-164">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following fields:</span></span>

 - <span data-ttu-id="852d8-165">코드. 표시</span><span class="sxs-lookup"><span data-stu-id="852d8-165">Code.Coding.Display</span></span>
 - <span data-ttu-id="852d8-166">단위</span><span class="sxs-lookup"><span data-stu-id="852d8-166">ValueQuantity.Unit</span></span>

<span data-ttu-id="852d8-167">리소스 검색에서 GET 메서드 및 다음 매개 변수를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="852d8-167">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="852d8-168">환자 =\<patient id></span><span class="sxs-lookup"><span data-stu-id="852d8-168">patient=\<patient id></span></span>
 - <span data-ttu-id="852d8-169">_sort =-날짜</span><span class="sxs-lookup"><span data-stu-id="852d8-169">_sort=-date</span></span>
 - <span data-ttu-id="852d8-170">범주 ("category = 필수-서명")에서 중요 한 서명 목록을 검색 하는 방법을 쿼리 합니다.</span><span class="sxs-lookup"><span data-stu-id="852d8-170">category (we will query for "category=vital-signs") to retrieve the list of vital signs.</span></span>

<span data-ttu-id="852d8-171">통화에 대 한 다음 예제를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="852d8-171">Refer to this example of the call:</span></span>

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

<span data-ttu-id="852d8-172">[https://www.hl7.org/fhir/stu3/observation.html](https://www.hl7.org/fhir/stu3/observation.html)이 필드 집합에 대 한 자세한 내용은을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="852d8-172">See [https://www.hl7.org/fhir/stu3/observation.html](https://www.hl7.org/fhir/stu3/observation.html) for other details on this field set.</span></span>

## <a name="condition"></a><span data-ttu-id="852d8-173">조건</span><span class="sxs-lookup"><span data-stu-id="852d8-173">Condition</span></span>

<span data-ttu-id="852d8-174">다음은 [Argonaut condition 프로필](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html)의 하위 집합인 필요한 최소 필드입니다.</span><span class="sxs-lookup"><span data-stu-id="852d8-174">Here's the minimum required fields, which are a subset of the [Argonaut condition profile](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html).</span></span>

 - <span data-ttu-id="852d8-175">코드. 코딩 [0]. 표시</span><span class="sxs-lookup"><span data-stu-id="852d8-175">Code.Coding[0].Display</span></span>

<span data-ttu-id="852d8-176">Argonaut 필드 외에도 멋진 사용자 환경을 위해 환자 앱에서는 다음 필드도 읽을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="852d8-176">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following fields:</span></span>

 - <span data-ttu-id="852d8-177">AssertedDate</span><span class="sxs-lookup"><span data-stu-id="852d8-177">AssertedDate</span></span>
 - <span data-ttu-id="852d8-178">문제의</span><span class="sxs-lookup"><span data-stu-id="852d8-178">Severity</span></span>

<span data-ttu-id="852d8-179">리소스 검색에서 GET 메서드 및 다음 매개 변수를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="852d8-179">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="852d8-180">환자 =\<patient id></span><span class="sxs-lookup"><span data-stu-id="852d8-180">patient=\<patient id></span></span>
 - <span data-ttu-id="852d8-181">_count =\<max results></span><span class="sxs-lookup"><span data-stu-id="852d8-181">_count=\<max results></span></span>

<span data-ttu-id="852d8-182">이 통화의 다음 예제를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="852d8-182">See the following example of this call:</span></span>

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

<span data-ttu-id="852d8-183">[https://hl7.org/fhir/stu3/condition.html](https://hl7.org/fhir/stu3/condition.html)이 필드 집합에 대 한 자세한 내용은을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="852d8-183">See [https://hl7.org/fhir/stu3/condition.html](https://hl7.org/fhir/stu3/condition.html) for other details on this field set.</span></span>

## <a name="encounter"></a><span data-ttu-id="852d8-184">문제가</span><span class="sxs-lookup"><span data-stu-id="852d8-184">Encounter</span></span>

<span data-ttu-id="852d8-185">[미국 핵심 발생 프로필](https://hl7.org/fhir/us/core/2018Jan/StructureDefinition-us-core-encounter.html) 의 하위 집합인 최소 필수 필드는 "필드에" 필드가 있어야 합니다. "</span><span class="sxs-lookup"><span data-stu-id="852d8-185">These are the minimum required fields, which are a subset of the [US Core Encounter profile](https://hl7.org/fhir/us/core/2018Jan/StructureDefinition-us-core-encounter.html) "must have" fields).</span></span>

 - <span data-ttu-id="852d8-186">상태</span><span class="sxs-lookup"><span data-stu-id="852d8-186">Status</span></span>
 - <span data-ttu-id="852d8-187">[0]을 입력 합니다. 코딩 [0]. 표시</span><span class="sxs-lookup"><span data-stu-id="852d8-187">Type[0].Coding[0].Display</span></span>

<span data-ttu-id="852d8-188">또한 미국 Core 발생 프로필의 "지원 해야 하는" 필드에는 다음과 같은 필드가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="852d8-188">In addition, the following fields from US Core Encounter profile's "must support" fields:</span></span>

 - <span data-ttu-id="852d8-189">기간. 시작</span><span class="sxs-lookup"><span data-stu-id="852d8-189">Period.Start</span></span>
 - <span data-ttu-id="852d8-190">위치 [0]. 위치. 표시</span><span class="sxs-lookup"><span data-stu-id="852d8-190">Location[0].Location.Display</span></span>

<span data-ttu-id="852d8-191">리소스 검색에서 GET 메서드 및 다음 매개 변수를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="852d8-191">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="852d8-192">환자 =\<patient id></span><span class="sxs-lookup"><span data-stu-id="852d8-192">patient=\<patient id></span></span>
 - <span data-ttu-id="852d8-193">_sort: desc =\<field ex. date></span><span class="sxs-lookup"><span data-stu-id="852d8-193">_sort:desc=\<field ex. date></span></span>
 - <span data-ttu-id="852d8-194">_count =\<max results></span><span class="sxs-lookup"><span data-stu-id="852d8-194">_count=\<max results></span></span>

<span data-ttu-id="852d8-195">목표는 환자 마지막으로 알려진 위치를 검색할 수 있다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="852d8-195">The goal is to be able to retrieve the patient's last known location.</span></span> <span data-ttu-id="852d8-196">각 발생은 위치 리소스를 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="852d8-196">Each encounter references a location resource.</span></span> <span data-ttu-id="852d8-197">또한 참조에는 위치의 표시 필드도 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="852d8-197">The reference shall also include the location's display field.</span></span>

<span data-ttu-id="852d8-198">[https://hl7.org/fhir/stu3/encounter.html](https://hl7.org/fhir/stu3/encounter.html)이 필드 집합에 대 한 자세한 내용은을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="852d8-198">See [https://hl7.org/fhir/stu3/encounter.html](https://hl7.org/fhir/stu3/encounter.html) for other details on this field set.</span></span>

## <a name="allergyintolerance"></a><span data-ttu-id="852d8-199">AllergyIntolerance</span><span class="sxs-lookup"><span data-stu-id="852d8-199">AllergyIntolerance</span></span>

<span data-ttu-id="852d8-200">다음은 [Argonaut AllergyIntolerance](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-allergyintolerance.html) 프로필의 하위 집합인 최소 필수 필드입니다.</span><span class="sxs-lookup"><span data-stu-id="852d8-200">These are the minimum required fields, which are a subset of the [Argonaut AllergyIntolerance](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-allergyintolerance.html) profile:</span></span>

 - <span data-ttu-id="852d8-201">코드. 텍스트</span><span class="sxs-lookup"><span data-stu-id="852d8-201">Code.Text</span></span>
 - <span data-ttu-id="852d8-202">코드. 코딩 [0]. 표시</span><span class="sxs-lookup"><span data-stu-id="852d8-202">Code.Coding[0].Display</span></span>
 - <span data-ttu-id="852d8-203">ClinicalStatus/VerificationStatus (두 가지 모두 읽었습니다)</span><span class="sxs-lookup"><span data-stu-id="852d8-203">ClinicalStatus/VerificationStatus (we read both)</span></span>

<span data-ttu-id="852d8-204">Argonaut 필드 외에도 멋진 사용자 환경을 위해 환자 앱에서 다음 필드도 읽을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="852d8-204">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following field:</span></span>

 - <span data-ttu-id="852d8-205">AssertedDate</span><span class="sxs-lookup"><span data-stu-id="852d8-205">AssertedDate</span></span>
 - <span data-ttu-id="852d8-206">참고. 텍스트</span><span class="sxs-lookup"><span data-stu-id="852d8-206">Note.Text</span></span>
 - <span data-ttu-id="852d8-207">반응은</span><span class="sxs-lookup"><span data-stu-id="852d8-207">Reaction</span></span>
    - <span data-ttu-id="852d8-208">물질 (1 개의 코딩 요소)</span><span class="sxs-lookup"><span data-stu-id="852d8-208">Substance (one coding element)</span></span>
    - <span data-ttu-id="852d8-209">Manifestation (1 코딩 요소)</span><span class="sxs-lookup"><span data-stu-id="852d8-209">Manifestation (one coding element)</span></span>

<span data-ttu-id="852d8-210">리소스 검색에서 GET 메서드 및 다음 매개 변수를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="852d8-210">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="852d8-211">환자 =  \<patient id></span><span class="sxs-lookup"><span data-stu-id="852d8-211">Patient =  \<patient id></span></span>

<span data-ttu-id="852d8-212">통화에 대 한 다음 예제를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="852d8-212">See the following example of the call:</span></span> 

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

<span data-ttu-id="852d8-213">[https://hl7.org/fhir/stu3/allergyintolerance.html](https://hl7.org/fhir/stu3/allergyintolerance.html)이 필드 집합에 대 한 자세한 내용은을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="852d8-213">See [https://hl7.org/fhir/stu3/allergyintolerance.html](https://hl7.org/fhir/stu3/allergyintolerance.html) for other details on this field set.</span></span>

## <a name="medication-request"></a><span data-ttu-id="852d8-214">투약 요청</span><span class="sxs-lookup"><span data-stu-id="852d8-214">Medication Request</span></span>

<span data-ttu-id="852d8-215">[미국 Core 투약 요청 프로필](http://www.hl7.org/fhir/us/core/StructureDefinition-us-core-medicationrequest.html)의 하위 집합인 최소 필수 필드는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="852d8-215">These are the minimum required fields, which are a subset of the [US Core Medication Request profile](http://www.hl7.org/fhir/us/core/StructureDefinition-us-core-medicationrequest.html):</span></span>

 - <span data-ttu-id="852d8-216">투약. 표시 (참조 하는 경우)</span><span class="sxs-lookup"><span data-stu-id="852d8-216">Medication.Display (if Reference)</span></span>
 - <span data-ttu-id="852d8-217">투약 (if CodableConcept)</span><span class="sxs-lookup"><span data-stu-id="852d8-217">Medication.Text (if CodableConcept)</span></span>
 - <span data-ttu-id="852d8-218">기관 Edon</span><span class="sxs-lookup"><span data-stu-id="852d8-218">AuthoredOn</span></span>
 - <span data-ttu-id="852d8-219">요청자. 에이전트 디스플레이</span><span class="sxs-lookup"><span data-stu-id="852d8-219">Requester.Agent.Display</span></span>

<span data-ttu-id="852d8-220">멋진 사용자 환경을 위해 미국 Core 필드 외에도 환자 앱에서 다음 필드를 읽을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="852d8-220">In addition to the US Core fields, for a great user experience the Patients app can also read the following fields:</span></span>

 - <span data-ttu-id="852d8-221">DosageInstruction[..]. 본문</span><span class="sxs-lookup"><span data-stu-id="852d8-221">DosageInstruction[..].Text</span></span>
 - <span data-ttu-id="852d8-222">본문</span><span class="sxs-lookup"><span data-stu-id="852d8-222">Text</span></span>

<span data-ttu-id="852d8-223">리소스 검색에서 GET 메서드 및 다음 매개 변수를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="852d8-223">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="852d8-224">환자 =\<patient id></span><span class="sxs-lookup"><span data-stu-id="852d8-224">patient=\<patient id></span></span>
 - <span data-ttu-id="852d8-225">_count =\<max results></span><span class="sxs-lookup"><span data-stu-id="852d8-225">_count=\<max results></span></span>

<span data-ttu-id="852d8-226">[https://www.hl7.org/fhir/medicationrequest.html](https://www.hl7.org/fhir/medicationrequest.html)이 필드 집합에 대 한 자세한 내용은을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="852d8-226">See [https://www.hl7.org/fhir/medicationrequest.html](https://www.hl7.org/fhir/medicationrequest.html) for other details on this field set.</span></span>

## <a name="coverage"></a><span data-ttu-id="852d8-227">통신이</span><span class="sxs-lookup"><span data-stu-id="852d8-227">Coverage</span></span>

<span data-ttu-id="852d8-228">미국 Core 또는 Argonaut 프로필에서 다루지 않는 최소 필수 필드는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="852d8-228">These are the minimum required fields, not covered by either US Core or Argonaut profiles:</span></span>

 - <span data-ttu-id="852d8-229">그룹화에서 하나 이상의 요소를 사용 하 여</span><span class="sxs-lookup"><span data-stu-id="852d8-229">Grouping, at least one element with</span></span>
    - <span data-ttu-id="852d8-230">GroupDisplay</span><span class="sxs-lookup"><span data-stu-id="852d8-230">GroupDisplay</span></span>
    - <span data-ttu-id="852d8-231">계획 표시</span><span class="sxs-lookup"><span data-stu-id="852d8-231">PlanDisplay</span></span>
 - <span data-ttu-id="852d8-232">안에</span><span class="sxs-lookup"><span data-stu-id="852d8-232">Period</span></span>
 - <span data-ttu-id="852d8-233">SubscriberId</span><span class="sxs-lookup"><span data-stu-id="852d8-233">SubscriberId</span></span>

<span data-ttu-id="852d8-234">리소스 검색에서 GET 메서드 및 다음 매개 변수를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="852d8-234">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="852d8-235">환자 = \<patient id></span><span class="sxs-lookup"><span data-stu-id="852d8-235">Patient = \<patient id></span></span>

<span data-ttu-id="852d8-236">[https://hl7.org/fhir/stu3/coverage.html](https://www.hl7.org/fhir/medicationrequest.html)이 필드 집합에 대 한 자세한 내용은을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="852d8-236">See [https://hl7.org/fhir/stu3/coverage.html](https://www.hl7.org/fhir/medicationrequest.html) for other details on this field set.</span></span>
