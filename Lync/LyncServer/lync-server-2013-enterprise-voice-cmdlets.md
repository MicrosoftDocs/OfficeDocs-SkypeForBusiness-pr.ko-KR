---
title: 'Lync Server 2013: Enterprise Voice cmdlet'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enterprise Voice cmdlets
ms:assetid: 7d7c6d94-3ead-4d99-95f7-c31b448ab9e2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg415658(v=OCS.15)
ms:contentKeyID: 48184613
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 91f20a5a1df722e92454e0200a0c8174ff37d4dc
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48533205"
---
# <a name="enterprise-voice-cmdlets-in-lync-server-2013"></a><span data-ttu-id="d06bb-102">Lync Server 2013의 Enterprise Voice cmdlet</span><span class="sxs-lookup"><span data-stu-id="d06bb-102">Enterprise Voice cmdlets in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d06bb-103">_**마지막으로 수정 된 항목:** 2014-03-19_</span><span class="sxs-lookup"><span data-stu-id="d06bb-103">_**Topic Last Modified:** 2014-03-19_</span></span>

<span data-ttu-id="d06bb-104">Enterprise Voice는 Microsoft의 VoIP(Voice over IP)에 대한 구현입니다.</span><span class="sxs-lookup"><span data-stu-id="d06bb-104">Enterprise Voice is the Microsoft implementation of Voice over IP (VoIP).</span></span> <span data-ttu-id="d06bb-105">Microsoft Lync Server 2013에서 Enterprise Voice를 관리 하는 데 사용할 수 있는 cmdlet을 사용 하면 다이얼 플랜 (이전의 위치 프로필), 음성 정책, 경로 및 정규화 규칙을 만들고 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d06bb-105">The cmdlets available for managing Enterprise Voice in Microsoft Lync Server 2013 will allow you to create and modify dial plans (formerly known as location profiles), voice policies, routes, and normalization rules.</span></span>

<div>

## <a name="enterprise-voice-cmdlets"></a><span data-ttu-id="d06bb-106">Enterprise Voice Cmdlet</span><span class="sxs-lookup"><span data-stu-id="d06bb-106">Enterprise Voice Cmdlets</span></span>

<span data-ttu-id="d06bb-107">Enterprise Voice에 해당 되는 대부분의 관리 작업은 Lync Server 제어판에서 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d06bb-107">Most management tasks that apply to Enterprise Voice can be performed from the Lync Server Control Panel.</span></span> <span data-ttu-id="d06bb-108">이러한 동일한 작업은 Lync Server 관리 셸 또는 스크립트 내에서 cmdlet을 사용 하 여 수행 하거나 특정 작업을 자동화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d06bb-108">These same tasks can be performed using cmdlets from the Lync Server Management Shell or from within a script, allowing you to automate certain tasks.</span></span> <span data-ttu-id="d06bb-109">다음은 Enterprise Voice 관리와 직접 관련 된 cmdlet 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="d06bb-109">The following is a list of cmdlets that relate directly to managing Enterprise Voice:</span></span>

