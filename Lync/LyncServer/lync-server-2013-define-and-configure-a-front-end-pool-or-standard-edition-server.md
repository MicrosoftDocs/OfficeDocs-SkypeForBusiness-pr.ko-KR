---
title: 프런트 엔드 풀 또는 Standard Edition server 정의 및 구성
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Define and configure a Front End pool or Standard Edition server
ms:assetid: 713fc263-23dd-414a-b001-82932e4fe966
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398538(v=OCS.15)
ms:contentKeyID: 48184457
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bfd8cc2b12032e1283c10e26d4a9fa879621233f
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42209173"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="define-and-configure-a-front-end-pool-or-standard-edition-server-in-lync-server-2013"></a><span data-ttu-id="e57cf-102">Lync Server 2013에서 프런트 엔드 풀 또는 Standard Edition 서버 정의 및 구성</span><span class="sxs-lookup"><span data-stu-id="e57cf-102">Define and configure a Front End pool or Standard Edition server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e57cf-103">_**마지막으로 수정 된 항목:** 2013-03-08_</span><span class="sxs-lookup"><span data-stu-id="e57cf-103">_**Topic Last Modified:** 2013-03-08_</span></span>

<span data-ttu-id="e57cf-p101">이 절차는 로컬 관리자 구성원 자격 또는 권한이 있는 도메인 그룹 구성원 자격이 없어도 수행할 수 있습니다. 즉, 컴퓨터에 표준 사용자로 로그온하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e57cf-p101">This procedure does not require membership in a local administrator or privileged domain group. You should log on to a computer as a standard user.</span></span>

<span data-ttu-id="e57cf-106">엔터프라이즈 서버를 배포 하는 경우 풀에 있는 최소 개수의 프런트 엔드 서버가 항상 실행 되 고 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e57cf-106">If you are deploying an Enterprise server, a minimum number of Front End Servers in a pool must be running at all times.</span></span> <span data-ttu-id="e57cf-107">다음 표에서는 이러한 요구 사항을 요약해서 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="e57cf-107">The following table summarizes these requirements.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e57cf-108">풀에 있는 총 프런트 엔드 서버 수</span><span class="sxs-lookup"><span data-stu-id="e57cf-108">Total number of Front End Servers in the pool</span></span></th>
<th><span data-ttu-id="e57cf-109">풀 작동을 위해 실행되어야 하는 서버 수</span><span class="sxs-lookup"><span data-stu-id="e57cf-109">Number of servers that must be running for pool to be functional</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e57cf-110">1-2</span><span class="sxs-lookup"><span data-stu-id="e57cf-110">1-2</span></span></p></td>
<td><p><span data-ttu-id="e57cf-111">개</span><span class="sxs-lookup"><span data-stu-id="e57cf-111">1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e57cf-112">3-4</span><span class="sxs-lookup"><span data-stu-id="e57cf-112">3-4</span></span></p></td>
<td><p><span data-ttu-id="e57cf-113">2</span><span class="sxs-lookup"><span data-stu-id="e57cf-113">2</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e57cf-114">5-6</span><span class="sxs-lookup"><span data-stu-id="e57cf-114">5-6</span></span></p></td>
<td><p><span data-ttu-id="e57cf-115">3(sp3)</span><span class="sxs-lookup"><span data-stu-id="e57cf-115">3</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e57cf-116">7-8</span><span class="sxs-lookup"><span data-stu-id="e57cf-116">7-8</span></span></p></td>
<td><p><span data-ttu-id="e57cf-117">1-4</span><span class="sxs-lookup"><span data-stu-id="e57cf-117">4</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e57cf-118">9-10</span><span class="sxs-lookup"><span data-stu-id="e57cf-118">9-10</span></span></p></td>
<td><p><span data-ttu-id="e57cf-119">2-5</span><span class="sxs-lookup"><span data-stu-id="e57cf-119">5</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e57cf-120">11-12</span><span class="sxs-lookup"><span data-stu-id="e57cf-120">11-12</span></span></p></td>
<td><p><span data-ttu-id="e57cf-121">6 </span><span class="sxs-lookup"><span data-stu-id="e57cf-121">6</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]
> <span data-ttu-id="e57cf-122">Lync Server 2013의 경우 풀에서 프런트 엔드 서버를 추가 또는 제거할 때마다 서비스를 다시 시작 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e57cf-122">For Lync Server 2013, any time you add or remove a Front End Server from the pool, you must restart services.</span></span> <span data-ttu-id="e57cf-123">서버를 제거하고 추가하는 작업은 개별 작업으로 수행되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e57cf-123">Removing and adding servers should be done as separate operations.</span></span> <span data-ttu-id="e57cf-124">예를 들어 프런트 엔드 서버 두 대를 추가 하 고 두 프런트 엔드 서버를 제거 하려면 다음 프로세스를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="e57cf-124">For example, if you are going to add two Front End Servers and remove two Front End Servers, use the following process:</span></span> 
> <OL>
> <LI>
> <P><span data-ttu-id="e57cf-125">2개의 프런트 엔드 서버를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="e57cf-125">Remove the two Front End Servers.</span></span></P>
> <LI>
> <P><span data-ttu-id="e57cf-126">토폴로지를 게시하고 다시 활성화합니다.</span><span class="sxs-lookup"><span data-stu-id="e57cf-126">Publish and re-activate the topology.</span></span></P>
> <LI>
> <P><span data-ttu-id="e57cf-127">서비스를 다시 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="e57cf-127">Restart the services</span></span></P>
> <LI>
> <P><span data-ttu-id="e57cf-128">2개의 프런트 엔드 서버를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="e57cf-128">Add the two Front End Servers.</span></span></P>
> <LI>
> <P><span data-ttu-id="e57cf-129">토폴로지를 게시하고 다시 활성화합니다.</span><span class="sxs-lookup"><span data-stu-id="e57cf-129">Publish and re-activate the topology.</span></span></P>
> <LI>
> <P><span data-ttu-id="e57cf-130">서비스를 다시 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="e57cf-130">Restart the services.</span></span></P></LI></OL>



