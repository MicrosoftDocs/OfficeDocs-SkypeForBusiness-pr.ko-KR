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
# <a name="dstu2-interface-specification"></a><span data-ttu-id="5ab11-103">DSTU2 인터페이스 사양</span><span class="sxs-lookup"><span data-stu-id="5ab11-103">DSTU2 interface specification</span></span>

> [!NOTE]
> <span data-ttu-id="5ab11-104">2020 년 10 월 30 일에 효력을 환자 앱이 만료 되어 팀의 [목록 앱](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) 으로 대체 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="5ab11-104">Effective October 30, 2020, the Patients app has been retired and replaced by the [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) in Teams.</span></span> <span data-ttu-id="5ab11-105">목록을 사용 하는 경우 의료 기관에서 팀은 팀 모임에서 일반 환자 모니터링과의 interdisciplinary에 이르기까지 시나리오에 대 한 환자 목록을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ab11-105">With Lists, care teams in your healthcare organization can create patient lists for scenarios ranging from rounds and interdisciplinary team meetings to general patient monitoring.</span></span> <span data-ttu-id="5ab11-106">목록에서 환자 서식 파일을 확인 하 여 시작 하세요.</span><span class="sxs-lookup"><span data-stu-id="5ab11-106">Check out the Patients template in Lists to get started.</span></span> <span data-ttu-id="5ab11-107">조직에서 목록 앱을 관리 하는 방법에 대해 자세히 알아보려면 [목록 관리 앱](../../manage-lists-app.md) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5ab11-107">To learn more about how to manage the Lists app in your organization, see [Manage the Lists app](../../manage-lists-app.md)</span></span>

<span data-ttu-id="5ab11-108">Microsoft 팀 환자 앱을 사용 하도록 FTO r 서버를 설정 또는 재구성 하려면 앱이 액세스 해야 하는 데이터에 대 한 이해가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ab11-108">Setting up or reconfiguring an FHIR server to work with the Microsoft Teams Patients app requires understanding what data the app needs to access.</span></span> <span data-ttu-id="5ab11-109">FHIR 서버는 다음 리소스에 대해 번들을 사용 하 여 POST 요청을 지원 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ab11-109">The FHIR server must support POST requests using bundles for the following resources:</span></span>

