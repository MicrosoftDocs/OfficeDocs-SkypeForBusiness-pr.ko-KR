---
title: 'Lync Server 2013: 엔터프라이즈 음성 cmdlet 문제 해결'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Troubleshooting Enterprise Voice cmdlets
ms:assetid: 28ec32d2-6d1e-40e6-b2a8-065803288e8b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg415638(v=OCS.15)
ms:contentKeyID: 48183697
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 499da8c727237a581af55e56aec3517a7a427e44
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745038"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="troubleshooting-enterprise-voice-cmdlets-in-lync-server-2013"></a><span data-ttu-id="1d5bf-102">Lync Server 2013에서 엔터프라이즈 음성 cmdlet 문제 해결</span><span class="sxs-lookup"><span data-stu-id="1d5bf-102">Troubleshooting Enterprise Voice cmdlets in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1d5bf-103">_**마지막으로 수정한 주제:** 2012-06-20_</span><span class="sxs-lookup"><span data-stu-id="1d5bf-103">_**Topic Last Modified:** 2012-06-20_</span></span>

<span data-ttu-id="1d5bf-104">Microsoft Lync Server 2013 구현의 일부로 엔터프라이즈 음성을 설정 하는 것은 수신 및 발신 통화가 예상 대로 완료 되도록 모든 사용자가 함께 작업 해야 하는 경로, 정책 및 규칙을 만드는 것과 관련이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d5bf-104">Setting up Enterprise Voice as part of your Microsoft Lync Server 2013 implementation involves creating routes, policies and rules that must all work together to ensure incoming and outgoing calls are completed as expected.</span></span> <span data-ttu-id="1d5bf-105">Lync Server 관리 셸에는 연결 및 경로를 테스트 하 고 구현 중에 발생할 수 있는 문제를 해결 하는 데 사용할 수 있는 cmdlet이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d5bf-105">Lync Server Management Shell includes cmdlets that can be used to test connections and paths and to troubleshoot issues that may arise during implementation.</span></span>

<div>

## <a name="troubleshooting-enterprise-voice-cmdlets"></a><span data-ttu-id="1d5bf-106">엔터프라이즈 음성 Cmdlet 문제 해결</span><span class="sxs-lookup"><span data-stu-id="1d5bf-106">Troubleshooting Enterprise Voice Cmdlets</span></span>

<span data-ttu-id="1d5bf-107">다음 cmdlet을 사용 하 여 엔터프라이즈 음성 연결을 테스트 하 고 문제를 해결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d5bf-107">The following cmdlets can be used to test and troubleshoot Enterprise Voice connections.</span></span>

<span data-ttu-id="1d5bf-108">**엔터프라이즈 음성 Cmdlet 문제 해결**</span><span class="sxs-lookup"><span data-stu-id="1d5bf-108">**Troubleshooting Enterprise Voice Cmdlets**</span></span>

  - <span></span>  
    <span data-ttu-id="1d5bf-109">[Get-CsVoiceConfiguration](https://technet.microsoft.com/en-us/library/Gg398815(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="1d5bf-109">[Get-CsVoiceConfiguration](https://technet.microsoft.com/en-us/library/Gg398815(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="1d5bf-110">[제거-CsVoiceConfiguration](https://technet.microsoft.com/en-us/library/Gg398804(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="1d5bf-110">[Remove-CsVoiceConfiguration](https://technet.microsoft.com/en-us/library/Gg398804(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="1d5bf-111">[Set-CsVoiceConfiguration](https://technet.microsoft.com/en-us/library/Gg398967(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="1d5bf-111">[Set-CsVoiceConfiguration](https://technet.microsoft.com/en-us/library/Gg398967(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="1d5bf-112">[Get-CsVoiceTestConfiguration](https://technet.microsoft.com/en-us/library/Gg412957(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="1d5bf-112">[Get-CsVoiceTestConfiguration](https://technet.microsoft.com/en-us/library/Gg412957(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="1d5bf-113">[새로운 CsVoiceTestConfiguration](https://technet.microsoft.com/en-us/library/Gg398961(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="1d5bf-113">[New-CsVoiceTestConfiguration](https://technet.microsoft.com/en-us/library/Gg398961(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="1d5bf-114">[제거-CsVoiceTestConfiguration](https://technet.microsoft.com/en-us/library/Gg412813(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="1d5bf-114">[Remove-CsVoiceTestConfiguration](https://technet.microsoft.com/en-us/library/Gg412813(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="1d5bf-115">[Set-CsVoiceTestConfiguration](https://technet.microsoft.com/en-us/library/Gg398614(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="1d5bf-115">[Set-CsVoiceTestConfiguration](https://technet.microsoft.com/en-us/library/Gg398614(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="1d5bf-116">[테스트-CsVoiceTestConfiguration](https://technet.microsoft.com/en-us/library/Gg398260(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="1d5bf-116">[Test-CsVoiceTestConfiguration](https://technet.microsoft.com/en-us/library/Gg398260(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="1d5bf-117">[테스트-CsDialPlan 플랜](https://technet.microsoft.com/en-us/library/Gg399024(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="1d5bf-117">[Test-CsDialPlan](https://technet.microsoft.com/en-us/library/Gg399024(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="1d5bf-118">[테스트-CsVoiceNormalizationRule](https://technet.microsoft.com/en-us/library/Gg399003(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="1d5bf-118">[Test-CsVoiceNormalizationRule](https://technet.microsoft.com/en-us/library/Gg399003(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="1d5bf-119">[테스트-CsVoicePolicy](https://technet.microsoft.com/en-us/library/Gg398310(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="1d5bf-119">[Test-CsVoicePolicy](https://technet.microsoft.com/en-us/library/Gg398310(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="1d5bf-120">[테스트-CsVoiceRoute](https://technet.microsoft.com/en-us/library/Gg425873(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="1d5bf-120">[Test-CsVoiceRoute](https://technet.microsoft.com/en-us/library/Gg425873(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="1d5bf-121">[테스트-CsVoiceUser](https://technet.microsoft.com/en-us/library/Gg413013(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="1d5bf-121">[Test-CsVoiceUser](https://technet.microsoft.com/en-us/library/Gg413013(v=OCS.15))</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="1d5bf-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1d5bf-122">See Also</span></span>


[<span data-ttu-id="1d5bf-123">Lync Server 2013의 엔터프라이즈 음성 cmdlet</span><span class="sxs-lookup"><span data-stu-id="1d5bf-123">Enterprise Voice cmdlets in Lync Server 2013</span></span>](lync-server-2013-enterprise-voice-cmdlets.md)  


[<span data-ttu-id="1d5bf-124">Lync Server PowerShell 블로그</span><span class="sxs-lookup"><span data-stu-id="1d5bf-124">Lync Server PowerShell Blog</span></span>](http://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