</div>

<span data-ttu-id="e57cf-131">토폴로지를 정의한 후에는 다음 절차를 사용 하 여 사이트의 프런트 엔드 풀을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="e57cf-131">After you have defined your topology, use the following procedure to define a Front End pool for your site.</span></span> <span data-ttu-id="e57cf-132">토폴로지를 정의 하는 방법에 대 한 자세한 내용은 [Lync Server 2013에 대 한 토폴로지 작성기에서 토폴로지 정의 및 구성을](lync-server-2013-define-and-configure-a-topology-in-topology-builder.md)참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="e57cf-132">For details about defining the topology, see [Define and configure a topology in Topology Builder for Lync Server 2013](lync-server-2013-define-and-configure-a-topology-in-topology-builder.md).</span></span>

<div>

## <a name="to-define-a-front-end-pool"></a><span data-ttu-id="e57cf-133">프런트 엔드 풀을 정의 하려면</span><span class="sxs-lookup"><span data-stu-id="e57cf-133">To define a Front End pool</span></span>

1.  <span data-ttu-id="e57cf-134">새 프런트 엔드 풀 정의 마법사의 **새 프런트 엔드 풀 정의** 페이지에서 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="e57cf-134">In the Define New Front End Pool Wizard, on the **Define the New Front End pool** page, click **Next**.</span></span>

2.  <span data-ttu-id="e57cf-135">**프런트 엔드 풀 FQDN 정의** 페이지에서 만들려는 풀의 fqdn (정규화 된 도메인 이름)을 입력 하 고 **Enterprise Edition 프런트 엔드 풀**을 클릭 한 후 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e57cf-135">On the **Define the Front End pool FQDN** page, enter a fully qualified domain name (FQDN) for the pool you are creating, click **Enterprise Edition Front End pool**, and then click **Next**.</span></span>

3.  <span data-ttu-id="e57cf-136">**이 풀의 컴퓨터 정의** 페이지에서 풀의 첫 번째 프런트 엔드 서버에 대 한 컴퓨터 FQDN을 입력 한 다음 **추가**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e57cf-136">On the **Define the computers in this pool** page, enter a computer FQDN for the first Front End Server in the pool, and then click **Add**.</span></span> <span data-ttu-id="e57cf-137">풀에 추가할 추가 컴퓨터 (최대 12 개)에 대해이 단계를 반복 하 고 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e57cf-137">Repeat this step for any additional computers (up to twelve) that you want to add to the pool, and then click **Next**.</span></span>

