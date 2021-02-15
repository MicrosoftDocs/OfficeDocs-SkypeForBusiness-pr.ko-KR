---
title: 비즈니스용 Skype 서버 2015의 초기 토폴로지 디자인 만들기
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 4/5/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: f3131153-de14-41be-b1e6-7d4bb0191af1
description: 비즈니스용 Skype 서버 계획 도구 설치를 마치면 계획 도구를 시작하고 제안된 비즈니스용 Skype 서버 2015 인프라 디자인을 시작할 수 있습니다.
ms.openlocfilehash: 7de930de8d7e194f14145c1a976fbe6b96cf234a
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49834968"
---
# <a name="create-the-initial-topology-design-for-skype-for-business-server-2015"></a><span data-ttu-id="d917e-103">비즈니스용 Skype 서버 2015의 초기 토폴로지 디자인 만들기</span><span class="sxs-lookup"><span data-stu-id="d917e-103">Create the initial topology design for Skype for Business Server 2015</span></span>

<span data-ttu-id="d917e-104">비즈니스용 Skype 서버 계획 도구 설치를 마치면 계획 도구를 시작하고 제안된 비즈니스용 Skype 서버 2015 인프라 디자인을 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d917e-104">After you have finished installing the Skype for Business Server Planning Tool, you are ready to start the Planning Tool and begin designing the proposed Skype for Business Server 2015 infrastructure.</span></span>

> [!NOTE]
>  <span data-ttu-id="d917e-105">계획 도구는 사이트 및 토폴로지 디자인 시 의사 결정 프로세스를 알리는 자세한 가이드가 있는 마법사 기반 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="d917e-105">The Planning Tool is a wizard-driven tool with detailed guides to inform your decision-making process in designing your sites and topology.</span></span> <span data-ttu-id="d917e-106">이 항목은 모든 가이드가 아니라 디자인 세션에서 계획 도구를 사용할 수 있도록 도와주기 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="d917e-106">This topic is intended not as an exhaustive guide, but simply to help get you started using the Planning Tool in your design sessions.</span></span>

### <a name="to-get-started-using-the-planning-tool-and-create-the-initial-design"></a><span data-ttu-id="d917e-107">계획 도구 사용을 시작하고 초기 디자인을 만들하려면</span><span class="sxs-lookup"><span data-stu-id="d917e-107">To get started using the Planning Tool and create the initial design</span></span>

1. <span data-ttu-id="d917e-108">비즈니스용 Skype 서버 2015 계획 도구 시작: **시작,** **모든** 프로그램, 비즈니스용 Skype **서버 2015,** 계획 **도구를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="d917e-108">Start the Skype for Business Server 2015 Planning Tool: Click **Start**, click **All Programs**, click **Skype for Business Server 2015**, and then click **Planning Tool**.</span></span>

2. <span data-ttu-id="d917e-109">계획 도구가 시작된 후 비즈니스용 Skype 서버 **2015** 계획 도구 시작 페이지가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="d917e-109">After the Planning Tool has started, the **Welcome to the Planning Tool for Skype for Business Server 2015** page appears.</span></span> <span data-ttu-id="d917e-110">다음 옵션 중 하나를 선택하면 디자인을 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d917e-110">Choose one of the following options to begin your design:</span></span>

   - <span data-ttu-id="d917e-111">**옵션 1: 시작** 시작을 **클릭하면** 조건을 정의하기 위한 관련 선택과 함께 특정 일련의 인터뷰 질문이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d917e-111">**Option 1: Get Started** Clicking **Get Started** provides a specific series of interview questions with relevant selections to define the criteria.</span></span> <span data-ttu-id="d917e-112">초기 시작 인터뷰 섹션을 완료한 후 디자인  사이트로 진행하여 사이트 아키텍처를 정의합니다. </span><span class="sxs-lookup"><span data-stu-id="d917e-112">After you have finished the initial **Get Started** interview section, you proceed into **Design Sites** to define your site architecture.</span></span> <span data-ttu-id="d917e-113">이 옵션을 완료하기 위해 3단계로 진행합니다.</span><span class="sxs-lookup"><span data-stu-id="d917e-113">To complete this option, proceed to step 3.</span></span>

   - <span data-ttu-id="d917e-114">**옵션 2: 사이트 디자인** 시작 **페이지에서 사이트를** 디자인하면 시작 섹션에 제시된 인터뷰 질문이 **무시됩니다.**</span><span class="sxs-lookup"><span data-stu-id="d917e-114">**Option 2: Design Sites** Clicking **Design Sites** at the Welcome page bypasses the interview questions presented in the **Get Started** section.</span></span> <span data-ttu-id="d917e-115">시작 섹션의 인터뷰 질문에 응답하여 수집된 정보는  이 옵션을 사용하여 기본값으로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="d917e-115">The information that would have been gathered by responding to the interview questions in **Get Started** section is set to default values with this option.</span></span> <span data-ttu-id="d917e-116">숙련된 디자이너는 디자인 사이트를 클릭하여 초기 인터뷰를 무시하고 필요한 경우 중앙 사이트 시작 페이지에서 기본값을 변경할 **수** 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d917e-116">By clicking **Design Sites**, the experienced designer can bypass the initial interview and change the default values, as needed, on the **Central Sites** start page.</span></span> <span data-ttu-id="d917e-117">이 옵션을 완료하기 위해 3-5단계를 건너뛰고 6단계에서 시작하십시오.</span><span class="sxs-lookup"><span data-stu-id="d917e-117">To complete this option, skip over steps 3-5 and start at step 6.</span></span>

   - <span data-ttu-id="d917e-118">**옵션 3: 저장된 토폴로지 표시** 계획 도구를 이전으로 사용하여 토폴로지가 이미 완료 및 저장된 경우 이러한 대부분의 단계를 건너뛰고 토폴로지 열기 및 표시로 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d917e-118">**Option 3: Display Your Saved Topology** If you have already completed and saved a topology through previous use of the Planning Tool, you can skip over most of these steps and start by opening and displaying the topology.</span></span> <span data-ttu-id="d917e-119">또한 토폴로지의 변경 및 업데이트를 적용하고 다시 프레이브한 다음 Microsoft Excel 또는 Microsoft Visio로 내보낼 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d917e-119">You can also make changes and updates to the topology, resave it, and then export it to Microsoft Excel or Microsoft Visio.</span></span> <span data-ttu-id="d917e-120">이 옵션을 완료하기 위해 3-12단계를 건너뛰고 13단계에서 시작하십시오.</span><span class="sxs-lookup"><span data-stu-id="d917e-120">To complete this option, skip over steps 3-12 and start at step 13.</span></span>

