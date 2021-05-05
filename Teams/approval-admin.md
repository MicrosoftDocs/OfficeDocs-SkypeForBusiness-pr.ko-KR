---
title: Teams의 승인 응용 프로그램 가용성
author: cichur
ms.author: v-cichur
ms.reviewer: farhazk
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
searchScope:
- Microsoft Teams
search.appverid: MET150
description: Microsoft Teams의 승인 응용 프로그램 가용성에 대해 알아보세요.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 127fc2831e58e7ddea152c7754015a9126390ecc
ms.sourcegitcommit: 5a738cbb96f09edd8c3779f9385bc9ed126e3001
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2021
ms.locfileid: "52212171"
---
# <a name="teams-approvals-app-availability"></a><span data-ttu-id="d9973-103">Teams 승인 앱 가용성</span><span class="sxs-lookup"><span data-stu-id="d9973-103">Teams Approvals app availability</span></span>

<span data-ttu-id="d9973-104">승인 앱은 모든 Microsoft Teams 사용자를 위한 개인 앱으로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9973-104">The Approvals app is available as a personal app for all Microsoft Teams users.</span></span>
<span data-ttu-id="d9973-105">승인 앱은 감사, 규정 준수, 책임 및 워크플로를 Teams의 정형 및 비정형 승인에 모두 적용할 수 있는 간단한 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d9973-105">The Approvals app provides a simple way to bring auditing, compliance, accountability, and workflows to both structured and unstructured Approvals in Teams.</span></span>

 ![승인 앱을 표시합니다.](media/approvals-selection.png)

<span data-ttu-id="d9973-107">승인 앱을 고정하여 메뉴 모음에 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9973-107">Users can pin the Approvals app to save it to the menu bar.</span></span>

 ![승인 앱에 고정 옵션을 표시합니다.](media/approvalApp-pin.png)

<span data-ttu-id="d9973-109">승인 앱에서 생성된 첫 번째 승인이은 기본 CDS(일반 데이터 서비스) 환경에서 승인 솔루션의 프로비저닝을 트리거합니다.</span><span class="sxs-lookup"><span data-stu-id="d9973-109">The first approval created from the Approvals app will trigger the provisioning of the Approval Solution in the default Common Data Service (CDS) environment.</span></span> <span data-ttu-id="d9973-110">승인 앱에서 생성된 승인은 기본 CDS 환경에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="d9973-110">Approvals created from the Approvals app will be stored in the default CDS environment.</span></span>

<span data-ttu-id="d9973-111">이 자료에서는 승인 앱 요구 사항 및 역할에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d9973-111">This article describes the Approvals app requirements and roles.</span></span>

> [!NOTE]
> <span data-ttu-id="d9973-112">이 기능은 아직(정부 커뮤니티 클라우드), GCC(GCCH) 및 국방부(DOD) 정부 커뮤니티 클라우드 사용자에게 릴리스되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="d9973-112">This feature hasn't been released to Government Community Cloud (GCC), Government Community Cloud High (GCCH), and Department of Defense (DOD) users yet.</span></span>

## <a name="required-permissions-and-licenses"></a><span data-ttu-id="d9973-113">필요한 권한 및 라이선스</span><span class="sxs-lookup"><span data-stu-id="d9973-113">Required permissions and licenses</span></span>

<span data-ttu-id="d9973-114">승인 앱을 사용하려면 다음 항목에 대한 권한이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9973-114">To use the Approvals app, you need permission for the following items:</span></span>

- <span data-ttu-id="d9973-115">Microsoft CDS 데이터베이스를 만들 수 있는 사용 권한입니다.</span><span class="sxs-lookup"><span data-stu-id="d9973-115">Permissions to create a Microsoft CDS database.</span></span>