4.  <span data-ttu-id="e57cf-138">**기능 선택** 페이지에서 이 프런트 엔드 풀에 필요한 기능의 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e57cf-138">On the **Select features** page, select the check boxes for the features that you want on this Front End pool.</span></span> <span data-ttu-id="e57cf-139">예를 들어 IM (인스턴트 메시징) 및 현재 상태 기능만 배포 하는 경우에는 음성, 비디오 및 공동 작업 회의 기능을 나타내기 때문에 단체 IM을 허용 하 고 **전화 접속 (PSTN) 회의**, **Enterprise Voice**또는 **통화 허용 제어** 확인란이 선택 되지 않도록 **회의** 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e57cf-139">For example, if you are deploying only instant messaging (IM) and presence features, you would select the **Conferencing** check box to allow multiparty IM but would not select the **Dial-in (PSTN) conferencing**, **Enterprise Voice**, or **Call Admission Control** check boxes, because they represent voice, video, and collaborative conferencing features.</span></span>
    
      - <span data-ttu-id="e57cf-140">**회의**   이 항목을 선택 하면 다음을 비롯 한 다양 한 기능을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e57cf-140">**Conferencing**   This selection enables a rich set of features including:</span></span>
        
          - <span data-ttu-id="e57cf-141">IM 세션에서 둘 이상의 사용자를 포함하는 IM</span><span class="sxs-lookup"><span data-stu-id="e57cf-141">IM with more than two parties in an IM session.</span></span>
        
          - <span data-ttu-id="e57cf-142">문서 공동 작업, 응용 프로그램 공유 및 데스크톱 공유를 포함하는 회의</span><span class="sxs-lookup"><span data-stu-id="e57cf-142">Conferencing, which includes document collaboration, application sharing, and desktop sharing.</span></span>
        
          - <span data-ttu-id="e57cf-143">A/V 회의-사용자가 Live Meeting 서비스나 타사 오디오 브리지 등의 외부 서비스 없이도 실시간 전화 회의를 할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="e57cf-143">A/V conferencing, which enables users to have real-time audio/video (A/V) conferences without the need for external services such as the Live Meeting service or a third-party audio bridge.</span></span>
    
      - <span data-ttu-id="e57cf-144">**전화 접속 (pstn) 회의**   를 통해 사용자는 오디오 회의 공급자 없이도 공중 전화망 (pstn) 전화를 사용 하 여 Lync Server 2013 회의의 오디오 부분에 참가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e57cf-144">**Dial-in (PSTN) conferencing**   Allows users to join the audio portion of a Lync Server 2013 conference by using a public switched telephone network (PSTN) phone without requiring an audio conferencing provider.</span></span>
    
      - <span data-ttu-id="e57cf-145">**Enterprise voice**   enterprise voice는 Lync Server 2013의 VoIP (Voice over IP) 솔루션으로, 사용자가 전화를 걸고 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e57cf-145">**Enterprise Voice**   Enterprise Voice is the Voice over IP (VoIP) solution in Lync Server 2013 that allows users to make and receive phone calls.</span></span> <span data-ttu-id="e57cf-146">음성 통화, 음성 메일 및 하드웨어 장치 또는 소프트웨어 클라이언트를 사용 하는 기타 기능에 Lync Server 2013을 사용 하려면이 기능을 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="e57cf-146">You would deploy this feature if you plan to use Lync Server 2013 for voice calls, voice mail, and other functions that use a hardware device or a software client.</span></span>
    
      - <span data-ttu-id="e57cf-147">**Cac (통화 허용 제어)**   cac는 사용 가능한 네트워크 대역폭을 기반으로 음성 또는 비디오 통화와 같은 실시간 통신 세션을 설정할지 여부를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e57cf-147">**Call admission control (CAC)**   CAC determines, based on available network bandwidth, whether to allow real-time communications sessions such as voice or video calls to be established.</span></span> <span data-ttu-id="e57cf-148">IM과 현재 상태만 배포한 경우에는 두 기능 모두 CAC를 사용하지 않으므로 CAC가 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e57cf-148">If you have deployed only IM and presence, CAC is not needed because neither of these two features uses CAC.</span></span>
    
      - <span data-ttu-id="e57cf-149">**보관**   보관은 Lync Server 2013를 통해 전송 되는 IM 콘텐츠, 회의 (모임) 콘텐츠 또는 둘 다를 보관할 수 있는 방법을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="e57cf-149">**Archiving**   Archiving provides a way for you to archive IM content, conferencing (meeting) content, or both that is sent through Lync Server 2013.</span></span>
    
      - <span data-ttu-id="e57cf-150">**모니터링 모니터링 서버**   를 사용 하면 네트워크 및 끝점의 미디어 품질, VoIP 통화, IM 메시지, A/V 대화, 모임, 응용 프로그램 공유, 파일 전송, 실패 한 통화에 대 한 통화 오류 및 문제 해결 정보를 설명 하는 수치 데이터를 수집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e57cf-150">**Monitoring**   Monitoring Server enables you to collect numerical data that describes the media quality on your network and endpoints, usage information related to VoIP calls, IM messages, A/V conversations, meetings, application sharing, and file transfers, and call error and troubleshooting information for failed calls.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="e57cf-p109">배포에서 CAC를 사용하도록 설정하려면 중앙 사이트당 정확히 하나의 풀에서 CAC를 사용하도록 설정해야 합니다. 음성 기능이나 A/V 회의를 배포하는 경우 CAC를 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="e57cf-p109">If you would like to enable CAC in your deployment, it is required that you enable CAC in exactly one pool per central site. CAC is recommended if you are deploying voice features or A/V conferencing.</span></span>

    
    </div>
    
    <span data-ttu-id="e57cf-p110">다음 표에는 사용 가능한 기능(위쪽)과 사용자에게 제공되는 기능(왼쪽)이 나와 있습니다. 표에서 선택되어 있는 항목은 조직에 대해 해당 기능을 사용하도록 설정하기 위해 선택해야 하는 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="e57cf-p110">The following table shows the available features (top) and the functions offered to users (left). The selections in the table are what you should select to enable those features for your organization.</span></span>
    
    
    <table>
    <colgroup>
    <col style="width: 20%" />
    <col style="width: 20%" />
    <col style="width: 20%" />
    <col style="width: 20%" />
    <col style="width: 20%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th></th>
    <th><span data-ttu-id="e57cf-155">전화</span><span class="sxs-lookup"><span data-stu-id="e57cf-155">Conferencing</span></span></th>
    <th><span data-ttu-id="e57cf-156">전화 접속 회의</span><span class="sxs-lookup"><span data-stu-id="e57cf-156">Dial-In Conferencing</span></span></th>
    <th><span data-ttu-id="e57cf-157">Enterprise Voice</span><span class="sxs-lookup"><span data-stu-id="e57cf-157">Enterprise Voice</span></span></th>
    <th><span data-ttu-id="e57cf-158">통화 허용 제어</span><span class="sxs-lookup"><span data-stu-id="e57cf-158">Call Admission Control</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="e57cf-159">인스턴트 메시징 및 현재 상태</span><span class="sxs-lookup"><span data-stu-id="e57cf-159">Instant messaging and presence</span></span></p></td>
    <td><p><span data-ttu-id="e57cf-160">X</span><span class="sxs-lookup"><span data-stu-id="e57cf-160">X</span></span></p></td>
    <td></td>
    <td></td>
    <td></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="e57cf-161">전화</span><span class="sxs-lookup"><span data-stu-id="e57cf-161">Conferencing</span></span></p></td>
    <td><p><span data-ttu-id="e57cf-162">X</span><span class="sxs-lookup"><span data-stu-id="e57cf-162">X</span></span></p></td>
    <td><p><span data-ttu-id="e57cf-163">X</span><span class="sxs-lookup"><span data-stu-id="e57cf-163">X</span></span></p></td>
    <td></td>
    <td></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="e57cf-164">A/V 회의</span><span class="sxs-lookup"><span data-stu-id="e57cf-164">A/V conferencing</span></span></p></td>
    <td><p><span data-ttu-id="e57cf-165">X</span><span class="sxs-lookup"><span data-stu-id="e57cf-165">X</span></span></p></td>
    <td><p><span data-ttu-id="e57cf-166">X</span><span class="sxs-lookup"><span data-stu-id="e57cf-166">X</span></span></p></td>
    <td></td>
    <td><p><span data-ttu-id="e57cf-167">X</span><span class="sxs-lookup"><span data-stu-id="e57cf-167">X</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="e57cf-168">Enterprise Voice</span><span class="sxs-lookup"><span data-stu-id="e57cf-168">Enterprise Voice</span></span></p></td>
    <td></td>
    <td></td>
    <td><p><span data-ttu-id="e57cf-169">X</span><span class="sxs-lookup"><span data-stu-id="e57cf-169">X</span></span></p></td>
    <td><p><span data-ttu-id="e57cf-170">X</span><span class="sxs-lookup"><span data-stu-id="e57cf-170">X</span></span></p></td>
    </tr>
    </tbody>
    </table>