3. <span data-ttu-id="d917e-121">**시작을** 클릭하여 비즈니스용 Skype 서버 2015 토폴로지 디자인 시작을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d917e-121">Click **Get Started** to begin designing your Skype for Business Server 2015 topology.</span></span>

4. <span data-ttu-id="d917e-122">디자인에 적절한 조건을 선택하여 각 섹션에 응답한  다음 다음을 클릭하여 다음 마법사 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="d917e-122">Answer each section by selecting the appropriate criteria for your design, and then click **Next** to proceed to the next Wizard page.</span></span> <span data-ttu-id="d917e-123">**뒤로를** 클릭하여 이전 페이지에서 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="d917e-123">Click **Back** to make changes on previous pages.</span></span>

    > [!TIP]
    > <span data-ttu-id="d917e-124">각 페이지에는 선택 기준에 대한 설명과 기본 설정 방법 및 용량 계획에 기반한 권장 사항이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d917e-124">Each page has a description of the selection criteria, and recommendations based on preferred practices and capacity planning.</span></span> <span data-ttu-id="d917e-125">추가 세부 정보가 필요한  경우 자세한 내용을 클릭하여 Microsoft 웹 사이트의 비즈니스용 Skype 서버 2015 계획 설명서에서 자세한 정보를 읽어 보아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d917e-125">If you require additional details, click **Learn more** to read detailed information from the Skype for Business Server 2015 Planning documentation on the Microsoft  website.</span></span> <span data-ttu-id="d917e-126">Microsoft 웹 사이트에 액세스하려면 인터넷에 연결해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d917e-126">You must have Internet connectivity to access the Microsoft  website.</span></span>

5. <span data-ttu-id="d917e-127">디자인에 적합한 옵션을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d917e-127">Select the appropriate options for your design.</span></span> <span data-ttu-id="d917e-128">초기 조건이 정의되면 페이지가 기능 개요가 완료된 것을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d917e-128">After the initial criteria are defined, a page will confirm that your Features Overview is complete.</span></span>

6. <span data-ttu-id="d917e-129">사이트 **디자인을 클릭하여** 중앙 사이트를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="d917e-129">Click **Design Sites** to define your central site.</span></span>

    > [!NOTE]
    > <span data-ttu-id="d917e-130">각 비즈니스용 Skype 서버 2015 토폴로지에는 하나 이상의 중앙 사이트가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d917e-130">Each Skype for Business Server 2015 topology will have at least one central site.</span></span> <span data-ttu-id="d917e-131">디자인에는 단일 중앙 사이트, 여러 분기 사이트가 있는 중앙 사이트, 여러 중앙 사이트 또는 각 중앙 사이트와 연결된 분기 사이트가 있는 여러 중앙 사이트가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d917e-131">Your design may have a single central site, a central site with a number of branch sites, a number of central sites, or a number of central sites with branch sites associated with each central site.</span></span>

7. <span data-ttu-id="d917e-132">사이트 **이름에** 이 중앙 사이트를 식별할 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="d917e-132">In **Site Name**, type the name that will identify this central site.</span></span>

8. <span data-ttu-id="d917e-133">사이트 **홈 사용자에** 이 중앙 사이트에 있을 예상되는 On-premises 동시 사용자 수를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="d917e-133">In **Site Homed Users**, type the expected number of on-premises concurrent users who will be homed in this central site.</span></span>