- [<span data-ttu-id="5ab11-110">환자가</span><span class="sxs-lookup"><span data-stu-id="5ab11-110">Patient</span></span>](#patient)
- [<span data-ttu-id="5ab11-111">탑</span><span class="sxs-lookup"><span data-stu-id="5ab11-111">Observation</span></span>](#observation)
- [<span data-ttu-id="5ab11-112">조건</span><span class="sxs-lookup"><span data-stu-id="5ab11-112">Condition</span></span>](#condition)
- [<span data-ttu-id="5ab11-113">문제가</span><span class="sxs-lookup"><span data-stu-id="5ab11-113">Encounter</span></span>](#encounter)
- [<span data-ttu-id="5ab11-114">Allergy intolerance</span><span class="sxs-lookup"><span data-stu-id="5ab11-114">Allergy intolerance</span></span>](#allergyintolerance)
- [<span data-ttu-id="5ab11-115">통신이</span><span class="sxs-lookup"><span data-stu-id="5ab11-115">Coverage</span></span>](#coverage)
- [<span data-ttu-id="5ab11-116">투약 주문</span><span class="sxs-lookup"><span data-stu-id="5ab11-116">Medication Order</span></span>](#medication-order)
- [<span data-ttu-id="5ab11-117">위치</span><span class="sxs-lookup"><span data-stu-id="5ab11-117">Location</span></span>](#location)

> [!NOTE]
> <span data-ttu-id="5ab11-118">환자 리소스는 유일한 필수 리소스 이며 앱이 전혀 로드 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5ab11-118">The Patient resource is the only mandatory resource (without which the app will not load at all.</span></span> <span data-ttu-id="5ab11-119">그러나 Microsoft 팀 환자 앱을 사용 하 여 최상의 최종 사용자 환경을 제공 하기 위해 파트너는 위에서 설명한 모든 사양에 대 한 지원을 구현 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="5ab11-119">However, it is recommended that the Partner implement support for all the above mentioned resources per specifications provided below for the best end-user experience with the Microsoft Teams Patients App.</span></span>

<span data-ttu-id="5ab11-120">Microsoft 팀 환자 앱에서 두 개 이상의 리소스에 대 한 쿼리는 요청에 대 한 번들 (일괄)을 FHIR 서버의 URL에 게시 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ab11-120">Queries from the Microsoft Teams Patients app for more than one resource post a bundle (BATCH) of requests to the FHIR server's URL.</span></span> <span data-ttu-id="5ab11-121">서버는 각 요청을 처리 하 고 각 요청과 일치 하는 리소스의 번들을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ab11-121">The server processes each request and returns a bundle of the resources matched by each request.</span></span> <span data-ttu-id="5ab11-122">자세한 내용 및 예제는를 참조 하세요 [https://www.hl7.org/fhir/DSTU2/http.html#transaction](https://www.hl7.org/fhir/DSTU2/http.html#transaction) .</span><span class="sxs-lookup"><span data-stu-id="5ab11-122">For more information and examples, see [https://www.hl7.org/fhir/DSTU2/http.html#transaction](https://www.hl7.org/fhir/DSTU2/http.html#transaction).</span></span>

<span data-ttu-id="5ab11-123">다음의 모든 팔 로우 리소스는 직접 리소스 참조를 통해 액세스할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ab11-123">All the following FHIR resources should be accessible by direct resource reference.</span></span>

## <a name="conformance-minimum-required-field-set"></a><span data-ttu-id="5ab11-124">준수 최소 필수 필드 집합</span><span class="sxs-lookup"><span data-stu-id="5ab11-124">Conformance minimum required field set</span></span>

 <span data-ttu-id="5ab11-125">FA r 서버는 기능에 대 한 factual 요약을 제공 하기 위해 준수 문을 구현 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ab11-125">The FHIR Server must implement the conformance statement for us to have a factual summary of its capabilities.</span></span> <span data-ttu-id="5ab11-126">DSTU2 FA r 서버에서 다음 매개 변수가 예상 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5ab11-126">We expect the below parameters in a DSTU2 FHIR Server:</span></span>

 - <span data-ttu-id="5ab11-127">받침대</span><span class="sxs-lookup"><span data-stu-id="5ab11-127">REST</span></span>

    - <span data-ttu-id="5ab11-128">모드</span><span class="sxs-lookup"><span data-stu-id="5ab11-128">Mode</span></span>
    - <span data-ttu-id="5ab11-129">개입</span><span class="sxs-lookup"><span data-stu-id="5ab11-129">Interaction</span></span>
    - <span data-ttu-id="5ab11-130">자원: 종류</span><span class="sxs-lookup"><span data-stu-id="5ab11-130">Resource: Type</span></span>
    - <span data-ttu-id="5ab11-131">보안: [OAuth uri 용 확장](https://hl7.org/fhir/extension-oauth-uris.html)</span><span class="sxs-lookup"><span data-stu-id="5ab11-131">Security: [Extension for OAuth URIs](https://hl7.org/fhir/extension-oauth-uris.html)</span></span>
   
 - <span data-ttu-id="5ab11-132">Fto Rversion (코드에는 여러 버전을 지원할 때 피벗할 버전을 파악 하기 위해 필요 합니다.)</span><span class="sxs-lookup"><span data-stu-id="5ab11-132">FhirVersion (Our code requires this to understand which version we should pivot to as we support multiple versions.)</span></span>

<span data-ttu-id="5ab11-133">[https://www.hl7.org/fhir/dstu2/conformance.html](https://www.hl7.org/fhir/dstu2/conformance.html)이 필드 집합에 대 한 자세한 내용은을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5ab11-133">See [https://www.hl7.org/fhir/dstu2/conformance.html](https://www.hl7.org/fhir/dstu2/conformance.html) for other details on this field set.</span></span>

## <a name="patient"></a><span data-ttu-id="5ab11-134">환자가</span><span class="sxs-lookup"><span data-stu-id="5ab11-134">Patient</span></span>

<span data-ttu-id="5ab11-135">다음은 [Argonaut 환자 프로필](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html) 필드의 하위 집합인 최소 필수 필드입니다.</span><span class="sxs-lookup"><span data-stu-id="5ab11-135">These are the minimum required fields, which are a subset of the [Argonaut patient profile](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html) fields:</span></span>

 - <span data-ttu-id="5ab11-136">패밀리 이름</span><span class="sxs-lookup"><span data-stu-id="5ab11-136">Name.Family</span></span>
 - <span data-ttu-id="5ab11-137">Name. 지정 된</span><span class="sxs-lookup"><span data-stu-id="5ab11-137">Name.Given</span></span>
 - <span data-ttu-id="5ab11-138">성별을</span><span class="sxs-lookup"><span data-stu-id="5ab11-138">Gender</span></span>
 - <span data-ttu-id="5ab11-139">생년월일</span><span class="sxs-lookup"><span data-stu-id="5ab11-139">BirthDate</span></span>
 - <span data-ttu-id="5ab11-140">MRN (Identifier)</span><span class="sxs-lookup"><span data-stu-id="5ab11-140">MRN (Identifier)</span></span>

<span data-ttu-id="5ab11-141">Argonaut 필드 외에도 멋진 사용자 환경을 위해 환자 앱은 다음 필드도 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="5ab11-141">In addition to the Argonaut fields, for a great user experience the Patients app also reads the following fields:</span></span>

 - <span data-ttu-id="5ab11-142">이름을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ab11-142">Name.Use</span></span>
 - <span data-ttu-id="5ab11-143">Name. 접두사</span><span class="sxs-lookup"><span data-stu-id="5ab11-143">Name.Prefix</span></span>
 - <span data-ttu-id="5ab11-144">CareProvider (환자 리소스에 대 한이 참조에는 다음 예제에 표시 된 표시 필드가 포함 되어야 합니다.)</span><span class="sxs-lookup"><span data-stu-id="5ab11-144">CareProvider (This reference on the Patient resource should include the display fields shown in the following example.)</span></span>

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

<span data-ttu-id="5ab11-145">리소스 검색에서는/Patient/_search 및 다음 매개 변수에 POST 메서드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ab11-145">A resource search uses the POST method at /Patient/_search and the following parameters:</span></span>

 - <span data-ttu-id="5ab11-146">i</span><span class="sxs-lookup"><span data-stu-id="5ab11-146">id</span></span>
 - <span data-ttu-id="5ab11-147">패밀리: contains = (가족 이름에 값이 포함 되어 있는 모든 환자를 검색 합니다.)</span><span class="sxs-lookup"><span data-stu-id="5ab11-147">family:contains=(searches for all patients whose family name contains the value.)</span></span>
 - <span data-ttu-id="5ab11-148">지정 =\<substring></span><span class="sxs-lookup"><span data-stu-id="5ab11-148">given=\<substring></span></span>
 - <span data-ttu-id="5ab11-149">name =\<substring></span><span class="sxs-lookup"><span data-stu-id="5ab11-149">name=\<substring></span></span>
 - <span data-ttu-id="5ab11-150">생년월일 = (정확한 일치)</span><span class="sxs-lookup"><span data-stu-id="5ab11-150">birthdate=(exact match)</span></span>
 - <span data-ttu-id="5ab11-151">\_count (반환 해야 하는 최대 결과 수)</span><span class="sxs-lookup"><span data-stu-id="5ab11-151">\_count (maximum number of results that should be returned)</span></span> <br> <span data-ttu-id="5ab11-152">응답에는 검색 결과로 반환 되는 레코드의 총 개수가 포함 되어야 하 고, \_ PatientsApp에서 반환 되는 레코드 수를 제한 하기 위해 count가 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5ab11-152">The response should contain the total count of records returned as a result of the search, and \_count will be used by the PatientsApp to limit the number of records returned.</span></span>
 - <span data-ttu-id="5ab11-153">identifier =\<mrn></span><span class="sxs-lookup"><span data-stu-id="5ab11-153">identifier=\<mrn></span></span>

<span data-ttu-id="5ab11-154">목표는 다음을 수행 하 여 환자를 검색 하 고 필터링 할 수 있다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="5ab11-154">The goal is to be able to search and filter for a patient by the following:</span></span>

- <span data-ttu-id="5ab11-155">ID:이는 모든 자원의 모든 리소스에 있는 자원 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="5ab11-155">ID: This is the resource ID that every resource in FHIR has.</span></span>
- <span data-ttu-id="5ab11-156">MRN이는 임상 직원이 알고 있는 환자에 대 한 실제 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="5ab11-156">MRN: This is the actual identifier for the patient that clinical staff would know.</span></span> <span data-ttu-id="5ab11-157">이 MRN는 FA r의 식별자 리소스 내에 있는 식별자 유형을 기반으로 한다는 것을 이해 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ab11-157">We understand this MRN is based on the type of identifier inside the identifier resource in FHIR</span></span>
- <span data-ttu-id="5ab11-158">이름</span><span class="sxs-lookup"><span data-stu-id="5ab11-158">Name</span></span>
- <span data-ttu-id="5ab11-159">생년월일</span><span class="sxs-lookup"><span data-stu-id="5ab11-159">Birthdate</span></span>

<span data-ttu-id="5ab11-160">이 통화의 다음 예제를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5ab11-160">See the following example  of this call.</span></span>

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

<span data-ttu-id="5ab11-161">[https://www.hl7.org/fhir/DSTU2/Patient.html](https://www.hl7.org/fhir/DSTU2/Patient.html)이 필드 집합에 대 한 자세한 내용은을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5ab11-161">See [https://www.hl7.org/fhir/DSTU2/Patient.html](https://www.hl7.org/fhir/DSTU2/Patient.html) for other details on this field set.</span></span>

## <a name="observation"></a><span data-ttu-id="5ab11-162">탑</span><span class="sxs-lookup"><span data-stu-id="5ab11-162">Observation</span></span>

<span data-ttu-id="5ab11-163">다음은 Argonaut 필수 기호 프로필의 하위 집합인 필요한 최소 필드입니다.</span><span class="sxs-lookup"><span data-stu-id="5ab11-163">These are the minimum required fields, which are a subset of the Argonaut vital signs profile:</span></span>

 - <span data-ttu-id="5ab11-164">유효 (날짜 시간 또는 기간)</span><span class="sxs-lookup"><span data-stu-id="5ab11-164">Effective (date time or period)</span></span>
 - <span data-ttu-id="5ab11-165">코드. 코딩 코드</span><span class="sxs-lookup"><span data-stu-id="5ab11-165">Code.Coding.Code</span></span>
 - <span data-ttu-id="5ab11-166">값</span><span class="sxs-lookup"><span data-stu-id="5ab11-166">ValueQuantity.Value</span></span>

<span data-ttu-id="5ab11-167">Argonaut 필드 외에도 멋진 사용자 환경을 위해 환자 앱은 다음 필드도 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="5ab11-167">In addition to the Argonaut fields, for a great user experience the Patients app also reads the following fields:</span></span>

 - <span data-ttu-id="5ab11-168">코드. 표시</span><span class="sxs-lookup"><span data-stu-id="5ab11-168">Code.Coding.Display</span></span>
 - <span data-ttu-id="5ab11-169">단위</span><span class="sxs-lookup"><span data-stu-id="5ab11-169">ValueQuantity.Unit</span></span>

<span data-ttu-id="5ab11-170">구성 요소 관찰을 사용 하는 경우 각 구성 요소 관찰에 대해 동일한 논리가 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5ab11-170">If using component observations, the same logic applies for each component observation.</span></span>

<span data-ttu-id="5ab11-171">리소스 검색에서 GET 메서드 및 다음 매개 변수를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ab11-171">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="5ab11-172">환자 =\<patient id\></span><span class="sxs-lookup"><span data-stu-id="5ab11-172">patient=\<patient id\></span></span>
 - <span data-ttu-id="5ab11-173">sort: desc =\<field ex. date\></span><span class="sxs-lookup"><span data-stu-id="5ab11-173">sort:desc=\<field ex. date\></span></span>

<span data-ttu-id="5ab11-174">목표는 환자, [VitalSigns] (관람?)에 대 한 최신 필수 서명을 검색할 수 있다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="5ab11-174">The goal is to be able to retrieve the latest vital signs for a patient, [VitalSigns.DSTU.saz]  (observation?).</span></span>

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

<span data-ttu-id="5ab11-175">[https://www.hl7.org/fhir/DSTU2/Observation.html](https://www.hl7.org/fhir/DSTU2/Observation.html)이 필드 집합에 대 한 자세한 내용은을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5ab11-175">See [https://www.hl7.org/fhir/DSTU2/Observation.html](https://www.hl7.org/fhir/DSTU2/Observation.html) for other details on this field set.</span></span>

## <a name="condition"></a><span data-ttu-id="5ab11-176">조건</span><span class="sxs-lookup"><span data-stu-id="5ab11-176">Condition</span></span>

<span data-ttu-id="5ab11-177">다음은 [Argonaut condition 프로필](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html)의 하위 집합인 최소 필수 필드입니다.</span><span class="sxs-lookup"><span data-stu-id="5ab11-177">These are the minimum required fields, which are a subset of the [Argonaut condition profile](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html):</span></span>

1. <span data-ttu-id="5ab11-178">코드. 코딩 [0]. 표시</span><span class="sxs-lookup"><span data-stu-id="5ab11-178">Code.Coding[0].Display</span></span>

<span data-ttu-id="5ab11-179">Argonaut 필드 외에도 멋진 사용자 환경을 위해 환자 앱에서는 다음 필드도 읽을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ab11-179">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following fields:</span></span>

 - <span data-ttu-id="5ab11-180">기록 된 날짜</span><span class="sxs-lookup"><span data-stu-id="5ab11-180">Date Recorded</span></span>
 - <span data-ttu-id="5ab11-181">문제의</span><span class="sxs-lookup"><span data-stu-id="5ab11-181">Severity</span></span>

<span data-ttu-id="5ab11-182">리소스 검색에서 GET 메서드 및 다음 매개 변수를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ab11-182">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="5ab11-183">환자 =\<patient id></span><span class="sxs-lookup"><span data-stu-id="5ab11-183">patient=\<patient id></span></span>
 - <span data-ttu-id="5ab11-184">_count =\<max results></span><span class="sxs-lookup"><span data-stu-id="5ab11-184">_count=\<max results></span></span>

<span data-ttu-id="5ab11-185">이 통화의 다음 예제를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5ab11-185">See the following example of this call:</span></span>

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

<span data-ttu-id="5ab11-186">[https://www.hl7.org/fhir/DSTU2/Condition.html](https://www.hl7.org/fhir/DSTU2/Condition.html)이 필드 집합에 대 한 자세한 내용은을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5ab11-186">See [https://www.hl7.org/fhir/DSTU2/Condition.html](https://www.hl7.org/fhir/DSTU2/Condition.html) for other details on this field set.</span></span>

## <a name="encounter"></a><span data-ttu-id="5ab11-187">문제가</span><span class="sxs-lookup"><span data-stu-id="5ab11-187">Encounter</span></span>

<span data-ttu-id="5ab11-188">미국 핵심 발생 프로필 "있어야 하는" 필드의 하위 집합인 최소 필수 필드는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="5ab11-188">These are the minimum required fields, which are a subset of the US Core Encounter profile "must have" fields:</span></span>

 - <span data-ttu-id="5ab11-189">상태</span><span class="sxs-lookup"><span data-stu-id="5ab11-189">Status</span></span>
 - <span data-ttu-id="5ab11-190">[0]을 입력 합니다. 코딩 [0]. 표시</span><span class="sxs-lookup"><span data-stu-id="5ab11-190">Type[0].Coding[0].Display</span></span>

<span data-ttu-id="5ab11-191">또한 미국 Core 발생 프로필의 "지원 해야 하는" 필드는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="5ab11-191">In addition, the following fields from US Core Encounter profile's "must support" fields</span></span>

 - <span data-ttu-id="5ab11-192">기간. 시작</span><span class="sxs-lookup"><span data-stu-id="5ab11-192">Period.Start</span></span>
 - <span data-ttu-id="5ab11-193">위치 [0]. 위치. 표시</span><span class="sxs-lookup"><span data-stu-id="5ab11-193">Location[0].Location.Display</span></span>

<span data-ttu-id="5ab11-194">리소스 검색에서 GET 메서드 및 다음 매개 변수를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ab11-194">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="5ab11-195">환자 =\<patient id></span><span class="sxs-lookup"><span data-stu-id="5ab11-195">patient=\<patient id></span></span>
 - <span data-ttu-id="5ab11-196">_sort: desc =\<field ex. date></span><span class="sxs-lookup"><span data-stu-id="5ab11-196">_sort:desc=\<field ex. date></span></span>
 - <span data-ttu-id="5ab11-197">_count =\<max results></span><span class="sxs-lookup"><span data-stu-id="5ab11-197">_count=\<max results></span></span>

<span data-ttu-id="5ab11-198">목표는 환자 마지막으로 알려진 위치를 검색할 수 있다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="5ab11-198">The goal is to be able to retrieve the patient's last known location.</span></span> <span data-ttu-id="5ab11-199">각 발생은 위치 리소스를 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ab11-199">Each encounter references a location resource.</span></span> <span data-ttu-id="5ab11-200">또한 참조에는 위치의 표시 필드도 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5ab11-200">The reference shall also include the location's display field.</span></span> <span data-ttu-id="5ab11-201">이 통화의 다음 예제를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5ab11-201">See the following example of this call.</span></span>

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

<span data-ttu-id="5ab11-202">[https://www.hl7.org/fhir/DSTU2/Encounter.htm](https://www.hl7.org/fhir/DSTU2/Encounter.htm)이 필드 집합에 대 한 자세한 내용은을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5ab11-202">See [https://www.hl7.org/fhir/DSTU2/Encounter.htm](https://www.hl7.org/fhir/DSTU2/Encounter.htm) for other details on this field set.</span></span>

## <a name="allergyintolerance"></a><span data-ttu-id="5ab11-203">AllergyIntolerance</span><span class="sxs-lookup"><span data-stu-id="5ab11-203">AllergyIntolerance</span></span>

<span data-ttu-id="5ab11-204">다음은 Argonaut AllergyIntolerance 프로필의 하위 집합인 최소 필수 필드입니다.</span><span class="sxs-lookup"><span data-stu-id="5ab11-204">These are the minimum required fields, which are a subset of the Argonaut AllergyIntolerance profile:</span></span>

 - <span data-ttu-id="5ab11-205">코드. 텍스트</span><span class="sxs-lookup"><span data-stu-id="5ab11-205">Code.Text</span></span>
 - <span data-ttu-id="5ab11-206">코드. 코딩 [0]. 표시</span><span class="sxs-lookup"><span data-stu-id="5ab11-206">Code.Coding[0].Display</span></span>
 - <span data-ttu-id="5ab11-207">상태</span><span class="sxs-lookup"><span data-stu-id="5ab11-207">Status</span></span>

<span data-ttu-id="5ab11-208">Argonaut 필드 외에도 멋진 사용자 환경을 위해 환자 앱은 다음 필드도 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="5ab11-208">In addition to the Argonaut fields, for a great user experience the Patients app also reads the following fields:</span></span>

 - <span data-ttu-id="5ab11-209">RecordedDate</span><span class="sxs-lookup"><span data-stu-id="5ab11-209">RecordedDate</span></span>
 - <span data-ttu-id="5ab11-210">참고. 텍스트</span><span class="sxs-lookup"><span data-stu-id="5ab11-210">Note.Text</span></span>
 - <span data-ttu-id="5ab11-211">[...]에 반응 합니다. 물질. 텍스트</span><span class="sxs-lookup"><span data-stu-id="5ab11-211">Reaction[..].Substance.Text</span></span>
 - <span data-ttu-id="5ab11-212">[...]에 반응 합니다. Manifestation[..]. 본문</span><span class="sxs-lookup"><span data-stu-id="5ab11-212">Reaction[..].Manifestation[..].Text</span></span>
 - <span data-ttu-id="5ab11-213">텍스트. i v</span><span class="sxs-lookup"><span data-stu-id="5ab11-213">Text.Div</span></span>

<span data-ttu-id="5ab11-214">리소스 검색에서 GET 메서드 및 다음 매개 변수를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ab11-214">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="5ab11-215">환자 =  \<patient id></span><span class="sxs-lookup"><span data-stu-id="5ab11-215">Patient =  \<patient id></span></span>

<span data-ttu-id="5ab11-216">이 통화의 다음 예제를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5ab11-216">See the following example of this call:</span></span>

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

<span data-ttu-id="5ab11-217">[https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html](https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html)이 필드 집합에 대 한 자세한 내용은을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5ab11-217">See [https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html](https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html) for other details on this field set.</span></span>

## <a name="medication-order"></a><span data-ttu-id="5ab11-218">투약 주문</span><span class="sxs-lookup"><span data-stu-id="5ab11-218">Medication Order</span></span>

<span data-ttu-id="5ab11-219">다음은 Argonaut MedicationOrder 프로필의 하위 집합인 최소 필수 필드입니다.</span><span class="sxs-lookup"><span data-stu-id="5ab11-219">These are the minimum required fields, which are a subset of the Argonaut MedicationOrder profile:</span></span>

 - <span data-ttu-id="5ab11-220">기록 된 날짜</span><span class="sxs-lookup"><span data-stu-id="5ab11-220">DateWritten</span></span>
 - <span data-ttu-id="5ab11-221">Prescriber</span><span class="sxs-lookup"><span data-stu-id="5ab11-221">Prescriber.Display</span></span>
 - <span data-ttu-id="5ab11-222">투약. 표시 (참조 하는 경우)</span><span class="sxs-lookup"><span data-stu-id="5ab11-222">Medication.Display (if reference)</span></span>
 - <span data-ttu-id="5ab11-223">투약. 텍스트 (if 개념)</span><span class="sxs-lookup"><span data-stu-id="5ab11-223">Medication.Text (if concept)</span></span>

<span data-ttu-id="5ab11-224">Argonaut 필드 외에도 멋진 사용자 환경을 위해 환자 앱에서는 다음 필드도 읽을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ab11-224">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following fields:</span></span>

 - <span data-ttu-id="5ab11-225">날짜 종료</span><span class="sxs-lookup"><span data-stu-id="5ab11-225">DateEnded</span></span>
 - <span data-ttu-id="5ab11-226">DosageInstruction</span><span class="sxs-lookup"><span data-stu-id="5ab11-226">DosageInstruction.Text</span></span>
 - <span data-ttu-id="5ab11-227">텍스트. i v</span><span class="sxs-lookup"><span data-stu-id="5ab11-227">Text.Div</span></span>

<span data-ttu-id="5ab11-228">리소스 검색에서 GET 메서드 및 다음 매개 변수를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ab11-228">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="5ab11-229">환자 =\<patient id></span><span class="sxs-lookup"><span data-stu-id="5ab11-229">patient=\<patient id></span></span>
 - <span data-ttu-id="5ab11-230">_count =\<max results></span><span class="sxs-lookup"><span data-stu-id="5ab11-230">_count=\<max results></span></span>

<span data-ttu-id="5ab11-231">이 통화의 다음 예제를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5ab11-231">See the following example of this call:</span></span>

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

<span data-ttu-id="5ab11-232">[https://www.hl7.org/fhir/DSTU2/MedicationOrder.html](https://www.hl7.org/fhir/DSTU2/MedicationOrder.html)이 필드 집합에 대 한 자세한 내용은을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5ab11-232">See [https://www.hl7.org/fhir/DSTU2/MedicationOrder.html](https://www.hl7.org/fhir/DSTU2/MedicationOrder.html) for other details on this field set.</span></span>

## <a name="coverage"></a><span data-ttu-id="5ab11-233">통신이</span><span class="sxs-lookup"><span data-stu-id="5ab11-233">Coverage</span></span>

<span data-ttu-id="5ab11-234">미국 Core 또는 Argonaut 프로필에서 다루지 않는 최소 필수 필드는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="5ab11-234">These are the minimum required fields, not covered by either US Core or Argonaut profiles:</span></span>

 - <span data-ttu-id="5ab11-235">Payor</span><span class="sxs-lookup"><span data-stu-id="5ab11-235">Payor</span></span>

<span data-ttu-id="5ab11-236">리소스 검색에서 GET 메서드 및 다음 매개 변수를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ab11-236">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="5ab11-237">환자 =\<patient id></span><span class="sxs-lookup"><span data-stu-id="5ab11-237">patient=\<patient id></span></span>

<span data-ttu-id="5ab11-238">이 통화의 다음 예제를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5ab11-238">See the following example of this call:</span></span>

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
    
<span data-ttu-id="5ab11-239">[https://www.hl7.org/fhir/DSTU2/Coverage.html](https://www.hl7.org/fhir/DSTU2/Coverage.html)이 필드 집합에 대 한 자세한 내용은을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5ab11-239">See [https://www.hl7.org/fhir/DSTU2/Coverage.html](https://www.hl7.org/fhir/DSTU2/Coverage.html) for other details on this field set.</span></span>

## <a name="location"></a><span data-ttu-id="5ab11-240">위치</span><span class="sxs-lookup"><span data-stu-id="5ab11-240">Location</span></span>

<span data-ttu-id="5ab11-241">이 리소스는 [발생](#encounter) 리소스에 대 한 참조로만 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5ab11-241">This resource is only being used as a reference on the [Encounter](#encounter) resource.</span></span>

<span data-ttu-id="5ab11-242">[https://www.hl7.org/fhir/DSTU2/Location.html](https://www.hl7.org/fhir/DSTU2/Location.html)이 필드 집합에 대 한 자세한 내용은을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5ab11-242">See [https://www.hl7.org/fhir/DSTU2/Location.html](https://www.hl7.org/fhir/DSTU2/Location.html) for other details on this field set.</span></span>