5.  <span data-ttu-id="e57cf-171">**배치 된 서버 역할 선택** 페이지에서 프런트 엔드 서버에 대 한 중재 서버를 함께 배치할 독립 실행형 서버로 배포 하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e57cf-171">On the **Select collocated server roles** page, you can to collocate the Mediation Server on the Front End Server or to deploy it as a stand-alone server.</span></span>
    
    <span data-ttu-id="e57cf-172">함께 배치할는 프런트 엔드 풀에서 중재 서버를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e57cf-172">You can collocate the Mediation Server on the Front End pool.</span></span>
    
      - <span data-ttu-id="e57cf-173">Enterprise Edition 프런트 엔드 풀에서 중재 서버를 함께 배치할 확인란이 선택 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="e57cf-173">If you intend to collocate the Mediation Server on the Enterprise Edition Front End pool, ensure the check box is selected.</span></span> <span data-ttu-id="e57cf-174">서버 역할은 풀 서버에 배포됩니다.</span><span class="sxs-lookup"><span data-stu-id="e57cf-174">The server role will be deployed on the pool servers.</span></span>
    
      - <span data-ttu-id="e57cf-175">중재 서버를 독립 실행형 서버로 배포 하려는 경우 해당 확인란의 선택을 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="e57cf-175">If you intend to deploy the Mediation Server as a stand-alone server, clear the appropriate check box.</span></span> <span data-ttu-id="e57cf-176">프런트 엔드 서버를 완전히 배포한 후에 중재 서버를 별도의 배포 단계에 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="e57cf-176">You will deploy Mediation Server in a separate deployment step after you completely deploy the Front End Server.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="e57cf-177">가능한 경우 중재 서버를 배치하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="e57cf-177">We recommend that you collocate the Mediation Server if possible.</span></span> <span data-ttu-id="e57cf-178">배치 된 또는 독립 실행형 중재 서버에 대 한 지원에 대 한 자세한 내용은 계획 설명서의 <A href="lync-server-2013-components-and-topologies-for-mediation-server.md">Lync server 2013에서 중재 서버의 구성 요소 및 토폴로지</A> 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="e57cf-178">For details about support for collocated or stand-alone Mediation Servers, see <A href="lync-server-2013-components-and-topologies-for-mediation-server.md">Components and topologies for Mediation Server in Lync Server 2013</A> in the Planning documentation.</span></span>

    
    </div>

