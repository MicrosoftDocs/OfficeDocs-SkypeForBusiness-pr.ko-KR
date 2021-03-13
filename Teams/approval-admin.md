---
title: Teams의 승인 응용 프로그램 가용성
author: cichur
ms.author: v-cichur
ms.reviewer: aravin
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
ms.openlocfilehash: f916b4e794c862a05a42f075ca2f210a079ff42a
ms.sourcegitcommit: fdef9b52247097e5cae64f01b6b2b710c5b203cf
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/20/2021
ms.locfileid: "49909522"
---
# <a name="teams-approvals-app-availability"></a><span data-ttu-id="4bc73-103">Teams 승인 앱 가용성</span><span class="sxs-lookup"><span data-stu-id="4bc73-103">Teams Approvals app availability</span></span>

<span data-ttu-id="4bc73-104">승인 앱은 모든 Microsoft Teams 사용자를 위한 개인 앱으로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4bc73-104">The Approvals app is available as a personal app for all Microsoft Teams users.</span></span>
<span data-ttu-id="4bc73-105">승인 앱은 감사, 규정 준수, 책임 및 워크플로를 Teams의 정형 및 비정형 승인에 모두 적용할 수 있는 간단한 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="4bc73-105">The Approvals app provides a simple way to bring auditing, compliance, accountability, and workflows to both structured and unstructured Approvals in Teams.</span></span>

 ![승인 앱을 표시합니다.](media/approvals-selection.png)

<span data-ttu-id="4bc73-107">승인 앱을 고정하여 메뉴 모음에 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4bc73-107">Users can pin the Approvals app to save it to the menu bar.</span></span>

 ![승인 앱에 고정 옵션을 표시합니다.](media/approvalApp-pin.png)

<span data-ttu-id="4bc73-109">승인 앱에서 생성된 첫 번째 승인이은 기본 CDS(일반 데이터 서비스) 환경에서 승인 솔루션의 프로비저닝을 트리거합니다.</span><span class="sxs-lookup"><span data-stu-id="4bc73-109">The first approval created from the Approvals app will trigger the provisioning of the Approval Solution in the default Common Data Service (CDS) environment.</span></span> <span data-ttu-id="4bc73-110">승인 앱에서 생성된 승인은 기본 CDS 환경에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="4bc73-110">Approvals created from the Approvals app will be stored in the default CDS environment.</span></span>

<span data-ttu-id="4bc73-111">이 자료에서는 승인 앱 요구 사항 및 역할에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="4bc73-111">This article describes the Approvals app requirements and roles.</span></span>

## <a name="required-permissions-and-licenses"></a><span data-ttu-id="4bc73-112">필요한 권한 및 라이선스</span><span class="sxs-lookup"><span data-stu-id="4bc73-112">Required permissions and licenses</span></span>

<span data-ttu-id="4bc73-113">승인 앱을 사용하려면 다음 항목에 대한 권한이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bc73-113">To use the Approvals app, you need permission for the following items:</span></span>

- <span data-ttu-id="4bc73-114">Microsoft CDS 데이터베이스를 만들 수 있는 사용 권한입니다.</span><span class="sxs-lookup"><span data-stu-id="4bc73-114">Permissions to create a Microsoft CDS database.</span></span>

