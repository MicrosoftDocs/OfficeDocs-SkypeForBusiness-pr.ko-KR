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
ms.openlocfilehash: 5d5ba5c2c5179d5c333472450fd9b2e9c270a4e9
ms.sourcegitcommit: 7579dda8018691eb1a724cb0311b53333dc3ae5a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/25/2021
ms.locfileid: "53142844"
---
# <a name="sync-student-information-system-sis-data-with-education-insights"></a><span data-ttu-id="f19d5-103">SIS(학생 정보 시스템) 데이터와 Education Insights 동기화</span><span class="sxs-lookup"><span data-stu-id="f19d5-103">Sync Student Information System (SIS) data with Education Insights</span></span>
<span data-ttu-id="f19d5-104">더 많은 데이터가 [Education Insights](class-insights.md)에 제공될수록 교육자는 학생을 더 잘 지원할 수 있으며 교육 리더는 교육자를 더 잘 지원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f19d5-104">The more data is fed into [Education Insights](class-insights.md), the better educators can support their students, and education leaders can support the educators.</span></span>

<span data-ttu-id="f19d5-105">조직 수준의 Insights를 제공하려면 Insights가 교육 시스템의 계층 구조가 올바르게 매핑되도록 [SDS(학교 데이터 동기화)](/SchoolDataSync)를 사용하여 SIS(학생 정보 시스템)에 연결해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f19d5-105">To provide organization-level Insights, we must use [School Data Sync (SDS)](/SchoolDataSync) to connect to the Student Information System (SIS) so that Insights has the hierarchical structure of the educational system mapped correctly.</span></span> 

<span data-ttu-id="f19d5-106">Teams의 수업 구조와 권한을 사용하기 때문에 이 동기화에 대해 수업 교육자로서 수업 수준 Insights를 볼 필요가 *없습니다*.</span><span class="sxs-lookup"><span data-stu-id="f19d5-106">Viewing class-level Insights as the class educator *does not* require this sync because we use Teams' class structure and permissions.</span></span>

## <a name="plan-your-school-data-sync-integration"></a><span data-ttu-id="f19d5-107">학교 데이터 동기화 통합 계획</span><span class="sxs-lookup"><span data-stu-id="f19d5-107">Plan your School Data Sync integration</span></span>
<span data-ttu-id="f19d5-108">Microsoft School 데이터 동기화(SDS라고도 함)는 학교 정보 시스템(즉, SIS) 데이터를 제공하며 교육 시스템의 계층 구조이며, 학생 및 조직 계층 구조에 대한 추가 데이터를 제공하며, 할당된 사용자를 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="f19d5-108">The Microsoft School Data Sync (a.k.a SDS) provides the School Information System (a.k.a SIS) data and it’s hierarchical structure of the educational system and maps which user is assigned where, as well as provides additional data on the student and organizational hierarchy.</span></span>

<span data-ttu-id="f19d5-109">Insights는 [SDS V2.1 파일 형식](/schooldatasync/sds-v2.1-csv-file-format)을 사용할 때 가장 잘 작동하지만 [SDS V2 파일 형식](/schooldatasync/sds-v2-csv-file-format) 및 [SDS V1 파일 형식에서](/schooldatasync/school-data-sync-format-csv-files-for-sds) *제한적으로 작동합니다*.</span><span class="sxs-lookup"><span data-stu-id="f19d5-109">Insights works best when using [SDS V2.1 file format](/schooldatasync/sds-v2.1-csv-file-format) but also supports [SDS V2 file format](/schooldatasync/sds-v2-csv-file-format) and  [SDS V1 file format](/schooldatasync/school-data-sync-format-csv-files-for-sds) *with limited functionality*.</span></span>


### <a name="differences-between-sds-v1-and-v2-file-formats"></a><span data-ttu-id="f19d5-110">SDS V1과 V2 파일 형식의 차이점</span><span class="sxs-lookup"><span data-stu-id="f19d5-110">Differences between SDS V1 and V2 file formats</span></span>

