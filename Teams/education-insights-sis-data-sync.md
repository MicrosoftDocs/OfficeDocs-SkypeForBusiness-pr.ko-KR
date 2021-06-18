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
ms.openlocfilehash: 9b0d9ae3788be09e4a66724e6122791a91b6879f
ms.sourcegitcommit: 35ee6946b6f560a268d1313bf51c3cc94d8d52f1
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/17/2021
ms.locfileid: "52997737"
---
# <a name="sync-student-information-system-sis-data-with-education-insights"></a><span data-ttu-id="7ad74-103">SIS(학생 정보 시스템) 데이터와 Education Insights 동기화</span><span class="sxs-lookup"><span data-stu-id="7ad74-103">Sync Student Information System (SIS) data with Education Insights</span></span>
<span data-ttu-id="7ad74-104">더 많은 데이터가 [Education Insights](class-insights.md)에 제공될수록 교육자는 학생을 더 잘 지원할 수 있으며 교육 리더는 교육자를 더 잘 지원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7ad74-104">The more data is fed into [Education Insights](class-insights.md), the better educators can support their students, and education leaders can support the educators.</span></span>

<span data-ttu-id="7ad74-105">조직 수준의 Insights를 제공하려면 Insights가 교육 시스템의 계층 구조가 올바르게 매핑되도록 [SDS(학교 데이터 동기화)](/SchoolDataSync)를 사용하여 SIS(학생 정보 시스템)에 연결해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7ad74-105">To provide organization-level Insights, we must use [School Data Sync (SDS)](/SchoolDataSync) to connect to the Student Information System (SIS) so that Insights has the hierarchical structure of the educational system mapped correctly.</span></span> 

<span data-ttu-id="7ad74-106">Teams의 수업 구조와 권한을 사용하기 때문에 이 동기화에 대해 수업 교육자로서 수업 수준 Insights를 볼 필요가 *없습니다*.</span><span class="sxs-lookup"><span data-stu-id="7ad74-106">Viewing class-level Insights as the class educator *does not* require this sync because we use Teams' class structure and permissions.</span></span>

## <a name="plan-your-school-data-sync-integration"></a><span data-ttu-id="7ad74-107">학교 데이터 동기화 통합 계획</span><span class="sxs-lookup"><span data-stu-id="7ad74-107">Plan your School Data Sync integration</span></span>
<span data-ttu-id="7ad74-108">Microsoft School 데이터 동기화(SDS라고도 함)는 학교 정보 시스템(즉, SIS) 데이터를 제공하며 교육 시스템의 계층 구조이며, 학생 및 조직 계층 구조에 대한 추가 데이터를 제공하며, 할당된 사용자를 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="7ad74-108">The Microsoft School Data Sync (a.k.a SDS) provides the School Information System (a.k.a SIS) data and it’s hierarchical structure of the educational system and maps which user is assigned where, as well as provides additional data on the student and organizational hierarchy.</span></span>

<span data-ttu-id="7ad74-109">Insights는 [SDS V2 파일 형식](/schooldatasync/sds-v2-csv-file-format)을 사용할 때 사용할 때 가장 잘 작동하지만, *기능이 제한* 된 [SDS V1 파일 형식](/schooldatasync/school-data-sync-format-csv-files-for-sds)도 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="7ad74-109">Insights works best when using [SDS V2 file format](/schooldatasync/sds-v2-csv-file-format) and up, but also supports [SDS V1 file format](/schooldatasync/school-data-sync-format-csv-files-for-sds) *with limited functionality*.</span></span>


### <a name="differences-between-sds-v1-and-v2-file-formats"></a><span data-ttu-id="7ad74-110">SDS V1과 V2 파일 형식의 차이점</span><span class="sxs-lookup"><span data-stu-id="7ad74-110">Differences between SDS V1 and V2 file formats</span></span>

<span data-ttu-id="7ad74-111">인사이트를 최대한 활용하려면 파일 형식 v2 또는 v2.1(출시 예정)을 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="7ad74-111">To get the most out of insights it is recommended to use file format v2 or v2.1 (Coming soon)</span></span>

