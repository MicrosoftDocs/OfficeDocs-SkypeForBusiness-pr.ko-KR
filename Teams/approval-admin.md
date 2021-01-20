---
title: Teams의 승인 애플리케이션 가용성
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
description: Microsoft Teams의 승인 애플리케이션 가용성에 대해 자세히 배워야 합니다.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: f916b4e794c862a05a42f075ca2f210a079ff42a
ms.sourcegitcommit: fdef9b52247097e5cae64f01b6b2b710c5b203cf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/20/2021
ms.locfileid: "49909522"
---
# <a name="teams-approvals-app-availability"></a><span data-ttu-id="3aaa3-103">Teams 승인 앱 가용성</span><span class="sxs-lookup"><span data-stu-id="3aaa3-103">Teams Approvals app availability</span></span>

<span data-ttu-id="3aaa3-104">승인 앱은 모든 Microsoft Teams 사용자의 개인 앱으로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3aaa3-104">The Approvals app is available as a personal app for all Microsoft Teams users.</span></span>
<span data-ttu-id="3aaa3-105">승인 앱은 Teams에서 구조적 및 비구조적 승인에 감사, 규정 준수, 책임 및 워크플로를 가져오는 간단한 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="3aaa3-105">The Approvals app provides a simple way to bring auditing, compliance, accountability, and workflows to both structured and unstructured Approvals in Teams.</span></span>

 ![승인 앱 표시](media/approvals-selection.png)

<span data-ttu-id="3aaa3-107">사용자는 승인 앱을 고정하여 메뉴 표시줄에 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3aaa3-107">Users can pin the Approvals app to save it to the menu bar.</span></span>

 ![고정 옵션으로 승인 앱 표시](media/approvalApp-pin.png)

<span data-ttu-id="3aaa3-109">승인 앱에서 만든 첫 번째 승인은 기본 CDS(Common Data Service) 환경에서 승인 솔루션의 프로비전을 트리거합니다.</span><span class="sxs-lookup"><span data-stu-id="3aaa3-109">The first approval created from the Approvals app will trigger the provisioning of the Approval Solution in the default Common Data Service (CDS) environment.</span></span> <span data-ttu-id="3aaa3-110">승인 앱에서 만든 승인은 기본 CDS 환경에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="3aaa3-110">Approvals created from the Approvals app will be stored in the default CDS environment.</span></span>

<span data-ttu-id="3aaa3-111">이 문서에서는 승인 앱 요구 사항 및 역할에 대해 설명하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3aaa3-111">This article describes the Approvals app requirements and roles.</span></span>

## <a name="required-permissions-and-licenses"></a><span data-ttu-id="3aaa3-112">필요한 사용 권한 및 라이선스</span><span class="sxs-lookup"><span data-stu-id="3aaa3-112">Required permissions and licenses</span></span>

<span data-ttu-id="3aaa3-113">승인 앱을 사용하려면 다음 항목에 대한 권한이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="3aaa3-113">To use the Approvals app, you need permission for the following items:</span></span>

- <span data-ttu-id="3aaa3-114">Microsoft CDS 데이터베이스를 만들 수 있는 권한.</span><span class="sxs-lookup"><span data-stu-id="3aaa3-114">Permissions to create a Microsoft CDS database.</span></span>