<span data-ttu-id="d06bb-110">**[Lync Server 2013의 Enterprise Voice cmdlet 문제 해결](lync-server-2013-troubleshooting-enterprise-voice-cmdlets.md)**</span><span class="sxs-lookup"><span data-stu-id="d06bb-110">**[Troubleshooting Enterprise Voice cmdlets in Lync Server 2013](lync-server-2013-troubleshooting-enterprise-voice-cmdlets.md)**</span></span>

  - <span></span>  
    <span data-ttu-id="d06bb-111">[CsVoiceConfiguration](https://technet.microsoft.com/library/Gg398815(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="d06bb-111">[Get-CsVoiceConfiguration](https://technet.microsoft.com/library/Gg398815(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="d06bb-112">[CsVoiceConfiguration을 제거 합니다.](https://technet.microsoft.com/library/Gg398804(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="d06bb-112">[Remove-CsVoiceConfiguration](https://technet.microsoft.com/library/Gg398804(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="d06bb-113">[CsVoiceConfiguration](https://technet.microsoft.com/library/Gg398967(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="d06bb-113">[Set-CsVoiceConfiguration](https://technet.microsoft.com/library/Gg398967(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="d06bb-114">[수정한 구성은 test-csvoicetestconfiguration](https://technet.microsoft.com/library/Gg412957(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="d06bb-114">[Get-CsVoiceTestConfiguration](https://technet.microsoft.com/library/Gg412957(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="d06bb-115">[수정한 구성은 test-csvoicetestconfiguration](https://technet.microsoft.com/library/Gg398961(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="d06bb-115">[New-CsVoiceTestConfiguration](https://technet.microsoft.com/library/Gg398961(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="d06bb-116">[수정한 구성은 test-csvoicetestconfiguration을 제거 합니다.](https://technet.microsoft.com/library/Gg412813(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="d06bb-116">[Remove-CsVoiceTestConfiguration](https://technet.microsoft.com/library/Gg412813(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="d06bb-117">[수정한 구성은 test-csvoicetestconfiguration](https://technet.microsoft.com/library/Gg398614(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="d06bb-117">[Set-CsVoiceTestConfiguration](https://technet.microsoft.com/library/Gg398614(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="d06bb-118">[수정한 구성은 test-csvoicetestconfiguration](https://technet.microsoft.com/library/Gg398260(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="d06bb-118">[Test-CsVoiceTestConfiguration](https://technet.microsoft.com/library/Gg398260(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="d06bb-119">[테스트-CsDialPlan 플랜](https://technet.microsoft.com/library/Gg399024(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="d06bb-119">[Test-CsDialPlan](https://technet.microsoft.com/library/Gg399024(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="d06bb-120">[Get-csvoicenormalizationrule](https://technet.microsoft.com/library/Gg399003(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="d06bb-120">[Test-CsVoiceNormalizationRule](https://technet.microsoft.com/library/Gg399003(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="d06bb-121">[Set-csvoicepolicy](https://technet.microsoft.com/library/Gg398310(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="d06bb-121">[Test-CsVoicePolicy](https://technet.microsoft.com/library/Gg398310(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="d06bb-122">[Get-csvoiceroute](https://technet.microsoft.com/library/Gg425873(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="d06bb-122">[Test-CsVoiceRoute](https://technet.microsoft.com/library/Gg425873(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="d06bb-123">[CsVoiceUser](https://technet.microsoft.com/library/Gg413013(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="d06bb-123">[Test-CsVoiceUser](https://technet.microsoft.com/library/Gg413013(v=OCS.15))</span></span>

<span data-ttu-id="d06bb-124">**[Lync Server 2013의 음성 정규화 규칙 cmdlet](lync-server-2013-voice-normalization-rules-cmdlets.md)**</span><span class="sxs-lookup"><span data-stu-id="d06bb-124">**[Voice normalization rules cmdlets in Lync Server 2013](lync-server-2013-voice-normalization-rules-cmdlets.md)**</span></span>

  - <span></span>  
    <span data-ttu-id="d06bb-125">[Get-csvoicenormalizationrule](https://technet.microsoft.com/library/Gg398393(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="d06bb-125">[Get-CsVoiceNormalizationRule](https://technet.microsoft.com/library/Gg398393(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="d06bb-126">[Get-csvoicenormalizationrule](https://technet.microsoft.com/library/Gg398240(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="d06bb-126">[New-CsVoiceNormalizationRule](https://technet.microsoft.com/library/Gg398240(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="d06bb-127">[Get-csvoicenormalizationrule을 제거 합니다.](https://technet.microsoft.com/library/Gg398501(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="d06bb-127">[Remove-CsVoiceNormalizationRule](https://technet.microsoft.com/library/Gg398501(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="d06bb-128">[Get-csvoicenormalizationrule](https://technet.microsoft.com/library/Gg398491(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="d06bb-128">[Set-CsVoiceNormalizationRule](https://technet.microsoft.com/library/Gg398491(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="d06bb-129">[Get-csvoicenormalizationrule](https://technet.microsoft.com/library/Gg399003(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="d06bb-129">[Test-CsVoiceNormalizationRule](https://technet.microsoft.com/library/Gg399003(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="d06bb-130">[CsVoiceRegex](https://technet.microsoft.com/library/Gg412751(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="d06bb-130">[New-CsVoiceRegex](https://technet.microsoft.com/library/Gg412751(v=OCS.15))</span></span>

<span data-ttu-id="d06bb-131">**[Lync Server 2013의 음성 정책 cmdlet](lync-server-2013-voice-policy-cmdlets.md)**</span><span class="sxs-lookup"><span data-stu-id="d06bb-131">**[Voice policy cmdlets in Lync Server 2013](lync-server-2013-voice-policy-cmdlets.md)**</span></span>

  - <span></span>  
    <span data-ttu-id="d06bb-132">[Get-CsDialPlan 플랜](https://technet.microsoft.com/library/Gg413043(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="d06bb-132">[Get-CsDialPlan](https://technet.microsoft.com/library/Gg413043(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="d06bb-133">[부여-CsDialPlan 플랜](https://technet.microsoft.com/library/Gg398547(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="d06bb-133">[Grant-CsDialPlan](https://technet.microsoft.com/library/Gg398547(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="d06bb-134">[새 CsDialPlan 플랜](https://technet.microsoft.com/library/Gg425860(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="d06bb-134">[New-CsDialPlan](https://technet.microsoft.com/library/Gg425860(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="d06bb-135">[CsDialPlan 다이얼 플랜 제거](https://technet.microsoft.com/library/Gg398791(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="d06bb-135">[Remove-CsDialPlan](https://technet.microsoft.com/library/Gg398791(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="d06bb-136">[설정-CsDialPlan 플랜](https://technet.microsoft.com/library/Gg398644(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="d06bb-136">[Set-CsDialPlan](https://technet.microsoft.com/library/Gg398644(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="d06bb-137">[테스트-CsDialPlan 플랜](https://technet.microsoft.com/library/Gg399024(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="d06bb-137">[Test-CsDialPlan](https://technet.microsoft.com/library/Gg399024(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="d06bb-138">[G-CsPstnUsage 사용](https://technet.microsoft.com/library/Gg412734(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="d06bb-138">[Get-CsPstnUsage](https://technet.microsoft.com/library/Gg412734(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="d06bb-139">[설정-CsPstnUsage](https://technet.microsoft.com/library/Gg399069(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="d06bb-139">[Set-CsPstnUsage](https://technet.microsoft.com/library/Gg399069(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="d06bb-140">[Set-csvoicepolicy](https://technet.microsoft.com/library/Gg398101(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="d06bb-140">[Get-CsVoicePolicy](https://technet.microsoft.com/library/Gg398101(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="d06bb-141">[Set-csvoicepolicy](https://technet.microsoft.com/library/Gg398828(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="d06bb-141">[Grant-CsVoicePolicy](https://technet.microsoft.com/library/Gg398828(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="d06bb-142">[Set-csvoicepolicy](https://technet.microsoft.com/library/Gg425856(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="d06bb-142">[New-CsVoicePolicy](https://technet.microsoft.com/library/Gg425856(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="d06bb-143">[Set-csvoicepolicy을 제거 합니다.](https://technet.microsoft.com/library/Gg398309(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="d06bb-143">[Remove-CsVoicePolicy](https://technet.microsoft.com/library/Gg398309(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="d06bb-144">[Set-csvoicepolicy](https://technet.microsoft.com/library/Gg399021(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="d06bb-144">[Set-CsVoicePolicy](https://technet.microsoft.com/library/Gg399021(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="d06bb-145">[Set-csvoicepolicy](https://technet.microsoft.com/library/Gg398310(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="d06bb-145">[Test-CsVoicePolicy](https://technet.microsoft.com/library/Gg398310(v=OCS.15))</span></span>

<span data-ttu-id="d06bb-146">**[Lync Server 2013의 음성 라우팅 cmdlet](lync-server-2013-voice-routing-cmdlets.md)**</span><span class="sxs-lookup"><span data-stu-id="d06bb-146">**[Voice routing cmdlets in Lync Server 2013](lync-server-2013-voice-routing-cmdlets.md)**</span></span>

  - <span></span>  
    <span data-ttu-id="d06bb-147">[Get-CsRoutingConfiguration](https://technet.microsoft.com/library/Gg425851(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="d06bb-147">[Get-CsRoutingConfiguration](https://technet.microsoft.com/library/Gg425851(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="d06bb-148">[새-CsRoutingConfiguration](https://technet.microsoft.com/library/Gg399056(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="d06bb-148">[New-CsRoutingConfiguration](https://technet.microsoft.com/library/Gg399056(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="d06bb-149">[제거-CsRoutingConfiguration](https://technet.microsoft.com/library/Gg398643(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="d06bb-149">[Remove-CsRoutingConfiguration](https://technet.microsoft.com/library/Gg398643(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="d06bb-150">[설정-CsRoutingConfiguration](https://technet.microsoft.com/library/Gg412811(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="d06bb-150">[Set-CsRoutingConfiguration](https://technet.microsoft.com/library/Gg412811(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="d06bb-151">[Get-csvoiceroute](https://technet.microsoft.com/library/Gg425926(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="d06bb-151">[Get-CsVoiceRoute](https://technet.microsoft.com/library/Gg425926(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="d06bb-152">[Get-csvoiceroute](https://technet.microsoft.com/library/Gg398197(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="d06bb-152">[New-CsVoiceRoute](https://technet.microsoft.com/library/Gg398197(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="d06bb-153">[Get-csvoiceroute을 제거 합니다.](https://technet.microsoft.com/library/Gg398468(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="d06bb-153">[Remove-CsVoiceRoute](https://technet.microsoft.com/library/Gg398468(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="d06bb-154">[Get-csvoiceroute](https://technet.microsoft.com/library/Gg412893(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="d06bb-154">[Set-CsVoiceRoute](https://technet.microsoft.com/library/Gg412893(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="d06bb-155">[Get-csvoiceroute](https://technet.microsoft.com/library/Gg425873(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="d06bb-155">[Test-CsVoiceRoute](https://technet.microsoft.com/library/Gg425873(v=OCS.15))</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="d06bb-156">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d06bb-156">See Also</span></span>


[<span data-ttu-id="d06bb-157">Lync Server 2013의 고급 Enterprise Voice cmdlet</span><span class="sxs-lookup"><span data-stu-id="d06bb-157">Advanced Enterprise Voice cmdlets in Lync Server 2013</span></span>](lync-server-2013-advanced-enterprise-voice-cmdlets.md)  
[<span data-ttu-id="d06bb-158">Lync Server 2013의 음성 응용 프로그램 cmdlet</span><span class="sxs-lookup"><span data-stu-id="d06bb-158">Voice application cmdlets in Lync Server 2013</span></span>](lync-server-2013-voice-application-cmdlets.md)  


[<span data-ttu-id="d06bb-159">Lync Server PowerShell 블로그</span><span class="sxs-lookup"><span data-stu-id="d06bb-159">Lync Server PowerShell Blog</span></span>](https://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

