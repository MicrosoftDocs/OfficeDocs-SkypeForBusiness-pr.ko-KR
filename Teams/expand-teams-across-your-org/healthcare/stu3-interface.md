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
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
appliesto:
- Microsoft Teams
ms.reviewer: anach
description: Electronic Health Records를 환자 앱과 STU3 인터페이스 Microsoft Teams 통합하는 방법을 알아보고
ms.custom: seo-marvel-apr2020
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 4e20619badb2509d0a90f396563a98796e718e2f
ms.sourcegitcommit: beaaee10019f4eda746f348888a4a3c2aaa6f196
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2020
ms.locfileid: "48803496"
---
# <a name="stu3-interface-specification"></a><span data-ttu-id="0a8d5-103">STU3 인터페이스 사양</span><span class="sxs-lookup"><span data-stu-id="0a8d5-103">STU3 interface specification</span></span>

> [!NOTE]
> <span data-ttu-id="0a8d5-104">2020년 10월 30일부터 환자 앱이 폐기되고 Teams 내 [목록 앱](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db)으로 대체되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0a8d5-104">Effective October 30, 2020, the Patients app has been retired and replaced by the [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) in Teams.</span></span> <span data-ttu-id="0a8d5-105">환자 앱 데이터는 팀을 백업하는 Office 365 그룹의 그룹 사서함에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="0a8d5-105">Patients app data is stored in the group mailbox of the Office 365 group that backs the team.</span></span> <span data-ttu-id="0a8d5-106">환자 앱과 연결된 모든 데이터는 이 그룹에 보존되지만 사용자 인터페이스를 통해 더 이상 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0a8d5-106">All data associated with the Patients app is retained in this group but can no longer be accessed through the user interface.</span></span> <span data-ttu-id="0a8d5-107">사용자는 [목록 앱](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db)을 사용하여 목록을 다시 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0a8d5-107">Users can re-create their lists using the [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db).</span></span>
>
><span data-ttu-id="0a8d5-108">목록 기능을 사용하면 의료 조직의 관리 팀은 라운드 및 분야별 팀 모임에서 일반 환자 모니터링에 이르는 다양한 시나리오에 대한 환자 목록을 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0a8d5-108">With Lists, care teams in your healthcare organization can create patient lists for scenarios ranging from rounds and interdisciplinary team meetings to general patient monitoring.</span></span> <span data-ttu-id="0a8d5-109">시작을 위해 목록에서 환자 서식 파일을 체크 아웃합니다.</span><span class="sxs-lookup"><span data-stu-id="0a8d5-109">Check out the Patients template in Lists to get started.</span></span> <span data-ttu-id="0a8d5-110">조직에서 목록 앱을 관리하는 방법에 대한 자세한 내용은 [목록 앱 관리](../../manage-lists-app.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0a8d5-110">To learn more about how to manage the Lists app in your organization, see [Manage the Lists app](../../manage-lists-app.md).</span></span>

<span data-ttu-id="0a8d5-111">환자 앱과 함께 작동하기 위해 FHIR 서버를 설정하거나 Microsoft Teams 앱에 액세스하는 데 필요한 데이터를 이해해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0a8d5-111">Setting up or reconfiguring an FHIR server to work with the Microsoft Teams Patients app requires understanding what data the app needs to access.</span></span> <span data-ttu-id="0a8d5-112">FHIR 서버는 다음 리소스에 대한 번들을 사용하여 POST 요청을 지원해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0a8d5-112">The FHIR server must support POST requests using bundles for the following resources:</span></span>

