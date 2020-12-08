---
title: Teams에 대한 과제
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
search.appverid: MET150
ms.reviewer: jastark
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.assignments.overview
- ms.teamsadmincenter.assignments.tooltip.emaildigest
- ms.teamsadmincenter.assignments.tooltip.makecode
- ms.teamsadmincenter.assignments.tooltip.turnitin
description: 교육용 Teams의 Microsoft Teams 관리 센터에서 과제를 관리하는 방법을 배워야 합니다.
localization_priority: Normal
appliesto:
- Microsoft Teams
ms.openlocfilehash: 64be355da30feb3c629569f583897353c21cfa37
ms.sourcegitcommit: 481d18b76304adfa340b5f1b2f1b7965e9ff4993
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/07/2020
ms.locfileid: "49586621"
---
# <a name="assignments-in-teams-for-education"></a><span data-ttu-id="a7274-103">교육용 Teams의 과제</span><span class="sxs-lookup"><span data-stu-id="a7274-103">Assignments in Teams for Education</span></span>

<span data-ttu-id="a7274-104">교육용 Teams의 과제 및 성적 기능을 통해 강사는 학생들에게 작업, 작업 또는 퀴즈를 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a7274-104">The Assignments and Grades features in Teams for Education allow educators to assign tasks, work, or quizzes to their students.</span></span> <span data-ttu-id="a7274-105">강사는 과제 타임라인, 지침, 제출할 리소스 추가, 채점기한 채점 등 다양한 기능을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a7274-105">Educators can manage assignment timelines, instructions, add resources to turn in, grade with rubrics, and more.</span></span> <span data-ttu-id="a7274-106">성적 탭에서 수업 및 개별 학생의 진행 상황을 추적할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a7274-106">They can also track class and individual student progress in the Grades tab.</span></span>

