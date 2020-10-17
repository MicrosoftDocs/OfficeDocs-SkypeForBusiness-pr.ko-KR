---
title: 'Lync Server 2013: 호스팅된 Exchange 사용자 관리'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Hosted Exchange user management
ms:assetid: e8723af5-0604-4d7d-bad2-463a9832efb4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399037(v=OCS.15)
ms:contentKeyID: 48185887
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e4a54c4a7a3833fdd31999d7613659f9a35f9732
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48504205"
---
# <a name="hosted-exchange-user-management-in-lync-server-2013"></a><span data-ttu-id="e8278-102">Lync Server 2013의 호스팅된 Exchange 사용자 관리</span><span class="sxs-lookup"><span data-stu-id="e8278-102">Hosted Exchange user management in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e8278-103">_**마지막으로 수정 된 항목:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="e8278-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="e8278-104">사서함이 호스팅된 Exchange 서비스에 있는 Lync Server 2013 사용자에 게 음성 메일 서비스를 제공 하려면 호스트 된 음성 메일에 대해 사용자 계정을 사용 하도록 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8278-104">To provide voice mail services for Lync Server 2013 users whose mailboxes are located on a hosted Exchange service, you must enable their user accounts for hosted voice mail.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e8278-105">Lync Server 2013 사용자를 호스팅된 음성 메일에 대해 사용 하도록 설정 하기 전에 해당 사용자 계정에 적용 되는 호스팅된 음성 메일 정책을 배포 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8278-105">Before a Lync Server 2013 user can be enabled for hosted voice mail, a hosted voice mail policy that applies to the corresponding user account must be deployed.</span></span> <span data-ttu-id="e8278-106">정책이 사용 하도록 설정할 사용자에 게 적용 되는 한, 범위에서 전역, 사이트 또는 사용자별가 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e8278-106">The policy can be global, site, or per-user in scope, as long as it applies to the user whom you want to enable.</span></span> <span data-ttu-id="e8278-107">자세한 내용은 <A href="lync-server-2013-hosted-voice-mail-policies.md">Lync Server 2013에서 호스팅된 음성 메일 정책</A>를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="e8278-107">For details, see <A href="lync-server-2013-hosted-voice-mail-policies.md">Hosted voice mail policies in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="the-msexchucvoicemailsettings-attribute"></a><span data-ttu-id="e8278-108">MsExchUCVoiceMailSettings 특성</span><span class="sxs-lookup"><span data-stu-id="e8278-108">The msExchUCVoiceMailSettings Attribute</span></span>

<span data-ttu-id="e8278-109">Lync Server 2013에서는 Lync Server 2013 Active Directory 스키마 준비의 일부로 만들어지는 **msExchUCVoiceMailSettings**라는 새로운 사용자 특성을 소개 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8278-109">Lync Server 2013 introduces a new user attribute named **msExchUCVoiceMailSettings**, which is created as part of the Lync Server 2013 Active Directory schema preparation.</span></span> <span data-ttu-id="e8278-110">이 다중값 특성은 Lync Server 2013 및 호스팅된 Exchange 서비스에서 공유 하는 음성 메일 설정을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8278-110">This multivalued attribute holds voice mail settings that are shared by Lync Server 2013 and the hosted Exchange service.</span></span>

<span data-ttu-id="e8278-111">호스트 된 Exchange 서비스는 경우에 따라 Exchange UM을 사용 하도록 설정 하는 프로세스에서 또는 호스트 된 Exchange 서버로 사서함을 전송 하는 프로세스 중에 msExchUCVoiceMailSettings 특성의 값을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e8278-111">The hosted Exchange service may in some cases set the value of the msExchUCVoiceMailSettings attribute in the process of enabling Exchange UM, or during the process of transferring mailboxes to a hosted Exchange Server.</span></span> <span data-ttu-id="e8278-112">이 특성을 Exchange에서 설정 하지 않은 경우 Lync Server 2013 관리자는이 항목 앞부분에 설명 된 대로 Set-CsUser cmdlet을 실행 하 여 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8278-112">If this attribute is not set by Exchange, the Lync Server 2013 administrator must set it by running the Set-CsUser cmdlet, as described earlier in this topic.</span></span>

