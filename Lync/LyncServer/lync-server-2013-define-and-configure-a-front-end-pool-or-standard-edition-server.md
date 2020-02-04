---
title: 프런트 엔드 풀 또는 Standard Edition 서버 정의 및 구성
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
ms.openlocfilehash: ddc430370c59e279e0e36aa662da0f33973e0d80
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762766"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="define-and-configure-a-front-end-pool-or-standard-edition-server-in-lync-server-2013"></a><span data-ttu-id="228d0-102">Lync Server 2013에서 프런트 엔드 풀 또는 Standard Edition 서버 정의 및 구성</span><span class="sxs-lookup"><span data-stu-id="228d0-102">Define and configure a Front End pool or Standard Edition server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="228d0-103">_**마지막으로 수정한 주제:** 2013-03-08_</span><span class="sxs-lookup"><span data-stu-id="228d0-103">_**Topic Last Modified:** 2013-03-08_</span></span>

<span data-ttu-id="228d0-104">이 절차에서는 로컬 관리자 또는 특권 도메인 그룹의 멤버 자격을 요구 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="228d0-104">This procedure does not require membership in a local administrator or privileged domain group.</span></span> <span data-ttu-id="228d0-105">표준 사용자로 컴퓨터에 로그온 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="228d0-105">You should log on to a computer as a standard user.</span></span>

<span data-ttu-id="228d0-106">엔터프라이즈 서버를 배포 하는 경우 풀에 있는 프런트 엔드 서버의 최소 수는 항상 실행 중 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="228d0-106">If you are deploying an Enterprise server, a minimum number of Front End Servers in a pool must be running at all times.</span></span> <span data-ttu-id="228d0-107">다음 표에는 이러한 요구 사항이 요약 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="228d0-107">The following table summarizes these requirements.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="228d0-108">풀의 총 프런트 엔드 서버 수</span><span class="sxs-lookup"><span data-stu-id="228d0-108">Total number of Front End Servers in the pool</span></span></th>
<th><span data-ttu-id="228d0-109">풀을 작동 하기 위해 실행 해야 하는 서버 수</span><span class="sxs-lookup"><span data-stu-id="228d0-109">Number of servers that must be running for pool to be functional</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="228d0-110">1-2</span><span class="sxs-lookup"><span data-stu-id="228d0-110">1-2</span></span></p></td>
<td><p><span data-ttu-id="228d0-111">1</span><span class="sxs-lookup"><span data-stu-id="228d0-111">1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="228d0-112">3-4</span><span class="sxs-lookup"><span data-stu-id="228d0-112">3-4</span></span></p></td>
<td><p><span data-ttu-id="228d0-113">2</span><span class="sxs-lookup"><span data-stu-id="228d0-113">2</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="228d0-114">5-6</span><span class="sxs-lookup"><span data-stu-id="228d0-114">5-6</span></span></p></td>
<td><p><span data-ttu-id="228d0-115">3</span><span class="sxs-lookup"><span data-stu-id="228d0-115">3</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="228d0-116">7-8</span><span class="sxs-lookup"><span data-stu-id="228d0-116">7-8</span></span></p></td>
<td><p><span data-ttu-id="228d0-117">4(tcp/ipv4)</span><span class="sxs-lookup"><span data-stu-id="228d0-117">4</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="228d0-118">9-10</span><span class="sxs-lookup"><span data-stu-id="228d0-118">9-10</span></span></p></td>
<td><p><span data-ttu-id="228d0-119">5mb</span><span class="sxs-lookup"><span data-stu-id="228d0-119">5</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="228d0-120">11-12</span><span class="sxs-lookup"><span data-stu-id="228d0-120">11-12</span></span></p></td>
<td><p><span data-ttu-id="228d0-121">26</span><span class="sxs-lookup"><span data-stu-id="228d0-121">6</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]
> <span data-ttu-id="228d0-122">Lync Server 2013의 경우 풀에서 프런트 엔드 서버를 추가 하거나 제거할 때마다 서비스를 다시 시작 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="228d0-122">For Lync Server 2013, any time you add or remove a Front End Server from the pool, you must restart services.</span></span> <span data-ttu-id="228d0-123">서버 제거 및 추가는 별도의 작업으로 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="228d0-123">Removing and adding servers should be done as separate operations.</span></span> <span data-ttu-id="228d0-124">예를 들어 프런트 엔드 서버 두 개를 추가 하 고 프런트 엔드 서버 두 개를 제거 하려면 다음 프로세스를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="228d0-124">For example, if you are going to add two Front End Servers and remove two Front End Servers, use the following process:</span></span> 
> <OL>
> <LI>
> <P><span data-ttu-id="228d0-125">두 프런트 엔드 서버를 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="228d0-125">Remove the two Front End Servers.</span></span></P>
> <LI>
> <P><span data-ttu-id="228d0-126">토폴로지를 게시 하 고 다시 활성화 합니다.</span><span class="sxs-lookup"><span data-stu-id="228d0-126">Publish and re-activate the topology.</span></span></P>
> <LI>
> <P><span data-ttu-id="228d0-127">서비스 다시 시작</span><span class="sxs-lookup"><span data-stu-id="228d0-127">Restart the services</span></span></P>
> <LI>
> <P><span data-ttu-id="228d0-128">두 프런트 엔드 서버를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="228d0-128">Add the two Front End Servers.</span></span></P>
> <LI>
> <P><span data-ttu-id="228d0-129">토폴로지를 게시 하 고 다시 활성화 합니다.</span><span class="sxs-lookup"><span data-stu-id="228d0-129">Publish and re-activate the topology.</span></span></P>
> <LI>
> <P><span data-ttu-id="228d0-130">서비스를 다시 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="228d0-130">Restart the services.</span></span></P></LI></OL>