- <span data-ttu-id="4bc73-115">[flow.microsoft.com](https://flow.microsoft.com/)의 계정</span><span class="sxs-lookup"><span data-stu-id="4bc73-115">An account on [flow.microsoft.com](https://flow.microsoft.com/)</span></span>

- <span data-ttu-id="4bc73-116">대상 환경의 관리자 역할</span><span class="sxs-lookup"><span data-stu-id="4bc73-116">Administrator Role in the target environment.</span></span>

- <span data-ttu-id="4bc73-117">[Power Automatic](https://docs.microsoft.com/power-automate/get-started-approvals), Office 365 또는 Dynamics 365에 대한 라이선스</span><span class="sxs-lookup"><span data-stu-id="4bc73-117">License for a [Power Automate](https://docs.microsoft.com/power-automate/get-started-approvals), an Office 365, or a Dynamics 365.</span></span>

## <a name="storage-with-cds"></a><span data-ttu-id="4bc73-118">CDS가 포함된 저장소</span><span class="sxs-lookup"><span data-stu-id="4bc73-118">Storage with CDS</span></span>

<span data-ttu-id="4bc73-119">일반 데이터 모델(CDM)은 CDS의 비즈니스 및 분석 응용 프로그램에서 사용되는 공유 데이터 언어입니다.</span><span class="sxs-lookup"><span data-stu-id="4bc73-119">The Common Data Model (CDM) is the shared data language used by business and analytical applications in the CDS.</span></span> <span data-ttu-id="4bc73-120">Microsoft 및 파트너가 게시한 표준화된 확장 가능한 데이터 스키마 세트로 구성되어 응용 프로그램 및 비즈니스 프로세스에서 데이터와 데이터 의미의 일관성을 유지합니다.</span><span class="sxs-lookup"><span data-stu-id="4bc73-120">It consists of a set of a standardized, extensible data schemas published by Microsoft and our partners that enables consistency of data and its meaning across applications and business processes.</span></span> <span data-ttu-id="4bc73-121">[Microsoft Power Platform의 일반 데이터 모델](https://docs.microsoft.com/power-automate/get-started-approvals)에 대해 자세히 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="4bc73-121">Learn more about the [Common Data Model of the Microsoft Power Platform](https://docs.microsoft.com/power-automate/get-started-approvals).</span></span>

<span data-ttu-id="4bc73-122">[승인 워크플로](https://docs.microsoft.com/power-automate/modern-approvals)에 대해 자세히 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="4bc73-122">Learn more about the [Approval workflow](https://docs.microsoft.com/power-automate/modern-approvals).</span></span>

## <a name="approvals-teams-app-permissions"></a><span data-ttu-id="4bc73-123">승인 Teams 앱 사용 권한</span><span class="sxs-lookup"><span data-stu-id="4bc73-123">Approvals Teams app permissions</span></span>

<span data-ttu-id="4bc73-124">승인 Teams 앱을 통해 다음 기능에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4bc73-124">The Approvals Teams app lets you access the following features:</span></span>

- <span data-ttu-id="4bc73-125">메시지에 제공하는 메시지 및 데이터를 수신합니다.</span><span class="sxs-lookup"><span data-stu-id="4bc73-125">Receive messages and data that you provide to it.</span></span>

- <span data-ttu-id="4bc73-126">메시지 및 알림을 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="4bc73-126">Send you messages and notifications.</span></span>

- <span data-ttu-id="4bc73-127">Teams이 제공한 헤더 없이 개인 앱 및 대화 상자를 렌더링합니다.</span><span class="sxs-lookup"><span data-stu-id="4bc73-127">Render personal apps and dialogs without a Teams-provided header.</span></span>

- <span data-ttu-id="4bc73-128">이름, 전자 메일 주소, 회사 이름 및 기본 설정 언어와 같은 프로필 정보에 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="4bc73-128">Access your profile information such as your name, email address, company name, and preferred language.</span></span>

- <span data-ttu-id="4bc73-129">Teams 구성원이 채널에 제공하는 메시지 및 데이터를 수신합니다.</span><span class="sxs-lookup"><span data-stu-id="4bc73-129">Receive messages and data that team members provide to it in a channel.</span></span>

- <span data-ttu-id="4bc73-130">채널에서 메시지 및 알림을 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="4bc73-130">Send messages and notifications in a channel.</span></span>

- <span data-ttu-id="4bc73-131">다음과 같은 Teams 정보에 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="4bc73-131">Access your team's information:</span></span>
  - <span data-ttu-id="4bc73-132">팀 이름</span><span class="sxs-lookup"><span data-stu-id="4bc73-132">team name</span></span>
  - <span data-ttu-id="4bc73-133">채널 목록</span><span class="sxs-lookup"><span data-stu-id="4bc73-133">channel list</span></span>
  - <span data-ttu-id="4bc73-134">명단(팀 구성원의 이름 및 전자 메일 주소)</span><span class="sxs-lookup"><span data-stu-id="4bc73-134">roster (team member's names and email addresses).</span></span>

- <span data-ttu-id="4bc73-135">팀의 정보를 사용하여 팀에 연락하세요.</span><span class="sxs-lookup"><span data-stu-id="4bc73-135">Use the team's information to contact them.</span></span>

## <a name="disable-the-approvals-app"></a><span data-ttu-id="4bc73-136">승인 앱 사용 해제</span><span class="sxs-lookup"><span data-stu-id="4bc73-136">Disable the Approvals app</span></span>

<span data-ttu-id="4bc73-137">기본적으로 승인 앱은 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4bc73-137">The Approvals app is available by default.</span></span> <span data-ttu-id="4bc73-138">Teams 관리 센터에서 앱을 비활성화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4bc73-138">You can disable the app in the Teams admin center.</span></span>

  1. <span data-ttu-id="4bc73-139">Teams 관리 센터에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="4bc73-139">Sign in to the Teams admin center.</span></span>

  2. <span data-ttu-id="4bc73-140">**Teams 앱** 을 확장하고 **앱 관리** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4bc73-140">Expand **Teams apps** and select **Manage apps**.</span></span>

  3. <span data-ttu-id="4bc73-141">승인 앱을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="4bc73-141">Search for the Approvals app.</span></span>

![팀 앱 > 앱 관리가 강조 표시된 관리 센터 탐색이 나타납니다.](media/manage-approval-apps.png)

  4. <span data-ttu-id="4bc73-143">승인을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4bc73-143">Select Approvals.</span></span>

  5. <span data-ttu-id="4bc73-144">조직에 대한 앱을 비활성화하려면 토글을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4bc73-144">Select the toggle to disable the app for your organization.</span></span>

![승인 앱의 세부 정보 표시](media/approvals-details.png)

## <a name="retention-policy"></a><span data-ttu-id="4bc73-146">보존 정책</span><span class="sxs-lookup"><span data-stu-id="4bc73-146">Retention policy</span></span>

<span data-ttu-id="4bc73-147">승인 앱에서 생성된 승인은 현재 백업을 지원하지 않는 기본 CDS 환경에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="4bc73-147">Approvals created from the Approvals App are stored in the default CDS environment, which doesn’t support backups at this time.</span></span> <span data-ttu-id="4bc73-148">[환경을 백업 및 복원하는 방법에 대해 자세히 알아보세요. PowerPlatform \|Microsoft Docs](https://docs.microsoft.com/power-platform/admin/backup-restore-environments).</span><span class="sxs-lookup"><span data-stu-id="4bc73-148">Learn more about how to [Back up and restore environments - Power Platform \| Microsoft Docs](https://docs.microsoft.com/power-platform/admin/backup-restore-environments).</span></span>

## <a name="auditing"></a><span data-ttu-id="4bc73-149">감사</span><span class="sxs-lookup"><span data-stu-id="4bc73-149">Auditing</span></span>

<span data-ttu-id="4bc73-150">승인 앱은 Microsoft 365 보안 및 규정 준수 센터 내에서 감사 이벤트를 기록합니다.</span><span class="sxs-lookup"><span data-stu-id="4bc73-150">The Approvals App logs audit events within the Microsoft 365 Security and Compliance Center.</span></span> <span data-ttu-id="4bc73-151">감사 로그를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4bc73-151">You can view the audit log.</span></span>

1. <span data-ttu-id="4bc73-152">Microsoft 365 규정 준수 사이트로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="4bc73-152">Go to the Microsoft 365 Compliance Site.</span></span>

2. <span data-ttu-id="4bc73-153">**감사** 섹션을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4bc73-153">Select the **Audit** section.</span></span>

3. <span data-ttu-id="4bc73-154">**Microsoft Teams 승인 작업** 에서 활동을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="4bc73-154">Search for activities under **Microsoft Teams approvals activities**.</span></span>

<span data-ttu-id="4bc73-155">다음 활동을 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4bc73-155">You can search for the following activities:</span></span>

- <span data-ttu-id="4bc73-156">새 승인 요청 만들기</span><span class="sxs-lookup"><span data-stu-id="4bc73-156">Create new approval request</span></span>

- <span data-ttu-id="4bc73-157">승인 요청 세부 정보 보기</span><span class="sxs-lookup"><span data-stu-id="4bc73-157">View approval request details</span></span>

- <span data-ttu-id="4bc73-158">승인된 승인 요청</span><span class="sxs-lookup"><span data-stu-id="4bc73-158">Approved approval request</span></span>

- <span data-ttu-id="4bc73-159">승인 요청 거부</span><span class="sxs-lookup"><span data-stu-id="4bc73-159">Rejected approval request</span></span>

- <span data-ttu-id="4bc73-160">승인 요청 취소</span><span class="sxs-lookup"><span data-stu-id="4bc73-160">Canceled approval request</span></span>

- <span data-ttu-id="4bc73-161">공유 승인 요청</span><span class="sxs-lookup"><span data-stu-id="4bc73-161">Shared approval request</span></span>

- <span data-ttu-id="4bc73-162">승인 요청에 첨부된 파일</span><span class="sxs-lookup"><span data-stu-id="4bc73-162">File attached to approval request</span></span>

- <span data-ttu-id="4bc73-163">재할당된 승인 요청</span><span class="sxs-lookup"><span data-stu-id="4bc73-163">Reassigned approval request</span></span>

- <span data-ttu-id="4bc73-164">승인 요청에 전자 서명 추가</span><span class="sxs-lookup"><span data-stu-id="4bc73-164">Added e-signature to approval request</span></span>

<span data-ttu-id="4bc73-165">Flow 내에서 더 많은 감사 승인에 액세스하려면 기본 승인 엔터티 승인, 승인 요청 및 승인 응답에 대한 기본 환경에서 감사를 사용하도록 설정하고 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="4bc73-165">For access to more auditing approvals within Flow, enable and configure auditing in the default environment for the primary approval entities Approval, Approval Request, and Approval Response.</span></span> <span data-ttu-id="4bc73-166">생성, 업데이트 및 삭제 작업은 승인 레코드에 대해 감사할 수 있는 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="4bc73-166">Create, update, and delete operations are auditable events for Approval records.</span></span> <span data-ttu-id="4bc73-167">[보안 및 규정 준수를 위한 감사 데이터 및 사용자 활동 - Power Platform \|Microsoft Docs](https://docs.microsoft.com/power-platform/admin/audit-data-user-activity)에 대해 자세히 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="4bc73-167">Learn more about [Audit data and user activity for security and compliance - Power Platform \| Microsoft Docs](https://docs.microsoft.com/power-platform/admin/audit-data-user-activity).</span></span>

<span data-ttu-id="4bc73-168">감사는 [Microsoft 365 보안 및 규정 준수 센터](https://support.office.com/article/go-to-the-office-365-security-compliance-center-7e696a40-b86b-4a20-afcc-559218b7b1b8?ui=en-US&rs=en-US&ad=US)에서 추가로 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4bc73-168">Auditing can be customized further in the [Microsoft 365 Security and Compliance Center](https://support.office.com/article/go-to-the-office-365-security-compliance-center-7e696a40-b86b-4a20-afcc-559218b7b1b8?ui=en-US&rs=en-US&ad=US).</span></span>

1. <span data-ttu-id="4bc73-169">미리 구성된 보고서를 사용하려면 Microsoft 365 보안 및 규정 준수에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="4bc73-169">To use the preconfigured reports, sign in to Microsoft 365 Security and Compliance.</span></span>

2. <span data-ttu-id="4bc73-170">**검색 및 조사** 를 선택하세요.</span><span class="sxs-lookup"><span data-stu-id="4bc73-170">Select **Search & investigation**.</span></span>

3. <span data-ttu-id="4bc73-171">감사 로그를 검색하고 **Dynamics 365 활동** 탭을 선택하세요.</span><span class="sxs-lookup"><span data-stu-id="4bc73-171">Search the Audit log and select the **Dynamics 365 activities** tab.</span></span>

<span data-ttu-id="4bc73-172">[Microsoft Dataverse 및 모델 기반 앱 활동 로깅-Power Platform](https://docs.microsoft.com/power-platform/admin/enable-use-comprehensive-auditing)에 대해 자세히 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="4bc73-172">Learn more about [Microsoft Dataverse and model-driven apps activity logging - Power Platform](https://docs.microsoft.com/power-platform/admin/enable-use-comprehensive-auditing).</span></span>

## <a name="security"></a><span data-ttu-id="4bc73-173">보안</span><span class="sxs-lookup"><span data-stu-id="4bc73-173">Security</span></span>

<span data-ttu-id="4bc73-174">Teams 승인 앱에서 사용자는 새 승인을 만들고 보내고 받은 승인을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4bc73-174">From the Teams Approvals app, users have access to create new Approvals and view Approvals that they have sent and received.</span></span> <span data-ttu-id="4bc73-175">사용자는 요청의 응답자 또는 뷰어가 아니면 다른 사용자가 만든 승인에 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4bc73-175">Users won't have access to Approvals that are created by others unless they're either a responder or a viewer of the request.</span></span>

> [!Note]
> <span data-ttu-id="4bc73-176">사용자가 승인이 만들어진 채팅 또는 채널의 일부인 경우 요청의 뷰어 역할이 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="4bc73-176">A user will be given a viewer role of a request if they are part of the chat or channel where the approval was created.</span></span> <span data-ttu-id="4bc73-177">승인이 생성되었을 때 해당 역할이 부여되지 않은 경우 요청에 대한 조치를 취할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4bc73-177">They won't have the ability to take action on the request if they weren't given that role when the approval was created.</span></span>