| <span data-ttu-id="f19d5-111">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="f19d5-111">Data type</span></span> | <span data-ttu-id="f19d5-112">V1</span><span class="sxs-lookup"><span data-stu-id="f19d5-112">V1</span></span> | <span data-ttu-id="f19d5-113">V2 및 V2.1</span><span class="sxs-lookup"><span data-stu-id="f19d5-113">V2 and V2.1</span></span> |
|:--- |:--- |:--- |
| <span data-ttu-id="f19d5-114">**사용자**</span><span class="sxs-lookup"><span data-stu-id="f19d5-114">**Users**</span></span> |<span data-ttu-id="f19d5-115">교육 리더에 대한 조직 수준 권한을 수동으로 설정해야 하므로 ‘강사‘ 역할만 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="f19d5-115">Supports only ‘educator’ role, as a result org-level permissions for your education leaders need to be set manually</span></span>|<span data-ttu-id="f19d5-116">역할 기반 권한을 설정할 수 있도록 다중 역할을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="f19d5-116">Supports multiple roles so that role-based permissions can be set</span></span>|
| <span data-ttu-id="f19d5-117">**조직**</span><span class="sxs-lookup"><span data-stu-id="f19d5-117">**Orgs**</span></span> | <span data-ttu-id="f19d5-118">'학교' 집계 수준만 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="f19d5-118">Supports only ‘schools’, aggregation level.</span></span><br><br><span data-ttu-id="f19d5-119">따라서 다중 집계 수준을 제공하지 않으며 다른 유형의 학교(예: 초등학교와 중/고등학교, 과학중/고등학교와 예술중/고등학교)를 비교하기 위해 제한된 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f19d5-119">As a result, does not provide multiple aggregation levels and provide limited ability to compare different types of schools (e.g primary vs. secondary school, science vs. art school)</span></span>|<span data-ttu-id="f19d5-120">구역/기관, 대학(4년제), 대학(전문대), 교수진, 캠퍼스, 지역 프로그램 등 다중 계층 구조형을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="f19d5-120">Supports multi-layer hierarchy, including district/institution, universities, colleges, faculties, campuses, regions, programs, etc.</span></span><br><br><span data-ttu-id="f19d5-121">다중 계층 수준을 허용하고 각 수준의 조직 수준 단위를 간편하게 비교하고 특정 수준에 권한을 할당하고 조직 수준별로 목표를 설정하는 등의 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f19d5-121">Allows for multiple aggregation levels and to easily compare between organizational units at each level, assign permissions to specific levels, set goals by org level, etc.</span></span>|
| <span data-ttu-id="f19d5-122">**추가 선택적 정보**</span><span class="sxs-lookup"><span data-stu-id="f19d5-122">**Additional optional information**</span></span> |<span data-ttu-id="f19d5-123">없음</span><span class="sxs-lookup"><span data-stu-id="f19d5-123">None</span></span>|<span data-ttu-id="f19d5-124">**V2.1 파일 형식만**</span><span class="sxs-lookup"><span data-stu-id="f19d5-124">**V2.1 file format only**</span></span><br><br><span data-ttu-id="f19d5-125">*교육 세션* - 세션 기간(학기, 학년도 등)</span><span class="sxs-lookup"><span data-stu-id="f19d5-125">*Academic Sessions* - timeframes of sessions (semesters, school years etc.)</span></span><br><br><span data-ttu-id="f19d5-126">인구 통계 및 학생 플래그\* - 인종, 성별과 같은 데이터뿐만 아니라 특별 프로그램(IEP, 504)</span><span class="sxs-lookup"><span data-stu-id="f19d5-126">Demographics and student flags\* - data like race, ethnicity, and gender, as well as special programs (IEP, 504)</span></span>|

> [!NOTE]
> <span data-ttu-id="f19d5-127">고객은 2021년 7월 15일부터 파일 형식 v2를 온보딩할 수 없으며 대신 v2.1 형식을 사용해야 합니다. 향후 모든 업그레이드 및 새 기능은 v2.1 형식으로 수행되며 파일 형식 v1과 완전히 호환됩니다.</span><span class="sxs-lookup"><span data-stu-id="f19d5-127">Customers will not be able on onboard file format v2 starting July 15th 2021, and will need to use the v2.1 format instead, all future upgrades and new capabilitie will be done on the v2.1 format and it will be fully backward compatible to file format v1.</span></span>

### <a name="best-practices"></a><span data-ttu-id="f19d5-128">모범 사례</span><span class="sxs-lookup"><span data-stu-id="f19d5-128">Best practices</span></span>

<span data-ttu-id="f19d5-129">계층 구조의 정확한 매핑과 계층 구조 내에서 모든 사람이 속한 위치를 통해 Insights는 다양한 교육 리더 유형에 대해 정확한 데이터와 더 정확하고 관련있는 정보를 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f19d5-129">The accurate mapping of the hierarchy and where everyone belongs within that hierarchy, enables Insights to provide accurate data and more precise and relevant insights for the different types of education leaders.</span></span>

<span data-ttu-id="f19d5-130">더 자세한 정보를 제공할수록 보고서와 스포트라이트가 더 좋아지고 관련성이 더 높아집니다.</span><span class="sxs-lookup"><span data-stu-id="f19d5-130">The more detail you provide, the better and more relevant the reports and spotlights will be.</span></span>

