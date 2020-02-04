---
title: 'Lync Server 2013: Microsoft Exchange Server의 통합 메시징과 함께 작동하도록 Lync Server 2013 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure Lync Server 2013 to work with Unified Messaging on Microsoft Exchange Server
ms:assetid: 1098ae4d-f57f-44f3-804e-39889d9fc14e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398193(v=OCS.15)
ms:contentKeyID: 48183430
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 985b2d286f65be2353c2ace0d59872f4d0fc47ad
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41729748"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-lync-server-2013-to-work-with-unified-messaging-on-microsoft-exchange-server"></a><span data-ttu-id="34ec9-102">Microsoft Exchange Server의 통합 메시징과 함께 작동하도록 Lync Server 2013 구성</span><span class="sxs-lookup"><span data-stu-id="34ec9-102">Configure Lync Server 2013 to work with Unified Messaging on Microsoft Exchange Server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span data-ttu-id="34ec9-103">_**마지막으로 수정한 주제:** 2013-04-03_</span><span class="sxs-lookup"><span data-stu-id="34ec9-103">_**Topic Last Modified:** 2013-04-03_</span></span>

<span data-ttu-id="34ec9-104">이 단계를 수행 하려면 Exchange UM 통합 유틸리티 (OcsUmUtil. exe)가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="34ec9-104">This step requires the Exchange UM Integration Utility (OcsUmUtil.exe).</span></span> <span data-ttu-id="34ec9-105">이 도구는 다음의 Lync Server 2013 서버에 있습니다. \\프로그램 파일\\공통 파일\\Microsoft Lync Server 2013\\지원 폴더</span><span class="sxs-lookup"><span data-stu-id="34ec9-105">This tool is located on the Lync Server 2013 server in the ..\\Program Files\\Common Files\\Microsoft Lync Server 2013\\Support folder.</span></span>

<div>

## <a name="running-the-exchange-um-integration-utility"></a><span data-ttu-id="34ec9-106">Exchange UM 통합 유틸리티 실행</span><span class="sxs-lookup"><span data-stu-id="34ec9-106">Running the Exchange UM Integration Utility</span></span>

<span data-ttu-id="34ec9-107">Exchange UM 통합 유틸리티는 다음 특성을 가진 사용자 계정에서 실행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="34ec9-107">The Exchange UM Integration Utility must be run from a user account with the following characteristics:</span></span>

  - <span data-ttu-id="34ec9-108">RTCUniversalServerAdmins 및 RtcUniversalUserAdmins 그룹의 구성원 자격 (Exchange Server 통합 메시징 설정 읽기 권한이 포함 되어 있음)</span><span class="sxs-lookup"><span data-stu-id="34ec9-108">Membership in the RTCUniversalServerAdmins and RtcUniversalUserAdmins groups (which includes permission to read Exchange Server Unified Messaging settings).</span></span>

  - <span data-ttu-id="34ec9-109">지정 된 OU (조직 구성 단위) 컨테이너에서 연락처 개체를 만들기 위한 도메인 내의 사용자 권한</span><span class="sxs-lookup"><span data-stu-id="34ec9-109">User rights within the domain to create contact objects in the specified organizational unit (OU) container.</span></span>

<span data-ttu-id="34ec9-110">Exchange UM 통합 유틸리티를 실행 하는 경우 다음 작업이 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="34ec9-110">When you run the Exchange UM Integration Utility, it performs the following tasks:</span></span>

  - <span data-ttu-id="34ec9-111">엔터프라이즈 음성 사용자가 사용할 각 자동 전화 교환 및 가입자 액세스 번호에 대 한 연락처 개체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="34ec9-111">Creates contact objects for each auto-attendant and subscriber access number to be used by Enterprise Voice users.</span></span>

  - <span data-ttu-id="34ec9-112">각 Enterprise Voice dial 계획의 이름이 해당 UM (통합 메시징) 다이얼 플랜 전화 컨텍스트와 일치 하는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="34ec9-112">Verifies that the name of each Enterprise Voice dial plan matches its corresponding unified messaging (UM) dial plan phone context.</span></span> <span data-ttu-id="34ec9-113">이 일치는 UM 다이얼 플랜이 Exchange 2010 서비스 팩 1 보다 *이전* 버전의 exchange에서 실행 되는 경우에만 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="34ec9-113">This matching is necessary only if the UM dial plan is running on a version of Exchange *earlier* than Exchange 2010 Service Pack 1 (SP1).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="34ec9-114">Exchange UM 통합 유틸리티를 실행 하기 전에 다음을 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="34ec9-114">Before running the Exchange UM Integration Utility, be sure that you have done the following:</span></span>