<span data-ttu-id="a7274-107">[교육용 Teams에서](https://support.office.com/article/microsoft-teams-5aa4431a-8a3c-4aa5-87a6-b6401abea114?ui=en-US&rs=en-IE&ad=IE#ID0EAABAAA=Assignments)과제 및 성적에 대해 자세히 알아보고</span><span class="sxs-lookup"><span data-stu-id="a7274-107">[Learn more about Assignments and Grades in Teams for Education](https://support.office.com/article/microsoft-teams-5aa4431a-8a3c-4aa5-87a6-b6401abea114?ui=en-US&rs=en-IE&ad=IE#ID0EAABAAA=Assignments).</span></span>

> [!Note]
> <span data-ttu-id="a7274-108">다른 플랫폼의 Teams 할당에 대한 자세한 내용은 플랫폼에 따라 [Teams 기능을 참조하세요.](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3)</span><span class="sxs-lookup"><span data-stu-id="a7274-108">For details about Teams assignments on different platforms, see [Teams features by platform](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3).</span></span>

## <a name="assignments-integrations-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="a7274-109">Microsoft Teams 관리 센터의 과제 통합</span><span class="sxs-lookup"><span data-stu-id="a7274-109">Assignments integrations in the Microsoft Teams admin center</span></span>

<span data-ttu-id="a7274-110">Microsoft Teams 관리 센터에서 관리자 설정을 사용하여 조직 및 학생 내의 강사에 대한 기능을 설정하거나 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a7274-110">Using the admin settings in the Microsoft Teams admin center, you can turn features on or off for educators within your organization and their students.</span></span> <span data-ttu-id="a7274-111">다음은 할당과 관련된 설정입니다.</span><span class="sxs-lookup"><span data-stu-id="a7274-111">The following are settings related to Assignments:</span></span>

<span data-ttu-id="a7274-112"><a name="#bkemaildigest"> </a></span><span class="sxs-lookup"><span data-stu-id="a7274-112"><a name="#bkemaildigest"> </a></span></span>
### <a name="weekly-guardian-email-digest"></a><span data-ttu-id="a7274-113">주간 보호자 전자 메일 다이제스트</span><span class="sxs-lookup"><span data-stu-id="a7274-113">Weekly guardian email digest</span></span>


<span data-ttu-id="a7274-114">보호자 전자 메일은 주말마다 부모 또는 보호자에게 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="a7274-114">Guardian emails are sent each weekend to parents or guardians.</span></span> <span data-ttu-id="a7274-115">전자 메일에는 이전 주 및 다음 주에 대한 과제에 대한 정보가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a7274-115">The email contains information about assignments from the previous week and for the upcoming week.</span></span> <span data-ttu-id="a7274-116">School Data Sync를 사용하여 부모 및 보호자 [동기화를 설정하면 됩니다.](https://docs.microsoft.com/schooldatasync/parent-contact-sync)</span><span class="sxs-lookup"><span data-stu-id="a7274-116">The Parent and Guardian Sync can be setup using [School Data Sync](https://docs.microsoft.com/schooldatasync/parent-contact-sync).</span></span>

1. <span data-ttu-id="a7274-117">SDS에서 부모 및 보호자 동기화를 통해 부모 연락처 정보를 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a7274-117">Import parent contact information via Parent and Guardian Sync in SDS.</span></span> <span data-ttu-id="a7274-118">부모 및 보호자 동기화를 사용하도록 설정하는 방법에 대한 지침은 부모 및 보호자 동기화 [활성화를 참조하세요.](https://docs.microsoft.com/schooldatasync/parent-contact-sync#enabling-parent-and-guardian-sync)</span><span class="sxs-lookup"><span data-stu-id="a7274-118">For instructions on how to enable Parent and Guardian Sync, see [Enabling Parent and Guardian Sync](https://docs.microsoft.com/schooldatasync/parent-contact-sync#enabling-parent-and-guardian-sync).</span></span>

2. <span data-ttu-id="a7274-119">설정이 기본적으로 해제되어 있는 Microsoft Teams 관리 센터에서 보호자 설정을 켜면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a7274-119">Turn on the Guardian Setting in the Microsoft Teams admin center, as the setting is turned off by default.</span></span> <span data-ttu-id="a7274-120">이렇게 하면 교사가 주간 다이제스트를 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a7274-120">This will enable teachers to send out a weekly digest.</span></span>

   > [!NOTE]
   > <span data-ttu-id="a7274-121">교사는 자신의 개인 수업 팀 내에서 설정을 선택 해제하여 다이제스트를 옵트아웃할 수 있습니다(학부모/보호자 전자 메일에 > 설정).**Assignment Settings > Parent/Guardian Emails**</span><span class="sxs-lookup"><span data-stu-id="a7274-121">Teachers can opt-out of the digest by deselecting the setting inside their own personal class team (**Assignment Settings > Parent/Guardian Emails**).</span></span>

<span data-ttu-id="a7274-122">부모가 전자 메일을 받을지 확인하려면 다음 세 가지 항목이 true가 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7274-122">To verify that Parents will get the email the following three items must be true:</span></span>

 - <span data-ttu-id="a7274-123">SDS에서 학생 프로필에 첨부되어 있으며 부모 또는 보호자로 _태그가_ 지정된 전자 메일 _주소입니다._</span><span class="sxs-lookup"><span data-stu-id="a7274-123">Email address attached to the student profile in SDS and tagged as _Parent_ or _Guardian_.</span></span> <span data-ttu-id="a7274-124">자세한 내용은 부모 및 보호자 동기화 [파일 형식을 참조합니다.](https://docs.microsoft.com/schooldatasync/parent-contact-sync-file-format)</span><span class="sxs-lookup"><span data-stu-id="a7274-124">For details, see [Parent and Guardian Sync File Format](https://docs.microsoft.com/schooldatasync/parent-contact-sync-file-format).</span></span>

 - <span data-ttu-id="a7274-125">학생은 과제 설정에서 교사가 전자 메일을 사용할 수 없는 하나 이상의 [수업에 속합니다.](https://support.microsoft.com/office/adjust-assignment-settings-in-your-class-team-05bb3b89-1cdf-415a-b6c7-44add0376a77)</span><span class="sxs-lookup"><span data-stu-id="a7274-125">Students belong to at least one class in which e-mail is not disabled by the teacher in [assignment settings](https://support.microsoft.com/office/adjust-assignment-settings-in-your-class-team-05bb3b89-1cdf-415a-b6c7-44add0376a77).</span></span>

 - <span data-ttu-id="a7274-126">전자 메일에는 지난 주 또는 다음 주에 기한이 있는 과제에 대한 정보가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a7274-126">The emails will contain information about assignments that had a due date in the previous week or in the upcoming week.</span></span>

<span data-ttu-id="a7274-127">이 기능에 대한 기본 설정은 - **끄기입니다.**</span><span class="sxs-lookup"><span data-stu-id="a7274-127">Default setting for this feature is - **Off**.</span></span>


<span data-ttu-id="a7274-128"><a name="bkmakecode"> </a></span><span class="sxs-lookup"><span data-stu-id="a7274-128"><a name="bkmakecode"> </a></span></span>
### <a name="makecode"></a><span data-ttu-id="a7274-129">MakeCode</span><span class="sxs-lookup"><span data-stu-id="a7274-129">MakeCode</span></span>
<span data-ttu-id="a7274-130">Microsoft MakeCode는 모든 학생에게 컴퓨터 과학을 생생하게 전하는 블록 기반 코딩 플랫폼입니다.</span><span class="sxs-lookup"><span data-stu-id="a7274-130">Microsoft MakeCode is a block-based coding platform that brings computer science to life for all students.</span></span> 

<span data-ttu-id="a7274-131">MakeCode는 Microsoft 사용 약관 및 개인 정보 취급 방침이 적용된 [Microsoft](https://go.microsoft.com/fwlink/?LinkID=206977) [제품입니다.](https://go.microsoft.com/fwlink/?LinkId=521839)</span><span class="sxs-lookup"><span data-stu-id="a7274-131">MakeCode is a Microsoft product that is subject to the Microsoft [terms of use](https://go.microsoft.com/fwlink/?LinkID=206977) and [privacy](https://go.microsoft.com/fwlink/?LinkId=521839) policies.</span></span>

<span data-ttu-id="a7274-132">이 기능에 대한 기본 설정은 - **끄기입니다.**</span><span class="sxs-lookup"><span data-stu-id="a7274-132">Default setting for this feature is - **Off**.</span></span>

<span data-ttu-id="a7274-133">Teams에서 MakeCode 할당을 사용하도록 설정하려면 **Teams** 관리 센터로 이동하여 과제 섹션으로 이동한 다음 MakeCode 토글 옵션을 **켜기로 전환합니다.** **Assignments**</span><span class="sxs-lookup"><span data-stu-id="a7274-133">To enable MakeCode assignments in Teams, go to the **Teams Admin Center**, navigate to the **Assignments** section, and turn the MakeCode toggle option to **On**.</span></span> <span data-ttu-id="a7274-134">**저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a7274-134">Click **Save**.</span></span> <span data-ttu-id="a7274-135">이러한 설정이 적용되는 데 몇 시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a7274-135">Allow a few hours for these settings to take effect.</span></span>

<span data-ttu-id="a7274-136">이 기능의 작동 방식에 대한 자세한 내용은 이 비디오 [데모를 참조하세요.](https://makecode.com/blog/teams/teams-assignments)</span><span class="sxs-lookup"><span data-stu-id="a7274-136">For more information on how this feature works, see this [video demonstration](https://makecode.com/blog/teams/teams-assignments).</span></span>

<span data-ttu-id="a7274-137">[MakeCode에 대해 자세히 알아보고](https://aka.ms/makecode)</span><span class="sxs-lookup"><span data-stu-id="a7274-137">[Learn more about MakeCode](https://aka.ms/makecode).</span></span>

<span data-ttu-id="a7274-138"><a name="#turnitin"> </a></span><span class="sxs-lookup"><span data-stu-id="a7274-138"><a name="#turnitin"> </a></span></span>
### <a name="turnitin"></a><span data-ttu-id="a7274-139">Turnitin</span><span class="sxs-lookup"><span data-stu-id="a7274-139">Turnitin</span></span>

<span data-ttu-id="a7274-140">[Turnitin은](https://www.turnitin.com/) 교육용 무결성 서비스입니다.</span><span class="sxs-lookup"><span data-stu-id="a7274-140">[Turnitin](https://www.turnitin.com/) is an academic integrity service.</span></span> <span data-ttu-id="a7274-141">자체 약관 및 개인 정보 취급 방침이 적용된 타사 제품 또는 서비스입니다.</span><span class="sxs-lookup"><span data-stu-id="a7274-141">This is a third-party product or service that is subject to its own terms and privacy policy.</span></span> <span data-ttu-id="a7274-142">귀하는 제3자 제품 및 서비스를 사용할 책임이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a7274-142">You are responsible for your use of any third-party products and services.</span></span>

<span data-ttu-id="a7274-143">이 기능에 대한 기본 설정은 **끄기입니다.**</span><span class="sxs-lookup"><span data-stu-id="a7274-143">Default setting for this feature is - **Off**..</span></span>

<span data-ttu-id="a7274-144">조직에 대해 Turnitin을 사용하도록 설정하려면 Turnitin 구독이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="a7274-144">To enable Turnitin for your organization, you will need a Turnitin subscription.</span></span> <span data-ttu-id="a7274-145">그런 다음 Turnitin 관리 콘솔에서 찾을 수 있는 다음 정보를 입력할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a7274-145">Then you can input the following information, which can be found in your Turnitin admin console:</span></span>

  * <span data-ttu-id="a7274-146">**TurnitinApiKey:** 통합의 관리 콘솔에 있는 32자 GUID입니다.</span><span class="sxs-lookup"><span data-stu-id="a7274-146">**TurnitinApiKey**: This is a 32-character GUID found in the admin console under Integrations.</span></span>
  * <span data-ttu-id="a7274-147">**TurnitinApiUrl:** Turnitin 관리 콘솔의 HTTPS URL입니다.</span><span class="sxs-lookup"><span data-stu-id="a7274-147">**TurnitinApiUrl**: This is the HTTPS URL of your Turnitin admin console.</span></span>

<span data-ttu-id="a7274-148">이 정보를 얻는 데 도움이 되는 몇 가지 지침은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="a7274-148">Here are some instructions to help you obtain this information.</span></span>

<span data-ttu-id="a7274-149">**TurnitinApiUrl은** 관리 콘솔의 호스트 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="a7274-149">The **TurnitinApiUrl** is the host address of your admin console.</span></span>
<span data-ttu-id="a7274-150">예: `https://your-tenant-name.turnitin.com`</span><span class="sxs-lookup"><span data-stu-id="a7274-150">Example: `https://your-tenant-name.turnitin.com`</span></span>

<span data-ttu-id="a7274-151">관리 콘솔은 통합과 연결된 API 키와 통합을 만들 수 있는 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="a7274-151">The admin console is where you can create an integration and an API key associated with the integration.</span></span>

<span data-ttu-id="a7274-152">측면 **메뉴에서** 통합을 선택한 다음 통합 **추가를** 선택하고 통합에 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="a7274-152">Select **Integrations** from the side menu, then select **Add Integration** and give the integration a name.</span></span>

![새 통합 추가를 보여주는 스크린샷](./educationImages/Assignments_mopo_turnitin2.png)

<span data-ttu-id="a7274-154">프롬프트를 따라가면 **TurnitinApiKey가** 부여됩니다.</span><span class="sxs-lookup"><span data-stu-id="a7274-154">The **TurnitinApiKey** will be given to you after you follow the prompts.</span></span> <span data-ttu-id="a7274-155">API 키를 복사하여 Microsoft Teams 관리 센터에 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="a7274-155">Copy the API key and paste it into the Microsoft Teams admin center.</span></span>  <span data-ttu-id="a7274-156">키를 볼 수 있는 유일한 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="a7274-156">This is the only time you can view the key.</span></span>

![API 키 복사를 보여주는 스크린샷](./educationImages/Assignments_mopo_turnitin3.png)

<span data-ttu-id="a7274-158">이 설정에 **대한** 관리 센터에서 저장 단추를 클릭하면 이러한 설정이 적용되는 데 몇 시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a7274-158">Upon clicking the **Save** button in the admin center for this setting, allow a few hours for these settings to take effect.</span></span>