6.  <span data-ttu-id="e57cf-179">서버 **역할을이 프런트 엔드 풀과 연결** 페이지를 사용 하 여 서버 역할을 정의 하 고 프런트 엔드 풀과 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e57cf-179">The **Associate server roles with this Front End pool** page lets you define and associate server roles with the Front End pool.</span></span> <span data-ttu-id="e57cf-180">사용할 수 있는 역할은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="e57cf-180">The following role is available:</span></span>
    
    <span data-ttu-id="e57cf-181">**에 지 풀**   사용 단일에 지 서버 또는에 지 서버 풀을 정의 하 고 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="e57cf-181">**Enable an Edge pool**   Defines and associates a single Edge Server or a pool of Edge Servers.</span></span> <span data-ttu-id="e57cf-182">에 지 서버는 페더레이션 사용자를 포함 하 여 조직 외부의 사용자와 조직과의 공동 작업을 용이 하 게 합니다.</span><span class="sxs-lookup"><span data-stu-id="e57cf-182">An Edge Server facilitates communication and collaboration between users inside the organization and people outside the organization, including federated users.</span></span>
    
    <span data-ttu-id="e57cf-183">서버 역할을 배포하고 연결하는 데 사용할 수 있는 두 가지 가능한 시나리오가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e57cf-183">There are two possible scenarios that you can use to deploy and associate the server roles:</span></span>
    
    <span data-ttu-id="e57cf-p116">첫 번째 시나리오는 새로운 설치에 대한 새 토폴로지를 정의하는 경우입니다. 다음 두 가지 중 한 가지 방법으로 설치에 접근할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e57cf-p116">For scenario one, you are defining a new topology for a new installation. You can approach the installation in one of two ways:</span></span>
    
      - <span data-ttu-id="e57cf-186">확인란을 비워 두고 토폴로지 정의를 진행합니다.</span><span class="sxs-lookup"><span data-stu-id="e57cf-186">Leave the check box clear and proceed with defining the topology.</span></span> <span data-ttu-id="e57cf-187">프런트 엔드 및 백 엔드 서버 역할을 게시, 구성 및 테스트 한 후에는 토폴로지 작성기를 다시 실행 하 여 역할 서버를 토폴로지에 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e57cf-187">After you have published, configured, and tested the Front End and Back End Server roles, you can run Topology Builder again to add the role servers to the topology.</span></span> <span data-ttu-id="e57cf-188">이 전략을 사용 하면 추가 역할을 추가 하지 않고도 프런트 엔드 풀 및 SQL Server를 실행 하는 서버를 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e57cf-188">This strategy will enable you to test the Front End pool and the server running SQL Server without additional complications from additional roles.</span></span> <span data-ttu-id="e57cf-189">초기 테스트를 완료 한 후에는 토폴로지 작성기를 다시 실행 하 여 배포 해야 하는 역할을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e57cf-189">After you have completed your initial testing, you can run Topology Builder again to select the roles you need to deploy.</span></span>
    
      - <span data-ttu-id="e57cf-190">설치해야 하는 역할을 선택하고 이 역할에 맞게 하드웨어를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="e57cf-190">Select roles that you need to install, and then set up the hardware to accommodate the selected roles.</span></span>
    
    <span data-ttu-id="e57cf-191">시나리오 2의 경우 기존 배포가 있고 인프라가 새 역할에 대해 준비 되어 있거나 기존 역할을 새 프런트 엔드 서버에 연결 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e57cf-191">For scenario two, you have an existing deployment and your infrastructure is ready for new roles or you need to associate existing roles with a new Front End Server:</span></span>
    
      - <span data-ttu-id="e57cf-192">이 경우 배포 하거나 새 프런트 엔드 서버에 연결 하려는 역할을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e57cf-192">In this case, you will select the roles that you intend to deploy or associate with the new Front End Server.</span></span> <span data-ttu-id="e57cf-193">어느 경우든 계속해 역할을 정의하고 필요한 하드웨어를 설정한 후 설치를 계속합니다.</span><span class="sxs-lookup"><span data-stu-id="e57cf-193">In either case, you will proceed with the definition of the roles, set up any needed hardware, and proceed with the installation.</span></span>

