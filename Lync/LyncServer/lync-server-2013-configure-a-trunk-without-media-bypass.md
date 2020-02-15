---
title: 'Lync Server 2013: 미디어 바이패스 없이 트렁크 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure a trunk without media bypass
ms:assetid: 3422e93e-7bd2-4470-968c-dc38345b18ca
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425831(v=OCS.15)
ms:contentKeyID: 48183825
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bd810c64f546c907f0fd00d2dc2fea43e09fa1bf
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42028799"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-a-trunk-without-media-bypass-in-lync-server-2013"></a><span data-ttu-id="14223-102">Lync Server 2013에서 미디어 바이패스 없이 트렁크 구성</span><span class="sxs-lookup"><span data-stu-id="14223-102">Configure a trunk without media bypass in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="14223-103">_**마지막으로 수정 된 항목:** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="14223-103">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="14223-104">미디어 바이패스가 비활성화된 트렁크를 구성하려면 다음 단계를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="14223-104">If you want to configure a trunk with media bypass disabled, follow these steps.</span></span> <span data-ttu-id="14223-105">미디어 바이패스를 사용 하 여 트렁크를 구성 하려면 [Lync Server 2013에서 미디어 바이패스를 사용 하 여 트렁크 구성](lync-server-2013-configure-a-trunk-with-media-bypass.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="14223-105">If you want to configure a trunk with media bypass enabled, see [Configure a trunk with media bypass in Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md).</span></span>

<span data-ttu-id="14223-p102">트렁크 구성은 아래에 설명된 것처럼 해당 트렁크 구성에 할당된 트렁크에 적용되는 매개 변수 집합을 그룹화합니다. 특정 트렁크 구성의 범위를 전역으로(특정 사이트 또는 풀 구성을 포함하지 않는 모든 트렁크가 포함됨) 또는 사이트나 풀로 지정할 수 있습니다. 풀 수준 트렁크 구성은 특정 트렁크 구성의 범위를 단일 트렁크로 지정하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="14223-p102">A trunk configuration, as described below, groups a set of parameters that are applied to trunks assigned this trunk configuration. A particular trunk configuration can be scoped globally (to all trunks that do not have more specific site or pool configuration), or to a site, or to a pool. The pool-level trunk configuration is used to scope a specific trunk configuration to a single trunk.</span></span>

<span id="BKMK_ConfigTrunkGenericSteps"></span>

<div>

## <a name="to-configure-a-trunk-without-media-bypass"></a><span data-ttu-id="14223-109">미디어 바이패스를 사용하지 않는 트렁크를 구성하려면</span><span class="sxs-lookup"><span data-stu-id="14223-109">To configure a trunk without media bypass</span></span>

1.  <span data-ttu-id="14223-110">RTCUniversalServerAdmins 그룹의 구성원으로 또는 CsVoiceAdministrator, CsServerAdministrator 또는 CsAdministrator 역할의 구성원으로 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="14223-110">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="14223-111">자세한 내용은 [Lync Server 2013에서 설치 권한 위임을](lync-server-2013-delegate-setup-permissions.md)참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="14223-111">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="14223-112">브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="14223-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="14223-113">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="14223-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="14223-114">왼쪽 탐색 모음에서 **음성 라우팅**을 클릭한 다음 **트렁크 구성**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="14223-114">In the left navigation bar, click **Voice Routing**, and then click **Trunk Configuration**.</span></span>

4.  <span data-ttu-id="14223-115">**트렁크 구성** 페이지에서 다음 방법 중 하나를 사용하여 트렁크를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="14223-115">On the **Trunk Configuration** page, use one of the following methods to configure a trunk:</span></span>
    
      - <span data-ttu-id="14223-116">기존 트렁크(예: **전역** 트렁크)를 두 번 클릭하여 **트렁크 구성 편집** 대화 상자를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="14223-116">Double-click an existing trunk (for example, the **Global** trunk) to display the **Edit Trunk Configuration** dialog box.</span></span>
    
      - <span data-ttu-id="14223-117">**새로 만들기**를 클릭한 다음 새 트렁크 구성의 범위를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="14223-117">Click **New**, and then select a scope for the new trunk configuration:</span></span>
        
          - <span data-ttu-id="14223-118">**사이트 트렁크:** **사이트 선택** 에서이 트렁크 구성에 대 한 사이트를 선택 하 고 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="14223-118">**Site trunk:** Choose the site for this trunk configuration in **Select a Site** , and then click **OK**.</span></span> <span data-ttu-id="14223-119">트렁크 구성이 이미 만들어진 사이트는 **사이트 선택** 대화 상자에 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="14223-119">Note that if a trunk configuration has already been created for a site, the site does not appear in **Select a Site**.</span></span> <span data-ttu-id="14223-120">이 트렁크 구성은 사이트의 모든 트렁크에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="14223-120">This trunk configuration will be applied to all trunks in the site.</span></span>
        
          - <span data-ttu-id="14223-121">**풀 트렁크:** 이 트렁크 구성이 적용 되는 트렁크의 이름을 선택 하 고 **확인** **을 클릭** 합니다.</span><span class="sxs-lookup"><span data-stu-id="14223-121">**Pool trunk:** Choose the name of the trunk that this trunk configuration applies to in **Select a Service** and click **OK**.</span></span> <span data-ttu-id="14223-122">이 트렁크는 루트 트렁크 또는 토폴로지 작성기에 정의 된 추가 트렁크 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14223-122">This trunk can be the root trunk, or any additional trunks defined in Topology Builder.</span></span> <span data-ttu-id="14223-123">트렁크 구성이 이미 만들어진 특정 트렁크는 **서비스 선택** 대화 상자에 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="14223-123">Note that if a trunk configuration has already been created for a specific trunk, the trunk does not appear in **Select a Service**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="14223-124">트렁크 구성 범위는 선택한 후에 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="14223-124">After you select the scope of the trunk configuration, it cannot be changed.</span></span><BR><span data-ttu-id="14223-125"><STRONG>이름</STRONG> 필드는 트렁크 구성의 연결된 사이트 또는 서비스 이름으로 미리 채워지며 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="14223-125">The <STRONG>Name</STRONG> field is prepopulated with the name of the trunk configuration’s associated site or service and cannot be changed.</span></span>

    
    </div>

5.  <span data-ttu-id="14223-126">다음 **암호화 지원 수준** 옵션 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="14223-126">Select one of the following **Encryption support level** options:</span></span>
    
      - <span data-ttu-id="14223-127">**필수 사항:** Secure SRTP (실시간 전송 프로토콜) 암호화는 중재 서버와 게이트웨이 또는 PBX (private branch exchange) 간의 트래픽을 보호 하는 데 사용 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="14223-127">**Required:** Secure real-time transport protocol (SRTP) encryption must be used to help protect traffic between the Mediation Server and the gateway or private branch exchange (PBX).</span></span>
    
      - <span data-ttu-id="14223-128">**선택 사항:** 서비스 공급자 또는 장비 제조업체에서 지 원하는 경우 SRTP 암호화가 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="14223-128">**Optional:** SRTP encryption will be used if the service provider or equipment manufacturer supports it.</span></span>
    
      - <span data-ttu-id="14223-129">**지원 되지 않음:** SRTP 암호화는 서비스 공급자 또는 장비 제조업체에서 지원 하지 않으므로 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="14223-129">**Not Supported:** SRTP encryption is not supported by the service provider or equipment manufacturer and therefore will not be used.</span></span>

6.  <span data-ttu-id="14223-130">**미디어 바이패스 사용** 확인란의 선택이 취소되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="14223-130">Be sure that the **Enable media bypass** check box is cleared.</span></span>

7.  <span data-ttu-id="14223-p107">알려진 미디어 종료 지점(예: 미디어 종료 IP가 신호 종료 IP와 같은 공중 전화망(PSTN) 게이트웨이)이 있는 경우 **중앙 집중식 미디어 처리** 확인란을 선택합니다. 트렁크에 알려진 미디어 종료 지점이 없는 경우에는 이 확인란의 선택을 취소합니다.</span><span class="sxs-lookup"><span data-stu-id="14223-p107">Select the **Centralized media processing** check box if there is a well-known media termination point (for example, a public switched telephone network (PSTN) gateway where the media termination has the same IP as the signaling termination). Clear this check box if the trunk does not have a well-known media termination point.</span></span>

8.  <span data-ttu-id="14223-133">트렁크 피어가 중재 서버에서 받은 SIP를 수신 하는 것을 지원 하면 **게이트웨이를 참조로 보내기를 사용** 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="14223-133">If the trunk peer supports receiving SIP REFER requests from the Mediation Server, select the **Enable sending refer to the gateway** check box.</span></span>

9.  <span data-ttu-id="14223-p108">원하는 경우 트렁크 간 라우팅을 사용하도록 설정하려면 PSTN 사용 레코드를 이 트렁크 구성에 연결하고 구성합니다. 이 트렁크 구성에 연결되는 PSTN 사용은 Lync 끝점에서 시작되지 않은 트렁크를 통과하는 모든 수신 전화에 적용됩니다. 트렁크 구성에 연결된 PSTN 사용 레코드를 관리하려면 다음 방법 중 하나를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="14223-p108">(Optional) To enable inter-trunk routing, associate and configure PSTN usage records to this trunk configuration. The PSTN usages associated to this trunk configuration will be applied for all incoming calls through the trunk that is not originating from a Lync endpoint. To manage PSTN usage records associated to a trunk configuration, use one of the following methods:</span></span>
    
      - <span data-ttu-id="14223-137">Enterprise Voice 배포에서 사용할 수 있는 모든 PSTN 사용 레코드 목록에서 하나 이상의 레코드를 선택 하려면 **선택을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="14223-137">To select one or more records from a list of all PSTN usage records available in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="14223-138">이 트렁크 구성과 연결할 레코드를 강조 표시하고 **확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="14223-138">Highlight the records you want to associate with this trunk configuration and then click **OK**.</span></span>
    
      - <span data-ttu-id="14223-139">이 트렁크 구성에서 PSTN 사용 레코드를 제거하려면 레코드를 강조 표시하고 **제거**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="14223-139">To remove a PSTN usage record from this trunk configuration, select the record and click **Remove**.</span></span>
    
      - <span data-ttu-id="14223-140">새 PSTN 사용 레코드를 정의하고 이 트렁크 구성과 연결하려면 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="14223-140">To define a new PSTN usage record and associate it with this trunk configuration, do the following:</span></span>
        
        1.  <span data-ttu-id="14223-141">**새로 만들기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="14223-141">Click **New**.</span></span>
        
        2.  <span data-ttu-id="14223-142">**이름** 필드에서 레코드를 설명하는 고유한 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="14223-142">In the **Name** field, specify a descriptive name for the record that is unique.</span></span>
            
            <div>
            

            > [!NOTE]  
            > <span data-ttu-id="14223-143">PSTN 사용 레코드 이름은 Enterprise Voice 배포 내에서 고유 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="14223-143">The PSTN usage record name must be unique within the Enterprise Voice deployment.</span></span> <span data-ttu-id="14223-144">레코드를 저장한 후에는 <STRONG>이름</STRONG> 필드를 편집할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="14223-144">After the record is saved, the <STRONG>Name</STRONG> field cannot be edited.</span></span>

            
            </div>
        
        3.  <span data-ttu-id="14223-145">다음 방법 중 하나를 사용하여 이 PSTN 사용 레코드에 대한 경로를 구성하고 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="14223-145">Use one of the following methods to associate and configure routes for this PSTN usage record:</span></span>
            
              - <span data-ttu-id="14223-146">Enterprise Voice 배포에서 사용 가능한 모든 경로 목록에서 하나 이상의 경로를 선택 하려면 **선택을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="14223-146">To select one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="14223-147">이 PSTN 사용 레코드와 연결할 경로를 강조 표시한 다음 **확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="14223-147">Highlight the routes you want to associate with this PSTN usage record, and click **OK**.</span></span>
            
              - <span data-ttu-id="14223-148">PSTN 사용 레코드에서 경로를 제거하려면 경로를 선택하고 **제거**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="14223-148">To remove a route from the PSTN usage record, select the route, and click **Remove**.</span></span>
            
              - <span data-ttu-id="14223-149">새 경로를 정의하고 이 PSTN 사용 레코드와 연결하려면 **새로 만들기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="14223-149">To define a new route and associate it to this PSTN usage record, click **New**.</span></span> <span data-ttu-id="14223-150">자세한 내용은 [Lync Server 2013에서 음성 경로 만들기](lync-server-2013-create-a-voice-route.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="14223-150">For details, see [Create a voice route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span></span>
            
              - <span data-ttu-id="14223-151">이 PSTN 사용 레코드에 연결된 경로를 편집하려면 경로를 선택하고 **자세한 정보 표시**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="14223-151">To edit a route that is associated with this PSTN usage record, select the route, and click **Show details**.</span></span> <span data-ttu-id="14223-152">자세한 내용은 [Lync Server 2013에서 음성 경로 수정을](lync-server-2013-modify-a-voice-route.md)참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="14223-152">For details, see [Modify a voice route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span></span>
        
        4.  <span data-ttu-id="14223-153">**확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="14223-153">Click **OK**.</span></span>
    
      - <span data-ttu-id="14223-154">이 트렁크 구성에 이미 연결된 PSTN 사용 레코드를 편집하려면 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="14223-154">To edit a PSTN usage record that is already associated with this trunk configuration, do the following:</span></span>
        
        1.  <span data-ttu-id="14223-155">편집할 PSTN 사용 레코드를 선택하고 **자세한 정보 표시**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="14223-155">Select the PSTN usage record you want to edit, and click **Show details**.</span></span>
        
        2.  <span data-ttu-id="14223-156">다음 방법 중 하나를 사용하여 이 PSTN 사용 레코드에 대한 경로를 구성하고 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="14223-156">Use one of the following methods to associate and configure routes for this PSTN usage record:</span></span>
            
              - <span data-ttu-id="14223-157">Enterprise Voice 배포에서 사용 가능한 모든 경로 목록에서 하나 이상의 경로를 선택 하려면 **선택을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="14223-157">To select one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="14223-158">이 PSTN 사용 레코드와 연결할 경로를 강조 표시한 다음 **확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="14223-158">Highlight the routes you want to associate with this PSTN usage record, and click **OK**.</span></span>
            
              - <span data-ttu-id="14223-159">PSTN 사용 레코드에서 경로를 제거하려면 경로를 선택하고 **제거**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="14223-159">To remove a route from the PSTN usage record, select the route, and click **Remove**.</span></span>
            
              - <span data-ttu-id="14223-160">새 경로를 정의하고 이 PSTN 사용 레코드와 연결하려면 **새로 만들기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="14223-160">To define a new route and associate it to this PSTN usage record, click **New**.</span></span> <span data-ttu-id="14223-161">자세한 내용은 [Lync Server 2013에서 음성 경로 만들기](lync-server-2013-create-a-voice-route.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="14223-161">For details, see [Create a voice route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span></span>
            
              - <span data-ttu-id="14223-162">이 PSTN 사용 레코드에 연결된 경로를 편집하려면 경로를 선택하고 **자세한 정보 표시**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="14223-162">To edit a route that is associated with this PSTN usage record, select the route, and click **Show details**.</span></span> <span data-ttu-id="14223-163">자세한 내용은 [Lync Server 2013에서 음성 경로 수정을](lync-server-2013-modify-a-voice-route.md)참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="14223-163">For details, see [Modify a voice route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span></span>
        
        3.  <span data-ttu-id="14223-164">**확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="14223-164">Click **OK**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="14223-165">구성 중인 트렁크에 연결 된 중재 서버 피어에 따라 PSTN 사용 레코드를 연결 하는 것이 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="14223-165">It important to associate PSTN usage records according to the Mediation Server peer that is associated to the trunk being configured.</span></span> <span data-ttu-id="14223-166">중재 서버 피어가 PSTN 게이트웨이 또는 SBC (Session Border Controller) 인 경우 트렁크 구성이 pstn 대상 또는 Lync를 통해 연결 된 다른 다운스트림 시스템으로 경로 하는 PSTN 사용 레코드에 연결 되어 있지 않는 것이 좋습니다. 서버.</span><span class="sxs-lookup"><span data-stu-id="14223-166">If the Mediation Server peer is a PSTN gateway or a Session Border Controller (SBC), it is strongly recommended that the trunk configuration is not associated to a PSTN usage record that routes to a PSTN destination or any other downstream systems connected via Lync Server.</span></span>

    
    </div>

10. <span data-ttu-id="14223-p118">최적의 성능을 유지하도록 PSTN 사용 레코드를 정렬합니다. 목록에서 레코드의 위치를 변경하려면 PSTN 사용 레코드를 선택하고 위쪽 또는 아래쪽 화살표를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="14223-p118">Arrange the PSTN usage records for optimum performance. To change a record’s position in the list, select the PSTN usage record, and click the up or down arrows.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="14223-169">PSTN 사용 레코드가 트렁크 구성에서 나열되는 순서가 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="14223-169">The order in which PSTN usage records are listed in the trunk configuration is significant.</span></span> <span data-ttu-id="14223-170">Lync Server가 목록을 위에서 아래로 트래버스 합니다.</span><span class="sxs-lookup"><span data-stu-id="14223-170">Lync Server traverses the list from top to down.</span></span>

    
    </div>

11. <span data-ttu-id="14223-171">NAT 또는 방화벽 뒤의 클라이언트와 래치를 지원하는 SBC에 대해 미디어 바이패스를 사용하도록 설정하려면 **RTP 래치 사용**을 선택해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="14223-171">**Enable RTP Latching** should be selected to enable bypass media for clients behind a NAT or firewall and an SBC that supports latching.</span></span>

12. <span data-ttu-id="14223-172">중재 서버의 게이트웨이 피어로 통화 기록 정보를 보낼 수 있도록 하려면 **착신 전환 사용 내역** 을 선택 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="14223-172">**Enable forward call history** should be selected to enable sending of call history information to the gateway peer of the Mediation Server.</span></span>

13. <span data-ttu-id="14223-173">No **Forward 사용-어설션된-설정 됨-Identity data** 를 선택 하 여 중재 서버 쪽 및 게이트웨이 쪽 간에 전달 될 수 있도록, 또는이 위치에 있는 경우에는 반대로 보낸 사람 정보를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="14223-173">**Enable forward P-Asserted-Identity data** should be selected to enable PAI call originator information to be forwarded between the Mediation Server side and gateway side (and vice versa), when present.</span></span>

14. <span data-ttu-id="14223-174">빠른 장애 조치(failover)를 사용하도록 설정하려면 **아웃바운드 라우팅 장애 조치(failover) 타이머 사용**을 선택해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="14223-174">**Enable outbound routing failover timer** should be selected to enable fast failover.</span></span> <span data-ttu-id="14223-175">이 트렁크와 연결된 게이트웨이는 아웃바운드 통화를 처리하는 10초 이내에 알림을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14223-175">The gateway associated with this trunk can give notification within 10 seconds that it is processing an outbound call.</span></span> <span data-ttu-id="14223-176">중재 서버에서이 알림을 받지 못하면 다른 트렁크로 전환 하는 것이 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="14223-176">Rerouting to another trunk will occur if this notification is not received by the Mediation Server.</span></span> <span data-ttu-id="14223-177">대기 시간으로 인해 응답 시간이 지연되거나 게이트웨이가 응답하는 데 10초보다 오래 걸리는 네트워크에서는 빠른 장애 조치(failover)를 사용하지 않도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="14223-177">On networks where latency may delay the response time or the gateway takes longer than 10 seconds to respond, the fast failover should be disabled.</span></span>

15. <span data-ttu-id="14223-178">원하는 경우 트렁크에 대해 **호출 번호 변환 규칙**을 연결 및 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="14223-178">(Optional) Associate and configure **calling number translation rules** for the trunk.</span></span> <span data-ttu-id="14223-179">이러한 변환 규칙은 아웃바운드 통화의 호출 번호에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="14223-179">These translation rules apply to the calling number for outbound calls</span></span>
    
      - <span data-ttu-id="14223-180">Enterprise Voice 배포에서 사용할 수 있는 모든 변환 규칙 목록에서 하나 이상의 규칙을 선택 하려면 **선택을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="14223-180">To choose one or more rules from a list of all translation rules that are available in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="14223-181">**변환 규칙 선택**에서 트렁크와 연결할 규칙을 클릭한 다음 **확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="14223-181">In **Select Translation Rules**, click the rules that you want to associate with the trunk, and then click **OK**.</span></span>
    
      - <span data-ttu-id="14223-182">새 변환 규칙을 정의하고 트렁크와 연결하려면 **새로 만들기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="14223-182">To define a new translation rule and associate it with the trunk, click **New**.</span></span> <span data-ttu-id="14223-183">새 규칙을 정의 하는 방법에 대 한 자세한 내용은 배포 설명서의 [Lync Server 2013에서 변환 규칙 정의](lync-server-2013-defining-translation-rules.md) 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="14223-183">For details about defining a new rule, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md) in the Deployment documentation.</span></span>
    
      - <span data-ttu-id="14223-184">트렁크와 이미 연결된 변환 규칙을 편집하려면 규칙 이름을 클릭한 다음 **자세한 정보 표시**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="14223-184">To edit a translation rule that is already associated with the trunk, click the rule name, and then click **Show details**.</span></span> <span data-ttu-id="14223-185">자세한 내용은 배포 설명서에서 [Lync Server 2013의 변환 규칙 정의](lync-server-2013-defining-translation-rules.md) 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="14223-185">For details, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md) in the Deployment documentation.</span></span>
    
      - <span data-ttu-id="14223-186">기존 변환 규칙을 복사하여 새 규칙을 정의하는 시작 시점으로 사용하려면 규칙 이름을 클릭하고 **복사**를 클릭한 다음 **붙여넣기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="14223-186">To copy an existing translation rule to use as a starting point for defining a new rule, click the rule name and click **Copy**, and then click **Paste**.</span></span> <span data-ttu-id="14223-187">자세한 내용은 [Lync Server 2013에서 변환 규칙 정의](lync-server-2013-defining-translation-rules.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="14223-187">For details, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md).</span></span>
    
      - <span data-ttu-id="14223-188">트렁크에서 변환 규칙을 제거하려면 규칙 이름을 강조 표시하고 **제거**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="14223-188">To remove a translation rule from the trunk, highlight the rule name and click **Remove**.</span></span>
    
    <div>
    
    <table>
    <thead>
    <tr class="header">
    <th><img src="images/Gg398321.security(OCS.15).gif" title="보안이" alt="security" /><span data-ttu-id="14223-190">보안 메모:</span><span class="sxs-lookup"><span data-stu-id="14223-190">Security Note:</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><span data-ttu-id="14223-191">연결된 트렁크 피어에서 변환 규칙을 구성한 경우에는 두 규칙이 충돌할 수 있으므로 변환 규칙을 트렁크와 연결하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="14223-191">Do not associate translation rules with a trunk if you have configured translation rules on the associated trunk peer, because the two rules might conflict.</span></span></td>
    </tr>
    </tbody>
    </table>
    
    </div>

16. <span data-ttu-id="14223-p126">원하는 경우 트렁크에 대해 **호출된 번호 변환 규칙**을 연결 및 구성합니다. 변환 규칙은 아웃바운드 통화의 호출된 번호에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="14223-p126">(Optional) Associate and configure **called number translation rules** for the trunk. The translation rules apply to the called number in an outbound call.</span></span>
    
      - <span data-ttu-id="14223-194">Enterprise Voice 배포에서 사용할 수 있는 모든 변환 규칙 목록에서 하나 이상의 규칙을 선택 하려면 **선택을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="14223-194">To choose one or more rules from a list of all translation rules that are available in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="14223-195">**변환 규칙 선택**에서 트렁크와 연결할 규칙을 클릭한 다음 **확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="14223-195">In **Select Translation Rules**, click the rules that you want to associate with the trunk, and then click **OK**.</span></span>
    
      - <span data-ttu-id="14223-196">새 변환 규칙을 정의하고 트렁크와 연결하려면 **새로 만들기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="14223-196">To define a new translation rule and associate it with the trunk, click **New**.</span></span> <span data-ttu-id="14223-197">새 규칙을 정의 하는 방법에 대 한 자세한 내용은 배포 설명서의 [Lync Server 2013에서 변환 규칙 정의](lync-server-2013-defining-translation-rules.md) 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="14223-197">For details about defining a new rule, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md) in the Deployment documentation.</span></span>
    
      - <span data-ttu-id="14223-198">트렁크와 이미 연결된 변환 규칙을 편집하려면 규칙 이름을 클릭한 다음 **자세한 정보 표시**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="14223-198">To edit a translation rule that is already associated with the trunk, click the rule name, and then click **Show details**.</span></span> <span data-ttu-id="14223-199">자세한 내용은 배포 설명서에서 [Lync Server 2013의 변환 규칙 정의](lync-server-2013-defining-translation-rules.md) 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="14223-199">For details, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md) in the Deployment documentation.</span></span>
    
      - <span data-ttu-id="14223-200">기존 변환 규칙을 복사하여 새 규칙을 정의하는 시작 시점으로 사용하려면 규칙 이름을 클릭하고 **복사**를 클릭한 다음 **붙여넣기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="14223-200">To copy an existing translation rule to use as a starting point for defining a new rule, click the rule name and click **Copy**, and then click **Paste**.</span></span> <span data-ttu-id="14223-201">자세한 내용은 [Lync Server 2013에서 변환 규칙 정의](lync-server-2013-defining-translation-rules.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="14223-201">For details, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md).</span></span>
    
      - <span data-ttu-id="14223-202">트렁크에서 변환 규칙을 제거하려면 규칙 이름을 강조 표시하고 **제거**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="14223-202">To remove a translation rule from the trunk, highlight the rule name and click **Remove**.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="14223-203">연결된 트렁크 피어에서 변환 규칙을 구성한 경우에는 두 규칙이 충돌할 수 있으므로 변환 규칙을 트렁크와 연결하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="14223-203">Do not associate translation rules with a trunk if you have configured translation rules on the associated trunk peer, because the two rules might conflict.</span></span>

    
    </div>

17. <span data-ttu-id="14223-204">트렁크의 변환 규칙이 올바른 순서로 정렬 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="14223-204">Make sure that the trunk’s translation rules are arranged in the correct order.</span></span> <span data-ttu-id="14223-205">목록에서 규칙의 위치를 변경하려면 규칙 이름을 강조 표시하고 위쪽 또는 아래쪽 화살표를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="14223-205">To change a rule’s position in the list, highlight the rule name, and then click the up or down arrow.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="14223-206">Lync Server는 번역 규칙 목록을 위에서 아래로 이동 하 고 전화 건 번호와 일치 하는 첫 번째 규칙을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="14223-206">Lync Server traverses the translation rule list from the top down and uses the first rule that matches the dialed number.</span></span> <span data-ttu-id="14223-207">전화를 건 번호가 둘 이상의 변환 규칙과 일치할 수 있도록 트렁크를 구성하는 경우에는 제약이 많은 규칙이 제약이 적은 규칙보다 위에 정렬되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="14223-207">If you configure a trunk so that a dialed number can match more than one translation rule, be sure that the more restrictive rules are sorted above the less restrictive rules.</span></span> <span data-ttu-id="14223-208">예를 들어 모든 11자리 숫자와 일치하는 변환 규칙과 +1425로 시작하는 11자리 숫자와만 일치하는 변환 규칙이 있는 경우 모든 11자리 숫자와 일치하는 규칙이 보다 제한적인 규칙 아래에 정렬되어야 합니다<EM>.</EM></span><span class="sxs-lookup"><span data-stu-id="14223-208">For example, if you have included a translation rule that matches any 11-digit number and a translation rule that matches only 11-digit numbers that start with +1425, be sure that the rule that matches any 11-digit number is sorted <EM>below</EM> the more restrictive rule.</span></span>

    
    </div>

18. <span data-ttu-id="14223-209">트렁크 구성을 마쳤으면 **확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="14223-209">When you are finished configuring the trunk, click **OK**.</span></span>

19. <span data-ttu-id="14223-210">**트렁크 구성** 페이지에서 **커밋**을 클릭하고 **모두 커밋**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="14223-210">On the **Trunk Configuration** page, click **Commit**, and then click **Commit all**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="14223-211">트렁크 구성을 만들거나 수정할 때는 항상 <STRONG>모두 커밋</STRONG> 명령을 실행하여 구성 변경 내용을 게시해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="14223-211">Whenever you create or modify a trunk configuration, you must run the <STRONG>Commit all</STRONG> command to publish the configuration change.</span></span> <span data-ttu-id="14223-212">자세한 내용은 작업 설명서의 <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Lync Server 2013에서 음성 라우팅 구성에 보류 중인 변경 내용 게시</A> 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="14223-212">For details, see <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish pending changes to the voice routing configuration in Lync Server 2013</A> in the Operations documentation.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="14223-213">참고 항목</span><span class="sxs-lookup"><span data-stu-id="14223-213">See Also</span></span>


[<span data-ttu-id="14223-214">Lync Server 2013의 미디어 바이패스로 트렁크 구성</span><span class="sxs-lookup"><span data-stu-id="14223-214">Configure a trunk with media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-with-media-bypass.md)  


[<span data-ttu-id="14223-215">Lync Server 2013에서 변환 규칙 정의</span><span class="sxs-lookup"><span data-stu-id="14223-215">Defining translation rules in Lync Server 2013</span></span>](lync-server-2013-defining-translation-rules.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