- <span data-ttu-id="d9973-116">[flow.microsoft.com](https://flow.microsoft.com/)의 계정</span><span class="sxs-lookup"><span data-stu-id="d9973-116">An account on [flow.microsoft.com](https://flow.microsoft.com/)</span></span>

- <span data-ttu-id="d9973-117">대상 환경의 관리자 역할</span><span class="sxs-lookup"><span data-stu-id="d9973-117">Administrator Role in the target environment.</span></span>

- <span data-ttu-id="d9973-118">[Power Automatic](/power-automate/get-started-approvals), Office 365 또는 Dynamics 365에 대한 라이선스</span><span class="sxs-lookup"><span data-stu-id="d9973-118">License for a [Power Automate](/power-automate/get-started-approvals), an Office 365, or a Dynamics 365.</span></span>

- <span data-ttu-id="d9973-119">사용자가 새 승인 템플릿을 설정하려면 Microsoft Forms에 대한 라이선스가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="d9973-119">License for Microsoft Forms is required for users to set up new approval templates.</span></span>

## <a name="storage-with-cds"></a><span data-ttu-id="d9973-120">CDS가 포함된 저장소</span><span class="sxs-lookup"><span data-stu-id="d9973-120">Storage with CDS</span></span>

<span data-ttu-id="d9973-121">일반 데이터 모델(CDM)은 CDS의 비즈니스 및 분석 응용 프로그램에서 사용되는 공유 데이터 언어입니다.</span><span class="sxs-lookup"><span data-stu-id="d9973-121">The Common Data Model (CDM) is the shared data language used by business and analytical applications in the CDS.</span></span> <span data-ttu-id="d9973-122">Microsoft 및 파트너가 게시한 표준화된 확장 가능한 데이터 스키마 세트로 구성되어 응용 프로그램 및 비즈니스 프로세스에서 데이터와 데이터 의미의 일관성을 유지합니다.</span><span class="sxs-lookup"><span data-stu-id="d9973-122">It consists of a set of a standardized, extensible data schemas published by Microsoft and our partners that enables consistency of data and its meaning across applications and business processes.</span></span> <span data-ttu-id="d9973-123">[Microsoft Power Platform의 일반 데이터 모델](/power-automate/get-started-approvals)에 대해 자세히 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="d9973-123">Learn more about the [Common Data Model of the Microsoft Power Platform](/power-automate/get-started-approvals).</span></span>

<span data-ttu-id="d9973-124">[승인 워크플로](/power-automate/modern-approvals)에 대해 자세히 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="d9973-124">Learn more about the [Approval workflow](/power-automate/modern-approvals).</span></span>

<span data-ttu-id="d9973-125">템플릿에서 만든 승인은 여전히 타이틀, 세부 정보, 템플릿 ID 등의 데이터를 CDS에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="d9973-125">Approvals that are created from a template still store data in CDS, such as their title, details, template ID, and more.</span></span> <span data-ttu-id="d9973-126">승인 요청에 제출된 응답은 양식에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="d9973-126">Responses that are submitted on the approval request are stored in Forms.</span></span> <span data-ttu-id="d9973-127"> [Microsoft Forms용 데이터 저장소에 대해 자세히 알아보자.](https://support.microsoft.com/office/data-storage-for-microsoft-forms-97a34e2e-98e1-4dc2-b6b4-7a8444cb1dc3#:~:text=Where%20data%20is%20stored%20for%20Microsoft%20Forms.%20Microsoft,European-based%20tenants%20is%20stored%20on%20servers%20in%20Europe)</span><span class="sxs-lookup"><span data-stu-id="d9973-127">Learn more about  [Data storage for Microsoft Forms](https://support.microsoft.com/office/data-storage-for-microsoft-forms-97a34e2e-98e1-4dc2-b6b4-7a8444cb1dc3#:~:text=Where%20data%20is%20stored%20for%20Microsoft%20Forms.%20Microsoft,European-based%20tenants%20is%20stored%20on%20servers%20in%20Europe).</span></span>

>[!Note]
><span data-ttu-id="d9973-128">Microsoft Forms 사이트에서 양식 서식 파일을 삭제하면 승인 템플릿이 중단되고 사용자가 요청을 시작할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d9973-128">If you delete the Form template on the Microsoft Forms site, it will break your Approval template and users will not be able to start the request.</span></span> <span data-ttu-id="d9973-129">Microsoft Forms에서 삭제된 승인 템플릿을 열려고 할 때 "CDB TableNotFound"에 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="d9973-129">Users will get an error "CDB TableNotFound" when trying to open an Approval template that has been deleted on Microsoft Forms.</span></span>

<span data-ttu-id="d9973-130">승인 템플릿은 Microsoft 내에서만 내부적으로 Storage 규격 스토리지 플랫폼인 SDS(기판 데이터 Storage)에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="d9973-130">The approval templates are stored in Substrate Data Storage (SDS), which is a compliant storage platform used internally only inside Microsoft.</span></span> <span data-ttu-id="d9973-131">조직 범위 템플릿은 SDS의 "테넌트 데이터베이스"에 저장되고 팀 범위 템플릿은 SDS의 "그룹 데이터베이스"에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="d9973-131">The organization-scoped templates are stored in “tenant shard” of SDS, and team-scoped templates are stored in “group shards” of SDS.</span></span> <span data-ttu-id="d9973-132">즉, 구성 범위 템플릿은 테넌트의 동일한 수명을 공유하고 팀 범위 템플릿은 팀의 동일한 수명을 공유합니다.</span><span class="sxs-lookup"><span data-stu-id="d9973-132">This means that the org-scoped templates share the same lifetime of the tenant and team-scoped templates share the same lifetime of the team.</span></span> <span data-ttu-id="d9973-133">따라서 팀을 영구적으로 삭제하면 관련 템플릿이 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="d9973-133">So, permanently deleting the team deletes the related templates.</span></span>

## <a name="approvals-teams-app-permissions"></a><span data-ttu-id="d9973-134">승인 Teams 앱 사용 권한</span><span class="sxs-lookup"><span data-stu-id="d9973-134">Approvals Teams app permissions</span></span>

<span data-ttu-id="d9973-135">승인 Teams 앱을 통해 다음 기능에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9973-135">The Approvals Teams app lets you access the following features:</span></span>

- <span data-ttu-id="d9973-136">메시지에 제공하는 메시지 및 데이터를 수신합니다.</span><span class="sxs-lookup"><span data-stu-id="d9973-136">Receive messages and data that you provide to it.</span></span>

- <span data-ttu-id="d9973-137">메시지 및 알림을 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="d9973-137">Send you messages and notifications.</span></span>

- <span data-ttu-id="d9973-138">Teams이 제공한 헤더 없이 개인 앱 및 대화 상자를 렌더링합니다.</span><span class="sxs-lookup"><span data-stu-id="d9973-138">Render personal apps and dialogs without a Teams-provided header.</span></span>

- <span data-ttu-id="d9973-139">이름, 전자 메일 주소, 회사 이름 및 기본 설정 언어와 같은 프로필 정보에 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="d9973-139">Access your profile information such as your name, email address, company name, and preferred language.</span></span>

- <span data-ttu-id="d9973-140">Teams 구성원이 채널에 제공하는 메시지 및 데이터를 수신합니다.</span><span class="sxs-lookup"><span data-stu-id="d9973-140">Receive messages and data that team members provide to it in a channel.</span></span>

- <span data-ttu-id="d9973-141">채널에서 메시지 및 알림을 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="d9973-141">Send messages and notifications in a channel.</span></span>

- <span data-ttu-id="d9973-142">다음과 같은 Teams 정보에 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="d9973-142">Access your team's information:</span></span>
  - <span data-ttu-id="d9973-143">팀 이름</span><span class="sxs-lookup"><span data-stu-id="d9973-143">team name</span></span>
  - <span data-ttu-id="d9973-144">채널 목록</span><span class="sxs-lookup"><span data-stu-id="d9973-144">channel list</span></span>
  - <span data-ttu-id="d9973-145">명단(팀 구성원의 이름 및 전자 메일 주소)</span><span class="sxs-lookup"><span data-stu-id="d9973-145">roster (team member's names and email addresses).</span></span>

- <span data-ttu-id="d9973-146">팀의 정보를 사용하여 팀에 연락하세요.</span><span class="sxs-lookup"><span data-stu-id="d9973-146">Use the team's information to contact them.</span></span>

<span data-ttu-id="d9973-147">승인 템플릿 사용 권한</span><span class="sxs-lookup"><span data-stu-id="d9973-147">Approval Template Permissions</span></span>

- <span data-ttu-id="d9973-148">모든 팀 소유자는 소유한 팀에 대한 승인 템플릿을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9973-148">All team owners can create an approval template for teams that they own.</span></span>

- <span data-ttu-id="d9973-149">관리자가 처음으로 전체 조직에 대한 템플릿을 만들면 전역 및 팀의 서비스 관리자를 Teams 테넌트의 모든 관리자에 대한 새 팀을 자동으로 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d9973-149">When an Admin creates a template for their entire organization for the first time, it will automatically create a new Teams team for all admins of the tenant, including the global and Team’s service admins.</span></span> <span data-ttu-id="d9973-150">이러한 관리자는 팀의 소유자로 추가될 것이기 때문에 조직 템플릿을 공동 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9973-150">These admins will be added as owners of the team, so they can co-manage organizational templates.</span></span> <span data-ttu-id="d9973-151">팀을 만든 후 조직에 새로운 관리자는 팀 소유자로 수동으로 추가해야 조직 전체 템플릿을 관리할 수 있는 권한이 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="d9973-151">Admins that are new to the organization after the team has been created need to be manually added as team owners so they have the same permissions to manage organization-wide templates.</span></span>

> [!Note]
> <span data-ttu-id="d9973-152">관리자가 팀을 삭제하는 경우 모든 관련 데이터를 복원하기 위해 AAD(Azure Active Directory) 포털 내에서 복원할 Azure Active Directory 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9973-152">If an admin deletes the team, you have one month to restore it within the Azure Active Directory (AAD) portal to restore all related data.</span></span> <span data-ttu-id="d9973-153">한 달이 지난 후 또는 관리자가 이 팀을 리사이즈 bin 내에서 삭제하면 관련된 모든 데이터가 손실됩니다.</span><span class="sxs-lookup"><span data-stu-id="d9973-153">After one month, or if the admin deletes this team within the recycle bin, you will lose all the related data.</span></span>

## <a name="disable-the-approvals-app"></a><span data-ttu-id="d9973-154">승인 앱 사용 해제</span><span class="sxs-lookup"><span data-stu-id="d9973-154">Disable the Approvals app</span></span>

<span data-ttu-id="d9973-155">기본적으로 승인 앱은 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9973-155">The Approvals app is available by default.</span></span> <span data-ttu-id="d9973-156">Teams 관리 센터에서 앱을 비활성화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9973-156">You can disable the app in the Teams admin center.</span></span>

  1. <span data-ttu-id="d9973-157">Teams 관리 센터에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="d9973-157">Sign in to the Teams admin center.</span></span>

  2. <span data-ttu-id="d9973-158">**Teams 앱** 을 확장하고 **앱 관리** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d9973-158">Expand **Teams apps** and select **Manage apps**.</span></span>

  3. <span data-ttu-id="d9973-159">승인 앱을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="d9973-159">Search for the Approvals app.</span></span>

     ![팀 앱 > 앱 관리가 강조 표시된 관리 센터 탐색이 나타납니다.](media/manage-approval-apps.png)

  4. <span data-ttu-id="d9973-161">승인을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d9973-161">Select Approvals.</span></span>

  5. <span data-ttu-id="d9973-162">조직에 대한 앱을 비활성화하려면 토글을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d9973-162">Select the toggle to disable the app for your organization.</span></span>

     ![승인 앱의 세부 정보 표시](media/approvals-details.png)

## <a name="retention-policy"></a><span data-ttu-id="d9973-164">보존 정책</span><span class="sxs-lookup"><span data-stu-id="d9973-164">Retention policy</span></span>

<span data-ttu-id="d9973-165">승인 앱에서 생성된 승인은 현재 백업을 지원하지 않는 기본 CDS 환경에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="d9973-165">Approvals created from the Approvals App are stored in the default CDS environment, which doesn’t support backups at this time.</span></span> <span data-ttu-id="d9973-166">[환경을 백업 및 복원하는 방법에 대해 자세히 알아보세요. PowerPlatform \|Microsoft Docs](/power-platform/admin/backup-restore-environments).</span><span class="sxs-lookup"><span data-stu-id="d9973-166">Learn more about how to [Back up and restore environments - Power Platform \| Microsoft Docs](/power-platform/admin/backup-restore-environments).</span></span>

<span data-ttu-id="d9973-167">양식에 저장된 데이터는 팀 소유자가 Microsoft Forms 웹앱의  삭제된 폼 탭에서 정리할 때까지 삭제되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d9973-167">Data stored in Forms will not be deleted until the team owners clean it up from the **deleted forms** tab in the Microsoft Forms web app.</span></span>

## <a name="data-limitations"></a><span data-ttu-id="d9973-168">데이터 제한 사항</span><span class="sxs-lookup"><span data-stu-id="d9973-168">Data limitations</span></span>

<span data-ttu-id="d9973-169">각 팀은 최대 400개 이상의 승인 템플릿을 포함할 수 있으며, 각 템플릿은 Microsoft Forms의 현재 기능에 따라 최대 50,000개 요청을 수집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9973-169">Each team can contain at most 400 approvals templates, and each template can collect a maximum of 50,000 requests based on the current capability in Microsoft Forms.</span></span>

## <a name="auditing"></a><span data-ttu-id="d9973-170">감사</span><span class="sxs-lookup"><span data-stu-id="d9973-170">Auditing</span></span>

<span data-ttu-id="d9973-171">승인 앱은 Microsoft 365 보안 및 규정 준수 센터 내에서 감사 이벤트를 기록합니다.</span><span class="sxs-lookup"><span data-stu-id="d9973-171">The Approvals App logs audit events within the Microsoft 365 Security and Compliance Center.</span></span> <span data-ttu-id="d9973-172">감사 로그를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9973-172">You can view the audit log.</span></span>

1. <span data-ttu-id="d9973-173">Microsoft 365 규정 준수 사이트로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="d9973-173">Go to the Microsoft 365 Compliance Site.</span></span>

2. <span data-ttu-id="d9973-174">**감사** 섹션을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d9973-174">Select the **Audit** section.</span></span>

3. <span data-ttu-id="d9973-175">**Microsoft Teams 승인 작업** 에서 활동을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="d9973-175">Search for activities under **Microsoft Teams approvals activities**.</span></span>

<span data-ttu-id="d9973-176">다음 활동을 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9973-176">You can search for the following activities:</span></span>

- <span data-ttu-id="d9973-177">새 승인 요청 만들기</span><span class="sxs-lookup"><span data-stu-id="d9973-177">Create new approval request</span></span>

- <span data-ttu-id="d9973-178">승인 요청 세부 정보 보기</span><span class="sxs-lookup"><span data-stu-id="d9973-178">View approval request details</span></span>

- <span data-ttu-id="d9973-179">승인된 승인 요청</span><span class="sxs-lookup"><span data-stu-id="d9973-179">Approved approval request</span></span>

- <span data-ttu-id="d9973-180">승인 요청 거부</span><span class="sxs-lookup"><span data-stu-id="d9973-180">Rejected approval request</span></span>

- <span data-ttu-id="d9973-181">승인 요청 취소</span><span class="sxs-lookup"><span data-stu-id="d9973-181">Canceled approval request</span></span>

- <span data-ttu-id="d9973-182">공유 승인 요청</span><span class="sxs-lookup"><span data-stu-id="d9973-182">Shared approval request</span></span>

- <span data-ttu-id="d9973-183">승인 요청에 첨부된 파일</span><span class="sxs-lookup"><span data-stu-id="d9973-183">File attached to approval request</span></span>

- <span data-ttu-id="d9973-184">재할당된 승인 요청</span><span class="sxs-lookup"><span data-stu-id="d9973-184">Reassigned approval request</span></span>

- <span data-ttu-id="d9973-185">승인 요청에 전자 서명 추가</span><span class="sxs-lookup"><span data-stu-id="d9973-185">Added e-signature to approval request</span></span>

- <span data-ttu-id="d9973-186">확인된 전자 서명 요청 세부 정보</span><span class="sxs-lookup"><span data-stu-id="d9973-186">Viewed e-signature request details</span></span>

- <span data-ttu-id="d9973-187">검토된 전자 서명 요청</span><span class="sxs-lookup"><span data-stu-id="d9973-187">Reviewed e-signature request</span></span>

- <span data-ttu-id="d9973-188">취소된 전자 서명 요청</span><span class="sxs-lookup"><span data-stu-id="d9973-188">Canceled e-signature request</span></span>

- <span data-ttu-id="d9973-189">새 템플릿 만들기</span><span class="sxs-lookup"><span data-stu-id="d9973-189">Create a new template</span></span>

- <span data-ttu-id="d9973-190">기존 템플릿 편집</span><span class="sxs-lookup"><span data-stu-id="d9973-190">Edit an existing template</span></span>

- <span data-ttu-id="d9973-191">템플릿 사용/사용 안 하도록 설정</span><span class="sxs-lookup"><span data-stu-id="d9973-191">Enable/disable a template</span></span>

- <span data-ttu-id="d9973-192">보기 템플릿</span><span class="sxs-lookup"><span data-stu-id="d9973-192">Viewed template</span></span>

<span data-ttu-id="d9973-193">Flow 내에서 더 많은 감사 승인에 액세스하려면 기본 승인 엔터티 승인, 승인 요청 및 승인 응답에 대한 기본 환경에서 감사를 사용하도록 설정하고 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="d9973-193">For access to more auditing approvals within Flow, enable and configure auditing in the default environment for the primary approval entities Approval, Approval Request, and Approval Response.</span></span> <span data-ttu-id="d9973-194">생성, 업데이트 및 삭제 작업은 승인 레코드에 대해 감사할 수 있는 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="d9973-194">Create, update, and delete operations are auditable events for Approval records.</span></span> <span data-ttu-id="d9973-195">[보안 및 규정 준수를 위한 감사 데이터 및 사용자 활동 - Power Platform \|Microsoft Docs](/power-platform/admin/audit-data-user-activity)에 대해 자세히 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="d9973-195">Learn more about [Audit data and user activity for security and compliance - Power Platform \| Microsoft Docs](/power-platform/admin/audit-data-user-activity).</span></span>

<span data-ttu-id="d9973-196">감사는 [Microsoft 365 보안 및 규정 준수 센터](https://support.office.com/article/go-to-the-office-365-security-compliance-center-7e696a40-b86b-4a20-afcc-559218b7b1b8?ui=en-US&rs=en-US&ad=US)에서 추가로 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9973-196">Auditing can be customized further in the [Microsoft 365 Security and Compliance Center](https://support.office.com/article/go-to-the-office-365-security-compliance-center-7e696a40-b86b-4a20-afcc-559218b7b1b8?ui=en-US&rs=en-US&ad=US).</span></span>

1. <span data-ttu-id="d9973-197">미리 구성된 보고서를 사용하려면 Microsoft 365 보안 및 규정 준수에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="d9973-197">To use the preconfigured reports, sign in to Microsoft 365 Security and Compliance.</span></span>

2. <span data-ttu-id="d9973-198">**검색 및 조사** 를 선택하세요.</span><span class="sxs-lookup"><span data-stu-id="d9973-198">Select **Search & investigation**.</span></span>

3. <span data-ttu-id="d9973-199">감사 로그를 검색하고 **Dynamics 365 활동** 탭을 선택하세요.</span><span class="sxs-lookup"><span data-stu-id="d9973-199">Search the Audit log and select the **Dynamics 365 activities** tab.</span></span>

<span data-ttu-id="d9973-200">[Microsoft Dataverse 및 모델 기반 앱 활동 로깅-Power Platform](/power-platform/admin/enable-use-comprehensive-auditing)에 대해 자세히 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="d9973-200">Learn more about [Microsoft Dataverse and model-driven apps activity logging - Power Platform](/power-platform/admin/enable-use-comprehensive-auditing).</span></span>

## <a name="security"></a><span data-ttu-id="d9973-201">보안</span><span class="sxs-lookup"><span data-stu-id="d9973-201">Security</span></span>

<span data-ttu-id="d9973-202">Teams 승인 앱에서 사용자는 새 승인을 만들고 보내고 받은 승인을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9973-202">From the Teams Approvals app, users have access to create new Approvals and view Approvals that they have sent and received.</span></span> <span data-ttu-id="d9973-203">사용자는 요청의 응답자 또는 뷰어가 아니면 다른 사용자가 만든 승인에 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d9973-203">Users won't have access to Approvals that are created by others unless they're either a responder or a viewer of the request.</span></span>

> [!Note]
> <span data-ttu-id="d9973-204">사용자가 승인이 만들어진 채팅 또는 채널의 일부인 경우 요청의 뷰어 역할이 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="d9973-204">A user will be given a viewer role of a request if they are part of the chat or channel where the approval was created.</span></span> <span data-ttu-id="d9973-205">승인이 생성되었을 때 해당 역할이 부여되지 않은 경우 요청에 대한 조치를 취할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d9973-205">They won't have the ability to take action on the request if they weren't given that role when the approval was created.</span></span>

## <a name="approvals-e-signature-integration"></a><span data-ttu-id="d9973-206">승인 전자 서명 통합</span><span class="sxs-lookup"><span data-stu-id="d9973-206">Approvals e-signature integration</span></span>

<span data-ttu-id="d9973-207">승인 앱에서 만든 전자 서명 승인은 선택한 공급자의 클라우드 환경에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="d9973-207">E-signature approvals created from the Approvals app are stored in the selected provider's cloud environment.</span></span> <span data-ttu-id="d9973-208">전자 서명 계약 주변의 저장소에 대한 자세한 내용은 선택한 공급자의 저장소 설명서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d9973-208">For further information about storage around the e-signature agreement, view the selected provider's storage documentation.</span></span>

<span data-ttu-id="d9973-209">승인 앱 전자 서명 기능을 사용하려면 다음 항목이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="d9973-209">To use the Approvals app e-signature feature, you need the following items:</span></span>

- <span data-ttu-id="d9973-210">사용 하도록 선택한 특정 전자 서명 공급자에 대한 라이선스입니다.</span><span class="sxs-lookup"><span data-stu-id="d9973-210">License for the specific e-signature provider you're choosing to use.</span></span> <span data-ttu-id="d9973-211">조직에 대한 라이선스를 얻기 위해 공급자의 사이트로 이동해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9973-211">In order to obtain a license for your organization, you'll need to go to the provider’s site.</span></span>

<span data-ttu-id="d9973-212">승인 전자 서명 기능의 경우 타사 서명 파트너가 기본적으로 Teams 앱에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d9973-212">For the Approvals e-signature functionality, third-party signature partners will appear in the Teams Approvals app by default.</span></span> <span data-ttu-id="d9973-213">관리 센터의 앱 설정에 액세스하여 특정 전자 서명 공급자를 Teams 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9973-213">You can disable specific e-signature providers by accessing app settings in the Teams admin center.</span></span>

1. <span data-ttu-id="d9973-214">관리 Teams 관리에서 승인 앱을 선택하고 **설정.** </span><span class="sxs-lookup"><span data-stu-id="d9973-214">In the Teams admin center, under **Manage apps**, select the **Approvals app** and choose **Settings**.</span></span>

2. <span data-ttu-id="d9973-215">각 전자 서명 공급자는 기본적으로 on 위치에 있는 토글 옆에 토글이 있습니다(오른쪽).</span><span class="sxs-lookup"><span data-stu-id="d9973-215">Each e-signature provider has a toggle next to it that is in the on position (right) by default.</span></span> <span data-ttu-id="d9973-216">토글을 왼쪽으로 밀어 특정 전자 서명 공급자를 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="d9973-216">Slide the toggle to the left to disable a specific e-signature provider.</span></span> <span data-ttu-id="d9973-217">관리자 Teams 공급자를 사용하지 않도록 설정하면 최종 사용자는 승인을 만들 때 공급자를 볼 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d9973-217">If a Teams admin disables a provider, end users won't see the provider when creating an approval.</span></span> <span data-ttu-id="d9973-218">또한 최종 사용자는 해당 공급자를 통해 만든 전자 서명 요청을 볼 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d9973-218">End users will also be unable to view any e-signature requests that were made with that provider.</span></span>

<span data-ttu-id="d9973-219">승인 앱에서 만든 전자 서명 승인은 선택한 공급자의 클라우드에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="d9973-219">E-signature Approvals created from the Approvals App are stored in the selected provider’s cloud.</span></span> <span data-ttu-id="d9973-220">따라서 전자 서명에 대한 데이터를 내보내기 위해 공급자의 사이트로 이동해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9973-220">You will therefore need to go to the provider's site in order to export any data about e-signatures.</span></span> <span data-ttu-id="d9973-221">이러한 계약의 내보내기 및 보존에 대한 공급자의 설명서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d9973-221">Refer to the provider's documentation about export and retention of these agreements.</span></span>