7.  <span data-ttu-id="e57cf-194">**SQL 저장소 정의** 페이지에서 다음 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="e57cf-194">On the **Define the SQL store** page, do one of the following:</span></span>
    
      - <span data-ttu-id="e57cf-195">토폴로지에 이미 정의된 기존 SQL Server 저장소를 사용하려면 **SQL 저장소**에서 인스턴스를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e57cf-195">To use an existing SQL Server store that has already been defined in your topology, select an instance from **SQL store**.</span></span>
    
      - <span data-ttu-id="e57cf-196">풀 정보를 저장할 새 SQL Server 인스턴스를 정의 하려면 **새로 만들기** 를 클릭 하 고 **새 sql 저장소 정의** 대화 상자에서 **SQL Server FQDN**을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e57cf-196">To define a new SQL Server instance to store pool information, click **New** and then specify the **SQL Server FQDN**in the **Define New SQL Store** dialog box.</span></span>
    
      - <span data-ttu-id="e57cf-197">SQL Server 인스턴스 이름을 지정하려면 **명명된 인스턴스**를 선택하고 인스턴스 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="e57cf-197">To specify the name of a SQL Server instance, select **Named Instance**, and then specify the name of the instance.</span></span>
    
      - <span data-ttu-id="e57cf-198">기본 인스턴스를 사용하려면 **기본 인스턴스**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="e57cf-198">To use the default instance, click **Default instance**.</span></span>
    
      - <span data-ttu-id="e57cf-199">SQL 미러링을 사용하려면 **SQL 미러링 사용**을 선택하고 기존 인스턴스를 선택하거나 새 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="e57cf-199">To use SQL Mirroring, select **Enable SQL mirroring** and select an existing instance or create a new instance.</span></span>

8.  <span data-ttu-id="e57cf-200">**파일 공유 정의** 페이지에서 다음 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="e57cf-200">On the **Define the file share** page, do one of the following:</span></span>
    
      - <span data-ttu-id="e57cf-201">토폴로지에 이미 정의된 파일 공유를 사용하려면 **이전에 정의된 파일 공유 사용**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e57cf-201">To use a file share that has already been defined in your topology, select **Use a previously defined file share**.</span></span>
    
      - <span data-ttu-id="e57cf-202">새 파일 공유를 정의하려면 **새 파일 공유 정의**를 선택하고 **파일 서버 FQDN** 상자에 파일 공유가 있는 기존 파일 서버의 FQDN을 입력한 다음 **파일 공유** 상자에 파일 공유 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="e57cf-202">To define a new file share, select **Define a new file share**, in the **File Server FQDN** box, enter the FQDN of the existing file server where the file share is to reside, and then enter a name for the file share in the **File Share** box.</span></span>
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="e57cf-203">Lync Server 2013에 대 한 파일 공유는 프런트 엔드 서버에 배치할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e57cf-203">The file share for Lync Server 2013 cannot be located on the Front End Server.</span></span> <span data-ttu-id="e57cf-204">이 예에서는 SQL Server 기반 백 엔드 서버에 파일 공유가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e57cf-204">Note that in this example, the file share has been located on the SQL Server-based Back End Server.</span></span> <span data-ttu-id="e57cf-205">이는 조직의 요구에 맞는 최적의 위치가 아닐 수 있으며, 파일 서버가 더 나은 선택일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e57cf-205">This might not be an optimal location for your organization’s requirements, and a file server might be a better choice.</span></span> <span data-ttu-id="e57cf-206">만들어진 파일 공유가 없는 상태에서 파일 공유를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e57cf-206">You can define the file share without the file share having been created.</span></span> <span data-ttu-id="e57cf-207">그러려면 토폴로지를 게시하기 전에 정의한 위치에 파일 공유를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e57cf-207">You will need to create the file share in the location you define before you publish the topology.</span></span>

    
    </div>

