---
title: 'Lync Server 2013: Microsoft Exchange Server의 통합 메시징과 함께 작동 하도록 Lync Server 2013 구성'
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
ms.openlocfilehash: 043015fb30ca21a697a9758a5fbb4d916b006046
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146451"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-lync-server-2013-to-work-with-unified-messaging-on-microsoft-exchange-server"></a><span data-ttu-id="237e5-102">Microsoft Exchange Server의 통합 메시징과 함께 작동 하도록 Lync Server 2013 구성</span><span class="sxs-lookup"><span data-stu-id="237e5-102">Configure Lync Server 2013 to work with Unified Messaging on Microsoft Exchange Server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span data-ttu-id="237e5-103">_**마지막으로 수정 된 항목:** 2013-04-03_</span><span class="sxs-lookup"><span data-stu-id="237e5-103">_**Topic Last Modified:** 2013-04-03_</span></span>

<span data-ttu-id="237e5-104">이 단계에서는 Exchange UM 통합 유틸리티(OcsUmUtil.exe)가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="237e5-104">This step requires the Exchange UM Integration Utility (OcsUmUtil.exe).</span></span> <span data-ttu-id="237e5-105">이 도구는의에 있는 Lync Server 2013 서버에 있습니다. \\프로그램 파일\\공용 파일\\Microsoft Lync Server 2013\\Support 폴더입니다.</span><span class="sxs-lookup"><span data-stu-id="237e5-105">This tool is located on the Lync Server 2013 server in the ..\\Program Files\\Common Files\\Microsoft Lync Server 2013\\Support folder.</span></span>

<div>

## <a name="running-the-exchange-um-integration-utility"></a><span data-ttu-id="237e5-106">Exchange UM 통합 유틸리티 실행</span><span class="sxs-lookup"><span data-stu-id="237e5-106">Running the Exchange UM Integration Utility</span></span>

<span data-ttu-id="237e5-107">Exchange UM 통합 유틸리티는 다음과 같은 사용자 계정에서 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="237e5-107">The Exchange UM Integration Utility must be run from a user account with the following characteristics:</span></span>

  - <span data-ttu-id="237e5-108">RTCUniversalServerAdmins 및 RtcUniversalUserAdmins 그룹의 구성원(Exchange Server 통합 메시징 설정을 읽을 수 있는 권한 포함)</span><span class="sxs-lookup"><span data-stu-id="237e5-108">Membership in the RTCUniversalServerAdmins and RtcUniversalUserAdmins groups (which includes permission to read Exchange Server Unified Messaging settings).</span></span>

  - <span data-ttu-id="237e5-109">도메인 내에서 지정 된 OU (조직 구성 단위) 컨테이너에 연락처 개체를 만들 수 있는 사용자 권한</span><span class="sxs-lookup"><span data-stu-id="237e5-109">User rights within the domain to create contact objects in the specified organizational unit (OU) container.</span></span>

<span data-ttu-id="237e5-110">Exchange UM 통합 유틸리티를 실행하면 다음 작업이 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="237e5-110">When you run the Exchange UM Integration Utility, it performs the following tasks:</span></span>

  - <span data-ttu-id="237e5-111">Enterprise Voice 사용자가 사용할 각 자동 전화 교환 및 구독자 액세스 번호에 대한 연락처 개체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="237e5-111">Creates contact objects for each auto-attendant and subscriber access number to be used by Enterprise Voice users.</span></span>

  - <span data-ttu-id="237e5-112">각 Enterprise Voice 다이얼 플랜의 이름이 해당 UM (통합 메시징) 다이얼 플랜 전화 컨텍스트와 일치 하는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="237e5-112">Verifies that the name of each Enterprise Voice dial plan matches its corresponding unified messaging (UM) dial plan phone context.</span></span> <span data-ttu-id="237e5-113">이 일치는 UM 다이얼 플랜이 Exchange 2010 SP1 (서비스 팩 1) *이전의* exchange 버전에서 실행 되는 경우에만 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="237e5-113">This matching is necessary only if the UM dial plan is running on a version of Exchange *earlier* than Exchange 2010 Service Pack 1 (SP1).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="237e5-114">Exchange UM 통합 유틸리티를 실행 하기 전에 다음을 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="237e5-114">Before running the Exchange UM Integration Utility, be sure that you have done the following:</span></span>
