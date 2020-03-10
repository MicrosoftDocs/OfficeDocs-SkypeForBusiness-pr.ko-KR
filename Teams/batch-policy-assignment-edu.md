---
title: 학교에서 대규모 사용자 집합에 정책 할당
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: saragava,karsmith
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: 일괄 처리 정책 할당을 사용 하 여 원격 학교 (teleschool, tele) 용도의 교육 기관에 대규모 사용자 집합에 정책을 할당 하는 방법에 대해 알아봅니다.
f1keywords: ''
ms.openlocfilehash: e95c6b035298ce583a0ad34a030f2086b7c12ff3
ms.sourcegitcommit: 33bec766519397f898518a999d358657a413924c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/10/2020
ms.locfileid: "42583358"
---
# <a name="assign-policies-to-large-sets-of-users-in-your-school"></a><span data-ttu-id="69cf5-103">학교에서 대규모 사용자 집합에 정책 할당</span><span class="sxs-lookup"><span data-stu-id="69cf5-103">Assign policies to large sets of users in your school</span></span>

<span data-ttu-id="69cf5-104">학생 및 교사에 게 Microsoft 팀의 다양 한 기능에 대 한 액세스 권한이 필요 한가요?</span><span class="sxs-lookup"><span data-stu-id="69cf5-104">Do you need to give your students and educators access to different features in Microsoft Teams?</span></span> <span data-ttu-id="69cf5-105">라이선스 유형을 기준으로 조직의 사용자를 빠르게 식별 한 다음 적절 한 정책을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69cf5-105">You can quickly identify the users in your organization by license type and then assign them the appropriate policy.</span></span> <span data-ttu-id="69cf5-106">이 자습서에서는 [일괄 처리 정책 할당](assign-policies.md#assign-a-policy-to-a-batch-of-users) 을 사용 하 여 사용자에 게 대량으로 모임 정책을 할당 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="69cf5-106">This tutorial shows you how to use [batch policy assignment](assign-policies.md#assign-a-policy-to-a-batch-of-users) to assign a meeting policy to users in bulk.</span></span>

<span data-ttu-id="69cf5-107">사용자 지정 정책을 만들고 할당 하지 않는 한 팀에서 팀 정책 유형의 전역 (조직 차원의 기본) 정책을 자동으로 얻을 수 있다는 점에 유의 하세요.</span><span class="sxs-lookup"><span data-stu-id="69cf5-107">Remember that in Teams, users automatically get the Global (Org-wide default) policy for a Teams policy type unless you create and assign a custom policy.</span></span> <span data-ttu-id="69cf5-108">학생 집단은 일반적으로 가장 큰 사용자 집합 이므로 가장 제한적인 설정을 받을 수 있으므로 다음을 수행 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="69cf5-108">Because the student population is often the largest set of users and they often receive the most restrictive settings, we recommend that you do the following:</span></span>

- <span data-ttu-id="69cf5-109">전역 (조직 전체 기본값) 정책을 편집 하 고 적용 하 여 학생에 대 한 접근 권한 제한</span><span class="sxs-lookup"><span data-stu-id="69cf5-109">Edit and apply the Global (Org-wide default) policy to restrict capabilities for students.</span></span> 
- <span data-ttu-id="69cf5-110">개인 채팅 및 모임 예약과 같은 핵심 기능을 허용 하는 사용자 지정 정책을 만들어 교직원 및 교육자에 게 정책을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="69cf5-110">Create a custom policy that allows core capabilities such as private chat and meeting scheduling and assign the policy to your staff and educators.</span></span>

<span data-ttu-id="69cf5-111">사용자 지정 정책을 만들어 교직원과 교육자에 게 배정할 때까지 해당 학교의 모든 사용자에 게 전역 정책이 적용 된다는 점을 기억 하세요.</span><span class="sxs-lookup"><span data-stu-id="69cf5-111">Keep in mind that the Global policy will apply to all users in your school until you create a custom policy and assign it to your staff and educators.</span></span>

<span data-ttu-id="69cf5-112">이 자습서에서 학생 들은 전역 모임 정책을 받게 되며 PowerShell을 사용 하 여 EducatorMeetingPolicy 이라는 사용자 지정 모임 정책을 직원 및 교사에 게 대량으로 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="69cf5-112">In this tutorial, students will get the Global meeting policy and we use PowerShell to assign a custom meeting policy named EducatorMeetingPolicy to staff and educators in bulk.</span></span> <span data-ttu-id="69cf5-113">학생에 대 한 모임 설정을 조정 하 고 교직원 및 교사를 위한 모임 환경을 정의 하는 사용자 지정 정책을 만드는 전역 정책을 편집 했다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="69cf5-113">We assume that you've edited the Global policy to tailor meeting settings for students and created a custom policy that defines the meeting experience for staff and educators.</span></span>

