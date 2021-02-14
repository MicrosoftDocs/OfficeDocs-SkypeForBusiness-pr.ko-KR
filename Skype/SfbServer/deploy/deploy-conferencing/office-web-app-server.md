---
title: 비즈니스용 Skype 서버에서 Office Web Apps 서버와의 통합 구성
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b7e9149e-bf16-4120-afe0-3ee09c88f5eb
description: '요약: 웹 회의에 PowerPoint 프레젠테이션을 사용하도록 Office Web Apps 서버와 비즈니스용 Skype 서버 간의 통합을 구성하는 방법을 알아보는 이 항목을 참조하세요.'
ms.openlocfilehash: 005bd9fe7d7fece7d488935002e7146fc5a9ffe4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49820468"
---
# <a name="configure-integration-with-office-web-apps-server-in-skype-for-business-server"></a><span data-ttu-id="361d6-103">비즈니스용 Skype 서버에서 Office Web Apps 서버와의 통합 구성</span><span class="sxs-lookup"><span data-stu-id="361d6-103">Configure integration with Office Web Apps Server in Skype for Business Server</span></span>
 
<span data-ttu-id="361d6-104">**요약:** 웹 회의에 PowerPoint 프레젠테이션을 사용하도록 Office Web Apps 서버와 비즈니스용 Skype 서버 간의 통합을 구성하는 방법을 알아보는 이 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="361d6-104">**Summary:** Read this topic to learn how to configure integration between Office Web Apps Server and Skype for Business Server to enable PowerPoint presentations for web conferencing.</span></span>
  
<span data-ttu-id="361d6-105">비즈니스용 Skype 서버는 Office Web Apps 서버를 사용하여 웹 회의에 대한 PowerPoint 프레젠테이션을 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="361d6-105">Skype for Business Server employs Office Web Apps Server to handle PowerPoint presentations for web conferencing.</span></span> <span data-ttu-id="361d6-106">이 방법의 이점에 대한 자세한 내용은 비즈니스용 Skype 서버의 회의 [계획(Plan for conferencing)을 참조하십시오.](../../plan-your-deployment/conferencing/conferencing.md)</span><span class="sxs-lookup"><span data-stu-id="361d6-106">For information about the advantages to this approach, see [Plan for conferencing in Skype for Business Server](../../plan-your-deployment/conferencing/conferencing.md).</span></span>
  
