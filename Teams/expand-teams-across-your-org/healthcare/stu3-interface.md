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
ms.openlocfilehash: 9282d6b6245b92a675c69ba1fcbf4ad726cdff62
ms.sourcegitcommit: 0a51738879b13991986a3a872445daa8bd20533d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2020
ms.locfileid: "48766901"
---
# <a name="stu3-interface-specification"></a><span data-ttu-id="612ab-103">STU3 인터페이스 사양</span><span class="sxs-lookup"><span data-stu-id="612ab-103">STU3 interface specification</span></span>

> [!IMPORTANT]
> <span data-ttu-id="612ab-104">**2020 년 10 월 30 일에는 환자 앱이 더 이상 사용 되지 않으며 사용자는 더 이상 팀 앱 스토어에서 설치할 수 없게 됩니다. 지금 팀에서 [목록 앱](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) 사용을 시작 하는 것이 좋습니다.**</span><span class="sxs-lookup"><span data-stu-id="612ab-104">**Effective October 30, 2020, the Patients app will be deprecated and users will no longer be able to install it from the Teams app store. We encourage you to start using the [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) in Teams today.**</span></span>
>
><span data-ttu-id="612ab-105">환자 앱 데이터는 팀을 백업 하는 Office 365 그룹의 그룹 사서함에 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="612ab-105">Patients app data is stored in the group mailbox of the Office 365 group that backs the team.</span></span> <span data-ttu-id="612ab-106">환자 앱이 종료 되 면 관련 된 모든 데이터는이 그룹에 보존 되지만 사용자 인터페이스를 통해 더 이상 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="612ab-106">When the Patients app is retired, all data associated with it will be retained in this group but can no longer be accessed through the user interface.</span></span> <span data-ttu-id="612ab-107">현재 사용자는 [목록 앱](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db)을 사용 하 여 목록을 다시 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="612ab-107">Current users can re-create their lists using the [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db).</span></span>
>
><span data-ttu-id="612ab-108">[목록 앱](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) 은 모든 팀 사용자를 위해 사전 설치 되어 있으며 모든 팀과 채널에서 탭으로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="612ab-108">The [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) is pre-installed for all Teams users and is available as a tab in every team and channel.</span></span> <span data-ttu-id="612ab-109">상태 팀은 목록을 사용 하 여 기본 제공 환자 서식 파일을 사용 하거나, 처음부터 또는 Excel로 데이터를 가져와 환자 목록을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="612ab-109">With Lists, health teams can create patient lists using the built-in Patients template, from scratch, or by importing data to Excel.</span></span> <span data-ttu-id="612ab-110">조직에서 목록 앱을 관리 하는 방법에 대해 자세히 알아보려면 [목록 앱 관리](../../manage-lists-app.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="612ab-110">To learn more about how to manage the Lists app in your organization, see [Manage the Lists app](../../manage-lists-app.md).</span></span>

[!INCLUDE [preview-feature](../../includes/preview-feature.md)]

<span data-ttu-id="612ab-111">Microsoft 팀 환자 앱을 사용 하도록 FTO r 서버를 설정 또는 재구성 하려면 앱이 액세스 해야 하는 데이터에 대 한 이해가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="612ab-111">Setting up or reconfiguring an FHIR server to work with the Microsoft Teams Patients app requires understanding what data the app needs to access.</span></span> <span data-ttu-id="612ab-112">FHIR 서버는 다음 리소스에 대해 번들을 사용 하 여 POST 요청을 지원 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="612ab-112">The FHIR server must support POST requests using bundles for the following resources:</span></span>

- [<span data-ttu-id="612ab-113">환자가</span><span class="sxs-lookup"><span data-stu-id="612ab-113">Patient</span></span>](#patient)
- [<span data-ttu-id="612ab-114">탑</span><span class="sxs-lookup"><span data-stu-id="612ab-114">Observation</span></span>](#observation)
- [<span data-ttu-id="612ab-115">조건</span><span class="sxs-lookup"><span data-stu-id="612ab-115">Condition</span></span>](#condition)
- [<span data-ttu-id="612ab-116">문제가</span><span class="sxs-lookup"><span data-stu-id="612ab-116">Encounter</span></span>](#encounter)
- [<span data-ttu-id="612ab-117">Allergy Intolerance</span><span class="sxs-lookup"><span data-stu-id="612ab-117">Allergy Intolerance</span></span>](#allergyintolerance)
- [<span data-ttu-id="612ab-118">통신이</span><span class="sxs-lookup"><span data-stu-id="612ab-118">Coverage</span></span>](#coverage)
- <span data-ttu-id="612ab-119">[투약 문](#medication-request) (DSTU2 버전의 PatientsApp에서 MedicationOrder를 대체 합니다.)</span><span class="sxs-lookup"><span data-stu-id="612ab-119">[Medication Statement](#medication-request) (replaces the MedicationOrder in the DSTU2 version of the PatientsApp)</span></span>
- <span data-ttu-id="612ab-120">위치 (이 리소스에서 필요로 하는 정보가 발생할 수 있음)</span><span class="sxs-lookup"><span data-stu-id="612ab-120">Location (the information needed from this resource can be included in Encounter)</span></span>

> [!NOTE]
> <span data-ttu-id="612ab-121">환자 리소스는 유일한 필수 리소스 (앱이 전혀 로드 되지 않는)에만 사용 됩니다. 그러나 Microsoft 팀 환자 앱을 사용 하 여 최상의 최종 사용자 환경을 제공 하기 위해 파트너는 위에서 설명한 모든 사양에 대 한 지원을 구현 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="612ab-121">The Patient resource is the only mandatory resource (without which the app will not load at all); However, it is recommended that the Partner implement support for all the above mentioned resources per specifications provided below for the best end-user experience with the Microsoft Teams Patients App.</span></span>

<span data-ttu-id="612ab-122">두 개 이상의 리소스에 대 한 Microsoft 팀 환자 앱의 쿼리는 요청에 대 한 번들 (일괄 처리)을 FTO r 서버의 URL에 게시 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="612ab-122">Queries from the Microsoft Teams Patients app for more than one resource shall post a bundle (BATCH) of requests to the FHIR server's URL.</span></span> <span data-ttu-id="612ab-123">서버는 각 요청을 처리 하 고 각 요청과 일치 하는 리소스의 번들을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="612ab-123">The server shall process each request and return a bundle of the resources matched by each request.</span></span> <span data-ttu-id="612ab-124">자세한 내용 및 예제는를 참조 하세요 [https://www.hl7.org/fhir/STU3/http.html#transaction](https://www.hl7.org/fhir/STU3/http.html#transaction) .</span><span class="sxs-lookup"><span data-stu-id="612ab-124">For more information and examples, see [https://www.hl7.org/fhir/STU3/http.html#transaction](https://www.hl7.org/fhir/STU3/http.html#transaction).</span></span>

## <a name="capability-statement"></a><span data-ttu-id="612ab-125">역량 명세서</span><span class="sxs-lookup"><span data-stu-id="612ab-125">Capability Statement</span></span>

<span data-ttu-id="612ab-126">최소 필수 필드는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="612ab-126">These are the minimum required fields:</span></span>

 - <span data-ttu-id="612ab-127">받침대</span><span class="sxs-lookup"><span data-stu-id="612ab-127">REST</span></span>

    - <span data-ttu-id="612ab-128">모드</span><span class="sxs-lookup"><span data-stu-id="612ab-128">Mode</span></span>
    - <span data-ttu-id="612ab-129">개입</span><span class="sxs-lookup"><span data-stu-id="612ab-129">Interaction</span></span>
    - <span data-ttu-id="612ab-130">자원: 종류</span><span class="sxs-lookup"><span data-stu-id="612ab-130">Resource: Type</span></span>
    - <span data-ttu-id="612ab-131">보안: [OAuth uri 용 확장](https://hl7.org/fhir/extension-oauth-uris.html)</span><span class="sxs-lookup"><span data-stu-id="612ab-131">Security: [Extension for OAuth URIs](https://hl7.org/fhir/extension-oauth-uris.html)</span></span>
    
 - <span data-ttu-id="612ab-132">Fto Rversion (코드에는 어떤 버전을 피벗할 것인지 이해 하기 위해 필요 합니다.)</span><span class="sxs-lookup"><span data-stu-id="612ab-132">FhirVersion (Our code requires this to understand which version we should pivot to.)</span></span>

<span data-ttu-id="612ab-133">[https://www.hl7.org/fhir/stu3/capabilitystatement.html](https://www.hl7.org/fhir/stu3/capabilitystatement.html)이 필드 집합에 대 한 자세한 내용은을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="612ab-133">See [https://www.hl7.org/fhir/stu3/capabilitystatement.html](https://www.hl7.org/fhir/stu3/capabilitystatement.html) for other details on this field set.</span></span>

## <a name="patient"></a><span data-ttu-id="612ab-134">환자가</span><span class="sxs-lookup"><span data-stu-id="612ab-134">Patient</span></span>

<span data-ttu-id="612ab-135">다음은 Argonaut 환자 프로필 필드의 하위 집합인 최소 필수 필드입니다.</span><span class="sxs-lookup"><span data-stu-id="612ab-135">Here are the minimum required fields, which are a subset of the Argonaut patient profile fields:</span></span>

 - <span data-ttu-id="612ab-136">Name. 지정 된</span><span class="sxs-lookup"><span data-stu-id="612ab-136">Name.Given</span></span>
 - <span data-ttu-id="612ab-137">패밀리 이름</span><span class="sxs-lookup"><span data-stu-id="612ab-137">Name.Family</span></span>
 - <span data-ttu-id="612ab-138">성별을</span><span class="sxs-lookup"><span data-stu-id="612ab-138">Gender</span></span>
 - <span data-ttu-id="612ab-139">생년월일</span><span class="sxs-lookup"><span data-stu-id="612ab-139">BirthDate</span></span>
 - <span data-ttu-id="612ab-140">MRN (Identifier)</span><span class="sxs-lookup"><span data-stu-id="612ab-140">MRN (Identifier)</span></span>

<span data-ttu-id="612ab-141">[Argonaut 필드](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html)외에도 멋진 사용자 환경을 위해 환자 앱에서는 다음 필드도 읽을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="612ab-141">In addition to the [Argonaut fields](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html), for a great user experience the Patients app can also read the following fields:</span></span>

 - <span data-ttu-id="612ab-142">이름을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="612ab-142">Name.Use</span></span>
 - <span data-ttu-id="612ab-143">Name. 접두사</span><span class="sxs-lookup"><span data-stu-id="612ab-143">Name.Prefix</span></span>
 - <span data-ttu-id="612ab-144">[GeneralPractitioner]-GeneralPractitioner 참조는 환자 리소스 (표시 필드에만 해당)에 포함 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="612ab-144">[GeneralPractitioner] - The GeneralPractitioner reference should be included in the Patient resource (display field only)</span></span>

<span data-ttu-id="612ab-145">리소스 검색에서는/Patient/_search 및 다음 매개 변수에 POST 메서드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="612ab-145">A resource search uses the POST method at /Patient/_search and the following parameters:</span></span>

 - <span data-ttu-id="612ab-146">i</span><span class="sxs-lookup"><span data-stu-id="612ab-146">id</span></span>
 - <span data-ttu-id="612ab-147">family = (가족 이름에 값이 포함 되어 있는 모든 환자 검색)</span><span class="sxs-lookup"><span data-stu-id="612ab-147">family=(searches for all patients whose family name contains the value)</span></span>
 - <span data-ttu-id="612ab-148">지정 =\<substring></span><span class="sxs-lookup"><span data-stu-id="612ab-148">given=\<substring></span></span>
 - <span data-ttu-id="612ab-149">생년월일 = (정확한 일치)</span><span class="sxs-lookup"><span data-stu-id="612ab-149">birthdate=(exact match)</span></span>
 - <span data-ttu-id="612ab-150">성별 = (관리자 성별 중 하나에 해당 하는 값)</span><span class="sxs-lookup"><span data-stu-id="612ab-150">gender=(values being one of the administrative-gender)</span></span>
 - <span data-ttu-id="612ab-151">\_count (반환 해야 하는 최대 결과 수)</span><span class="sxs-lookup"><span data-stu-id="612ab-151">\_count (maximum number of results that should be returned)</span></span> <br> <span data-ttu-id="612ab-152">응답에는 검색 결과에 따라 반환 되는 레코드의 총 개수가 포함 되어야 하며 \_ 반환 되는 레코드 수를 제한 하기 위해 PatientsApp에서 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="612ab-152">The response should contain the total count of records returned as a result of the search and \_count will be used by the PatientsApp to limit the number of records returned.</span></span>
 - <span data-ttu-id="612ab-153">identifier =\<mrn></span><span class="sxs-lookup"><span data-stu-id="612ab-153">identifier=\<mrn></span></span>

<span data-ttu-id="612ab-154">목표는 다음을 수행 하 여 환자를 검색 하 고 필터링 할 수 있다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="612ab-154">The goal is to be able to search and filter for a patient by the following:</span></span>

- <span data-ttu-id="612ab-155">ID:이는 모든 자원의 모든 리소스에 있는 자원 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="612ab-155">ID: This is the resource ID that every resource in FHIR has.</span></span>
- <span data-ttu-id="612ab-156">MRN이는 임상 직원이 알고 있는 환자에 대 한 실제 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="612ab-156">MRN: This is the actual identifier for the patient that clinical staff would know.</span></span> <span data-ttu-id="612ab-157">이 MRN는 FA r의 식별자 리소스 내에 있는 식별자 유형을 기반으로 이해 합니다.</span><span class="sxs-lookup"><span data-stu-id="612ab-157">We understand this MRN is based on the type of identifier inside the identifier resource in FHIR.</span></span>
- <span data-ttu-id="612ab-158">이름</span><span class="sxs-lookup"><span data-stu-id="612ab-158">Name</span></span>
- <span data-ttu-id="612ab-159">생년월일</span><span class="sxs-lookup"><span data-stu-id="612ab-159">Birthdate</span></span>

<span data-ttu-id="612ab-160">통화에 대 한 다음 예제를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="612ab-160">See the following example of the call:</span></span>

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

<span data-ttu-id="612ab-161">[https://hl7.org/fhir/stu3/patient.html](https://hl7.org/fhir/stu3/patient.html)이 필드 집합에 대 한 자세한 내용은을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="612ab-161">See [https://hl7.org/fhir/stu3/patient.html](https://hl7.org/fhir/stu3/patient.html) for other details on this field set.</span></span>

## <a name="observation"></a><span data-ttu-id="612ab-162">탑</span><span class="sxs-lookup"><span data-stu-id="612ab-162">Observation</span></span>

<span data-ttu-id="612ab-163">[Argonaut Vital-Signs 프로필](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-vitalsigns.html)의 하위 집합인 최소 필수 필드입니다.</span><span class="sxs-lookup"><span data-stu-id="612ab-163">These are the minimum required fields, which are a subset of the [Argonaut Vital-Signs profile](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-vitalsigns.html).</span></span>

 - <span data-ttu-id="612ab-164">유효 (날짜 시간 또는 기간)</span><span class="sxs-lookup"><span data-stu-id="612ab-164">Effective (date time or period)</span></span>
 - <span data-ttu-id="612ab-165">코드. 코딩 코드</span><span class="sxs-lookup"><span data-stu-id="612ab-165">Code.Coding.Code</span></span>
 - <span data-ttu-id="612ab-166">값</span><span class="sxs-lookup"><span data-stu-id="612ab-166">ValueQuantity.Value</span></span>

<span data-ttu-id="612ab-167">Argonaut 필드 외에도 멋진 사용자 환경을 위해 환자 앱에서는 다음 필드도 읽을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="612ab-167">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following fields:</span></span>

 - <span data-ttu-id="612ab-168">코드. 표시</span><span class="sxs-lookup"><span data-stu-id="612ab-168">Code.Coding.Display</span></span>
 - <span data-ttu-id="612ab-169">단위</span><span class="sxs-lookup"><span data-stu-id="612ab-169">ValueQuantity.Unit</span></span>

<span data-ttu-id="612ab-170">리소스 검색에서 GET 메서드 및 다음 매개 변수를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="612ab-170">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="612ab-171">환자 =\<patient id></span><span class="sxs-lookup"><span data-stu-id="612ab-171">patient=\<patient id></span></span>
 - <span data-ttu-id="612ab-172">_sort =-날짜</span><span class="sxs-lookup"><span data-stu-id="612ab-172">_sort=-date</span></span>
 - <span data-ttu-id="612ab-173">범주 ("category = 필수-서명")에서 중요 한 서명 목록을 검색 하는 방법을 쿼리 합니다.</span><span class="sxs-lookup"><span data-stu-id="612ab-173">category (we will query for "category=vital-signs") to retrieve the list of vital signs.</span></span>

<span data-ttu-id="612ab-174">통화에 대 한 다음 예제를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="612ab-174">Refer to this example of the call:</span></span>

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

<span data-ttu-id="612ab-175">[https://www.hl7.org/fhir/stu3/observation.html](https://www.hl7.org/fhir/stu3/observation.html)이 필드 집합에 대 한 자세한 내용은을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="612ab-175">See [https://www.hl7.org/fhir/stu3/observation.html](https://www.hl7.org/fhir/stu3/observation.html) for other details on this field set.</span></span>

## <a name="condition"></a><span data-ttu-id="612ab-176">조건</span><span class="sxs-lookup"><span data-stu-id="612ab-176">Condition</span></span>

<span data-ttu-id="612ab-177">다음은 [Argonaut condition 프로필](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html)의 하위 집합인 필요한 최소 필드입니다.</span><span class="sxs-lookup"><span data-stu-id="612ab-177">Here's the minimum required fields, which are a subset of the [Argonaut condition profile](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html).</span></span>

 - <span data-ttu-id="612ab-178">코드. 코딩 [0]. 표시</span><span class="sxs-lookup"><span data-stu-id="612ab-178">Code.Coding[0].Display</span></span>

<span data-ttu-id="612ab-179">Argonaut 필드 외에도 멋진 사용자 환경을 위해 환자 앱에서는 다음 필드도 읽을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="612ab-179">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following fields:</span></span>

 - <span data-ttu-id="612ab-180">AssertedDate</span><span class="sxs-lookup"><span data-stu-id="612ab-180">AssertedDate</span></span>
 - <span data-ttu-id="612ab-181">문제의</span><span class="sxs-lookup"><span data-stu-id="612ab-181">Severity</span></span>

<span data-ttu-id="612ab-182">리소스 검색에서 GET 메서드 및 다음 매개 변수를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="612ab-182">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="612ab-183">환자 =\<patient id></span><span class="sxs-lookup"><span data-stu-id="612ab-183">patient=\<patient id></span></span>
 - <span data-ttu-id="612ab-184">_count =\<max results></span><span class="sxs-lookup"><span data-stu-id="612ab-184">_count=\<max results></span></span>

<span data-ttu-id="612ab-185">이 통화의 다음 예제를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="612ab-185">See the following example of this call:</span></span>

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

<span data-ttu-id="612ab-186">[https://hl7.org/fhir/stu3/condition.html](https://hl7.org/fhir/stu3/condition.html)이 필드 집합에 대 한 자세한 내용은을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="612ab-186">See [https://hl7.org/fhir/stu3/condition.html](https://hl7.org/fhir/stu3/condition.html) for other details on this field set.</span></span>

## <a name="encounter"></a><span data-ttu-id="612ab-187">문제가</span><span class="sxs-lookup"><span data-stu-id="612ab-187">Encounter</span></span>

<span data-ttu-id="612ab-188">[미국 핵심 발생 프로필](https://hl7.org/fhir/us/core/2018Jan/StructureDefinition-us-core-encounter.html) 의 하위 집합인 최소 필수 필드는 "필드에" 필드가 있어야 합니다. "</span><span class="sxs-lookup"><span data-stu-id="612ab-188">These are the minimum required fields, which are a subset of the [US Core Encounter profile](https://hl7.org/fhir/us/core/2018Jan/StructureDefinition-us-core-encounter.html) "must have" fields).</span></span>

 - <span data-ttu-id="612ab-189">상태</span><span class="sxs-lookup"><span data-stu-id="612ab-189">Status</span></span>
 - <span data-ttu-id="612ab-190">[0]을 입력 합니다. 코딩 [0]. 표시</span><span class="sxs-lookup"><span data-stu-id="612ab-190">Type[0].Coding[0].Display</span></span>

<span data-ttu-id="612ab-191">또한 미국 Core 발생 프로필의 "지원 해야 하는" 필드에는 다음과 같은 필드가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="612ab-191">In addition, the following fields from US Core Encounter profile's "must support" fields:</span></span>

 - <span data-ttu-id="612ab-192">기간. 시작</span><span class="sxs-lookup"><span data-stu-id="612ab-192">Period.Start</span></span>
 - <span data-ttu-id="612ab-193">위치 [0]. 위치. 표시</span><span class="sxs-lookup"><span data-stu-id="612ab-193">Location[0].Location.Display</span></span>

<span data-ttu-id="612ab-194">리소스 검색에서 GET 메서드 및 다음 매개 변수를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="612ab-194">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="612ab-195">환자 =\<patient id></span><span class="sxs-lookup"><span data-stu-id="612ab-195">patient=\<patient id></span></span>
 - <span data-ttu-id="612ab-196">_sort: desc =\<field ex. date></span><span class="sxs-lookup"><span data-stu-id="612ab-196">_sort:desc=\<field ex. date></span></span>
 - <span data-ttu-id="612ab-197">_count =\<max results></span><span class="sxs-lookup"><span data-stu-id="612ab-197">_count=\<max results></span></span>

<span data-ttu-id="612ab-198">목표는 환자 마지막으로 알려진 위치를 검색할 수 있다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="612ab-198">The goal is to be able to retrieve the patient's last known location.</span></span> <span data-ttu-id="612ab-199">각 발생은 위치 리소스를 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="612ab-199">Each encounter references a location resource.</span></span> <span data-ttu-id="612ab-200">또한 참조에는 위치의 표시 필드도 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="612ab-200">The reference shall also include the location's display field.</span></span>

<span data-ttu-id="612ab-201">[https://hl7.org/fhir/stu3/encounter.html](https://hl7.org/fhir/stu3/encounter.html)이 필드 집합에 대 한 자세한 내용은을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="612ab-201">See [https://hl7.org/fhir/stu3/encounter.html](https://hl7.org/fhir/stu3/encounter.html) for other details on this field set.</span></span>

## <a name="allergyintolerance"></a><span data-ttu-id="612ab-202">AllergyIntolerance</span><span class="sxs-lookup"><span data-stu-id="612ab-202">AllergyIntolerance</span></span>

<span data-ttu-id="612ab-203">다음은 [Argonaut AllergyIntolerance](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-allergyintolerance.html) 프로필의 하위 집합인 최소 필수 필드입니다.</span><span class="sxs-lookup"><span data-stu-id="612ab-203">These are the minimum required fields, which are a subset of the [Argonaut AllergyIntolerance](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-allergyintolerance.html) profile:</span></span>

 - <span data-ttu-id="612ab-204">코드. 텍스트</span><span class="sxs-lookup"><span data-stu-id="612ab-204">Code.Text</span></span>
 - <span data-ttu-id="612ab-205">코드. 코딩 [0]. 표시</span><span class="sxs-lookup"><span data-stu-id="612ab-205">Code.Coding[0].Display</span></span>
 - <span data-ttu-id="612ab-206">ClinicalStatus/VerificationStatus (두 가지 모두 읽었습니다)</span><span class="sxs-lookup"><span data-stu-id="612ab-206">ClinicalStatus/VerificationStatus (we read both)</span></span>

<span data-ttu-id="612ab-207">Argonaut 필드 외에도 멋진 사용자 환경을 위해 환자 앱에서 다음 필드도 읽을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="612ab-207">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following field:</span></span>

 - <span data-ttu-id="612ab-208">AssertedDate</span><span class="sxs-lookup"><span data-stu-id="612ab-208">AssertedDate</span></span>
 - <span data-ttu-id="612ab-209">참고. 텍스트</span><span class="sxs-lookup"><span data-stu-id="612ab-209">Note.Text</span></span>
 - <span data-ttu-id="612ab-210">반응은</span><span class="sxs-lookup"><span data-stu-id="612ab-210">Reaction</span></span>
    - <span data-ttu-id="612ab-211">물질 (1 개의 코딩 요소)</span><span class="sxs-lookup"><span data-stu-id="612ab-211">Substance (one coding element)</span></span>
    - <span data-ttu-id="612ab-212">Manifestation (1 코딩 요소)</span><span class="sxs-lookup"><span data-stu-id="612ab-212">Manifestation (one coding element)</span></span>

<span data-ttu-id="612ab-213">리소스 검색에서 GET 메서드 및 다음 매개 변수를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="612ab-213">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="612ab-214">환자 =  \<patient id></span><span class="sxs-lookup"><span data-stu-id="612ab-214">Patient =  \<patient id></span></span>

<span data-ttu-id="612ab-215">통화에 대 한 다음 예제를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="612ab-215">See the following example of the call:</span></span> 

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

<span data-ttu-id="612ab-216">[https://hl7.org/fhir/stu3/allergyintolerance.html](https://hl7.org/fhir/stu3/allergyintolerance.html)이 필드 집합에 대 한 자세한 내용은을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="612ab-216">See [https://hl7.org/fhir/stu3/allergyintolerance.html](https://hl7.org/fhir/stu3/allergyintolerance.html) for other details on this field set.</span></span>

## <a name="medication-request"></a><span data-ttu-id="612ab-217">투약 요청</span><span class="sxs-lookup"><span data-stu-id="612ab-217">Medication Request</span></span>

<span data-ttu-id="612ab-218">[미국 Core 투약 요청 프로필](http://www.hl7.org/fhir/us/core/StructureDefinition-us-core-medicationrequest.html)의 하위 집합인 최소 필수 필드는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="612ab-218">These are the minimum required fields, which are a subset of the [US Core Medication Request profile](http://www.hl7.org/fhir/us/core/StructureDefinition-us-core-medicationrequest.html):</span></span>

 - <span data-ttu-id="612ab-219">투약. 표시 (참조 하는 경우)</span><span class="sxs-lookup"><span data-stu-id="612ab-219">Medication.Display (if Reference)</span></span>
 - <span data-ttu-id="612ab-220">투약 (if CodableConcept)</span><span class="sxs-lookup"><span data-stu-id="612ab-220">Medication.Text (if CodableConcept)</span></span>
 - <span data-ttu-id="612ab-221">기관 Edon</span><span class="sxs-lookup"><span data-stu-id="612ab-221">AuthoredOn</span></span>
 - <span data-ttu-id="612ab-222">요청자. 에이전트 디스플레이</span><span class="sxs-lookup"><span data-stu-id="612ab-222">Requester.Agent.Display</span></span>

<span data-ttu-id="612ab-223">멋진 사용자 환경을 위해 미국 Core 필드 외에도 환자 앱에서 다음 필드를 읽을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="612ab-223">In addition to the US Core fields, for a great user experience the Patients app can also read the following fields:</span></span>

 - <span data-ttu-id="612ab-224">DosageInstruction[..]. 본문</span><span class="sxs-lookup"><span data-stu-id="612ab-224">DosageInstruction[..].Text</span></span>
 - <span data-ttu-id="612ab-225">본문</span><span class="sxs-lookup"><span data-stu-id="612ab-225">Text</span></span>

<span data-ttu-id="612ab-226">리소스 검색에서 GET 메서드 및 다음 매개 변수를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="612ab-226">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="612ab-227">환자 =\<patient id></span><span class="sxs-lookup"><span data-stu-id="612ab-227">patient=\<patient id></span></span>
 - <span data-ttu-id="612ab-228">_count =\<max results></span><span class="sxs-lookup"><span data-stu-id="612ab-228">_count=\<max results></span></span>

<span data-ttu-id="612ab-229">[https://www.hl7.org/fhir/medicationrequest.html](https://www.hl7.org/fhir/medicationrequest.html)이 필드 집합에 대 한 자세한 내용은을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="612ab-229">See [https://www.hl7.org/fhir/medicationrequest.html](https://www.hl7.org/fhir/medicationrequest.html) for other details on this field set.</span></span>

## <a name="coverage"></a><span data-ttu-id="612ab-230">통신이</span><span class="sxs-lookup"><span data-stu-id="612ab-230">Coverage</span></span>

<span data-ttu-id="612ab-231">미국 Core 또는 Argonaut 프로필에서 다루지 않는 최소 필수 필드는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="612ab-231">These are the minimum required fields, not covered by either US Core or Argonaut profiles:</span></span>

 - <span data-ttu-id="612ab-232">그룹화에서 하나 이상의 요소를 사용 하 여</span><span class="sxs-lookup"><span data-stu-id="612ab-232">Grouping, at least one element with</span></span>
    - <span data-ttu-id="612ab-233">GroupDisplay</span><span class="sxs-lookup"><span data-stu-id="612ab-233">GroupDisplay</span></span>
    - <span data-ttu-id="612ab-234">계획 표시</span><span class="sxs-lookup"><span data-stu-id="612ab-234">PlanDisplay</span></span>
 - <span data-ttu-id="612ab-235">안에</span><span class="sxs-lookup"><span data-stu-id="612ab-235">Period</span></span>
 - <span data-ttu-id="612ab-236">SubscriberId</span><span class="sxs-lookup"><span data-stu-id="612ab-236">SubscriberId</span></span>

<span data-ttu-id="612ab-237">리소스 검색에서 GET 메서드 및 다음 매개 변수를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="612ab-237">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="612ab-238">환자 = \<patient id></span><span class="sxs-lookup"><span data-stu-id="612ab-238">Patient = \<patient id></span></span>

<span data-ttu-id="612ab-239">[https://hl7.org/fhir/stu3/coverage.html](https://www.hl7.org/fhir/medicationrequest.html)이 필드 집합에 대 한 자세한 내용은을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="612ab-239">See [https://hl7.org/fhir/stu3/coverage.html](https://www.hl7.org/fhir/medicationrequest.html) for other details on this field set.</span></span>