<span data-ttu-id="e8278-113">특성의 키/값 쌍 및 해당 작성자가 다음 표에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e8278-113">The attribute’s key/value pairs and their authors are shown in the following table.</span></span>

### <a name="the-msexchucvoicemailsettings-attribute-keyvalue-pairs"></a><span data-ttu-id="e8278-114">MsExchUCVoiceMailSettings 특성 키/값 쌍</span><span class="sxs-lookup"><span data-stu-id="e8278-114">The msExchUCVoiceMailSettings Attribute Key/Value Pairs</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e8278-115">값</span><span class="sxs-lookup"><span data-stu-id="e8278-115">Value</span></span></th>
<th><span data-ttu-id="e8278-116">만든 이</span><span class="sxs-lookup"><span data-stu-id="e8278-116">Author</span></span></th>
<th><span data-ttu-id="e8278-117">의미</span><span class="sxs-lookup"><span data-stu-id="e8278-117">Meaning</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e8278-118">ExchangeHostedVoiceMail = 1</span><span class="sxs-lookup"><span data-stu-id="e8278-118">ExchangeHostedVoiceMail=1</span></span></p></td>
<td><p><span data-ttu-id="e8278-119">Exchange</span><span class="sxs-lookup"><span data-stu-id="e8278-119">Exchange</span></span></p></td>
<td><p><span data-ttu-id="e8278-120">사용자가 Exchange Server에의 한 호스팅된 UM 액세스를 사용할 수 있도록 설정 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="e8278-120">User has been enabled for hosted UM access by Exchange Server.</span></span> <span data-ttu-id="e8278-121">Exchange UM 라우팅 응용 프로그램은 사용자의 호스팅된 음성 메일 정책에서 라우팅 세부 정보를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8278-121">The Exchange UM Routing application will check the user’s hosted voice mail policy for routing details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8278-122">ExchangeHostedVoiceMail = 0</span><span class="sxs-lookup"><span data-stu-id="e8278-122">ExchangeHostedVoiceMail=0</span></span></p></td>
<td><p><span data-ttu-id="e8278-123">Exchange</span><span class="sxs-lookup"><span data-stu-id="e8278-123">Exchange</span></span></p></td>
<td><p><span data-ttu-id="e8278-124">사용자가 Exchange Server의 호스팅된 UM 액세스를 사용 하지 않도록 설정 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="e8278-124">User has been disabled for hosted UM access by Exchange Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8278-125">CsHostedVoiceMail 사서함 = 1</span><span class="sxs-lookup"><span data-stu-id="e8278-125">CsHostedVoiceMail=1</span></span></p></td>
<td><p><span data-ttu-id="e8278-126">Lync Server</span><span class="sxs-lookup"><span data-stu-id="e8278-126">Lync Server</span></span></p></td>
<td><p><span data-ttu-id="e8278-127">Lync Server 2013에서 사용자가 호스팅된 UM 액세스를 사용 하도록 설정 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="e8278-127">User has been enabled for hosted UM access by Lync Server 2013.</span></span> <span data-ttu-id="e8278-128">Lync Server 2013 ExUM 라우팅 응용 프로그램은 라우팅 세부 정보에 대해 사용자의 호스팅된 음성 메일 정책을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8278-128">The Lync Server 2013 ExUM Routing application will check the user’s hosted voice mail policy for routing details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8278-129">CsHostedVoiceMail 사서함 = 0</span><span class="sxs-lookup"><span data-stu-id="e8278-129">CsHostedVoiceMail=0</span></span></p></td>
<td><p><span data-ttu-id="e8278-130">Lync Server</span><span class="sxs-lookup"><span data-stu-id="e8278-130">Lync Server</span></span></p></td>
<td><p><span data-ttu-id="e8278-131">Lync Server 2013에서 사용자가 호스팅된 UM 액세스를 사용 하지 않도록 설정 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="e8278-131">User has been disabled for hosted UM access by Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="e8278-132">특성에 이미 Lync Server 2013 키/값 쌍 (CSHostedVoiceMail 메일 = 0 또는 CSHostedVoiceMail 메일 = 1)이 아닌 값이 있는 경우에는 다른 응용 프로그램에서 해당 특성을 관리할 수 있음을 알리는 경고가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e8278-132">If the attribute already has values other than one of the Lync Server 2013 key/value pairs (CSHostedVoiceMail=0 or CSHostedVoiceMail=1), a warning will indicate that the attribute may be managed by a different application.</span></span> <span data-ttu-id="e8278-133">예를 들어 키/값 쌍 ExchangeHostedVoiceMail = 0 또는 ExchangeHostedVoiceMail = 1이 이미 있는 경우 경고가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e8278-133">For example, a warning is displayed if the key/value pair ExchangeHostedVoiceMail=0 or ExchangeHostedVoiceMail=1 is already present.</span></span> <span data-ttu-id="e8278-134">이 경우 Active Directory를 편집 하 여 값을 변경 하거나 다음 cmdlet을 실행 하 여 값을 null로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e8278-134">In that case, you can change the value by editing it the Active Directory, or run the following cmdlet to set the value to null:</span></span><BR><span data-ttu-id="e8278-135">Set-CsUser-id 사용자-HostedVoicemail $null</span><span class="sxs-lookup"><span data-stu-id="e8278-135">Set-CsUser –identity user –HostedVoicemail $null</span></span>



