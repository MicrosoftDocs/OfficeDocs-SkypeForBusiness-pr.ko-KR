---
title: 'Lync Server 2013: 음성 라우팅 cmdlet'
description: 'Lync Server 2013: 음성 라우팅 cmdlet'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Voice routing cmdlets
ms:assetid: 8f05b25e-cc62-4d85-a5d8-4ed56f28dfbf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg416494(v=OCS.15)
ms:contentKeyID: 48184821
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b895eb84bccea6fcb014e61d5609b45c8c14d4cd
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48554074"
---
# <a name="voice-routing-cmdlets-in-lync-server-2013"></a><span data-ttu-id="49a55-103">Lync Server 2013의 음성 라우팅 cmdlet</span><span class="sxs-lookup"><span data-stu-id="49a55-103">Voice routing cmdlets in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="49a55-104">_**마지막으로 수정 된 항목:** 2012-06-26_</span><span class="sxs-lookup"><span data-stu-id="49a55-104">_**Topic Last Modified:** 2012-06-26_</span></span>

<span data-ttu-id="49a55-105">음성 경로에는 Microsoft Lync Server 2013에서 PSTN (공중 전화망) 또는 PBX (private branch exchange)에서 Enterprise Voice 사용자 로부터 전화 번호로 통화를 라우팅하는 방법을 설명 하는 지침이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="49a55-105">Voice routes contain instructions that tell Microsoft Lync Server 2013 how to route calls from Enterprise Voice users to phone numbers on the public switched telephone network (PSTN) or a private branch exchange (PBX).</span></span>

<div>

## <a name="voice-routing-cmdlets"></a><span data-ttu-id="49a55-106">음성 라우팅 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="49a55-106">Voice Routing Cmdlets</span></span>

<span data-ttu-id="49a55-107">음성 경로를 구성하려면 다음 cmdlet를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="49a55-107">Use the following cmdlets to configure voice routes.</span></span>

<span data-ttu-id="49a55-108">**음성 라우팅**</span><span class="sxs-lookup"><span data-stu-id="49a55-108">**Voice Routing**</span></span>

  - <span></span>  
    <span data-ttu-id="49a55-109">[Get-CsRoutingConfiguration](https://technet.microsoft.com/library/Gg425851(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="49a55-109">[Get-CsRoutingConfiguration](https://technet.microsoft.com/library/Gg425851(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="49a55-110">[새-CsRoutingConfiguration](https://technet.microsoft.com/library/Gg399056(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="49a55-110">[New-CsRoutingConfiguration](https://technet.microsoft.com/library/Gg399056(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="49a55-111">[제거-CsRoutingConfiguration](https://technet.microsoft.com/library/Gg398643(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="49a55-111">[Remove-CsRoutingConfiguration](https://technet.microsoft.com/library/Gg398643(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="49a55-112">[설정-CsRoutingConfiguration](https://technet.microsoft.com/library/Gg412811(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="49a55-112">[Set-CsRoutingConfiguration](https://technet.microsoft.com/library/Gg412811(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="49a55-113">[Get-csvoiceroute](https://technet.microsoft.com/library/Gg425926(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="49a55-113">[Get-CsVoiceRoute](https://technet.microsoft.com/library/Gg425926(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="49a55-114">[Get-csvoiceroute](https://technet.microsoft.com/library/Gg398197(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="49a55-114">[New-CsVoiceRoute](https://technet.microsoft.com/library/Gg398197(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="49a55-115">[Get-csvoiceroute을 제거 합니다.](https://technet.microsoft.com/library/Gg398468(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="49a55-115">[Remove-CsVoiceRoute](https://technet.microsoft.com/library/Gg398468(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="49a55-116">[Get-csvoiceroute](https://technet.microsoft.com/library/Gg412893(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="49a55-116">[Set-CsVoiceRoute](https://technet.microsoft.com/library/Gg412893(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="49a55-117">[Get-csvoiceroute](https://technet.microsoft.com/library/Gg425873(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="49a55-117">[Test-CsVoiceRoute](https://technet.microsoft.com/library/Gg425873(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="49a55-118">[Get-csvoiceroutingpolicy](https://technet.microsoft.com/library/JJ204940(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="49a55-118">[Get-CsVoiceRoutingPolicy](https://technet.microsoft.com/library/JJ204940(v=OCS.15))</span></span>

  - <span data-ttu-id="49a55-119">[Get-csvoiceroutingpolicy](https://technet.microsoft.com/library/JJ205141(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="49a55-119">[Grant-CsVoiceRoutingPolicy](https://technet.microsoft.com/library/JJ205141(v=OCS.15))</span></span>

  - <span data-ttu-id="49a55-120">[Get-csvoiceroutingpolicy](https://technet.microsoft.com/library/JJ205135(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="49a55-120">[New-CsVoiceRoutingPolicy](https://technet.microsoft.com/library/JJ205135(v=OCS.15))</span></span>

  - <span data-ttu-id="49a55-121">[Get-csvoiceroutingpolicy을 제거 합니다.](https://technet.microsoft.com/library/JJ204799(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="49a55-121">[Remove-CsVoiceRoutingPolicy](https://technet.microsoft.com/library/JJ204799(v=OCS.15))</span></span>

  - <span data-ttu-id="49a55-122">[Get-csvoiceroutingpolicy](https://technet.microsoft.com/library/JJ205313(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="49a55-122">[Set-CsVoiceRoutingPolicy](https://technet.microsoft.com/library/JJ205313(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="49a55-123">[G-CsPstnUsage 사용](https://technet.microsoft.com/library/Gg412734(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="49a55-123">[Get-CsPstnUsage](https://technet.microsoft.com/library/Gg412734(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="49a55-124">[설정-CsPstnUsage](https://technet.microsoft.com/library/Gg399069(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="49a55-124">[Set-CsPstnUsage](https://technet.microsoft.com/library/Gg399069(v=OCS.15))</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="49a55-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="49a55-125">See Also</span></span>


[<span data-ttu-id="49a55-126">Lync Server 2013의 Enterprise Voice cmdlet</span><span class="sxs-lookup"><span data-stu-id="49a55-126">Enterprise Voice cmdlets in Lync Server 2013</span></span>](lync-server-2013-enterprise-voice-cmdlets.md)  
[<span data-ttu-id="49a55-127">Lync Server 2013의 PSTN 연결 cmdlet</span><span class="sxs-lookup"><span data-stu-id="49a55-127">PSTN connectivity cmdlets in Lync Server 2013</span></span>](lync-server-2013-pstn-connectivity-cmdlets.md)  


[<span data-ttu-id="49a55-128">Lync Server PowerShell 블로그</span><span class="sxs-lookup"><span data-stu-id="49a55-128">Lync Server PowerShell Blog</span></span>](https://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