- <span data-ttu-id="3aaa3-115">계정의 [flow.microsoft.com](https://flow.microsoft.com/)</span><span class="sxs-lookup"><span data-stu-id="3aaa3-115">An account on [flow.microsoft.com](https://flow.microsoft.com/)</span></span>

- <span data-ttu-id="3aaa3-116">대상 환경에서 관리자 역할입니다.</span><span class="sxs-lookup"><span data-stu-id="3aaa3-116">Administrator Role in the target environment.</span></span>

- <span data-ttu-id="3aaa3-117">[Power Automate,](https://docs.microsoft.com/power-automate/get-started-approvals)Office 365 또는 Dynamics 365에 대한 라이선스입니다.</span><span class="sxs-lookup"><span data-stu-id="3aaa3-117">License for a [Power Automate](https://docs.microsoft.com/power-automate/get-started-approvals), an Office 365, or a Dynamics 365.</span></span>

## <a name="storage-with-cds"></a><span data-ttu-id="3aaa3-118">CDS를 사용하여 저장소</span><span class="sxs-lookup"><span data-stu-id="3aaa3-118">Storage with CDS</span></span>

<span data-ttu-id="3aaa3-119">CDM(공통 데이터 모델)은 CDS의 비즈니스 및 분석 애플리케이션에서 사용하는 공유 데이터 언어입니다.</span><span class="sxs-lookup"><span data-stu-id="3aaa3-119">The Common Data Model (CDM) is the shared data language used by business and analytical applications in the CDS.</span></span> <span data-ttu-id="3aaa3-120">Microsoft 및 파트너가 게시한 표준화된, 전개할 수 있는 데이터 스마마 집합으로 구성됩니다. 이 집합은 애플리케이션 및 비즈니스 프로세스에서 데이터의 일관성과 의미를 사용할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="3aaa3-120">It consists of a set of a standardized, extensible data schemas published by Microsoft and our partners that enables consistency of data and its meaning across applications and business processes.</span></span> <span data-ttu-id="3aaa3-121">Microsoft Power [Platform의 일반](https://docs.microsoft.com/power-automate/get-started-approvals)데이터 모델에 대해 자세히 알아보고</span><span class="sxs-lookup"><span data-stu-id="3aaa3-121">Learn more about the [Common Data Model of the Microsoft Power Platform](https://docs.microsoft.com/power-automate/get-started-approvals).</span></span>

<span data-ttu-id="3aaa3-122">승인 워크플로에 [대해 자세히 배워야 합니다.](https://docs.microsoft.com/power-automate/modern-approvals)</span><span class="sxs-lookup"><span data-stu-id="3aaa3-122">Learn more about the [Approval workflow](https://docs.microsoft.com/power-automate/modern-approvals).</span></span>

## <a name="approvals-teams-app-permissions"></a><span data-ttu-id="3aaa3-123">승인 Teams 앱 사용 권한</span><span class="sxs-lookup"><span data-stu-id="3aaa3-123">Approvals Teams app permissions</span></span>

<span data-ttu-id="3aaa3-124">승인 팀 앱을 사용하면 다음 기능에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3aaa3-124">The Approvals Teams app lets you access the following features:</span></span>

- <span data-ttu-id="3aaa3-125">사용자에게 제공하는 메시지 및 데이터를 수신합니다.</span><span class="sxs-lookup"><span data-stu-id="3aaa3-125">Receive messages and data that you provide to it.</span></span>

- <span data-ttu-id="3aaa3-126">메시지 및 알림을 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="3aaa3-126">Send you messages and notifications.</span></span>

- <span data-ttu-id="3aaa3-127">Teams에서 제공하는 헤더 없이 개인 앱 및 대화 상자를 렌더링합니다.</span><span class="sxs-lookup"><span data-stu-id="3aaa3-127">Render personal apps and dialogs without a Teams-provided header.</span></span>

- <span data-ttu-id="3aaa3-128">이름, 전자 메일 주소, 회사 이름 및 기본 설정 언어와 같은 프로필 정보에 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="3aaa3-128">Access your profile information such as your name, email address, company name, and preferred language.</span></span>

- <span data-ttu-id="3aaa3-129">팀 구성원이 채널에서 제공하는 메시지 및 데이터를 수신합니다.</span><span class="sxs-lookup"><span data-stu-id="3aaa3-129">Receive messages and data that team members provide to it in a channel.</span></span>

- <span data-ttu-id="3aaa3-130">채널에서 메시지 및 알림을 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="3aaa3-130">Send messages and notifications in a channel.</span></span>

- <span data-ttu-id="3aaa3-131">팀의 정보에 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="3aaa3-131">Access your team's information:</span></span>
  - <span data-ttu-id="3aaa3-132">팀 이름</span><span class="sxs-lookup"><span data-stu-id="3aaa3-132">team name</span></span>
  - <span data-ttu-id="3aaa3-133">채널 목록</span><span class="sxs-lookup"><span data-stu-id="3aaa3-133">channel list</span></span>
  - <span data-ttu-id="3aaa3-134">명단(팀 구성원 이름 및 전자 메일 주소)</span><span class="sxs-lookup"><span data-stu-id="3aaa3-134">roster (team member's names and email addresses).</span></span>

- <span data-ttu-id="3aaa3-135">팀의 정보를 사용하여 연락합니다.</span><span class="sxs-lookup"><span data-stu-id="3aaa3-135">Use the team's information to contact them.</span></span>

## <a name="disable-the-approvals-app"></a><span data-ttu-id="3aaa3-136">승인 앱 사용 안</span><span class="sxs-lookup"><span data-stu-id="3aaa3-136">Disable the Approvals app</span></span>

<span data-ttu-id="3aaa3-137">승인 앱은 기본적으로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3aaa3-137">The Approvals app is available by default.</span></span> <span data-ttu-id="3aaa3-138">Teams 관리 센터에서 앱을 사용하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3aaa3-138">You can disable the app in the Teams admin center.</span></span>

  1. <span data-ttu-id="3aaa3-139">Teams 관리 센터에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="3aaa3-139">Sign in to the Teams admin center.</span></span>

  2. <span data-ttu-id="3aaa3-140">**Teams 앱을 확장하고** 앱 **관리를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="3aaa3-140">Expand **Teams apps** and select **Manage apps**.</span></span>

  3. <span data-ttu-id="3aaa3-141">승인 앱을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="3aaa3-141">Search for the Approvals app.</span></span>

![Teams Apps가 강조 표시된 관리 센터 탐색을 > 앱 관리](media/manage-approval-apps.png)

  4. <span data-ttu-id="3aaa3-143">승인을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3aaa3-143">Select Approvals.</span></span>

  5. <span data-ttu-id="3aaa3-144">조직의 앱을 사용하지 않도록 설정하려면 토글을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3aaa3-144">Select the toggle to disable the app for your organization.</span></span>

![승인 앱에 대한 세부 정보를 보여줍니다.](media/approvals-details.png)

## <a name="retention-policy"></a><span data-ttu-id="3aaa3-146">보존 정책</span><span class="sxs-lookup"><span data-stu-id="3aaa3-146">Retention policy</span></span>

<span data-ttu-id="3aaa3-147">승인 앱에서 만든 승인은 현재 백업을 지원하지 않는 기본 CDS 환경에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="3aaa3-147">Approvals created from the Approvals App are stored in the default CDS environment, which doesn’t support backups at this time.</span></span> <span data-ttu-id="3aaa3-148">환경을 백업 및 복원하는 방법에 대해 자세히 [알아보십시오. Power Platform \| Microsoft Docs](https://docs.microsoft.com/power-platform/admin/backup-restore-environments)</span><span class="sxs-lookup"><span data-stu-id="3aaa3-148">Learn more about how to [Back up and restore environments - Power Platform \| Microsoft Docs](https://docs.microsoft.com/power-platform/admin/backup-restore-environments).</span></span>

## <a name="auditing"></a><span data-ttu-id="3aaa3-149">감사</span><span class="sxs-lookup"><span data-stu-id="3aaa3-149">Auditing</span></span>

<span data-ttu-id="3aaa3-150">승인 앱은 Microsoft 365 보안 및 규정 준수 센터 내에서 감사 이벤트를 기록합니다.</span><span class="sxs-lookup"><span data-stu-id="3aaa3-150">The Approvals App logs audit events within the Microsoft 365 Security and Compliance Center.</span></span> <span data-ttu-id="3aaa3-151">감사 로그를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3aaa3-151">You can view the audit log.</span></span>

1. <span data-ttu-id="3aaa3-152">Microsoft 365 규정 준수 사이트로 이동하세요.</span><span class="sxs-lookup"><span data-stu-id="3aaa3-152">Go to the Microsoft 365 Compliance Site.</span></span>

2. <span data-ttu-id="3aaa3-153">감사 **섹션을** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3aaa3-153">Select the **Audit** section.</span></span>

3. <span data-ttu-id="3aaa3-154">Microsoft Teams 승인 **활동에서 활동을 검색합니다.**</span><span class="sxs-lookup"><span data-stu-id="3aaa3-154">Search for activities under **Microsoft Teams approvals activities**.</span></span>

<span data-ttu-id="3aaa3-155">다음 활동을 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3aaa3-155">You can search for the following activities:</span></span>

- <span data-ttu-id="3aaa3-156">새 승인 요청 만들기</span><span class="sxs-lookup"><span data-stu-id="3aaa3-156">Create new approval request</span></span>

- <span data-ttu-id="3aaa3-157">승인 요청 세부 정보 보기</span><span class="sxs-lookup"><span data-stu-id="3aaa3-157">View approval request details</span></span>

- <span data-ttu-id="3aaa3-158">승인된 승인 요청</span><span class="sxs-lookup"><span data-stu-id="3aaa3-158">Approved approval request</span></span>

- <span data-ttu-id="3aaa3-159">승인 요청 거부</span><span class="sxs-lookup"><span data-stu-id="3aaa3-159">Rejected approval request</span></span>

- <span data-ttu-id="3aaa3-160">승인 요청 취소</span><span class="sxs-lookup"><span data-stu-id="3aaa3-160">Canceled approval request</span></span>

- <span data-ttu-id="3aaa3-161">공유 승인 요청</span><span class="sxs-lookup"><span data-stu-id="3aaa3-161">Shared approval request</span></span>

- <span data-ttu-id="3aaa3-162">승인 요청에 첨부된 파일</span><span class="sxs-lookup"><span data-stu-id="3aaa3-162">File attached to approval request</span></span>

- <span data-ttu-id="3aaa3-163">재할당 승인 요청</span><span class="sxs-lookup"><span data-stu-id="3aaa3-163">Reassigned approval request</span></span>

- <span data-ttu-id="3aaa3-164">승인 요청에 전자 서명 추가</span><span class="sxs-lookup"><span data-stu-id="3aaa3-164">Added e-signature to approval request</span></span>

<span data-ttu-id="3aaa3-165">Flow 내에서 더 많은 감사 승인에 액세스하려면 기본 승인 엔터티 승인, 승인 요청 및 승인 응답에 대한 기본 환경에서 감사를 사용하도록 설정하고 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="3aaa3-165">For access to more auditing approvals within Flow, enable and configure auditing in the default environment for the primary approval entities Approval, Approval Request, and Approval Response.</span></span> <span data-ttu-id="3aaa3-166">만들기, 업데이트 및 삭제 작업은 승인 레코드에 대해 감사할 수 있는 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="3aaa3-166">Create, update, and delete operations are auditable events for Approval records.</span></span> <span data-ttu-id="3aaa3-167">보안 및 규정 준수를 위한 데이터 및 사용자 활동 감사에 대해 자세히 [알아보기 - Power Platform \| Microsoft Docs.](https://docs.microsoft.com/power-platform/admin/audit-data-user-activity)</span><span class="sxs-lookup"><span data-stu-id="3aaa3-167">Learn more about [Audit data and user activity for security and compliance - Power Platform \| Microsoft Docs](https://docs.microsoft.com/power-platform/admin/audit-data-user-activity).</span></span>

<span data-ttu-id="3aaa3-168">[Microsoft 365](https://support.office.com/article/go-to-the-office-365-security-compliance-center-7e696a40-b86b-4a20-afcc-559218b7b1b8?ui=en-US&rs=en-US&ad=US)보안 및 규정 준수 센터에서 감사를 추가로 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3aaa3-168">Auditing can be customized further in the [Microsoft 365 Security and Compliance Center](https://support.office.com/article/go-to-the-office-365-security-compliance-center-7e696a40-b86b-4a20-afcc-559218b7b1b8?ui=en-US&rs=en-US&ad=US).</span></span>

1. <span data-ttu-id="3aaa3-169">미리 구성한 보고서를 사용 하도록 Microsoft 365 보안 및 규정 준수에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="3aaa3-169">To use the preconfigured reports, sign in to Microsoft 365 Security and Compliance.</span></span>

2. <span data-ttu-id="3aaa3-170">검색 **& 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="3aaa3-170">Select **Search & investigation**.</span></span>

3. <span data-ttu-id="3aaa3-171">감사 로그를 검색하고 **Dynamics 365** 활동 탭을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3aaa3-171">Search the Audit log and select the **Dynamics 365 activities** tab.</span></span>

<span data-ttu-id="3aaa3-172">[Microsoft Dataverse](https://docs.microsoft.com/power-platform/admin/enable-use-comprehensive-auditing)및 모델 기반 앱 활동 로깅에 대한 자세한 정보 - Power Platform.</span><span class="sxs-lookup"><span data-stu-id="3aaa3-172">Learn more about [Microsoft Dataverse and model-driven apps activity logging - Power Platform](https://docs.microsoft.com/power-platform/admin/enable-use-comprehensive-auditing).</span></span>

## <a name="security"></a><span data-ttu-id="3aaa3-173">보안</span><span class="sxs-lookup"><span data-stu-id="3aaa3-173">Security</span></span>

<span data-ttu-id="3aaa3-174">Teams 승인 앱에서 사용자는 새 승인을 만들고 보내고 받은 승인을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3aaa3-174">From the Teams Approvals app, users have access to create new Approvals and view Approvals that they have sent and received.</span></span> <span data-ttu-id="3aaa3-175">사용자가 요청의 응답자 또는 뷰어가 아니면 다른 사용자가 만든 승인에 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3aaa3-175">Users won't have access to Approvals that are created by others unless they're either a responder or a viewer of the request.</span></span>

> [!Note]
> <span data-ttu-id="3aaa3-176">사용자가 승인이 만들어진 채팅 또는 채널의 일부인 경우 요청의 뷰어 역할을 부여합니다.</span><span class="sxs-lookup"><span data-stu-id="3aaa3-176">A user will be given a viewer role of a request if they are part of the chat or channel where the approval was created.</span></span> <span data-ttu-id="3aaa3-177">승인을 만들 때 해당 역할을 부여하지 않은 경우 요청에 대해 조치를 취할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3aaa3-177">They won't have the ability to take action on the request if they weren't given that role when the approval was created.</span></span>