> <ul>
> <li><p><span data-ttu-id="34ec9-115">Exchange 제품 설명서에 설명 된 대로 하나 이상의 Exchange UM 다이얼 플랜을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="34ec9-115">Create one or more Exchange UM dial plans, as described in the Exchange product documentation.</span></span></p>
> <p><span data-ttu-id="34ec9-116">Microsoft Exchange Server 2010의 경우에 &quot;&quot; <a href="http://go.microsoft.com/fwlink/p/?linkid=186177">http://go.microsoft.com/fwlink/p/?linkId=186177</a>는 UM 다이얼 플랜 만들기를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="34ec9-116">For Microsoft Exchange Server 2010, see &quot;Create a UM Dial Plan&quot; at <a href="http://go.microsoft.com/fwlink/p/?linkid=186177">http://go.microsoft.com/fwlink/p/?linkId=186177</a>.</span></span></p>
> <p><span data-ttu-id="34ec9-117">Microsoft Exchange Server 2007 SP1(서비스 팩 1)의 경우에 &quot;&quot; <a href="http://go.microsoft.com/fwlink/p/?linkid=185771">http://go.microsoft.com/fwlink/p/?linkId=185771</a>는 통합 메시징 SIP URI 다이얼 플랜을 만드는 방법을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="34ec9-117">For Microsoft Exchange Server 2007 Service Pack 1 (SP1), see &quot;How to Create a Unified Messaging SIP URI Dial Plan&quot; at <a href="http://go.microsoft.com/fwlink/p/?linkid=185771">http://go.microsoft.com/fwlink/p/?linkId=185771</a>.</span></span></p></li>
> <li><p><span data-ttu-id="34ec9-118"><a href="lync-server-2013-create-a-dial-plan.md">Lync server 2013에서 다이얼 플랜 만들기</a>에 설명 된 대로 하나 이상의 해당 Lync Server 다이얼 플랜을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="34ec9-118">Create one or more corresponding Lync Server dial plans, as described in <a href="lync-server-2013-create-a-dial-plan.md">Create a dial plan in Lync Server 2013</a>.</span></span></p></li>
> <ul><li><span data-ttu-id="34ec9-119">Microsoft Exchange Server 2010 SP1 이전 버전의 Exchange를 사용 하는 경우 Lync Server 2013 다이얼 플랜 <STRONG>간단한 이름</STRONG> 필드에 해당 하는 exchange UM (통합 메시징) SIP 다이얼 플랜의 FQDN (정규화 된 도메인 이름)을 입력 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="34ec9-119">If you are using a version of Exchange that is earlier than Microsoft Exchange Server 2010 SP1, you must enter the fully qualified domain name (FQDN) of the corresponding Exchange Unified Messaging (UM) SIP dial plan in the Lync Server 2013 dial plan <STRONG>Simple name</STRONG> field.</span></span> <span data-ttu-id="34ec9-120">Microsoft Exchange Server 2010 SP1 또는 최신 서비스 팩을 사용 하는 경우에는이 다이얼 플랜 이름 일치가 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="34ec9-120">If you are using Microsoft Exchange Server 2010 SP1 or latest service pack, this dial plan name matching is not necessary.</span></span></li></ul>
> <li><span data-ttu-id="34ec9-121">자동 전화 교환을 만들고 구독자 액세스 번호와 자동 전화 교환 번호가 모두 E 164 형식으로 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="34ec9-121">Create an auto-attendant and make sure that both the subscriber access number and auto-attendant number are in E.164 format.</span></span></li></ul>


<div>

## <a name="to-run-the-exchange-um-integration-utility"></a><span data-ttu-id="34ec9-122">Exchange UM 통합 유틸리티를 실행 하려면</span><span class="sxs-lookup"><span data-stu-id="34ec9-122">To run the Exchange UM Integration Utility</span></span>

1.  <span data-ttu-id="34ec9-123">프런트 엔드 서버에서 명령 프롬프트를 열고 **cd% CommonProgramFiles%\\Microsoft Lync Server 2013\\지원을**입력 한 다음 enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="34ec9-123">On a Front End Server, open a command prompt and type **cd %CommonProgramFiles%\\Microsoft Lync Server 2013\\Support**, and then press ENTER.</span></span>

2.  <span data-ttu-id="34ec9-124">**Ocsumutil**을 입력 한 다음 enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="34ec9-124">Type **OcsUmUtil.exe**, and then press ENTER.</span></span>

3.  <span data-ttu-id="34ec9-125">**데이터 로드** 를 클릭 하 여 신뢰할 수 있는 모든 Exchange 포리스트를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="34ec9-125">Click **Load Data** to find all trusted Exchange forests.</span></span>

4.  <span data-ttu-id="34ec9-126">**SIP 다이얼** 플랜 목록에서 연락처 개체를 만들 UM SIP 다이얼 플랜을 선택한 다음 **추가**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="34ec9-126">In the **SIP Dial Plans** list, select a UM SIP dial plan for which you want to create contact objects, and then click **Add**.</span></span>