9. <span data-ttu-id="d917e-134">클라우드 **홈 사용자에** 이 중앙 사이트에 있을 온라인 동시 사용자의 예상 수를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="d917e-134">In **Cloud Homed Users**, type the expected number of online concurrent users who will be homed in this central site.</span></span>

10. <span data-ttu-id="d917e-135">필요한 경우 온라인 공동 작업, 사용자, 음성, 추가 배포 옵션 또는 서버 응용 프로그램에 대한 선택을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="d917e-135">Modify the selections for Online Collaboration, Users, Voice, Additional Deployment Options, or Server Applications, as needed.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="d917e-136">디자인의 이 시점에서는 배포에 대한 옵션만 선택하거나 선택을 취소할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d917e-136">At this point in the design, you can only select or clear options for your deployment.</span></span> <span data-ttu-id="d917e-137">그러나 계획 도구의 이후 단계에서 더 많은 옵션을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d917e-137">However, you can configure more options in a later phase of the Planning Tool.</span></span> <span data-ttu-id="d917e-138">사용할 수 없거나 지울 수 없는 옵션도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d917e-138">There are also options that are unavailable and cannot be cleared.</span></span> <span data-ttu-id="d917e-139">또한 다른 옵션을 지우기 위해 하나의 옵션을 선택 취소해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d917e-139">In addition, you may have to clear one option in order to clear another.</span></span> <span data-ttu-id="d917e-140">예를 들어 음성에서  Enterprise Voice 옵션을 선택 취소하면 서버 응용 프로그램  아래에 있는 응답 그룹, 공지 및 통화 파크 옵션(모두 Enterprise Voice)도 지워지게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d917e-140">For example, if you clear the **Enterprise Voice** option under Voice, then the **Response Group**, **Announcement**, and **Call Park** options under Server Applications (all of which are features of Enterprise Voice) are also cleared.</span></span>

11. <span data-ttu-id="d917e-141">사이트 이름 및 사용자 수를 정의한 후 다음을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="d917e-141">After defining a site name and number of users, click **Next**.</span></span>

12. <span data-ttu-id="d917e-142">다음 페이지에서는 SIP 도메인, 회의 설정, 음성 설정 및 인프라, Exchange UM, 외부 사용자 액세스, 영구 채팅 설정, 클라이언트 설정, 지정 옵션 및 분기 사이트에 대한 정보를 요청합니다.</span><span class="sxs-lookup"><span data-stu-id="d917e-142">The following pages ask for information about SIP domains, conference settings, voice settings and infrastructure, Exchange UM, external user access, Persistent Chat settings, client settings, collocation options, and branch sites.</span></span> <span data-ttu-id="d917e-143">이러한 질문에 적절하게 답변하세요.</span><span class="sxs-lookup"><span data-stu-id="d917e-143">Answer these questions as appropriate.</span></span>

13. <span data-ttu-id="d917e-144">마지막 질문은 다른 중앙 사이트를 만들지 묻습니다.</span><span class="sxs-lookup"><span data-stu-id="d917e-144">The final question asks if you want to create another central site.</span></span> <span data-ttu-id="d917e-145">**'예'를** 선택하면 계획 도구가 중앙 사이트 페이지로 돌아온다.</span><span class="sxs-lookup"><span data-stu-id="d917e-145">If you select **Yes**, then the Planning Tool returns to the Central Sites page.</span></span> <span data-ttu-id="d917e-146">아니요를 선택한  **경우** 다음을 클릭한 다음 그리기(그리기)를 클릭하여 상위 수준 전역 토폴로지 보기를 표시합니다. </span><span class="sxs-lookup"><span data-stu-id="d917e-146">If you select **No**, click **Next**, and then click **Draw** to display the high-level Global Topology view.</span></span>

14. <span data-ttu-id="d917e-147">기존 토폴로지 보려면 표시를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="d917e-147">To view an existing topology, click **Display**.</span></span>

15. <span data-ttu-id="d917e-148">이전에 저장한 토폴로지의 .xml 파일을 클릭한 다음 **열기 를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="d917e-148">Click the .xml file that represents the previously saved topology, and then click **Open**.</span></span>

16. <span data-ttu-id="d917e-149">계획 도구에 전역 토폴로지 페이지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d917e-149">The Planning Tool displays the Global Topology page.</span></span> <span data-ttu-id="d917e-150">이제 계획 도구에서 사용할 수 있는 도구를 사용하여 토폴로지 편집, 업데이트 또는 변경을 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d917e-150">You can now begin editing, updating, or changing the topology by using the tools available in the Planning Tool.</span></span>

## <a name="see-also"></a><span data-ttu-id="d917e-151">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d917e-151">See also</span></span>

[<span data-ttu-id="d917e-152">디자인 편집</span><span class="sxs-lookup"><span data-stu-id="d917e-152">Editing the Design</span></span>](https://technet.microsoft.com/library/08f639ba-0e5f-4ae7-9191-c3d96c25b169.aspx)
