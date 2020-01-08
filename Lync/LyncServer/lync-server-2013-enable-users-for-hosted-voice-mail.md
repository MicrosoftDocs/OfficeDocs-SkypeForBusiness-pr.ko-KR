---
title: Lync Server 2013에서 사용자가 호스팅된 음성 사서함을 사용할 수 있도록 설정
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enable users for hosted voice mail
ms:assetid: fa559f8f-ef99-43a1-b580-9e998b95efb8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413062(v=OCS.15)
ms:contentKeyID: 48185919
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 45872df26989d8d264ce77406bfbce86f321ccf8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982379"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-users-for-hosted-voice-mail-in-lync-server-2013"></a><span data-ttu-id="a1b59-102">Lync Server 2013에서 사용자가 호스팅된 음성 사서함을 사용할 수 있도록 설정</span><span class="sxs-lookup"><span data-stu-id="a1b59-102">Enable users for hosted voice mail in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a1b59-103">_**마지막으로 수정한 주제:** 2012-09-24_</span><span class="sxs-lookup"><span data-stu-id="a1b59-103">_**Topic Last Modified:** 2012-09-24_</span></span>

<span data-ttu-id="a1b59-104">호스트 된 Exchange UM (통합 메시징) 서비스에서 Lync Server 2013 사용자가 음성 메일을 사용 하도록 설정 하려면 다음 절차를 따르세요.</span><span class="sxs-lookup"><span data-stu-id="a1b59-104">Follow the procedure to enable Lync Server 2013 users for voice mail on a hosted Exchange Unified Messaging (UM) service.</span></span>

<span data-ttu-id="a1b59-105">자세한 내용은 계획 설명서의 [Lync Server 2013에서 호스트 된 Exchange 사용자 관리](lync-server-2013-hosted-exchange-user-management.md) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a1b59-105">For details, see [Hosted Exchange user management in Lync Server 2013](lync-server-2013-hosted-exchange-user-management.md) in the Planning documentation.</span></span>

<span data-ttu-id="a1b59-106">[집합-CsUser](https://docs.microsoft.com/powershell/module/skype/Set-CsUser) cmdlet에 대 한 자세한 내용은 Lync Server 관리 셸 설명서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a1b59-106">For details about the [Set-CsUser](https://docs.microsoft.com/powershell/module/skype/Set-CsUser) cmdlet, see the Lync Server Management Shell documentation.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="a1b59-107">Lync Server 2013 사용자가 호스트 된 음성 메일을 사용 하도록 설정 하기 전에 해당 사용자 계정에 적용 되는 호스팅 음성 메일 정책을 배포 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b59-107">Before a Lync Server 2013 user can be enabled for hosted voice mail, a hosted voice mail policy that applies to their user account must be deployed.</span></span> <span data-ttu-id="a1b59-108">자세한 내용은 <A href="lync-server-2013-hosted-voice-mail-policies.md">Lync Server 2013의 호스팅된 음성 메일 정책을</A>참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a1b59-108">For details, see <A href="lync-server-2013-hosted-voice-mail-policies.md">Hosted voice mail policies in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-enable-users-for-hosted-voice-mail"></a><span data-ttu-id="a1b59-109">사용자가 호스팅되는 음성 메일을 사용할 수 있도록 설정</span><span class="sxs-lookup"><span data-stu-id="a1b59-109">To enable users for hosted voice mail</span></span>

1.  <span data-ttu-id="a1b59-110">Lync Server 관리 셸 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **lync server management shell**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b59-110">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="a1b59-111">Set-CsUser cmdlet을 실행 하 여 호스팅된 음성 메일에 대 한 사용자 계정을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b59-111">Run the Set-CsUser cmdlet to configure the user account for hosted voice mail.</span></span> <span data-ttu-id="a1b59-112">예를 들어 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b59-112">For example, run:</span></span>
    
        Set-CsUser -HostedVoiceMail $True -Identity "contoso\kenmyer"
    
    <span data-ttu-id="a1b59-113">위의 예는 다음 매개 변수를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b59-113">The preceding example sets the following parameters:</span></span>
    
      - <span data-ttu-id="a1b59-114">**HostedVoiceMail** 를 사용 하면 사용자의 음성 메일 통화를 호스트 된 Exchange UM로 라우팅할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1b59-114">**HostedVoiceMail** enables a user’s voice mail calls to be routed to hosted Exchange UM.</span></span> <span data-ttu-id="a1b59-115">또한 Microsoft Lync 2013에 "음성 메일 전화 걸기" 표시기가 표시 되도록 신호를 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="a1b59-115">It also signals Microsoft Lync 2013 to light up the “call voice mail” indicator.</span></span>
    
      - <span data-ttu-id="a1b59-116">**Id** 수정할 사용자 계정을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b59-116">**Identity** specifies the user account to be modified.</span></span> <span data-ttu-id="a1b59-117">Id 값은 다음 형식 중 하나를 사용 하 여 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1b59-117">The Identity value can be specified using any of the following formats:</span></span>
        
          - <span data-ttu-id="a1b59-118">사용자의 SIP 주소</span><span class="sxs-lookup"><span data-stu-id="a1b59-118">The user's SIP address</span></span>
        
          - <span data-ttu-id="a1b59-119">사용자의 Active Directory 사용자-주 이름</span><span class="sxs-lookup"><span data-stu-id="a1b59-119">The user's Active Directory User-Principal-Name</span></span>
        
          - <span data-ttu-id="a1b59-120">사용자의 도메인\\로그온 이름 (예: contoso\\kenmyer)</span><span class="sxs-lookup"><span data-stu-id="a1b59-120">The user's domain\\logon name (for example, contoso\\kenmyer)</span></span>
        
          - <span data-ttu-id="a1b59-121">사용자의 Active Directory 도메인 서비스 표시 이름 (예:: 진구 Myer)</span><span class="sxs-lookup"><span data-stu-id="a1b59-121">The user's Active Directory Domain Services Display-Name (for example, Ken Myer).</span></span> <span data-ttu-id="a1b59-122">표시 이름을 Id 값으로 사용 하는 경우 별표 (\*) 와일드 카드 문자를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1b59-122">If using the Display-Name as the Identity value, you can use the asterisk (\*) wildcard character.</span></span> <span data-ttu-id="a1b59-123">예를 들어 Id "\* smith"는 "smith" 문자열 값으로 끝나는 표시 이름을 가진 모든 사용자를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b59-123">For example, the Identity "\* Smith" returns all the users who have a Display-Name that ends with the string value "Smith".</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="a1b59-124">SAM-계정 이름이 포리스트에서 고유 하지 않아도 되므로 사용자의 Active Directory SAM-계정 이름을 Id 값으로 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a1b59-124">The user’s Active Directory SAM-Account-Name cannot be used as the Identity value because the SAM-Account-Name is not necessarily unique in the forest.</span></span>

        
        </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

