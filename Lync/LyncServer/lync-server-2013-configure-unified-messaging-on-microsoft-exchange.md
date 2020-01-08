---
title: 'Lync Server 2013: Microsoft Exchange에서 통합 메시징 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure Unified Messaging on Microsoft Exchange
ms:assetid: 07547968-c59b-4dde-ace4-9fd286933759
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398129(v=OCS.15)
ms:contentKeyID: 48183311
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c4a97a97d96f91b0433c65b7eb3e352dcf47c7d5
ms.sourcegitcommit: 30ed4457d7004ba732372fee11a6f0b1baf48e05
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/08/2020
ms.locfileid: "40979337"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-unified-messaging-on-microsoft-exchange-for-lync-server-2013"></a><span data-ttu-id="a4b6e-102">Lync Server 2013 용 Microsoft Exchange에서 통합 메시징 구성</span><span class="sxs-lookup"><span data-stu-id="a4b6e-102">Configure Unified Messaging on Microsoft Exchange for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a4b6e-103">_**마지막으로 수정한 주제:** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="a4b6e-103">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="a4b6e-104">이 항목에서는 Enterprise Voice에서 사용할 수 있도록 Microsoft Exchange Server에서 Exchange UM (통합 메시징)를 구성 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4b6e-104">This topic describes how to configure Exchange Unified Messaging (UM) on a Microsoft Exchange Server for use with Enterprise Voice.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a4b6e-105">이 항목의 cmdlet 예제는 exchange 2007 버전의 Exchange 관리 셸에 대 한 구문을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4b6e-105">The cmdlet examples in this topic provide syntax for the Exchange 2007 version of Exchange Management Shell.</span></span> <span data-ttu-id="a4b6e-106">Exchange 2010 또는 Exchange 2013을 실행 중인 경우에는 해당 설명서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a4b6e-106">If you are running Exchange 2010 or Exchange 2013, see the appropriate documentation as referenced.</span></span>



</div>

<div>

## <a name="to-configure-a-server-running-exchange-server-um"></a><span data-ttu-id="a4b6e-107">Exchange Server UM을 실행 하는 서버를 구성 하려면</span><span class="sxs-lookup"><span data-stu-id="a4b6e-107">To configure a server running Exchange Server UM</span></span>