| <span data-ttu-id="7ad74-112">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="7ad74-112">Data type</span></span> | <span data-ttu-id="7ad74-113">V1</span><span class="sxs-lookup"><span data-stu-id="7ad74-113">V1</span></span> | <span data-ttu-id="7ad74-114">V2</span><span class="sxs-lookup"><span data-stu-id="7ad74-114">V2</span></span> |
|:--- |:--- |:--- |
| <span data-ttu-id="7ad74-115">**사용자**</span><span class="sxs-lookup"><span data-stu-id="7ad74-115">**Users**</span></span> | <span data-ttu-id="7ad74-116">V1 형식에는 **교육자만** 포함되어 있으므로 교육 리더에 대한 조직 수준 권한을 설정하려면 각각의 권한을 수동으로 정의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7ad74-116">The V1 format contains **only educators**, so to set org-level permissions for your education leaders, you need to define each one's permission manually.</span></span> | <span data-ttu-id="7ad74-117">V2 형식에는 역할 기반 권한을 할당할 수 있도록 **모든 역할** 이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7ad74-117">The V2 format contains **all the roles** so that you can assign role-based permissions.</span></span> |
| <span data-ttu-id="7ad74-118">**조직**</span><span class="sxs-lookup"><span data-stu-id="7ad74-118">**Orgs**</span></span> | <span data-ttu-id="7ad74-119">V1 형식에는 **학교만** 포함되어 있으므로 한 집계 수준(모든 학교)만 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="7ad74-119">The V1 format contains **only schools**, so you see only one aggregation level (all your schools).</span></span> <span data-ttu-id="7ad74-120">플랫 목록을 사용하여 특정 학교를 확대할 수 있지만, 이 목록에는 많은 학교나 비교하기 어려운 여러 유형의 학교(예: 초/중/고/과학/예술 학교)가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7ad74-120">You can zoom in to a specific school using a flat list, but this list may have a large number of schools or contain different types of schools that are hard to compare (such as primary to secondary school or science to art school).</span></span><br/><br/> <span data-ttu-id="7ad74-121">계층 구조가 있는 경우 과학 또는 예술 부서와 같이 의미 있는 수준을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7ad74-121">When there is a hierarchy in place, you can create levels that make sense, such as a science or art department.</span></span>| <span data-ttu-id="7ad74-122">V2 형식은 대학, 학부, 캠퍼스, 지역, 프로그램 등 **학군 또는 기관의 전체 계층 구조에 대한 전체 계층** 을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="7ad74-122">The V2 format contains **the full hierarchy of your district or institution**, including universities, colleges, faculties, campuses, regions, programs, and so on.</span></span><br/><br/> <span data-ttu-id="7ad74-123">계층 구조를 사용하여 계층 구조의 수준별로 관련 집계를 보고, 각 수준에서 조직 단위를 빠르게 비교하고, 특정 수준에 대한 권한을 할당하고, 조직 수준별로 목표를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7ad74-123">With a hierarchy, you can see relevant aggregation by each level of the hierarchy, quickly compare between organizational units at each level, assign permission to specific levels, set goals by org level, and so on.</span></span>|

> [!NOTE]
> <span data-ttu-id="7ad74-124">고객은 2021년 7월 15일부터 파일 형식 v2를 온보딩할 수 없으며 대신 v2.1 형식을 사용해야 합니다. 향후 모든 업그레이드 및 새 기능은 v2.1 형식으로 수행되며 파일 형식 v1과 완전히 호환됩니다.</span><span class="sxs-lookup"><span data-stu-id="7ad74-124">Customers will not be able on onboard file format v2 starting July 15th 2021, and will need to use the v2.1 format instead, all future upgrades and new capabilitie will be done on the v2.1 format and it will be fully backward compatible to file format v1.</span></span>

## <a name="best-practices"></a><span data-ttu-id="7ad74-125">모범 사례</span><span class="sxs-lookup"><span data-stu-id="7ad74-125">Best practices</span></span>
<span data-ttu-id="7ad74-126">계층 구조의 정확한 매핑과 계층 구조 내에서 모든 사람이 속한 위치를 통해 Insights는 다양한 교육 리더 유형에 대해 정확한 데이터와 더 정확하고 관련있는 정보를 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7ad74-126">The accurate mapping of the hierarchy and where everyone belongs within that hierarchy, enables Insights to provide accurate data and more precise and relevant insights for the different types of education leaders.</span></span>

<span data-ttu-id="7ad74-127">더 자세한 정보를 제공할수록 보고서와 스포트라이트가 더 좋아지고 관련성이 더 높아집니다.</span><span class="sxs-lookup"><span data-stu-id="7ad74-127">The more detail you provide, the better and more relevant the reports and spotlights will be.</span></span>

<span data-ttu-id="7ad74-128">다음은 사용자가 Insights를 가장 잘 활용할 수 있도록 SDS의 원활한 배포를 보장하는 몇 가지 모범 사례입니다.</span><span class="sxs-lookup"><span data-stu-id="7ad74-128">Here are some best practices to ensure the smooth deployment of SDS so that your users can make the most out of Insights.</span></span>

### <a name="file-format-version-to-ue"></a><span data-ttu-id="7ad74-129">ue 파일 형식 버전</span><span class="sxs-lookup"><span data-stu-id="7ad74-129">File format version to ue</span></span>
*   <span data-ttu-id="7ad74-130">파일 형식 V2.1(출시 예정)을 사용하고 Education Insights에서 사용하는 선택적 데이터를 동기화합니다.</span><span class="sxs-lookup"><span data-stu-id="7ad74-130">Use file format V2.1 (coming soon) and sync the optional data used by Education Insights</span></span>

### <a name="users-and-roles"></a><span data-ttu-id="7ad74-131">사용자 및 역할</span><span class="sxs-lookup"><span data-stu-id="7ad74-131">Users and Roles</span></span>
*   <span data-ttu-id="7ad74-132">제공하고 동기화 한 파일에 **모든 사용자** 가 나열되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="7ad74-132">Make sure **all users are listed in the files** you provide and synced.</span></span> <span data-ttu-id="7ad74-133">여기에는 자신이 포함된 조직 단위의 데이터를 봐야 하는 모든 학생과 교직원이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="7ad74-133">This includes all students and staff that need to see data for the organizational units they cover.</span></span>
    <span data-ttu-id="7ad74-134">현재 SDS에 교육자만 나열되어 있는 경우 파일을 SDS에 업로드하고 데이터를 동기화하기 전에 다른 사용자를 수동으로 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="7ad74-134">If you currently only have educators listed in the SIS, add the other users manually before uploading the files to SDS and syncing the data.</span></span>
    <span data-ttu-id="7ad74-135">일부 학생이 누락된 경우 Insights에서 수집한 통계는 등록된 학생들에게서만 온 것이며, 이 경우 데이터와 결론에 오해의 소지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7ad74-135">The stats gathered by Insights is only from the registered students, if some students re missing, that will make the data and conclusions misleading.</span></span>
    
