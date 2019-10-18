---
title: 환자 App 및 EHR integration STU3 인터페이스
author: jambirk
ms.author: jambirk
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: MET150
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
appliesto:
- Microsoft Teams
ms.reviewer: anach
description: Microsoft 팀 환자 앱 EHR 통합
ms.openlocfilehash: 836c28f339a3936f03315b005c0eedfc49e0f2ba
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2019
ms.locfileid: "37569246"
---
# <a name="stu3-interface-specification"></a><span data-ttu-id="ed9c6-103">STU3 인터페이스 사양</span><span class="sxs-lookup"><span data-stu-id="ed9c6-103">STU3 interface specification</span></span>

[!INCLUDE [preview-feature](../../includes/preview-feature.md)]

<span data-ttu-id="ed9c6-104">Microsoft 팀 환자 앱을 사용 하도록 FTO r 서버를 설정 또는 재구성 하려면 앱이 액세스 해야 하는 데이터에 대 한 이해가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed9c6-104">Setting up or reconfiguring an FHIR server to work with the Microsoft Teams Patients app requires understanding what data the app needs to access.</span></span> <span data-ttu-id="ed9c6-105">FHIR 서버는 다음 리소스에 대해 번들을 사용 하 여 POST 요청을 지원 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed9c6-105">The FHIR server must support POST requests using bundles for the following resources:</span></span>