![팀 관리 센터의 모임 정책 페이지 스크린샷](media/edu-batch-policy-assignment.png)

<span data-ttu-id="69cf5-115">직원 및 강사에 게 사용자 지정 모임 정책을 대량으로 할당 하려면 다음 단계를 따르세요.</span><span class="sxs-lookup"><span data-stu-id="69cf5-115">Follow these steps to assign a custom meeting policy to staff and educators in bulk.</span></span>

## <a name="connect-to-the-azure-ad-powershell-for-graph-module-and-the-teams-powershell-module"></a><span data-ttu-id="69cf5-116">Graph 모듈 및 팀 PowerShell 모듈에 대 한 Azure AD PowerShell에 연결</span><span class="sxs-lookup"><span data-stu-id="69cf5-116">Connect to the Azure AD PowerShell for Graph module and the Teams PowerShell module</span></span>

<span data-ttu-id="69cf5-117">이 문서의 단계를 수행 하기 전에 Graph 모듈에 대 한 Azure AD PowerShell을 설치 하 고 연결 해야 합니다 (할당 된 라이선스의 사용자 식별) 및 Microsoft 팀 PowerShell 모듈의 시험판 버전 (정책 지정 해당 사용자).</span><span class="sxs-lookup"><span data-stu-id="69cf5-117">Before you perform the steps in this article, you’ll need to install and connect to the Azure AD PowerShell for Graph module (to identify users by their assigned licenses) and the pre-release version of the Microsoft Teams PowerShell module (to assign the policies to those users).</span></span>

### <a name="install-and-connect-to-the-azure-ad-powershell-for-graph-module"></a><span data-ttu-id="69cf5-118">Graph 모듈에 대 한 Azure AD PowerShell 설치 및 연결</span><span class="sxs-lookup"><span data-stu-id="69cf5-118">Install and connect to the Azure AD PowerShell for Graph module</span></span>

<span data-ttu-id="69cf5-119">관리자 권한으로 windows PowerShell 명령 프롬프트를 열고 (관리자로 Windows PowerShell 실행) 다음을 실행 하 여 Graph 모듈에 대 한 Azure Active Directory PowerShell을 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="69cf5-119">Open an elevated Windows PowerShell command prompt (run Windows PowerShell as an administrator), and then run the following to install the Azure Active Directory PowerShell for Graph module.</span></span>

```powershell
Install-Module AzureAD
```

<span data-ttu-id="69cf5-120">Azure AD에 연결 하려면 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="69cf5-120">Run the following to connect to Azure AD.</span></span>

```powershell
Connect-AzureAD
```

<span data-ttu-id="69cf5-121">메시지가 표시 되 면 관리자 자격 증명을 사용 하 여 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="69cf5-121">When you're prompted, sign in using your admin credentials.</span></span>

