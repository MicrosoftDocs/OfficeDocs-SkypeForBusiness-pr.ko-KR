---
title: 중재 서버 구성
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Configure Mediation Server
ms:assetid: 583236fd-33cd-4045-81df-baa58ed07779
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204913(v=OCS.15)
ms:contentKeyID: 48184207
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0705d51d321aba21a8bad7ba0e26351bf26bc5f0
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42180871"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-mediation-server"></a><span data-ttu-id="81203-102">중재 서버 구성</span><span class="sxs-lookup"><span data-stu-id="81203-102">Configure Mediation Server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="81203-103">_**마지막으로 수정 된 항목:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="81203-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="81203-104">이 절차에서는 레거시 Office Communications Server 2007 R2 중재 서버가 아닌 Lync server 2013 중재 서버를 사용 하도록 Lync Server 2013 풀을 구성 하는 단계를 자세히 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="81203-104">This procedure details the steps to configure the Lync Server 2013 pool to use the Lync Server 2013 Mediation Server, instead of the legacy Office Communications Server 2007 R2 Mediation Server.</span></span>

<span data-ttu-id="81203-p101">서버 역할을 추가하거나 제거할 때 토폴로지를 성공적으로 게시하거나 사용 또는 사용하지 않도록 설정하려면 RTCUniversalServerAdmins 및 Domain Admins 그룹 구성원인 사용자로 로그인해야 합니다. 또한 서버 역할을 추가하는 데 적절한 관리자 권한 및 사용 권한을 위임할 수 있습니다. 자세한 내용은 Standard Edition 서버 또는 Enterprise Edition 서버 배포 설명서에서 설정 권한 위임을 참조하십시오. 기타 구성을 변경하려는 경우에는 RTCUniversalServerAdmins 그룹 구성원 자격만 있으면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="81203-p101">To successfully publish, enable, or disable a topology when adding or removing a server role, you should be logged in as a user who is a member of the RTCUniversalServerAdmins and Domain Admins groups. It is also possible to delegate the proper administrator rights and permissions for adding server roles. For details, see Delegate Setup Permissions in the Standard Edition server or Enterprise Edition server Deployment documentation. For other configuration changes, only membership in the RTCUniversalServerAdmins group is required.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="81203-109">Lync Server 2013에서 작동 하는 정규화 된 PSTN 게이트웨이, IP Pbx 및 SIP 트렁크 서비스를 찾는 방법에 대 한 최신 정보는에서 <A href="https://go.microsoft.com/fwlink/p/?linkid=206015">https://go.microsoft.com/fwlink/p/?linkId=206015</A>"Microsoft 통합 커뮤니케이션 오픈 상호 운용성 프로그램"을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="81203-109">For the latest information on finding qualified PSTN gateways, IP-PBXs, and SIP trunking services that work with Lync Server 2013, see "Microsoft Unified Communications Open Interoperability Program" at <A href="https://go.microsoft.com/fwlink/p/?linkid=206015">https://go.microsoft.com/fwlink/p/?linkId=206015</A>.</span></span>



</div>

<div>

## <a name="to-configure-mediation-server-using-topology-builder"></a><span data-ttu-id="81203-110">토폴로지 작성기를 사용하여 중재 서버를 구성하려면</span><span class="sxs-lookup"><span data-stu-id="81203-110">To configure Mediation Server Using Topology Builder</span></span>

1.  <span data-ttu-id="81203-111">토폴로지 작성기에서 기존 토폴로지를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="81203-111">Open an existing topology from Topology Builder.</span></span>

2.  <span data-ttu-id="81203-112">왼쪽 창에서 **PSTN 게이트웨이**로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="81203-112">In the left pane, navigate to **PSTN gateways**.</span></span>

3.  <span data-ttu-id="81203-113">**PSTN 게이트웨이**를 마우스 오른쪽 단추로 클릭한 다음 **새 IP/PSTN 게이트웨이**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="81203-113">Right-click **PSTN gateways**, and then click **New IP/PSTN Gateway**.</span></span>

4.  <span data-ttu-id="81203-114">**새 IP/PSTN 게이트웨이 정의** 페이지에서 다음 정보를 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="81203-114">Complete the **Define New IP/PSTN Gateway** page with the following information:</span></span>
    
      - <span data-ttu-id="81203-p102">게이트웨이의 FQDN 또는 IP 주소를 입력합니다. 게이트웨이에서 TLS 프로토콜을 사용하는 경우 게이트웨이의 FQDN이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="81203-p102">Enter the gateway FQDN or IP address. The FQDN of the gateway is required if the gateway uses the TLS protocol.</span></span>
    
      - <span data-ttu-id="81203-117">**IP/PSTN 게이트웨이용 수신 대기 포트**의 기본값을 사용하거나 값이 수정된 경우 새 수신 대기 포트를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="81203-117">Accept the default value of the **Listening port for IP/PSTN gateway** or enter the new listening port if it was modified.</span></span>
    
      - <span data-ttu-id="81203-118">**SIP 전송 프로토콜**을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="81203-118">Set the **Sip Transport Protocol**.</span></span>

5.  <span data-ttu-id="81203-119">왼쪽 창에서 **Enterprise Edition 프런트 엔드 풀** 또는 **Standard Edition 서버**로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="81203-119">In the left pane, navigate to the **Enterprise Edition Front End pool** or the **Standard Edition Server**.</span></span>

6.  <span data-ttu-id="81203-120">풀을 마우스 오른쪽 단추로 클릭한 다음 **속성 편집**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="81203-120">Right-click the pool, and then click **Edit Properties**.</span></span>

7.  <span data-ttu-id="81203-121">**중재 서버**에서 **수신 대기 포트**를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="81203-121">Under **Mediation Server**, set the **Listening ports**.</span></span>

8.  <span data-ttu-id="81203-122">그런 다음 새로 만든 PSTN 게이트웨이를 선택하고 **추가**를 클릭하여 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="81203-122">Next, associate the newly created PSTN gateway by selecting it and clicking **Add**.</span></span>

9.  <span data-ttu-id="81203-123">**토폴로지 작성기**에서 맨 위에 있는 **Lync Server** 노드를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="81203-123">In **Topology Builder**, select the top-most node **Lync Server**.</span></span>

10. <span data-ttu-id="81203-124">**동작** 메뉴에서 **토폴로지 게시**를 선택한 후 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="81203-124">From the **Action** menu, select **Publish Topology** and then click **Next**.</span></span>

11. <span data-ttu-id="81203-125">**게시 마법사**가 완료되면 **마침**을 클릭하여 마법사를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="81203-125">When the **Publishing wizard** completes, click **Finish** to close the wizard.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="81203-126">음성 경로가 올바른 중재 서버를 가리키는지 확인 하려면 다음 항목을 완료 하 여 <A href="change-voice-routes-to-use-the-new-lync-server-2013-mediation-server.md">새 Lync server 2013 중재 서버를 사용 하도록 음성 경로를 변경</A> 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="81203-126">It is important that you complete the next topic, <A href="change-voice-routes-to-use-the-new-lync-server-2013-mediation-server.md">Change voice routes to use the new Lync Server 2013 Mediation Server</A> to ensure that the voice routes are pointing to the correct Mediation Server.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