9.  <span data-ttu-id="e57cf-208">**웹 서비스 URL 지정** 페이지에서 다음 중 하나 이상을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="e57cf-208">On the **Specify the Web Services URL** page, do one or both of the following:</span></span>
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="e57cf-209">기본 URL은 URL에서 https://를 생략한 웹 서비스 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="e57cf-209">The base URL is the Web Services identity for the URL, minus the https://.</span></span> <span data-ttu-id="e57cf-210">예를 들어 풀의 웹 서비스에 대 한 전체 URL이 인 https://pool01.contoso.net경우 기본 URL은 pool01.contoso.net입니다.</span><span class="sxs-lookup"><span data-stu-id="e57cf-210">For example, if the full URL for the Web Services of the pool is https://pool01.contoso.net, the base URL is pool01.contoso.net.</span></span>

    
    </div>
    
    <div>
    

    > [!WARNING]
    > <span data-ttu-id="e57cf-211">프런트 엔드 풀 또는 프런트 엔드 서버가 두 개 이상 있는 경우에는 외부 웹 서비스 FQDN이 고유 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e57cf-211">If you have more than one Front End pool or Front End Server, the external Web services FQDN must be unique.</span></span> <span data-ttu-id="e57cf-212">예를 들어 프런트 엔드 서버의 외부 웹 서비스 FQDN을 <STRONG>pool01.contoso.com</STRONG>로 정의 하는 경우 다른 프런트 엔드 풀 또는 프런트 엔드 서버에 대해 <STRONG>pool01.contoso.com</STRONG> 를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e57cf-212">For example, if you define the external Web services FQDN of a Front End Server as <STRONG>pool01.contoso.com</STRONG>, you cannot use <STRONG>pool01.contoso.com</STRONG> for another Front End pool or Front End Server.</span></span>

    
    </div>
    
    1.  <span data-ttu-id="e57cf-213">DNS 부하 분산을 구성 하는 경우 내부 **웹 서비스 풀 Fqdn 다시 정의** 확인란을 선택 하 고, 내부 기본 url (예: 내부-\<기본 Url\>)을 **내부 기본 url**에 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="e57cf-213">If you are configuring DNS load balancing, select the **Override internal Web Services pool FQDN** check box, enter the internal base URL (which must be different from the pool FQDN and could be, for example, internal-\<your base URL\>) in **Internal Base URL**.</span></span>
        
        <div>
        

        > [!WARNING]
        > <span data-ttu-id="e57cf-214">내부 웹 서비스를 자체 정의 된 FQDN으로 재정의 하려는 경우 각 FQDN은 다른 프런트 엔드 풀, 디렉터 또는 디렉터 풀에서 고유 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e57cf-214">If you decide to override the Internal web services with a self-defined FQDN, each FQDN must be unique from any other Front End pool, Director or a Director pool.</span></span> <span data-ttu-id="e57cf-215">Url 또는 정규화 된 도메인 이름을 정의할 때는 표준 문자 (-Z, a-z, 0 – 9 및 하이픈 포함) <STRONG>만 사용</STRONG> 합니다.</span><span class="sxs-lookup"><span data-stu-id="e57cf-215"><STRONG>Use only standard characters</STRONG> (including A–Z, a–z, 0–9, and hyphens) when defining URLs or fully qualified domain names.</span></span> <span data-ttu-id="e57cf-216">유니코드 문자나 밑줄은 사용하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="e57cf-216">Do not use Unicode characters or underscores.</span></span> <span data-ttu-id="e57cf-217">URL 또는 FQDN의 비표준 문자는 외부 DNS 및 공용 CAs에서 지원 되지 않는 경우가 많습니다 (즉, URL 또는 FQDN을 인증서의 주체 이름 또는 주체 대체 이름에 할당 해야 하는 경우).</span><span class="sxs-lookup"><span data-stu-id="e57cf-217">Nonstandard characters in a URL or FQDN are often not supported by external DNS and public CAs (that is, when the URL or FQDN must be assigned to the subject name or subject alternative name in the certificate).</span></span>

        
        </div>
    
    2.  <span data-ttu-id="e57cf-218">필요한 경우 외부 **기본 url에**외부 기본 url을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="e57cf-218">Optionally enter the external base URL in **External Base URL**.</span></span> <span data-ttu-id="e57cf-219">외부 기본 URL을 입력 하 여 내부 도메인 명명과 구분 합니다.</span><span class="sxs-lookup"><span data-stu-id="e57cf-219">You would enter the external base URL to differentiate it from your internal domain naming.</span></span> <span data-ttu-id="e57cf-220">내부 도메인은 contoso.net이고 외부 도메인 이름은 contoso.com인 경우를 예로 들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e57cf-220">For example, your internal domain is contoso.net, but your external domain name is contoso.com.</span></span> <span data-ttu-id="e57cf-221">Contoso.com 도메인 이름을 사용 하 여 URL을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="e57cf-221">You would define the URL using the contoso.com domain name.</span></span> <span data-ttu-id="e57cf-222">이는 역방향 프록시의 경우에도 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="e57cf-222">This is also important in the case of a reverse proxy.</span></span> <span data-ttu-id="e57cf-223">외부 기본 URL 도메인 이름은 역방향 프록시의 FQDN에 대 한 도메인 이름과 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="e57cf-223">The external base URL domain name would be the same as the domain name of the FQDN of the reverse proxy.</span></span> <span data-ttu-id="e57cf-224">인스턴트 메시징 및 현재 상태에는 프런트 엔드 풀에 대 한 HTTP 액세스가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="e57cf-224">Instant messaging and presence does require HTTP access to the Front End pool.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="e57cf-225">DNS 부하 분산을 사용하려면 적절한 DNS 레코드를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e57cf-225">To use DNS load balancing, you must create the appropriate DNS records.</span></span> <span data-ttu-id="e57cf-226">자세한 내용은 <A href="lync-server-2013-configure-dns-for-load-balancing.md">Lync Server 2013에서 부하 분산을 위한 DNS 구성을</A>참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="e57cf-226">For details, see <A href="lync-server-2013-configure-dns-for-load-balancing.md">Configure DNS for load balancing in Lync Server 2013</A>.</span></span>

    
    </div>