> <ul>
> <li><p><span data-ttu-id="237e5-115">Exchange 제품 설명서에 설명 된 대로 하나 이상의 Exchange UM 다이얼 플랜을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="237e5-115">Create one or more Exchange UM dial plans, as described in the Exchange product documentation.</span></span></p>
> <p><span data-ttu-id="237e5-116">Microsoft Exchange Server 2010의 경우에 &quot;&quot; <a href="https://go.microsoft.com/fwlink/p/?linkid=186177">https://go.microsoft.com/fwlink/p/?linkId=186177</a>는 UM 다이얼 플랜 만들기를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="237e5-116">For Microsoft Exchange Server 2010, see &quot;Create a UM Dial Plan&quot; at <a href="https://go.microsoft.com/fwlink/p/?linkid=186177">https://go.microsoft.com/fwlink/p/?linkId=186177</a>.</span></span></p>
> <p><span data-ttu-id="237e5-117">Microsoft Exchange Server 2007 SP1 (서비스 팩 1)의 경우 통합 &quot;메시징 SIP URI 다이얼 플랜&quot; 을 만드는 방법을 참조 하세요 <a href="https://go.microsoft.com/fwlink/p/?linkid=185771">https://go.microsoft.com/fwlink/p/?linkId=185771</a>.</span><span class="sxs-lookup"><span data-stu-id="237e5-117">For Microsoft Exchange Server 2007 Service Pack 1 (SP1), see &quot;How to Create a Unified Messaging SIP URI Dial Plan&quot; at <a href="https://go.microsoft.com/fwlink/p/?linkid=185771">https://go.microsoft.com/fwlink/p/?linkId=185771</a>.</span></span></p></li>
> <li><p><span data-ttu-id="237e5-118"><a href="lync-server-2013-create-a-dial-plan.md">Lync server 2013의 다이얼 플랜 만들기</a>에 설명 된 대로 해당 하는 lync server 다이얼 플랜을 하나 이상 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="237e5-118">Create one or more corresponding Lync Server dial plans, as described in <a href="lync-server-2013-create-a-dial-plan.md">Create a dial plan in Lync Server 2013</a>.</span></span></p></li>
> <ul><li><span data-ttu-id="237e5-119">Microsoft Exchange Server 2010 s p 1 보다 이전 버전의 Exchange를 사용 하는 경우 Lync Server 2013 다이얼 플랜 <STRONG>단순한 이름</STRONG> 필드에 해당 하는 exchange UM (통합 메시징) SIP 다이얼 플랜의 FQDN (정규화 된 도메인 이름)을 입력 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="237e5-119">If you are using a version of Exchange that is earlier than Microsoft Exchange Server 2010 SP1, you must enter the fully qualified domain name (FQDN) of the corresponding Exchange Unified Messaging (UM) SIP dial plan in the Lync Server 2013 dial plan <STRONG>Simple name</STRONG> field.</span></span> <span data-ttu-id="237e5-120">Microsoft Exchange Server 2010 SP1 또는 최신 서비스 팩을 사용 하는 경우에는이 다이얼 플랜 이름 일치가 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="237e5-120">If you are using Microsoft Exchange Server 2010 SP1 or latest service pack, this dial plan name matching is not necessary.</span></span></li></ul>
> <li><span data-ttu-id="237e5-121">자동 전화 교환을 만들고 구독자 액세스 번호와 자동 전화 교환 번호가 모두 E.164 형식인지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="237e5-121">Create an auto-attendant and make sure that both the subscriber access number and auto-attendant number are in E.164 format.</span></span></li></ul>


<div>

## <a name="to-run-the-exchange-um-integration-utility"></a><span data-ttu-id="237e5-122">Exchange UM 통합 유틸리티를 실행하려면</span><span class="sxs-lookup"><span data-stu-id="237e5-122">To run the Exchange UM Integration Utility</span></span>

1.  <span data-ttu-id="237e5-123">프런트 엔드 서버에서 명령 프롬프트를 열고 **cd% CommonProgramFiles%\\Microsoft Lync Server 2013\\Support**를 입력 한 다음 enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="237e5-123">On a Front End Server, open a command prompt and type **cd %CommonProgramFiles%\\Microsoft Lync Server 2013\\Support**, and then press ENTER.</span></span>

2.  <span data-ttu-id="237e5-124">**OcsUmUtil.exe**를 입력하고 Enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="237e5-124">Type **OcsUmUtil.exe**, and then press ENTER.</span></span>

3.  <span data-ttu-id="237e5-125">**데이터 로드**를 클릭하여 모든 신뢰할 수 있는 Exchange 포리스트를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="237e5-125">Click **Load Data** to find all trusted Exchange forests.</span></span>

4.  <span data-ttu-id="237e5-126">**SIP 다이얼 플랜** 목록에서 연락처 개체를 만들 UM SIP 다이얼 플랜을 선택하고 **추가**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="237e5-126">In the **SIP Dial Plans** list, select a UM SIP dial plan for which you want to create contact objects, and then click **Add**.</span></span>