<span data-ttu-id="69cf5-122">자세한 내용은 [Graph 용 Azure Active Directory PowerShell 모듈을 사용 하 여 연결](https://docs.microsoft.com/eoffice365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="69cf5-122">To learn more, see [Connect with the Azure Active Directory PowerShell for Graph module](https://docs.microsoft.com/eoffice365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>

### <a name="install-and-connect-to-the-pre-release-version-of-the-teams-powershell-module"></a><span data-ttu-id="69cf5-123">팀 PowerShell 모듈의 시험판 버전 설치 및 연결</span><span class="sxs-lookup"><span data-stu-id="69cf5-123">Install and connect to the pre-release version of the Teams PowerShell module</span></span>

<span data-ttu-id="69cf5-124">필요한 cmdlet은 팀 PowerShell 모듈의 시험판 버전에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69cf5-124">The cmdlets you'll need are in the pre-release version of the Teams PowerShell module.</span></span> <span data-ttu-id="69cf5-125">[Microsoft 팀 powershell 모듈 설치 및 연결](assign-policies.md#install-and-connect-to-the-microsoft-teams-powershell-module) 의 단계를 따라 먼저 일반적으로 사용 가능한 팀 powershell 모듈 (설치 되어 있는 경우)을 제거한 다음 PowerShell 테스트 갤러리에서 해당 모듈의 최신 시험판 버전을 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="69cf5-125">Follow the steps in [Install and connect to the Microsoft Teams PowerShell module](assign-policies.md#install-and-connect-to-the-microsoft-teams-powershell-module) to first uninstall the Generally Available version of the Teams PowerShell module (if it's installed), and then install the latest pre-release version of the module from the PowerShell Test Gallery.</span></span>

<span data-ttu-id="69cf5-126">다음을 실행 하 여 팀에 연결 하 고 세션을 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="69cf5-126">Run the following to connect to Teams and start a session.</span></span>

```powershell
Connect-MicrosoftTeams
```
<span data-ttu-id="69cf5-127">메시지가 표시 되 면 Azure AD에 연결 하는 데 사용한 것과 동일한 관리자 자격 증명을 사용 하 여 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="69cf5-127">When you're prompted, sign in using the same admin credentials you used to connect to Azure AD.</span></span>

## <a name="identify-your-users"></a><span data-ttu-id="69cf5-128">사용자 식별</span><span class="sxs-lookup"><span data-stu-id="69cf5-128">Identify your users</span></span>

<span data-ttu-id="69cf5-129">먼저 다음을 실행 하 여 라이선스 유형별로 교직원 및 교사를 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="69cf5-129">First, run the following to identify your staff and educators by license type.</span></span> <span data-ttu-id="69cf5-130">조직에서 사용 중인 Sku를 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69cf5-130">This tells you what SKUs are in use in your organization.</span></span> <span data-ttu-id="69cf5-131">그런 다음 교직원 SKU가 지정 된 교직원 및 교사를 식별할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69cf5-131">You can then identify staff and educators that have a Faculty SKU assigned.</span></span>

```powershell
Get-AzureADSubscribedSku
```

```powershell
$skus = Get-AzureADSubscribedSku
```

<span data-ttu-id="69cf5-132">반환 되는 결과:</span><span class="sxs-lookup"><span data-stu-id="69cf5-132">Which returns:</span></span>

```
ObjectId                                                                  SkuPartNumber      SkuId
--------                                                                  -------------      -----
ee1a846c-79e9-4bc3-9189-011ca89be890_e97c048c-37a4-45fb-ab50-022fbf07a370 M365EDU_A5_FACULTY e97c048c-37a4-45fb-ab50-922fbf07a370
ee1a846c-79e9-4bc3-9189-011ca89be890_46c119d4-0379-4a9d-85e4-97c66d3f909e M365EDU_A5_STUDENT 46c119d4-0379-4a9d-85e4-97c66d3f909e
```

<span data-ttu-id="69cf5-133">이 예제에서는 교직원 라이선스 SkuId "e97c048c-37a4-45fb-ab50-922fbf07a370" 라는 것을 출력에 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="69cf5-133">In this example, the output shows that the Faculty license SkuId is “e97c048c-37a4-45fb-ab50-922fbf07a370”.</span></span>

> [!NOTE]
> <span data-ttu-id="69cf5-134">교육 Sku 및 SKU Id 목록을 보려면 [교육 sku 참조](sku-reference-edu.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="69cf5-134">To see a list of Education SKUs and SKU IDs, see [Education SKU reference](sku-reference-edu.md).</span></span>

<span data-ttu-id="69cf5-135">다음으로, 다음을 실행 하 여이 라이선스가 있는 사용자를 식별 하 고 함께 수집 합니다.</span><span class="sxs-lookup"><span data-stu-id="69cf5-135">Next, we run the following to identify the users that have this license and collect them all together.</span></span>

```powershell
$faculty = Get-AzureADUser -All $true | Where-Object (($_.assignedLicenses).SkuId -contains “e97c048c-37a4-45fb-ab50-922fbf07a370”)
```

## <a name="assign-a-policy-in-bulk"></a><span data-ttu-id="69cf5-136">대량으로 정책 할당</span><span class="sxs-lookup"><span data-stu-id="69cf5-136">Assign a policy in bulk</span></span>

<span data-ttu-id="69cf5-137">이제 사용자에 게 적절 한 정책을 대량으로 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="69cf5-137">Now, we assign the appropriate policies to users in bulk.</span></span> <span data-ttu-id="69cf5-138">정책을 할당 하거나 업데이트 하는 데 사용할 수 있는 최대 사용자 수는 한 번에 2만입니다.</span><span class="sxs-lookup"><span data-stu-id="69cf5-138">The maximum number of users for which you can assign or update policies is 20,000 at a time.</span></span> <span data-ttu-id="69cf5-139">예를 들어 2만 개 이상의 직원과 교육자가 있는 경우 여러 일괄 처리를 제출 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="69cf5-139">For example, if you have more than 20,000 staff and educators, you’ll need to submit multiple batches.</span></span>

<span data-ttu-id="69cf5-140">다음을 실행 하 여 EducatorMeetingPolicy 이라는 모임 정책을 교직원 및 교육자에 게 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="69cf5-140">Run the following to assign the meeting policy named EducatorMeetingPolicy to your staff and educators.</span></span>

```powershell
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMeetingPolicy -PolicyName EducatorMeetingPolicy -Identity $faculty.ObjectId
```

> [!NOTE]
> <span data-ttu-id="69cf5-141">TeamsMessagingPolicy와 같이 대량으로 다른 정책 유형을 할당 하려면 할당할 정책 및 ```PolicyType``` ```PolicyName``` 정책 이름으로 변경 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="69cf5-141">To assign a different policy type in bulk, like TeamsMessagingPolicy, you’ll need to change ```PolicyType``` to the policy that you're assigning and ```PolicyName``` to the policy name.</span></span>

## <a name="get-the-status-of-a-bulk-assignment"></a><span data-ttu-id="69cf5-142">대량 배정 상태 가져오기</span><span class="sxs-lookup"><span data-stu-id="69cf5-142">Get the status of a bulk assignment</span></span>

<span data-ttu-id="69cf5-143">각 대량 과제는 정책 할당의 진행률을 추적 하거나 발생할 수 있는 오류를 식별 하는 데 사용할 수 있는 작업 ID를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="69cf5-143">Each bulk assignment returns an operation ID, which you can use to track the progress of the policy assignments or identify any failures that might occur.</span></span> <span data-ttu-id="69cf5-144">예를 들어 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="69cf5-144">For example, run the following:</span></span>

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId 3964004e-caa8-4eb4-b0d2-7dd2c8173c8c | fl
```

<span data-ttu-id="69cf5-145">일괄 작업에서 각 사용자의 할당 상태를 보려면 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="69cf5-145">To view the assignment status of each user in the batch operation, run the following.</span></span> <span data-ttu-id="69cf5-146">각 사용자에 대 한 세부 정보 ```UserState``` 는 속성에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69cf5-146">Details of each user are in the ```UserState``` property.</span></span>

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId 3964004e-caa8-4eb4-b0d2-7dd2c8173c8c | Select -ExpandProperty UserState
```

## <a name="assign-a-policy-in-bulk-if-you-have-more-than-20000-users"></a><span data-ttu-id="69cf5-147">2만 명 이상의 사용자가 있는 경우 대량으로 정책 할당</span><span class="sxs-lookup"><span data-stu-id="69cf5-147">Assign a policy in bulk if you have more than 20,000 users</span></span>

<span data-ttu-id="69cf5-148">먼저 다음을 실행 하 여 보유 하 고 있는 교직원 및 강사 수를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="69cf5-148">First, run the following to see how many staff and educators you have:</span></span>

```powershell
$faculty.count
```

<span data-ttu-id="69cf5-149">사용자 Id의 전체 목록을 제공 하는 대신 다음을 실행 하 여 첫 번째 2만을 지정 하 고 다음 2만 등</span><span class="sxs-lookup"><span data-stu-id="69cf5-149">Instead of providing the whole list of user IDs, run the following to specify the first 20,000, and then the next 20,000, and so on.</span></span>

```powershell
Assign-CsPolicy -PolicyType TeamsMeetingPolicy -PolicyName EducatorMeetingPolicy -Identities $faculty[0..19999].ObjectId
```

<span data-ttu-id="69cf5-150">전체 사용자 목록에 도달할 때까지 사용자 Id의 범위를 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69cf5-150">You can change the range of user IDs until you reach the full list of users.</span></span> <span data-ttu-id="69cf5-151">예를 들어 첫 ```$faculty[0..19999``` 번째 일괄 처리를 입력 하 ```$faculty[20000..39999``` 고 두 번째 일괄 처리에 ```$faculty[40000..59999``` 대해, 세 번째 일괄 처리에 대해 enter 키를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="69cf5-151">For example, enter ```$faculty[0..19999``` for the first batch, use ```$faculty[20000..39999``` for the second batch, enter ```$faculty[40000..59999``` for the third batch, and so on.</span></span>

## <a name="get-the-policies-assigned-to-a-user"></a><span data-ttu-id="69cf5-152">사용자에 게 할당 된 정책 가져오기</span><span class="sxs-lookup"><span data-stu-id="69cf5-152">Get the policies assigned to a user</span></span>

<span data-ttu-id="69cf5-153">특정 사용자에 게 할당 된 모든 정책을 보려면 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="69cf5-153">Run the following to see all the policies that are assigned to a specific user.</span></span> <span data-ttu-id="69cf5-154">다음 예에서는 hannah@contoso.com에 할당 된 정책을 가져오는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="69cf5-154">The following example shows you how to get the policies that are assigned to hannah@contoso.com.</span></span>

```powershell
Get-CsUserPolicyAssignment -Identity hannah@contoso.com
```

## <a name="faq"></a><span data-ttu-id="69cf5-155">FAQ</span><span class="sxs-lookup"><span data-stu-id="69cf5-155">FAQ</span></span>

<span data-ttu-id="69cf5-156">**학생, 교직원 및 교육자 인 모든 사용자가 라이선스를 자동으로 할당 해야 합니다. 어떻게 하면 되나요?**</span><span class="sxs-lookup"><span data-stu-id="69cf5-156">**I want to make sure that all users that are students, staff, and educators automatically get licenses assigned. How can I do that?**</span></span>

<span data-ttu-id="69cf5-157">팀 제품 팀은 보안 그룹에 정책 지정을 지원 하기 위해 작업을 수행 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69cf5-157">The Teams product team is doing work to support assigning policies to security groups.</span></span> <span data-ttu-id="69cf5-158">이때 학생 및 교사를 위한 그룹을 만든 다음 해당 그룹에 대 한 적절 한 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69cf5-158">At that time, you’ll be able to create groups for your students and teachers, and then the appropriate policies to those groups.</span></span> <span data-ttu-id="69cf5-159">이 자습서를 사용 하 여 할당 한 정책 등의 명시적인 사용자 할당이 그룹에서 상속 된 정책 보다 우선 한다는 점에 유의 하세요.</span><span class="sxs-lookup"><span data-stu-id="69cf5-159">Note that explicit user assignments (such as the policies that you’ve assigned using this tutorial) will override policies inherited from a group.</span></span> <span data-ttu-id="69cf5-160">이 기능이 지원 되는 경우 그룹에 정책 할당을 사용 하 고 상속 된 그룹 정책을 얻을 수 있도록 사용자를 업데이트 하는 방법에 대 한 자세한 지침을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="69cf5-160">When this feature is supported, we’ll provide more instructions on how to use policy assignment to groups and update your users to ensure they get the inherited group policies.</span></span>

<span data-ttu-id="69cf5-161">**팀에 대 한 PowerShell에 익숙하지 않습니다. 자세한 내용은 어디에서 확인할 수 있나요?**</span><span class="sxs-lookup"><span data-stu-id="69cf5-161">**I’m not familiar with PowerShell for Teams. Where can I learn more?**</span></span>

<span data-ttu-id="69cf5-162">[팀 Powershell 개요](teams-powershell-overview.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="69cf5-162">See [Teams Powershell overview](teams-powershell-overview.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="69cf5-163">관련 항목</span><span class="sxs-lookup"><span data-stu-id="69cf5-163">Related topics</span></span>

- [<span data-ttu-id="69cf5-164">사용자에 게 정책 할당</span><span class="sxs-lookup"><span data-stu-id="69cf5-164">Assign policies to your users</span></span>](assign-policies.md)
- [<span data-ttu-id="69cf5-165">새로운 CsBatchPolicyAssignmentOperation</span><span class="sxs-lookup"><span data-stu-id="69cf5-165">New-CsBatchPolicyAssignmentOperation</span></span>](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation)
- [<span data-ttu-id="69cf5-166">Get-CsBatchPolicyAssignmentOperation</span><span class="sxs-lookup"><span data-stu-id="69cf5-166">Get-CsBatchPolicyAssignmentOperation</span></span>](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation)
- [<span data-ttu-id="69cf5-167">Get-CsUserPolicyAssignment</span><span class="sxs-lookup"><span data-stu-id="69cf5-167">Get-CsUserPolicyAssignment</span></span>](https://docs.microsoft.com/powershell/module/teams/get-csuserpolicyassignment)