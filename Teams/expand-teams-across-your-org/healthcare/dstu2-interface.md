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
description: Microsoft 팀 환자 앱 EHR 통합
ms.openlocfilehash: 10a6b21e583b5fdd3e70857c4cfc5e7e21a7e988
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42153820"
---
# <a name="dstu2-interface-specification"></a><span data-ttu-id="b2ffd-103">DSTU2 인터페이스 사양</span><span class="sxs-lookup"><span data-stu-id="b2ffd-103">DSTU2 interface specification</span></span>

[!INCLUDE [preview-feature](../../includes/preview-feature.md)]

<span data-ttu-id="b2ffd-104">Microsoft 팀 환자 앱을 사용 하도록 FTO r 서버를 설정 또는 재구성 하려면 앱이 액세스 해야 하는 데이터에 대 한 이해가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="b2ffd-104">Setting up or reconfiguring an FHIR server to work with the Microsoft Teams Patients app requires understanding what data the app needs to access.</span></span> <span data-ttu-id="b2ffd-105">FHIR 서버는 다음 리소스에 대해 번들을 사용 하 여 POST 요청을 지원 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b2ffd-105">The FHIR server must support POST requests using bundles for the following resources:</span></span>

- [<span data-ttu-id="b2ffd-106">환자가</span><span class="sxs-lookup"><span data-stu-id="b2ffd-106">Patient</span></span>](#patient)
- [<span data-ttu-id="b2ffd-107">탑</span><span class="sxs-lookup"><span data-stu-id="b2ffd-107">Observation</span></span>](#observation)
- [<span data-ttu-id="b2ffd-108">조건</span><span class="sxs-lookup"><span data-stu-id="b2ffd-108">Condition</span></span>](#condition)
- [<span data-ttu-id="b2ffd-109">문제가</span><span class="sxs-lookup"><span data-stu-id="b2ffd-109">Encounter</span></span>](#encounter)
- [<span data-ttu-id="b2ffd-110">Allergy intolerance</span><span class="sxs-lookup"><span data-stu-id="b2ffd-110">Allergy intolerance</span></span>](#allergyintolerance)
- [<span data-ttu-id="b2ffd-111">통신이</span><span class="sxs-lookup"><span data-stu-id="b2ffd-111">Coverage</span></span>](#coverage)
- [<span data-ttu-id="b2ffd-112">투약 주문</span><span class="sxs-lookup"><span data-stu-id="b2ffd-112">Medication Order</span></span>](#medication-order)
- [<span data-ttu-id="b2ffd-113">위치</span><span class="sxs-lookup"><span data-stu-id="b2ffd-113">Location</span></span>](#location)

> [!NOTE]
> <span data-ttu-id="b2ffd-114">환자 리소스는 유일한 필수 리소스 이며 앱이 전혀 로드 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b2ffd-114">The Patient resource is the only mandatory resource (without which the app will not load at all.</span></span> <span data-ttu-id="b2ffd-115">그러나 Microsoft 팀 환자 앱을 사용 하 여 최상의 최종 사용자 환경을 제공 하기 위해 파트너는 위에서 설명한 모든 사양에 대 한 지원을 구현 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="b2ffd-115">However, it is recommended that the Partner implement support for all the above mentioned resources per specifications provided below for the best end-user experience with the Microsoft Teams Patients App.</span></span>

<span data-ttu-id="b2ffd-116">Microsoft 팀 환자 앱에서 두 개 이상의 리소스에 대 한 쿼리는 요청에 대 한 번들 (일괄)을 FHIR 서버의 URL에 게시 합니다.</span><span class="sxs-lookup"><span data-stu-id="b2ffd-116">Queries from the Microsoft Teams Patients app for more than one resource post a bundle (BATCH) of requests to the FHIR server's URL.</span></span> <span data-ttu-id="b2ffd-117">서버는 각 요청을 처리 하 고 각 요청과 일치 하는 리소스의 번들을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="b2ffd-117">The server processes each request and returns a bundle of the resources matched by each request.</span></span> <span data-ttu-id="b2ffd-118">자세한 내용 및 예제는를 참조 [https://www.hl7.org/fhir/DSTU2/http.html#transaction](https://www.hl7.org/fhir/DSTU2/http.html#transaction)하세요.</span><span class="sxs-lookup"><span data-stu-id="b2ffd-118">For more information and examples, see [https://www.hl7.org/fhir/DSTU2/http.html#transaction](https://www.hl7.org/fhir/DSTU2/http.html#transaction).</span></span>

<span data-ttu-id="b2ffd-119">다음의 모든 팔 로우 리소스는 직접 리소스 참조를 통해 액세스할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b2ffd-119">All the following FHIR resources should be accessible by direct resource reference.</span></span>

## <a name="conformance-minimum-required-field-set"></a><span data-ttu-id="b2ffd-120">준수 최소 필수 필드 집합</span><span class="sxs-lookup"><span data-stu-id="b2ffd-120">Conformance minimum required field set</span></span>

 <span data-ttu-id="b2ffd-121">FA r 서버는 기능에 대 한 factual 요약을 제공 하기 위해 준수 문을 구현 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b2ffd-121">The FHIR Server must implement the conformance statement for us to have a factual summary of its capabilities.</span></span> <span data-ttu-id="b2ffd-122">DSTU2 FA r 서버에서 다음 매개 변수가 예상 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b2ffd-122">We expect the below parameters in a DSTU2 FHIR Server:</span></span>

1. <span data-ttu-id="b2ffd-123">받침대</span><span class="sxs-lookup"><span data-stu-id="b2ffd-123">REST</span></span>
   1. <span data-ttu-id="b2ffd-124">모드</span><span class="sxs-lookup"><span data-stu-id="b2ffd-124">Mode</span></span>
   2. <span data-ttu-id="b2ffd-125">개입</span><span class="sxs-lookup"><span data-stu-id="b2ffd-125">Interaction</span></span>
   3. <span data-ttu-id="b2ffd-126">자원: 종류</span><span class="sxs-lookup"><span data-stu-id="b2ffd-126">Resource: Type</span></span>
   4. <span data-ttu-id="b2ffd-127">보안: [OAuth uri 용 확장](https://hl7.org/fhir/extension-oauth-uris.html)</span><span class="sxs-lookup"><span data-stu-id="b2ffd-127">Security: [Extension for OAuth URIs](https://hl7.org/fhir/extension-oauth-uris.html)</span></span>
2. <span data-ttu-id="b2ffd-128">Fto Rversion (코드에는 여러 버전을 지원할 때 피벗할 버전을 파악 하기 위해 필요 합니다.)</span><span class="sxs-lookup"><span data-stu-id="b2ffd-128">FhirVersion (Our code requires this to understand which version we should pivot to as we support multiple versions.)</span></span>

<span data-ttu-id="b2ffd-129">이 [https://www.hl7.org/fhir/dstu2/conformance.html](https://www.hl7.org/fhir/dstu2/conformance.html) 필드 집합에 대 한 자세한 내용은을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b2ffd-129">See [https://www.hl7.org/fhir/dstu2/conformance.html](https://www.hl7.org/fhir/dstu2/conformance.html) for other details on this field set.</span></span>

## <a name="patient"></a><span data-ttu-id="b2ffd-130">환자가</span><span class="sxs-lookup"><span data-stu-id="b2ffd-130">Patient</span></span>

<span data-ttu-id="b2ffd-131">다음은 [Argonaut 환자 프로필](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html) 필드의 하위 집합인 최소 필수 필드입니다.</span><span class="sxs-lookup"><span data-stu-id="b2ffd-131">These are the minimum required fields, which are a subset of the [Argonaut patient profile](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html) fields:</span></span>

1. <span data-ttu-id="b2ffd-132">패밀리 이름</span><span class="sxs-lookup"><span data-stu-id="b2ffd-132">Name.Family</span></span>
2. <span data-ttu-id="b2ffd-133">Name. 지정 된</span><span class="sxs-lookup"><span data-stu-id="b2ffd-133">Name.Given</span></span>
3. <span data-ttu-id="b2ffd-134">성별을</span><span class="sxs-lookup"><span data-stu-id="b2ffd-134">Gender</span></span>
4. <span data-ttu-id="b2ffd-135">생년월일</span><span class="sxs-lookup"><span data-stu-id="b2ffd-135">BirthDate</span></span>
5. <span data-ttu-id="b2ffd-136">MRN (Identifier)</span><span class="sxs-lookup"><span data-stu-id="b2ffd-136">MRN (Identifier)</span></span>

<span data-ttu-id="b2ffd-137">Argonaut 필드 외에도 멋진 사용자 환경을 위해 환자 앱은 다음 필드도 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="b2ffd-137">In addition to the Argonaut fields, for a great user experience the Patients app also reads the following fields:</span></span>

1. <span data-ttu-id="b2ffd-138">이름을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b2ffd-138">Name.Use</span></span>
2. <span data-ttu-id="b2ffd-139">Name. 접두사</span><span class="sxs-lookup"><span data-stu-id="b2ffd-139">Name.Prefix</span></span>
3. <span data-ttu-id="b2ffd-140">CareProvider (환자 리소스에 대 한이 참조에는 다음 예제에 표시 된 표시 필드가 포함 되어야 합니다.)</span><span class="sxs-lookup"><span data-stu-id="b2ffd-140">CareProvider (This reference on the Patient resource should include the display fields shown in the following example.)</span></span>

* * *

    <span data-ttu-id="b2ffd-141">요청: <fa r-server>/Patient/<환자 번호></span><span class="sxs-lookup"><span data-stu-id="b2ffd-141">Request: GET <fhir-server>/Patient/<patient-id></span></span>
    
    <span data-ttu-id="b2ffd-142">응답: {"resourceType": "환자", "id": "<환자 id>",.</span><span class="sxs-lookup"><span data-stu-id="b2ffd-142">Response: { "resourceType": "Patient", "id": "<patient-id>", .</span></span>
      <span data-ttu-id="b2ffd-143">.</span><span class="sxs-lookup"><span data-stu-id="b2ffd-143">.</span></span>
      <span data-ttu-id="b2ffd-144">.</span><span class="sxs-lookup"><span data-stu-id="b2ffd-144">.</span></span>
      <span data-ttu-id="b2ffd-145">"name": [{"사용": "공식", "전위": ["Mr"], "family": ["Chau"], "지정": ["Hugh"]}], "식별자": [{"사용": "공식", "유형": {"코딩": [{"시스템": "https://hl7.org/fhir/v2/0203", "코드": "Mr"}]}, "값": "1234567": "성별": "남성", "careProvider": [{"표시": "홍 길동"}],} 1957-06-05</span><span class="sxs-lookup"><span data-stu-id="b2ffd-145">"name": [ { "use": "official", "prefix": [ "Mr" ], "family": [ "Chau" ], "given": [ "Hugh" ] } ], "identifier": [ { "use": "official", "type": { "coding": [ { "system": "https://hl7.org/fhir/v2/0203", "code": "MR" } ] }, "value": "1234567" } ], "gender": "male", "birthDate": "1957-06-05", "careProvider": [{ "display": "Jane Doe" }], }</span></span>

* * *

<span data-ttu-id="b2ffd-146">리소스 검색에서는/Patient/_search 및 다음 매개 변수에 POST 메서드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b2ffd-146">A resource search uses the POST method at /Patient/_search and the following parameters:</span></span>

1. <span data-ttu-id="b2ffd-147">i</span><span class="sxs-lookup"><span data-stu-id="b2ffd-147">id</span></span>
2. <span data-ttu-id="b2ffd-148">패밀리: contains = (가족 이름에 값이 포함 되어 있는 모든 환자를 검색 합니다.)</span><span class="sxs-lookup"><span data-stu-id="b2ffd-148">family:contains=(searches for all patients whose family name contains the value.)</span></span>
3. <span data-ttu-id="b2ffd-149">지정 된\<= 하위 문자열></span><span class="sxs-lookup"><span data-stu-id="b2ffd-149">given=\<substring></span></span>
4. <span data-ttu-id="b2ffd-150">name =\<substring></span><span class="sxs-lookup"><span data-stu-id="b2ffd-150">name=\<substring></span></span>
5. <span data-ttu-id="b2ffd-151">생년월일 = (정확한 일치)</span><span class="sxs-lookup"><span data-stu-id="b2ffd-151">birthdate=(exact match)</span></span>
6. <span data-ttu-id="b2ffd-152">\_count (반환 해야 하는 최대 결과 수)</span><span class="sxs-lookup"><span data-stu-id="b2ffd-152">\_count (maximum number of results that should be returned)</span></span> <br> <span data-ttu-id="b2ffd-153">응답에는 검색 결과로 반환 되는 레코드의 총 개수가 포함 되어야 하 고 \_, PatientsApp에서 반환 되는 레코드 수를 제한 하기 위해 count가 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b2ffd-153">The response should contain the total count of records returned as a result of the search, and \_count will be used by the PatientsApp to limit the number of records returned.</span></span>
7. <span data-ttu-id="b2ffd-154">식별자 =\<mrn</span><span class="sxs-lookup"><span data-stu-id="b2ffd-154">identifier=\<mrn></span></span>

<span data-ttu-id="b2ffd-155">목표는 다음을 수행 하 여 환자를 검색 하 고 필터링 할 수 있다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="b2ffd-155">The goal is to be able to search and filter for a patient by the following:</span></span>

- <span data-ttu-id="b2ffd-156">ID:이는 모든 자원의 모든 리소스에 있는 자원 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="b2ffd-156">ID: This is the resource ID that every resource in FHIR has.</span></span>
- <span data-ttu-id="b2ffd-157">MRN이는 임상 직원이 알고 있는 환자에 대 한 실제 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="b2ffd-157">MRN: This is the actual identifier for the patient that clinical staff would know.</span></span> <span data-ttu-id="b2ffd-158">이 MRN는 FA r의 식별자 리소스 내에 있는 식별자 유형을 기반으로 한다는 것을 이해 합니다.</span><span class="sxs-lookup"><span data-stu-id="b2ffd-158">We understand this MRN is based on the type of identifier inside the identifier resource in FHIR</span></span>
- <span data-ttu-id="b2ffd-159">이름</span><span class="sxs-lookup"><span data-stu-id="b2ffd-159">Name</span></span>
- <span data-ttu-id="b2ffd-160">생년월일</span><span class="sxs-lookup"><span data-stu-id="b2ffd-160">Birthdate</span></span>

<span data-ttu-id="b2ffd-161">이 통화의 다음 예제를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b2ffd-161">See the following example  of this call.</span></span>

* * *

    <span data-ttu-id="b2ffd-162">요청: POST <fa r-서버>/Patient/_search 요청 본문: 지정 = hugh&family = chau</span><span class="sxs-lookup"><span data-stu-id="b2ffd-162">Request: POST <fhir-server>/Patient/_search Request Body: given=hugh&family=chau</span></span>
    
    <span data-ttu-id="b2ffd-163">응답: {"resourceType": "번들", "id": "<번들 id>",.</span><span class="sxs-lookup"><span data-stu-id="b2ffd-163">Response: { "resourceType": "Bundle", "id": "<bundle-id>", .</span></span>
      <span data-ttu-id="b2ffd-164">.</span><span class="sxs-lookup"><span data-stu-id="b2ffd-164">.</span></span>
      <span data-ttu-id="b2ffd-165">.</span><span class="sxs-lookup"><span data-stu-id="b2ffd-165">.</span></span>
      <span data-ttu-id="b2ffd-166">"항목": [{"리소스": {"resourceType": "환자", "id": "<환자 id>", "name": [{"텍스트": "Hugh Chau", "가족": ["Chau"], "지정": ["Hugh"]}], "성별": "1957-06-05"}, "검색": {"mode": "match"}}]}</span><span class="sxs-lookup"><span data-stu-id="b2ffd-166">"entry": [ { "resource": { "resourceType": "Patient", "id": "<patient-id>", "name": [ { "text": "Hugh Chau", "family": [ "Chau" ], "given": [ "Hugh" ] } ], "gender": "male", "birthDate": "1957-06-05" }, "search": { "mode": "match" } } ] }</span></span>

* * *

<span data-ttu-id="b2ffd-167">이 [https://www.hl7.org/fhir/DSTU2/Patient.html](https://www.hl7.org/fhir/DSTU2/Patient.html) 필드 집합에 대 한 자세한 내용은을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b2ffd-167">See [https://www.hl7.org/fhir/DSTU2/Patient.html](https://www.hl7.org/fhir/DSTU2/Patient.html) for other details on this field set.</span></span>

## <a name="observation"></a><span data-ttu-id="b2ffd-168">탑</span><span class="sxs-lookup"><span data-stu-id="b2ffd-168">Observation</span></span>

<span data-ttu-id="b2ffd-169">다음은 Argonaut 필수 기호 프로필의 하위 집합인 필요한 최소 필드입니다.</span><span class="sxs-lookup"><span data-stu-id="b2ffd-169">These are the minimum required fields, which are a subset of the Argonaut vital signs profile:</span></span>

 1. <span data-ttu-id="b2ffd-170">유효 (날짜 시간 또는 기간)</span><span class="sxs-lookup"><span data-stu-id="b2ffd-170">Effective (date time or period)</span></span>
 2. <span data-ttu-id="b2ffd-171">코드. 코딩 코드</span><span class="sxs-lookup"><span data-stu-id="b2ffd-171">Code.Coding.Code</span></span>
 3. <span data-ttu-id="b2ffd-172">값</span><span class="sxs-lookup"><span data-stu-id="b2ffd-172">ValueQuantity.Value</span></span>

<span data-ttu-id="b2ffd-173">Argonaut 필드 외에도 멋진 사용자 환경을 위해 환자 앱은 다음 필드도 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="b2ffd-173">In addition to the Argonaut fields, for a great user experience the Patients app also reads the following fields:</span></span>

 1. <span data-ttu-id="b2ffd-174">코드. 표시</span><span class="sxs-lookup"><span data-stu-id="b2ffd-174">Code.Coding.Display</span></span>
 2. <span data-ttu-id="b2ffd-175">단위</span><span class="sxs-lookup"><span data-stu-id="b2ffd-175">ValueQuantity.Unit</span></span>

<span data-ttu-id="b2ffd-176">구성 요소 관찰을 사용 하는 경우 각 구성 요소 관찰에 대해 동일한 논리가 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b2ffd-176">If using component observations, the same logic applies for each component observation.</span></span>

<span data-ttu-id="b2ffd-177">리소스 검색에서 GET 메서드 및 다음 매개 변수를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b2ffd-177">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="b2ffd-178">환자 =\<환자 일련번호\></span><span class="sxs-lookup"><span data-stu-id="b2ffd-178">patient=\<patient id\></span></span>
2. <span data-ttu-id="b2ffd-179">sort: desc =\<필드 ex</span><span class="sxs-lookup"><span data-stu-id="b2ffd-179">sort:desc=\<field ex.</span></span> <span data-ttu-id="b2ffd-180">시작일\></span><span class="sxs-lookup"><span data-stu-id="b2ffd-180">date\></span></span>

<span data-ttu-id="b2ffd-181">목표는 환자, [VitalSigns] (관람?)에 대 한 최신 필수 서명을 검색할 수 있다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="b2ffd-181">The goal is to be able to retrieve the latest vital signs for a patient, [VitalSigns.DSTU.saz]  (observation?).</span></span>

* * *

    <span data-ttu-id="b2ffd-182">요청: <fa r-서버>/관찰? 환자 =<환자 id>&_sort:d esc = 날짜&category = 필수-기호</span><span class="sxs-lookup"><span data-stu-id="b2ffd-182">Request: GET <fhir-server>/Observation?patient=<patient-id>&_sort:desc=date&category=vital-signs</span></span>
    
    <span data-ttu-id="b2ffd-183">응답: {"resourceType": "번들", "id": "<번들 id>", "": "searchset", "total": 20, "entry": [{"리소스": {"resourceType": "관찰", "id": "<resource-id>", "category": {"코딩": [{code]: "필수-기호"}],}, "코드": {"코딩": [{"시스템": "http://loinc.org", "코드": "39156-5", "display": "bmi"}],}, "effectiveDateTime": "2009-12-01", "": {"값": 34.4, "단위": "kg/m2", "시스템": "http://unitsofmeasure.org", "코드": "kg/m2"}},},.</span><span class="sxs-lookup"><span data-stu-id="b2ffd-183">Response: { "resourceType": "Bundle", "id": "<bundle-id>", "type": "searchset", "total": 20, "entry": [ { "resource": { "resourceType": "Observation", "id": "<resource-id>", "category": { "coding": [ { code": "vital-signs" } ], }, "code": { "coding": [ { "system": "http://loinc.org", "code": "39156-5", "display": "bmi" } ], }, "effectiveDateTime": "2009-12-01", "valueQuantity": { "value": 34.4, "unit": "kg/m2", "system": "http://unitsofmeasure.org", "code": "kg/m2" } }, }, .</span></span>
        <span data-ttu-id="b2ffd-184">.</span><span class="sxs-lookup"><span data-stu-id="b2ffd-184">.</span></span>
        <span data-ttu-id="b2ffd-185">.</span><span class="sxs-lookup"><span data-stu-id="b2ffd-185">.</span></span>
      <span data-ttu-id="b2ffd-186">] }</span><span class="sxs-lookup"><span data-stu-id="b2ffd-186">] }</span></span>

* * *

<span data-ttu-id="b2ffd-187">이 [https://www.hl7.org/fhir/DSTU2/Observation.html](https://www.hl7.org/fhir/DSTU2/Observation.html) 필드 집합에 대 한 자세한 내용은을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b2ffd-187">See [https://www.hl7.org/fhir/DSTU2/Observation.html](https://www.hl7.org/fhir/DSTU2/Observation.html) for other details on this field set.</span></span>

## <a name="condition"></a><span data-ttu-id="b2ffd-188">조건</span><span class="sxs-lookup"><span data-stu-id="b2ffd-188">Condition</span></span>

<span data-ttu-id="b2ffd-189">다음은 [Argonaut condition 프로필](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html)의 하위 집합인 최소 필수 필드입니다.</span><span class="sxs-lookup"><span data-stu-id="b2ffd-189">These are the minimum required fields, which are a subset of the [Argonaut condition profile](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html):</span></span>

1. <span data-ttu-id="b2ffd-190">코드. 코딩 [0]. 표시</span><span class="sxs-lookup"><span data-stu-id="b2ffd-190">Code.Coding[0].Display</span></span>

<span data-ttu-id="b2ffd-191">Argonaut 필드 외에도 멋진 사용자 환경을 위해 환자 앱에서는 다음 필드도 읽을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b2ffd-191">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following fields:</span></span>

1. <span data-ttu-id="b2ffd-192">기록 된 날짜</span><span class="sxs-lookup"><span data-stu-id="b2ffd-192">Date Recorded</span></span>
2. <span data-ttu-id="b2ffd-193">문제의</span><span class="sxs-lookup"><span data-stu-id="b2ffd-193">Severity</span></span>

<span data-ttu-id="b2ffd-194">리소스 검색에서 GET 메서드 및 다음 매개 변수를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b2ffd-194">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="b2ffd-195">환자 =\<환자 id></span><span class="sxs-lookup"><span data-stu-id="b2ffd-195">patient=\<patient id></span></span>
2. <span data-ttu-id="b2ffd-196">_count =\<최대 결과></span><span class="sxs-lookup"><span data-stu-id="b2ffd-196">_count=\<max results></span></span>

<span data-ttu-id="b2ffd-197">이 통화의 다음 예제를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b2ffd-197">See the following example of this call:</span></span>

* * *

    <span data-ttu-id="b2ffd-198">요청: <fa r-server>/Condition? 환자 =<환자-id>&_count = 10</span><span class="sxs-lookup"><span data-stu-id="b2ffd-198">Request: GET <fhir-server>/Condition?patient=<patient-id>&_count=10</span></span>
    
    <span data-ttu-id="b2ffd-199">응답: {"resourceType": "번들", "id": "<번들 id>" "," 유형 ":" searchset "," total ":" entry ": [{" 리소스 ": {" resourceType ":" Condition "," id ":" <리소스 id> "," 코드 ": {" 코딩 ": [{" 시스템 ":" "http://snomed.info/sct," 코드 ":" 386033004 "," display ":" Neuropathy (nerve) "dateRecorded": "심각도": {"코딩": [{"syst 2018-09-17 em ":"http://snomed.info/sct"," 코드 ":" 24484000 "," display ":" 심각 "}]}},}]}</span><span class="sxs-lookup"><span data-stu-id="b2ffd-199">Response: {   "resourceType": "Bundle",   "id": "<bundle-id>",   "type": "searchset",   "total": 1,   "entry": [     {       "resource": {         "resourceType": "Condition",         "id": "<resource-id>",         "code": {           "coding": [             {               "system": "http://snomed.info/sct",               "code": "386033004",               "display": "Neuropathy (nerve damage)"             }           ]         },         "dateRecorded": "2018-09-17",         "severity": {           "coding": [             {               "system": "http://snomed.info/sct",               "code": "24484000",               "display": "Severe"             }           ]         }       },     }   ] }</span></span>

* * *

<span data-ttu-id="b2ffd-200">이 [https://www.hl7.org/fhir/DSTU2/Condition.html](https://www.hl7.org/fhir/DSTU2/Condition.html) 필드 집합에 대 한 자세한 내용은을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b2ffd-200">See [https://www.hl7.org/fhir/DSTU2/Condition.html](https://www.hl7.org/fhir/DSTU2/Condition.html) for other details on this field set.</span></span>

## <a name="encounter"></a><span data-ttu-id="b2ffd-201">문제가</span><span class="sxs-lookup"><span data-stu-id="b2ffd-201">Encounter</span></span>

<span data-ttu-id="b2ffd-202">미국 핵심 발생 프로필 "있어야 하는" 필드의 하위 집합인 최소 필수 필드는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="b2ffd-202">These are the minimum required fields, which are a subset of the US Core Encounter profile “must have” fields:</span></span>

1. <span data-ttu-id="b2ffd-203">상태</span><span class="sxs-lookup"><span data-stu-id="b2ffd-203">Status</span></span>
2. <span data-ttu-id="b2ffd-204">[0]을 입력 합니다. 코딩 [0]. 표시</span><span class="sxs-lookup"><span data-stu-id="b2ffd-204">Type[0].Coding[0].Display</span></span>

<span data-ttu-id="b2ffd-205">또한 미국 Core 발생 프로필의 "지원 해야 하는" 필드는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="b2ffd-205">In addition, the following fields from US Core Encounter profile’s “must support” fields</span></span>

1. <span data-ttu-id="b2ffd-206">기간. 시작</span><span class="sxs-lookup"><span data-stu-id="b2ffd-206">Period.Start</span></span>
2. <span data-ttu-id="b2ffd-207">위치 [0]. 위치. 표시</span><span class="sxs-lookup"><span data-stu-id="b2ffd-207">Location[0].Location.Display</span></span>

<span data-ttu-id="b2ffd-208">리소스 검색에서 GET 메서드 및 다음 매개 변수를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b2ffd-208">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="b2ffd-209">환자 =\<환자 id></span><span class="sxs-lookup"><span data-stu-id="b2ffd-209">patient=\<patient id></span></span>
2. <span data-ttu-id="b2ffd-210">_sort: desc =\<field ex</span><span class="sxs-lookup"><span data-stu-id="b2ffd-210">_sort:desc=\<field ex.</span></span> <span data-ttu-id="b2ffd-211">날짜></span><span class="sxs-lookup"><span data-stu-id="b2ffd-211">date></span></span>
3. <span data-ttu-id="b2ffd-212">_count =\<최대 결과></span><span class="sxs-lookup"><span data-stu-id="b2ffd-212">_count=\<max results></span></span>

<span data-ttu-id="b2ffd-213">목표는 환자 마지막으로 알려진 위치를 검색할 수 있다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="b2ffd-213">The goal is to be able to retrieve the patient’s last known location.</span></span> <span data-ttu-id="b2ffd-214">각 발생은 위치 리소스를 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="b2ffd-214">Each encounter references a location resource.</span></span> <span data-ttu-id="b2ffd-215">또한 참조에는 위치의 표시 필드도 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b2ffd-215">The reference shall also include the location’s display field.</span></span> <span data-ttu-id="b2ffd-216">이 통화의 다음 예제를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b2ffd-216">See the following example of this call.</span></span>
* * *

    <span data-ttu-id="b2ffd-217">요청: <fa r-서버>/발생? 환자 =<환자-id>&_sort:d esc = date&_count = 1</span><span class="sxs-lookup"><span data-stu-id="b2ffd-217">Request: GET <fhir-server>/Encounter?patient=<patient-id>&_sort:desc=date&_count=1</span></span>
    
    <span data-ttu-id="b2ffd-218">응답: {"resourceType": "번들", "유형": "searchset", "total": 1, "항목": [{"리소스": "" resourceType ":" 발생 "," id ":" <리소스-id> "," 식별자 ": [{" 사용 ":" 공식 "," 값 ":"<id>"}]," 상태 ":" 도착 "," 유형 ": [{" 코딩 ": [{" 표시 ": [{" ""),}], "환자": {"" ":" 환자/<환자 ":" "시작": "09/17/2018 1:00:00 PM": "location": [{>              "위치": {"표시": "클리닉"},}]}}]}</span><span class="sxs-lookup"><span data-stu-id="b2ffd-218">Response: {   "resourceType": "Bundle",   "type": "searchset",   "total": 1,   "entry": [     {       "resource": {         "resourceType": "Encounter",         "id": "<resource-id>",         "identifier": [{ "use": "official", "value": "<id>" }],         "status": "arrived",         "type": [           {             "coding": [{ "display": "Appointment" }],           }         ],         "patient": { "reference": "Patient/<patient-id>" },         "period": { "start": "09/17/2018 1:00:00 PM" },         "location": [           {             "location": { "display": "Clinic - ENT" },           }         ]       }     }   ] }</span></span>

* * *

<span data-ttu-id="b2ffd-219">이 [https://www.hl7.org/fhir/DSTU2/Encounter.htm](https://www.hl7.org/fhir/DSTU2/Encounter.htm) 필드 집합에 대 한 자세한 내용은을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b2ffd-219">See [https://www.hl7.org/fhir/DSTU2/Encounter.htm](https://www.hl7.org/fhir/DSTU2/Encounter.htm) for other details on this field set.</span></span>

## <a name="allergyintolerance"></a><span data-ttu-id="b2ffd-220">AllergyIntolerance</span><span class="sxs-lookup"><span data-stu-id="b2ffd-220">AllergyIntolerance</span></span>

<span data-ttu-id="b2ffd-221">다음은 Argonaut AllergyIntolerance 프로필의 하위 집합인 최소 필수 필드입니다.</span><span class="sxs-lookup"><span data-stu-id="b2ffd-221">These are the minimum required fields, which are a subset of the Argonaut AllergyIntolerance profile:</span></span>

1. <span data-ttu-id="b2ffd-222">코드. 텍스트</span><span class="sxs-lookup"><span data-stu-id="b2ffd-222">Code.Text</span></span>
2. <span data-ttu-id="b2ffd-223">코드. 코딩 [0]. 표시</span><span class="sxs-lookup"><span data-stu-id="b2ffd-223">Code.Coding[0].Display</span></span>
3. <span data-ttu-id="b2ffd-224">상태</span><span class="sxs-lookup"><span data-stu-id="b2ffd-224">Status</span></span>

<span data-ttu-id="b2ffd-225">Argonaut 필드 외에도 멋진 사용자 환경을 위해 환자 앱은 다음 필드도 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="b2ffd-225">In addition to the Argonaut fields, for a great user experience the Patients app also reads the following fields:</span></span>

1. <span data-ttu-id="b2ffd-226">RecordedDate</span><span class="sxs-lookup"><span data-stu-id="b2ffd-226">RecordedDate</span></span>
2. <span data-ttu-id="b2ffd-227">참고. 텍스트</span><span class="sxs-lookup"><span data-stu-id="b2ffd-227">Note.Text</span></span>
3. <span data-ttu-id="b2ffd-228">[...]에 반응 합니다. 물질. 텍스트</span><span class="sxs-lookup"><span data-stu-id="b2ffd-228">Reaction[..].Substance.Text</span></span>
4. <span data-ttu-id="b2ffd-229">[...]에 반응 합니다. Manifestation[..]. 본문</span><span class="sxs-lookup"><span data-stu-id="b2ffd-229">Reaction[..].Manifestation[..].Text</span></span>
5. <span data-ttu-id="b2ffd-230">텍스트. i v</span><span class="sxs-lookup"><span data-stu-id="b2ffd-230">Text.Div</span></span>

<span data-ttu-id="b2ffd-231">리소스 검색에서 GET 메서드 및 다음 매개 변수를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b2ffd-231">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="b2ffd-232">환자 = \<환자 id></span><span class="sxs-lookup"><span data-stu-id="b2ffd-232">Patient =  \<patient id></span></span>

<span data-ttu-id="b2ffd-233">이 통화의 다음 예제를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b2ffd-233">See the following example of this call:</span></span>

* * *

    <span data-ttu-id="b2ffd-234">요청: <fa r-server>/AllergyIntolerance? 환자 =<환자 id></span><span class="sxs-lookup"><span data-stu-id="b2ffd-234">Request: GET <fhir-server>/AllergyIntolerance?patient=<patient-id></span></span>
    
    <span data-ttu-id="b2ffd-235">응답: {"resourceType": "번들", "id": "<번들 id>" "," 유형 ":" searchset "," total ":" entry ":" resourceType ":" AllergyIntolerance "," id ":" <리소스 id> "," recordedDate ": 2018 년 9 월-17T07:00:00.000 Z", "물질": {"text": "Cas 너트"}, "상태": "확인 됨", "반응": [{"물질": "cas") "manifestati on ": [{" text ":" Anaphylactic 반응은 "}]}}</span><span class="sxs-lookup"><span data-stu-id="b2ffd-235">Response: {   "resourceType": "Bundle",   "id": "<bundle-id>",   "type": "searchset",   "total": 1,   "entry": [     {       "resource": {         "resourceType": "AllergyIntolerance",         "id": "<resource-id>",         "recordedDate": "2018-09-17T07:00:00.000Z",         "substance": {           "text": "Cashew nuts"         },         "status": "confirmed",         "reaction": [           {             "substance": {               "text": "cashew nut allergenic extract Injectable Product"             },             "manifestation": [               {                 "text": "Anaphylactic reaction"               }             ]           }         ]       }     }   ] }</span></span>

* * *

<span data-ttu-id="b2ffd-236">이 [https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html](https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html) 필드 집합에 대 한 자세한 내용은을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b2ffd-236">See [https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html](https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html) for other details on this field set.</span></span>

## <a name="medication-order"></a><span data-ttu-id="b2ffd-237">투약 주문</span><span class="sxs-lookup"><span data-stu-id="b2ffd-237">Medication Order</span></span>

<span data-ttu-id="b2ffd-238">다음은 Argonaut MedicationOrder 프로필의 하위 집합인 최소 필수 필드입니다.</span><span class="sxs-lookup"><span data-stu-id="b2ffd-238">These are the minimum required fields, which are a subset of the Argonaut MedicationOrder profile:</span></span>

1. <span data-ttu-id="b2ffd-239">기록 된 날짜</span><span class="sxs-lookup"><span data-stu-id="b2ffd-239">DateWritten</span></span>
2. <span data-ttu-id="b2ffd-240">Prescriber</span><span class="sxs-lookup"><span data-stu-id="b2ffd-240">Prescriber.Display</span></span>
3. <span data-ttu-id="b2ffd-241">투약. 표시 (참조 하는 경우)</span><span class="sxs-lookup"><span data-stu-id="b2ffd-241">Medication.Display (if reference)</span></span>
4. <span data-ttu-id="b2ffd-242">투약. 텍스트 (if 개념)</span><span class="sxs-lookup"><span data-stu-id="b2ffd-242">Medication.Text (if concept)</span></span>

<span data-ttu-id="b2ffd-243">Argonaut 필드 외에도 멋진 사용자 환경을 위해 환자 앱에서는 다음 필드도 읽을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b2ffd-243">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following fields:</span></span>

1. <span data-ttu-id="b2ffd-244">날짜 종료</span><span class="sxs-lookup"><span data-stu-id="b2ffd-244">DateEnded</span></span>
2. <span data-ttu-id="b2ffd-245">DosageInstruction</span><span class="sxs-lookup"><span data-stu-id="b2ffd-245">DosageInstruction.Text</span></span>
3. <span data-ttu-id="b2ffd-246">텍스트. i v</span><span class="sxs-lookup"><span data-stu-id="b2ffd-246">Text.Div</span></span>

<span data-ttu-id="b2ffd-247">리소스 검색에서 GET 메서드 및 다음 매개 변수를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b2ffd-247">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="b2ffd-248">환자 =\<환자 id></span><span class="sxs-lookup"><span data-stu-id="b2ffd-248">patient=\<patient id></span></span>
2. <span data-ttu-id="b2ffd-249">_count =\<최대 결과></span><span class="sxs-lookup"><span data-stu-id="b2ffd-249">_count=\<max results></span></span>

<span data-ttu-id="b2ffd-250">이 통화의 다음 예제를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b2ffd-250">See the following example of this call:</span></span>

* * *

    <span data-ttu-id="b2ffd-251">요청: <fa r-서버>/MedicationOrder? 환자 =<환자 id>&_count = 10</span><span class="sxs-lookup"><span data-stu-id="b2ffd-251">Request: GET <fhir-server>/MedicationOrder?patient=<patient-id>&_count=10</span></span>
    
    <span data-ttu-id="b2ffd-252">응답: {"resourceType": "번들", "id": "<번들 id>", "유형": "searchset", "total": "entry": [{"리소스": {"resourceType": "MedicationOrder", "id": "<리소스 id>" 날짜 기록 ":" 2018-09-17 "," medicationCodeableConcept ": {" text ":" Lisinopril 20 MG Oral 태블릿 "}," prescriber ": {" display ":" "dosageInstruction": [{"text"}</span><span class="sxs-lookup"><span data-stu-id="b2ffd-252">Response: {   "resourceType": "Bundle",   "id": "<bundle-id>",   "type": "searchset",   "total": 1,   "entry": [     {       "resource": {         "resourceType": "MedicationOrder",         "id": "<resource-id>",         "dateWritten": "2018-09-17",         "medicationCodeableConcept": {           "text": "Lisinopril 20 MG Oral Tablet"         },         "prescriber": {           "display": "Jane Doe"         },         "dosageInstruction": [           {             "text": "1 daily"           }         ]       }     }   ] }</span></span>

* * *  

<span data-ttu-id="b2ffd-253">이 [https://www.hl7.org/fhir/DSTU2/MedicationOrder.html](https://www.hl7.org/fhir/DSTU2/MedicationOrder.html) 필드 집합에 대 한 자세한 내용은을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b2ffd-253">See [https://www.hl7.org/fhir/DSTU2/MedicationOrder.html](https://www.hl7.org/fhir/DSTU2/MedicationOrder.html) for other details on this field set.</span></span>

## <a name="coverage"></a><span data-ttu-id="b2ffd-254">통신이</span><span class="sxs-lookup"><span data-stu-id="b2ffd-254">Coverage</span></span>

<span data-ttu-id="b2ffd-255">미국 Core 또는 Argonaut 프로필에서 다루지 않는 최소 필수 필드는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="b2ffd-255">These are the minimum required fields, not covered by either US Core or Argonaut profiles:</span></span>

1. <span data-ttu-id="b2ffd-256">Payor</span><span class="sxs-lookup"><span data-stu-id="b2ffd-256">Payor</span></span>

<span data-ttu-id="b2ffd-257">리소스 검색에서 GET 메서드 및 다음 매개 변수를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b2ffd-257">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="b2ffd-258">환자 =\<환자 id></span><span class="sxs-lookup"><span data-stu-id="b2ffd-258">patient=\<patient id></span></span>

<span data-ttu-id="b2ffd-259">이 통화의 다음 예제를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b2ffd-259">See the following example of this call:</span></span>

* * *

    <span data-ttu-id="b2ffd-260">요청: <fa r-server>/Coverage? 환자 =<환자 id></span><span class="sxs-lookup"><span data-stu-id="b2ffd-260">Request: GET <fhir-server>/Coverage?patient=<patient-id></span></span>
    
    <span data-ttu-id="b2ffd-261">응답: {"resourceType": "번들", "유형": "searchset", "total": 1, "entry": {"리소스": "resourceType": "커버리지" "," id ":" <자원 id> "," 요금제 ":" 기본 보험 없음 "," 구독자 ": {" 참조 ":" 환자/<환자></span><span class="sxs-lookup"><span data-stu-id="b2ffd-261">Response: {   "resourceType": "Bundle",   "type": "searchset",   "total": 1,   "entry": [     {       "resource": {         "resourceType": "Coverage",         "id": "<resource-id>",         "plan": "No Primary Insurance",         "subscriber": { "reference": "Patient/<patient-id>" }       }     }   ] }</span></span>

* * *

<span data-ttu-id="b2ffd-262">이 [https://www.hl7.org/fhir/DSTU2/Coverage.html](https://www.hl7.org/fhir/DSTU2/Coverage.html) 필드 집합에 대 한 자세한 내용은을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b2ffd-262">See [https://www.hl7.org/fhir/DSTU2/Coverage.html](https://www.hl7.org/fhir/DSTU2/Coverage.html) for other details on this field set.</span></span>

## <a name="location"></a><span data-ttu-id="b2ffd-263">위치</span><span class="sxs-lookup"><span data-stu-id="b2ffd-263">Location</span></span>

<span data-ttu-id="b2ffd-264">이 리소스는 [발생](#encounter) 리소스에 대 한 참조로만 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b2ffd-264">This resource is only being used as a reference on the [Encounter](#encounter) resource.</span></span>

<span data-ttu-id="b2ffd-265">이 [https://www.hl7.org/fhir/DSTU2/Location.html](https://www.hl7.org/fhir/DSTU2/Location.html) 필드 집합에 대 한 자세한 내용은을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b2ffd-265">See [https://www.hl7.org/fhir/DSTU2/Location.html](https://www.hl7.org/fhir/DSTU2/Location.html) for other details on this field set.</span></span>