5.  <span data-ttu-id="237e5-p104">**연락처** 상자에서 기본 조직 구성 단위를 사용하거나 **찾아보기**를 클릭하여 **OU 선택기**를 시작합니다. **OU 선택기** 상자에서 OU를 선택하고 **확인**을 클릭하거나 **새 OU 만들기**를 클릭하여 루트 또는 도메인의 다른 OU 아래에 새 조직 구성 단위(예: "OU=RTC Special Accounts,DC=fourthcoffee,DC=com")를 만들고 **확인**을 클릭할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="237e5-p104">In the **Contact** box, accept the default organizational unit, or click **Browse** to start the **OU Picker**. In the **OU Picker** box, you can select an OU and click **OK**, or you can click **Make New OU** to create a new organizational unit under the root or any other OU in the domain (for example, "OU=RTC Special Accounts,DC=fourthcoffee,DC=com"), and then click **OK**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="237e5-129">이제 선택하거나 만든 OU의 DN(고유 이름)이 <STRONG>조직 구성 단위</STRONG> 상자에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="237e5-129">The distinguished name (DN) of the OU that you have selected or created is now displayed in the <STRONG>Organizational Unit</STRONG> box.</span></span>

    
    </div>

6.  <span data-ttu-id="237e5-130">**이름** 상자에서 기본 다이얼 플랜 이름을 적용하거나 만들고 있는 연락처 개체에 대해 새 표시 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="237e5-130">In the **Name** box, either accept the default dial plan name or type a new display name for the contact object that you are creating.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="237e5-131">예를 들어 구독자 액세스 연락처 개체를 만들고 있는 경우에는 구독자 액세스라고 명명하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="237e5-131">For example, if you are creating a subscriber access contact object, you might simply name it Subscriber Access.</span></span>

    
    </div>

7.  <span data-ttu-id="237e5-132">**SIP 주소** 상자에서 기본 SIP 주소를 그대로 적용하거나 새 SIP 주소를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="237e5-132">In the **SIP Address** box, either accept the default SIP address or type a new SIP address.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="237e5-133">새 SIP 주소를 입력할 경우 이 주소는 <STRONG>SIP:</STRONG>(즉 콜론을 포함하여 "SIP:")로 시작되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="237e5-133">If you type a new SIP address, it must begin with <STRONG>SIP:</STRONG> (that is, "SIP:" including the colon).</span></span>

    
    </div>

8.  <span data-ttu-id="237e5-134">**서버 또는 풀** 목록에서 연락처 개체를 사용 하도록 설정할 Standard Edition Server 또는 프런트 엔드 풀을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="237e5-134">In the **Server or Pool** list, select the Standard Edition server or Front End pool in which the contact object is to be enabled.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="237e5-135">Enterprise Voice 및 Exchange UM 사용자가 배포된 풀을 선택하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="237e5-135">Preferably, the pool you select is the same one pool where users enabled for Enterprise Voice and Exchange UM are deployed.</span></span>

    
    </div>

9.  <span data-ttu-id="237e5-136">**전화 번호** 목록에서 **전화 번호 입력** 또는 **Exchange UM에서 이 파일럿 번호 사용**을 선택한 다음 전화 번호를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="237e5-136">In the **Phone Number** list, select either **Enter phone number** or **Use this pilot number from Exchange UM** and then enter a phone number.</span></span>

10. <span data-ttu-id="237e5-137">**연락처 유형** 목록에서 만들 연락처 유형을 선택하고 **확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="237e5-137">In the **Contact Type** list, select the contact type that you want to create, and then click **OK**.</span></span>

11. <span data-ttu-id="237e5-138">추가로 만들 연락처 개체에 대해 1-10단계를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="237e5-138">Repeat steps 1 through 10 for additional contact objects that you want to create.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="237e5-p105">각 자동 전화 교환에 대해 적어도 하나의 연락처 개체를 만들어야 하며, 외부 액세스를 원하는 경우에는 구독자 액세스 연락처도 필요하고 DID(Direct Inward Dial) 번호도 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="237e5-p105">You should create at least one contact for each auto attendant. If you want external access, you also need a Subscriber Access contact and to specify Direct Inward Dial (DID) numbers.</span></span>

    
    </div>

</div>

<span data-ttu-id="237e5-p106">연락처 개체가 만들어졌는지 확인하려면 Active Directory 사용자 및 컴퓨터를 열고 개체를 만든 OU를 선택하십시오. 연락처 개체가 세부 정보 창에 나타나야 합니다.</span><span class="sxs-lookup"><span data-stu-id="237e5-p106">To verify that the contact objects have been created, open Active Directory Users and Computers and select the OU in which the objects were created. The contact objects should appear in the details pane.</span></span>

<span data-ttu-id="237e5-143"></div>

</div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="237e5-143"></div>

</div>

<span> </span>

</div>

</div>

</span></span></div>