5.  <span data-ttu-id="34ec9-127">**연락처** 상자에서 기본 조직 구성 단위를 그대로 사용 하거나 **찾아보기를** 클릭 하 여 **OU 선택기**를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="34ec9-127">In the **Contact** box, accept the default organizational unit, or click **Browse** to start the **OU Picker**.</span></span> <span data-ttu-id="34ec9-128">**Ou** 선택 상자에서 ou를 선택 하 고 **확인**을 클릭 하거나 **새 ou** 만들기를 클릭 하 여 도메인의 루트 또는 다른 ou 아래에 새 조직 구성 단위를 만들 수 있습니다 (예: "OU = RTC 특수 계정, dc = fourthcoffee, dc = com" **) .를**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="34ec9-128">In the **OU Picker** box, you can select an OU and click **OK**, or you can click **Make New OU** to create a new organizational unit under the root or any other OU in the domain (for example, "OU=RTC Special Accounts,DC=fourthcoffee,DC=com"), and then click **OK**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="34ec9-129">선택 하거나 만든 OU의 DN (고유 이름)이 이제 <STRONG>조직 구성 단위</STRONG> 상자에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="34ec9-129">The distinguished name (DN) of the OU that you have selected or created is now displayed in the <STRONG>Organizational Unit</STRONG> box.</span></span>

    
    </div>

6.  <span data-ttu-id="34ec9-130">**이름** 상자에서 기본 다이얼 플랜 이름을 그대로 사용 하거나 만들려는 연락처 개체의 새 표시 이름을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="34ec9-130">In the **Name** box, either accept the default dial plan name or type a new display name for the contact object that you are creating.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="34ec9-131">예를 들어 구독자 액세스 연락처 개체를 만드는 경우 단순히 구독자 액세스 이름을 이름만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="34ec9-131">For example, if you are creating a subscriber access contact object, you might simply name it Subscriber Access.</span></span>

    
    </div>

7.  <span data-ttu-id="34ec9-132">**Sip 주소** 상자에서 기본 sip 주소를 적용 하거나 새 sip 주소를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="34ec9-132">In the **SIP Address** box, either accept the default SIP address or type a new SIP address.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="34ec9-133">새로운 SIP 주소를 입력 하는 경우 <STRONG>sip:</STRONG> (즉, 콜론을 포함 하 여 "sip:")로 시작 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="34ec9-133">If you type a new SIP address, it must begin with <STRONG>SIP:</STRONG> (that is, "SIP:" including the colon).</span></span>

    
    </div>

8.  <span data-ttu-id="34ec9-134">**서버 또는 풀** 목록에서 연락처 개체를 사용할 수 있는 Standard Edition Server 또는 프런트 엔드 풀을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="34ec9-134">In the **Server or Pool** list, select the Standard Edition server or Front End pool in which the contact object is to be enabled.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="34ec9-135">선택 하는 풀은 Enterprise Voice 및 Exchange UM을 배포 하는 사용자가 동일한 한 풀입니다.</span><span class="sxs-lookup"><span data-stu-id="34ec9-135">Preferably, the pool you select is the same one pool where users enabled for Enterprise Voice and Exchange UM are deployed.</span></span>

    
    </div>

9.  <span data-ttu-id="34ec9-136">**전화 번호** 목록에서 **전화 번호 입력** 또는 **Exchange UM에서이 조종사 번호 사용** 을 선택 하 고 전화 번호를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="34ec9-136">In the **Phone Number** list, select either **Enter phone number** or **Use this pilot number from Exchange UM** and then enter a phone number.</span></span>

10. <span data-ttu-id="34ec9-137">**연락처 유형** 목록에서 만들려는 연락처 유형을 선택 하 고 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="34ec9-137">In the **Contact Type** list, select the contact type that you want to create, and then click **OK**.</span></span>

11. <span data-ttu-id="34ec9-138">만들려는 추가 연락처 개체에 대해 1 ~ 10 단계를 반복 합니다.</span><span class="sxs-lookup"><span data-stu-id="34ec9-138">Repeat steps 1 through 10 for additional contact objects that you want to create.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="34ec9-139">각 자동 전화 교환에 대해 하나 이상의 대화 상대를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="34ec9-139">You should create at least one contact for each auto attendant.</span></span> <span data-ttu-id="34ec9-140">외부 액세스를 원할 경우 구독자 액세스 연락처가 필요 하며 직접 안쪽 다이얼 (a) 번호를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="34ec9-140">If you want external access, you also need a Subscriber Access contact and to specify Direct Inward Dial (DID) numbers.</span></span>

    
    </div>

</div>

<span data-ttu-id="34ec9-141">연락처 개체가 만들어졌는지 확인 하려면 Active Directory 사용자 및 컴퓨터를 열고 개체가 만들어진 OU를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="34ec9-141">To verify that the contact objects have been created, open Active Directory Users and Computers and select the OU in which the objects were created.</span></span> <span data-ttu-id="34ec9-142">연락처 개체가 세부 정보 창에 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="34ec9-142">The contact objects should appear in the details pane.</span></span>

<span data-ttu-id="34ec9-143"></div>

</div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="34ec9-143"></div>

</div>

<span> </span>

</div>

</div>

</span></span></div>