#### <a name="file-format-version-to-use-adn-data-to-sync"></a><span data-ttu-id="f19d5-131">사용할 파일 형식 버전 및 동기화할 데이터</span><span class="sxs-lookup"><span data-stu-id="f19d5-131">File format version to use adn data to sync</span></span>
*   <span data-ttu-id="f19d5-132">파일 형식 V2.1을 사용하고 [여기](/schooldatasync/sds-for-insights-overview#education-insights-capabilities-matrix-and-sds-v21-csv)에서 설명된 대로 Education Insights에서 사용하는 선택적 데이터를 동기화합니다.</span><span class="sxs-lookup"><span data-stu-id="f19d5-132">Use file format V2.1 and sync the optional data used by Education Insights as described [here](/schooldatasync/sds-for-insights-overview#education-insights-capabilities-matrix-and-sds-v21-csv).</span></span>

#### <a name="users-and-roles"></a><span data-ttu-id="f19d5-133">사용자 및 역할</span><span class="sxs-lookup"><span data-stu-id="f19d5-133">Users and Roles</span></span>
*   <span data-ttu-id="f19d5-134">제공하고 동기화 한 파일에 **모든 사용자** 가 나열되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="f19d5-134">Make sure **all users are listed in the files** you provide and synced.</span></span> <span data-ttu-id="f19d5-135">여기에는 자신이 포함된 조직 단위의 데이터를 봐야 하는 모든 학생과 교직원이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="f19d5-135">This includes all students and staff that need to see data for the organizational units they cover.</span></span>
*   <span data-ttu-id="f19d5-136">현재 SDS에 교육자만 나열되어 있는 경우 파일을 SDS에 업로드하고 데이터를 동기화하기 전에 모든 다른 사용자를 수동으로 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="f19d5-136">If you currently only have educators listed in your SIS, add all other users manually before uploading the files to SDS and syncing the data.</span></span> <span data-ttu-id="f19d5-137">일부 학생이 누락된 경우 Insights에서 수집한 통계는 등록된 학생들에게서만 온 것이며, 이 경우 데이터와 결론에 오해의 소지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f19d5-137">The stats gathered by Insights will onlybe  from the registered students, if some students are missing, that will make the data and conclusions misleading.</span></span>
    
*   <span data-ttu-id="f19d5-138">플고비저닝에도 SDS를 사용하는 경우, **각 사용자의 성과 이름을 제공해야 합니다**.</span><span class="sxs-lookup"><span data-stu-id="f19d5-138">If you use SDS for provisioning as well, make sure to **provide the first and last name of each user**.</span></span> <span data-ttu-id="f19d5-139">그렇지 않으면, 학생이 전자 메일 주소로 참조되므로 최적의 환경이 될 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f19d5-139">Otherwise, students will be referenced by their email address, resulting in a non-optimal experience.</span></span>

*   <span data-ttu-id="f19d5-140">성적/연도 수준은 이 [매핑 목록](#supported-grade-level-values)을 기반으로 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f19d5-140">The grade/year level must be based on this [mapping list](#supported-grade-level-values).</span></span> 

*   <span data-ttu-id="f19d5-141">**나이/학년 수준을 모든 학생에 대해 추가** 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f19d5-141">Make sure to **add the year/grade level to all students** .</span></span>    

*   <span data-ttu-id="f19d5-142">**각 사용자를 관련 조직 단위** 에 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f19d5-142">Make sure to **assign each user to their relevant organizational unit**.</span></span>

    *   <span data-ttu-id="f19d5-143">학생은 둘 이상의 조직과 연결될 수 있습니다(예: 특수 프로그램 또는 두 개의 학부에 등록된 학생).</span><span class="sxs-lookup"><span data-stu-id="f19d5-143">A student can be associated to more than one organizational unit, for example, students who are registered in a special program or two faculties.</span></span> <span data-ttu-id="f19d5-144">학생에게 하나 이상의 조직 구성 단위가 있는 경우 해당 학생에 대한 사용자 파일의 각 줄에 대한 줄을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f19d5-144">In case the student has more then one organizational unit, provide a line for each in the users file for that student.</span></span>
    
    *   <span data-ttu-id="f19d5-145">IT 관리자는 직원의 조직 구성 단위에 따라 권한을 부여할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f19d5-145">IT admin can grant permissions based on organizational unit for staff.</span></span> <span data-ttu-id="f19d5-146">**올바른 단위 수준과 연결되어 있는지 확인** 하여 필요한 사용 권한을 받을 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="f19d5-146">**Make sure staff members are associated with the correct unit level**, so they receive the permissions they need.</span></span> <span data-ttu-id="f19d5-147">예를 들어, 4개의 학교에 배정된 상담사는 4개 학교의 모든 성적을 봐야 합니다. 교장은 자신의 학교의 모든 수업을 봐야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f19d5-147">For example, a counselor assigned to four schools needs to see all the grades in those schools; a principal needs to see all the classes in their school.</span></span> 
    
*   <span data-ttu-id="f19d5-148">**역할은 중요합니다**.</span><span class="sxs-lookup"><span data-stu-id="f19d5-148">**The role is vital**.</span></span> <span data-ttu-id="f19d5-149">이 닫힌 목록이지만 [목록](/schooldatasync/sds-v2-csv-file-format#enumerated-values-enum-supported)의 역할을 업로드한 각 사용자의 실제 역할과 일치시키세요.</span><span class="sxs-lookup"><span data-stu-id="f19d5-149">Although this list is closed, try to match the role from [the list](/schooldatasync/sds-v2-csv-file-format#enumerated-values-enum-supported) to the real role of each user you upload.</span></span> <span data-ttu-id="f19d5-150">이렇게 하면 그에 따라 역할 기반 권한을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f19d5-150">This will enable you to assign role-based permissions accordingly.</span></span> <span data-ttu-id="f19d5-151">예를 들어 모든 교장이 학교의 수업을 볼 수 있거나 모든 교수가 교직원을 볼 수 있는 권한을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f19d5-151">For example, provide permissions for all principals to see the classes in their school, or for all professors to see their faculty.</span></span> 

#### <a name="organizations"></a><span data-ttu-id="f19d5-152">조직</span><span class="sxs-lookup"><span data-stu-id="f19d5-152">Organizations</span></span>

* <span data-ttu-id="f19d5-153">**조직의 실제 및 완전한 계층 구조가 반영** 되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="f19d5-153">Make sure to **reflect the real and full hierarchy of your organization**.</span></span> <span data-ttu-id="f19d5-154">경우에 따라 이 계층은 SIS에 반영되지 않습니다. 이 경우 CSV 파일 efore 동기화에 수동으로 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f19d5-154">In some cases, this hierarchy is not reflected in the SIS, in which case it needs to be added manually to the CSV file efore syncing.</span></span>

* <span data-ttu-id="f19d5-155">**모든 조직 트리 아래의 모든 조직 단위ㅇ에 학생이나 수업** 이 있는지 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="f19d5-155">Make sure that **all organization units down the organization tree include students or classes**.</span></span> <span data-ttu-id="f19d5-156">학생은 트리의 최하위 가지에 있는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="f19d5-156">We recommend that students are on the lowest branch of the tree.</span></span>

> [!NOTE]
> <span data-ttu-id="f19d5-157">SDS 배포에 대한 자세한 내용은 [SDS 계획](/schooldatasync/planning-school-data-sync)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f19d5-157">For more details about SDS deployment, visit [Planning SDS](/schooldatasync/planning-school-data-sync).</span></span>

## <a name="integrate-sis-data-using-sds"></a><span data-ttu-id="f19d5-158">SDS를 사용하여 SIS 데이터 통합</span><span class="sxs-lookup"><span data-stu-id="f19d5-158">Integrate SIS data using SDS</span></span>

<span data-ttu-id="f19d5-p109">SDS(학교 데이터 동기화)는 교육용 Office 365와 함께 제공됩니다. SDS는 교육 기관의 SIS(학생 정보 시스템)에서 데이터를 읽고 이를 Teams와 같은 Microsoft 응용 프로그램과 통합하여 온라인 교실과 사용자를 자동으로 만들 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="f19d5-p109">School Data Sync (SDS) is provided with Office 365 for Education. SDS reads the data from an educational institution's Student Information System (SIS) and integrates it with Microsoft applications like Teams to enable the automatic creation of online classrooms and users.</span></span>

<span data-ttu-id="f19d5-161">또한, SIS 데이터를 Insights와 동기화합니다.</span><span class="sxs-lookup"><span data-stu-id="f19d5-161">It also synchronizes the SIS data with Insights.</span></span>

<span data-ttu-id="f19d5-162">IT 관리자는 프로비전 전용, Insights 전용 또는 두 가지 모두에 대해서 SDS를 사용하도록 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f19d5-162">As an IT Admin, you can choose to use SDS for provisioning only, Insights only or for both.</span></span>

<span data-ttu-id="f19d5-163">SIS 정보를 Educations Insights와 동기화하려면 [Insights에 SDS를 배포하는 방법](/schooldatasync/how-to-deploy-sds-for-insights)의 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="f19d5-163">To Sync your SIS information with Educations Insights follow the instructions in [How to deploy SDS for Insights](/schooldatasync/how-to-deploy-sds-for-insights).</span></span>

### <a name="deploy-sds"></a><span data-ttu-id="f19d5-164">SDS 배포</span><span class="sxs-lookup"><span data-stu-id="f19d5-164">Deploy SDS</span></span>
<span data-ttu-id="f19d5-165">**SDS를 이미 사용하는 경우** [모범 사례](#best-practices)를 따르는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="f19d5-165">**If you already use SDS**, we recommend you follow our [best practices](#best-practices).</span></span> 

<span data-ttu-id="f19d5-166">**아직 SDS를 사용하지 않는 경우** 지금 [SDS를 배포](/schooldatasync/deploying-school-data-sync)해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f19d5-166">**If you don't use SDS yet**, you now need to [deploy it](/schooldatasync/deploying-school-data-sync).</span></span>

<span data-ttu-id="f19d5-167">배포 프로세스 중에 사용자 및 클래스를 Teams에 프로비전하는 데 SDS를 사용할 것인지 아니면 Insights에 사용자 및 조직 계층을 제공하는 데만 사용할 것인지 결정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f19d5-167">During the deployment process, you can decide if you want to use SDS for provisioning users and classes to Teams or to use it only to provide user and organizational hierarchy to Insights as well.</span></span>

> [!NOTE]
> <span data-ttu-id="f19d5-168">현재의 한 해의 반이 지났고 이미 수동으로 팀을 만든 경우 SDS를 사용하여 Insights에 사용자 및 조직 계층 데이터를 제공하고 내년에는 Teams에 대한 사용자 및 클래스를 프로비전하는 데 SDS를 사용하는 것을 고려하십시오.</span><span class="sxs-lookup"><span data-stu-id="f19d5-168">If it's the middle of the year and you already created teams manually, use SDS only to provide the user and organizational hierarchy data to Insights, and next year consider using SDS for provisioning users and classes for Teams as well.</span></span>

### <a name="verify-the-sync-process"></a><span data-ttu-id="f19d5-169">동기화 프로세스 확인</span><span class="sxs-lookup"><span data-stu-id="f19d5-169">Verify the sync process</span></span>
<span data-ttu-id="f19d5-170">동기화 상태 진행률을 확인하려면 [Insights용 SDS 데이터 상태 및 모니터링](/schooldatasync/sds-for-insights-data-health-and-monitoring)의 지침을 따르세요.</span><span class="sxs-lookup"><span data-stu-id="f19d5-170">To verify the sync status progress follow the instructions in [SDS for Insights Data Health and Monitoring](/schooldatasync/sds-for-insights-data-health-and-monitoring).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f19d5-171">문제가 발생하면 [고객 지원](https://aka.ms/edusupport)에서 도움을 드리겠습니다.</span><span class="sxs-lookup"><span data-stu-id="f19d5-171">If you run into any problems, [customer support](https://aka.ms/edusupport) is there to help you.</span></span>

## <a name="supported-grade-level-values"></a><span data-ttu-id="f19d5-172">지원되는 성적 수준 값</span><span class="sxs-lookup"><span data-stu-id="f19d5-172">Supported grade level values</span></span>

<span data-ttu-id="f19d5-173">SDS 파일에서 열거된 값으로 정의된 성적/학년 수준인 CSV 파일 내에서 선택된 값 집합만 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f19d5-173">In the SDS files, grade/year level defined as Enumerated values, which means you can only provide a selected set of values within the CSV file.</span></span> <span data-ttu-id="f19d5-174">지정한 값 외의 다른 값은 동기화 처리 중에 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="f19d5-174">Anything other than values specified will result in an error during sync processing.</span></span>

<span data-ttu-id="f19d5-175">아래 섹션에서는 사용자 파일의 지원되는 값을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="f19d5-175">The section below defines the supported values in the users file.</span></span>

### <a name="united-states--worldwide-grade-levels"></a><span data-ttu-id="f19d5-176">미국/전 세계 성적 수준</span><span class="sxs-lookup"><span data-stu-id="f19d5-176">United States / worldwide grade levels</span></span>
|<span data-ttu-id="f19d5-177">파일 값(성적 열)</span><span class="sxs-lookup"><span data-stu-id="f19d5-177">Value in file (Grade column)</span></span> | <span data-ttu-id="f19d5-178">Insights의 레이블</span><span class="sxs-lookup"><span data-stu-id="f19d5-178">Label in Insights</span></span>|
|:---|:---| 
|<span data-ttu-id="f19d5-179">IT</span><span class="sxs-lookup"><span data-stu-id="f19d5-179">IT</span></span>|<span data-ttu-id="f19d5-180">유아</span><span class="sxs-lookup"><span data-stu-id="f19d5-180">Infant</span></span>|
|<span data-ttu-id="f19d5-181">PR</span><span class="sxs-lookup"><span data-stu-id="f19d5-181">PR</span></span>|<span data-ttu-id="f19d5-182">미취학 아동</span><span class="sxs-lookup"><span data-stu-id="f19d5-182">Pre-school</span></span>|
|<span data-ttu-id="f19d5-183">PK</span><span class="sxs-lookup"><span data-stu-id="f19d5-183">PK</span></span>|<span data-ttu-id="f19d5-184">유아</span><span class="sxs-lookup"><span data-stu-id="f19d5-184">Pre-kindergarten</span></span>|
|<span data-ttu-id="f19d5-185">TK</span><span class="sxs-lookup"><span data-stu-id="f19d5-185">TK</span></span>|<span data-ttu-id="f19d5-186">유치원 준비 아동</span><span class="sxs-lookup"><span data-stu-id="f19d5-186">Transitional Kindergarten</span></span>|
|<span data-ttu-id="f19d5-187">KG</span><span class="sxs-lookup"><span data-stu-id="f19d5-187">KG</span></span>|<span data-ttu-id="f19d5-188">유치원생</span><span class="sxs-lookup"><span data-stu-id="f19d5-188">Kindergarten</span></span>|
|<span data-ttu-id="f19d5-189">01 또는 1</span><span class="sxs-lookup"><span data-stu-id="f19d5-189">01 or 1</span></span>|<span data-ttu-id="f19d5-190">1학년</span><span class="sxs-lookup"><span data-stu-id="f19d5-190">First grade</span></span>|
|<span data-ttu-id="f19d5-191">02 또는 2</span><span class="sxs-lookup"><span data-stu-id="f19d5-191">02 or 2</span></span>|<span data-ttu-id="f19d5-192">2학년</span><span class="sxs-lookup"><span data-stu-id="f19d5-192">Second grade</span></span>|
|<span data-ttu-id="f19d5-193">03 또는 3</span><span class="sxs-lookup"><span data-stu-id="f19d5-193">03 or 3</span></span>|<span data-ttu-id="f19d5-194">3학년</span><span class="sxs-lookup"><span data-stu-id="f19d5-194">Third grade</span></span>|
|<span data-ttu-id="f19d5-195">04 또는 4</span><span class="sxs-lookup"><span data-stu-id="f19d5-195">04 or 4</span></span>|<span data-ttu-id="f19d5-196">4학년</span><span class="sxs-lookup"><span data-stu-id="f19d5-196">Fourth grade</span></span>|
|<span data-ttu-id="f19d5-197">05 또는 5</span><span class="sxs-lookup"><span data-stu-id="f19d5-197">05 or 5</span></span>|<span data-ttu-id="f19d5-198">5학년</span><span class="sxs-lookup"><span data-stu-id="f19d5-198">Fifth grade</span></span>|
|<span data-ttu-id="f19d5-199">06 또는 6</span><span class="sxs-lookup"><span data-stu-id="f19d5-199">06 or 6</span></span>|<span data-ttu-id="f19d5-200">6학년</span><span class="sxs-lookup"><span data-stu-id="f19d5-200">Sixth grade</span></span>|
|<span data-ttu-id="f19d5-201">07 또는 7</span><span class="sxs-lookup"><span data-stu-id="f19d5-201">07 or 7</span></span>|<span data-ttu-id="f19d5-202">중학교 1학년</span><span class="sxs-lookup"><span data-stu-id="f19d5-202">Seventh grade</span></span>|
|<span data-ttu-id="f19d5-203">08 또는 8</span><span class="sxs-lookup"><span data-stu-id="f19d5-203">08 or 8</span></span>|<span data-ttu-id="f19d5-204">중학교 2학년</span><span class="sxs-lookup"><span data-stu-id="f19d5-204">Eighth grade</span></span>|
|<span data-ttu-id="f19d5-205">09 또는 9</span><span class="sxs-lookup"><span data-stu-id="f19d5-205">09 or 9</span></span>|<span data-ttu-id="f19d5-206">중학교 3학년</span><span class="sxs-lookup"><span data-stu-id="f19d5-206">Ninth grade</span></span>|
|<span data-ttu-id="f19d5-207">10</span><span class="sxs-lookup"><span data-stu-id="f19d5-207">10</span></span>|<span data-ttu-id="f19d5-208">고등학교 1학년</span><span class="sxs-lookup"><span data-stu-id="f19d5-208">Tenth grade</span></span>|
|<span data-ttu-id="f19d5-209">11</span><span class="sxs-lookup"><span data-stu-id="f19d5-209">11</span></span>|<span data-ttu-id="f19d5-210">고등학교 2학년</span><span class="sxs-lookup"><span data-stu-id="f19d5-210">Eleventh grade</span></span>|
|<span data-ttu-id="f19d5-211">12</span><span class="sxs-lookup"><span data-stu-id="f19d5-211">12</span></span>|<span data-ttu-id="f19d5-212">고등학교 3학년</span><span class="sxs-lookup"><span data-stu-id="f19d5-212">Twelfth grade</span></span>|
|<span data-ttu-id="f19d5-213">PS</span><span class="sxs-lookup"><span data-stu-id="f19d5-213">PS</span></span>|<span data-ttu-id="f19d5-214">고등학교 졸업 후 교육</span><span class="sxs-lookup"><span data-stu-id="f19d5-214">Postsecondary</span></span>|
|<span data-ttu-id="f19d5-215">PS1</span><span class="sxs-lookup"><span data-stu-id="f19d5-215">PS1</span></span>|<span data-ttu-id="f19d5-216">고등학교 졸업 후 교육 1학년</span><span class="sxs-lookup"><span data-stu-id="f19d5-216">Postsecondary freshman</span></span>|
|<span data-ttu-id="f19d5-217">PS2</span><span class="sxs-lookup"><span data-stu-id="f19d5-217">PS2</span></span>|<span data-ttu-id="f19d5-218">고등학교 졸업 후 교육 2학년</span><span class="sxs-lookup"><span data-stu-id="f19d5-218">Postsecondary sophomore</span></span>|
|<span data-ttu-id="f19d5-219">PS3</span><span class="sxs-lookup"><span data-stu-id="f19d5-219">PS3</span></span>|<span data-ttu-id="f19d5-220">고등학교 졸업 후 교육 3학년</span><span class="sxs-lookup"><span data-stu-id="f19d5-220">Postsecondary junior</span></span>|
|<span data-ttu-id="f19d5-221">PS4</span><span class="sxs-lookup"><span data-stu-id="f19d5-221">PS4</span></span>|<span data-ttu-id="f19d5-222">고등학교 졸업 후 교육 4학년</span><span class="sxs-lookup"><span data-stu-id="f19d5-222">Postsecondary senior</span></span>|
|<span data-ttu-id="f19d5-223">학부생</span><span class="sxs-lookup"><span data-stu-id="f19d5-223">undergraduate</span></span>|<span data-ttu-id="f19d5-224">학부생</span><span class="sxs-lookup"><span data-stu-id="f19d5-224">Undergraduate</span></span>|
|<span data-ttu-id="f19d5-225">졸업</span><span class="sxs-lookup"><span data-stu-id="f19d5-225">graduate</span></span>|<span data-ttu-id="f19d5-226">졸업</span><span class="sxs-lookup"><span data-stu-id="f19d5-226">Graduate</span></span>|
|<span data-ttu-id="f19d5-227">대학원</span><span class="sxs-lookup"><span data-stu-id="f19d5-227">postgraduate</span></span>|<span data-ttu-id="f19d5-228">대학원(연구를 중점으로 공부하는 학부생)</span><span class="sxs-lookup"><span data-stu-id="f19d5-228">Postgraduate (graduate with an emphasis on research)</span></span>|
|<span data-ttu-id="f19d5-229">동창생</span><span class="sxs-lookup"><span data-stu-id="f19d5-229">alumni</span></span>|<span data-ttu-id="f19d5-230">동창생</span><span class="sxs-lookup"><span data-stu-id="f19d5-230">Alumni</span></span>|
|<span data-ttu-id="f19d5-231">평생 교육</span><span class="sxs-lookup"><span data-stu-id="f19d5-231">adultEducation</span></span>|<span data-ttu-id="f19d5-232">평생 교육</span><span class="sxs-lookup"><span data-stu-id="f19d5-232">Adult Education</span></span>|
|<span data-ttu-id="f19d5-233">UG</span><span class="sxs-lookup"><span data-stu-id="f19d5-233">UG</span></span>|<span data-ttu-id="f19d5-234">성적이 매겨지지 않음</span><span class="sxs-lookup"><span data-stu-id="f19d5-234">Ungraded</span></span>|
|<span data-ttu-id="f19d5-235">기타</span><span class="sxs-lookup"><span data-stu-id="f19d5-235">Other</span></span>|<span data-ttu-id="f19d5-236">기타</span><span class="sxs-lookup"><span data-stu-id="f19d5-236">Other</span></span>|

### <a name="united-kingdom-year-groups"></a><span data-ttu-id="f19d5-237">영국 연도 그룹</span><span class="sxs-lookup"><span data-stu-id="f19d5-237">United Kingdom year groups</span></span>
|<span data-ttu-id="f19d5-238">파일 값(성적 열)</span><span class="sxs-lookup"><span data-stu-id="f19d5-238">Value in file (Grade column)</span></span> | <span data-ttu-id="f19d5-239">Insights의 레이블</span><span class="sxs-lookup"><span data-stu-id="f19d5-239">Label in Insights</span></span>|
|:---|:---| 
|<span data-ttu-id="f19d5-240">IT</span><span class="sxs-lookup"><span data-stu-id="f19d5-240">IT</span></span>|<span data-ttu-id="f19d5-241">보육</span><span class="sxs-lookup"><span data-stu-id="f19d5-241">Nursery</span></span>|
|<span data-ttu-id="f19d5-242">PR</span><span class="sxs-lookup"><span data-stu-id="f19d5-242">PR</span></span>|<span data-ttu-id="f19d5-243">미취학 아동</span><span class="sxs-lookup"><span data-stu-id="f19d5-243">Pre-school</span></span>|
|<span data-ttu-id="f19d5-244">PK</span><span class="sxs-lookup"><span data-stu-id="f19d5-244">PK</span></span>|<span data-ttu-id="f19d5-245">리셉션</span><span class="sxs-lookup"><span data-stu-id="f19d5-245">Reception</span></span>|
|<span data-ttu-id="f19d5-246">01 또는 1</span><span class="sxs-lookup"><span data-stu-id="f19d5-246">01 or 1</span></span>|<span data-ttu-id="f19d5-247">1년</span><span class="sxs-lookup"><span data-stu-id="f19d5-247">Year 1</span></span>|
|<span data-ttu-id="f19d5-248">02 또는 2</span><span class="sxs-lookup"><span data-stu-id="f19d5-248">02 or 2</span></span>|<span data-ttu-id="f19d5-249">2년</span><span class="sxs-lookup"><span data-stu-id="f19d5-249">Year 2</span></span>|
|<span data-ttu-id="f19d5-250">03 또는 3</span><span class="sxs-lookup"><span data-stu-id="f19d5-250">03 or 3</span></span>|<span data-ttu-id="f19d5-251">3년</span><span class="sxs-lookup"><span data-stu-id="f19d5-251">Year 3</span></span>|
|<span data-ttu-id="f19d5-252">04 또는 4</span><span class="sxs-lookup"><span data-stu-id="f19d5-252">04 or 4</span></span>|<span data-ttu-id="f19d5-253">4년</span><span class="sxs-lookup"><span data-stu-id="f19d5-253">Year 4</span></span>|
|<span data-ttu-id="f19d5-254">05 또는 5</span><span class="sxs-lookup"><span data-stu-id="f19d5-254">05 or 5</span></span>|<span data-ttu-id="f19d5-255">5년</span><span class="sxs-lookup"><span data-stu-id="f19d5-255">Year 5</span></span>|
|<span data-ttu-id="f19d5-256">06 또는 6</span><span class="sxs-lookup"><span data-stu-id="f19d5-256">06 or 6</span></span>|<span data-ttu-id="f19d5-257">6년</span><span class="sxs-lookup"><span data-stu-id="f19d5-257">Year 6</span></span>|
|<span data-ttu-id="f19d5-258">07 또는 7</span><span class="sxs-lookup"><span data-stu-id="f19d5-258">07 or 7</span></span>|<span data-ttu-id="f19d5-259">7년</span><span class="sxs-lookup"><span data-stu-id="f19d5-259">Year 7</span></span>|
|<span data-ttu-id="f19d5-260">08 또는 8</span><span class="sxs-lookup"><span data-stu-id="f19d5-260">08 or 8</span></span>|<span data-ttu-id="f19d5-261">8년</span><span class="sxs-lookup"><span data-stu-id="f19d5-261">Year 8</span></span>|
|<span data-ttu-id="f19d5-262">09 또는 9</span><span class="sxs-lookup"><span data-stu-id="f19d5-262">09 or 9</span></span>|<span data-ttu-id="f19d5-263">9년</span><span class="sxs-lookup"><span data-stu-id="f19d5-263">Year 9</span></span>|
|<span data-ttu-id="f19d5-264">10</span><span class="sxs-lookup"><span data-stu-id="f19d5-264">10</span></span>|<span data-ttu-id="f19d5-265">10년</span><span class="sxs-lookup"><span data-stu-id="f19d5-265">Year 10</span></span>|
|<span data-ttu-id="f19d5-266">11</span><span class="sxs-lookup"><span data-stu-id="f19d5-266">11</span></span>|<span data-ttu-id="f19d5-267">11년</span><span class="sxs-lookup"><span data-stu-id="f19d5-267">Year 11</span></span>|
|<span data-ttu-id="f19d5-268">12</span><span class="sxs-lookup"><span data-stu-id="f19d5-268">12</span></span>|<span data-ttu-id="f19d5-269">12년</span><span class="sxs-lookup"><span data-stu-id="f19d5-269">Year 12</span></span>|
|<span data-ttu-id="f19d5-270">13</span><span class="sxs-lookup"><span data-stu-id="f19d5-270">13</span></span>|<span data-ttu-id="f19d5-271">13년</span><span class="sxs-lookup"><span data-stu-id="f19d5-271">Year 13</span></span>|
|<span data-ttu-id="f19d5-272">PS</span><span class="sxs-lookup"><span data-stu-id="f19d5-272">PS</span></span>|<span data-ttu-id="f19d5-273">고등학교 졸업 후 교육</span><span class="sxs-lookup"><span data-stu-id="f19d5-273">Postsecondary</span></span>|
|<span data-ttu-id="f19d5-274">PS1</span><span class="sxs-lookup"><span data-stu-id="f19d5-274">PS1</span></span>|<span data-ttu-id="f19d5-275">고등학교 졸업 후 교육 1년</span><span class="sxs-lookup"><span data-stu-id="f19d5-275">Postsecondary Year 1</span></span>|
|<span data-ttu-id="f19d5-276">PS2</span><span class="sxs-lookup"><span data-stu-id="f19d5-276">PS2</span></span>|<span data-ttu-id="f19d5-277">고등학교 졸업 후 교육 2년</span><span class="sxs-lookup"><span data-stu-id="f19d5-277">Postsecondary Year 2</span></span>|
|<span data-ttu-id="f19d5-278">PS3</span><span class="sxs-lookup"><span data-stu-id="f19d5-278">PS3</span></span>|<span data-ttu-id="f19d5-279">고등학교 졸업 후 교육 3년</span><span class="sxs-lookup"><span data-stu-id="f19d5-279">Postsecondary Year 3</span></span>|
|<span data-ttu-id="f19d5-280">PS4</span><span class="sxs-lookup"><span data-stu-id="f19d5-280">PS4</span></span>|<span data-ttu-id="f19d5-281">고등학교 졸업 후 교육 4년</span><span class="sxs-lookup"><span data-stu-id="f19d5-281">Postsecondary Year 4</span></span>|
|<span data-ttu-id="f19d5-282">학부생</span><span class="sxs-lookup"><span data-stu-id="f19d5-282">undergraduate</span></span>|<span data-ttu-id="f19d5-283">학부생</span><span class="sxs-lookup"><span data-stu-id="f19d5-283">Undergraduate</span></span>|
|<span data-ttu-id="f19d5-284">졸업</span><span class="sxs-lookup"><span data-stu-id="f19d5-284">graduate</span></span>|<span data-ttu-id="f19d5-285">졸업</span><span class="sxs-lookup"><span data-stu-id="f19d5-285">Graduate</span></span>|
|<span data-ttu-id="f19d5-286">대학원</span><span class="sxs-lookup"><span data-stu-id="f19d5-286">postgraduate</span></span>|<span data-ttu-id="f19d5-287">대학원(연구를 중점으로 공부하는 학부생)</span><span class="sxs-lookup"><span data-stu-id="f19d5-287">Postgraduate (graduate with an emphasis on research)</span></span>|
|<span data-ttu-id="f19d5-288">동창생</span><span class="sxs-lookup"><span data-stu-id="f19d5-288">alumni</span></span>|<span data-ttu-id="f19d5-289">동창생</span><span class="sxs-lookup"><span data-stu-id="f19d5-289">Alumni</span></span>|
|<span data-ttu-id="f19d5-290">평생 교육</span><span class="sxs-lookup"><span data-stu-id="f19d5-290">adultEducation</span></span>|<span data-ttu-id="f19d5-291">평생 교육</span><span class="sxs-lookup"><span data-stu-id="f19d5-291">Adult Education</span></span>|
|<span data-ttu-id="f19d5-292">UG</span><span class="sxs-lookup"><span data-stu-id="f19d5-292">UG</span></span>|<span data-ttu-id="f19d5-293">성적이 매겨지지 않음</span><span class="sxs-lookup"><span data-stu-id="f19d5-293">Ungraded</span></span>|
|<span data-ttu-id="f19d5-294">기타</span><span class="sxs-lookup"><span data-stu-id="f19d5-294">Other</span></span>|<span data-ttu-id="f19d5-295">기타</span><span class="sxs-lookup"><span data-stu-id="f19d5-295">Other</span></span>|