- [<span data-ttu-id="ed9c6-106">환자가</span><span class="sxs-lookup"><span data-stu-id="ed9c6-106">Patient</span></span>](#patient)
- [<span data-ttu-id="ed9c6-107">탑</span><span class="sxs-lookup"><span data-stu-id="ed9c6-107">Observation</span></span>](#observation)
- [<span data-ttu-id="ed9c6-108">조건</span><span class="sxs-lookup"><span data-stu-id="ed9c6-108">Condition</span></span>](#condition)
- [<span data-ttu-id="ed9c6-109">문제가</span><span class="sxs-lookup"><span data-stu-id="ed9c6-109">Encounter</span></span>](#encounter)
- [<span data-ttu-id="ed9c6-110">Allergy Intolerance</span><span class="sxs-lookup"><span data-stu-id="ed9c6-110">Allergy Intolerance</span></span>](#allergyintolerance)
- [<span data-ttu-id="ed9c6-111">통신이</span><span class="sxs-lookup"><span data-stu-id="ed9c6-111">Coverage</span></span>](#coverage)
- <span data-ttu-id="ed9c6-112">[투약 문](#medication-request) (DSTU2 버전의 PatientsApp에서 MedicationOrder를 대체 합니다.)</span><span class="sxs-lookup"><span data-stu-id="ed9c6-112">[Medication Statement](#medication-request) (replaces the MedicationOrder in the DSTU2 version of the PatientsApp)</span></span>
- <span data-ttu-id="ed9c6-113">위치 (이 리소스에서 필요로 하는 정보가 발생할 수 있음)</span><span class="sxs-lookup"><span data-stu-id="ed9c6-113">Location (the information needed from this resource can be included in Encounter)</span></span>

> [!NOTE]
> <span data-ttu-id="ed9c6-114">환자 리소스는 유일한 필수 리소스 (앱이 전혀 로드 되지 않는)에만 사용 됩니다. 그러나 Microsoft 팀 환자 앱을 사용 하 여 최상의 최종 사용자 환경을 제공 하기 위해 파트너는 위에서 설명한 모든 사양에 대 한 지원을 구현 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="ed9c6-114">The Patient resource is the only mandatory resource (without which the app will not load at all); However, it is recommended that the Partner implement support for all the above mentioned resources per specifications provided below for the best end-user experience with the Microsoft Teams Patients App.</span></span>

<span data-ttu-id="ed9c6-115">두 개 이상의 리소스에 대 한 Microsoft 팀 환자 앱의 쿼리는 요청에 대 한 번들 (일괄 처리)을 FTO r 서버의 URL에 게시 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed9c6-115">Queries from the Microsoft Teams Patients app for more than one resource shall post a bundle (BATCH) of requests to the FHIR server's URL.</span></span> <span data-ttu-id="ed9c6-116">서버는 각 요청을 처리 하 고 각 요청과 일치 하는 리소스의 번들을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed9c6-116">The server shall process each request and return a bundle of the resources matched by each request.</span></span> <span data-ttu-id="ed9c6-117">자세한 내용 및 예제는를 참조 [https://www.hl7.org/fhir/STU3/http.html#transaction](https://www.hl7.org/fhir/STU3/http.html#transaction)하세요.</span><span class="sxs-lookup"><span data-stu-id="ed9c6-117">For more information and examples, see [https://www.hl7.org/fhir/STU3/http.html#transaction](https://www.hl7.org/fhir/STU3/http.html#transaction).</span></span>

## <a name="capability-statement"></a><span data-ttu-id="ed9c6-118">역량 명세서</span><span class="sxs-lookup"><span data-stu-id="ed9c6-118">Capability Statement</span></span>

<span data-ttu-id="ed9c6-119">최소 필수 필드는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ed9c6-119">These are the minimum required fields:</span></span>

1. <span data-ttu-id="ed9c6-120">받침대</span><span class="sxs-lookup"><span data-stu-id="ed9c6-120">REST</span></span>
   1. <span data-ttu-id="ed9c6-121">모드</span><span class="sxs-lookup"><span data-stu-id="ed9c6-121">Mode</span></span>
   2. <span data-ttu-id="ed9c6-122">개입</span><span class="sxs-lookup"><span data-stu-id="ed9c6-122">Interaction</span></span>
   3. <span data-ttu-id="ed9c6-123">자원: 종류</span><span class="sxs-lookup"><span data-stu-id="ed9c6-123">Resource: Type</span></span>
   4. <span data-ttu-id="ed9c6-124">보안: [OAuth uri 용 확장](http://hl7.org/fhir/extension-oauth-uris.html)</span><span class="sxs-lookup"><span data-stu-id="ed9c6-124">Security: [Extension for OAuth URIs](http://hl7.org/fhir/extension-oauth-uris.html)</span></span>
2. <span data-ttu-id="ed9c6-125">Fto Rversion (코드에는 어떤 버전을 피벗할 것인지 이해 하기 위해 필요 합니다.)</span><span class="sxs-lookup"><span data-stu-id="ed9c6-125">FhirVersion (Our code requires this to understand which version we should pivot to.)</span></span>

<span data-ttu-id="ed9c6-126">이 [https://www.hl7.org/fhir/stu3/capabilitystatement.html](https://www.hl7.org/fhir/stu3/capabilitystatement.html) 필드 집합에 대 한 자세한 내용은을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ed9c6-126">See [https://www.hl7.org/fhir/stu3/capabilitystatement.html](https://www.hl7.org/fhir/stu3/capabilitystatement.html) for other details on this field set.</span></span>

## <a name="patient"></a><span data-ttu-id="ed9c6-127">환자가</span><span class="sxs-lookup"><span data-stu-id="ed9c6-127">Patient</span></span>

<span data-ttu-id="ed9c6-128">다음은 Argonaut 환자 프로필 필드의 하위 집합인 최소 필수 필드입니다.</span><span class="sxs-lookup"><span data-stu-id="ed9c6-128">Here are the minimum required fields, which are a subset of the Argonaut patient profile fields:</span></span>

1. <span data-ttu-id="ed9c6-129">Name. 지정 된</span><span class="sxs-lookup"><span data-stu-id="ed9c6-129">Name.Given</span></span>
2. <span data-ttu-id="ed9c6-130">패밀리 이름</span><span class="sxs-lookup"><span data-stu-id="ed9c6-130">Name.Family</span></span>
3. <span data-ttu-id="ed9c6-131">성별을</span><span class="sxs-lookup"><span data-stu-id="ed9c6-131">Gender</span></span>
4. <span data-ttu-id="ed9c6-132">생년월일</span><span class="sxs-lookup"><span data-stu-id="ed9c6-132">BirthDate</span></span>
5. <span data-ttu-id="ed9c6-133">MRN (Identifier)</span><span class="sxs-lookup"><span data-stu-id="ed9c6-133">MRN (Identifier)</span></span>

<span data-ttu-id="ed9c6-134">[Argonaut 필드](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html)외에도 멋진 사용자 환경을 위해 환자 앱에서는 다음 필드도 읽을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed9c6-134">In addition to the [Argonaut fields](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html), for a great user experience the Patients app can also read the following fields:</span></span>

1. <span data-ttu-id="ed9c6-135">이름을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed9c6-135">Name.Use</span></span>
2. <span data-ttu-id="ed9c6-136">Name. 접두사</span><span class="sxs-lookup"><span data-stu-id="ed9c6-136">Name.Prefix</span></span>
3. <span data-ttu-id="ed9c6-137">[GeneralPractitioner]-GeneralPractitioner 참조는 환자 리소스 (표시 필드에만 해당)에 포함 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed9c6-137">[GeneralPractitioner] - The GeneralPractitioner reference should be included in the Patient resource (display field only)</span></span>

<span data-ttu-id="ed9c6-138">리소스 검색에서는/Patient/_search의 POST 메서드 및 다음 매개 변수를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed9c6-138">A resource search uses the POST method at /Patient/_search and the following parameters:</span></span>

1. <span data-ttu-id="ed9c6-139">i</span><span class="sxs-lookup"><span data-stu-id="ed9c6-139">id</span></span>
2. <span data-ttu-id="ed9c6-140">family = (가족 이름에 값이 포함 되어 있는 모든 환자 검색)</span><span class="sxs-lookup"><span data-stu-id="ed9c6-140">family=(searches for all patients whose family name contains the value)</span></span>
3. <span data-ttu-id="ed9c6-141">지정 된\<= 하위 문자열></span><span class="sxs-lookup"><span data-stu-id="ed9c6-141">given=\<substring></span></span>
4. <span data-ttu-id="ed9c6-142">생년월일 = (정확한 일치)</span><span class="sxs-lookup"><span data-stu-id="ed9c6-142">birthdate=(exact match)</span></span>
5. <span data-ttu-id="ed9c6-143">성별 = (관리자 성별 중 하나에 해당 하는 값)</span><span class="sxs-lookup"><span data-stu-id="ed9c6-143">gender=(values being one of the administrative-gender)</span></span>
6. <span data-ttu-id="ed9c6-144">\_count (반환 해야 하는 최대 결과 수)</span><span class="sxs-lookup"><span data-stu-id="ed9c6-144">\_count (maximum number of results that should be returned)</span></span> <br> <span data-ttu-id="ed9c6-145">응답에는 검색 \_결과에 따라 반환 되는 레코드의 총 개수가 포함 되어야 하며 반환 되는 레코드 수를 제한 하기 위해 PatientsApp에서 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ed9c6-145">The response should contain the total count of records returned as a result of the search and \_count will be used by the PatientsApp to limit the number of records returned.</span></span>
7. <span data-ttu-id="ed9c6-146">식별자 =\<mrn</span><span class="sxs-lookup"><span data-stu-id="ed9c6-146">identifier=\<mrn></span></span>

<span data-ttu-id="ed9c6-147">목표는 다음을 수행 하 여 환자를 검색 하 고 필터링 할 수 있다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="ed9c6-147">The goal is to be able to search and filter for a patient by the following:</span></span>

- <span data-ttu-id="ed9c6-148">ID:이는 모든 자원의 모든 리소스에 있는 자원 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="ed9c6-148">ID: This is the resource ID that every resource in FHIR has.</span></span>
- <span data-ttu-id="ed9c6-149">MRN이는 임상 직원이 알고 있는 환자에 대 한 실제 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="ed9c6-149">MRN: This is the actual identifier for the patient that clinical staff would know.</span></span> <span data-ttu-id="ed9c6-150">이 MRN는 FA r의 식별자 리소스 내에 있는 식별자 유형을 기반으로 이해 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed9c6-150">We understand this MRN is based on the type of identifier inside the identifier resource in FHIR.</span></span>
- <span data-ttu-id="ed9c6-151">이름</span><span class="sxs-lookup"><span data-stu-id="ed9c6-151">Name</span></span>
- <span data-ttu-id="ed9c6-152">생년월일</span><span class="sxs-lookup"><span data-stu-id="ed9c6-152">Birthdate</span></span>

<span data-ttu-id="ed9c6-153">통화에 대 한 다음 예제를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ed9c6-153">See the following example of the call:</span></span>

* * *

    <span data-ttu-id="ed9c6-154">요청: POST <fa r-서버>/Patient/_search 요청 본문: 지정 = ruth&family = black</span><span class="sxs-lookup"><span data-stu-id="ed9c6-154">Request: POST <fhir-server>/Patient/_search Request Body: given=ruth&family=black</span></span>
    
    <span data-ttu-id="ed9c6-155">응답: {"resourceType": "번들", "id": "<번들 id>", "meta": {"lastUpdated": "2019-01-14T23:44:45.052 + 00:00"}, "type": "searchset", "total": "" "link": [{"관계": "self", "url": "entry": [{"> <fullUrl ": <fhir-서버>/Patient/<환자 번호>", "리소스": {"resourceType": "환자", "id": "<환자 id>", "meta": {"" 고 "" "" "" "37.000": "2017-10-18T19:: 2," 텍스트 ": {" status ":" 생성 됨 "," div ":"</span><span class="sxs-lookup"><span data-stu-id="ed9c6-155">Response: { "resourceType": "Bundle", "id": "<bundle-id>", "meta": { "lastUpdated": "2019-01-14T23:44:45.052+00:00" }, "type": "searchset", "total": 1, "link": [ { "relation": "self", "url": <fhir-server>/Patient/_search" } ], "entry": [ { "fullUrl": <fhir-server>/Patient/<patient-id>", "resource": { "resourceType": "Patient", "id": "<patient-id>", "meta": { "versionId": "1", "lastUpdated": "2017-10-18T18:32:37.000+00:00" }, "text": { "status": "generated", "div": "</span></span><div><span data-ttu-id="ed9c6-156">\n</span><span class="sxs-lookup"><span data-stu-id="ed9c6-156">\n</span></span>        <p><span data-ttu-id="ed9c6-157">Ruth 블랙</span><span class="sxs-lookup"><span data-stu-id="ed9c6-157">Ruth Black</span></span></p><span data-ttu-id="ed9c6-158">\n</span><span class="sxs-lookup"><span data-stu-id="ed9c6-158">\n</span></span>      </div><span data-ttu-id="ed9c6-159">"}," 식별자 ": [{" 사용 ":" 보통 "," 유형 ": {" 코딩 ": [{" 시스템 ":"http://hl7.org/fhir/v2/0203"," 코드 ":" MR "," 표시 ":" 의료 레코드 번호 "," userselected ": false}]," 텍스트 ":" 의료 레코드 번호 "}," system "http://hospital.smarthealthit.org:" 1234567 "}]," 활성 ": true" name ": [{" 사용 ":" 공식 "," 가족 ":" Black "," 지정 ": [" Ruth "," C "</span><span class="sxs-lookup"><span data-stu-id="ed9c6-159">" }, "identifier": [ { "use": "usual", "type": { "coding": [ { "system": "http://hl7.org/fhir/v2/0203", "code": "MR", "display": "Medical record number", "userSelected": false } ], "text": "Medical record number" }, "system": "http://hospital.smarthealthit.org", "value": "1234567" } ], "active": true, "name": [ { "use": "official", "family": "Black", "given": [ "Ruth", "C."</span></span>
    <span data-ttu-id="ed9c6-160">]}], "텔레콤": [{"시스템": "phone", "값": "800-599-2739", "사용": "홈"}, {"시스템": "전화", "값": "800-808-7785", "사용": "모바일"}, {"시스템": "전자 메일", "값": "ruth.black@example.com"} "," 성별 ":" 여성 "," 생년월일 ":" 1951-08-23 "," address ": [{" 사용 ":" 집 "," 줄 ": [" 26 남 RdApt 22 "]," city ":" Sapulpa "," 상태 ":" 확인 "," postalCode ":" 74066 "," 국가 ":" 검색 ": {" mode ":" match "}}]}</span><span class="sxs-lookup"><span data-stu-id="ed9c6-160">] } ], "telecom": [ { "system": "phone", "value": "800-599-2739", "use": "home" }, { "system": "phone", "value": "800-808-7785", "use": "mobile" }, { "system": "email", "value": "ruth.black@example.com" } ], "gender": "female", "birthDate": "1951-08-23", "address": [ { "use": "home", "line": [ "26 South RdApt 22" ], "city": "Sapulpa", "state": "OK", "postalCode": "74066", "country": "USA" } ] }, "search": { "mode": "match" } } ] }</span></span>

* * *

    <span data-ttu-id="ed9c6-161">요청: <fa r-server>/Patient/<환자 번호></span><span class="sxs-lookup"><span data-stu-id="ed9c6-161">Request: GET <fhir-server>/Patient/<patient-id></span></span>
    
    <span data-ttu-id="ed9c6-162">응답: {"resourceType": "환자", "id": "<환자 id>", "식별자": [{"사용": "일반적인", "유형": {"코딩": [{"시스템": "http://hl7.org/fhir/v2/0203", "system": "", "code": "MR",}], "텍스트": "의료 레코드 번호"}, "값": [{"사용": "공식", "1234567 family ":" 씨 "," 지정 된 ": [" 다니엘 "," X "</span><span class="sxs-lookup"><span data-stu-id="ed9c6-162">Response: { "resourceType": "Patient", "id": "<patient-id>", "identifier": [ { "use": "usual", "type": { "coding": [ { "system": "http://hl7.org/fhir/v2/0203", "code": "MR", } ], "text": "Medical record number" }, "value": "1234567" } ], "name": [ { "use": "official", "family": "Adams", "given": [ "Daniel", "X."</span></span> <span data-ttu-id="ed9c6-163">]}], "성별": "남성", "생년월일": "1925-12-23",}</span><span class="sxs-lookup"><span data-stu-id="ed9c6-163">] } ], "gender": "male", "birthDate": "1925-12-23", }</span></span>

* * *

<span data-ttu-id="ed9c6-164">이 [http://hl7.org/fhir/stu3/patient.html](http://hl7.org/fhir/stu3/patient.html) 필드 집합에 대 한 자세한 내용은을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ed9c6-164">See [http://hl7.org/fhir/stu3/patient.html](http://hl7.org/fhir/stu3/patient.html) for other details on this field set.</span></span>

## <a name="observation"></a><span data-ttu-id="ed9c6-165">탑</span><span class="sxs-lookup"><span data-stu-id="ed9c6-165">Observation</span></span>

<span data-ttu-id="ed9c6-166">다음은 Argonaut 필수 입력 [프로필](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-vitalsigns.html)의 하위 집합인 필요한 최소 필드입니다.</span><span class="sxs-lookup"><span data-stu-id="ed9c6-166">These are the minimum required fields, which are a subset of the [Argonaut Vital-Signs profile](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-vitalsigns.html).</span></span>

1. <span data-ttu-id="ed9c6-167">유효 (날짜 시간 또는 기간)</span><span class="sxs-lookup"><span data-stu-id="ed9c6-167">Effective (date time or period)</span></span>
2. <span data-ttu-id="ed9c6-168">코드. 코딩 코드</span><span class="sxs-lookup"><span data-stu-id="ed9c6-168">Code.Coding.Code</span></span>
3. <span data-ttu-id="ed9c6-169">값</span><span class="sxs-lookup"><span data-stu-id="ed9c6-169">ValueQuantity.Value</span></span>

<span data-ttu-id="ed9c6-170">Argonaut 필드 외에도 멋진 사용자 환경을 위해 환자 앱에서는 다음 필드도 읽을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed9c6-170">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following fields:</span></span>

1. <span data-ttu-id="ed9c6-171">코드. 표시</span><span class="sxs-lookup"><span data-stu-id="ed9c6-171">Code.Coding.Display</span></span>
2. <span data-ttu-id="ed9c6-172">단위</span><span class="sxs-lookup"><span data-stu-id="ed9c6-172">ValueQuantity.Unit</span></span>

<span data-ttu-id="ed9c6-173">리소스 검색에서 GET 메서드 및 다음 매개 변수를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed9c6-173">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="ed9c6-174">환자 =\<환자 id></span><span class="sxs-lookup"><span data-stu-id="ed9c6-174">patient=\<patient id></span></span>
2. <span data-ttu-id="ed9c6-175">_ 정렬 =-날짜</span><span class="sxs-lookup"><span data-stu-id="ed9c6-175">_sort=-date</span></span>
3. <span data-ttu-id="ed9c6-176">범주 ("category = 필수-서명")에서 중요 한 서명 목록을 검색 하는 방법을 쿼리 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed9c6-176">category (we will query for “category=vital-signs”) to retrieve the list of vital signs.</span></span>

<span data-ttu-id="ed9c6-177">통화에 대 한 다음 예제를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ed9c6-177">Refer to this example of the call:</span></span>

* * *

    <span data-ttu-id="ed9c6-178">요청: <fa r-서버>/관찰? 환자 =<환자 번호>&category = 필수-기호</span><span class="sxs-lookup"><span data-stu-id="ed9c6-178">Request: GET <fhir-server>/Observation?patient=<patient-id>&category=vital-signs</span></span>
    
    <span data-ttu-id="ed9c6-179">응답: {"resourceType": "번들", "id": "<번들-id>", "유형": "searchset", "total": 20, "entry": [{"리소스": {"resourceType": "관찰", "id": "<리소스 id>", "category": "http://hl7.org/fhir/observation-category" "시스템": "", "코드": " 필수-서명 "}],}]," 코드 ": {" 코딩 ": [{" 시스템 ":"http://loinc.org"," code ":" 8867-4 "," display ":" heart_rate "}]}," effectiveDateTime ":" 2009-04-08T00:00:00-06:00 "," # "값": 72.0, "unit": "" 시스템 ":"http://unitsofmeasure.org",}}},.</span><span class="sxs-lookup"><span data-stu-id="ed9c6-179">Response: { "resourceType": "Bundle", "id": "<bundle-id>", "type": "searchset", "total": 20, "entry": [ { "resource": { "resourceType": "Observation", "id": "<resource-id>", "category": [ { "coding": [ { "system": "http://hl7.org/fhir/observation-category", "code": "vital-signs" } ], } ], "code": { "coding": [ { "system": "http://loinc.org", "code": "8867-4", "display": "heart_rate" } ] }, "effectiveDateTime": "2009-04-08T00:00:00-06:00", "valueQuantity": { "value": 72.0, "unit": "{beats}/min", "system": "http://unitsofmeasure.org", } } }, .</span></span>
        <span data-ttu-id="ed9c6-180">.</span><span class="sxs-lookup"><span data-stu-id="ed9c6-180"></span></span>
        <span data-ttu-id="ed9c6-181">.</span><span class="sxs-lookup"><span data-stu-id="ed9c6-181"></span></span>
      <span data-ttu-id="ed9c6-182">] }</span><span class="sxs-lookup"><span data-stu-id="ed9c6-182"></span></span>

* * *

<span data-ttu-id="ed9c6-183">이 [https://www.hl7.org/fhir/stu3/observation.html](https://www.hl7.org/fhir/stu3/observation.html) 필드 집합에 대 한 자세한 내용은을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ed9c6-183">See [https://www.hl7.org/fhir/stu3/observation.html](https://www.hl7.org/fhir/stu3/observation.html) for other details on this field set.</span></span>

## <a name="condition"></a><span data-ttu-id="ed9c6-184">조건</span><span class="sxs-lookup"><span data-stu-id="ed9c6-184">Condition</span></span>

<span data-ttu-id="ed9c6-185">다음은 [Argonaut condition 프로필](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html)의 하위 집합인 필요한 최소 필드입니다.</span><span class="sxs-lookup"><span data-stu-id="ed9c6-185">Here's the minimum required fields, which are a subset of the [Argonaut condition profile](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html).</span></span>

1. <span data-ttu-id="ed9c6-186">코드. 코딩 [0]. 표시</span><span class="sxs-lookup"><span data-stu-id="ed9c6-186">Code.Coding[0].Display</span></span>

<span data-ttu-id="ed9c6-187">Argonaut 필드 외에도 멋진 사용자 환경을 위해 환자 앱에서는 다음 필드도 읽을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed9c6-187">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following fields:</span></span>

1. <span data-ttu-id="ed9c6-188">AssertedDate</span><span class="sxs-lookup"><span data-stu-id="ed9c6-188">AssertedDate</span></span>
2. <span data-ttu-id="ed9c6-189">문제의</span><span class="sxs-lookup"><span data-stu-id="ed9c6-189">Severity</span></span>

<span data-ttu-id="ed9c6-190">리소스 검색에서 GET 메서드 및 다음 매개 변수를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed9c6-190">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="ed9c6-191">환자 =\<환자 id></span><span class="sxs-lookup"><span data-stu-id="ed9c6-191">patient=\<patient id></span></span>
2. <span data-ttu-id="ed9c6-192">개수 =\<최대 결과></span><span class="sxs-lookup"><span data-stu-id="ed9c6-192">_count=\<max results></span></span>

<span data-ttu-id="ed9c6-193">이 통화의 다음 예제를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ed9c6-193">See the following example of this call:</span></span>

* * *

    <span data-ttu-id="ed9c6-194">요청: <fa r-server>/Condition? 환자 =<환자-id>&_count = 10</span><span class="sxs-lookup"><span data-stu-id="ed9c6-194">Request: GET <fhir-server>/Condition?patient=<patient-id>&_count=10</span></span>
    
    <span data-ttu-id="ed9c6-195">응답: {"resourceType": "번들", "id": "<번들 id>", "": "searchset", "total": 2, "entry": [{"리소스": {"resourceType": "Condition", "id": "<resource-id>", "code": {"코딩": [{"시스템": "http://snomed.info/sct", "코드": "185903001", " 표시 ":" influenza immunization ",}]}," 심각도 ": {" 코딩 ": [{" 시스템 ":"http://snomed.info/sct"," 코드 ":" 24484000 "," display ":" 심각도 "}]}," assertedDate ":" 2018-04-04 "}},.</span><span class="sxs-lookup"><span data-stu-id="ed9c6-195">Response: { "resourceType": "Bundle", "id": "<bundle-id>", "type": "searchset", "total": 2, "entry": [ { "resource": { "resourceType": "Condition", "id": "<resource-id>", "code": { "coding": [ { "system": "http://snomed.info/sct", "code": "185903001", "display": "Needs influenza immunization", } ] }, "severity": { "coding": [ { "system": "http://snomed.info/sct", "code": "24484000", "display": "Severe" } ] }, "assertedDate": "2018-04-04" } }, .</span></span>
        <span data-ttu-id="ed9c6-196">.</span><span class="sxs-lookup"><span data-stu-id="ed9c6-196"></span></span>
        <span data-ttu-id="ed9c6-197">.</span><span class="sxs-lookup"><span data-stu-id="ed9c6-197"></span></span>
      <span data-ttu-id="ed9c6-198">] }</span><span class="sxs-lookup"><span data-stu-id="ed9c6-198"></span></span>

* * *
<span data-ttu-id="ed9c6-199">이 [http://hl7.org/fhir/stu3/condition.html](http://hl7.org/fhir/stu3/condition.html) 필드 집합에 대 한 자세한 내용은을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ed9c6-199">See [http://hl7.org/fhir/stu3/condition.html](http://hl7.org/fhir/stu3/condition.html) for other details on this field set.</span></span>

## <a name="encounter"></a><span data-ttu-id="ed9c6-200">문제가</span><span class="sxs-lookup"><span data-stu-id="ed9c6-200">Encounter</span></span>

<span data-ttu-id="ed9c6-201">[미국 핵심 발생 프로필](http://hl7.org/fhir/us/core/2018Jan/StructureDefinition-us-core-encounter.html) 의 하위 집합인 최소 필수 필드는 "필드에" 필드가 있어야 합니다. "</span><span class="sxs-lookup"><span data-stu-id="ed9c6-201">These are the minimum required fields, which are a subset of the [US Core Encounter profile](http://hl7.org/fhir/us/core/2018Jan/StructureDefinition-us-core-encounter.html) “must have” fields).</span></span>

1. <span data-ttu-id="ed9c6-202">상태</span><span class="sxs-lookup"><span data-stu-id="ed9c6-202">Status</span></span>
2. <span data-ttu-id="ed9c6-203">[0]을 입력 합니다. 코딩 [0]. 표시</span><span class="sxs-lookup"><span data-stu-id="ed9c6-203">Type[0].Coding[0].Display</span></span>

<span data-ttu-id="ed9c6-204">또한 미국 Core 발생 프로필의 "지원 해야 하는" 필드에는 다음과 같은 필드가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed9c6-204">In addition, the following fields from US Core Encounter profile’s “must support” fields:</span></span>

1. <span data-ttu-id="ed9c6-205">기간. 시작</span><span class="sxs-lookup"><span data-stu-id="ed9c6-205">Period.Start</span></span>
2. <span data-ttu-id="ed9c6-206">위치 [0]. 위치. 표시</span><span class="sxs-lookup"><span data-stu-id="ed9c6-206">Location[0].Location.Display</span></span>

<span data-ttu-id="ed9c6-207">리소스 검색에서 GET 메서드 및 다음 매개 변수를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed9c6-207">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="ed9c6-208">환자 =\<환자 id></span><span class="sxs-lookup"><span data-stu-id="ed9c6-208">patient=\<patient id></span></span>
2. <span data-ttu-id="ed9c6-209">_ 정렬: desc =\<필드 ex</span><span class="sxs-lookup"><span data-stu-id="ed9c6-209">_sort:desc=\<field ex.</span></span> <span data-ttu-id="ed9c6-210">날짜></span><span class="sxs-lookup"><span data-stu-id="ed9c6-210">date></span></span>
3. <span data-ttu-id="ed9c6-211">개수 =\<최대 결과></span><span class="sxs-lookup"><span data-stu-id="ed9c6-211">_count=\<max results></span></span>

<span data-ttu-id="ed9c6-212">목표는 환자 마지막으로 알려진 위치를 검색할 수 있다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="ed9c6-212">The goal is to be able to retrieve the patient’s last known location.</span></span> <span data-ttu-id="ed9c6-213">각 발생은 위치 리소스를 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed9c6-213">Each encounter references a location resource.</span></span> <span data-ttu-id="ed9c6-214">또한 참조에는 위치의 표시 필드도 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ed9c6-214">The reference shall also include the location’s display field.</span></span>

<span data-ttu-id="ed9c6-215">이 [http://hl7.org/fhir/stu3/encounter.html](http://hl7.org/fhir/stu3/encounter.html) 필드 집합에 대 한 자세한 내용은을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ed9c6-215">See [http://hl7.org/fhir/stu3/encounter.html](http://hl7.org/fhir/stu3/encounter.html) for other details on this field set.</span></span>

## <a name="allergyintolerance"></a><span data-ttu-id="ed9c6-216">AllergyIntolerance</span><span class="sxs-lookup"><span data-stu-id="ed9c6-216">AllergyIntolerance</span></span>

<span data-ttu-id="ed9c6-217">다음은 [Argonaut AllergyIntolerance](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-allergyintolerance.html) 프로필의 하위 집합인 최소 필수 필드입니다.</span><span class="sxs-lookup"><span data-stu-id="ed9c6-217">These are the minimum required fields, which are a subset of the [Argonaut AllergyIntolerance](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-allergyintolerance.html) profile:</span></span>

1. <span data-ttu-id="ed9c6-218">코드. 텍스트</span><span class="sxs-lookup"><span data-stu-id="ed9c6-218">Code.Text</span></span>
2. <span data-ttu-id="ed9c6-219">코드. 코딩 [0]. 표시</span><span class="sxs-lookup"><span data-stu-id="ed9c6-219">Code.Coding[0].Display</span></span>
3. <span data-ttu-id="ed9c6-220">ClinicalStatus/VerificationStatus (두 가지 모두 읽었습니다)</span><span class="sxs-lookup"><span data-stu-id="ed9c6-220">ClinicalStatus/VerificationStatus (we read both)</span></span>

<span data-ttu-id="ed9c6-221">Argonaut 필드 외에도 멋진 사용자 환경을 위해 환자 앱에서 다음 필드도 읽을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed9c6-221">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following field:</span></span>

1. <span data-ttu-id="ed9c6-222">AssertedDate</span><span class="sxs-lookup"><span data-stu-id="ed9c6-222">AssertedDate</span></span>
2. <span data-ttu-id="ed9c6-223">참고. 텍스트</span><span class="sxs-lookup"><span data-stu-id="ed9c6-223">Note.Text</span></span>
3. <span data-ttu-id="ed9c6-224">반응은</span><span class="sxs-lookup"><span data-stu-id="ed9c6-224">Reaction</span></span>
    1. <span data-ttu-id="ed9c6-225">물질 (1 개의 코딩 요소)</span><span class="sxs-lookup"><span data-stu-id="ed9c6-225">Substance (one coding element)</span></span>
    2. <span data-ttu-id="ed9c6-226">Manifestation (1 코딩 요소)</span><span class="sxs-lookup"><span data-stu-id="ed9c6-226">Manifestation (one coding element)</span></span>

<span data-ttu-id="ed9c6-227">리소스 검색에서 GET 메서드 및 다음 매개 변수를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed9c6-227">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="ed9c6-228">환자 = \<환자 id></span><span class="sxs-lookup"><span data-stu-id="ed9c6-228">Patient =  \<patient id></span></span>

<span data-ttu-id="ed9c6-229">통화에 대 한 다음 예제를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ed9c6-229">See the following example of the call:</span></span> 

* * *

    <span data-ttu-id="ed9c6-230">요청: <fa r-server>/AllergyIntolerance? 환자 =<환자 id></span><span class="sxs-lookup"><span data-stu-id="ed9c6-230">Request: GET <fhir-server>/AllergyIntolerance?patient=<patient-id></span></span>
    
    <span data-ttu-id="ed9c6-231">응답: {"resourceType": "번들", "id": "<번들 id>", "유형": "searchset", "type": "#": "" resourceType ":" AllergyIntolerance "," id ":" clinicalStatus> <":" active "," ve rificationStatus ":" 확인 됨 "," 코드 ": {" 코딩 ": [{" 시스템 ":http://rxnav.nlm.nih.gov/REST/Ndfrt" "," 코드 ":" N0000175503 "," display ":" sulfonamide antibacterial ",}]," 텍스트 ":" sulfonamide ant ibacterial "}," assertedDate ":" 2018-01-01T00:00:00-7:00 "," 반응 ": [{" manifestation ": [{" "" "시스템": "http://snomed.info/sct", "코드":  "271807003", "display": "skin rash",}], "text": "skin rash"}]}</span><span class="sxs-lookup"><span data-stu-id="ed9c6-231">Response: {   "resourceType": "Bundle",   "id": "<bundle-id>",   "type": "searchset",   "total": 1,   "entry": [     {       "resource": {         "resourceType": "AllergyIntolerance",         "id": "<resource-id>",         "clinicalStatus": "active",         "verificationStatus": "confirmed",         "code": {           "coding": [             {               "system": "http://rxnav.nlm.nih.gov/REST/Ndfrt",               "code": "N0000175503",               "display": "sulfonamide antibacterial",             }           ],           "text": "sulfonamide antibacterial"         },         "assertedDate": "2018-01-01T00:00:00-07:00",         "reaction": [           {             "manifestation": [               {                 "coding": [                   {                     "system": "http://snomed.info/sct",                     "code": "271807003",                     "display": "skin rash",                   }                 ],                 "text": "skin rash"               }             ],           }         ]       }     }   ] }</span></span>

* * *

<span data-ttu-id="ed9c6-232">이 [http://hl7.org/fhir/stu3/allergyintolerance.html](http://hl7.org/fhir/stu3/allergyintolerance.html) 필드 집합에 대 한 자세한 내용은을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ed9c6-232">See [http://hl7.org/fhir/stu3/allergyintolerance.html](http://hl7.org/fhir/stu3/allergyintolerance.html) for other details on this field set.</span></span>

## <a name="medication-request"></a><span data-ttu-id="ed9c6-233">투약 요청</span><span class="sxs-lookup"><span data-stu-id="ed9c6-233">Medication Request</span></span>

<span data-ttu-id="ed9c6-234">[미국 Core 투약 요청 프로필](http://www.hl7.org/fhir/us/core/StructureDefinition-us-core-medicationrequest.html)의 하위 집합인 최소 필수 필드는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ed9c6-234">These are the minimum required fields, which are a subset of the [US Core Medication Request profile](http://www.hl7.org/fhir/us/core/StructureDefinition-us-core-medicationrequest.html):</span></span>

1. <span data-ttu-id="ed9c6-235">투약. 표시 (참조 하는 경우)</span><span class="sxs-lookup"><span data-stu-id="ed9c6-235">Medication.Display (if Reference)</span></span>
2. <span data-ttu-id="ed9c6-236">투약 (if CodableConcept)</span><span class="sxs-lookup"><span data-stu-id="ed9c6-236">Medication.Text (if CodableConcept)</span></span>
3. <span data-ttu-id="ed9c6-237">기관 Edon</span><span class="sxs-lookup"><span data-stu-id="ed9c6-237">AuthoredOn</span></span>
4. <span data-ttu-id="ed9c6-238">요청자. 에이전트 디스플레이</span><span class="sxs-lookup"><span data-stu-id="ed9c6-238">Requester.Agent.Display</span></span>

<span data-ttu-id="ed9c6-239">멋진 사용자 환경을 위해 미국 Core 필드 외에도 환자 앱에서 다음 필드를 읽을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed9c6-239">In addition to the US Core fields, for a great user experience the Patients app can also read the following fields:</span></span>

1. <span data-ttu-id="ed9c6-240">DosageInstruction[..]. 본문</span><span class="sxs-lookup"><span data-stu-id="ed9c6-240">DosageInstruction[..].Text</span></span>
2. <span data-ttu-id="ed9c6-241">본문</span><span class="sxs-lookup"><span data-stu-id="ed9c6-241">Text</span></span>

<span data-ttu-id="ed9c6-242">리소스 검색에서 GET 메서드 및 다음 매개 변수를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed9c6-242">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="ed9c6-243">환자 =\<환자 id></span><span class="sxs-lookup"><span data-stu-id="ed9c6-243">patient=\<patient id></span></span>
2. <span data-ttu-id="ed9c6-244">개수 =\<최대 결과></span><span class="sxs-lookup"><span data-stu-id="ed9c6-244">_count=\<max results></span></span>

<span data-ttu-id="ed9c6-245">이 [https://www.hl7.org/fhir/medicationrequest.html](https://www.hl7.org/fhir/medicationrequest.html) 필드 집합에 대 한 자세한 내용은을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ed9c6-245">See [https://www.hl7.org/fhir/medicationrequest.html](https://www.hl7.org/fhir/medicationrequest.html) for other details on this field set.</span></span>

## <a name="coverage"></a><span data-ttu-id="ed9c6-246">통신이</span><span class="sxs-lookup"><span data-stu-id="ed9c6-246">Coverage</span></span>

<span data-ttu-id="ed9c6-247">미국 Core 또는 Argonaut 프로필에서 다루지 않는 최소 필수 필드는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ed9c6-247">These are the minimum required fields, not covered by either US Core or Argonaut profiles:</span></span>

1. <span data-ttu-id="ed9c6-248">그룹화에서 하나 이상의 요소를 사용 하 여</span><span class="sxs-lookup"><span data-stu-id="ed9c6-248">Grouping, at least one element with</span></span>
    1. <span data-ttu-id="ed9c6-249">GroupDisplay</span><span class="sxs-lookup"><span data-stu-id="ed9c6-249">GroupDisplay</span></span>
    2. <span data-ttu-id="ed9c6-250">계획 표시</span><span class="sxs-lookup"><span data-stu-id="ed9c6-250">PlanDisplay</span></span>
2. <span data-ttu-id="ed9c6-251">안에</span><span class="sxs-lookup"><span data-stu-id="ed9c6-251">Period</span></span>
3. <span data-ttu-id="ed9c6-252">SubscriberId</span><span class="sxs-lookup"><span data-stu-id="ed9c6-252">SubscriberId</span></span>

<span data-ttu-id="ed9c6-253">리소스 검색에서 GET 메서드 및 다음 매개 변수를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed9c6-253">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="ed9c6-254">환자 = \<환자 id></span><span class="sxs-lookup"><span data-stu-id="ed9c6-254">Patient = \<patient id></span></span>

<span data-ttu-id="ed9c6-255">이 [http://hl7.org/fhir/stu3/coverage.html](https://www.hl7.org/fhir/medicationrequest.html) 필드 집합에 대 한 자세한 내용은을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ed9c6-255">See [http://hl7.org/fhir/stu3/coverage.html](https://www.hl7.org/fhir/medicationrequest.html) for other details on this field set.</span></span>
