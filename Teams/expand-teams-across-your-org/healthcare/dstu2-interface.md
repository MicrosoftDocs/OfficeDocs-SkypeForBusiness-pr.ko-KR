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
ms.openlocfilehash: ab502f66785af7947185fb0fbee0d3a55dd70c67
ms.sourcegitcommit: f4f5ad1391b472d64390180c81c2680f011a8a10
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2020
ms.locfileid: "48367608"
---
# <a name="dstu2-interface-specification"></a><span data-ttu-id="26524-103">DSTU2 인터페이스 사양</span><span class="sxs-lookup"><span data-stu-id="26524-103">DSTU2 interface specification</span></span>

> [!IMPORTANT]
> <span data-ttu-id="26524-104">**2020 년 10 월 30 일에는 환자 앱이 더 이상 사용 되지 않으며 사용자는 더 이상 팀 앱 스토어에서 설치할 수 없게 됩니다. 지금 팀에서 [목록 앱](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) 사용을 시작 하는 것이 좋습니다.**</span><span class="sxs-lookup"><span data-stu-id="26524-104">**Effective October 30, 2020, the Patients app will be deprecated and users will no longer be able to install it from the Teams app store. We encourage you to start using the [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) in Teams today.**</span></span>
>
><span data-ttu-id="26524-105">환자 앱 데이터는 팀을 백업 하는 Office 365 그룹의 그룹 사서함에 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="26524-105">Patients app data is stored in the group mailbox of the Office 365 group that backs the team.</span></span> <span data-ttu-id="26524-106">환자 앱이 종료 되 면 관련 된 모든 데이터는이 그룹에 보존 되지만 사용자 인터페이스를 통해 더 이상 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="26524-106">When the Patients app is retired, all data associated with it will be retained in this group but can no longer be accessed through the user interface.</span></span> <span data-ttu-id="26524-107">현재 사용자는 [목록 앱](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db)을 사용 하 여 목록을 다시 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26524-107">Current users can re-create their lists using the [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db).</span></span>
>
><span data-ttu-id="26524-108">[목록 앱](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) 은 모든 팀 사용자를 위해 사전 설치 되어 있으며 모든 팀과 채널에서 탭으로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26524-108">The [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) is pre-installed for all Teams users and is available as a tab in every team and channel.</span></span> <span data-ttu-id="26524-109">목록에서 기본 제공 환자 서식 파일을 사용 하거나, 처음부터 또는 Excel로 데이터를 가져오면 환자 목록을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26524-109">With Lists, care teams can create patient lists using the built-in Patients template, from scratch, or by importing data to Excel.</span></span> <span data-ttu-id="26524-110">조직에서 목록 앱을 관리 하는 방법에 대해 자세히 알아보려면 [목록 앱 관리](../../manage-lists-app.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="26524-110">To learn more about how to manage the Lists app in your organization, see [Manage the Lists app](../../manage-lists-app.md).</span></span>

[!INCLUDE [preview-feature](../../includes/preview-feature.md)]

<span data-ttu-id="26524-111">Microsoft 팀 환자 앱을 사용 하도록 FTO r 서버를 설정 또는 재구성 하려면 앱이 액세스 해야 하는 데이터에 대 한 이해가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="26524-111">Setting up or reconfiguring an FHIR server to work with the Microsoft Teams Patients app requires understanding what data the app needs to access.</span></span> <span data-ttu-id="26524-112">FHIR 서버는 다음 리소스에 대해 번들을 사용 하 여 POST 요청을 지원 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="26524-112">The FHIR server must support POST requests using bundles for the following resources:</span></span>

- [<span data-ttu-id="26524-113">환자가</span><span class="sxs-lookup"><span data-stu-id="26524-113">Patient</span></span>](#patient)
- [<span data-ttu-id="26524-114">탑</span><span class="sxs-lookup"><span data-stu-id="26524-114">Observation</span></span>](#observation)
- [<span data-ttu-id="26524-115">조건</span><span class="sxs-lookup"><span data-stu-id="26524-115">Condition</span></span>](#condition)
- [<span data-ttu-id="26524-116">문제가</span><span class="sxs-lookup"><span data-stu-id="26524-116">Encounter</span></span>](#encounter)
- [<span data-ttu-id="26524-117">Allergy intolerance</span><span class="sxs-lookup"><span data-stu-id="26524-117">Allergy intolerance</span></span>](#allergyintolerance)
- [<span data-ttu-id="26524-118">통신이</span><span class="sxs-lookup"><span data-stu-id="26524-118">Coverage</span></span>](#coverage)
- [<span data-ttu-id="26524-119">투약 주문</span><span class="sxs-lookup"><span data-stu-id="26524-119">Medication Order</span></span>](#medication-order)
- [<span data-ttu-id="26524-120">위치</span><span class="sxs-lookup"><span data-stu-id="26524-120">Location</span></span>](#location)

> [!NOTE]
> <span data-ttu-id="26524-121">환자 리소스는 유일한 필수 리소스 이며 앱이 전혀 로드 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="26524-121">The Patient resource is the only mandatory resource (without which the app will not load at all.</span></span> <span data-ttu-id="26524-122">그러나 Microsoft 팀 환자 앱을 사용 하 여 최상의 최종 사용자 환경을 제공 하기 위해 파트너는 위에서 설명한 모든 사양에 대 한 지원을 구현 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="26524-122">However, it is recommended that the Partner implement support for all the above mentioned resources per specifications provided below for the best end-user experience with the Microsoft Teams Patients App.</span></span>

<span data-ttu-id="26524-123">Microsoft 팀 환자 앱에서 두 개 이상의 리소스에 대 한 쿼리는 요청에 대 한 번들 (일괄)을 FHIR 서버의 URL에 게시 합니다.</span><span class="sxs-lookup"><span data-stu-id="26524-123">Queries from the Microsoft Teams Patients app for more than one resource post a bundle (BATCH) of requests to the FHIR server's URL.</span></span> <span data-ttu-id="26524-124">서버는 각 요청을 처리 하 고 각 요청과 일치 하는 리소스의 번들을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="26524-124">The server processes each request and returns a bundle of the resources matched by each request.</span></span> <span data-ttu-id="26524-125">자세한 내용 및 예제는를 참조 하세요 [https://www.hl7.org/fhir/DSTU2/http.html#transaction](https://www.hl7.org/fhir/DSTU2/http.html#transaction) .</span><span class="sxs-lookup"><span data-stu-id="26524-125">For more information and examples, see [https://www.hl7.org/fhir/DSTU2/http.html#transaction](https://www.hl7.org/fhir/DSTU2/http.html#transaction).</span></span>

<span data-ttu-id="26524-126">다음의 모든 팔 로우 리소스는 직접 리소스 참조를 통해 액세스할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="26524-126">All the following FHIR resources should be accessible by direct resource reference.</span></span>

## <a name="conformance-minimum-required-field-set"></a><span data-ttu-id="26524-127">준수 최소 필수 필드 집합</span><span class="sxs-lookup"><span data-stu-id="26524-127">Conformance minimum required field set</span></span>

 <span data-ttu-id="26524-128">FA r 서버는 기능에 대 한 factual 요약을 제공 하기 위해 준수 문을 구현 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="26524-128">The FHIR Server must implement the conformance statement for us to have a factual summary of its capabilities.</span></span> <span data-ttu-id="26524-129">DSTU2 FA r 서버에서 다음 매개 변수가 예상 됩니다.</span><span class="sxs-lookup"><span data-stu-id="26524-129">We expect the below parameters in a DSTU2 FHIR Server:</span></span>

1. <span data-ttu-id="26524-130">받침대</span><span class="sxs-lookup"><span data-stu-id="26524-130">REST</span></span>
   1. <span data-ttu-id="26524-131">모드</span><span class="sxs-lookup"><span data-stu-id="26524-131">Mode</span></span>
   2. <span data-ttu-id="26524-132">개입</span><span class="sxs-lookup"><span data-stu-id="26524-132">Interaction</span></span>
   3. <span data-ttu-id="26524-133">자원: 종류</span><span class="sxs-lookup"><span data-stu-id="26524-133">Resource: Type</span></span>
   4. <span data-ttu-id="26524-134">보안: [OAuth uri 용 확장](https://hl7.org/fhir/extension-oauth-uris.html)</span><span class="sxs-lookup"><span data-stu-id="26524-134">Security: [Extension for OAuth URIs](https://hl7.org/fhir/extension-oauth-uris.html)</span></span>
2. <span data-ttu-id="26524-135">Fto Rversion (코드에는 여러 버전을 지원할 때 피벗할 버전을 파악 하기 위해 필요 합니다.)</span><span class="sxs-lookup"><span data-stu-id="26524-135">FhirVersion (Our code requires this to understand which version we should pivot to as we support multiple versions.)</span></span>

<span data-ttu-id="26524-136">[https://www.hl7.org/fhir/dstu2/conformance.html](https://www.hl7.org/fhir/dstu2/conformance.html)이 필드 집합에 대 한 자세한 내용은을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="26524-136">See [https://www.hl7.org/fhir/dstu2/conformance.html](https://www.hl7.org/fhir/dstu2/conformance.html) for other details on this field set.</span></span>

## <a name="patient"></a><span data-ttu-id="26524-137">환자가</span><span class="sxs-lookup"><span data-stu-id="26524-137">Patient</span></span>

<span data-ttu-id="26524-138">다음은 [Argonaut 환자 프로필](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html) 필드의 하위 집합인 최소 필수 필드입니다.</span><span class="sxs-lookup"><span data-stu-id="26524-138">These are the minimum required fields, which are a subset of the [Argonaut patient profile](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html) fields:</span></span>

1. <span data-ttu-id="26524-139">패밀리 이름</span><span class="sxs-lookup"><span data-stu-id="26524-139">Name.Family</span></span>
2. <span data-ttu-id="26524-140">Name. 지정 된</span><span class="sxs-lookup"><span data-stu-id="26524-140">Name.Given</span></span>
3. <span data-ttu-id="26524-141">성별을</span><span class="sxs-lookup"><span data-stu-id="26524-141">Gender</span></span>
4. <span data-ttu-id="26524-142">생년월일</span><span class="sxs-lookup"><span data-stu-id="26524-142">BirthDate</span></span>
5. <span data-ttu-id="26524-143">MRN (Identifier)</span><span class="sxs-lookup"><span data-stu-id="26524-143">MRN (Identifier)</span></span>

<span data-ttu-id="26524-144">Argonaut 필드 외에도 멋진 사용자 환경을 위해 환자 앱은 다음 필드도 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="26524-144">In addition to the Argonaut fields, for a great user experience the Patients app also reads the following fields:</span></span>

1. <span data-ttu-id="26524-145">이름을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="26524-145">Name.Use</span></span>
2. <span data-ttu-id="26524-146">Name. 접두사</span><span class="sxs-lookup"><span data-stu-id="26524-146">Name.Prefix</span></span>
3. <span data-ttu-id="26524-147">CareProvider (환자 리소스에 대 한이 참조에는 다음 예제에 표시 된 표시 필드가 포함 되어야 합니다.)</span><span class="sxs-lookup"><span data-stu-id="26524-147">CareProvider (This reference on the Patient resource should include the display fields shown in the following example.)</span></span>

* * *

    <span data-ttu-id="26524-148">요청: <fa r-server>/Patient/<환자 번호></span><span class="sxs-lookup"><span data-stu-id="26524-148">Request: GET <fhir-server>/Patient/<patient-id></span></span>
    
    <span data-ttu-id="26524-149">응답: {"resourceType": "환자", "id": "<환자 id>",.</span><span class="sxs-lookup"><span data-stu-id="26524-149">Response: { "resourceType": "Patient", "id": "<patient-id>", .</span></span>
      <span data-ttu-id="26524-150">.</span><span class="sxs-lookup"><span data-stu-id="26524-150">.</span></span>
      <span data-ttu-id="26524-151">.</span><span class="sxs-lookup"><span data-stu-id="26524-151">.</span></span>
      <span data-ttu-id="26524-152">"name": [{"사용": "공식", "전위": ["Mr"], "family": ["Chau"], "지정": ["Hugh"]}], "식별자": [{"사용": "공식", "유형": {"코딩": [{"시스템": "" https://hl7.org/fhir/v2/0203 , "코드": "MR"}]}, "값": "1234567": "성별": "남성", "careProvider": [{"표시": "홍 길동"}],} 1957-06-05</span><span class="sxs-lookup"><span data-stu-id="26524-152">"name": [ { "use": "official", "prefix": [ "Mr" ], "family": [ "Chau" ], "given": [ "Hugh" ] } ], "identifier": [ { "use": "official", "type": { "coding": [ { "system": "https://hl7.org/fhir/v2/0203", "code": "MR" } ] }, "value": "1234567" } ], "gender": "male", "birthDate": "1957-06-05", "careProvider": [{ "display": "Jane Doe" }], }</span></span>

* * *

<span data-ttu-id="26524-153">리소스 검색에서는/Patient/_search 및 다음 매개 변수에 POST 메서드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="26524-153">A resource search uses the POST method at /Patient/_search and the following parameters:</span></span>

1. <span data-ttu-id="26524-154">i</span><span class="sxs-lookup"><span data-stu-id="26524-154">id</span></span>
2. <span data-ttu-id="26524-155">패밀리: contains = (가족 이름에 값이 포함 되어 있는 모든 환자를 검색 합니다.)</span><span class="sxs-lookup"><span data-stu-id="26524-155">family:contains=(searches for all patients whose family name contains the value.)</span></span>
3. <span data-ttu-id="26524-156">지정 =\<substring></span><span class="sxs-lookup"><span data-stu-id="26524-156">given=\<substring></span></span>
4. <span data-ttu-id="26524-157">name =\<substring></span><span class="sxs-lookup"><span data-stu-id="26524-157">name=\<substring></span></span>
5. <span data-ttu-id="26524-158">생년월일 = (정확한 일치)</span><span class="sxs-lookup"><span data-stu-id="26524-158">birthdate=(exact match)</span></span>
6. <span data-ttu-id="26524-159">\_count (반환 해야 하는 최대 결과 수)</span><span class="sxs-lookup"><span data-stu-id="26524-159">\_count (maximum number of results that should be returned)</span></span> <br> <span data-ttu-id="26524-160">응답에는 검색 결과로 반환 되는 레코드의 총 개수가 포함 되어야 하 고, \_ PatientsApp에서 반환 되는 레코드 수를 제한 하기 위해 count가 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="26524-160">The response should contain the total count of records returned as a result of the search, and \_count will be used by the PatientsApp to limit the number of records returned.</span></span>
7. <span data-ttu-id="26524-161">identifier =\<mrn></span><span class="sxs-lookup"><span data-stu-id="26524-161">identifier=\<mrn></span></span>

<span data-ttu-id="26524-162">목표는 다음을 수행 하 여 환자를 검색 하 고 필터링 할 수 있다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="26524-162">The goal is to be able to search and filter for a patient by the following:</span></span>

- <span data-ttu-id="26524-163">ID:이는 모든 자원의 모든 리소스에 있는 자원 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="26524-163">ID: This is the resource ID that every resource in FHIR has.</span></span>
- <span data-ttu-id="26524-164">MRN이는 임상 직원이 알고 있는 환자에 대 한 실제 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="26524-164">MRN: This is the actual identifier for the patient that clinical staff would know.</span></span> <span data-ttu-id="26524-165">이 MRN는 FA r의 식별자 리소스 내에 있는 식별자 유형을 기반으로 한다는 것을 이해 합니다.</span><span class="sxs-lookup"><span data-stu-id="26524-165">We understand this MRN is based on the type of identifier inside the identifier resource in FHIR</span></span>
- <span data-ttu-id="26524-166">이름</span><span class="sxs-lookup"><span data-stu-id="26524-166">Name</span></span>
- <span data-ttu-id="26524-167">생년월일</span><span class="sxs-lookup"><span data-stu-id="26524-167">Birthdate</span></span>

<span data-ttu-id="26524-168">이 통화의 다음 예제를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="26524-168">See the following example  of this call.</span></span>

* * *

    <span data-ttu-id="26524-169">요청: POST <fa r-서버>/Patient/_search 요청 본문: 지정 = hugh&family = chau</span><span class="sxs-lookup"><span data-stu-id="26524-169">Request: POST <fhir-server>/Patient/_search Request Body: given=hugh&family=chau</span></span>
    
    <span data-ttu-id="26524-170">응답: {"resourceType": "번들", "id": "<번들 id>",.</span><span class="sxs-lookup"><span data-stu-id="26524-170">Response: { "resourceType": "Bundle", "id": "<bundle-id>", .</span></span>
      <span data-ttu-id="26524-171">.</span><span class="sxs-lookup"><span data-stu-id="26524-171">.</span></span>
      <span data-ttu-id="26524-172">.</span><span class="sxs-lookup"><span data-stu-id="26524-172">.</span></span>
      <span data-ttu-id="26524-173">"항목": [{"리소스": {"resourceType": "환자", "id": "<환자 id>", "name": [{"텍스트": "Hugh Chau", "가족": ["Chau"], "지정": ["Hugh"]}], "성별": "1957-06-05"}, "검색": {"mode": "match"}}]}</span><span class="sxs-lookup"><span data-stu-id="26524-173">"entry": [ { "resource": { "resourceType": "Patient", "id": "<patient-id>", "name": [ { "text": "Hugh Chau", "family": [ "Chau" ], "given": [ "Hugh" ] } ], "gender": "male", "birthDate": "1957-06-05" }, "search": { "mode": "match" } } ] }</span></span>

* * *

<span data-ttu-id="26524-174">[https://www.hl7.org/fhir/DSTU2/Patient.html](https://www.hl7.org/fhir/DSTU2/Patient.html)이 필드 집합에 대 한 자세한 내용은을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="26524-174">See [https://www.hl7.org/fhir/DSTU2/Patient.html](https://www.hl7.org/fhir/DSTU2/Patient.html) for other details on this field set.</span></span>

## <a name="observation"></a><span data-ttu-id="26524-175">탑</span><span class="sxs-lookup"><span data-stu-id="26524-175">Observation</span></span>

<span data-ttu-id="26524-176">다음은 Argonaut 필수 기호 프로필의 하위 집합인 필요한 최소 필드입니다.</span><span class="sxs-lookup"><span data-stu-id="26524-176">These are the minimum required fields, which are a subset of the Argonaut vital signs profile:</span></span>

 1. <span data-ttu-id="26524-177">유효 (날짜 시간 또는 기간)</span><span class="sxs-lookup"><span data-stu-id="26524-177">Effective (date time or period)</span></span>
 2. <span data-ttu-id="26524-178">코드. 코딩 코드</span><span class="sxs-lookup"><span data-stu-id="26524-178">Code.Coding.Code</span></span>
 3. <span data-ttu-id="26524-179">값</span><span class="sxs-lookup"><span data-stu-id="26524-179">ValueQuantity.Value</span></span>

<span data-ttu-id="26524-180">Argonaut 필드 외에도 멋진 사용자 환경을 위해 환자 앱은 다음 필드도 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="26524-180">In addition to the Argonaut fields, for a great user experience the Patients app also reads the following fields:</span></span>

 1. <span data-ttu-id="26524-181">코드. 표시</span><span class="sxs-lookup"><span data-stu-id="26524-181">Code.Coding.Display</span></span>
 2. <span data-ttu-id="26524-182">단위</span><span class="sxs-lookup"><span data-stu-id="26524-182">ValueQuantity.Unit</span></span>

<span data-ttu-id="26524-183">구성 요소 관찰을 사용 하는 경우 각 구성 요소 관찰에 대해 동일한 논리가 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="26524-183">If using component observations, the same logic applies for each component observation.</span></span>

<span data-ttu-id="26524-184">리소스 검색에서 GET 메서드 및 다음 매개 변수를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="26524-184">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="26524-185">환자 =\<patient id\></span><span class="sxs-lookup"><span data-stu-id="26524-185">patient=\<patient id\></span></span>
2. <span data-ttu-id="26524-186">sort: desc =\<field ex. date\></span><span class="sxs-lookup"><span data-stu-id="26524-186">sort:desc=\<field ex. date\></span></span>

<span data-ttu-id="26524-187">목표는 환자, [VitalSigns] (관람?)에 대 한 최신 필수 서명을 검색할 수 있다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="26524-187">The goal is to be able to retrieve the latest vital signs for a patient, [VitalSigns.DSTU.saz]  (observation?).</span></span>

* * *

    <span data-ttu-id="26524-188">요청: <fa r-서버>/관찰? 환자 =<환자 id>&_sort:d esc = 날짜&category = 필수-기호</span><span class="sxs-lookup"><span data-stu-id="26524-188">Request: GET <fhir-server>/Observation?patient=<patient-id>&_sort:desc=date&category=vital-signs</span></span>
    
    <span data-ttu-id="26524-189">응답: {"resourceType": "번들", "id": "<번들 id>", "": "searchset", "total": 20, "entry": [{"리소스": {"resourceType": "관찰", "id": "<resource-id>", "category": {"코딩": [{code]: "필수-기호"}],}, "코드": {"코딩": [{"시스템": " http://loinc.org ", "코드": "39156-5", "display": "bmi"}],}, "effectiveDateTime": "2009-12-01", "": {"값": 34.4, "단위": "kg/m2", "시스템": " http://unitsofmeasure.org ", "코드": "kg/m2"}},},.</span><span class="sxs-lookup"><span data-stu-id="26524-189">Response: { "resourceType": "Bundle", "id": "<bundle-id>", "type": "searchset", "total": 20, "entry": [ { "resource": { "resourceType": "Observation", "id": "<resource-id>", "category": { "coding": [ { code": "vital-signs" } ], }, "code": { "coding": [ { "system": "http://loinc.org", "code": "39156-5", "display": "bmi" } ], }, "effectiveDateTime": "2009-12-01", "valueQuantity": { "value": 34.4, "unit": "kg/m2", "system": "http://unitsofmeasure.org", "code": "kg/m2" } }, }, .</span></span>
        <span data-ttu-id="26524-190">.</span><span class="sxs-lookup"><span data-stu-id="26524-190">.</span></span>
        <span data-ttu-id="26524-191">.</span><span class="sxs-lookup"><span data-stu-id="26524-191">.</span></span>
      <span data-ttu-id="26524-192">] }</span><span class="sxs-lookup"><span data-stu-id="26524-192">] }</span></span>

* * *

<span data-ttu-id="26524-193">[https://www.hl7.org/fhir/DSTU2/Observation.html](https://www.hl7.org/fhir/DSTU2/Observation.html)이 필드 집합에 대 한 자세한 내용은을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="26524-193">See [https://www.hl7.org/fhir/DSTU2/Observation.html](https://www.hl7.org/fhir/DSTU2/Observation.html) for other details on this field set.</span></span>

## <a name="condition"></a><span data-ttu-id="26524-194">조건</span><span class="sxs-lookup"><span data-stu-id="26524-194">Condition</span></span>

<span data-ttu-id="26524-195">다음은 [Argonaut condition 프로필](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html)의 하위 집합인 최소 필수 필드입니다.</span><span class="sxs-lookup"><span data-stu-id="26524-195">These are the minimum required fields, which are a subset of the [Argonaut condition profile](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html):</span></span>

1. <span data-ttu-id="26524-196">코드. 코딩 [0]. 표시</span><span class="sxs-lookup"><span data-stu-id="26524-196">Code.Coding[0].Display</span></span>

<span data-ttu-id="26524-197">Argonaut 필드 외에도 멋진 사용자 환경을 위해 환자 앱에서는 다음 필드도 읽을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26524-197">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following fields:</span></span>

1. <span data-ttu-id="26524-198">기록 된 날짜</span><span class="sxs-lookup"><span data-stu-id="26524-198">Date Recorded</span></span>
2. <span data-ttu-id="26524-199">문제의</span><span class="sxs-lookup"><span data-stu-id="26524-199">Severity</span></span>

<span data-ttu-id="26524-200">리소스 검색에서 GET 메서드 및 다음 매개 변수를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="26524-200">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="26524-201">환자 =\<patient id></span><span class="sxs-lookup"><span data-stu-id="26524-201">patient=\<patient id></span></span>
2. <span data-ttu-id="26524-202">_count =\<max results></span><span class="sxs-lookup"><span data-stu-id="26524-202">_count=\<max results></span></span>

<span data-ttu-id="26524-203">이 통화의 다음 예제를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="26524-203">See the following example of this call:</span></span>

* * *

    <span data-ttu-id="26524-204">요청: <fa r-server>/Condition? 환자 =<환자-id>&_count = 10</span><span class="sxs-lookup"><span data-stu-id="26524-204">Request: GET <fhir-server>/Condition?patient=<patient-id>&_count=10</span></span>
    
    <span data-ttu-id="26524-205">응답: {"resourceType": "번들", "id": "<번들 id>" "," 유형 ":" searchset "," "resourceType": "": "id": "<리소스 id>", "코드": {"코딩": [{"시스템": " http://snomed.info/sct ", "코드": "386033004", "display": "Neuropathy (nerve 손상)"}]}, "dateRecorded": "2018-09-17", "심각도": {"코딩": [{"시스템": " http://snomed.info/sct ", "코드": "24484000", "display": "심각한"}]}},}]}</span><span class="sxs-lookup"><span data-stu-id="26524-205">Response: {   "resourceType": "Bundle",   "id": "<bundle-id>",   "type": "searchset",   "total": 1,   "entry": [     {       "resource": {         "resourceType": "Condition",         "id": "<resource-id>",         "code": {           "coding": [             {               "system": "http://snomed.info/sct",               "code": "386033004",               "display": "Neuropathy (nerve damage)"             }           ]         },         "dateRecorded": "2018-09-17",         "severity": {           "coding": [             {               "system": "http://snomed.info/sct",               "code": "24484000",               "display": "Severe"             }           ]         }       },     }   ] }</span></span>

* * *

<span data-ttu-id="26524-206">[https://www.hl7.org/fhir/DSTU2/Condition.html](https://www.hl7.org/fhir/DSTU2/Condition.html)이 필드 집합에 대 한 자세한 내용은을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="26524-206">See [https://www.hl7.org/fhir/DSTU2/Condition.html](https://www.hl7.org/fhir/DSTU2/Condition.html) for other details on this field set.</span></span>

## <a name="encounter"></a><span data-ttu-id="26524-207">문제가</span><span class="sxs-lookup"><span data-stu-id="26524-207">Encounter</span></span>

<span data-ttu-id="26524-208">미국 핵심 발생 프로필 "있어야 하는" 필드의 하위 집합인 최소 필수 필드는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="26524-208">These are the minimum required fields, which are a subset of the US Core Encounter profile "must have" fields:</span></span>

1. <span data-ttu-id="26524-209">상태</span><span class="sxs-lookup"><span data-stu-id="26524-209">Status</span></span>
2. <span data-ttu-id="26524-210">[0]을 입력 합니다. 코딩 [0]. 표시</span><span class="sxs-lookup"><span data-stu-id="26524-210">Type[0].Coding[0].Display</span></span>

<span data-ttu-id="26524-211">또한 미국 Core 발생 프로필의 "지원 해야 하는" 필드는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="26524-211">In addition, the following fields from US Core Encounter profile's "must support" fields</span></span>

1. <span data-ttu-id="26524-212">기간. 시작</span><span class="sxs-lookup"><span data-stu-id="26524-212">Period.Start</span></span>
2. <span data-ttu-id="26524-213">위치 [0]. 위치. 표시</span><span class="sxs-lookup"><span data-stu-id="26524-213">Location[0].Location.Display</span></span>

<span data-ttu-id="26524-214">리소스 검색에서 GET 메서드 및 다음 매개 변수를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="26524-214">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="26524-215">환자 =\<patient id></span><span class="sxs-lookup"><span data-stu-id="26524-215">patient=\<patient id></span></span>
2. <span data-ttu-id="26524-216">_sort: desc =\<field ex. date></span><span class="sxs-lookup"><span data-stu-id="26524-216">_sort:desc=\<field ex. date></span></span>
3. <span data-ttu-id="26524-217">_count =\<max results></span><span class="sxs-lookup"><span data-stu-id="26524-217">_count=\<max results></span></span>

<span data-ttu-id="26524-218">목표는 환자 마지막으로 알려진 위치를 검색할 수 있다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="26524-218">The goal is to be able to retrieve the patient's last known location.</span></span> <span data-ttu-id="26524-219">각 발생은 위치 리소스를 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="26524-219">Each encounter references a location resource.</span></span> <span data-ttu-id="26524-220">또한 참조에는 위치의 표시 필드도 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="26524-220">The reference shall also include the location's display field.</span></span> <span data-ttu-id="26524-221">이 통화의 다음 예제를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="26524-221">See the following example of this call.</span></span>
* * *

    <span data-ttu-id="26524-222">요청: <fa r-서버>/발생? 환자 =<환자-id>&_sort:d esc = date&_count = 1</span><span class="sxs-lookup"><span data-stu-id="26524-222">Request: GET <fhir-server>/Encounter?patient=<patient-id>&_sort:desc=date&_count=1</span></span>
    
    <span data-ttu-id="26524-223">응답: {"resourceType": "번들", "유형": "searchset", "total": 1 "항목": [{"resource": {"resourceType": "발생", "id": "<리소스-id>", "식별자": [{"사용": "공식", "value": " <id> "}], "status": "도착", "유형": [{"코딩": [{"표시": "약속"}],}], "환자": {"참조": "환자/<환자 번호>"}, "기간": {"시작": "09/17/2018 1:00:00 PM"}, "위치": [{"위치": {"display": "클리닉"}</span><span class="sxs-lookup"><span data-stu-id="26524-223">Response: {   "resourceType": "Bundle",   "type": "searchset",   "total": 1,   "entry": [     {       "resource": {         "resourceType": "Encounter",         "id": "<resource-id>",         "identifier": [{ "use": "official", "value": "<id>" }],         "status": "arrived",         "type": [           {             "coding": [{ "display": "Appointment" }],           }         ],         "patient": { "reference": "Patient/<patient-id>" },         "period": { "start": "09/17/2018 1:00:00 PM" },         "location": [           {             "location": { "display": "Clinic - ENT" },           }         ]       }     }   ] }</span></span>

* * *

<span data-ttu-id="26524-224">[https://www.hl7.org/fhir/DSTU2/Encounter.htm](https://www.hl7.org/fhir/DSTU2/Encounter.htm)이 필드 집합에 대 한 자세한 내용은을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="26524-224">See [https://www.hl7.org/fhir/DSTU2/Encounter.htm](https://www.hl7.org/fhir/DSTU2/Encounter.htm) for other details on this field set.</span></span>

## <a name="allergyintolerance"></a><span data-ttu-id="26524-225">AllergyIntolerance</span><span class="sxs-lookup"><span data-stu-id="26524-225">AllergyIntolerance</span></span>

<span data-ttu-id="26524-226">다음은 Argonaut AllergyIntolerance 프로필의 하위 집합인 최소 필수 필드입니다.</span><span class="sxs-lookup"><span data-stu-id="26524-226">These are the minimum required fields, which are a subset of the Argonaut AllergyIntolerance profile:</span></span>

1. <span data-ttu-id="26524-227">코드. 텍스트</span><span class="sxs-lookup"><span data-stu-id="26524-227">Code.Text</span></span>
2. <span data-ttu-id="26524-228">코드. 코딩 [0]. 표시</span><span class="sxs-lookup"><span data-stu-id="26524-228">Code.Coding[0].Display</span></span>
3. <span data-ttu-id="26524-229">상태</span><span class="sxs-lookup"><span data-stu-id="26524-229">Status</span></span>

<span data-ttu-id="26524-230">Argonaut 필드 외에도 멋진 사용자 환경을 위해 환자 앱은 다음 필드도 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="26524-230">In addition to the Argonaut fields, for a great user experience the Patients app also reads the following fields:</span></span>

1. <span data-ttu-id="26524-231">RecordedDate</span><span class="sxs-lookup"><span data-stu-id="26524-231">RecordedDate</span></span>
2. <span data-ttu-id="26524-232">참고. 텍스트</span><span class="sxs-lookup"><span data-stu-id="26524-232">Note.Text</span></span>
3. <span data-ttu-id="26524-233">[...]에 반응 합니다. 물질. 텍스트</span><span class="sxs-lookup"><span data-stu-id="26524-233">Reaction[..].Substance.Text</span></span>
4. <span data-ttu-id="26524-234">[...]에 반응 합니다. Manifestation[..]. 본문</span><span class="sxs-lookup"><span data-stu-id="26524-234">Reaction[..].Manifestation[..].Text</span></span>
5. <span data-ttu-id="26524-235">텍스트. i v</span><span class="sxs-lookup"><span data-stu-id="26524-235">Text.Div</span></span>

<span data-ttu-id="26524-236">리소스 검색에서 GET 메서드 및 다음 매개 변수를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="26524-236">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="26524-237">환자 =  \<patient id></span><span class="sxs-lookup"><span data-stu-id="26524-237">Patient =  \<patient id></span></span>

<span data-ttu-id="26524-238">이 통화의 다음 예제를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="26524-238">See the following example of this call:</span></span>

* * *

    <span data-ttu-id="26524-239">요청: <fa r-server>/AllergyIntolerance? 환자 =<환자 id></span><span class="sxs-lookup"><span data-stu-id="26524-239">Request: GET <fhir-server>/AllergyIntolerance?patient=<patient-id></span></span>
    
    <span data-ttu-id="26524-240">응답: {"resourceType": "번들", "id": "<번들 id>", "유형": "searchset", "recordedDate", "total": "" entry ":" resourceType ":" AllergyIntolerance "," id ":" <리소스 id> "," ":" 2018 년 9-17T07:00:00.000 Z "," 물질 ": {" 텍스트 ":" Cas히 고 "" "status": "확인", "반응": [{"물질": {"text": "cas히 고 너트 allergenic Injectable Product"}, "manifestation": [{"텍스트": "Anaphylactic 반응"}]}</span><span class="sxs-lookup"><span data-stu-id="26524-240">Response: {   "resourceType": "Bundle",   "id": "<bundle-id>",   "type": "searchset",   "total": 1,   "entry": [     {       "resource": {         "resourceType": "AllergyIntolerance",         "id": "<resource-id>",         "recordedDate": "2018-09-17T07:00:00.000Z",         "substance": {           "text": "Cashew nuts"         },         "status": "confirmed",         "reaction": [           {             "substance": {               "text": "cashew nut allergenic extract Injectable Product"             },             "manifestation": [               {                 "text": "Anaphylactic reaction"               }             ]           }         ]       }     }   ] }</span></span>

* * *

<span data-ttu-id="26524-241">[https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html](https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html)이 필드 집합에 대 한 자세한 내용은을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="26524-241">See [https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html](https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html) for other details on this field set.</span></span>

## <a name="medication-order"></a><span data-ttu-id="26524-242">투약 주문</span><span class="sxs-lookup"><span data-stu-id="26524-242">Medication Order</span></span>

<span data-ttu-id="26524-243">다음은 Argonaut MedicationOrder 프로필의 하위 집합인 최소 필수 필드입니다.</span><span class="sxs-lookup"><span data-stu-id="26524-243">These are the minimum required fields, which are a subset of the Argonaut MedicationOrder profile:</span></span>

1. <span data-ttu-id="26524-244">기록 된 날짜</span><span class="sxs-lookup"><span data-stu-id="26524-244">DateWritten</span></span>
2. <span data-ttu-id="26524-245">Prescriber</span><span class="sxs-lookup"><span data-stu-id="26524-245">Prescriber.Display</span></span>
3. <span data-ttu-id="26524-246">투약. 표시 (참조 하는 경우)</span><span class="sxs-lookup"><span data-stu-id="26524-246">Medication.Display (if reference)</span></span>
4. <span data-ttu-id="26524-247">투약. 텍스트 (if 개념)</span><span class="sxs-lookup"><span data-stu-id="26524-247">Medication.Text (if concept)</span></span>

<span data-ttu-id="26524-248">Argonaut 필드 외에도 멋진 사용자 환경을 위해 환자 앱에서는 다음 필드도 읽을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26524-248">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following fields:</span></span>

1. <span data-ttu-id="26524-249">날짜 종료</span><span class="sxs-lookup"><span data-stu-id="26524-249">DateEnded</span></span>
2. <span data-ttu-id="26524-250">DosageInstruction</span><span class="sxs-lookup"><span data-stu-id="26524-250">DosageInstruction.Text</span></span>
3. <span data-ttu-id="26524-251">텍스트. i v</span><span class="sxs-lookup"><span data-stu-id="26524-251">Text.Div</span></span>

<span data-ttu-id="26524-252">리소스 검색에서 GET 메서드 및 다음 매개 변수를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="26524-252">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="26524-253">환자 =\<patient id></span><span class="sxs-lookup"><span data-stu-id="26524-253">patient=\<patient id></span></span>
2. <span data-ttu-id="26524-254">_count =\<max results></span><span class="sxs-lookup"><span data-stu-id="26524-254">_count=\<max results></span></span>

<span data-ttu-id="26524-255">이 통화의 다음 예제를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="26524-255">See the following example of this call:</span></span>

* * *

    <span data-ttu-id="26524-256">요청: <fa r-서버>/MedicationOrder? 환자 =<환자 id>&_count = 10</span><span class="sxs-lookup"><span data-stu-id="26524-256">Request: GET <fhir-server>/MedicationOrder?patient=<patient-id>&_count=10</span></span>
    
    <span data-ttu-id="26524-257">응답: {"resourceType": "번들", "id": "<번들 id>", "유형": "searchset", "total": "entry": [{"리소스": {"resourceType": "MedicationOrder", "id": "<리소스 id>" 날짜 기록 ":" 2018-09-17 "," medicationCodeableConcept ": {" text ":" Lisinopril 20 MG Oral 태블릿 "}," prescriber ": {" display ":" "dosageInstruction": [{"text"}</span><span class="sxs-lookup"><span data-stu-id="26524-257">Response: {   "resourceType": "Bundle",   "id": "<bundle-id>",   "type": "searchset",   "total": 1,   "entry": [     {       "resource": {         "resourceType": "MedicationOrder",         "id": "<resource-id>",         "dateWritten": "2018-09-17",         "medicationCodeableConcept": {           "text": "Lisinopril 20 MG Oral Tablet"         },         "prescriber": {           "display": "Jane Doe"         },         "dosageInstruction": [           {             "text": "1 daily"           }         ]       }     }   ] }</span></span>

* * *  

<span data-ttu-id="26524-258">[https://www.hl7.org/fhir/DSTU2/MedicationOrder.html](https://www.hl7.org/fhir/DSTU2/MedicationOrder.html)이 필드 집합에 대 한 자세한 내용은을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="26524-258">See [https://www.hl7.org/fhir/DSTU2/MedicationOrder.html](https://www.hl7.org/fhir/DSTU2/MedicationOrder.html) for other details on this field set.</span></span>

## <a name="coverage"></a><span data-ttu-id="26524-259">통신이</span><span class="sxs-lookup"><span data-stu-id="26524-259">Coverage</span></span>

<span data-ttu-id="26524-260">미국 Core 또는 Argonaut 프로필에서 다루지 않는 최소 필수 필드는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="26524-260">These are the minimum required fields, not covered by either US Core or Argonaut profiles:</span></span>

1. <span data-ttu-id="26524-261">Payor</span><span class="sxs-lookup"><span data-stu-id="26524-261">Payor</span></span>

<span data-ttu-id="26524-262">리소스 검색에서 GET 메서드 및 다음 매개 변수를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="26524-262">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="26524-263">환자 =\<patient id></span><span class="sxs-lookup"><span data-stu-id="26524-263">patient=\<patient id></span></span>

<span data-ttu-id="26524-264">이 통화의 다음 예제를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="26524-264">See the following example of this call:</span></span>

* * *

    <span data-ttu-id="26524-265">요청: <fa r-server>/Coverage? 환자 =<환자 id></span><span class="sxs-lookup"><span data-stu-id="26524-265">Request: GET <fhir-server>/Coverage?patient=<patient-id></span></span>
    
    <span data-ttu-id="26524-266">응답: {"resourceType": "번들", "유형": "searchset", "total": 1, "entry": {"리소스": "resourceType": "커버리지" "," id ":" <자원 id> "," 요금제 ":" 기본 보험 없음 "," 구독자 ": {" 참조 ":" 환자/<환자></span><span class="sxs-lookup"><span data-stu-id="26524-266">Response: {   "resourceType": "Bundle",   "type": "searchset",   "total": 1,   "entry": [     {       "resource": {         "resourceType": "Coverage",         "id": "<resource-id>",         "plan": "No Primary Insurance",         "subscriber": { "reference": "Patient/<patient-id>" }       }     }   ] }</span></span>

* * *

<span data-ttu-id="26524-267">[https://www.hl7.org/fhir/DSTU2/Coverage.html](https://www.hl7.org/fhir/DSTU2/Coverage.html)이 필드 집합에 대 한 자세한 내용은을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="26524-267">See [https://www.hl7.org/fhir/DSTU2/Coverage.html](https://www.hl7.org/fhir/DSTU2/Coverage.html) for other details on this field set.</span></span>

## <a name="location"></a><span data-ttu-id="26524-268">위치</span><span class="sxs-lookup"><span data-stu-id="26524-268">Location</span></span>

<span data-ttu-id="26524-269">이 리소스는 [발생](#encounter) 리소스에 대 한 참조로만 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="26524-269">This resource is only being used as a reference on the [Encounter](#encounter) resource.</span></span>

<span data-ttu-id="26524-270">[https://www.hl7.org/fhir/DSTU2/Location.html](https://www.hl7.org/fhir/DSTU2/Location.html)이 필드 집합에 대 한 자세한 내용은을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="26524-270">See [https://www.hl7.org/fhir/DSTU2/Location.html](https://www.hl7.org/fhir/DSTU2/Location.html) for other details on this field set.</span></span>
