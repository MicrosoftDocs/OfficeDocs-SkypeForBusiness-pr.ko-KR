---
title: 'Lync Server 2013: 사용자가 호스팅된 음성 메일을 사용할 수 있도록 설정'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable users for hosted voice mail
ms:assetid: fa559f8f-ef99-43a1-b580-9e998b95efb8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413062(v=OCS.15)
ms:contentKeyID: 48185919
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e7287f31a4dc0e43b0108ce666e9c65f51f75f2d
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42046661"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-users-for-hosted-voice-mail-in-lync-server-2013"></a><span data-ttu-id="ca8eb-102">Lync Server 2013에서 호스팅된 음성 메일에 대해 사용자를 사용 하도록 설정</span><span class="sxs-lookup"><span data-stu-id="ca8eb-102">Enable users for hosted voice mail in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ca8eb-103">_**마지막으로 수정 된 항목:** 2012-09-24_</span><span class="sxs-lookup"><span data-stu-id="ca8eb-103">_**Topic Last Modified:** 2012-09-24_</span></span>

<span data-ttu-id="ca8eb-104">호스팅된 Exchange UM (통합 메시징) 서비스에서 Lync Server 2013 사용자가 음성 메일을 사용할 수 있도록 설정 하는 절차를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca8eb-104">Follow the procedure to enable Lync Server 2013 users for voice mail on a hosted Exchange Unified Messaging (UM) service.</span></span>

<span data-ttu-id="ca8eb-105">자세한 내용은 계획 설명서의 [Lync Server 2013에서 호스팅된 Exchange 사용자 관리](lync-server-2013-hosted-exchange-user-management.md) 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="ca8eb-105">For details, see [Hosted Exchange user management in Lync Server 2013](lync-server-2013-hosted-exchange-user-management.md) in the Planning documentation.</span></span>

<span data-ttu-id="ca8eb-106">[CsUser](https://docs.microsoft.com/powershell/module/skype/Set-CsUser) cmdlet에 대 한 자세한 내용은 Lync Server 관리 셸 설명서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ca8eb-106">For details about the [Set-CsUser](https://docs.microsoft.com/powershell/module/skype/Set-CsUser) cmdlet, see the Lync Server Management Shell documentation.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="ca8eb-107">Lync Server 2013 사용자를 호스팅된 음성 메일에 대해 사용 하도록 설정 하기 전에 해당 사용자 계정에 적용 되는 호스팅된 음성 메일 정책을 배포 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca8eb-107">Before a Lync Server 2013 user can be enabled for hosted voice mail, a hosted voice mail policy that applies to their user account must be deployed.</span></span> <span data-ttu-id="ca8eb-108">자세한 내용은 <A href="lync-server-2013-hosted-voice-mail-policies.md">Lync Server 2013에서 호스팅된 음성 메일 정책</A>를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="ca8eb-108">For details, see <A href="lync-server-2013-hosted-voice-mail-policies.md">Hosted voice mail policies in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-enable-users-for-hosted-voice-mail"></a><span data-ttu-id="ca8eb-109">사용자가 호스팅된 음성 메일을 사용할 수 있도록 설정하려면</span><span class="sxs-lookup"><span data-stu-id="ca8eb-109">To enable users for hosted voice mail</span></span>

1.  <span data-ttu-id="ca8eb-110">**시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="ca8eb-110">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="ca8eb-p102">Set-CsUser cmdlet를 실행하여 호스팅된 음성 메일에 대한 사용자 계정을 구성합니다. 예를 들어 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="ca8eb-p102">Run the Set-CsUser cmdlet to configure the user account for hosted voice mail. For example, run:</span></span>
    
        Set-CsUser -HostedVoiceMail $True -Identity "contoso\kenmyer"
    
    <span data-ttu-id="ca8eb-113">위의 예는 다음 매개 변수를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="ca8eb-113">The preceding example sets the following parameters:</span></span>
    
      - <span data-ttu-id="ca8eb-114">**HostedVoiceMail**은 사용자의 음성 사서함 통화를 호스팅된 Exchange UM으로 라우팅할 수 있도록 해줍니다.</span><span class="sxs-lookup"><span data-stu-id="ca8eb-114">**HostedVoiceMail** enables a user’s voice mail calls to be routed to hosted Exchange UM.</span></span> <span data-ttu-id="ca8eb-115">또한 Microsoft Lync 2013에서 "음성 메일 통화" 표시기를 밝게 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca8eb-115">It also signals Microsoft Lync 2013 to light up the “call voice mail” indicator.</span></span>
    
      - <span data-ttu-id="ca8eb-p104">**Identity**는 수정할 사용자 계정을 지정합니다. Identity 값은 다음 형식 중 하나를 사용하여 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca8eb-p104">**Identity** specifies the user account to be modified. The Identity value can be specified using any of the following formats:</span></span>
        
          - <span data-ttu-id="ca8eb-118">사용자의 SIP 주소</span><span class="sxs-lookup"><span data-stu-id="ca8eb-118">The user's SIP address</span></span>
        
          - <span data-ttu-id="ca8eb-119">사용자의 Active Directory 사용자 계정 이름</span><span class="sxs-lookup"><span data-stu-id="ca8eb-119">The user's Active Directory User-Principal-Name</span></span>
        
          - <span data-ttu-id="ca8eb-120">사용자의 도메인\\로그온 이름 (예: contoso\\kenmyer)</span><span class="sxs-lookup"><span data-stu-id="ca8eb-120">The user's domain\\logon name (for example, contoso\\kenmyer)</span></span>
        
          - <span data-ttu-id="ca8eb-121">사용자의 Active Directory 도메인 서비스 표시 이름(예: Ken Myer).</span><span class="sxs-lookup"><span data-stu-id="ca8eb-121">The user's Active Directory Domain Services Display-Name (for example, Ken Myer).</span></span> <span data-ttu-id="ca8eb-122">표시 이름을 Id 값으로 사용 하는 경우 별표 (\*) 와일드 카드 문자를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca8eb-122">If using the Display-Name as the Identity value, you can use the asterisk (\*) wildcard character.</span></span> <span data-ttu-id="ca8eb-123">예를 들어 Id "\* smith"는 문자열 값 "smith"로 끝나는 표시 이름을 가진 모든 사용자를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca8eb-123">For example, the Identity "\* Smith" returns all the users who have a Display-Name that ends with the string value "Smith".</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="ca8eb-124">SAM 계정 이름은 포리스트에서 고유하지 않아도 되므로 사용자의 Active Directory SAM 계정 이름을 Identity 값으로 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ca8eb-124">The user’s Active Directory SAM-Account-Name cannot be used as the Identity value because the SAM-Account-Name is not necessarily unique in the forest.</span></span>

        
        </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