- [<span data-ttu-id="0a8d5-113">환자</span><span class="sxs-lookup"><span data-stu-id="0a8d5-113">Patient</span></span>](#patient)
- [<span data-ttu-id="0a8d5-114">관찰</span><span class="sxs-lookup"><span data-stu-id="0a8d5-114">Observation</span></span>](#observation)
- [<span data-ttu-id="0a8d5-115">조건</span><span class="sxs-lookup"><span data-stu-id="0a8d5-115">Condition</span></span>](#condition)
- [<span data-ttu-id="0a8d5-116">발생</span><span class="sxs-lookup"><span data-stu-id="0a8d5-116">Encounter</span></span>](#encounter)
- [<span data-ttu-id="0a8d5-117">알레르기 내성</span><span class="sxs-lookup"><span data-stu-id="0a8d5-117">Allergy Intolerance</span></span>](#allergyintolerance)
- [<span data-ttu-id="0a8d5-118">적용 범위</span><span class="sxs-lookup"><span data-stu-id="0a8d5-118">Coverage</span></span>](#coverage)
- <span data-ttu-id="0a8d5-119">[약물 치료](#medication-request) 문(PatientsApp의 DSTU2 버전에서 MedicationOrder 대체)</span><span class="sxs-lookup"><span data-stu-id="0a8d5-119">[Medication Statement](#medication-request) (replaces the MedicationOrder in the DSTU2 version of the PatientsApp)</span></span>
- <span data-ttu-id="0a8d5-120">위치(이 리소스에서 필요한 정보는 발생에 포함될 수 있습니다)</span><span class="sxs-lookup"><span data-stu-id="0a8d5-120">Location (the information needed from this resource can be included in Encounter)</span></span>

> [!NOTE]
> <span data-ttu-id="0a8d5-121">환자 리소스는 유일한 필수 리소스입니다(앱이 로드되지 않습니다). 그러나 파트너는 아래 제공된 사양에 따라 위에서 언급한 모든 리소스에 대한 지원을 구현하여 환자 앱의 최상의 최종 사용자 환경을 Microsoft Teams 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="0a8d5-121">The Patient resource is the only mandatory resource (without which the app will not load at all); However, it is recommended that the Partner implement support for all the above mentioned resources per specifications provided below for the best end-user experience with the Microsoft Teams Patients App.</span></span>

<span data-ttu-id="0a8d5-122">두 개 Microsoft Teams 환자 앱의 쿼리는 FHIR 서버의 URL에 요청의 번들(BATCH)을 게시해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0a8d5-122">Queries from the Microsoft Teams Patients app for more than one resource shall post a bundle (BATCH) of requests to the FHIR server's URL.</span></span> <span data-ttu-id="0a8d5-123">서버는 각 요청을 처리하고 각 요청에 일치하는 리소스 번들을 반환해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0a8d5-123">The server shall process each request and return a bundle of the resources matched by each request.</span></span> <span data-ttu-id="0a8d5-124">자세한 정보 및 예제는 [https://www.hl7.org/fhir/STU3/http.html#transaction](https://www.hl7.org/fhir/STU3/http.html#transaction) 를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0a8d5-124">For more information and examples, see [https://www.hl7.org/fhir/STU3/http.html#transaction](https://www.hl7.org/fhir/STU3/http.html#transaction).</span></span>

## <a name="capability-statement"></a><span data-ttu-id="0a8d5-125">기능 문</span><span class="sxs-lookup"><span data-stu-id="0a8d5-125">Capability Statement</span></span>

<span data-ttu-id="0a8d5-126">필요한 최소 필드는 다음입니다.</span><span class="sxs-lookup"><span data-stu-id="0a8d5-126">These are the minimum required fields:</span></span>

 - <span data-ttu-id="0a8d5-127">REST</span><span class="sxs-lookup"><span data-stu-id="0a8d5-127">REST</span></span>

    - <span data-ttu-id="0a8d5-128">모드</span><span class="sxs-lookup"><span data-stu-id="0a8d5-128">Mode</span></span>
    - <span data-ttu-id="0a8d5-129">상호 작용</span><span class="sxs-lookup"><span data-stu-id="0a8d5-129">Interaction</span></span>
    - <span data-ttu-id="0a8d5-130">리소스: 형식</span><span class="sxs-lookup"><span data-stu-id="0a8d5-130">Resource: Type</span></span>
    - <span data-ttu-id="0a8d5-131">보안: [OAuth URIS 확장](https://hl7.org/fhir/extension-oauth-uris.html)</span><span class="sxs-lookup"><span data-stu-id="0a8d5-131">Security: [Extension for OAuth URIs](https://hl7.org/fhir/extension-oauth-uris.html)</span></span>
    
 - <span data-ttu-id="0a8d5-132">FhirVersion(이 코드에서는 피벗해야 하는 버전을 이해해야 합니다.)</span><span class="sxs-lookup"><span data-stu-id="0a8d5-132">FhirVersion (Our code requires this to understand which version we should pivot to.)</span></span>

<span data-ttu-id="0a8d5-133">이 [https://www.hl7.org/fhir/stu3/capabilitystatement.html](https://www.hl7.org/fhir/stu3/capabilitystatement.html) 필드 집합에 대한 기타 세부 정보는 를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="0a8d5-133">See [https://www.hl7.org/fhir/stu3/capabilitystatement.html](https://www.hl7.org/fhir/stu3/capabilitystatement.html) for other details on this field set.</span></span>

## <a name="patient"></a><span data-ttu-id="0a8d5-134">환자</span><span class="sxs-lookup"><span data-stu-id="0a8d5-134">Patient</span></span>

<span data-ttu-id="0a8d5-135">Argonaut 환자 프로필 필드의 하위 집합인 최소 필수 필드는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="0a8d5-135">Here are the minimum required fields, which are a subset of the Argonaut patient profile fields:</span></span>

 - <span data-ttu-id="0a8d5-136">Name.Given</span><span class="sxs-lookup"><span data-stu-id="0a8d5-136">Name.Given</span></span>
 - <span data-ttu-id="0a8d5-137">Name.Family</span><span class="sxs-lookup"><span data-stu-id="0a8d5-137">Name.Family</span></span>
 - <span data-ttu-id="0a8d5-138">성별</span><span class="sxs-lookup"><span data-stu-id="0a8d5-138">Gender</span></span>
 - <span data-ttu-id="0a8d5-139">BirthDate</span><span class="sxs-lookup"><span data-stu-id="0a8d5-139">BirthDate</span></span>
 - <span data-ttu-id="0a8d5-140">MRN(식별자)</span><span class="sxs-lookup"><span data-stu-id="0a8d5-140">MRN (Identifier)</span></span>

<span data-ttu-id="0a8d5-141">[Argonaut](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html)필드 외에도, 훌륭한 사용자 환경을 위해 Patients 앱이 다음 필드를 읽을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0a8d5-141">In addition to the [Argonaut fields](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html), for a great user experience the Patients app can also read the following fields:</span></span>

 - <span data-ttu-id="0a8d5-142">Name.Use</span><span class="sxs-lookup"><span data-stu-id="0a8d5-142">Name.Use</span></span>
 - <span data-ttu-id="0a8d5-143">Name.Prefix</span><span class="sxs-lookup"><span data-stu-id="0a8d5-143">Name.Prefix</span></span>
 - <span data-ttu-id="0a8d5-144">[GeneralPractitioner] - GeneralPractitioner 참조가 환자 리소스에 포함되어야 합니다(표시 필드만 해당)</span><span class="sxs-lookup"><span data-stu-id="0a8d5-144">[GeneralPractitioner] - The GeneralPractitioner reference should be included in the Patient resource (display field only)</span></span>

<span data-ttu-id="0a8d5-145">리소스 검색은 /Patient/_search 및 다음 매개 변수에서 POST 메서드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="0a8d5-145">A resource search uses the POST method at /Patient/_search and the following parameters:</span></span>

 - <span data-ttu-id="0a8d5-146">id</span><span class="sxs-lookup"><span data-stu-id="0a8d5-146">id</span></span>
 - <span data-ttu-id="0a8d5-147">family=(가족 이름이 값을 포함하는 모든 환자를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="0a8d5-147">family=(searches for all patients whose family name contains the value)</span></span>
 - <span data-ttu-id="0a8d5-148">given=\<substring></span><span class="sxs-lookup"><span data-stu-id="0a8d5-148">given=\<substring></span></span>
 - <span data-ttu-id="0a8d5-149">birthdate=(정확한 일치)</span><span class="sxs-lookup"><span data-stu-id="0a8d5-149">birthdate=(exact match)</span></span>
 - <span data-ttu-id="0a8d5-150">gender=(값이 관리-성별 중 하나인 값)</span><span class="sxs-lookup"><span data-stu-id="0a8d5-150">gender=(values being one of the administrative-gender)</span></span>
 - <span data-ttu-id="0a8d5-151">\_count(반환해야 하는 최대 결과 수)</span><span class="sxs-lookup"><span data-stu-id="0a8d5-151">\_count (maximum number of results that should be returned)</span></span> <br> <span data-ttu-id="0a8d5-152">응답에는 검색 결과로 반환된 레코드의 총 수가 포함되어야 합니다. 반환된 레코드 수를 제한하기 위해 PatientsApp에서 사용할 수 \_ 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0a8d5-152">The response should contain the total count of records returned as a result of the search and \_count will be used by the PatientsApp to limit the number of records returned.</span></span>
 - <span data-ttu-id="0a8d5-153">식별자=\<mrn></span><span class="sxs-lookup"><span data-stu-id="0a8d5-153">identifier=\<mrn></span></span>

<span data-ttu-id="0a8d5-154">목표는 다음을 통해 환자를 검색하고 필터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0a8d5-154">The goal is to be able to search and filter for a patient by the following:</span></span>

- <span data-ttu-id="0a8d5-155">ID: FHIR의 모든 리소스가 있는 리소스 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="0a8d5-155">ID: This is the resource ID that every resource in FHIR has.</span></span>
- <span data-ttu-id="0a8d5-156">MRN: 이것은 임상 직원이 알고 있는 환자의 실제 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="0a8d5-156">MRN: This is the actual identifier for the patient that clinical staff would know.</span></span> <span data-ttu-id="0a8d5-157">이 MRN은 FHIR의 식별자 리소스 내부 식별자 유형을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="0a8d5-157">We understand this MRN is based on the type of identifier inside the identifier resource in FHIR.</span></span>
- <span data-ttu-id="0a8d5-158">이름</span><span class="sxs-lookup"><span data-stu-id="0a8d5-158">Name</span></span>
- <span data-ttu-id="0a8d5-159">Birthdate</span><span class="sxs-lookup"><span data-stu-id="0a8d5-159">Birthdate</span></span>

<span data-ttu-id="0a8d5-160">호출의 다음 예제를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="0a8d5-160">See the following example of the call:</span></span>

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

<span data-ttu-id="0a8d5-161">이 [https://hl7.org/fhir/stu3/patient.html](https://hl7.org/fhir/stu3/patient.html) 필드 집합에 대한 기타 세부 정보는 를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="0a8d5-161">See [https://hl7.org/fhir/stu3/patient.html](https://hl7.org/fhir/stu3/patient.html) for other details on this field set.</span></span>

## <a name="observation"></a><span data-ttu-id="0a8d5-162">관찰</span><span class="sxs-lookup"><span data-stu-id="0a8d5-162">Observation</span></span>

<span data-ttu-id="0a8d5-163">이 필드는 [Argonaut](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-vitalsigns.html)프로필의 하위 집합인 최소 Vital-Signs 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0a8d5-163">These are the minimum required fields, which are a subset of the [Argonaut Vital-Signs profile](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-vitalsigns.html).</span></span>

 - <span data-ttu-id="0a8d5-164">유효(날짜 시간 또는 기간)</span><span class="sxs-lookup"><span data-stu-id="0a8d5-164">Effective (date time or period)</span></span>
 - <span data-ttu-id="0a8d5-165">Code.Coding.Code</span><span class="sxs-lookup"><span data-stu-id="0a8d5-165">Code.Coding.Code</span></span>
 - <span data-ttu-id="0a8d5-166">ValueQuantity.Value</span><span class="sxs-lookup"><span data-stu-id="0a8d5-166">ValueQuantity.Value</span></span>

<span data-ttu-id="0a8d5-167">Argonaut 필드 외에도, 훌륭한 사용자 환경을 위해 Patients 앱은 다음 필드를 읽을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0a8d5-167">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following fields:</span></span>

 - <span data-ttu-id="0a8d5-168">Code.Coding.Display</span><span class="sxs-lookup"><span data-stu-id="0a8d5-168">Code.Coding.Display</span></span>
 - <span data-ttu-id="0a8d5-169">ValueQuantity.Unit</span><span class="sxs-lookup"><span data-stu-id="0a8d5-169">ValueQuantity.Unit</span></span>

<span data-ttu-id="0a8d5-170">리소스 검색은 GET 메서드 및 다음 매개 변수를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="0a8d5-170">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="0a8d5-171">patient=\<patient id></span><span class="sxs-lookup"><span data-stu-id="0a8d5-171">patient=\<patient id></span></span>
 - <span data-ttu-id="0a8d5-172">_sort=-date</span><span class="sxs-lookup"><span data-stu-id="0a8d5-172">_sort=-date</span></span>
 - <span data-ttu-id="0a8d5-173">범주("category=vital-signs"를 쿼리하여 중요한 기호 목록을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="0a8d5-173">category (we will query for "category=vital-signs") to retrieve the list of vital signs.</span></span>

<span data-ttu-id="0a8d5-174">호출의 이 예제를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="0a8d5-174">Refer to this example of the call:</span></span>

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

<span data-ttu-id="0a8d5-175">이 [https://www.hl7.org/fhir/stu3/observation.html](https://www.hl7.org/fhir/stu3/observation.html) 필드 집합에 대한 기타 세부 정보는 를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="0a8d5-175">See [https://www.hl7.org/fhir/stu3/observation.html](https://www.hl7.org/fhir/stu3/observation.html) for other details on this field set.</span></span>

## <a name="condition"></a><span data-ttu-id="0a8d5-176">조건</span><span class="sxs-lookup"><span data-stu-id="0a8d5-176">Condition</span></span>

<span data-ttu-id="0a8d5-177">Argonaut 조건 프로필의 하위 집합인 최소 필수 [필드는 다음과 같습니다.](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html)</span><span class="sxs-lookup"><span data-stu-id="0a8d5-177">Here's the minimum required fields, which are a subset of the [Argonaut condition profile](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html).</span></span>

 - <span data-ttu-id="0a8d5-178">Code.Coding[0]. 표시</span><span class="sxs-lookup"><span data-stu-id="0a8d5-178">Code.Coding[0].Display</span></span>

<span data-ttu-id="0a8d5-179">Argonaut 필드 외에도, 훌륭한 사용자 환경을 위해 Patients 앱은 다음 필드를 읽을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0a8d5-179">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following fields:</span></span>

 - <span data-ttu-id="0a8d5-180">AssertedDate</span><span class="sxs-lookup"><span data-stu-id="0a8d5-180">AssertedDate</span></span>
 - <span data-ttu-id="0a8d5-181">심각도</span><span class="sxs-lookup"><span data-stu-id="0a8d5-181">Severity</span></span>

<span data-ttu-id="0a8d5-182">리소스 검색은 GET 메서드 및 다음 매개 변수를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="0a8d5-182">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="0a8d5-183">patient=\<patient id></span><span class="sxs-lookup"><span data-stu-id="0a8d5-183">patient=\<patient id></span></span>
 - <span data-ttu-id="0a8d5-184">_count=\<max results></span><span class="sxs-lookup"><span data-stu-id="0a8d5-184">_count=\<max results></span></span>

<span data-ttu-id="0a8d5-185">이 호출의 다음 예제를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="0a8d5-185">See the following example of this call:</span></span>

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

<span data-ttu-id="0a8d5-186">이 [https://hl7.org/fhir/stu3/condition.html](https://hl7.org/fhir/stu3/condition.html) 필드 집합에 대한 기타 세부 정보는 를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="0a8d5-186">See [https://hl7.org/fhir/stu3/condition.html](https://hl7.org/fhir/stu3/condition.html) for other details on this field set.</span></span>

## <a name="encounter"></a><span data-ttu-id="0a8d5-187">발생</span><span class="sxs-lookup"><span data-stu-id="0a8d5-187">Encounter</span></span>

<span data-ttu-id="0a8d5-188">이는 미국 코어 만남 프로필 "필수" [](https://hl7.org/fhir/us/core/2018Jan/StructureDefinition-us-core-encounter.html) 필드의 하위 집합인 최소 필수 필드입니다.</span><span class="sxs-lookup"><span data-stu-id="0a8d5-188">These are the minimum required fields, which are a subset of the [US Core Encounter profile](https://hl7.org/fhir/us/core/2018Jan/StructureDefinition-us-core-encounter.html) "must have" fields).</span></span>

 - <span data-ttu-id="0a8d5-189">상태</span><span class="sxs-lookup"><span data-stu-id="0a8d5-189">Status</span></span>
 - <span data-ttu-id="0a8d5-190">[0]을 입력합니다. 코딩[0]. 표시</span><span class="sxs-lookup"><span data-stu-id="0a8d5-190">Type[0].Coding[0].Display</span></span>

<span data-ttu-id="0a8d5-191">또한 US Core Encounter 프로필의 "지원해야 합니다" 필드의 다음 필드는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="0a8d5-191">In addition, the following fields from US Core Encounter profile's "must support" fields:</span></span>

 - <span data-ttu-id="0a8d5-192">Period.Start</span><span class="sxs-lookup"><span data-stu-id="0a8d5-192">Period.Start</span></span>
 - <span data-ttu-id="0a8d5-193">Location[0]. Location.Display</span><span class="sxs-lookup"><span data-stu-id="0a8d5-193">Location[0].Location.Display</span></span>

<span data-ttu-id="0a8d5-194">리소스 검색은 GET 메서드 및 다음 매개 변수를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="0a8d5-194">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="0a8d5-195">patient=\<patient id></span><span class="sxs-lookup"><span data-stu-id="0a8d5-195">patient=\<patient id></span></span>
 - <span data-ttu-id="0a8d5-196">_sort:desc=\<field ex. date></span><span class="sxs-lookup"><span data-stu-id="0a8d5-196">_sort:desc=\<field ex. date></span></span>
 - <span data-ttu-id="0a8d5-197">_count=\<max results></span><span class="sxs-lookup"><span data-stu-id="0a8d5-197">_count=\<max results></span></span>

<span data-ttu-id="0a8d5-198">목표는 환자의 마지막 알려진 위치를 검색할 수 있게 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="0a8d5-198">The goal is to be able to retrieve the patient's last known location.</span></span> <span data-ttu-id="0a8d5-199">각 조우는 위치 리소스를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="0a8d5-199">Each encounter references a location resource.</span></span> <span data-ttu-id="0a8d5-200">참조에는 위치의 표시 필드도 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="0a8d5-200">The reference shall also include the location's display field.</span></span>

<span data-ttu-id="0a8d5-201">이 [https://hl7.org/fhir/stu3/encounter.html](https://hl7.org/fhir/stu3/encounter.html) 필드 집합에 대한 기타 세부 정보는 를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="0a8d5-201">See [https://hl7.org/fhir/stu3/encounter.html](https://hl7.org/fhir/stu3/encounter.html) for other details on this field set.</span></span>

## <a name="allergyintolerance"></a><span data-ttu-id="0a8d5-202">AllergyIntolerance</span><span class="sxs-lookup"><span data-stu-id="0a8d5-202">AllergyIntolerance</span></span>

<span data-ttu-id="0a8d5-203">다음은 [Argonaut AllergyIntolerance](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-allergyintolerance.html) 프로필의 하위 집합인 최소 필수 필드입니다.</span><span class="sxs-lookup"><span data-stu-id="0a8d5-203">These are the minimum required fields, which are a subset of the [Argonaut AllergyIntolerance](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-allergyintolerance.html) profile:</span></span>

 - <span data-ttu-id="0a8d5-204">Code.Text</span><span class="sxs-lookup"><span data-stu-id="0a8d5-204">Code.Text</span></span>
 - <span data-ttu-id="0a8d5-205">Code.Coding[0]. 표시</span><span class="sxs-lookup"><span data-stu-id="0a8d5-205">Code.Coding[0].Display</span></span>
 - <span data-ttu-id="0a8d5-206">ClinicalStatus/VerificationStatus(둘 다 읽음)</span><span class="sxs-lookup"><span data-stu-id="0a8d5-206">ClinicalStatus/VerificationStatus (we read both)</span></span>

<span data-ttu-id="0a8d5-207">Argonaut 필드 외에도, 훌륭한 사용자 환경을 위해 Patients 앱은 다음 필드를 읽을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0a8d5-207">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following field:</span></span>

 - <span data-ttu-id="0a8d5-208">AssertedDate</span><span class="sxs-lookup"><span data-stu-id="0a8d5-208">AssertedDate</span></span>
 - <span data-ttu-id="0a8d5-209">Note.Text</span><span class="sxs-lookup"><span data-stu-id="0a8d5-209">Note.Text</span></span>
 - <span data-ttu-id="0a8d5-210">반응</span><span class="sxs-lookup"><span data-stu-id="0a8d5-210">Reaction</span></span>
    - <span data-ttu-id="0a8d5-211">물질(하나의 코딩 요소)</span><span class="sxs-lookup"><span data-stu-id="0a8d5-211">Substance (one coding element)</span></span>
    - <span data-ttu-id="0a8d5-212">매니페스트(하나의 코딩 요소)</span><span class="sxs-lookup"><span data-stu-id="0a8d5-212">Manifestation (one coding element)</span></span>

<span data-ttu-id="0a8d5-213">리소스 검색은 GET 메서드 및 다음 매개 변수를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="0a8d5-213">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="0a8d5-214">환자 =  \<patient id></span><span class="sxs-lookup"><span data-stu-id="0a8d5-214">Patient =  \<patient id></span></span>

<span data-ttu-id="0a8d5-215">호출의 다음 예제를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="0a8d5-215">See the following example of the call:</span></span> 

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

<span data-ttu-id="0a8d5-216">이 [https://hl7.org/fhir/stu3/allergyintolerance.html](https://hl7.org/fhir/stu3/allergyintolerance.html) 필드 집합에 대한 기타 세부 정보는 를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="0a8d5-216">See [https://hl7.org/fhir/stu3/allergyintolerance.html](https://hl7.org/fhir/stu3/allergyintolerance.html) for other details on this field set.</span></span>

## <a name="medication-request"></a><span data-ttu-id="0a8d5-217">약물 요청</span><span class="sxs-lookup"><span data-stu-id="0a8d5-217">Medication Request</span></span>

<span data-ttu-id="0a8d5-218">다음은 미국 핵심 약물 요청 프로필의 하위 집합인 최소 필수 [필드입니다.](http://www.hl7.org/fhir/us/core/StructureDefinition-us-core-medicationrequest.html)</span><span class="sxs-lookup"><span data-stu-id="0a8d5-218">These are the minimum required fields, which are a subset of the [US Core Medication Request profile](http://www.hl7.org/fhir/us/core/StructureDefinition-us-core-medicationrequest.html):</span></span>

 - <span data-ttu-id="0a8d5-219">Medication.Display(참조인 경우)</span><span class="sxs-lookup"><span data-stu-id="0a8d5-219">Medication.Display (if Reference)</span></span>
 - <span data-ttu-id="0a8d5-220">Medication.Text(CodableConcept인 경우)</span><span class="sxs-lookup"><span data-stu-id="0a8d5-220">Medication.Text (if CodableConcept)</span></span>
 - <span data-ttu-id="0a8d5-221">AuthoredOn</span><span class="sxs-lookup"><span data-stu-id="0a8d5-221">AuthoredOn</span></span>
 - <span data-ttu-id="0a8d5-222">Requester.Agent.Display</span><span class="sxs-lookup"><span data-stu-id="0a8d5-222">Requester.Agent.Display</span></span>

<span data-ttu-id="0a8d5-223">US Core 필드 외에도, 훌륭한 사용자 환경을 위해 Patients 앱이 다음 필드를 읽을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0a8d5-223">In addition to the US Core fields, for a great user experience the Patients app can also read the following fields:</span></span>

 - <span data-ttu-id="0a8d5-224">복용량Instruction[...]. 텍스트</span><span class="sxs-lookup"><span data-stu-id="0a8d5-224">DosageInstruction[..].Text</span></span>
 - <span data-ttu-id="0a8d5-225">텍스트</span><span class="sxs-lookup"><span data-stu-id="0a8d5-225">Text</span></span>

<span data-ttu-id="0a8d5-226">리소스 검색은 GET 메서드 및 다음 매개 변수를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="0a8d5-226">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="0a8d5-227">patient=\<patient id></span><span class="sxs-lookup"><span data-stu-id="0a8d5-227">patient=\<patient id></span></span>
 - <span data-ttu-id="0a8d5-228">_count=\<max results></span><span class="sxs-lookup"><span data-stu-id="0a8d5-228">_count=\<max results></span></span>

<span data-ttu-id="0a8d5-229">이 [https://www.hl7.org/fhir/medicationrequest.html](https://www.hl7.org/fhir/medicationrequest.html) 필드 집합에 대한 기타 세부 정보는 를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="0a8d5-229">See [https://www.hl7.org/fhir/medicationrequest.html](https://www.hl7.org/fhir/medicationrequest.html) for other details on this field set.</span></span>

## <a name="coverage"></a><span data-ttu-id="0a8d5-230">적용 범위</span><span class="sxs-lookup"><span data-stu-id="0a8d5-230">Coverage</span></span>

<span data-ttu-id="0a8d5-231">다음은 미국 코어 또는 Argonaut 프로필에서 다루지 않는 최소 필수 필드입니다.</span><span class="sxs-lookup"><span data-stu-id="0a8d5-231">These are the minimum required fields, not covered by either US Core or Argonaut profiles:</span></span>

 - <span data-ttu-id="0a8d5-232">그룹화( 하나 이상의 요소와 함께</span><span class="sxs-lookup"><span data-stu-id="0a8d5-232">Grouping, at least one element with</span></span>
    - <span data-ttu-id="0a8d5-233">GroupDisplay</span><span class="sxs-lookup"><span data-stu-id="0a8d5-233">GroupDisplay</span></span>
    - <span data-ttu-id="0a8d5-234">PlanDisplay</span><span class="sxs-lookup"><span data-stu-id="0a8d5-234">PlanDisplay</span></span>
 - <span data-ttu-id="0a8d5-235">기간</span><span class="sxs-lookup"><span data-stu-id="0a8d5-235">Period</span></span>
 - <span data-ttu-id="0a8d5-236">SubscriberId</span><span class="sxs-lookup"><span data-stu-id="0a8d5-236">SubscriberId</span></span>

<span data-ttu-id="0a8d5-237">리소스 검색은 GET 메서드 및 다음 매개 변수를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="0a8d5-237">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="0a8d5-238">환자 = \<patient id></span><span class="sxs-lookup"><span data-stu-id="0a8d5-238">Patient = \<patient id></span></span>

<span data-ttu-id="0a8d5-239">이 [https://hl7.org/fhir/stu3/coverage.html](https://www.hl7.org/fhir/medicationrequest.html) 필드 집합에 대한 기타 세부 정보는 를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="0a8d5-239">See [https://hl7.org/fhir/stu3/coverage.html](https://www.hl7.org/fhir/medicationrequest.html) for other details on this field set.</span></span>