</div>

<span data-ttu-id="228d0-131">토폴로지를 정의한 후에는 다음 절차를 사용 하 여 사이트의 프런트 엔드 풀을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="228d0-131">After you have defined your topology, use the following procedure to define a Front End pool for your site.</span></span> <span data-ttu-id="228d0-132">토폴로지를 정의 하는 방법에 대 한 자세한 내용은 [Lync Server 2013에 대 한 토폴로지 작성기에서 토폴로지 정의 및 구성을](lync-server-2013-define-and-configure-a-topology-in-topology-builder.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="228d0-132">For details about defining the topology, see [Define and configure a topology in Topology Builder for Lync Server 2013](lync-server-2013-define-and-configure-a-topology-in-topology-builder.md).</span></span>

<div>

## <a name="to-define-a-front-end-pool"></a><span data-ttu-id="228d0-133">프런트 엔드 풀을 정의 하려면</span><span class="sxs-lookup"><span data-stu-id="228d0-133">To define a Front End pool</span></span>

1.  <span data-ttu-id="228d0-134">새 프런트 엔드 풀 정의 마법사의 **새 프런트 엔드 풀 정의** 페이지에서 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="228d0-134">In the Define New Front End Pool Wizard, on the **Define the New Front End pool** page, click **Next**.</span></span>

2.  <span data-ttu-id="228d0-135">**프런트 엔드 풀 Fqdn 정의** 페이지에서 만들려는 풀의 fqdn (정규화 된 도메인 이름)을 입력 하 고 **Enterprise Edition 프런트 엔드 풀**을 클릭 한 후 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="228d0-135">On the **Define the Front End pool FQDN** page, enter a fully qualified domain name (FQDN) for the pool you are creating, click **Enterprise Edition Front End pool**, and then click **Next**.</span></span>

3.  <span data-ttu-id="228d0-136">**이 풀의 컴퓨터 정의** 페이지에서 풀의 첫 번째 프런트 엔드 서버에 대 한 컴퓨터 FQDN을 입력 한 다음 **추가**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="228d0-136">On the **Define the computers in this pool** page, enter a computer FQDN for the first Front End Server in the pool, and then click **Add**.</span></span> <span data-ttu-id="228d0-137">풀에 추가 하려는 추가 컴퓨터 (최대 12 개)에 대해이 단계를 반복한 후 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="228d0-137">Repeat this step for any additional computers (up to twelve) that you want to add to the pool, and then click **Next**.</span></span>

4.  <span data-ttu-id="228d0-138">**기능 선택** 페이지에서이 프런트 엔드 풀에 대해 원하는 기능에 해당 하는 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="228d0-138">On the **Select features** page, select the check boxes for the features that you want on this Front End pool.</span></span> <span data-ttu-id="228d0-139">예를 들어 인스턴트 메시지 (IM) 및 현재 상태 기능만 배포 하는 경우에는 **회의** 확인란을 선택 하 여 단체 메신저를 허용 하 되 **전화 접속 (PSTN) 회의**, **엔터프라이즈 음성**또는 **통화 허용 제어** 확인란은 음성, 비디오, 공동 작업 회의 기능을 나타내므로 선택 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="228d0-139">For example, if you are deploying only instant messaging (IM) and presence features, you would select the **Conferencing** check box to allow multiparty IM but would not select the **Dial-in (PSTN) conferencing**, **Enterprise Voice**, or **Call Admission Control** check boxes, because they represent voice, video, and collaborative conferencing features.</span></span>
    
      - <span data-ttu-id="228d0-140">**회의**   : 다음을 비롯 한 다양 한 기능을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="228d0-140">**Conferencing**   This selection enables a rich set of features including:</span></span>
        
          - <span data-ttu-id="228d0-141">IM 세션에 두 명 이상의 파티가 있는 IM</span><span class="sxs-lookup"><span data-stu-id="228d0-141">IM with more than two parties in an IM session.</span></span>
        
          - <span data-ttu-id="228d0-142">회의에는 문서 공동 작업, 응용 프로그램 공유, 데스크톱 공유가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="228d0-142">Conferencing, which includes document collaboration, application sharing, and desktop sharing.</span></span>
        
          - <span data-ttu-id="228d0-143">Live Meeting 서비스 또는 타사 오디오 브리지와 같은 외부 서비스에 대 한 필요 없이 사용자가 실시간으로 오디오/비디오 (A/V) 회의를 할 수 있는 A/V 회의.</span><span class="sxs-lookup"><span data-stu-id="228d0-143">A/V conferencing, which enables users to have real-time audio/video (A/V) conferences without the need for external services such as the Live Meeting service or a third-party audio bridge.</span></span>
    
      - <span data-ttu-id="228d0-144">**전화 접속 (pstn) 회의**   를 통해 사용자는 오디오 회의 공급자 없이도 pstn (공개 전환 통신 네트워크) 전화를 사용 하 여 Lync Server 2013 컨퍼런스의 오디오 부분에 참가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="228d0-144">**Dial-in (PSTN) conferencing**   Allows users to join the audio portion of a Lync Server 2013 conference by using a public switched telephone network (PSTN) phone without requiring an audio conferencing provider.</span></span>
    
      - <span data-ttu-id="228d0-145">**Enterprise voice**   enterprise voice는 사용자가 전화를 걸고 받을 수 있는 Lync Server 2013의 VoIP (Voice over IP) 솔루션입니다.</span><span class="sxs-lookup"><span data-stu-id="228d0-145">**Enterprise Voice**   Enterprise Voice is the Voice over IP (VoIP) solution in Lync Server 2013 that allows users to make and receive phone calls.</span></span> <span data-ttu-id="228d0-146">음성 통화, 음성 메일 및 하드웨어 장치 또는 소프트웨어 클라이언트를 사용 하는 기타 기능을 위해 Lync Server 2013을 사용할 계획인 경우이 기능을 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="228d0-146">You would deploy this feature if you plan to use Lync Server 2013 for voice calls, voice mail, and other functions that use a hardware device or a software client.</span></span>
    
      - <span data-ttu-id="228d0-147">**Cac (통화 허용 제어)**   cac는 사용 가능한 네트워크 대역폭을 기준으로 음성 또는 영상 통화와 같은 실시간 통신 세션을 설정할 수 있는지 여부를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="228d0-147">**Call admission control (CAC)**   CAC determines, based on available network bandwidth, whether to allow real-time communications sessions such as voice or video calls to be established.</span></span> <span data-ttu-id="228d0-148">IM 및 현재 상태만 배포 하는 경우에는 이러한 두 기능 모두 CAC를 사용 하지 않으므로 CAC가 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="228d0-148">If you have deployed only IM and presence, CAC is not needed because neither of these two features uses CAC.</span></span>
    
      - <span data-ttu-id="228d0-149">**보관**   보관을 통해 Lync Server 2013를 통해 전송 되는 IM 콘텐츠, 회의 (모임) 콘텐츠 또는 둘 다를 보관할 수 있는 방법을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="228d0-149">**Archiving**   Archiving provides a way for you to archive IM content, conferencing (meeting) content, or both that is sent through Lync Server 2013.</span></span>
    
      - <span data-ttu-id="228d0-150">\*\*\*\*   모니터링 서버 모니터링을 사용 하면 네트워크 및 끝점의 미디어 품질, VoIP 통화와 관련 된 사용 정보, IM 메시지, A/V 대화, 모임, 응용 프로그램 공유, 파일 전송, 실패 한 통화에 대 한 통화 오류 및 문제 해결 정보를 설명 하는 숫자 데이터를 수집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="228d0-150">**Monitoring**   Monitoring Server enables you to collect numerical data that describes the media quality on your network and endpoints, usage information related to VoIP calls, IM messages, A/V conversations, meetings, application sharing, and file transfers, and call error and troubleshooting information for failed calls.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="228d0-151">배포에서 CAC를 사용 하도록 설정 하려면 중앙 사이트 당 정확히 하나의 풀에서 CAC를 사용 하도록 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="228d0-151">If you would like to enable CAC in your deployment, it is required that you enable CAC in exactly one pool per central site.</span></span> <span data-ttu-id="228d0-152">음성 기능 또는 A/V 회의를 배포 하는 경우에는 CAC가 권장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="228d0-152">CAC is recommended if you are deploying voice features or A/V conferencing.</span></span>

    
    </div>
    
    <span data-ttu-id="228d0-153">다음 표에서는 사용 가능한 기능 (위쪽)과 사용자에 게 제공 되는 기능 (왼쪽)을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="228d0-153">The following table shows the available features (top) and the functions offered to users (left).</span></span> <span data-ttu-id="228d0-154">테이블의 선택 사항에 따라 조직에서 해당 기능을 사용 하도록 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="228d0-154">The selections in the table are what you should select to enable those features for your organization.</span></span>
    
    
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
    <th><span data-ttu-id="228d0-155">회의</span><span class="sxs-lookup"><span data-stu-id="228d0-155">Conferencing</span></span></th>
    <th><span data-ttu-id="228d0-156">전화 접속 회의</span><span class="sxs-lookup"><span data-stu-id="228d0-156">Dial-In Conferencing</span></span></th>
    <th><span data-ttu-id="228d0-157">Enterprise Voice</span><span class="sxs-lookup"><span data-stu-id="228d0-157">Enterprise Voice</span></span></th>
    <th><span data-ttu-id="228d0-158">통화 허용 제어</span><span class="sxs-lookup"><span data-stu-id="228d0-158">Call Admission Control</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="228d0-159">인스턴트 메시징 및 현재 상태</span><span class="sxs-lookup"><span data-stu-id="228d0-159">Instant messaging and presence</span></span></p></td>
    <td><p><span data-ttu-id="228d0-160">축</span><span class="sxs-lookup"><span data-stu-id="228d0-160">X</span></span></p></td>
    <td></td>
    <td></td>
    <td></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="228d0-161">회의</span><span class="sxs-lookup"><span data-stu-id="228d0-161">Conferencing</span></span></p></td>
    <td><p><span data-ttu-id="228d0-162">축</span><span class="sxs-lookup"><span data-stu-id="228d0-162">X</span></span></p></td>
    <td><p><span data-ttu-id="228d0-163">축</span><span class="sxs-lookup"><span data-stu-id="228d0-163">X</span></span></p></td>
    <td></td>
    <td></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="228d0-164">A/V 회의</span><span class="sxs-lookup"><span data-stu-id="228d0-164">A/V conferencing</span></span></p></td>
    <td><p><span data-ttu-id="228d0-165">축</span><span class="sxs-lookup"><span data-stu-id="228d0-165">X</span></span></p></td>
    <td><p><span data-ttu-id="228d0-166">축</span><span class="sxs-lookup"><span data-stu-id="228d0-166">X</span></span></p></td>
    <td></td>
    <td><p><span data-ttu-id="228d0-167">축</span><span class="sxs-lookup"><span data-stu-id="228d0-167">X</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="228d0-168">Enterprise Voice</span><span class="sxs-lookup"><span data-stu-id="228d0-168">Enterprise Voice</span></span></p></td>
    <td></td>
    <td></td>
    <td><p><span data-ttu-id="228d0-169">축</span><span class="sxs-lookup"><span data-stu-id="228d0-169">X</span></span></p></td>
    <td><p><span data-ttu-id="228d0-170">축</span><span class="sxs-lookup"><span data-stu-id="228d0-170">X</span></span></p></td>
    </tr>
    </tbody>
    </table>


5.  <span data-ttu-id="228d0-171">**Collocated 서버 역할 선택** 페이지에서 프런트 엔드 서버에 대 한 중재 서버를 collocate 독립 실행형 서버로 배포 하도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="228d0-171">On the **Select collocated server roles** page, you can to collocate the Mediation Server on the Front End Server or to deploy it as a stand-alone server.</span></span>
    
    <span data-ttu-id="228d0-172">프런트 엔드 풀에서 중재 서버를 collocate 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="228d0-172">You can collocate the Mediation Server on the Front End pool.</span></span>
    
      - <span data-ttu-id="228d0-173">엔터프라이즈 버전 프런트 엔드 풀에서 중재 서버를 collocate 하려면 확인란이 선택 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="228d0-173">If you intend to collocate the Mediation Server on the Enterprise Edition Front End pool, ensure the check box is selected.</span></span> <span data-ttu-id="228d0-174">서버 역할이 풀 서버에 배포 됩니다.</span><span class="sxs-lookup"><span data-stu-id="228d0-174">The server role will be deployed on the pool servers.</span></span>
    
      - <span data-ttu-id="228d0-175">중재 서버를 독립 실행형 서버로 배포 하려는 경우 해당 확인란의 선택을 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="228d0-175">If you intend to deploy the Mediation Server as a stand-alone server, clear the appropriate check box.</span></span> <span data-ttu-id="228d0-176">프런트 엔드 서버를 완전히 배포한 후에는 중재 서버를 별도의 배포 단계에서 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="228d0-176">You will deploy Mediation Server in a separate deployment step after you completely deploy the Front End Server.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="228d0-177">가능한 경우 중재 서버를 collocate 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="228d0-177">We recommend that you collocate the Mediation Server if possible.</span></span> <span data-ttu-id="228d0-178">Collocated 또는 독립 실행형 중재 서버에 대 한 지원에 대 한 자세한 내용은 계획 설명서의 <A href="lync-server-2013-components-and-topologies-for-mediation-server.md">Lync server 2013에서 중재 서버용 구성 요소 및 토폴로지</A> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="228d0-178">For details about support for collocated or stand-alone Mediation Servers, see <A href="lync-server-2013-components-and-topologies-for-mediation-server.md">Components and topologies for Mediation Server in Lync Server 2013</A> in the Planning documentation.</span></span>

    
    </div>

6.  <span data-ttu-id="228d0-179">**이 프런트 엔드 풀을 사용 하 여 서버 역할 연결** 페이지를 통해 서버 역할을 정의 하 고 프런트 엔드 풀에 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="228d0-179">The **Associate server roles with this Front End pool** page lets you define and associate server roles with the Front End pool.</span></span> <span data-ttu-id="228d0-180">다음 역할을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="228d0-180">The following role is available:</span></span>
    
    <span data-ttu-id="228d0-181">**Edge 풀**   사용 단일 edge 서버 또는 edge 서버 풀을 정의 하 고 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="228d0-181">**Enable an Edge pool**   Defines and associates a single Edge Server or a pool of Edge Servers.</span></span> <span data-ttu-id="228d0-182">Edge 서버는 페더레이션 사용자와 조직 외부의 사용자 간 통신 및 공동 작업을 용이 하 게 합니다.</span><span class="sxs-lookup"><span data-stu-id="228d0-182">An Edge Server facilitates communication and collaboration between users inside the organization and people outside the organization, including federated users.</span></span>
    
    <span data-ttu-id="228d0-183">서버 역할을 배포 하 고 연결 하는 데 사용할 수 있는 두 가지 시나리오가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="228d0-183">There are two possible scenarios that you can use to deploy and associate the server roles:</span></span>
    
    <span data-ttu-id="228d0-184">시나리오 1의 경우 새 설치에 대 한 새 토폴로지를 정의 하 게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="228d0-184">For scenario one, you are defining a new topology for a new installation.</span></span> <span data-ttu-id="228d0-185">다음 두 가지 방법 중 하나를 사용 하 여 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="228d0-185">You can approach the installation in one of two ways:</span></span>
    
      - <span data-ttu-id="228d0-186">확인란을 선택 하지 않은 상태로 두고 토폴로지 정의를 계속 진행 합니다.</span><span class="sxs-lookup"><span data-stu-id="228d0-186">Leave the check box clear and proceed with defining the topology.</span></span> <span data-ttu-id="228d0-187">프런트 엔드 및 백 엔드 서버 역할을 게시 하 고 구성 하 고 테스트 한 후에는 토폴로지 작성기를 다시 실행 하 여 토폴로지에 역할 서버를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="228d0-187">After you have published, configured, and tested the Front End and Back End Server roles, you can run Topology Builder again to add the role servers to the topology.</span></span> <span data-ttu-id="228d0-188">이 전략을 사용 하면 추가 역할에서 추가적인 문제가 발생 하지 않고 프런트 엔드 풀 및 SQL Server를 실행 하는 서버를 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="228d0-188">This strategy will enable you to test the Front End pool and the server running SQL Server without additional complications from additional roles.</span></span> <span data-ttu-id="228d0-189">초기 테스트를 완료 한 후 토폴로지 작성기를 다시 실행 하 여 배포 해야 하는 역할을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="228d0-189">After you have completed your initial testing, you can run Topology Builder again to select the roles you need to deploy.</span></span>
    
      - <span data-ttu-id="228d0-190">설치 해야 하는 역할을 선택한 다음 선택한 역할을 수용할 수 있도록 하드웨어를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="228d0-190">Select roles that you need to install, and then set up the hardware to accommodate the selected roles.</span></span>
    
    <span data-ttu-id="228d0-191">시나리오 2의 경우 기존 배포가 있고 인프라에서 새 역할을 사용할 준비가 되었거나 기존 역할을 새 프런트 엔드 서버와 연결 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="228d0-191">For scenario two, you have an existing deployment and your infrastructure is ready for new roles or you need to associate existing roles with a new Front End Server:</span></span>
    
      - <span data-ttu-id="228d0-192">이 경우에는 새 프런트 엔드 서버에 배포 하거나 연결할 역할을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="228d0-192">In this case, you will select the roles that you intend to deploy or associate with the new Front End Server.</span></span> <span data-ttu-id="228d0-193">두 경우 모두 역할 정의를 진행 하 고, 필요한 하드웨어를 설정 하 고, 설치를 진행 하 게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="228d0-193">In either case, you will proceed with the definition of the roles, set up any needed hardware, and proceed with the installation.</span></span>

7.  <span data-ttu-id="228d0-194">**SQL 스토어 정의** 페이지에서 다음 중 하나를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="228d0-194">On the **Define the SQL store** page, do one of the following:</span></span>
    
      - <span data-ttu-id="228d0-195">토폴로지에 이미 정의 된 기존 SQL Server 저장소를 사용 하려면 **SQL store**에서 인스턴스를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="228d0-195">To use an existing SQL Server store that has already been defined in your topology, select an instance from **SQL store**.</span></span>
    
      - <span data-ttu-id="228d0-196">새 SQL Server 인스턴스를 정의 하 여 풀 정보를 저장 하려면 **새로 만들기** 를 클릭 한 다음 **새 sql store 정의** 대화 상자에서 **SQL server FQDN**을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="228d0-196">To define a new SQL Server instance to store pool information, click **New** and then specify the **SQL Server FQDN**in the **Define New SQL Store** dialog box.</span></span>
    
      - <span data-ttu-id="228d0-197">SQL Server 인스턴스의 이름을 지정 하려면 **명명 된 인스턴스**를 선택한 다음 인스턴스의 이름을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="228d0-197">To specify the name of a SQL Server instance, select **Named Instance**, and then specify the name of the instance.</span></span>
    
      - <span data-ttu-id="228d0-198">기본 인스턴스를 사용 하려면 **기본 인스턴스**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="228d0-198">To use the default instance, click **Default instance**.</span></span>
    
      - <span data-ttu-id="228d0-199">SQL 미러링을 사용 하려면 **sql 미러링 사용** 을 선택 하 고 기존 인스턴스를 선택 하거나 새 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="228d0-199">To use SQL Mirroring, select **Enable SQL mirroring** and select an existing instance or create a new instance.</span></span>

8.  <span data-ttu-id="228d0-200">**파일 공유 정의** 페이지에서 다음 중 하나를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="228d0-200">On the **Define the file share** page, do one of the following:</span></span>
    
      - <span data-ttu-id="228d0-201">토폴로지에 이미 정의 된 파일 공유를 사용 하려면 **이전에 정의 된 파일 공유 사용**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="228d0-201">To use a file share that has already been defined in your topology, select **Use a previously defined file share**.</span></span>
    
      - <span data-ttu-id="228d0-202">새 파일 공유를 정의 하려면 **새 파일 공유 정의**를 선택 하 고 **파일 서버 FQDN** 상자에 파일 공유가 위치할 기존 파일 서버의 FQDN을 입력 한 다음 **파일 공유** 상자에 파일 공유의 이름을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="228d0-202">To define a new file share, select **Define a new file share**, in the **File Server FQDN** box, enter the FQDN of the existing file server where the file share is to reside, and then enter a name for the file share in the **File Share** box.</span></span>
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="228d0-203">Lync Server 2013의 파일 공유는 프런트 엔드 서버에 있을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="228d0-203">The file share for Lync Server 2013 cannot be located on the Front End Server.</span></span> <span data-ttu-id="228d0-204">이 예제에서는 파일 공유가 SQL Server 기반 백 엔드 서버에 위치 합니다.</span><span class="sxs-lookup"><span data-stu-id="228d0-204">Note that in this example, the file share has been located on the SQL Server-based Back End Server.</span></span> <span data-ttu-id="228d0-205">이는 조직의 요구 사항에 적합 한 위치가 아닐 수 있으며 파일 서버를 선택 하는 것이 더 좋을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="228d0-205">This might not be an optimal location for your organization’s requirements, and a file server might be a better choice.</span></span> <span data-ttu-id="228d0-206">파일 공유를 만들지 않고 파일 공유를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="228d0-206">You can define the file share without the file share having been created.</span></span> <span data-ttu-id="228d0-207">토폴로지를 게시 하기 전에 사용자가 정의한 위치에 파일 공유를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="228d0-207">You will need to create the file share in the location you define before you publish the topology.</span></span>

    
    </div>

9.  <span data-ttu-id="228d0-208">**웹 서비스 URL 지정** 페이지에서 다음 중 하나 또는 모두를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="228d0-208">On the **Specify the Web Services URL** page, do one or both of the following:</span></span>
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="228d0-209">기본 URL은 URL의 웹 서비스 id (https://를 제외한)입니다.</span><span class="sxs-lookup"><span data-stu-id="228d0-209">The base URL is the Web Services identity for the URL, minus the https://.</span></span> <span data-ttu-id="228d0-210">예를 들어 풀의 웹 서비스에 대 한 전체 URL이 https://pool01.contoso.net기본 url 인 경우 pool01.contoso.net.</span><span class="sxs-lookup"><span data-stu-id="228d0-210">For example, if the full URL for the Web Services of the pool is https://pool01.contoso.net, the base URL is pool01.contoso.net.</span></span>

    
    </div>
    
    <div>
    

    > [!WARNING]
    > <span data-ttu-id="228d0-211">프런트 엔드 풀 또는 프런트 엔드 서버를 둘 이상 사용 하는 경우에는 외부 웹 서비스 FQDN이 고유 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="228d0-211">If you have more than one Front End pool or Front End Server, the external Web services FQDN must be unique.</span></span> <span data-ttu-id="228d0-212">예를 들어 프런트 엔드 서버의 외부 웹 서비스 FQDN을 <STRONG>pool01.contoso.com</STRONG>로 정의 하는 경우 다른 프런트 엔드 풀 또는 프런트 엔드 서버에 대해 <STRONG>pool01.contoso.com</STRONG> 를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="228d0-212">For example, if you define the external Web services FQDN of a Front End Server as <STRONG>pool01.contoso.com</STRONG>, you cannot use <STRONG>pool01.contoso.com</STRONG> for another Front End pool or Front End Server.</span></span>

    
    </div>
    
    1.  <span data-ttu-id="228d0-213">DNS 부하 분산을 구성 하는 경우 내부 **웹 서비스 풀 Fqdn 무시** 확인란을 선택 하 고 내부 기본 url (예:\<사용자의 기본 url\>과 내부 기본 url)을 입력 합니다. \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="228d0-213">If you are configuring DNS load balancing, select the **Override internal Web Services pool FQDN** check box, enter the internal base URL (which must be different from the pool FQDN and could be, for example, internal-\<your base URL\>) in **Internal Base URL**.</span></span>
        
        <div>
        

        > [!WARNING]
        > <span data-ttu-id="228d0-214">내부 웹 서비스를 자체 정의 FQDN으로 재정의 하기로 결정 한 경우 각 FQDN은 다른 프런트 엔드 풀, 디렉터 또는 디렉터 풀에서 고유 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="228d0-214">If you decide to override the Internal web services with a self-defined FQDN, each FQDN must be unique from any other Front End pool, Director or a Director pool.</span></span> <span data-ttu-id="228d0-215">Url 또는 정규화 된 도메인 이름을 정의할 때는 표준 문자 (-Z, a-z, 0 – 9 및 하이픈 포함) <STRONG>만 사용</STRONG> 합니다.</span><span class="sxs-lookup"><span data-stu-id="228d0-215"><STRONG>Use only standard characters</STRONG> (including A–Z, a–z, 0–9, and hyphens) when defining URLs or fully qualified domain names.</span></span> <span data-ttu-id="228d0-216">유니코드 문자나 밑줄은 사용 하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="228d0-216">Do not use Unicode characters or underscores.</span></span> <span data-ttu-id="228d0-217">URL 또는 fqdn의 비표준 문자는 외부 DNS 및 공개 Ca (즉 URL 또는 FQDN을 인증서의 주체 이름 또는 주체 대체 이름에 할당 해야 하는 경우)에서 지원 되지 않는 경우가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="228d0-217">Nonstandard characters in a URL or FQDN are often not supported by external DNS and public CAs (that is, when the URL or FQDN must be assigned to the subject name or subject alternative name in the certificate).</span></span>

        
        </div>
    
    2.  <span data-ttu-id="228d0-218">필요에 **따라 외부 기본**url에 외부 기본 url을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="228d0-218">Optionally enter the external base URL in **External Base URL**.</span></span> <span data-ttu-id="228d0-219">외부 기본 URL을 입력 하 여 내부 도메인 명명을 구분 합니다.</span><span class="sxs-lookup"><span data-stu-id="228d0-219">You would enter the external base URL to differentiate it from your internal domain naming.</span></span> <span data-ttu-id="228d0-220">예를 들어 내부 도메인은 contoso.net 외부 도메인 이름은 contoso.com입니다.</span><span class="sxs-lookup"><span data-stu-id="228d0-220">For example, your internal domain is contoso.net, but your external domain name is contoso.com.</span></span> <span data-ttu-id="228d0-221">Contoso.com 도메인 이름을 사용 하 여 URL을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="228d0-221">You would define the URL using the contoso.com domain name.</span></span> <span data-ttu-id="228d0-222">이는 리버스 프록시의 경우에도 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="228d0-222">This is also important in the case of a reverse proxy.</span></span> <span data-ttu-id="228d0-223">외부 기본 URL 도메인 이름은 역방향 프록시의 FQDN에 대 한 도메인 이름과 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="228d0-223">The external base URL domain name would be the same as the domain name of the FQDN of the reverse proxy.</span></span> <span data-ttu-id="228d0-224">인스턴트 메시지 및 현재 상태에는 프런트 엔드 풀에 대 한 HTTP 액세스가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="228d0-224">Instant messaging and presence does require HTTP access to the Front End pool.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="228d0-225">DNS 부하 분산을 사용 하려면 적절 한 DNS 레코드를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="228d0-225">To use DNS load balancing, you must create the appropriate DNS records.</span></span> <span data-ttu-id="228d0-226">자세한 내용은 <A href="lync-server-2013-configure-dns-for-load-balancing.md">Lync Server 2013에서 부하 분산을 위한 DNS 구성을</A>참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="228d0-226">For details, see <A href="lync-server-2013-configure-dns-for-load-balancing.md">Configure DNS for load balancing in Lync Server 2013</A>.</span></span>

    
    </div>

10. <span data-ttu-id="228d0-227">**기능 선택** 페이지에서 **회의** 를 선택한 경우 Office web apps **서버 선택** 페이지에서 그룹을 **office web apps 서버와 연결** 을 선택 하 고 **새로 만들기** (또는 드롭다운 목록에서 기존 Office Web Apps 서버 선택)를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="228d0-227">If you selected **Conferencing** on the **Select Features** page, on the **Select an Office Web Apps Server** page select **Associate pool with an Office Web Apps Server** and then click **New** (or select an existing Office Web Apps Server from the drop-down list).</span></span>

11. <span data-ttu-id="228d0-228">**새 Office Web Apps 서버 정의** 대화 상자에서 office web APPS 서버 **Fqdn** 상자에 office ONLINE server 컴퓨터의 fqdn (정규화 된 도메인 이름)을 입력 합니다. 이렇게 하면 office Web Apps 서버 검색 URL이 **Office Web Apps server 검색 url** 상자에 자동으로 입력 됩니다.</span><span class="sxs-lookup"><span data-stu-id="228d0-228">In the **Define New Office Web Apps Server** dialog box, type the fully qualified domain name (FQDN) of your Office Web Apps Server computer in the **Office Web Apps Server FQDN** box; when you do this, your Office Web Apps Server discovery URL should automatically be entered into the **Office Web Apps Server discovery URL** box.</span></span>
    
    <span data-ttu-id="228d0-229">Office Web Apps 서버가 Lync Server 2013와 같은 네트워크 영역에 설치 되어 있는 경우 **외부 네트워크 (즉, 경계/인터넷)에 Office Web Apps 서버를 배포** 하는 옵션을 선택 하지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="228d0-229">If the Office Web Apps Server is installed on-premises and in the same network zone as Lync Server 2013 then the option **Office Web Apps Server is deployed in an external network (that is, perimeter/Internet)** should not be selected.</span></span>
    
    <span data-ttu-id="228d0-230">Office Web Apps 서버가 내부 방화벽 외부에 배포 된 경우 **Office Web Apps 서버를 외부 네트워크 (즉, 외곽/인터넷)에 배포**하는 옵션을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="228d0-230">If the Office Web Apps Server is deployed outside your internal firewall, then select the option **Office Web Apps Server is deployed in an external network (that is, perimeter/Internet)**.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="228d0-231">자세한 내용은 <A href="lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md">Office Web Apps 서버 및 Lync server 2013의 통합 구성을</A>참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="228d0-231">For details, see <A href="lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md">Configuring integration with Office Web Apps Server and Lync Server 2013</A>.</span></span>

    
    </div>

12. <span data-ttu-id="228d0-232">**보관 SQL 저장소 정의** 페이지에서 기존 인스턴스 또는 SQL Server를 선택 하거나, 데이터 보관에 연결 된 데이터를 저장할 새 인스턴스를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="228d0-232">On the **Define the Archiving SQL store** page, select an existing instance or SQL Server, or define a new instance to store the data associated with archiving data.</span></span>

13. <span data-ttu-id="228d0-233">**모니터링 SQL Store 정의** 페이지에서 기존 인스턴스 또는 SQL Server를 선택 하거나 모니터링 데이터와 관련 된 데이터를 저장할 새 인스턴스를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="228d0-233">On the **Define the Monitoring SQL store** page, select an existing instance or SQL Server, or define a new instance to store the data associated with monitoring data.</span></span>

14. <span data-ttu-id="228d0-234">**다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="228d0-234">Click **Next**.</span></span> <span data-ttu-id="228d0-235">**이 프런트 엔드 풀을 사용 하 여 서버 역할 연결** 페이지에서 다른 역할 서버를 정의한 경우 서버 역할을 구성할 수 있도록 별도의 역할 구성 마법사 페이지가 열립니다.</span><span class="sxs-lookup"><span data-stu-id="228d0-235">If you defined other role servers on the **Associate server roles with this Front End pool** page, separate role configuration wizard pages will open to let you configure the server roles.</span></span> <span data-ttu-id="228d0-236">자세한 내용은 다음을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="228d0-236">For details, see the following:</span></span>
    
    [<span data-ttu-id="228d0-237">Lync Server 2013에서 외부 사용자 액세스 배포</span><span class="sxs-lookup"><span data-stu-id="228d0-237">Deploying external user access in Lync Server 2013</span></span>](lync-server-2013-deploying-external-user-access.md)

15. <span data-ttu-id="228d0-238">구성 및 배포할 추가 서버 역할을 선택 하지 않은 경우 또는 추가 역할 서버의 구성을 완료 한 경우 **마침을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="228d0-238">If you did not select additional server roles to configure and deploy, or when you have finished the configuration of the additional role servers, click **Finish**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

