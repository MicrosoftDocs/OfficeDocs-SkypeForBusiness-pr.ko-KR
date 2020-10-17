---
title: 'Lync Server 2013: 통화 대기 설정 구성'
description: 'Lync Server 2013: 통화 대기 설정을 구성 합니다.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure Call Park settings
ms:assetid: 3bed9d09-8363-4fff-a220-f0f6d3a81241
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425886(v=OCS.15)
ms:contentKeyID: 48183922
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e8862208a68c89151096349508a4c849a5649b70
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48546644"
---
# <a name="configure-call-park-settings-in-lync-server-2013"></a><span data-ttu-id="ad959-103">Lync Server 2013의 통화 대기 설정 구성</span><span class="sxs-lookup"><span data-stu-id="ad959-103">Configure Call Park settings in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ad959-104">_**마지막으로 수정 된 항목:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="ad959-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="ad959-105">기본 통화 대기 설정을 사용 하지 않으려면 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad959-105">If you don't want to use default Call Park settings, you can customize them.</span></span> <span data-ttu-id="ad959-106">통화 대기 응용 프로그램을 설치할 때 전역 설정은 기본적으로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ad959-106">When you install the Call Park application, global settings are configured by default.</span></span> <span data-ttu-id="ad959-107">전역 설정을 수정할 수 있으며 사이트별 설정을 지정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad959-107">You can modify the global settings, and you can also specify site-specific settings.</span></span> <span data-ttu-id="ad959-108">새 사이트별 설정을 만들려면 **New-CsCpsConfiguration** cmdlet을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ad959-108">Use the **New-CsCpsConfiguration** cmdlet to create new site-specific settings.</span></span> <span data-ttu-id="ad959-109">기존 설정을 수정하려면 **Set-CsCpsConfiguration** cmdlet을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ad959-109">Use the **Set-CsCpsConfiguration** cmdlet to modify existing settings.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ad959-110">대기된 통화의 시간이 초과되고 되걸기가 실패하는 경우 최소한 대체 대상에서 사용할 <STRONG>OnTimeoutURI</STRONG> 옵션을 구성하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="ad959-110">At a minimum, we recommend that you configure the <STRONG>OnTimeoutURI</STRONG> option for the fallback destination to use when a parked call times out and ringback fails.</span></span>



</div>

<span data-ttu-id="ad959-111">**New-CsCpsConfiguration** cmdlet 또는 **Set-CsCpsConfiguration** cmdlet을 사용하여 다음 설정 중 원하는 항목을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="ad959-111">Use **New-CsCpsConfiguration** cmdlet or the **Set-CsCpsConfiguration** cmdlet to configure any of the following settings:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ad959-112">옵션</span><span class="sxs-lookup"><span data-stu-id="ad959-112">This option:</span></span></th>
<th><span data-ttu-id="ad959-113">지정 내용</span><span class="sxs-lookup"><span data-stu-id="ad959-113">Specifies this:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ad959-114"><strong>CallPickupTimeoutThreshold</strong></span><span class="sxs-lookup"><span data-stu-id="ad959-114"><strong>CallPickupTimeoutThreshold</strong></span></span></p></td>
<td><p><span data-ttu-id="ad959-115">전화를 받았던 전화기에 벨이 다시 울릴 때까지 통화를 대기하고 있는 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="ad959-115">The amount of time that elapses after a call has been parked before it rings back to the phone where the call was answered.</span></span></p>
<p><span data-ttu-id="ad959-p102">hh:mm:ss 형식으로 시간, 분 및 초를 지정하여 값을 입력해야 합니다. 최소값은 10초이고 최대값은 10분입니다. 기본값은 00:01:30입니다.</span><span class="sxs-lookup"><span data-stu-id="ad959-p102">The value must be entered in the format hh:mm:ss to specify the hours, minutes, and seconds. The minimum value is 10 seconds, and the maximum value is 10 minutes. The default is 00:01:30.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ad959-119"><strong>Enablemusiconhold-</strong></span><span class="sxs-lookup"><span data-stu-id="ad959-119"><strong>EnableMusicOnHold</strong></span></span></p></td>
<td><p><span data-ttu-id="ad959-120">통화를 대기하는 동안 전화를 건 사람에게 음악이 재생되는지 여부입니다.</span><span class="sxs-lookup"><span data-stu-id="ad959-120">Whether music plays for a caller while a call is parked.</span></span></p>
<p><span data-ttu-id="ad959-p103">값은 True 또는 False이고, 기본값은 True입니다.</span><span class="sxs-lookup"><span data-stu-id="ad959-p103">Values are True or False. The default is True.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ad959-123"><strong>MaxCallPickupAttempts</strong></span><span class="sxs-lookup"><span data-stu-id="ad959-123"><strong>MaxCallPickupAttempts</strong></span></span></p></td>
<td><p><span data-ttu-id="ad959-p104">대기된 통화를 <strong>OnTimeoutURI</strong>에 대해 지정된 대체 URI(Uniform Resource Identifier)에 전달할 때까지 해당 통화가 전화기에서 다시 울리는 횟수입니다. 기본값은 1입니다.</span><span class="sxs-lookup"><span data-stu-id="ad959-p104">The number of times a parked call rings back to the answering phone before it is forwarded to the fallback Uniform Resource Identifier (URI) that is specified for <strong>OnTimeoutURI</strong>. The default is 1.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ad959-126"><strong>사용할 ontimeouturi</strong></span><span class="sxs-lookup"><span data-stu-id="ad959-126"><strong>OnTimeoutURI</strong></span></span></p></td>
<td><p><span data-ttu-id="ad959-127"><strong>MaxCallPickupAttempts</strong>가 초과될 때 응답하지 않은 대기된 통화를 경로 지정할 사용자 또는 응답 그룹의 SIP 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="ad959-127">The SIP address of the user or response group to which an unanswered parked call is routed when <strong>MaxCallPickupAttempts</strong> is exceeded.</span></span></p>
<p><span data-ttu-id="ad959-p105">값은 문자열 sip:로 시작하는 SIP URI여야 합니다(예: sip:bob@contoso.com). 기본적으로는 전달 주소가 지정되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ad959-p105">Value must be a SIP URI beginning with the string sip:. For example, sip:bob@contoso.com. The default is no forwarding address.</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="to-configure-call-park-settings"></a><span data-ttu-id="ad959-131">통화 대기 설정을 구성 하려면</span><span class="sxs-lookup"><span data-stu-id="ad959-131">To configure Call Park settings</span></span>

