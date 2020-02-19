---
title: 'Lync Server 2013: 회의 요구 사항 정의'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining your requirements for conferencing
ms:assetid: 5c83e268-22bf-42b2-bac3-3237b5e02e03
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204935(v=OCS.15)
ms:contentKeyID: 48184255
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ee3b7631a3c05fb497ee7fcdf37b6db984361845
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137819"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="defining-your-requirements-for-conferencing-in-lync-server-2013"></a><span data-ttu-id="73419-102">Lync Server 2013의 회의에 대 한 요구 사항 정의</span><span class="sxs-lookup"><span data-stu-id="73419-102">Defining your requirements for conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="73419-103">_**마지막으로 수정 된 항목:** 2012-09-30_</span><span class="sxs-lookup"><span data-stu-id="73419-103">_**Topic Last Modified:** 2012-09-30_</span></span>

<span data-ttu-id="73419-p101">배포할 회의 기능을 확인할 때는 사용자에게 제공하려는 기능 및 네트워크 대역폭 기능을 고려해야 합니다. 다음 질문 목록에 따라 회의 계획 프로세스에서 조직의 요구 사항을 기반으로 배포해야 하는 회의 기능을 확인하십시오.</span><span class="sxs-lookup"><span data-stu-id="73419-p101">When you are determining which conferencing capabilities to deploy, you need to consider the features that you want available to your users and your network bandwidth capabilities. The following list of questions guides you through the conferencing planning process to determine what features of conferencing you should deploy, based on your organization’s requirements.</span></span>

  - <span data-ttu-id="73419-106">**문서 공동 작업 및 응용 프로그램 공유가 포함된 웹 회의를 사용하려고 하십니까?**</span><span class="sxs-lookup"><span data-stu-id="73419-106">**Do you want to enable web conferencing, which includes document collaboration and application sharing?**</span></span>
    
    <span data-ttu-id="73419-107">이 경우 Microsoft Lync Server 2013, 계획 도구 또는 토폴로지 작성기에서 프런트 엔드 풀에 대 한 회의를 사용 하도록 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="73419-107">If so, you must enable conferencing for your Front End pool in the Microsoft Lync Server 2013, Planning Tool or in Topology Builder.</span></span> <span data-ttu-id="73419-108">회의를 사용하도록 설정할 때는 웹 회의와 A/V 회의를 모두 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="73419-108">When you enable conferencing, you enable both web conferencing and A/V conferencing.</span></span>
    
    <span data-ttu-id="73419-109">응용 프로그램 공유에는 문서 공동 작업보다 더 많은 네트워크 대역폭이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="73419-109">Application sharing requires and uses more network bandwidth than document collaboration.</span></span> <span data-ttu-id="73419-110">Lync Server 2013에서는 각 응용 프로그램 공유 세션을 제어 하는 제한 메커니즘을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="73419-110">Lync Server 2013 provides a throttling mechanism to control each application sharing session.</span></span> <span data-ttu-id="73419-111">기본적으로 대역폭 제한은 세션당 1.5KB/초로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="73419-111">By default, this is set to 1.5 KB/second for each session.</span></span>
    
    <span data-ttu-id="73419-112">문서 공동 작업을 수행하되, 응용 프로그램 공유를 사용하지 않으려면 회의를 활성화하고 모임 정책을 사용하여 응용 프로그램 공유를 사용하지 않도록 설정하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="73419-112">If you do not want to enable application sharing but you do want document collaboration, you can enable conferencing and use meeting policies to disable application sharing.</span></span> <span data-ttu-id="73419-113">모임 정책 구성에 대 한 자세한 내용은 [Lync Server 2013의 회의 정책을](lync-server-2013-conferencing-policies.md)참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="73419-113">For details about configuring meeting policies, see [Conferencing policies in Lync Server 2013](lync-server-2013-conferencing-policies.md).</span></span>
    
    <span data-ttu-id="73419-114">사용자가 PowerPoint 프레젠테이션을 공유할 수 있도록 하려면 Office Web Apps 서버를 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="73419-114">To enable users to share PowerPoint presentations, you need to configure Office Web Apps Server.</span></span> <span data-ttu-id="73419-115">Office Web Apps 서버를 구성 하는 방법에 대 한 자세한 내용은 [Office Web Apps 서버 및 Lync server 2013의 통합 구성을](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="73419-115">For details about configuring Office Web Apps Server, see [Configuring integration with Office Web Apps Server and Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).</span></span>

  - <span data-ttu-id="73419-116">**A/V 회의를 사용하려고 하십니까?**</span><span class="sxs-lookup"><span data-stu-id="73419-116">**Do you want to enable A/V conferencing?**</span></span>
    
    <span data-ttu-id="73419-117">이 경우 Lync Server 2013, 계획 도구 또는 토폴로지 작성기에서 프런트 엔드 풀에 대 한 회의를 사용 하도록 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="73419-117">If so, you must enable conferencing for your Front End pool in the Lync Server 2013, Planning Tool or in Topology Builder.</span></span> <span data-ttu-id="73419-118">회의를 사용하도록 설정할 때는 웹 회의와 A/V 회의를 모두 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="73419-118">When you enable conferencing, you enable both web conferencing and A/V conferencing.</span></span>
    
    <span data-ttu-id="73419-p107">A/V 회의에는 웹 회의(문서 공동 작업 및 응용 프로그램 공유 포함)보다 더 많은 네트워크 대역폭이 필요합니다. 웹 회의를 수행하되, A/V 회의를 사용하지 않으려면 회의를 활성화하고 모임 정책을 사용하여 A/V 전화 회의를 사용하지 않도록 설정하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="73419-p107">A/V conferencing requires and uses more network bandwidth than web conferencing (which includes document collaboration and application sharing). If you do not want to enable A/V conferencing but you do want to enable web conferencing, you can enable conferencing and use meeting policies to disable A/V conferences.</span></span>
    
    <span data-ttu-id="73419-p108">화상 회의는 사용하지 않고 오디오 회의만 사용하려면 A/V 회의를 활성화하고 모임 정책을 사용하여 화상 회의를 사용할 수 없도록 설정하면 됩니다. 또는 A/V 회의를 사용하고 특정 사용자만 A/V 전화 회의를 시작하거나 A/V 전화 회의에 참가하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73419-p108">If you do want to enable audio conferences but not video conferences, you can enable A/V conferencing and use meeting policies to prevent video conferences. Alternatively, you can enable A/V conferencing and enable only certain users to start or participate in A/V conferences.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="73419-123">엔터프라이즈 음성은 A/V 회의를 사용 하는 데 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="73419-123">Enterprise Voice is not required for you to use A/V conferencing.</span></span> <span data-ttu-id="73419-124">A/V 회의를 사용하도록 설정하면 전화 솔루션에 PBX를 사용하는 경우에도 오디오 장치가 있는 사용자는 자신의 전화 회의에 오디오를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73419-124">If you enable A/V conferencing, your users can add audio to their conferences if they have audio devices, even if you use a PBX for your telephone solution.</span></span>

    
    </div>

  - <span data-ttu-id="73419-125">**사용자가 PSTN 전화를 사용하여 전화 회의의 오디오 부분에 참가할 수 있도록 설정하시겠습니까?**</span><span class="sxs-lookup"><span data-stu-id="73419-125">**Do you want to enable users to join the audio portion of conferences when using a PSTN phone?**</span></span>
    
    <span data-ttu-id="73419-p110">그렇다면 전화 접속 회의를 배포하고 활성화해야 합니다. 그러면 조직 내부 및 외부의 초대 받은 사용자가 PSTN 전화를 사용하여 전화 회의의 오디오 부분에 참가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73419-p110">If so, deploy and enable dial-in conferencing. Invited users, both inside and outside your organization, can then join the audio portion of conferences by using a PSTN phone.</span></span>

  - <span data-ttu-id="73419-128">**Lync Server 2013 클라이언트를 사용 하는 외부 사용자가 사용 하도록 설정한 회의 유형에 참가할 수 있도록 설정 하 시겠습니까?**</span><span class="sxs-lookup"><span data-stu-id="73419-128">**Do you want to enable external users with Lync Server 2013 clients to join the types of conferences that you have enabled?**</span></span>
    
    <span data-ttu-id="73419-129">그렇다면 에지 서버를 배포해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="73419-129">If so, you should deploy Edge Servers.</span></span> <span data-ttu-id="73419-130">모임에 외부 참여를 허용 하 여 Lync Server 2013에 대 한 투자를 극대화 합니다.</span><span class="sxs-lookup"><span data-stu-id="73419-130">By allowing external participation in meetings, you maximize your investment in Lync Server 2013.</span></span> <span data-ttu-id="73419-131">예를 들어 랩톱을 Lync Server 2013와 함께 사용 하는 사용자는 집, 공항 또는 고객 사이트의 어디에서 든 지 회의에 참가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73419-131">For example, users with laptops with Lync Server 2013 can join conferences from wherever they are—at home, in the airport, or at customer sites.</span></span>
    
    <span data-ttu-id="73419-132">또한 에지 서버를 배포하면 고객 및 공급업체와 같은 다른 조직과 페더레이션 관계를 만들 수 있으며 이러한 조직의 사용자가 회사 내부의 사용자와 보다 쉽게 공동 작업할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73419-132">Additionally, with Edge Servers deployed you can create federated relationships with other organizations-such as your customers or vendors-and users from those organizations can more easily collaborate with your users.</span></span>
    
    <span data-ttu-id="73419-133">에 지 서버를 배포 하는 방법에 대 한 자세한 내용은 [Lync server 2013의 외부 사용자 액세스 계획](lync-server-2013-planning-for-external-user-access.md) 및 [lync server 2013의 외부 사용자 액세스 배포](lync-server-2013-deploying-external-user-access.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="73419-133">For details about deploying Edge Servers, see [Planning for external user access in Lync Server 2013](lync-server-2013-planning-for-external-user-access.md) and [Deploying external user access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md).</span></span> <span data-ttu-id="73419-134">Office Web Apps 서버에 대 한 외부 액세스를 사용 하는 방법에 대 한 자세한 내용은 [역방향 프록시 서버를 사용 하 여 Lync server 2013의 Office Web Apps 서버 게시](lync-server-2013-publishing-office-web-apps-server-using-a-reverse-proxy-server.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="73419-134">For details about enabling external access for Office Web Apps Server, see [Publishing Office Web Apps Server in Lync Server 2013 using a reverse proxy server](lync-server-2013-publishing-office-web-apps-server-using-a-reverse-proxy-server.md).</span></span>

  - <span data-ttu-id="73419-135">**Lync Server 2013 모임에 참가할 수 있는 클라이언트를 제어 하 시겠습니까?**</span><span class="sxs-lookup"><span data-stu-id="73419-135">**Do you want to control the clients that can join Lync Server 2013 meetings?**</span></span>
    
    <span data-ttu-id="73419-136">그렇다면 지원할 클라이언트 옵션만 사용할 수 있도록 모임 참가 페이지를 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="73419-136">If so, you should configure the meeting join page so that only the client options that you want to support are available.</span></span> <span data-ttu-id="73419-137">사용자가 예약 된 모임에 참가할 링크를 클릭할 때마다 Lync Server 2013에서 클라이언트가 컴퓨터에 이미 설치 되어 있는지 여부를 감지 합니다.</span><span class="sxs-lookup"><span data-stu-id="73419-137">Each time a user clicks a link to join a scheduled meeting, Lync Server 2013 detects whether a client is already installed on the computer.</span></span> <span data-ttu-id="73419-138">그런 다음 기본 클라이언트를 시작하고 대체 클라이언트에 대한 링크가 포함된 모임 참가 페이지를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="73419-138">It then starts the default client and opens the meeting join page, which contains links for alternate clients.</span></span> <span data-ttu-id="73419-139">모임 참가 페이지에는 항상 Microsoft Lync Web App을 사용할 수 있는 옵션이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73419-139">The meeting join page always contains the option to use Microsoft Lync Web App.</span></span> <span data-ttu-id="73419-140">이 옵션 외에도 참석자 및 이전 버전의 Communicator에 대 한 링크를 포함할지 여부를 결정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73419-140">In addition to this option, you can decide whether to include links for Attendee and previous versions of Communicator.</span></span> <span data-ttu-id="73419-141">자세한 내용은 [Lync Server 2013에서 모임 참가 페이지 구성을](lync-server-2013-configuring-the-meeting-join-page.md)참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="73419-141">For details, see [Configuring the meeting join page in Lync Server 2013](lync-server-2013-configuring-the-meeting-join-page.md).</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="73419-142">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="73419-142">In This Section</span></span>

  - [<span data-ttu-id="73419-143">Lync Server 2013의 웹 회의 요구 사항</span><span class="sxs-lookup"><span data-stu-id="73419-143">Web conferencing requirements in Lync Server 2013</span></span>](lync-server-2013-web-conferencing-requirements.md)

  - [<span data-ttu-id="73419-144">Lync Server 2013의 A/V 회의 요구 사항</span><span class="sxs-lookup"><span data-stu-id="73419-144">A/V conferencing requirements in Lync Server 2013</span></span>](lync-server-2013-a-v-conferencing-requirements.md)

  - [<span data-ttu-id="73419-145">Lync Server 2013의 전화 접속 회의 요구 사항</span><span class="sxs-lookup"><span data-stu-id="73419-145">Dial-in conferencing requirements in Lync Server 2013</span></span>](lync-server-2013-dial-in-conferencing-requirements.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="73419-146">참고 항목</span><span class="sxs-lookup"><span data-stu-id="73419-146">See Also</span></span>


[<span data-ttu-id="73419-147">Lync Server 2013의 회의 계획</span><span class="sxs-lookup"><span data-stu-id="73419-147">Planning for conferencing in Lync Server 2013</span></span>](lync-server-2013-planning-for-conferencing.md)  
[<span data-ttu-id="73419-148">Lync Server 2013의 회의에 대 한 배포 검사 목록</span><span class="sxs-lookup"><span data-stu-id="73419-148">Deployment checklist for conferencing in Lync Server 2013</span></span>](lync-server-2013-deployment-checklist-for-conferencing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