*   <span data-ttu-id="7ad74-136">**각 사용자의 성과 이름을 제공** 해야 합니다. </span><span class="sxs-lookup"><span data-stu-id="7ad74-136">Make sure to **provide the first and last name of each user**.</span></span> <span data-ttu-id="7ad74-137">그렇지 않으면 전자 메일 주소로 참조되며 이는 보고서 및 스포트라이트(학생 활동 또는 성과에 대한 인사이트가 있는 카드)에서 최적이 아닌 경험을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="7ad74-137">Otherwise, they will be referenced by their email address, and this provides a non-optimal experience in the reports and spotlights (cards with Insights on student activity or performance).</span></span>

*   <span data-ttu-id="7ad74-138">성적/연도 수준은 이 [매핑 목록](#supported-grade-level-values)을 기반으로 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7ad74-138">The grade/year level must be based on this [mapping list](#supported-grade-level-values).</span></span> 

*   <span data-ttu-id="7ad74-139">활동 데이터를 집계하고 필터링할 수 있도록 **모든 학생에 연도/성적 수준을 추가** 하는 것이 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="7ad74-139">It's important to **add the year/grade level to all students** so that the activity data can be aggregated and filtered by it.</span></span>    

*   <span data-ttu-id="7ad74-140">**각 사용자를 관련 조직 단위** 에 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7ad74-140">Make sure to **assign each user to their relevant organizational unit**.</span></span> <span data-ttu-id="7ad74-141">이러한 방식으로 교육 Insights는 교육 Insights 스포트라이트에서 잘못된 데이터를 표시하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7ad74-141">That way, Education Insights will not show misleading data in the Education Inisghts spotlights.</span></span>

    *   <span data-ttu-id="7ad74-142">학생은 둘 이상의 조직과 연결될 수 있습니다(예: 특수 프로그램 또는 두 개의 학부에 등록된 학생).</span><span class="sxs-lookup"><span data-stu-id="7ad74-142">A student can be associated to more than one organizational unit, for example, students who are registered in a special program or two faculties.</span></span> <span data-ttu-id="7ad74-143">학생에게 하나 이상의 조직 구성 단위가 있는 경우 해당 학생에 대한 사용자 파일의 각 줄에 대한 줄을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="7ad74-143">In case the student has more hte one organizational unit, provide a line for each in the users file for that student.</span></span>
    
    *   <span data-ttu-id="7ad74-144">IT 관리자는 직원의 조직 구성 단위에 따라 권한을 부여할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7ad74-144">IT admin can grant permissions based on organizational unit for staff.</span></span> <span data-ttu-id="7ad74-145">**올바른 단위 수준과 연결되어 있는지 확인** 하여 필요한 사용 권한을 받을 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="7ad74-145">**Make sure staff members are associated with the correct unit level**, so they receive the permissions they need.</span></span> <span data-ttu-id="7ad74-146">예를 들어, 4개의 학교에 배정된 상담사는 4개 학교의 모든 성적을 봐야 합니다. 교장은 자신의 학교의 모든 수업을 봐야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7ad74-146">For example, a counselor assigned to four schools needs to see all the grades in those schools; a principal needs to see all the classes in their school.</span></span> 
    
*   <span data-ttu-id="7ad74-147">**역할은 중요합니다**.</span><span class="sxs-lookup"><span data-stu-id="7ad74-147">**The role is vital**.</span></span> <span data-ttu-id="7ad74-148">이 닫힌 목록이지만 [목록](/schooldatasync/sds-v2-csv-file-format#enumerated-values-enum-supported)의 역할을 업로드한 각 사용자의 실제 역할과 일치시키세요.</span><span class="sxs-lookup"><span data-stu-id="7ad74-148">Although this list is closed, try to match the role from [the list](/schooldatasync/sds-v2-csv-file-format#enumerated-values-enum-supported) to the real role of each user you upload.</span></span> <span data-ttu-id="7ad74-149">이렇게 하면 그에 따라 역할 기반 권한을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7ad74-149">This will enable you to assign role-based permissions accordingly.</span></span> <span data-ttu-id="7ad74-150">예를 들어 모든 교장이 학교의 수업을 볼 수 있거나 모든 교수가 교직원을 볼 수 있는 권한을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="7ad74-150">For example, provide permissions for all principals to see the classes in their school, or for all professors to see their faculty.</span></span> 

### <a name="organizations"></a><span data-ttu-id="7ad74-151">조직</span><span class="sxs-lookup"><span data-stu-id="7ad74-151">Organizations</span></span>

* <span data-ttu-id="7ad74-152">**조직의 실제 및 완전한 계층 구조가 반영** 되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="7ad74-152">Make sure to **reflect the real and full hierarchy of your organization**.</span></span> <span data-ttu-id="7ad74-153">이 작업은 수동으로 파일을 추가하여 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7ad74-153">This can be achieved by manually adding the file.</span></span> <span data-ttu-id="7ad74-154">경우에 따라 이 계층 구조는 SIS에 반영되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7ad74-154">In some cases, this hierarchy is not reflected in the SIS.</span></span> <span data-ttu-id="7ad74-155">계층 구조의 수준별 관련 집계를 보고, 특정 수준에 권한을 할당하고, 목표를 조직 수준별로 설정하는 등의 작업이 필요한 경우도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7ad74-155">Still, it may be necessary  to see the relevant aggregation by each level of the hierarchy, assign permission to specific levels, set goals by organization level, and so on.</span></span> 

* <span data-ttu-id="7ad74-156">조직 트리 아래의 **모든 조직 단위에 학생 또는 수업이 포함** 되어 학생 데이터를 집계해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7ad74-156">Ensure that **all organization units down the organization tree include students or classes** to aggregate student data for them.</span></span> <span data-ttu-id="7ad74-157">학생은 트리의 최하위 가지에 있는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="7ad74-157">We recommend that students are on the lowest branch of the tree.</span></span>

> [!NOTE]
> <span data-ttu-id="7ad74-158">SDS 배포에 대한 자세한 내용은 [SDS 계획](/schooldatasync/planning-school-data-sync)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7ad74-158">For more details about SDS deployment, visit [Planning SDS](/schooldatasync/planning-school-data-sync).</span></span>

## <a name="integrate-sis-data-using-sds"></a><span data-ttu-id="7ad74-159">SDS를 사용하여 SIS 데이터 통합</span><span class="sxs-lookup"><span data-stu-id="7ad74-159">Integrate SIS data using SDS</span></span>

<span data-ttu-id="7ad74-160">SDS(학교 데이터 동기화)는 교육용 Office 365와 함께 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="7ad74-160">School Data Sync (SDS) is provided with Office 365 for Education.</span></span> <span data-ttu-id="7ad74-161">SDS는 교육 기관의 SIS(학생 정보 시스템)에서 데이터를 읽고 이를 Teams와 같은 Microsoft 응용 프로그램과 통합하여 온라인 교실과 사용자를 자동으로 만들 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="7ad74-161">SDS reads the data from an educational institution's Student Information System (SIS) and integrates it with Microsoft applications like Teams to enable the automatic creation of online classrooms and users.</span></span>

<span data-ttu-id="7ad74-162">또한, SIS 데이터를 Insights와 동기화합니다.</span><span class="sxs-lookup"><span data-stu-id="7ad74-162">It also synchronizes the SIS data with Insights.</span></span>

<span data-ttu-id="7ad74-163">IT 관리자는 프로비전 전용, Insights 전용 또는 두 가지 모두에 대해서 SDS를 사용하도록 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7ad74-163">As an IT Admin, you can choose to use SDS for provisioning only, Insights only or for both.</span></span>

<span data-ttu-id="7ad74-164">SIS 정보를 Educations Insights와 동기화하려면 [Insights에 SDS를 배포하는 방법](/schooldatasync/how-to-deploy-sds-for-insights)의 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="7ad74-164">To Sync your SIS information with Educations Insights follow the instructions in [How to deploy SDS for Insights](/schooldatasync/how-to-deploy-sds-for-insights).</span></span>

### <a name="deploy-sds"></a><span data-ttu-id="7ad74-165">SDS 배포</span><span class="sxs-lookup"><span data-stu-id="7ad74-165">Deploy SDS</span></span>
<span data-ttu-id="7ad74-166">**SDS를 이미 사용하는 경우** [모범 사례](#best-practices)를 따르는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="7ad74-166">**If you already use SDS**, we recommend you follow our [best practices](#best-practices).</span></span> 

<span data-ttu-id="7ad74-167">**아직 SDS를 사용하지 않는 경우** 지금 [SDS를 배포](/schooldatasync/deploying-school-data-sync)해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7ad74-167">**If you don't use SDS yet**, you now need to [deploy it](/schooldatasync/deploying-school-data-sync).</span></span>

<span data-ttu-id="7ad74-168">배포 프로세스 중에 사용자 및 클래스를 Teams에 프로비전하는 데 SDS를 사용할 것인지 아니면 Insights에 사용자 및 조직 계층을 제공하는 데만 사용할 것인지 결정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7ad74-168">During the deployment process, you can decide if you want to use SDS for provisioning users and classes to Teams or to use it only to provide user and organizational hierarchy to Insights as well.</span></span>

> [!NOTE]
> <span data-ttu-id="7ad74-169">현재의 한 해의 반이 지났고 이미 수동으로 팀을 만든 경우 SDS를 사용하여 Insights에 사용자 및 조직 계층 데이터를 제공하고 내년에는 Teams에 대한 사용자 및 클래스를 프로비전하는 데 SDS를 사용하는 것을 고려하십시오.</span><span class="sxs-lookup"><span data-stu-id="7ad74-169">If it's the middle of the year and you already created teams manually, use SDS only to provide the user and organizational hierarchy data to Insights, and next year consider using SDS for provisioning users and classes for Teams as well.</span></span>

### <a name="verify-the-sync-process"></a><span data-ttu-id="7ad74-170">동기화 프로세스 확인</span><span class="sxs-lookup"><span data-stu-id="7ad74-170">Verify the sync process</span></span>
<span data-ttu-id="7ad74-171">동기화 상태 진행률을 확인하려면 [Insights용 SDS 데이터 상태 및 모니터링](/schooldatasync/sds-for-insights-data-health-and-monitoring)의 지침을 따르세요.</span><span class="sxs-lookup"><span data-stu-id="7ad74-171">To verify the sync status progress follow the instructions in [SDS for Insights Data Health and Monitoring](/schooldatasync/sds-for-insights-data-health-and-monitoring).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7ad74-172">문제가 발생하면 [고객 지원](https://aka.ms/edusupport)에서 도움을 드리겠습니다.</span><span class="sxs-lookup"><span data-stu-id="7ad74-172">If you run into any problems, [customer support](https://aka.ms/edusupport) is there to help you.</span></span>

## <a name="supported-grade-level-values"></a><span data-ttu-id="7ad74-173">지원되는 성적 수준 값</span><span class="sxs-lookup"><span data-stu-id="7ad74-173">Supported grade level values</span></span>

<span data-ttu-id="7ad74-174">SDS 파일에서 열거된 값으로 정의된 성적/학년 수준인 CSV 파일 내에서 선택된 값 집합만 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7ad74-174">In the SDS files, grade/year level defined as Enumerated values, which means you can only provide a selected set of values within the CSV file.</span></span> <span data-ttu-id="7ad74-175">지정한 값 외의 다른 값은 동기화 처리 중에 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="7ad74-175">Anything other than values specified will result in an error during sync processing.</span></span>

<span data-ttu-id="7ad74-176">아래 섹션에서는 사용자 파일의 지원되는 값을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="7ad74-176">The section below defines the supported values in the users file.</span></span>

### <a name="united-states--worldwide-grade-levels"></a><span data-ttu-id="7ad74-177">미국/전 세계 성적 수준</span><span class="sxs-lookup"><span data-stu-id="7ad74-177">United States / worldwide grade levels</span></span>
|<span data-ttu-id="7ad74-178">파일 값(성적 열)</span><span class="sxs-lookup"><span data-stu-id="7ad74-178">Value in file (Grade column)</span></span> | <span data-ttu-id="7ad74-179">Insights의 레이블</span><span class="sxs-lookup"><span data-stu-id="7ad74-179">Label in Insights</span></span>|
|:---|:---| 
|<span data-ttu-id="7ad74-180">IT</span><span class="sxs-lookup"><span data-stu-id="7ad74-180">IT</span></span>|<span data-ttu-id="7ad74-181">유아</span><span class="sxs-lookup"><span data-stu-id="7ad74-181">Infant</span></span>|
|<span data-ttu-id="7ad74-182">PR</span><span class="sxs-lookup"><span data-stu-id="7ad74-182">PR</span></span>|<span data-ttu-id="7ad74-183">미취학 아동</span><span class="sxs-lookup"><span data-stu-id="7ad74-183">Pre-school</span></span>|
|<span data-ttu-id="7ad74-184">PK</span><span class="sxs-lookup"><span data-stu-id="7ad74-184">PK</span></span>|<span data-ttu-id="7ad74-185">유아</span><span class="sxs-lookup"><span data-stu-id="7ad74-185">Pre-kindergarten</span></span>|
|<span data-ttu-id="7ad74-186">TK</span><span class="sxs-lookup"><span data-stu-id="7ad74-186">TK</span></span>|<span data-ttu-id="7ad74-187">유치원 준비 아동</span><span class="sxs-lookup"><span data-stu-id="7ad74-187">Transitional Kindergarten</span></span>|
|<span data-ttu-id="7ad74-188">KG</span><span class="sxs-lookup"><span data-stu-id="7ad74-188">KG</span></span>|<span data-ttu-id="7ad74-189">유치원생</span><span class="sxs-lookup"><span data-stu-id="7ad74-189">Kindergarten</span></span>|
|<span data-ttu-id="7ad74-190">01 또는 1</span><span class="sxs-lookup"><span data-stu-id="7ad74-190">01 or 1</span></span>|<span data-ttu-id="7ad74-191">1학년</span><span class="sxs-lookup"><span data-stu-id="7ad74-191">First grade</span></span>|
|<span data-ttu-id="7ad74-192">02 또는 2</span><span class="sxs-lookup"><span data-stu-id="7ad74-192">02 or 2</span></span>|<span data-ttu-id="7ad74-193">2학년</span><span class="sxs-lookup"><span data-stu-id="7ad74-193">Second grade</span></span>|
|<span data-ttu-id="7ad74-194">03 또는 3</span><span class="sxs-lookup"><span data-stu-id="7ad74-194">03 or 3</span></span>|<span data-ttu-id="7ad74-195">3학년</span><span class="sxs-lookup"><span data-stu-id="7ad74-195">Third grade</span></span>|
|<span data-ttu-id="7ad74-196">04 또는 4</span><span class="sxs-lookup"><span data-stu-id="7ad74-196">04 or 4</span></span>|<span data-ttu-id="7ad74-197">4학년</span><span class="sxs-lookup"><span data-stu-id="7ad74-197">Fourth grade</span></span>|
|<span data-ttu-id="7ad74-198">05 또는 5</span><span class="sxs-lookup"><span data-stu-id="7ad74-198">05 or 5</span></span>|<span data-ttu-id="7ad74-199">5학년</span><span class="sxs-lookup"><span data-stu-id="7ad74-199">Fifth grade</span></span>|
|<span data-ttu-id="7ad74-200">06 또는 6</span><span class="sxs-lookup"><span data-stu-id="7ad74-200">06 or 6</span></span>|<span data-ttu-id="7ad74-201">6학년</span><span class="sxs-lookup"><span data-stu-id="7ad74-201">Sixth grade</span></span>|
|<span data-ttu-id="7ad74-202">07 또는 7</span><span class="sxs-lookup"><span data-stu-id="7ad74-202">07 or 7</span></span>|<span data-ttu-id="7ad74-203">중학교 1학년</span><span class="sxs-lookup"><span data-stu-id="7ad74-203">Seventh grade</span></span>|
|<span data-ttu-id="7ad74-204">08 또는 8</span><span class="sxs-lookup"><span data-stu-id="7ad74-204">08 or 8</span></span>|<span data-ttu-id="7ad74-205">중학교 2학년</span><span class="sxs-lookup"><span data-stu-id="7ad74-205">Eighth grade</span></span>|
|<span data-ttu-id="7ad74-206">09 또는 9</span><span class="sxs-lookup"><span data-stu-id="7ad74-206">09 or 9</span></span>|<span data-ttu-id="7ad74-207">중학교 3학년</span><span class="sxs-lookup"><span data-stu-id="7ad74-207">Ninth grade</span></span>|
|<span data-ttu-id="7ad74-208">10</span><span class="sxs-lookup"><span data-stu-id="7ad74-208">10</span></span>|<span data-ttu-id="7ad74-209">고등학교 1학년</span><span class="sxs-lookup"><span data-stu-id="7ad74-209">Tenth grade</span></span>|
|<span data-ttu-id="7ad74-210">11</span><span class="sxs-lookup"><span data-stu-id="7ad74-210">11</span></span>|<span data-ttu-id="7ad74-211">고등학교 2학년</span><span class="sxs-lookup"><span data-stu-id="7ad74-211">Eleventh grade</span></span>|
|<span data-ttu-id="7ad74-212">12</span><span class="sxs-lookup"><span data-stu-id="7ad74-212">12</span></span>|<span data-ttu-id="7ad74-213">고등학교 3학년</span><span class="sxs-lookup"><span data-stu-id="7ad74-213">Twelfth grade</span></span>|
|<span data-ttu-id="7ad74-214">PS</span><span class="sxs-lookup"><span data-stu-id="7ad74-214">PS</span></span>|<span data-ttu-id="7ad74-215">고등학교 졸업 후 교육</span><span class="sxs-lookup"><span data-stu-id="7ad74-215">Postsecondary</span></span>|
|<span data-ttu-id="7ad74-216">PS1</span><span class="sxs-lookup"><span data-stu-id="7ad74-216">PS1</span></span>|<span data-ttu-id="7ad74-217">고등학교 졸업 후 교육 1학년</span><span class="sxs-lookup"><span data-stu-id="7ad74-217">Postsecondary freshman</span></span>|
|<span data-ttu-id="7ad74-218">PS2</span><span class="sxs-lookup"><span data-stu-id="7ad74-218">PS2</span></span>|<span data-ttu-id="7ad74-219">고등학교 졸업 후 교육 2학년</span><span class="sxs-lookup"><span data-stu-id="7ad74-219">Postsecondary sophomore</span></span>|
|<span data-ttu-id="7ad74-220">PS3</span><span class="sxs-lookup"><span data-stu-id="7ad74-220">PS3</span></span>|<span data-ttu-id="7ad74-221">고등학교 졸업 후 교육 3학년</span><span class="sxs-lookup"><span data-stu-id="7ad74-221">Postsecondary junior</span></span>|
|<span data-ttu-id="7ad74-222">PS4</span><span class="sxs-lookup"><span data-stu-id="7ad74-222">PS4</span></span>|<span data-ttu-id="7ad74-223">고등학교 졸업 후 교육 4학년</span><span class="sxs-lookup"><span data-stu-id="7ad74-223">Postsecondary senior</span></span>|
|<span data-ttu-id="7ad74-224">학부생</span><span class="sxs-lookup"><span data-stu-id="7ad74-224">undergraduate</span></span>|<span data-ttu-id="7ad74-225">학부생</span><span class="sxs-lookup"><span data-stu-id="7ad74-225">Undergraduate</span></span>|
|<span data-ttu-id="7ad74-226">졸업</span><span class="sxs-lookup"><span data-stu-id="7ad74-226">graduate</span></span>|<span data-ttu-id="7ad74-227">졸업</span><span class="sxs-lookup"><span data-stu-id="7ad74-227">Graduate</span></span>|
|<span data-ttu-id="7ad74-228">대학원</span><span class="sxs-lookup"><span data-stu-id="7ad74-228">postgraduate</span></span>|<span data-ttu-id="7ad74-229">대학원(연구를 중점으로 공부하는 학부생)</span><span class="sxs-lookup"><span data-stu-id="7ad74-229">Postgraduate (graduate with an emphasis on research)</span></span>|
|<span data-ttu-id="7ad74-230">동창생</span><span class="sxs-lookup"><span data-stu-id="7ad74-230">alumni</span></span>|<span data-ttu-id="7ad74-231">동창생</span><span class="sxs-lookup"><span data-stu-id="7ad74-231">Alumni</span></span>|
|<span data-ttu-id="7ad74-232">평생 교육</span><span class="sxs-lookup"><span data-stu-id="7ad74-232">adultEducation</span></span>|<span data-ttu-id="7ad74-233">평생 교육</span><span class="sxs-lookup"><span data-stu-id="7ad74-233">Adult Education</span></span>|
|<span data-ttu-id="7ad74-234">UG</span><span class="sxs-lookup"><span data-stu-id="7ad74-234">UG</span></span>|<span data-ttu-id="7ad74-235">성적이 매겨지지 않음</span><span class="sxs-lookup"><span data-stu-id="7ad74-235">Ungraded</span></span>|
|<span data-ttu-id="7ad74-236">기타</span><span class="sxs-lookup"><span data-stu-id="7ad74-236">Other</span></span>|<span data-ttu-id="7ad74-237">기타</span><span class="sxs-lookup"><span data-stu-id="7ad74-237">Other</span></span>|

### <a name="united-kingdom-year-groups"></a><span data-ttu-id="7ad74-238">영국 연도 그룹</span><span class="sxs-lookup"><span data-stu-id="7ad74-238">United Kingdom year groups</span></span>
|<span data-ttu-id="7ad74-239">파일 값(성적 열)</span><span class="sxs-lookup"><span data-stu-id="7ad74-239">Value in file (Grade column)</span></span> | <span data-ttu-id="7ad74-240">Insights의 레이블</span><span class="sxs-lookup"><span data-stu-id="7ad74-240">Label in Insights</span></span>|
|:---|:---| 
|<span data-ttu-id="7ad74-241">IT</span><span class="sxs-lookup"><span data-stu-id="7ad74-241">IT</span></span>|<span data-ttu-id="7ad74-242">보육</span><span class="sxs-lookup"><span data-stu-id="7ad74-242">Nursery</span></span>|
|<span data-ttu-id="7ad74-243">PR</span><span class="sxs-lookup"><span data-stu-id="7ad74-243">PR</span></span>|<span data-ttu-id="7ad74-244">미취학 아동</span><span class="sxs-lookup"><span data-stu-id="7ad74-244">Pre-school</span></span>|
|<span data-ttu-id="7ad74-245">PK</span><span class="sxs-lookup"><span data-stu-id="7ad74-245">PK</span></span>|<span data-ttu-id="7ad74-246">리셉션</span><span class="sxs-lookup"><span data-stu-id="7ad74-246">Reception</span></span>|
|<span data-ttu-id="7ad74-247">01 또는 1</span><span class="sxs-lookup"><span data-stu-id="7ad74-247">01 or 1</span></span>|<span data-ttu-id="7ad74-248">1년</span><span class="sxs-lookup"><span data-stu-id="7ad74-248">Year 1</span></span>|
|<span data-ttu-id="7ad74-249">02 또는 2</span><span class="sxs-lookup"><span data-stu-id="7ad74-249">02 or 2</span></span>|<span data-ttu-id="7ad74-250">2년</span><span class="sxs-lookup"><span data-stu-id="7ad74-250">Year 2</span></span>|
|<span data-ttu-id="7ad74-251">03 또는 3</span><span class="sxs-lookup"><span data-stu-id="7ad74-251">03 or 3</span></span>|<span data-ttu-id="7ad74-252">3년</span><span class="sxs-lookup"><span data-stu-id="7ad74-252">Year 3</span></span>|
|<span data-ttu-id="7ad74-253">04 또는 4</span><span class="sxs-lookup"><span data-stu-id="7ad74-253">04 or 4</span></span>|<span data-ttu-id="7ad74-254">4년</span><span class="sxs-lookup"><span data-stu-id="7ad74-254">Year 4</span></span>|
|<span data-ttu-id="7ad74-255">05 또는 5</span><span class="sxs-lookup"><span data-stu-id="7ad74-255">05 or 5</span></span>|<span data-ttu-id="7ad74-256">5년</span><span class="sxs-lookup"><span data-stu-id="7ad74-256">Year 5</span></span>|
|<span data-ttu-id="7ad74-257">06 또는 6</span><span class="sxs-lookup"><span data-stu-id="7ad74-257">06 or 6</span></span>|<span data-ttu-id="7ad74-258">6년</span><span class="sxs-lookup"><span data-stu-id="7ad74-258">Year 6</span></span>|
|<span data-ttu-id="7ad74-259">07 또는 7</span><span class="sxs-lookup"><span data-stu-id="7ad74-259">07 or 7</span></span>|<span data-ttu-id="7ad74-260">7년</span><span class="sxs-lookup"><span data-stu-id="7ad74-260">Year 7</span></span>|
|<span data-ttu-id="7ad74-261">08 또는 8</span><span class="sxs-lookup"><span data-stu-id="7ad74-261">08 or 8</span></span>|<span data-ttu-id="7ad74-262">8년</span><span class="sxs-lookup"><span data-stu-id="7ad74-262">Year 8</span></span>|
|<span data-ttu-id="7ad74-263">09 또는 9</span><span class="sxs-lookup"><span data-stu-id="7ad74-263">09 or 9</span></span>|<span data-ttu-id="7ad74-264">9년</span><span class="sxs-lookup"><span data-stu-id="7ad74-264">Year 9</span></span>|
|<span data-ttu-id="7ad74-265">10</span><span class="sxs-lookup"><span data-stu-id="7ad74-265">10</span></span>|<span data-ttu-id="7ad74-266">10년</span><span class="sxs-lookup"><span data-stu-id="7ad74-266">Year 10</span></span>|
|<span data-ttu-id="7ad74-267">11</span><span class="sxs-lookup"><span data-stu-id="7ad74-267">11</span></span>|<span data-ttu-id="7ad74-268">11년</span><span class="sxs-lookup"><span data-stu-id="7ad74-268">Year 11</span></span>|
|<span data-ttu-id="7ad74-269">12</span><span class="sxs-lookup"><span data-stu-id="7ad74-269">12</span></span>|<span data-ttu-id="7ad74-270">12년</span><span class="sxs-lookup"><span data-stu-id="7ad74-270">Year 12</span></span>|
|<span data-ttu-id="7ad74-271">13</span><span class="sxs-lookup"><span data-stu-id="7ad74-271">13</span></span>|<span data-ttu-id="7ad74-272">13년</span><span class="sxs-lookup"><span data-stu-id="7ad74-272">Year 13</span></span>|
|<span data-ttu-id="7ad74-273">PS</span><span class="sxs-lookup"><span data-stu-id="7ad74-273">PS</span></span>|<span data-ttu-id="7ad74-274">고등학교 졸업 후 교육</span><span class="sxs-lookup"><span data-stu-id="7ad74-274">Postsecondary</span></span>|
|<span data-ttu-id="7ad74-275">PS1</span><span class="sxs-lookup"><span data-stu-id="7ad74-275">PS1</span></span>|<span data-ttu-id="7ad74-276">고등학교 졸업 후 교육 1년</span><span class="sxs-lookup"><span data-stu-id="7ad74-276">Postsecondary Year 1</span></span>|
|<span data-ttu-id="7ad74-277">PS2</span><span class="sxs-lookup"><span data-stu-id="7ad74-277">PS2</span></span>|<span data-ttu-id="7ad74-278">고등학교 졸업 후 교육 2년</span><span class="sxs-lookup"><span data-stu-id="7ad74-278">Postsecondary Year 2</span></span>|
|<span data-ttu-id="7ad74-279">PS3</span><span class="sxs-lookup"><span data-stu-id="7ad74-279">PS3</span></span>|<span data-ttu-id="7ad74-280">고등학교 졸업 후 교육 3년</span><span class="sxs-lookup"><span data-stu-id="7ad74-280">Postsecondary Year 3</span></span>|
|<span data-ttu-id="7ad74-281">PS4</span><span class="sxs-lookup"><span data-stu-id="7ad74-281">PS4</span></span>|<span data-ttu-id="7ad74-282">고등학교 졸업 후 교육 4년</span><span class="sxs-lookup"><span data-stu-id="7ad74-282">Postsecondary Year 4</span></span>|
|<span data-ttu-id="7ad74-283">학부생</span><span class="sxs-lookup"><span data-stu-id="7ad74-283">undergraduate</span></span>|<span data-ttu-id="7ad74-284">학부생</span><span class="sxs-lookup"><span data-stu-id="7ad74-284">Undergraduate</span></span>|
|<span data-ttu-id="7ad74-285">졸업</span><span class="sxs-lookup"><span data-stu-id="7ad74-285">graduate</span></span>|<span data-ttu-id="7ad74-286">졸업</span><span class="sxs-lookup"><span data-stu-id="7ad74-286">Graduate</span></span>|
|<span data-ttu-id="7ad74-287">대학원</span><span class="sxs-lookup"><span data-stu-id="7ad74-287">postgraduate</span></span>|<span data-ttu-id="7ad74-288">대학원(연구를 중점으로 공부하는 학부생)</span><span class="sxs-lookup"><span data-stu-id="7ad74-288">Postgraduate (graduate with an emphasis on research)</span></span>|
|<span data-ttu-id="7ad74-289">동창생</span><span class="sxs-lookup"><span data-stu-id="7ad74-289">alumni</span></span>|<span data-ttu-id="7ad74-290">동창생</span><span class="sxs-lookup"><span data-stu-id="7ad74-290">Alumni</span></span>|
|<span data-ttu-id="7ad74-291">평생 교육</span><span class="sxs-lookup"><span data-stu-id="7ad74-291">adultEducation</span></span>|<span data-ttu-id="7ad74-292">평생 교육</span><span class="sxs-lookup"><span data-stu-id="7ad74-292">Adult Education</span></span>|
|<span data-ttu-id="7ad74-293">UG</span><span class="sxs-lookup"><span data-stu-id="7ad74-293">UG</span></span>|<span data-ttu-id="7ad74-294">성적이 매겨지지 않음</span><span class="sxs-lookup"><span data-stu-id="7ad74-294">Ungraded</span></span>|
|<span data-ttu-id="7ad74-295">기타</span><span class="sxs-lookup"><span data-stu-id="7ad74-295">Other</span></span>|<span data-ttu-id="7ad74-296">기타</span><span class="sxs-lookup"><span data-stu-id="7ad74-296">Other</span></span>|