<span data-ttu-id="361d6-107">Office Web Apps 서버를 사용하도록 비즈니스용 Skype 서버를 구성하려면 먼저 Office Web Apps 서버가 이미 배포 및 구성되어 있는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="361d6-107">Before you can configure Skype for Business Server to use Office Web Apps Server, you must ensure that Office Web Apps Server is already deployed and configured.</span></span> <span data-ttu-id="361d6-108">Office Web Apps 서버에 대한 자세한 내용은 인프라 [배포: Office Online Server 문서를 참조하십시오.](https://go.microsoft.com/fwlink/p/?linkid=257525)</span><span class="sxs-lookup"><span data-stu-id="361d6-108">For information on Office Web Apps Server, see the article [Deploy the infrastructure: Office Online Server](https://go.microsoft.com/fwlink/p/?linkid=257525).</span></span> 
  
<span data-ttu-id="361d6-109">Office Web Apps 서버를 성공적으로 설치하고 웹 팜을 올바르게 구성한 후 비즈니스용 Skype 서버 토폴로지에서 Office Web Apps 서버 검색 URL을 비즈니스용 Skype 서버 토폴로지에 추가하여 새 서버와 통신하도록 비즈니스용 Skype 서버를 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="361d6-109">After Office Web Apps Server has been successfully installed and your Web farm correctly configured, you must then configure Skype for Business Server to communicate with the new server by adding the Office Web Apps Server discovery URL to your Skype for Business Server topology.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="361d6-110">Office Web Apps 서버의 최신 이니션은 비즈니스용 Skype 서버에서 지원되는 Office Online Server입니다.</span><span class="sxs-lookup"><span data-stu-id="361d6-110">The latest iteration of Office Web Apps Server is named Office Online Server, which is supported by Skype for Business Server.</span></span> <span data-ttu-id="361d6-111">자세한 내용은 [Office Online Server 설명서를 참조하십시오.](https://technet.microsoft.com/library/jj219456%28v=office.16%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="361d6-111">For more detail, refer to the [Office Online Server documentation](https://technet.microsoft.com/library/jj219456%28v=office.16%29.aspx).</span></span> 
  
## <a name="configure-skype-for-business-server-to-communicate-with-office-web-apps-server"></a><span data-ttu-id="361d6-112">Office Web Apps 서버와 통신하도록 비즈니스용 Skype 서버 구성</span><span class="sxs-lookup"><span data-stu-id="361d6-112">Configure Skype for Business Server to communicate with Office Web Apps Server</span></span>

<span data-ttu-id="361d6-113">토폴로지에 Office Web Apps 서버를 추가하기 위해 다음 단계를 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="361d6-113">To add Office Web Apps Server to your topology, complete the following steps:</span></span>
  
1. <span data-ttu-id="361d6-114">비즈니스용 Skype 서버 토폴로지 작성기 열기.</span><span class="sxs-lookup"><span data-stu-id="361d6-114">Open Skype for Business Server Topology Builder.</span></span>
    
2. <span data-ttu-id="361d6-115">**토폴로지 작성기** 대화 상자에서 **기존 배포에서 토폴로지 다운로드** 를 선택한 후 **확인** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="361d6-115">In the **Topology Builder** dialog box, select **Download Topology from existing deployment** and then click **OK**.</span></span>
    
3. <span data-ttu-id="361d6-p104">**토폴로지를 다른 이름으로 저장** 대화 상자에서 **파일 이름** 상자에 토폴로지 문서 이름(예: **PreWebAppsServerTopology**)을 입력한 후 **저장** 을 클릭합니다. 이 토폴로지는 나중에 새 토폴로지에 문제가 발생한 경우 검색하고 다시 게시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="361d6-p104">In the **Save Topology As** dialog box, type a name for your topology document (for example, **PreWebAppsServerTopology**) in the **File name** box and then click **Save**. This topology can later be retrieved and republished if you encounter problems with your new topology.</span></span>
    
4. <span data-ttu-id="361d6-118">토폴로지 작성기에서 비즈니스용 **Skype** 서버를 확장하고, 사이트의 이름을 확장하고, **Enterprise Edition 프런트** 엔드 풀을 확장하고, 풀 중 하나의 이름을 마우스 오른쪽 단추로 클릭한 다음 속성 편집을 클릭합니다. </span><span class="sxs-lookup"><span data-stu-id="361d6-118">In Topology Builder, expand **Skype for Business Server**, expand the name of your site, expand **Enterprise Edition Front End pools**, right-click the name of one of your pools, and then click **Edit Properties**.</span></span>
    
5. <span data-ttu-id="361d6-119">**속성 편집** 대화 상자의 **일반** 탭에서 **Office Web Apps Server 연결** 제목을 찾아서 **새로 만들기** 를 클릭합니다(또는 드롭다운 목록에서 기존 Office Web Apps Server 선택).</span><span class="sxs-lookup"><span data-stu-id="361d6-119">In the **Edit Properties** dialog box, on the **General** tab, find the heading **Associate Office Web Apps Server** and then click **New** (or select an existing Office Web Apps Server from the drop-down list).</span></span>
    
6. <span data-ttu-id="361d6-120">**새 Office Web Apps Server 정의** 대화 상자에서 **Office Web Apps Server FQDN** 상자에 Office Web Apps Server 컴퓨터의 FQDN(정규화된 도메인 이름)을 입력합니다. 이렇게 하면 Office Web Apps Server 검색 URL이 **Office Web Apps Server 검색 URL** 상자에 자동으로 입력됩니다.</span><span class="sxs-lookup"><span data-stu-id="361d6-120">In the **Define New Office Web Apps Server** dialog box, type the fully qualified domain name (FQDN) of your Office Web Apps Server computer in the **Office Web Apps Server FQDN** box; when you do this, your Office Web Apps Server discovery URL should automatically be entered into the **Office Web Apps Server discovery URL** box.</span></span>
    
   - <span data-ttu-id="361d6-121">Office Web Apps 서버가 비즈니스용 Skype 서버와 같은 네트워크 영역과 모든 프레미스에 설치되어 있는 경우 **Office Web Apps 서버가** 외부 네트워크(경계/인터넷)에 배포되는 옵션을 선택하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="361d6-121">If the Office Web Apps Server is installed on-premises and in the same network zone as Skype for Business Server then the option **Office Web Apps Server is deployed in an external network (that is, perimeter/Internet)** should not be selected.</span></span>
    
   - <span data-ttu-id="361d6-122">Office Web Apps Server가 내부 방화벽 외부에 배포된 경우 **Office Web Apps Server가 외부 네트워크에 배포되어 있습니다(경계/인터넷).** 옵션을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="361d6-122">If the Office Web Apps Server is deployed outside your internal firewall, then select the option **Office Web Apps Server is deployed in an external network (that is, perimeter/Internet)**.</span></span>
    
7. <span data-ttu-id="361d6-123">**새 Office Web Apps Server 정의** 대화 상자에서 **확인** 을 클릭한 후 **속성 편집** 대화 상자에서 **확인** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="361d6-123">In the **Define New Office Web Apps Server** dialog box, click **OK**, and then click **OK** in the **Edit Properties** dialog box.</span></span> <span data-ttu-id="361d6-124">그러면 검색 URL이 풀의 연결 중 하나로 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="361d6-124">The discovery URL will then be listed as one of the pool's Associations.</span></span>
    
<span data-ttu-id="361d6-125">Office Web Apps Server와 연결해야 하는 각 풀에 대해 이 프로세스를 반복해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="361d6-125">You will have to repeat this process for each pool that needs to be associated with your Office Web Apps Server.</span></span>
  
<span data-ttu-id="361d6-126">토폴로지에 검색 URL을 추가한 후 업데이트된 토폴로지가 게시되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="361d6-126">After you have added the discovery URL to the topology, you must then publish the updated topology.</span></span> <span data-ttu-id="361d6-127">이렇게 하려면 토폴로지 작성기에서 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="361d6-127">To do that in Topology Builder:</span></span>
  
1. <span data-ttu-id="361d6-128">**동작** 을 클릭하고, **토폴로지 게시** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="361d6-128">Click **Action** and then click **Publish Topology**.</span></span>
    
2. <span data-ttu-id="361d6-129">토폴로지 게시 마법사의 **토폴로지 게시** 페이지에서 **다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="361d6-129">In the Publish Topology wizard, on the **Publish the Topology** page, click **Next**.</span></span>
    
3. <span data-ttu-id="361d6-130">**게시 마법사 완료** 페이지에서 **마침** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="361d6-130">On the **Publishing wizard complete** page, click **Finish**.</span></span>
    
4. <span data-ttu-id="361d6-131">토폴로지 작성기를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="361d6-131">Close Topology Builder.</span></span>
    
## <a name="configure-access-for-external-users"></a><span data-ttu-id="361d6-132">외부 사용자에 대한 액세스 구성</span><span class="sxs-lookup"><span data-stu-id="361d6-132">Configure access for external users</span></span>

<span data-ttu-id="361d6-133">외부 사용자(즉, 조직의 방화벽 외부에서 로그온하는 사용자)가 Office Web Apps 서버 PowerPoint 프레젠테이션에 액세스할 수 있도록 하려는 경우 Office Web Apps 서버 및 역방향 프록시 서버를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="361d6-133">If you want external users (that is, users logging on from outside your organization's firewall) to have access to Office Web Apps Server PowerPoint presentations, then you will need to use Office Web Apps Server and a reverse proxy server.</span></span> <span data-ttu-id="361d6-134">또한 사용자가 서버에 연결할 수 있도록 하는 웹 사이트 게시 규칙을 만들고 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="361d6-134">You will also need to create and configure a website publishing rule, which will help ensure that users are able to connect to the server.</span></span> 
  
## <a name="validate-the-configuration"></a><span data-ttu-id="361d6-135">구성 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="361d6-135">Validate the configuration</span></span>

<span data-ttu-id="361d6-136">Office Web Apps 서버가 토폴로지에 추가되고 해당 토폴로지가 게시된 후 비즈니스용 Skype 서버 이벤트 로그에 두 개의 새 이벤트 로그 이벤트가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="361d6-136">After Office Web Apps Server has been added to the topology, and after that topology has been published, you should see two new event log events in the Skype for Business Server event log.</span></span> <span data-ttu-id="361d6-137">먼저 LS 데이터 MCU 이벤트(이벤트 ID 41034)를 추가해야 합니다. 이 이벤트는 Office Web Apps 서버가 검색된 것으로 보고됩니다.</span><span class="sxs-lookup"><span data-stu-id="361d6-137">First, an LS Data MCU event (event ID 41034) should be added; this event will report that the Office Web Apps Server has been discovered:</span></span>
  
 <span data-ttu-id="361d6-138">**웹 회의 서버 Office Web Apps 서버가 검색되어 PowerPoint 콘텐츠가 사용하도록 설정됩니다.**</span><span class="sxs-lookup"><span data-stu-id="361d6-138">**Web Conferencing Server Office Web Apps Server is discovered, PowerPoint content is enabled.**</span></span>
  
<span data-ttu-id="361d6-p109">또한 백 오피스 Office Web Apps 서버 URL을 보고하는 또 다른 LS 데이터 MCU 이벤트(이벤트 ID 41032)도 표시되어야 합니다. 예를 들면 다음과 같은 로그가 표시되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="361d6-p109">In addition to that you should see another LS Data MCU event (event ID 41032) that reports back Office Web Apps Server URLs. For example, you should see something similar to this:</span></span>
  
 <span data-ttu-id="361d6-141">**웹 회의 서버 Office Web Apps 서버 검색이 성공했습니다.**</span><span class="sxs-lookup"><span data-stu-id="361d6-141">**Web Conferencing Server Office Web Apps Server discovery has succeeded.**</span></span>
  
 <span data-ttu-id="361d6-142">**Office Web Apps 서버 내부 발표자 페이지: https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0&amp ;embed=**</span><span class="sxs-lookup"><span data-stu-id="361d6-142">**Office Web Apps Server internal presenter page: https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0&amp;embed=**</span></span>
  
 <span data-ttu-id="361d6-143">**Office Web Apps 서버 내부 참석자 페이지: https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0&amp ;embed=true&amp;=**</span><span class="sxs-lookup"><span data-stu-id="361d6-143">**Office Web Apps Server internal attendee page: https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0&amp;embed=true&amp;=**</span></span>
  
<span data-ttu-id="361d6-144">외부 사용자에 대한 액세스를 구성한 경우 다음 사항도 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="361d6-144">If you have configured access for external users, you will also see something similar to:</span></span>
  
 <span data-ttu-id="361d6-145">**Office Web Apps 서버 외부 발표자 페이지: https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0&amp ;embed**</span><span class="sxs-lookup"><span data-stu-id="361d6-145">**Office Web Apps Server external presenter page: https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0&amp;embed**</span></span>
  
 <span data-ttu-id="361d6-146">**Office Web Apps 서버 내부 참석자 <https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0&amp;embed=true&amp> 페이지:**</span><span class="sxs-lookup"><span data-stu-id="361d6-146">**Office Web Apps Server internal attendee page: <https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0&amp;embed=true&amp>;**</span></span>
  
<span data-ttu-id="361d6-147">이벤트 ID가 41033인 LS 데이터 MCU 이벤트가 표시되는 경우 이는 Office Web Apps 서버가 검색되지 않았음을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="361d6-147">If you see an LS Data MCU event with the event ID of 41033 that means that Office Web Apps Server discovery has failed.</span></span> <span data-ttu-id="361d6-148">이 경우 비즈니스용 Skype 서버는 새로 구성된 Office Web Apps 서버를 검색하는 데 필요한 수만큼 시도합니다.</span><span class="sxs-lookup"><span data-stu-id="361d6-148">In that case, Skype for Business Server will try as many times as needed to discover the newly-configured Office Web Apps Server.</span></span> <span data-ttu-id="361d6-149">검색 프로세스가 계속 실패할 경우에는 Office Web Apps 서버를 토폴로지 문서에서 제거하고 업데이트된 토폴로지를 게시한 다음 연결 문제가 해결된 후에 Office Web Apps 서버를 토폴로지에 다시 추가해 봅니다.</span><span class="sxs-lookup"><span data-stu-id="361d6-149">If the discovery process fails repeatedly you should remove Office Web Apps Server from your topology document, publish the updated topology, and then try adding Office Web Apps Server back to the topology after the connectivity issues have been resolved.</span></span>
  
<span data-ttu-id="361d6-150">Office Web Apps 서버가 올바르게 구성되고 검색 프로세스에서 인식된 경우 비즈니스용 Skype 클라이언트 쌍 간에 PowerPoint 프레젠테이션을 공유하여 Office Web Apps 서버가 예상대로 작동하고 있는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="361d6-150">If Office Web Apps Server appears to be configured correctly and has been recognized by the discovery process you can verify that Office Web Apps Server is working as expected by sharing a PowerPoint presentation between a pair of Skype for Business clients.</span></span> <span data-ttu-id="361d6-151">사용자 A가 PowerPoint 프레젠테이션을 로드하고 표시할 수 있으며 사용자 B가 모임에 참가하고 해당 프레젠테이션을 볼 수 있는 경우에는 Office Web Apps 서버가 작동 중인 것입니다.</span><span class="sxs-lookup"><span data-stu-id="361d6-151">If User A can load and display the PowerPoint presentation and if User B can then join the meeting and see that presentation then Office Web Apps Server is working.</span></span>
  
<span data-ttu-id="361d6-152">Office Web Apps 서버가 올바르게 구성된 것으로 나타나도 PowerPoint 프레젠테이션을 공유하려고 할 때 "서버 연결 문제로 인해 일부 공유 기능을 사용할 수 없습니다."라는 오류 메시지가 표시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="361d6-152">Even if Office Web Apps Server appears to be configured correctly, you could potentially receive the error message "Some sharing features are unavailable due to server connectivity issues" when you try sharing a PowerPoint presentation.</span></span> <span data-ttu-id="361d6-153">이러한 오류 메시지가 나타나면 새 Office Web Apps 서버와 연결된 프런트 엔드 서버를 다시 시작해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="361d6-153">If you receive that error message you should restart the Front End server (or servers) associated with the new Office Web Apps Server.</span></span>
  

