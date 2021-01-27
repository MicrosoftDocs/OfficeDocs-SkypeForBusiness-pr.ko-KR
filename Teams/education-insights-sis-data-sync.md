---
title: SIS(학생 정보 시스템) 데이터와 Education Insights 동기화
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: karsmith
description: SIS(학생 정보 시스템) 데이터를 Microsoft Teams의 Education Insights 동기화
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7570368a6b9bd889bc5ed632cd1d057d70ae791a
ms.sourcegitcommit: 086d27c9381fc1f1c6523d4c48dea275dea917b7
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/26/2021
ms.locfileid: "49986431"
---
# <a name="sync-student-information-system-sis-data-with-education-insights"></a><span data-ttu-id="9a129-103">SIS(학생 정보 시스템) 데이터와 Education Insights 동기화</span><span class="sxs-lookup"><span data-stu-id="9a129-103">Sync Student Information System (SIS) data with Education Insights</span></span>
<span data-ttu-id="9a129-104">더 많은 데이터가 [Education Insights](class-insights.md)에 제공될수록 교육자는 학생을 더 잘 지원할 수 있으며 교육 리더는 교육자를 더 잘 지원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9a129-104">The more data is fed into [Education Insights](class-insights.md), the better educators can support their students, and education leaders can support the educators.</span></span>