10. <span data-ttu-id="e57cf-227">**기능 선택** 페이지에서 **회의** 를 선택한 경우 **office web Apps 서버 선택** 페이지에서 **office web apps server에 풀 연결** 을 선택 하 고 **새로 만들기** (또는 드롭다운 목록에서 기존 Office Web Apps 서버 선택)를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e57cf-227">If you selected **Conferencing** on the **Select Features** page, on the **Select an Office Web Apps Server** page select **Associate pool with an Office Web Apps Server** and then click **New** (or select an existing Office Web Apps Server from the drop-down list).</span></span>

11. <span data-ttu-id="e57cf-228">**새 Office Web Apps Server 정의** 대화 상자에서 **Office Web Apps Server FQDN** 상자에 Office Web Apps Server 컴퓨터의 FQDN(정규화된 도메인 이름)을 입력합니다. 이렇게 하면 Office Web Apps Server 검색 URL이 **Office Web Apps Server 검색 URL** 상자에 자동으로 입력됩니다.</span><span class="sxs-lookup"><span data-stu-id="e57cf-228">In the **Define New Office Web Apps Server** dialog box, type the fully qualified domain name (FQDN) of your Office Web Apps Server computer in the **Office Web Apps Server FQDN** box; when you do this, your Office Web Apps Server discovery URL should automatically be entered into the **Office Web Apps Server discovery URL** box.</span></span>
    
    <span data-ttu-id="e57cf-229">Office Web Apps 서버를 Lync Server 2013와 동일한 네트워크 영역에 설치 하는 경우에는 **Office Web Apps 서버를 외부 네트워크 (경계/인터넷)에 배포** 하는 옵션을 선택 하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e57cf-229">If the Office Web Apps Server is installed on-premises and in the same network zone as Lync Server 2013 then the option **Office Web Apps Server is deployed in an external network (that is, perimeter/Internet)** should not be selected.</span></span>
    
    <span data-ttu-id="e57cf-230">Office Web Apps Server가 내부 방화벽 외부에 배포된 경우 **Office Web Apps Server가 외부 네트워크에 배포되어 있습니다(경계/인터넷).** 옵션을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e57cf-230">If the Office Web Apps Server is deployed outside your internal firewall, then select the option **Office Web Apps Server is deployed in an external network (that is, perimeter/Internet)**.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="e57cf-231">자세한 내용은 <A href="lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md">Office Web Apps 서버 및 Lync server 2013의 통합 구성을</A>참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e57cf-231">For details, see <A href="lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md">Configuring integration with Office Web Apps Server and Lync Server 2013</A>.</span></span>

    
    </div>

12. <span data-ttu-id="e57cf-232">**보관 SQL 저장소 정의** 페이지에서 기존 인스턴스 또는 SQL Server를 선택하거나 보관 데이터와 연결된 데이터를 저장할 새 인스턴스를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="e57cf-232">On the **Define the Archiving SQL store** page, select an existing instance or SQL Server, or define a new instance to store the data associated with archiving data.</span></span>

13. <span data-ttu-id="e57cf-233">**모니터링 SQL 저장소 정의** 페이지에서 기존 인스턴스 또는 SQL Server를 선택하거나 모니터링 데이터와 연결된 데이터를 저장할 새 인스턴스를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="e57cf-233">On the **Define the Monitoring SQL store** page, select an existing instance or SQL Server, or define a new instance to store the data associated with monitoring data.</span></span>

14. <span data-ttu-id="e57cf-234">**다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="e57cf-234">Click **Next**.</span></span> <span data-ttu-id="e57cf-235">**서버 역할을이 프런트 엔드 풀과 연결** 페이지에서 다른 역할 서버를 정의한 경우에는 서버 역할을 구성할 수 있도록 별도의 역할 구성 마법사 페이지가 열립니다.</span><span class="sxs-lookup"><span data-stu-id="e57cf-235">If you defined other role servers on the **Associate server roles with this Front End pool** page, separate role configuration wizard pages will open to let you configure the server roles.</span></span> <span data-ttu-id="e57cf-236">자세한 내용은 다음을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="e57cf-236">For details, see the following:</span></span>
    
    [<span data-ttu-id="e57cf-237">Lync Server 2013에서 외부 사용자 액세스 배포</span><span class="sxs-lookup"><span data-stu-id="e57cf-237">Deploying external user access in Lync Server 2013</span></span>](lync-server-2013-deploying-external-user-access.md)

15. <span data-ttu-id="e57cf-238">구성하고 배포할 추가 서버 역할을 선택하지 않았거나 추가 역할 서버 구성을 마친 경우 **마침**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="e57cf-238">If you did not select additional server roles to configure and deploy, or when you have finished the configuration of the additional role servers, click **Finish**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