1.  <span data-ttu-id="a4b6e-108">각 엔터프라이즈 음성 위치 프로필에 대 한 SIP (UM 세션 초기화 프로토콜)의 URI (Uniform Resource Identifier) 다이얼 플랜을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a4b6e-108">Create a UM Session Initiation Protocol (SIP) Uniform Resource Identifier (URI) dial plan for each of your Enterprise Voice location profiles.</span></span> <span data-ttu-id="a4b6e-109">Exchange 관리 콘솔을 사용 하도록 선택한 경우 보안 설정 **(기본 설정)** 을 사용 하 여 새 다이얼 플랜을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a4b6e-109">If you choose to use the Exchange Management Console, create a new dial plan with the security setting **Secured (preferred)**.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="a4b6e-110">보안 설정 값을 <STRONG>sip</STRONG> 트래픽 전용으로 암호화를 사용 하도록 설정 하는 경우, 앞에서 권장 하는 것 처럼 프런트 엔드 풀에 암호화가 필요 하도록 구성 된 경우에는이 보안 설정이 충분 하지 않으므로,이는 풀에 SIP 및 RTP 트래픽 모두에 대 한 암호화가 필요 하다는 것을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4b6e-110">If you set your security setting value to <STRONG>SIP Secured</STRONG> to require encryption for SIP traffic only, as previously recommended, note that this security setting on a dial plan is insufficient if the Front End pool is configured to require encryption, which means the pool requires encryption for both SIP and RTP traffic.</span></span> <span data-ttu-id="a4b6e-111">다이얼 플랜 및 풀 보안 설정이 호환 되지 않으면 프런트 엔드 풀에서 Exchange UM에 대 한 모든 호출이 실패 하 고 "호환 되지 않는 보안 설정"이 있음을 나타내는 오류가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4b6e-111">When the dial plan and pool security settings are not compatible, all calls to Exchange UM from the Front End pool will fail, resulting in an error indicating that you have an "Incompatible security setting."</span></span>

    
    </div>
    
    <span data-ttu-id="a4b6e-112">Exchange 관리 셸을 사용 하는 경우 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4b6e-112">If you use the Exchange Management Shell, type:</span></span>
    ```powershell
     New-UMDialPlan -Name <dial plan name> -UriType "SipName" -VoipSecurity <SIPSecured|Unsecured|Secured> -NumberOfDigitsInExtension <number of digits> -AccessTelephoneNumbers <access number in E.164 format>
    ```
    <span data-ttu-id="a4b6e-113">자세한 내용은 다음을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a4b6e-113">For details, see:</span></span>
    
      - <span data-ttu-id="a4b6e-114">Office Communications Server 2007의 경우에는 "통합 메시징 SIP URI 다이얼 플랜을 만드는 방법" [http://go.microsoft.com/fwlink/p/?LinkId=268632](http://go.microsoft.com/fwlink/p/?linkid=268632) 및 "새 umdialplan: Exchange 2007 도움말"을 참조 하세요 [http://go.microsoft.com/fwlink/p/?LinkId=268666](http://go.microsoft.com/fwlink/p/?linkid=268666).</span><span class="sxs-lookup"><span data-stu-id="a4b6e-114">For Office Communications Server 2007, see "How to Create a Unified Messaging SIP URI Dial Plan" at [http://go.microsoft.com/fwlink/p/?LinkId=268632](http://go.microsoft.com/fwlink/p/?linkid=268632) and "New-UMDialplan: Exchange 2007 Help" at [http://go.microsoft.com/fwlink/p/?LinkId=268666](http://go.microsoft.com/fwlink/p/?linkid=268666).</span></span>
    
      - <span data-ttu-id="a4b6e-115">Exchange 2010의 경우에는 "UM 다이얼 플랜 만들기" [http://go.microsoft.com/fwlink/p/?LinkId=268674](http://go.microsoft.com/fwlink/p/?linkid=268674) 및 "새 umdialplan 플랜: Exchange 2010 도움말"을 참조 [http://go.microsoft.com/fwlink/p/?LinkId=268680](http://go.microsoft.com/fwlink/p/?linkid=268680)하세요.</span><span class="sxs-lookup"><span data-stu-id="a4b6e-115">For Exchange 2010, see "Create a UM Dial Plan" at [http://go.microsoft.com/fwlink/p/?LinkId=268674](http://go.microsoft.com/fwlink/p/?linkid=268674) and "New-UMDialplan: Exchange 2010 Help" at [http://go.microsoft.com/fwlink/p/?LinkId=268680](http://go.microsoft.com/fwlink/p/?linkid=268680).</span></span>
    
      - <span data-ttu-id="a4b6e-116">Exchange 2013는에서 [http://go.microsoft.com/fwlink/p/?LinkID=266579](http://go.microsoft.com/fwlink/p/?linkid=266579)"통합 메시징"을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a4b6e-116">For Exchange 2013, see "Unified Messaging" at [http://go.microsoft.com/fwlink/p/?LinkID=266579](http://go.microsoft.com/fwlink/p/?linkid=266579).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a4b6e-117"><STRONG>SIPSecured</STRONG> 의 보안 수준을 선택 하는지 여부는 보안 실시간 전송 프로토콜 (SRTP)이 미디어 암호화에 대해 활성화 되었는지 여부에 <STRONG>따라 달라 집니다</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="a4b6e-117">Whether you select a security level of <STRONG>SIPSecured</STRONG> or <STRONG>Secured</STRONG> depends on whether secure real-time transport protocol (SRTP) is activated or deactivated for media encryption.</span></span> <span data-ttu-id="a4b6e-118">Lync Server 2010에서 Exchange UM과 통합 하는 경우이는 Lync Server 미디어 구성의 암호화 수준과 일치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4b6e-118">For the Lync Server 2010 integration with Exchange UM, this should correspond to the encryption level in the Lync Server media configuration.</span></span> <span data-ttu-id="a4b6e-119">Lync Server 미디어 구성은 <STRONG>CsMediaConfiguration</STRONG> cmdlet을 실행 하 여 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4b6e-119">The Lync Server media configuration can be viewed by running the <STRONG>Get-CsMediaConfiguration</STRONG> cmdlet.</span></span> <span data-ttu-id="a4b6e-120">자세한 내용은 Lync Server 관리 셸 설명서의 Get-help CsMediaConfiguration을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a4b6e-120">For details, see Get-CsMediaConfiguration in the Lync Server Management Shell documentation.</span></span><BR><span data-ttu-id="a4b6e-121">적절 한 VoIP 보안 설정을 선택 하는 방법에 대 한 자세한 내용은 온 <A href="lync-server-2013-deployment-process-for-integrating-on-premises-unified-messaging.md">-프레미스 통합 메시징 및 Lync Server 2013 통합에 대 한 배포 프로세스</A>를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a4b6e-121">For details about selecting the appropriate VoIP Security setting, see <A href="lync-server-2013-deployment-process-for-integrating-on-premises-unified-messaging.md">Deployment process for integrating on-premises Unified Messaging and Lync Server 2013</A>.</span></span>

    
    </div>

2.  <span data-ttu-id="a4b6e-122">다음 cmdlet을 실행 하 여 각 UM 다이얼 플랜에 대 한 FQDN (정규화 된 도메인 이름)을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="a4b6e-122">Run the following cmdlet to obtain the fully qualified domain name (FQDN) for each UM dial plan:</span></span>
    
    ```powershell
    (Get-UMDialPlan <dialplanname>).PhoneContext  
    ```
    
    <span data-ttu-id="a4b6e-123">자세한 내용은 다음을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a4b6e-123">For details, see:</span></span>
    
      - <span data-ttu-id="a4b6e-124">Exchange 2007의 경우에 [http://go.microsoft.com/fwlink/p/?LinkId=268678](http://go.microsoft.com/fwlink/p/?linkid=268678)는 "get-help 다이얼 플랜: Exchange 2007 도움말"을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a4b6e-124">For Exchange 2007, see "Get-UMDialplan: Exchange 2007 Help" at [http://go.microsoft.com/fwlink/p/?LinkId=268678](http://go.microsoft.com/fwlink/p/?linkid=268678).</span></span>
    
      - <span data-ttu-id="a4b6e-125">Exchange 2010의 경우에 [http://go.microsoft.com/fwlink/p/?LinkId=268679](http://go.microsoft.com/fwlink/p/?linkid=268679)는 "get-help 다이얼 플랜: Exchange 2010 도움말"을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a4b6e-125">For Exchange 2010, see "Get-UMDialplan: Exchange 2010 Help" at [http://go.microsoft.com/fwlink/p/?LinkId=268679](http://go.microsoft.com/fwlink/p/?linkid=268679).</span></span>
    
      - <span data-ttu-id="a4b6e-126">Exchange 2013는에서 [http://go.microsoft.com/fwlink/p/?LinkID=266579](http://go.microsoft.com/fwlink/p/?linkid=266579)"통합 메시징"을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a4b6e-126">For Exchange 2013, see "Unified Messaging" at [http://go.microsoft.com/fwlink/p/?LinkID=266579](http://go.microsoft.com/fwlink/p/?linkid=266579).</span></span>

3.  <span data-ttu-id="a4b6e-127">각 UM 다이얼 플랜의 다이얼 플랜 이름을 기록 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4b6e-127">Record the dial plan name of each UM dial plan.</span></span> <span data-ttu-id="a4b6e-128">사용 중인 Exchange Server 버전에 따라 다이얼 플랜 이름이 일치 하도록 각 UM 다이얼 플랜의 해당 Lync Server 다이얼 플랜 이름으로 나중에 각 다이얼 플랜 이름에 대 한 FQDN을 사용 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4b6e-128">Depending on your version of Exchange Server, you may need to use the FQDN of each dial plan name later as the name of each UM dial plan’s corresponding Lync Server dial plan so that the dial plan names match.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a4b6e-129">Lync Server 다이얼 플랜 이름은 Exchange 2010 SP1 <EM>이전</EM> 버전의 EXCHANGE에서 um 다이얼 플랜을 실행 하는 경우에만 um 다이얼 플랜 이름과 일치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4b6e-129">Lync Server dial plan names must match UM dial plan names only if the UM dial plan is running on a version of Exchange <EM>earlier</EM> than Exchange 2010 SP1.</span></span>

    
    </div>

4.  <span data-ttu-id="a4b6e-130">다음과 같이 Exchange UM을 (를) 실행 하는 서버에 다이얼 플랜을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4b6e-130">Add the dial plan to the server running Exchange UM as follows:</span></span>
    
      - <span data-ttu-id="a4b6e-131">Exchange 관리 콘솔을 사용 하도록 선택한 경우 서버에 대 한 속성 시트에서 다이얼 플랜을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4b6e-131">If you choose to use the Exchange Management Console, you can add the dial plan from the property sheet for the server.</span></span> <span data-ttu-id="a4b6e-132">특정 지침은 Exchange Server 제품 설명서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a4b6e-132">For specific instructions, see the Exchange Server product documentation.</span></span>
        
        <span data-ttu-id="a4b6e-133">Exchange 2007의 경우, "다이얼 플랜에 통합 메시징 서버를 추가 하는 방법" [http://go.microsoft.com/fwlink/p/?LinkId=268681](http://go.microsoft.com/fwlink/p/?linkid=268681)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a4b6e-133">For Exchange 2007, see "How to Add Unified Messaging Server to a Dial Plan" at [http://go.microsoft.com/fwlink/p/?LinkId=268681](http://go.microsoft.com/fwlink/p/?linkid=268681).</span></span>
        
        <span data-ttu-id="a4b6e-134">Exchange 2010의 경우에서 [http://go.microsoft.com/fwlink/p/?LinkId=268682](http://go.microsoft.com/fwlink/p/?linkid=268682)"UM 서버의 속성 보기 또는 구성"을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a4b6e-134">For Exchange 2010, see "View or Configure the Properties of a UM Server" at [http://go.microsoft.com/fwlink/p/?LinkId=268682](http://go.microsoft.com/fwlink/p/?linkid=268682).</span></span>
        
        <span data-ttu-id="a4b6e-135">Exchange 2013는에서 [http://go.microsoft.com/fwlink/p/?LinkID=266579](http://go.microsoft.com/fwlink/p/?linkid=266579)"통합 메시징"을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a4b6e-135">For Exchange 2013, see "Unified Messaging" at [http://go.microsoft.com/fwlink/p/?LinkID=266579](http://go.microsoft.com/fwlink/p/?linkid=266579).</span></span>
    
      - <span data-ttu-id="a4b6e-136">Exchange 관리 셸을 사용 하는 경우 각 Exchange UM 서버에 대해 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4b6e-136">If you use the Exchange Management Shell, run the following for each of your Exchange UM servers:</span></span>
        ```powershell
        $ums=get-umserver; 
        $dp=get-umdialplan -id <name of dial-plan created in step 1>; 
        $ums[0].DialPlans +=$dp.Identity; 
        set-umservice -instance $ums[0]
        ```
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a4b6e-137">다음 단계를 수행 하기 전에 모든 Enterprise Voice 사용자가 Exchange Server 사서함으로 구성 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4b6e-137">Before you perform the following step, make sure that all Enterprise Voice users have been configured with an Exchange Server mailbox.</span></span><BR><span data-ttu-id="a4b6e-138">Exchange 2007의 경우에 <A href="http://go.microsoft.com/fwlink/p/?linkid=268685">http://go.microsoft.com/fwlink/p/?LinkId=268685</A>는 exchange Server 2007 TechNet 라이브러리를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a4b6e-138">For Exchange 2007, see the Exchange Server 2007 TechNet Library at <A href="http://go.microsoft.com/fwlink/p/?linkid=268685">http://go.microsoft.com/fwlink/p/?LinkId=268685</A>.</span></span><BR><span data-ttu-id="a4b6e-139">Exchange 2010의 경우에 <A href="http://go.microsoft.com/fwlink/p/?linkid=268686">http://go.microsoft.com/fwlink/p/?LinkId=268686</A>는 exchange Server 2010 TechNet 라이브러리를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a4b6e-139">For Exchange 2010, see the Exchange Server 2010 TechNet Library at <A href="http://go.microsoft.com/fwlink/p/?linkid=268686">http://go.microsoft.com/fwlink/p/?LinkId=268686</A>.</span></span><BR><span data-ttu-id="a4b6e-140">1 단계에서 만든 각 다이얼 플랜에 대 한 사서함 정책을 지정할 때 기본 정책이 나 사용자가 만든 정책 중 하나를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4b6e-140">When specifying a mailbox policy for each dial plan that you created in step 1, select either the default policy or one that you have created.</span></span>

    
    </div>

5.  <span data-ttu-id="a4b6e-141">\<Exchange 설치 디렉터리\>\\스크립트로 이동한 다음 exchange를 단일 포리스트에 배포 하는 경우 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4b6e-141">Navigate to \<Exchange installation directory\>\\Scripts, and then if Exchange is deployed in a single forest, type:</span></span>
    ```console
    exchucutil.ps1
    ```
    <span data-ttu-id="a4b6e-142">또는 Exchange가 여러 포리스트에 배포 된 경우 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4b6e-142">Or, if Exchange is deployed in multiple forests, type:</span></span>
    ```console
    exchucutil.ps1 -Forest:"<forest FQDN>"
    ```
    <span data-ttu-id="a4b6e-143">여기서 포리스트 FQDN은 Lync 서버가 배포 되는 포리스트를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4b6e-143">where forest FQDN specifies the forest in which Lync Server is deployed.</span></span>
    
    <span data-ttu-id="a4b6e-144">여러 IP 게이트웨이와 연결 된 UM 다이얼 플랜이 하나 이상 있는 경우 6 단계로 넘어갑니다.</span><span class="sxs-lookup"><span data-stu-id="a4b6e-144">If you have one or more UM dial plans that are associated with multiple IP gateways, continue to step 6.</span></span> <span data-ttu-id="a4b6e-145">다이얼 플랜이 각 IP 게이트웨이와만 연결 되어 있는 경우 6 단계를 건너뜁니다.</span><span class="sxs-lookup"><span data-stu-id="a4b6e-145">If your dial plans are each associated with only a single IP gateway, skip step 6.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="a4b6e-146">Exchucutil를 실행 <EM>한 후</EM> <STRONG>Lync Server 프런트 엔드</STRONG> 서비스 (rtcsrv)를 다시 시작 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4b6e-146">Be sure to restart the <STRONG>Lync Server Front-End</STRONG> service (rtcsrv.exe) <EM>after</EM> you run exchucutil.ps1.</span></span> <span data-ttu-id="a4b6e-147">그렇지 않으면 Lync Server는 토폴로지에서 통합 메시징을 검색 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a4b6e-147">Otherwise, Lync Server will not detect Unified Messaging in the topology.</span></span>

    
    </div>

6.  <span data-ttu-id="a4b6e-148">Exchange 관리 셸 또는 Exchange 관리 콘솔을 사용 하 여 각 다이얼 플랜에 연결 된 IP 게이트웨이 중 하나를 제외 하 고 모두에 대해 아웃 바운드 호출을 사용 하지 않도록 설정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4b6e-148">Using either the Exchange Management Shell or Exchange Management Console, disable outbound calling for all but one of the IP gateways associated with each of your dial plans.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a4b6e-149">이 단계는 전화 접속 시나리오의 경우 처럼 Exchange Server 통합 메시징을 실행 하는 서버에의 한 아웃 바운드 호출이 회사 방화벽을 안정적으로 트래버스 하도록 하기 위해 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4b6e-149">This step is necessary to make sure that outbound calls by the server running Exchange Server Unified Messaging to external users (for example, as is the case with play-on-phone scenarios) reliably traverse the corporate firewall.</span></span>

    
    </div>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="a4b6e-150">나가는 통화를 허용 하는 데 사용할 UM IP 게이트웨이를 선택 하는 경우 대부분의 트래픽을 처리 하는 것을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4b6e-150">When selecting the UM IP gateway through which to allow outgoing calls, choose the one that is likely to handle the most traffic.</span></span> <span data-ttu-id="a4b6e-151">Lync Server 디렉터 풀에 연결 하는 IP 게이트웨이를 통해 나가는 트래픽을 허용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a4b6e-151">Do not allow outgoing traffic through an IP gateway that connects to a pool of Lync Server Directors.</span></span> <span data-ttu-id="a4b6e-152">또한 다른 중앙 사이트 또는 지점 사이트의 풀을 사용 하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="a4b6e-152">Also avoid pools in another central site or a branch site.</span></span> <span data-ttu-id="a4b6e-153">다음 방법 중 하나를 사용 하 여 IP 게이트웨이를 통과 하는 데 나가는 통화를 차단할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4b6e-153">You can use either of the following methods to block outgoing calls from passing through an IP gateway:</span></span>

    
    </div>
    
      - <span data-ttu-id="a4b6e-154">Exchange 관리 셸을 사용 하는 경우 다음 명령을 실행 하 여 각 IP 게이트웨이를 사용 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4b6e-154">If you use the Exchange Management Shell, disable each IP gateway by running the following command:</span></span>
        ```powershell
        Set-UMIPGateway <gatewayname> -OutcallsAllowed $false
        ```
        <span data-ttu-id="a4b6e-155">Exchange 2007의 경우에서 [http://go.microsoft.com/fwlink/p/?LinkId=268687](http://go.microsoft.com/fwlink/p/?linkid=268687)"Set UMIPGateway: Exchange 2007 도움말"을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a4b6e-155">For Exchange 2007, see "Set-UMIPGateway: Exchange 2007 Help" at [http://go.microsoft.com/fwlink/p/?LinkId=268687](http://go.microsoft.com/fwlink/p/?linkid=268687).</span></span>
        
        <span data-ttu-id="a4b6e-156">Exchange 2010의 경우에서 [http://go.microsoft.com/fwlink/p/?LinkId=268688](http://go.microsoft.com/fwlink/p/?linkid=268688)"Set UMIPGateway: Exchange 2010 도움말"을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a4b6e-156">For Exchange 2010, see "Set-UMIPGateway: Exchange 2010 Help" at [http://go.microsoft.com/fwlink/p/?LinkId=268688](http://go.microsoft.com/fwlink/p/?linkid=268688).</span></span>
    
      - <span data-ttu-id="a4b6e-157">Exchange 관리 콘솔을 사용 하는 경우 **이 IP 게이트웨이를 통해 발신 전화 허용** 확인란의 선택을 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4b6e-157">If you use the Exchange Management Console, clear the **Allow outgoing calls through this IP gateway** check box.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="a4b6e-158">UM SIP URI 다이얼 플랜을 단일 IP 게이트웨이와만 연결 하는 경우이 게이트웨이를 통해 나가는 호출을 허용 하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="a4b6e-158">If your UM SIP URI dial plan is associated with only a single IP gateway, do not disallow outgoing calls through this gateway.</span></span>

    
    </div>

7.  <span data-ttu-id="a4b6e-159">각 Lync Server 다이얼 플랜에 대 한 UM 자동 전화 교환을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a4b6e-159">Create a UM auto-attendant for each Lync Server dial plan.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="a4b6e-160">자동 전화 교환 이름에 공백을 포함 하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="a4b6e-160">Do not include any spaces in the name of the auto attendant.</span></span>

    
    </div>
    
    ```powershell
    New-umautoattendant -name <auto attendant name> -umdialplan < name of dial plan created in step 1> -PilotIdentifierList <auto attendant phone number in E.164 format> -SpeechEnabled $true -Status Enabled
    ```
    <span data-ttu-id="a4b6e-161">자세한 내용은 다음을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a4b6e-161">For details, see:</span></span>
    
      - <span data-ttu-id="a4b6e-162">Exchange 2007의 경우에는에서 [http://go.microsoft.com/fwlink/p/?LinkId=268689](http://go.microsoft.com/fwlink/p/?linkid=268689)"새로운 UMAutoAttendant 전화 교환: Exchange 2007 도움말"을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a4b6e-162">For Exchange 2007, see "New-UMAutoAttendant: Exchange 2007 Help" at [http://go.microsoft.com/fwlink/p/?LinkId=268689](http://go.microsoft.com/fwlink/p/?linkid=268689).</span></span>
    
      - <span data-ttu-id="a4b6e-163">Exchange 2010의 경우에는에서 [http://go.microsoft.com/fwlink/p/?LinkId=268690](http://go.microsoft.com/fwlink/p/?linkid=268690)"새로운 UMAutoAttendant 전화 교환: Exchange 2010 도움말"을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a4b6e-163">For Exchange 2010, see "New-UMAutoAttendant: Exchange 2010 Help" at [http://go.microsoft.com/fwlink/p/?LinkId=268690](http://go.microsoft.com/fwlink/p/?linkid=268690).</span></span>
    
    <span data-ttu-id="a4b6e-164">각 사용자에 대해 Lync Server 사용자가 엔터프라이즈 음성을 사용할 수 있도록 설정한 후 SIP Uri를 확인 한 후에 다음 단계를 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4b6e-164">The following step should be performed for each user after you have enabled Lync Server users for Enterprise Voice and know their SIP URIs.</span></span>

8.  <span data-ttu-id="a4b6e-165">UM 다이얼 플랜을 사용 하 여 Exchange UM 사용자 (각각의 Exchange 사서함을 구성 해야 함)를 연결 하 고 각 사용자에 대 한 SIP URI를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a4b6e-165">Associate Exchange UM users (each of whom should be configured with an Exchange mail box) with the UM dial plan and create a SIP URI for each user.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a4b6e-166">다음 샘플의 <STRONG>SIPResourceIdentifier</STRONG> 는 Lync Server 사용자의 SIP 주소 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4b6e-166">The <STRONG>SIPResourceIdentifier</STRONG> in the following sample must be the SIP address of the Lync Server user.</span></span>

    
    </div>
    
    ```powershell
    enable-ummailbox -id <user name> -ummailboxpolicy <name of the mailbox policy for the dial plan created in step 1> -Extensions <extension> -SIPResourceIdentifier "<user name>@<full domain name>" -PIN <user pin>
    ```
    <span data-ttu-id="a4b6e-167">자세한 내용은 다음을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a4b6e-167">For details, see:</span></span>
    
      - <span data-ttu-id="a4b6e-168">Exchange 2007의 경우에서 [http://go.microsoft.com/fwlink/p/?LinkId=268691](http://go.microsoft.com/fwlink/p/?linkid=268691)"Enable-ummailbox: Exchange 2007 도움말"을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a4b6e-168">For Exchange 2007, see "Enable-UMMailbox: Exchange 2007 Help" at [http://go.microsoft.com/fwlink/p/?LinkId=268691](http://go.microsoft.com/fwlink/p/?linkid=268691).</span></span>
    
      - <span data-ttu-id="a4b6e-169">Exchange 2010의 경우에서 [http://go.microsoft.com/fwlink/p/?LinkId=268692](http://go.microsoft.com/fwlink/p/?linkid=268692)"Enable-ummailbox: Exchange 2010 도움말"을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a4b6e-169">For Exchange 2010, see "Enable-UMMailbox: Exchange 2010 Help" at [http://go.microsoft.com/fwlink/p/?LinkId=268692](http://go.microsoft.com/fwlink/p/?linkid=268692).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