<span data-ttu-id="9a129-105">조직 수준의 Insights를 제공하려면 Insights가 교육 시스템의 계층 구조가 올바르게 매핑되도록 [SDS(학교 데이터 동기화)](https://docs.microsoft.com/SchoolDataSync)를 사용하여 SIS(학생 정보 시스템)에 연결해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a129-105">To provide organization-level Insights, we must use [School Data Sync (SDS)](https://docs.microsoft.com/SchoolDataSync) to connect to the Student Information System (SIS) so that Insights has the hierarchical structure of the educational system mapped correctly.</span></span> 

<span data-ttu-id="9a129-106">Teams의 수업 구조와 권한을 사용하기 때문에 수업 교육자로서 수업 수준 Insights를 볼 필요가 *없습니다*.</span><span class="sxs-lookup"><span data-stu-id="9a129-106">Viewing class-level Insights as the class educator *does not* require this because we use Teams' class structure and permissions.</span></span>

## <a name="plan-your-sis-integration"></a><span data-ttu-id="9a129-107">SIS 통합 계획</span><span class="sxs-lookup"><span data-stu-id="9a129-107">Plan your SIS integration</span></span>
<span data-ttu-id="9a129-108">SIS 데이터는 교육 시스템의 계층 구조와 사용자가 어디에 할당되었는지 지도를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="9a129-108">The SIS data provides the hierarchical structure of the educational system and maps which user is assigned where.</span></span>

<span data-ttu-id="9a129-109">Insights는 [SDS V2 파일 형식](https://docs.microsoft.com/schooldatasync/sds-v2-csv-file-format)을 사용할 때 사용할 때 가장 잘 작동하지만, 기능이 *제한된* [SDS V1 파일 형식](https://docs.microsoft.com/schooldatasync/school-data-sync-format-csv-files-for-sds)도 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="9a129-109">Insights works best when using [SDS V2 file format](https://docs.microsoft.com/schooldatasync/sds-v2-csv-file-format) but also supports [SDS V1 file format](https://docs.microsoft.com/schooldatasync/school-data-sync-format-csv-files-for-sds) with *limited* functionality.</span></span>

### <a name="differences-between-sds-v1-and-v2-file-formats"></a><span data-ttu-id="9a129-110">SDS V1과 V2 파일 형식의 차이점</span><span class="sxs-lookup"><span data-stu-id="9a129-110">Differences between SDS V1 and V2 file formats</span></span>

| <span data-ttu-id="9a129-111">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="9a129-111">Data type</span></span> |   <span data-ttu-id="9a129-112">V1</span><span class="sxs-lookup"><span data-stu-id="9a129-112">V1</span></span> | <span data-ttu-id="9a129-113">V2(권장)</span><span class="sxs-lookup"><span data-stu-id="9a129-113">V2 (recommended)</span></span> |
|:--- |:--- |:--- |
| <span data-ttu-id="9a129-114">**사용자**</span><span class="sxs-lookup"><span data-stu-id="9a129-114">**Users**</span></span> | <span data-ttu-id="9a129-115">V1 형식에는 **교육자만** 포함되어 있으므로 교육 리더에 대한 조직 수준 권한을 설정하려면 교육 리더를 검색하고 각각의 권한을 수동으로 정의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a129-115">The V1 format contains **only educators**, so to set org-level permissions for your education leaders, you need to search for them and define each one's permission manually.</span></span> | <span data-ttu-id="9a129-116">V2 형식에는 역할 기반 권한을 할당할 수 있도록 **모든 역할** 이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9a129-116">The V2 format contains **all the roles** so that you can assign role-based permissions.</span></span> |
| <span data-ttu-id="9a129-117">**조직**</span><span class="sxs-lookup"><span data-stu-id="9a129-117">**Orgs**</span></span> | <span data-ttu-id="9a129-118">V1 형식에는 **학교만** 포함되어 있으므로 한 집계 수준(모든 학교)만 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="9a129-118">The V1 format contains **only schools**, so you see only one aggregation level (all your schools).</span></span> <span data-ttu-id="9a129-119">플랫 목록을 사용하여 특정 학교를 확대할 수 있지만, 이 목록에는 많은 학교나 비교하기 어려운 여러 유형의 학교(예: 초/중/고/과학/예술 학교)가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9a129-119">You can zoom in to a specific school using a flat list, but this list may have a large number of schools or contain different types of schools that are hard to compare (such as primary to secondary school or science to art school).</span></span><br/><br/> <span data-ttu-id="9a129-120">계층 구조가 있는 경우 과학 또는 예술 부서와 같이 의미 있는 수준을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9a129-120">When there is a hierarchy in place, you can create levels that make sense, such as a science or art department.</span></span>| <span data-ttu-id="9a129-121">V2 형식은 대학, 학부, 캠퍼스, 지역, 프로그램 등 **학군 또는 기관의 전체 계층 구조에 대한 전체 계층** 을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="9a129-121">The V2 format contains **the full hierarchy of your district or institution**, including universities, colleges, faculties, campuses, regions, programs and so on.</span></span><br/><br/> <span data-ttu-id="9a129-122">계층 구조를 사용하여 계층 구조의 수준별로 관련 집계를 보고, 각 수준에서 조직 단위를 빠르게 비교하고, 특정 수준에 대한 권한을 할당하고, 조직 수준별로 목표를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9a129-122">With a hierarchy, you can see relevant aggregation by each level of the hierarchy, quickly compare between organizational units at each level, assign permission to specific levels, set goals by org level, and so on.</span></span>|

### <a name="type-of-data-required"></a><span data-ttu-id="9a129-123">필요한 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="9a129-123">Type of data required</span></span>
<span data-ttu-id="9a129-124">다음 표에서는 Insights를 최대한 활용하는 데 필요한 데이터 형식을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="9a129-124">The following table provides the type of data required to get the best out of Insights.</span></span>

| <span data-ttu-id="9a129-125">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="9a129-125">Data type</span></span> | <span data-ttu-id="9a129-126">제공해야 할 항목의 예</span><span class="sxs-lookup"><span data-stu-id="9a129-126">Examples for what you need to provide</span></span>|<span data-ttu-id="9a129-127">중요한 이유는 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="9a129-127">Why it's important?</span></span>|
|:--- |:--- |:--- |
| <span data-ttu-id="9a129-128">**사용자**</span><span class="sxs-lookup"><span data-stu-id="9a129-128">**Users**</span></span> |   <span data-ttu-id="9a129-129">역할(예: 학생)</span><span class="sxs-lookup"><span data-stu-id="9a129-129">Role (such as student)</span></span><br/> <span data-ttu-id="9a129-130">학년(예: 10)</span><span class="sxs-lookup"><span data-stu-id="9a129-130">Grade/Year level (such as 10)</span></span><br/> <span data-ttu-id="9a129-131">조직(이름)</span><span class="sxs-lookup"><span data-stu-id="9a129-131">Org (name)</span></span> | <span data-ttu-id="9a129-132">각 사용자에게 역할, 학년 및 조직을 올바르게 할당하면 요약 및 집계가 올바른지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9a129-132">When we correctly assign each person to their role, grade/year level, and organization, we can ensure that the summaries and aggregations are correct.</span></span>|
| <span data-ttu-id="9a129-133">**조직**</span><span class="sxs-lookup"><span data-stu-id="9a129-133">**Orgs**</span></span> | <span data-ttu-id="9a129-134">조직 유형(예: 대학)</span><span class="sxs-lookup"><span data-stu-id="9a129-134">Org type (such as college)</span></span> |   <span data-ttu-id="9a129-135">여기서는 계층 구조가 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="9a129-135">The hierarchy here is important.</span></span> <span data-ttu-id="9a129-136">예를 들어 학교는 학군에 속할 수 있으며 학군은 주에 속할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9a129-136">For example, schools may belong to a district, and that district may belong to a state.</span></span><br/> <span data-ttu-id="9a129-137">학군 교육 리더가 데이터를 볼 수 있는 경우 해당 학군의 학교 데이터에만 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="9a129-137">When a district education leader is permitted to see data, it's only for the schools in that district.</span></span>|
| <span data-ttu-id="9a129-138">**수업**</span><span class="sxs-lookup"><span data-stu-id="9a129-138">**Classes**</span></span> | <span data-ttu-id="9a129-139">제목(예: 컴퓨터 과학 101)</span><span class="sxs-lookup"><span data-stu-id="9a129-139">Title (such as Computer science 101)</span></span> | <span data-ttu-id="9a129-140">여기에서는 조직에서 진행하는 수업을 자세히 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="9a129-140">This details which classes are held in the organization.</span></span> <span data-ttu-id="9a129-141">올바른 수업에 학생을 할당할 수 있도록 올바르게 매핑해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a129-141">This must be correctly mapped so that we can assign the student to the correct class.</span></span> |
| <span data-ttu-id="9a129-142">**등록**</span><span class="sxs-lookup"><span data-stu-id="9a129-142">**Enrollment**</span></span> | <span data-ttu-id="9a129-143">역할(예: 학생)</span><span class="sxs-lookup"><span data-stu-id="9a129-143">Role (such as student)</span></span> | <span data-ttu-id="9a129-144">등록은 학생과 교육자용으로, 등록된 수업을 알 수 있게 해줍니다.</span><span class="sxs-lookup"><span data-stu-id="9a129-144">This is for students and educators and enables us to know in which class they are registered.</span></span> |

> [!NOTE]
> <span data-ttu-id="9a129-145">배포 프로세스 동안 Teams에서 사용자 및 수업을 프로비전하는 데 SDS를 사용할지 아니면 데이터를 Insights에 사용할지 결정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9a129-145">During the deployment process, you can decide if you want to use SDS for provisioning users and classes in Teams or to use it only to provide data to Insights.</span></span>

## <a name="best-practices"></a><span data-ttu-id="9a129-146">모범 사례</span><span class="sxs-lookup"><span data-stu-id="9a129-146">Best practices</span></span>
<span data-ttu-id="9a129-147">계층 구조 및 계층 구조 내에서 모든 사람이 속한 위치를 정확하게 매핑하면 Insights가 다양한 교육 리더 유형에 대해 정확한 데이터와 더 정확하고 관련 있는 정보를 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9a129-147">The accurate mapping of the hierarchy and where everyone belongs within that hierarchy enables Insights to provide accurate data and more precise and relevant insights for the different types of education leaders.</span></span>

<span data-ttu-id="9a129-148">여기에 더 자세한 정보를 제공할수록 보고서와 스포트라이트가 더 좋아지고 관련성이 더 높아집니다.</span><span class="sxs-lookup"><span data-stu-id="9a129-148">The more detail you provide here, the better and more relevant the reports and spotlights will be.</span></span>
<span data-ttu-id="9a129-149">다음은 사용자가 Insights를 가장 잘 활용할 수 있도록 SDS의 원활한 배포를 보장하는 몇 가지 모범 사례입니다.</span><span class="sxs-lookup"><span data-stu-id="9a129-149">Here are some best practices based to ensure the smooth deployment of SDS so that your users can make the most out of Insights.</span></span>

### <a name="users"></a><span data-ttu-id="9a129-150">사용자</span><span class="sxs-lookup"><span data-stu-id="9a129-150">Users</span></span>
*   <span data-ttu-id="9a129-151">제공하고 동기화 한 파일에 *모든 사용자* 가 나열되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="9a129-151">Make sure *all users* are listed in the files you provide and synced.</span></span> <span data-ttu-id="9a129-152">여기에는 자신이 포함된 조직 단위의 데이터를 봐야 하는 모든 학생과 교직원이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="9a129-152">This includes all students and staff that need to see data for the organizational units they cover.</span></span>

    <span data-ttu-id="9a129-153">현재 SIS에 교육자만 나열되어 있는 경우 파일을 SIS에 업로드하고 데이터를 동기화하기 전에 다른 사용자를 수동으로 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="9a129-153">If you currently only have educators listed in the SIS, add the other users manually before uploading the files to SIS and syncing the data.</span></span>

    <span data-ttu-id="9a129-154">일부 학생이 누락된 경우 Insights에서 수집한 통계는 등록된 학생들에게서만 온 것이며, 이 경우 데이터와 결론에 오해의 소지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9a129-154">If some students are missing, the stats gathered by Insights is only from the registered students, and that will make the data and conclusions misleading.</span></span>
    
*   <span data-ttu-id="9a129-155">*각 사용자의 성과 이름을 제공* 해야 합니다. </span><span class="sxs-lookup"><span data-stu-id="9a129-155">Make sure to *provide the first and last name of each user*.</span></span> <span data-ttu-id="9a129-156">제공하지 않으면 해당 학생은 전자 메일 주소로 참조되며, 이는 보고서 및 스포트라이트(학생 활동 또는 성과에 대한 Insights가 있는 카드)에서 덜 긍정적인 환경을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="9a129-156">If not, they are referenced by their email address, and this provides a less than positive experience in the reports and spotlights (cards with Insights on student activity or performance).</span></span>

*   <span data-ttu-id="9a129-157">*학년은 2자리 숫자로 입력해야 합니다*(예: 7학년에 대해 07).</span><span class="sxs-lookup"><span data-stu-id="9a129-157">The *grade/year level must be input as 2 digits* (for example, 07 for Year 7).</span></span> <span data-ttu-id="9a129-158">[매핑 목록](https://docs.microsoft.com/schooldatasync/sds-v2-csv-file-format#enumerated-values-enum-supported)을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="9a129-158">Check out the [mapping list](https://docs.microsoft.com/schooldatasync/sds-v2-csv-file-format#enumerated-values-enum-supported).</span></span> 

*   <span data-ttu-id="9a129-159">학년이 데이터를 필터링할 수 있도록 *모든 학생에게 학년을 추가* 하는 것이 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="9a129-159">It's important to *add the year/grade level to all students* so that a grade/year level can filter the data.</span></span>    

*   <span data-ttu-id="9a129-160">*각 사용자를 관련 조직 단위* 에 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a129-160">Make sure to *assign each user to their relevant organizational unit*.</span></span> <span data-ttu-id="9a129-161">이 방법으로 각 단위의 집계 데이터를 기반으로 하여 잘못된 데이터가 스포트라이트에 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9a129-161">In this way, we won't show misleading data in our spotlights based on aggregated data for each unit.</span></span>

    *   <span data-ttu-id="9a129-162">학생은 둘 이상의 조직과 연결될 수 있습니다(예: 특수 프로그램 또는 두 개의 학부에 등록된 학생).</span><span class="sxs-lookup"><span data-stu-id="9a129-162">A student can be associated with more than one org unit, for example, students who are registered in a special program or two faculties.</span></span> <span data-ttu-id="9a129-163">이 경우 해당 학생의 사용자 파일에 조직별로 하나씩 두 줄을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="9a129-163">In such a case, provide two lines in the users file for that student – one for each organization.</span></span>
    
    *   <span data-ttu-id="9a129-164">직원의 조직 단위를 기반으로 관련 권한을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9a129-164">Based on the org unit for staff, you will be able to define the relevant permissions.</span></span> <span data-ttu-id="9a129-165">올바른 단위 수준과 연결되어 있는지 확인하여 필요한 사용 권한을 받을 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a129-165">Make sure they are associated with the correct unit level, so they receive the permissions they need.</span></span> <span data-ttu-id="9a129-166">예를 들어, 4개의 학교에 배정된 상담사는 4개 학교의 모든 수업을 봐야 합니다. 교장은 자신의 학교의 모든 수업을 봐야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a129-166">For example, a counselor assigned to four schools needs to see all the classes in these schools; a principal needs to see all the classes in their school.</span></span> 
    
*   <span data-ttu-id="9a129-167">역할은 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="9a129-167">The role is vital.</span></span> <span data-ttu-id="9a129-168">이 목록이 닫힌 목록이지만 [목록](https://docs.microsoft.com/schooldatasync/sds-v2-csv-file-format#enumerated-values-enum-supported)의 역할을 업로드한 각 사용자의 실제 역할과 일치시키세요.</span><span class="sxs-lookup"><span data-stu-id="9a129-168">Although this is a closed list, try to match the role from [the list](https://docs.microsoft.com/schooldatasync/sds-v2-csv-file-format#enumerated-values-enum-supported) to the real role of each user you upload.</span></span> <span data-ttu-id="9a129-169">이 방법으로 역할 기반 권한을 그에 따라 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9a129-169">In this way, you can assign role-based permissions accordingly.</span></span> <span data-ttu-id="9a129-170">예를 들어 모든 교장이 학교의 수업을 볼 수 있거나 모든 교수가 교직원을 볼 수 있는 권한을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="9a129-170">For example, provide permissions for all principals to see the classes in their school, or for all professors to see their faculty.</span></span> 

### <a name="organizations"></a><span data-ttu-id="9a129-171">조직</span><span class="sxs-lookup"><span data-stu-id="9a129-171">Organizations</span></span>

* <span data-ttu-id="9a129-172">*조직의 실제 계층 구조가 반영* 되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="9a129-172">Make sure to *reflect the real hierarchy of your organization*.</span></span> <span data-ttu-id="9a129-173">이 작업은 수동으로 파일을 추가하여 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9a129-173">This can be achieved by manually adding the file.</span></span> <span data-ttu-id="9a129-174">경우에 따라 이 계층 구조는 SIS에 반영되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9a129-174">In some cases, this hierarchy is not reflected in the SIS.</span></span> <span data-ttu-id="9a129-175">계층 구조의 수준별 관련 집계를 보고, 특정 수준에 권한을 할당하고, 목표를 조직 수준별로 설정하는 등의 작업이 필요한 경우도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9a129-175">Still, it may be necessary here to see the relevant aggregation by each level of the hierarchy, assign permission to specific levels, set goals by org level, and so on.</span></span> 

* <span data-ttu-id="9a129-176">학생 데이터를 집계하기 위해 *조직 트리 아래의 모든 조직 단위에 학생 또는 수업* 이 포함되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="9a129-176">Ensure that *all org units down the org tree include students or classes* to aggregate student data for them.</span></span> <span data-ttu-id="9a129-177">학생은 트리의 최하위 가지에 있는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="9a129-177">We recommend that students are on the lowest branch of the tree.</span></span>

> [!NOTE]
> <span data-ttu-id="9a129-178">SDS 배포에 대한 자세한 내용은 [SDS 계획](https://docs.microsoft.com/schooldatasync/planning-school-data-sync)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9a129-178">For more details about SDS deployment, visit [Planning SDS](https://docs.microsoft.com/schooldatasync/planning-school-data-sync).</span></span>

## <a name="integrate-sis-using-sds"></a><span data-ttu-id="9a129-179">SDS를 사용하여 SIS 통합</span><span class="sxs-lookup"><span data-stu-id="9a129-179">Integrate SIS using SDS</span></span>

<span data-ttu-id="9a129-180">SDS(학교 데이터 동기화)는 교육용 Office 365와 함께 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="9a129-180">School Data Sync (SDS) is provided with Office 365 for Education.</span></span> <span data-ttu-id="9a129-181">SDS는 교육 기관의 SIS(학생 정보 시스템)에서 데이터를 읽고 이를 Teams와 통합하여 온라인 교실과 사용자를 자동으로 만들 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a129-181">SDS reads the data from an educational institution's Student Information System (SIS) and integrates it with Teams to enable the automatic creation of online classrooms and users.</span></span>

<span data-ttu-id="9a129-182">또한, SIS 데이터를 Insights와 동기화합니다.</span><span class="sxs-lookup"><span data-stu-id="9a129-182">It also synchronizes the SIS data with Insights.</span></span>

### <a name="sync-with-insights"></a><span data-ttu-id="9a129-183">Insights와 동기화</span><span class="sxs-lookup"><span data-stu-id="9a129-183">Sync with Insights</span></span>

<span data-ttu-id="9a129-184">먼저, 동기화 프로세스를 시작하려면 Insights 토글을 켜야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a129-184">First, you need to turn the Insights toggle on to start the sync process.</span></span>

* <span data-ttu-id="9a129-185">[**SDS 포털**](https://sds.microsoft.com)에서 **설정** 으로 이동하고, **Insights용 데이터 수집** 까지 스크롤하여 내리고, 사용하도록 설정되어 있는지 확인합니다(기본적으로 *설정* 되어 있음).</span><span class="sxs-lookup"><span data-stu-id="9a129-185">On the [**SDS portal**](https://sds.microsoft.com), go to **Settings**, scroll down to **Collect data for Insights** and check that it's enabled (it's turned *on* by default).</span></span>

* <span data-ttu-id="9a129-186">다음 스위치인 **SDS(미리 보기)에서 조직 데이터 동기화** 까지 아래로 스크롤하고 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="9a129-186">Scroll down to the next switch, **Sync organizational data from SDS (preview)**, and turn on.</span></span>

<span data-ttu-id="9a129-187">설정 페이지에서 *SDS(미리 보기)에서 조직 데이터 동기화* 옵션이 없는 경우 [등록 페이지](https://aka.ms/insights/join)로 이동하여 정보를 제공하면 팀 구성원이 연락을 드리겠습니다.</span><span class="sxs-lookup"><span data-stu-id="9a129-187">If you do not see the option for *Sync organizational data from SDS (preview)* on the Settings page, go to the [sign-up page](https://aka.ms/insights/join) to provide your information, and a team member will reach out to you.</span></span>

:::image type="content" source="media/insights-sds-settings.png" alt-text="Insights와 동기화 토글":::

### <a name="deploy-sds"></a><span data-ttu-id="9a129-189">SDS 배포</span><span class="sxs-lookup"><span data-stu-id="9a129-189">Deploy SDS</span></span>
<span data-ttu-id="9a129-190">**SDS를 이미 사용하는 경우** [모범 사례](#best-practices)를 따르는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="9a129-190">**If you already use SDS**, we recommend you follow our [best practices](#best-practices).</span></span> 

<span data-ttu-id="9a129-191">현재 프로필을 Insights와 동기화하려면 **프로필 동기화** 로 이동하고, **편집** 을 클릭하고, **SDS에서 조직 데이터 동기화** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9a129-191">To sync your current profiles with Insights, go to your **Sync Profile(s)**, click **Edit**, and select **Sync organizational data from SDS**.</span></span> <span data-ttu-id="9a129-192">초기 동기화를 위해 SIS에서 데이터를 새로 고친 후 보고서를 사용할 수 있을 때까지 24시간을 기다리는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="9a129-192">For the initial sync, we recommend waiting 24 hours for the reports to be available after the data is refreshed from your SIS.</span></span>  

<span data-ttu-id="9a129-193">**아직 SDS를 사용하지 않는 경우** 지금 [SDS를 배포](https://docs.microsoft.com/schooldatasync/deploying-school-data-sync)해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a129-193">**If you don't use SDS yet**, you now need to [deploy it](https://docs.microsoft.com/schooldatasync/deploying-school-data-sync).</span></span>

<span data-ttu-id="9a129-194">배포 프로세스 동안 Teams에서 사용자 및 수업을 프로비전하는 데 SDS를 사용할지 아니면 데이터를 Insights에 사용할지 결정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9a129-194">During the deployment process, you can decide if you want to use SDS for provisioning users and classes in Teams or to use it only to provide data to Insights.</span></span>

> [!NOTE]
> <span data-ttu-id="9a129-195">현재 한 해의 반이 지났고 이미 수동으로 팀을 만든 경우 SDS를 사용하여 Insights에 데이터만 제공하고 내년에 Teams에서 사용자와 수업을 프로비전하는 데 SDS를 사용하는 것을 고려하세요.</span><span class="sxs-lookup"><span data-stu-id="9a129-195">If it's the middle of the year and you already created teams manually, use SDS only to provide the data to Insights, and next year consider to use SDS for provisioning users and classes in Teams as well.</span></span>

### <a name="verify-the-sync-process"></a><span data-ttu-id="9a129-196">동기화 프로세스 확인</span><span class="sxs-lookup"><span data-stu-id="9a129-196">Verify the sync process</span></span>
<span data-ttu-id="9a129-197">조직 데이터 동기화 옆에 새 상태 영역이 나타납니다. 설정 페이지에서 미리 보기입니다.</span><span class="sxs-lookup"><span data-stu-id="9a129-197">A new status area appears next to Sync organizational data – Preview on the Settings page.</span></span>
 
*   <span data-ttu-id="9a129-198">상태가 **진행 중** 이면 SDS 프로필을 배포한 후 최대 24시간까지 기다리세요.</span><span class="sxs-lookup"><span data-stu-id="9a129-198">If the status is **In progress**, please wait up to 24 hours after deployment of the SDS profile.</span></span>

*   <span data-ttu-id="9a129-199">상태가 **완료됨** 이라면 축하합니다, 조직 수준에서 Insights를 보고 다음 단계로 계속할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9a129-199">If the status is **Completed**, congratulations, you can see Insights at the organizational level, and continue to the next step.</span></span>

*   <span data-ttu-id="9a129-200">상태가 **오류로 완료**, **경고로 완료** 또는 **중단됨** 인 경우 최근 동기화에 대한 오류와 경고가 포함된 로그 파일을 다운로드하고 이러한 오류를 해결할 수 있는지 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="9a129-200">If the status is **Completed with errors**, **Completed with warnings**, or **Aborted**, download the log file that contains the errors and warnings for the latest sync and check if you can fix these errors.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="9a129-201">문제가 발생하면 [고객 지원](https://aka.ms/edusupport)에서 도움을 드리겠습니다.</span><span class="sxs-lookup"><span data-stu-id="9a129-201">If you run into any problems, [customer support](https://aka.ms/edusupport) is there to help you.</span></span>