1.  <span data-ttu-id="ad959-132">Lync server 관리 셸이 RTCUniversalServerAdmins 그룹의 구성원으로 설치 되어 있거나 [Lync server 2013의 설치 권한 위임](lync-server-2013-delegate-setup-permissions.md)에 설명 된 대로 필요한 사용자 권한으로 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad959-132">Log on to the computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="ad959-133">**시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="ad959-133">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="ad959-134">을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="ad959-134">Run:</span></span>
    
        New-CsCpsConfiguration -Identity site:<sitename to apply settings> [-CallPickupTimeoutThreshold <hh:mm:ss>] -[EnableMusicOnHold <$true | $false>] [-MaxCallPickupAttempts <number of rings>] [-OnTimeoutURI sip:<sip URI for routing unanswered call>]
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="ad959-135"><STRONG>Get-CsSite</STRONG> cmdlet을 사용하여 사이트를 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="ad959-135">Use the <STRONG>Get-CsSite</STRONG> cmdlet to identify the site.</span></span> <span data-ttu-id="ad959-136">자세한 내용은 Lync Server Management Shell 설명서를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="ad959-136">For details, see Lync Server Management Shell documentation.</span></span>

    
    </div>
    
    <span data-ttu-id="ad959-137">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ad959-137">For example:</span></span>
    
        New-CsCpsConfiguration -Identity site:Redmond1 -CallPickupTimeoutThreshold 00:01:00 -EnableMusicOnHold $false -MaxCallPickupAttempts 2 -OnTimeoutURI sip:bob@contoso.com

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="ad959-138">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ad959-138">See Also</span></span>


[<span data-ttu-id="ad959-139">Lync Server 2013에서 통화 대기 음악 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="ad959-139">Customize Call Park music on hold in Lync Server 2013</span></span>](lync-server-2013-customize-call-park-music-on-hold.md)  


[<span data-ttu-id="ad959-140">New-cscpsconfiguration</span><span class="sxs-lookup"><span data-stu-id="ad959-140">New-CsCpsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsCpsConfiguration)  
[<span data-ttu-id="ad959-141">New-cscpsconfiguration</span><span class="sxs-lookup"><span data-stu-id="ad959-141">Set-CsCpsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsCpsConfiguration)  
[<span data-ttu-id="ad959-142">Get-CsSite</span><span class="sxs-lookup"><span data-stu-id="ad959-142">Get-CsSite</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsSite)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