</div>

</div>

<div>

## <a name="enabling-users-for-hosted-voice-mail"></a><span data-ttu-id="e8278-136">사용자가 호스팅된 음성 메일을 사용할 수 있도록 설정</span><span class="sxs-lookup"><span data-stu-id="e8278-136">Enabling Users for Hosted Voice Mail</span></span>

<span data-ttu-id="e8278-137">사용자의 음성 메일 통화를 호스팅된 Exchange UM으로 라우팅되도록 설정 하려면 Set-CsUser cmdlet을 실행 하 여 *HostedVoiceMail* 매개 변수의 값을 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8278-137">To enable a user’s voice mail calls to be routed to hosted Exchange UM, you must run the Set-CsUser cmdlet to set the value of the *HostedVoiceMail* parameter.</span></span> <span data-ttu-id="e8278-138">이 매개 변수는 Lync Server 2013에 "음성 메일 통화" 표시기를 밝게 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8278-138">This parameter also signals Lync Server 2013 to light up the “call voice mail” indicator.</span></span>

  - <span data-ttu-id="e8278-139">다음 예에서는 호스트 된 음성 메일에 대해 Pilar Ackerman의 사용자 계정을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8278-139">The following example enables Pilar Ackerman’s user account for hosted voice mail:</span></span>
    
        Set-CsUser -Identity "Pilar Ackerman" -HostedVoiceMail $True
    
    <span data-ttu-id="e8278-140">이 cmdlet은이 사용자에 게 호스팅된 음성 메일 정책 (전역, 사이트 수준 또는 사용자 단위)이 적용 되는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8278-140">The cmdlet verifies that a hosted voice mail policy (global, site-level or per-user) applies to this user.</span></span> <span data-ttu-id="e8278-141">정책이 적용 되지 않으면 cmdlet이 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8278-141">If no policy applies, the cmdlet fails.</span></span>

  - <span data-ttu-id="e8278-142">다음 예에서는 호스트 된 음성 메일에 대해 Pilar Ackerman의 사용자 계정을 사용 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8278-142">The following example disables Pilar Ackerman’s user account for hosted voice mail:</span></span>
    
        Set-CsUser -Identity "Pilar Ackerman" -HostedVoiceMail $False
    
    <span data-ttu-id="e8278-143">이 cmdlet은이 사용자에 게 호스트 된 음성 메일 정책 (전역, 사이트 수준 또는 사용자 단위)이 적용 되지 않음을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8278-143">The cmdlet verifies that no hosted voice mail policy (global, site-level or per-user) applies to this user.</span></span> <span data-ttu-id="e8278-144">정책이 적용 되 면 cmdlet이 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8278-144">If a policy does apply, the cmdlet fails.</span></span>

<span data-ttu-id="e8278-145">Set-CsUser cmdlet을 사용 하는 방법에 대 한 자세한 내용은 Lync Server 관리 셸 설명서를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="e8278-145">For details about using the Set-CsUser cmdlet, see the Lync Server Management Shell documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

