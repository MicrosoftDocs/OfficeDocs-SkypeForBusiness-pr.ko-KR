---
title: Patients App 및 EHR 통합 DSTU2 인터페이스
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
description: FHIR 서버를 설정하거나 재구성하는 Teams 환자 앱과 함께 작동할 수 있는 DSTU2 인터페이스 사양에 대해 Microsoft Teams 대해 자세히 알아보습니다.
ms.custom: seo-marvel-mar2020
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 12833ea55977cf7e8d18ee5c10b1f17d898b27b3
ms.sourcegitcommit: beaaee10019f4eda746f348888a4a3c2aaa6f196
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2020
ms.locfileid: "48803486"
---
# <a name="dstu2-interface-specification"></a><span data-ttu-id="13e56-103">DSTU2 인터페이스 사양</span><span class="sxs-lookup"><span data-stu-id="13e56-103">DSTU2 interface specification</span></span>

> [!NOTE]
> <span data-ttu-id="13e56-104">2020년 10월 30일부터 환자 앱이 폐기되고 Teams 내 [목록 앱](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db)으로 대체되었습니다.</span><span class="sxs-lookup"><span data-stu-id="13e56-104">Effective October 30, 2020, the Patients app has been retired and replaced by the [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) in Teams.</span></span> <span data-ttu-id="13e56-105">환자 앱 데이터는 팀을 백업하는 Office 365 그룹의 그룹 사서함에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="13e56-105">Patients app data is stored in the group mailbox of the Office 365 group that backs the team.</span></span> <span data-ttu-id="13e56-106">환자 앱과 연결된 모든 데이터는 이 그룹에 보존되지만 사용자 인터페이스를 통해 더 이상 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="13e56-106">All data associated with the Patients app is retained in this group but can no longer be accessed through the user interface.</span></span> <span data-ttu-id="13e56-107">사용자는 [목록 앱](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db)을 사용하여 목록을 다시 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="13e56-107">Users can re-create their lists using the [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db).</span></span>
>
><span data-ttu-id="13e56-108">목록 기능을 사용하면 의료 조직의 관리 팀은 라운드 및 분야별 팀 모임에서 일반 환자 모니터링에 이르는 다양한 시나리오에 대한 환자 목록을 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="13e56-108">With Lists, care teams in your healthcare organization can create patient lists for scenarios ranging from rounds and interdisciplinary team meetings to general patient monitoring.</span></span> <span data-ttu-id="13e56-109">시작을 위해 목록에서 환자 서식 파일을 체크 아웃합니다.</span><span class="sxs-lookup"><span data-stu-id="13e56-109">Check out the Patients template in Lists to get started.</span></span> <span data-ttu-id="13e56-110">조직에서 목록 앱을 관리하는 방법에 대한 자세한 내용은 [목록 앱 관리](../../manage-lists-app.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="13e56-110">To learn more about how to manage the Lists app in your organization, see [Manage the Lists app](../../manage-lists-app.md).</span></span>

<span data-ttu-id="13e56-111">환자 앱과 함께 작동하기 위해 FHIR 서버를 설정하거나 Microsoft Teams 앱에 액세스하는 데 필요한 데이터를 이해해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="13e56-111">Setting up or reconfiguring an FHIR server to work with the Microsoft Teams Patients app requires understanding what data the app needs to access.</span></span> <span data-ttu-id="13e56-112">FHIR 서버는 다음 리소스에 대한 번들을 사용하여 POST 요청을 지원해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="13e56-112">The FHIR server must support POST requests using bundles for the following resources:</span></span>

- [<span data-ttu-id="13e56-113">환자</span><span class="sxs-lookup"><span data-stu-id="13e56-113">Patient</span></span>](#patient)
- [<span data-ttu-id="13e56-114">관찰</span><span class="sxs-lookup"><span data-stu-id="13e56-114">Observation</span></span>](#observation)
- [<span data-ttu-id="13e56-115">조건</span><span class="sxs-lookup"><span data-stu-id="13e56-115">Condition</span></span>](#condition)
- [<span data-ttu-id="13e56-116">발생</span><span class="sxs-lookup"><span data-stu-id="13e56-116">Encounter</span></span>](#encounter)
- [<span data-ttu-id="13e56-117">알레르기 비관성</span><span class="sxs-lookup"><span data-stu-id="13e56-117">Allergy intolerance</span></span>](#allergyintolerance)
- [<span data-ttu-id="13e56-118">적용 범위</span><span class="sxs-lookup"><span data-stu-id="13e56-118">Coverage</span></span>](#coverage)
- [<span data-ttu-id="13e56-119">약물 주문</span><span class="sxs-lookup"><span data-stu-id="13e56-119">Medication Order</span></span>](#medication-order)
- [<span data-ttu-id="13e56-120">위치</span><span class="sxs-lookup"><span data-stu-id="13e56-120">Location</span></span>](#location)

> [!NOTE]
> <span data-ttu-id="13e56-121">Patient 리소스는 앱이 로드되지 않는 유일한 필수 리소스입니다.</span><span class="sxs-lookup"><span data-stu-id="13e56-121">The Patient resource is the only mandatory resource (without which the app will not load at all.</span></span> <span data-ttu-id="13e56-122">그러나 파트너는 아래 제공된 사양에 따라 위에서 언급한 모든 리소스에 대한 지원을 구현하여 환자 앱의 최상의 최종 사용자 환경을 Microsoft Teams 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="13e56-122">However, it is recommended that the Partner implement support for all the above mentioned resources per specifications provided below for the best end-user experience with the Microsoft Teams Patients App.</span></span>

<span data-ttu-id="13e56-123">두 Microsoft Teams 리소스에 대한 쿼리는 FHIR 서버의 URL에 요청 번들(BATCH)을 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="13e56-123">Queries from the Microsoft Teams Patients app for more than one resource post a bundle (BATCH) of requests to the FHIR server's URL.</span></span> <span data-ttu-id="13e56-124">서버는 각 요청을 처리하고 각 요청과 일치하는 리소스 번들을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="13e56-124">The server processes each request and returns a bundle of the resources matched by each request.</span></span> <span data-ttu-id="13e56-125">자세한 정보 및 예제는 [https://www.hl7.org/fhir/DSTU2/http.html#transaction](https://www.hl7.org/fhir/DSTU2/http.html#transaction) 를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="13e56-125">For more information and examples, see [https://www.hl7.org/fhir/DSTU2/http.html#transaction](https://www.hl7.org/fhir/DSTU2/http.html#transaction).</span></span>

<span data-ttu-id="13e56-126">다음 모든 FHIR 리소스는 직접 리소스 참조를 통해 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="13e56-126">All the following FHIR resources should be accessible by direct resource reference.</span></span>

## <a name="conformance-minimum-required-field-set"></a><span data-ttu-id="13e56-127">준수 최소 필수 필드 집합</span><span class="sxs-lookup"><span data-stu-id="13e56-127">Conformance minimum required field set</span></span>

 <span data-ttu-id="13e56-128">FHIR Server는 해당 기능에 대한 사실적 요약을 구현하기 위해 준수 문을 구현해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="13e56-128">The FHIR Server must implement the conformance statement for us to have a factual summary of its capabilities.</span></span> <span data-ttu-id="13e56-129">DSTU2 FHIR Server에서 아래 매개 변수를 예상합니다.</span><span class="sxs-lookup"><span data-stu-id="13e56-129">We expect the below parameters in a DSTU2 FHIR Server:</span></span>

 - <span data-ttu-id="13e56-130">REST</span><span class="sxs-lookup"><span data-stu-id="13e56-130">REST</span></span>

    - <span data-ttu-id="13e56-131">모드</span><span class="sxs-lookup"><span data-stu-id="13e56-131">Mode</span></span>
    - <span data-ttu-id="13e56-132">상호 작용</span><span class="sxs-lookup"><span data-stu-id="13e56-132">Interaction</span></span>
    - <span data-ttu-id="13e56-133">리소스: 형식</span><span class="sxs-lookup"><span data-stu-id="13e56-133">Resource: Type</span></span>
    - <span data-ttu-id="13e56-134">보안: [OAuth URIS 확장](https://hl7.org/fhir/extension-oauth-uris.html)</span><span class="sxs-lookup"><span data-stu-id="13e56-134">Security: [Extension for OAuth URIs](https://hl7.org/fhir/extension-oauth-uris.html)</span></span>
   
 - <span data-ttu-id="13e56-135">FhirVersion(이 코드에서는 여러 버전을 지원할 때 피벗해야 하는 버전을 이해해야 합니다.)</span><span class="sxs-lookup"><span data-stu-id="13e56-135">FhirVersion (Our code requires this to understand which version we should pivot to as we support multiple versions.)</span></span>

<span data-ttu-id="13e56-136">이 [https://www.hl7.org/fhir/dstu2/conformance.html](https://www.hl7.org/fhir/dstu2/conformance.html) 필드 집합에 대한 기타 세부 정보는 를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="13e56-136">See [https://www.hl7.org/fhir/dstu2/conformance.html](https://www.hl7.org/fhir/dstu2/conformance.html) for other details on this field set.</span></span>

## <a name="patient"></a><span data-ttu-id="13e56-137">환자</span><span class="sxs-lookup"><span data-stu-id="13e56-137">Patient</span></span>

<span data-ttu-id="13e56-138">다음은 [Argonaut](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html) 환자 프로필 필드의 하위 집합인 최소 필수 필드입니다.</span><span class="sxs-lookup"><span data-stu-id="13e56-138">These are the minimum required fields, which are a subset of the [Argonaut patient profile](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html) fields:</span></span>

 - <span data-ttu-id="13e56-139">Name.Family</span><span class="sxs-lookup"><span data-stu-id="13e56-139">Name.Family</span></span>
 - <span data-ttu-id="13e56-140">Name.Given</span><span class="sxs-lookup"><span data-stu-id="13e56-140">Name.Given</span></span>
 - <span data-ttu-id="13e56-141">성별</span><span class="sxs-lookup"><span data-stu-id="13e56-141">Gender</span></span>
 - <span data-ttu-id="13e56-142">BirthDate</span><span class="sxs-lookup"><span data-stu-id="13e56-142">BirthDate</span></span>
 - <span data-ttu-id="13e56-143">MRN(식별자)</span><span class="sxs-lookup"><span data-stu-id="13e56-143">MRN (Identifier)</span></span>

<span data-ttu-id="13e56-144">Argonaut 필드 외에도, 훌륭한 사용자 환경을 위해 Patients 앱은 다음 필드도 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="13e56-144">In addition to the Argonaut fields, for a great user experience the Patients app also reads the following fields:</span></span>

 - <span data-ttu-id="13e56-145">Name.Use</span><span class="sxs-lookup"><span data-stu-id="13e56-145">Name.Use</span></span>
 - <span data-ttu-id="13e56-146">Name.Prefix</span><span class="sxs-lookup"><span data-stu-id="13e56-146">Name.Prefix</span></span>
 - <span data-ttu-id="13e56-147">CareProvider(환자 리소스의 이 참조에는 다음 예제에 표시된 표시 필드가 포함되어야 합니다.)</span><span class="sxs-lookup"><span data-stu-id="13e56-147">CareProvider (This reference on the Patient resource should include the display fields shown in the following example.)</span></span>

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

<span data-ttu-id="13e56-148">리소스 검색은 /Patient/_search 및 다음 매개 변수에서 POST 메서드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="13e56-148">A resource search uses the POST method at /Patient/_search and the following parameters:</span></span>

 - <span data-ttu-id="13e56-149">id</span><span class="sxs-lookup"><span data-stu-id="13e56-149">id</span></span>
 - <span data-ttu-id="13e56-150">family:contains=(가족 이름이 값을 포함하는 모든 환자를 검색합니다.)</span><span class="sxs-lookup"><span data-stu-id="13e56-150">family:contains=(searches for all patients whose family name contains the value.)</span></span>
 - <span data-ttu-id="13e56-151">given=\<substring></span><span class="sxs-lookup"><span data-stu-id="13e56-151">given=\<substring></span></span>
 - <span data-ttu-id="13e56-152">name=\<substring></span><span class="sxs-lookup"><span data-stu-id="13e56-152">name=\<substring></span></span>
 - <span data-ttu-id="13e56-153">birthdate=(정확한 일치)</span><span class="sxs-lookup"><span data-stu-id="13e56-153">birthdate=(exact match)</span></span>
 - <span data-ttu-id="13e56-154">\_count(반환해야 하는 최대 결과 수)</span><span class="sxs-lookup"><span data-stu-id="13e56-154">\_count (maximum number of results that should be returned)</span></span> <br> <span data-ttu-id="13e56-155">응답에는 검색 결과로 반환된 레코드의 총 수가 포함되어야 합니다. 반환된 레코드 수를 제한하기 위해 \_ PatientsApp에서 개수를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="13e56-155">The response should contain the total count of records returned as a result of the search, and \_count will be used by the PatientsApp to limit the number of records returned.</span></span>
 - <span data-ttu-id="13e56-156">식별자=\<mrn></span><span class="sxs-lookup"><span data-stu-id="13e56-156">identifier=\<mrn></span></span>

<span data-ttu-id="13e56-157">목표는 다음을 통해 환자를 검색하고 필터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="13e56-157">The goal is to be able to search and filter for a patient by the following:</span></span>

- <span data-ttu-id="13e56-158">ID: FHIR의 모든 리소스가 있는 리소스 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="13e56-158">ID: This is the resource ID that every resource in FHIR has.</span></span>
- <span data-ttu-id="13e56-159">MRN: 이것은 임상 직원이 알고 있는 환자의 실제 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="13e56-159">MRN: This is the actual identifier for the patient that clinical staff would know.</span></span> <span data-ttu-id="13e56-160">이 MRN은 FHIR의 식별자 리소스 내부 식별자 유형을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="13e56-160">We understand this MRN is based on the type of identifier inside the identifier resource in FHIR</span></span>
- <span data-ttu-id="13e56-161">이름</span><span class="sxs-lookup"><span data-stu-id="13e56-161">Name</span></span>
- <span data-ttu-id="13e56-162">Birthdate</span><span class="sxs-lookup"><span data-stu-id="13e56-162">Birthdate</span></span>

<span data-ttu-id="13e56-163">이 호출의 다음 예제를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="13e56-163">See the following example  of this call.</span></span>

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

<span data-ttu-id="13e56-164">이 [https://www.hl7.org/fhir/DSTU2/Patient.html](https://www.hl7.org/fhir/DSTU2/Patient.html) 필드 집합에 대한 기타 세부 정보는 를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="13e56-164">See [https://www.hl7.org/fhir/DSTU2/Patient.html](https://www.hl7.org/fhir/DSTU2/Patient.html) for other details on this field set.</span></span>

## <a name="observation"></a><span data-ttu-id="13e56-165">관찰</span><span class="sxs-lookup"><span data-stu-id="13e56-165">Observation</span></span>

<span data-ttu-id="13e56-166">다음은 Argonaut 중요 기호 프로필의 하위 집합인 최소 필수 필드입니다.</span><span class="sxs-lookup"><span data-stu-id="13e56-166">These are the minimum required fields, which are a subset of the Argonaut vital signs profile:</span></span>

 - <span data-ttu-id="13e56-167">유효(날짜 시간 또는 기간)</span><span class="sxs-lookup"><span data-stu-id="13e56-167">Effective (date time or period)</span></span>
 - <span data-ttu-id="13e56-168">Code.Coding.Code</span><span class="sxs-lookup"><span data-stu-id="13e56-168">Code.Coding.Code</span></span>
 - <span data-ttu-id="13e56-169">ValueQuantity.Value</span><span class="sxs-lookup"><span data-stu-id="13e56-169">ValueQuantity.Value</span></span>

<span data-ttu-id="13e56-170">Argonaut 필드 외에도, 훌륭한 사용자 환경을 위해 Patients 앱은 다음 필드도 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="13e56-170">In addition to the Argonaut fields, for a great user experience the Patients app also reads the following fields:</span></span>

 - <span data-ttu-id="13e56-171">Code.Coding.Display</span><span class="sxs-lookup"><span data-stu-id="13e56-171">Code.Coding.Display</span></span>
 - <span data-ttu-id="13e56-172">ValueQuantity.Unit</span><span class="sxs-lookup"><span data-stu-id="13e56-172">ValueQuantity.Unit</span></span>

<span data-ttu-id="13e56-173">구성 요소 관찰을 사용하는 경우 각 구성 요소 관찰에 동일한 논리가 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="13e56-173">If using component observations, the same logic applies for each component observation.</span></span>

<span data-ttu-id="13e56-174">리소스 검색은 GET 메서드 및 다음 매개 변수를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="13e56-174">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="13e56-175">patient=\<patient id\></span><span class="sxs-lookup"><span data-stu-id="13e56-175">patient=\<patient id\></span></span>
 - <span data-ttu-id="13e56-176">sort:desc=\<field ex. date\></span><span class="sxs-lookup"><span data-stu-id="13e56-176">sort:desc=\<field ex. date\></span></span>

<span data-ttu-id="13e56-177">목표는 환자에 대한 최신 중요 징후인 [VitalSigns.DSTU.saz](관찰?)를 검색할 수 있게 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="13e56-177">The goal is to be able to retrieve the latest vital signs for a patient, [VitalSigns.DSTU.saz]  (observation?).</span></span>

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

<span data-ttu-id="13e56-178">이 [https://www.hl7.org/fhir/DSTU2/Observation.html](https://www.hl7.org/fhir/DSTU2/Observation.html) 필드 집합에 대한 기타 세부 정보는 를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="13e56-178">See [https://www.hl7.org/fhir/DSTU2/Observation.html](https://www.hl7.org/fhir/DSTU2/Observation.html) for other details on this field set.</span></span>

## <a name="condition"></a><span data-ttu-id="13e56-179">조건</span><span class="sxs-lookup"><span data-stu-id="13e56-179">Condition</span></span>

<span data-ttu-id="13e56-180">다음은 [Argonaut](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html)조건 프로필의 하위 집합인 최소 필수 필드입니다.</span><span class="sxs-lookup"><span data-stu-id="13e56-180">These are the minimum required fields, which are a subset of the [Argonaut condition profile](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html):</span></span>

1. <span data-ttu-id="13e56-181">Code.Coding[0]. 표시</span><span class="sxs-lookup"><span data-stu-id="13e56-181">Code.Coding[0].Display</span></span>

<span data-ttu-id="13e56-182">Argonaut 필드 외에도, 훌륭한 사용자 환경을 위해 Patients 앱은 다음 필드를 읽을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="13e56-182">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following fields:</span></span>

 - <span data-ttu-id="13e56-183">기록된 날짜</span><span class="sxs-lookup"><span data-stu-id="13e56-183">Date Recorded</span></span>
 - <span data-ttu-id="13e56-184">심각도</span><span class="sxs-lookup"><span data-stu-id="13e56-184">Severity</span></span>

<span data-ttu-id="13e56-185">리소스 검색은 GET 메서드 및 다음 매개 변수를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="13e56-185">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="13e56-186">patient=\<patient id></span><span class="sxs-lookup"><span data-stu-id="13e56-186">patient=\<patient id></span></span>
 - <span data-ttu-id="13e56-187">_count=\<max results></span><span class="sxs-lookup"><span data-stu-id="13e56-187">_count=\<max results></span></span>

<span data-ttu-id="13e56-188">이 호출의 다음 예제를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="13e56-188">See the following example of this call:</span></span>

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

<span data-ttu-id="13e56-189">이 [https://www.hl7.org/fhir/DSTU2/Condition.html](https://www.hl7.org/fhir/DSTU2/Condition.html) 필드 집합에 대한 기타 세부 정보는 를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="13e56-189">See [https://www.hl7.org/fhir/DSTU2/Condition.html](https://www.hl7.org/fhir/DSTU2/Condition.html) for other details on this field set.</span></span>

## <a name="encounter"></a><span data-ttu-id="13e56-190">발생</span><span class="sxs-lookup"><span data-stu-id="13e56-190">Encounter</span></span>

<span data-ttu-id="13e56-191">다음은 미국 Core Encounter 프로필 "필수" 필드의 하위 집합인 최소 필수 필드입니다.</span><span class="sxs-lookup"><span data-stu-id="13e56-191">These are the minimum required fields, which are a subset of the US Core Encounter profile "must have" fields:</span></span>

 - <span data-ttu-id="13e56-192">상태</span><span class="sxs-lookup"><span data-stu-id="13e56-192">Status</span></span>
 - <span data-ttu-id="13e56-193">[0]을 입력합니다. 코딩[0]. 표시</span><span class="sxs-lookup"><span data-stu-id="13e56-193">Type[0].Coding[0].Display</span></span>

<span data-ttu-id="13e56-194">또한 US Core Encounter 프로필의 "지원해야 합니다" 필드의 다음 필드</span><span class="sxs-lookup"><span data-stu-id="13e56-194">In addition, the following fields from US Core Encounter profile's "must support" fields</span></span>

 - <span data-ttu-id="13e56-195">Period.Start</span><span class="sxs-lookup"><span data-stu-id="13e56-195">Period.Start</span></span>
 - <span data-ttu-id="13e56-196">Location[0]. Location.Display</span><span class="sxs-lookup"><span data-stu-id="13e56-196">Location[0].Location.Display</span></span>

<span data-ttu-id="13e56-197">리소스 검색은 GET 메서드 및 다음 매개 변수를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="13e56-197">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="13e56-198">patient=\<patient id></span><span class="sxs-lookup"><span data-stu-id="13e56-198">patient=\<patient id></span></span>
 - <span data-ttu-id="13e56-199">_sort:desc=\<field ex. date></span><span class="sxs-lookup"><span data-stu-id="13e56-199">_sort:desc=\<field ex. date></span></span>
 - <span data-ttu-id="13e56-200">_count=\<max results></span><span class="sxs-lookup"><span data-stu-id="13e56-200">_count=\<max results></span></span>

<span data-ttu-id="13e56-201">목표는 환자의 마지막 알려진 위치를 검색할 수 있게 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="13e56-201">The goal is to be able to retrieve the patient's last known location.</span></span> <span data-ttu-id="13e56-202">각 조우는 위치 리소스를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="13e56-202">Each encounter references a location resource.</span></span> <span data-ttu-id="13e56-203">참조에는 위치의 표시 필드도 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="13e56-203">The reference shall also include the location's display field.</span></span> <span data-ttu-id="13e56-204">이 호출의 다음 예제를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="13e56-204">See the following example of this call.</span></span>

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

<span data-ttu-id="13e56-205">이 [https://www.hl7.org/fhir/DSTU2/Encounter.htm](https://www.hl7.org/fhir/DSTU2/Encounter.htm) 필드 집합에 대한 기타 세부 정보는 를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="13e56-205">See [https://www.hl7.org/fhir/DSTU2/Encounter.htm](https://www.hl7.org/fhir/DSTU2/Encounter.htm) for other details on this field set.</span></span>

## <a name="allergyintolerance"></a><span data-ttu-id="13e56-206">AllergyIntolerance</span><span class="sxs-lookup"><span data-stu-id="13e56-206">AllergyIntolerance</span></span>

<span data-ttu-id="13e56-207">다음은 Argonaut AllergyIntolerance 프로필의 하위 집합인 최소 필수 필드입니다.</span><span class="sxs-lookup"><span data-stu-id="13e56-207">These are the minimum required fields, which are a subset of the Argonaut AllergyIntolerance profile:</span></span>

 - <span data-ttu-id="13e56-208">Code.Text</span><span class="sxs-lookup"><span data-stu-id="13e56-208">Code.Text</span></span>
 - <span data-ttu-id="13e56-209">Code.Coding[0]. 표시</span><span class="sxs-lookup"><span data-stu-id="13e56-209">Code.Coding[0].Display</span></span>
 - <span data-ttu-id="13e56-210">상태</span><span class="sxs-lookup"><span data-stu-id="13e56-210">Status</span></span>

<span data-ttu-id="13e56-211">Argonaut 필드 외에도, 훌륭한 사용자 환경을 위해 Patients 앱은 다음 필드도 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="13e56-211">In addition to the Argonaut fields, for a great user experience the Patients app also reads the following fields:</span></span>

 - <span data-ttu-id="13e56-212">RecordedDate</span><span class="sxs-lookup"><span data-stu-id="13e56-212">RecordedDate</span></span>
 - <span data-ttu-id="13e56-213">Note.Text</span><span class="sxs-lookup"><span data-stu-id="13e56-213">Note.Text</span></span>
 - <span data-ttu-id="13e56-214">Reaction[...]. Substance.Text</span><span class="sxs-lookup"><span data-stu-id="13e56-214">Reaction[..].Substance.Text</span></span>
 - <span data-ttu-id="13e56-215">Reaction[...]. Manifestation[...]. 텍스트</span><span class="sxs-lookup"><span data-stu-id="13e56-215">Reaction[..].Manifestation[..].Text</span></span>
 - <span data-ttu-id="13e56-216">Text.Div</span><span class="sxs-lookup"><span data-stu-id="13e56-216">Text.Div</span></span>

<span data-ttu-id="13e56-217">리소스 검색은 GET 메서드 및 다음 매개 변수를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="13e56-217">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="13e56-218">환자 =  \<patient id></span><span class="sxs-lookup"><span data-stu-id="13e56-218">Patient =  \<patient id></span></span>

<span data-ttu-id="13e56-219">이 호출의 다음 예제를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="13e56-219">See the following example of this call:</span></span>

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

<span data-ttu-id="13e56-220">이 [https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html](https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html) 필드 집합에 대한 기타 세부 정보는 를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="13e56-220">See [https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html](https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html) for other details on this field set.</span></span>

## <a name="medication-order"></a><span data-ttu-id="13e56-221">약물 주문</span><span class="sxs-lookup"><span data-stu-id="13e56-221">Medication Order</span></span>

<span data-ttu-id="13e56-222">다음은 Argonaut MedicationOrder 프로필의 하위 집합인 최소 필수 필드입니다.</span><span class="sxs-lookup"><span data-stu-id="13e56-222">These are the minimum required fields, which are a subset of the Argonaut MedicationOrder profile:</span></span>

 - <span data-ttu-id="13e56-223">DateWritten</span><span class="sxs-lookup"><span data-stu-id="13e56-223">DateWritten</span></span>
 - <span data-ttu-id="13e56-224">Prescriber.Display</span><span class="sxs-lookup"><span data-stu-id="13e56-224">Prescriber.Display</span></span>
 - <span data-ttu-id="13e56-225">Medication.Display(참조하는 경우)</span><span class="sxs-lookup"><span data-stu-id="13e56-225">Medication.Display (if reference)</span></span>
 - <span data-ttu-id="13e56-226">Medication.Text(개념이 있는 경우)</span><span class="sxs-lookup"><span data-stu-id="13e56-226">Medication.Text (if concept)</span></span>

<span data-ttu-id="13e56-227">Argonaut 필드 외에도, 훌륭한 사용자 환경을 위해 Patients 앱은 다음 필드를 읽을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="13e56-227">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following fields:</span></span>

 - <span data-ttu-id="13e56-228">DateEnded</span><span class="sxs-lookup"><span data-stu-id="13e56-228">DateEnded</span></span>
 - <span data-ttu-id="13e56-229">복용량Instruction.Text</span><span class="sxs-lookup"><span data-stu-id="13e56-229">DosageInstruction.Text</span></span>
 - <span data-ttu-id="13e56-230">Text.Div</span><span class="sxs-lookup"><span data-stu-id="13e56-230">Text.Div</span></span>

<span data-ttu-id="13e56-231">리소스 검색은 GET 메서드 및 다음 매개 변수를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="13e56-231">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="13e56-232">patient=\<patient id></span><span class="sxs-lookup"><span data-stu-id="13e56-232">patient=\<patient id></span></span>
 - <span data-ttu-id="13e56-233">_count=\<max results></span><span class="sxs-lookup"><span data-stu-id="13e56-233">_count=\<max results></span></span>

<span data-ttu-id="13e56-234">이 호출의 다음 예제를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="13e56-234">See the following example of this call:</span></span>

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

<span data-ttu-id="13e56-235">이 [https://www.hl7.org/fhir/DSTU2/MedicationOrder.html](https://www.hl7.org/fhir/DSTU2/MedicationOrder.html) 필드 집합에 대한 기타 세부 정보는 를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="13e56-235">See [https://www.hl7.org/fhir/DSTU2/MedicationOrder.html](https://www.hl7.org/fhir/DSTU2/MedicationOrder.html) for other details on this field set.</span></span>

## <a name="coverage"></a><span data-ttu-id="13e56-236">적용 범위</span><span class="sxs-lookup"><span data-stu-id="13e56-236">Coverage</span></span>

<span data-ttu-id="13e56-237">다음은 미국 코어 또는 Argonaut 프로필에서 다루지 않는 최소 필수 필드입니다.</span><span class="sxs-lookup"><span data-stu-id="13e56-237">These are the minimum required fields, not covered by either US Core or Argonaut profiles:</span></span>

 - <span data-ttu-id="13e56-238">Payor</span><span class="sxs-lookup"><span data-stu-id="13e56-238">Payor</span></span>

<span data-ttu-id="13e56-239">리소스 검색은 GET 메서드 및 다음 매개 변수를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="13e56-239">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="13e56-240">patient=\<patient id></span><span class="sxs-lookup"><span data-stu-id="13e56-240">patient=\<patient id></span></span>

<span data-ttu-id="13e56-241">이 호출의 다음 예제를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="13e56-241">See the following example of this call:</span></span>

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
    
<span data-ttu-id="13e56-242">이 [https://www.hl7.org/fhir/DSTU2/Coverage.html](https://www.hl7.org/fhir/DSTU2/Coverage.html) 필드 집합에 대한 기타 세부 정보는 를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="13e56-242">See [https://www.hl7.org/fhir/DSTU2/Coverage.html](https://www.hl7.org/fhir/DSTU2/Coverage.html) for other details on this field set.</span></span>

## <a name="location"></a><span data-ttu-id="13e56-243">위치</span><span class="sxs-lookup"><span data-stu-id="13e56-243">Location</span></span>

<span data-ttu-id="13e56-244">이 리소스는 만남 리소스에서 [참조로만 사용됩니다.](#encounter)</span><span class="sxs-lookup"><span data-stu-id="13e56-244">This resource is only being used as a reference on the [Encounter](#encounter) resource.</span></span>

<span data-ttu-id="13e56-245">이 [https://www.hl7.org/fhir/DSTU2/Location.html](https://www.hl7.org/fhir/DSTU2/Location.html) 필드 집합에 대한 기타 세부 정보는 를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="13e56-245">See [https://www.hl7.org/fhir/DSTU2/Location.html](https://www.hl7.org/fhir/DSTU2/Location.html) for other details on this field set.</span></span>
