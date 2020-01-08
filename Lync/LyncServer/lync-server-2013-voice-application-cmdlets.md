---
title: 'Lync Server 2013: Voice application cmdlet'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Voice application cmdlets
ms:assetid: 0d73ace6-1185-484a-980a-4b3d63ba507b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg415634(v=OCS.15)
ms:contentKeyID: 48183404
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 83ada9177e86c88349214d5d7191de15c4ecab81
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984341"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="voice-application-cmdlets-in-lync-server-2013"></a><span data-ttu-id="2b0e6-102">Lync Server 2013의 음성 응용 프로그램 cmdlet</span><span class="sxs-lookup"><span data-stu-id="2b0e6-102">Voice application cmdlets in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2b0e6-103">_**마지막으로 수정한 주제:** 2012-10-09_</span><span class="sxs-lookup"><span data-stu-id="2b0e6-103">_**Topic Last Modified:** 2012-10-09_</span></span>

<span data-ttu-id="2b0e6-104">음성 응용 프로그램은 프런트 엔드 서버의 응용 프로그램 서비스에서 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2b0e6-104">Voice applications run on the Application service on the Front End Server.</span></span> <span data-ttu-id="2b0e6-105">이러한 응용 프로그램은 통화를 대기 상태로 처리 하 고, 할당 되지 않은 번호와 UM (Exchange 통합 메시징)을 사용 하 고, 응답 그룹 응용 프로그램을 실행할 수 있도록 하 여 수신 및 발신 전화 통화를 관리 하도록 도와줍니다.</span><span class="sxs-lookup"><span data-stu-id="2b0e6-105">These applications help you manage incoming and outgoing phone calls by allowing you to park calls, deal with unassigned numbers, coordinate with Exchange Unified Messaging (UM), and run Response Group application.</span></span>

<div>

## <a name="voice-application-cmdlets"></a><span data-ttu-id="2b0e6-106">음성 응용 프로그램 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="2b0e6-106">Voice Application Cmdlets</span></span>

<span data-ttu-id="2b0e6-107">다음은 음성 응용 프로그램을 처리 하는 cmdlet 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="2b0e6-107">The following is a list of cmdlets that deal with voice applications:</span></span>

<span data-ttu-id="2b0e6-108">**[Lync Server 2013의 통화 공원 응용 프로그램 cmdlet](lync-server-2013-call-park-application-cmdlets.md)**</span><span class="sxs-lookup"><span data-stu-id="2b0e6-108">**[Call Park application cmdlets in Lync Server 2013](lync-server-2013-call-park-application-cmdlets.md)**</span></span>

  - <span></span>  
    <span data-ttu-id="2b0e6-109">[Get-CsCallParkOrbit](https://technet.microsoft.com/en-us/library/Gg398554(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2b0e6-109">[Get-CsCallParkOrbit](https://technet.microsoft.com/en-us/library/Gg398554(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="2b0e6-110">[새로운 CsCallParkOrbit](https://technet.microsoft.com/en-us/library/Gg398936(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2b0e6-110">[New-CsCallParkOrbit](https://technet.microsoft.com/en-us/library/Gg398936(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="2b0e6-111">[제거-CsCallParkOrbit](https://technet.microsoft.com/en-us/library/Gg412901(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2b0e6-111">[Remove-CsCallParkOrbit](https://technet.microsoft.com/en-us/library/Gg412901(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="2b0e6-112">[Set-CsCallParkOrbit](https://technet.microsoft.com/en-us/library/Gg398796(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2b0e6-112">[Set-CsCallParkOrbit](https://technet.microsoft.com/en-us/library/Gg398796(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="2b0e6-113">[Set-CsCallParkServiceMusicOnHoldFile](https://technet.microsoft.com/en-us/library/Gg412836(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2b0e6-113">[Set-CsCallParkServiceMusicOnHoldFile](https://technet.microsoft.com/en-us/library/Gg412836(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="2b0e6-114">[Get-CsCpsConfiguration](https://technet.microsoft.com/en-us/library/Gg398948(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2b0e6-114">[Get-CsCpsConfiguration](https://technet.microsoft.com/en-us/library/Gg398948(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="2b0e6-115">[새로운 CsCpsConfiguration](https://technet.microsoft.com/en-us/library/Gg412919(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2b0e6-115">[New-CsCpsConfiguration](https://technet.microsoft.com/en-us/library/Gg412919(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="2b0e6-116">[제거-CsCpsConfiguration](https://technet.microsoft.com/en-us/library/Gg398358(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2b0e6-116">[Remove-CsCpsConfiguration](https://technet.microsoft.com/en-us/library/Gg398358(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="2b0e6-117">[Set-CsCpsConfiguration](https://technet.microsoft.com/en-us/library/Gg412721(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2b0e6-117">[Set-CsCpsConfiguration](https://technet.microsoft.com/en-us/library/Gg412721(v=OCS.15))</span></span>

<span data-ttu-id="2b0e6-118">**[Lync Server 2013의 Exchange UM cmdlet](lync-server-2013-exchange-um-cmdlets.md)**</span><span class="sxs-lookup"><span data-stu-id="2b0e6-118">**[Exchange UM cmdlets in Lync Server 2013](lync-server-2013-exchange-um-cmdlets.md)**</span></span>

  - <span></span>  
    <span data-ttu-id="2b0e6-119">[Get-C(Um연락처)](https://technet.microsoft.com/en-us/library/Gg412725(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2b0e6-119">[Get-CsExUmContact](https://technet.microsoft.com/en-us/library/Gg412725(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="2b0e6-120">[이사-C간 Um접점](https://technet.microsoft.com/en-us/library/Gg425842(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2b0e6-120">[Move-CsExUmContact](https://technet.microsoft.com/en-us/library/Gg425842(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="2b0e6-121">[신규-C또는 Um연락처](https://technet.microsoft.com/en-us/library/Gg398139(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2b0e6-121">[New-CsExUmContact](https://technet.microsoft.com/en-us/library/Gg398139(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="2b0e6-122">[제거-C간 Umcontact](rehttps://technet.microsoft.com/en-us/library/Gg425842(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2b0e6-122">[Remove-CsExUmContact](rehttps://technet.microsoft.com/en-us/library/Gg425842(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="2b0e6-123">[Set-C간 Umcontact](https://technet.microsoft.com/en-us/library/Gg412944(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2b0e6-123">[Set-CsExUmContact](https://technet.microsoft.com/en-us/library/Gg412944(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="2b0e6-124">[테스트-CsExStorageConnectivity](https://technet.microsoft.com/en-us/library/JJ204740(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2b0e6-124">[Test-CsExStorageConnectivity](https://technet.microsoft.com/en-us/library/JJ204740(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="2b0e6-125">[테스트-CsExStorageNotification](https://technet.microsoft.com/en-us/library/JJ205331(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2b0e6-125">[Test-CsExStorageNotification](https://technet.microsoft.com/en-us/library/JJ205331(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="2b0e6-126">[Test-CsExUMConnectivity](https://technet.microsoft.com/en-us/library/JJ204784(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2b0e6-126">[Test-CsExUMConnectivity](https://technet.microsoft.com/en-us/library/JJ204784(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="2b0e6-127">[Test-CsExUMVoiceMail](https://technet.microsoft.com/en-us/library/JJ205058(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2b0e6-127">[Test-CsExUMVoiceMail](https://technet.microsoft.com/en-us/library/JJ205058(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="2b0e6-128">[Get-CsHostedVoicemailPolicy](https://technet.microsoft.com/en-us/library/Gg398348(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2b0e6-128">[Get-CsHostedVoicemailPolicy](https://technet.microsoft.com/en-us/library/Gg398348(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="2b0e6-129">[부여-CsHostedVoicemailPolicy](https://technet.microsoft.com/en-us/library/Gg412829(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2b0e6-129">[Grant-CsHostedVoicemailPolicy](https://technet.microsoft.com/en-us/library/Gg412829(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="2b0e6-130">[새로운 CsHostedVoicemailPolicy](https://technet.microsoft.com/en-us/library/Gg398653(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2b0e6-130">[New-CsHostedVoicemailPolicy](https://technet.microsoft.com/en-us/library/Gg398653(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="2b0e6-131">[제거-CsHostedVoicemailPolicy](https://technet.microsoft.com/en-us/library/Gg398211(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2b0e6-131">[Remove-CsHostedVoicemailPolicy](https://technet.microsoft.com/en-us/library/Gg398211(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="2b0e6-132">[Set-CsHostedVoicemailPolicy](https://technet.microsoft.com/en-us/library/Gg412722(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2b0e6-132">[Set-CsHostedVoicemailPolicy](https://technet.microsoft.com/en-us/library/Gg412722(v=OCS.15))</span></span>

<span data-ttu-id="2b0e6-133">**[Lync Server 2013의 응답 그룹 응용 프로그램 cmdlet](lync-server-2013-response-group-application-cmdlets.md)**</span><span class="sxs-lookup"><span data-stu-id="2b0e6-133">**[Response Group application cmdlets in Lync Server 2013](lync-server-2013-response-group-application-cmdlets.md)**</span></span>

  - <span></span>  
    <span data-ttu-id="2b0e6-134">[Get-CsRgsAgentGroup](https://technet.microsoft.com/en-us/library/Gg425793(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2b0e6-134">[Get-CsRgsAgentGroup](https://technet.microsoft.com/en-us/library/Gg425793(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="2b0e6-135">[새로운 CsRgsAgentGroup](https://technet.microsoft.com/en-us/library/Gg413065(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2b0e6-135">[New-CsRgsAgentGroup](https://technet.microsoft.com/en-us/library/Gg413065(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="2b0e6-136">[제거-CsRgsAgentGroup](https://technet.microsoft.com/en-us/library/Gg398969(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2b0e6-136">[Remove-CsRgsAgentGroup](https://technet.microsoft.com/en-us/library/Gg398969(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="2b0e6-137">[Set-CsRgsAgentGroup](https://technet.microsoft.com/en-us/library/Gg425955(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2b0e6-137">[Set-CsRgsAgentGroup](https://technet.microsoft.com/en-us/library/Gg425955(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="2b0e6-138">[새로운 CsRgsAnswer](https://technet.microsoft.com/en-us/library/Gg412812(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2b0e6-138">[New-CsRgsAnswer](https://technet.microsoft.com/en-us/library/Gg412812(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="2b0e6-139">[가져오기-CsRgsAudioFile](https://technet.microsoft.com/en-us/library/Gg412830(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2b0e6-139">[Import-CsRgsAudioFile](https://technet.microsoft.com/en-us/library/Gg412830(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="2b0e6-140">[새로운 CsRgsCallAction](https://technet.microsoft.com/en-us/library/Gg398136(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2b0e6-140">[New-CsRgsCallAction](https://technet.microsoft.com/en-us/library/Gg398136(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="2b0e6-141">[Export-CsRgsConfiguration](https://technet.microsoft.com/en-us/library/JJ205011(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2b0e6-141">[Export-CsRgsConfiguration](https://technet.microsoft.com/en-us/library/JJ205011(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="2b0e6-142">[Get-CsRgsConfiguration](https://technet.microsoft.com/en-us/library/Gg412762(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2b0e6-142">[Get-CsRgsConfiguration](https://technet.microsoft.com/en-us/library/Gg412762(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="2b0e6-143">[가져오기-CsRgsConfiguration](https://technet.microsoft.com/en-us/library/JJ205245(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2b0e6-143">[Import-CsRgsConfiguration](https://technet.microsoft.com/en-us/library/JJ205245(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="2b0e6-144">[Move-CsRgsConfiguration](https://technet.microsoft.com/en-us/library/Gg398782(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2b0e6-144">[Move-CsRgsConfiguration](https://technet.microsoft.com/en-us/library/Gg398782(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="2b0e6-145">[Set-CsRgsConfiguration](https://technet.microsoft.com/en-us/library/Gg425728(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2b0e6-145">[Set-CsRgsConfiguration](https://technet.microsoft.com/en-us/library/Gg425728(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="2b0e6-146">[새로운 CsRgsHoliday](https://technet.microsoft.com/en-us/library/Gg398075(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2b0e6-146">[New-CsRgsHoliday](https://technet.microsoft.com/en-us/library/Gg398075(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="2b0e6-147">[Get-CsRgsHolidaySet](https://technet.microsoft.com/en-us/library/Gg412983(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2b0e6-147">[Get-CsRgsHolidaySet](https://technet.microsoft.com/en-us/library/Gg412983(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="2b0e6-148">[New-CsRgsHolidaySet](https://technet.microsoft.com/en-us/library/Gg398403(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2b0e6-148">[New-CsRgsHolidaySet](https://technet.microsoft.com/en-us/library/Gg398403(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="2b0e6-149">[Remove-CsRgsHolidaySet](https://technet.microsoft.com/en-us/library/Gg398521(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2b0e6-149">[Remove-CsRgsHolidaySet](https://technet.microsoft.com/en-us/library/Gg398521(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="2b0e6-150">[Set-CsRgsHolidaySet](https://technet.microsoft.com/en-us/library/Gg398736(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2b0e6-150">[Set-CsRgsHolidaySet](https://technet.microsoft.com/en-us/library/Gg398736(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="2b0e6-151">[Get-CsRgsHoursOfBusiness](https://technet.microsoft.com/en-us/library/Gg398284(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2b0e6-151">[Get-CsRgsHoursOfBusiness](https://technet.microsoft.com/en-us/library/Gg398284(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="2b0e6-152">[새로운 CsRgsHoursOfBusiness](https://technet.microsoft.com/en-us/library/Gg398291(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2b0e6-152">[New-CsRgsHoursOfBusiness](https://technet.microsoft.com/en-us/library/Gg398291(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="2b0e6-153">[제거-CsRgsHoursOfBusiness](https://technet.microsoft.com/en-us/library/Gg398568(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2b0e6-153">[Remove-CsRgsHoursOfBusiness](https://technet.microsoft.com/en-us/library/Gg398568(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="2b0e6-154">[Set-CsRgsHoursOfBusiness](https://technet.microsoft.com/en-us/library/Gg412929(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2b0e6-154">[Set-CsRgsHoursOfBusiness](https://technet.microsoft.com/en-us/library/Gg412929(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="2b0e6-155">[새로운 CsRgsPrompt](https://technet.microsoft.com/en-us/library/Gg398486(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2b0e6-155">[New-CsRgsPrompt](https://technet.microsoft.com/en-us/library/Gg398486(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="2b0e6-156">[새로운 CsRgsQuestion](https://technet.microsoft.com/en-us/library/Gg398186(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2b0e6-156">[New-CsRgsQuestion](https://technet.microsoft.com/en-us/library/Gg398186(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="2b0e6-157">[Get-CsRgsQueue](https://technet.microsoft.com/en-us/library/Gg412759(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2b0e6-157">[Get-CsRgsQueue](https://technet.microsoft.com/en-us/library/Gg412759(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="2b0e6-158">[새로운 CsRgsQueue](https://technet.microsoft.com/en-us/library/Gg398989(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2b0e6-158">[New-CsRgsQueue](https://technet.microsoft.com/en-us/library/Gg398989(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="2b0e6-159">[제거-CsRgsQueue](https://technet.microsoft.com/en-us/library/Gg398576(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2b0e6-159">[Remove-CsRgsQueue](https://technet.microsoft.com/en-us/library/Gg398576(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="2b0e6-160">[Set-CsRgsQueue](https://technet.microsoft.com/en-us/library/Gg412947(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2b0e6-160">[Set-CsRgsQueue](https://technet.microsoft.com/en-us/library/Gg412947(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="2b0e6-161">[새로운 CsRgsTimeRange](https://technet.microsoft.com/en-us/library/Gg399040(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2b0e6-161">[New-CsRgsTimeRange](https://technet.microsoft.com/en-us/library/Gg399040(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="2b0e6-162">[Get-CsRgsWorkflow](https://technet.microsoft.com/en-us/library/Gg425766(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2b0e6-162">[Get-CsRgsWorkflow](https://technet.microsoft.com/en-us/library/Gg425766(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="2b0e6-163">[새로운 CsRgsWorkflow](https://technet.microsoft.com/en-us/library/Gg398246(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2b0e6-163">[New-CsRgsWorkflow](https://technet.microsoft.com/en-us/library/Gg398246(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="2b0e6-164">[제거-CsRgsWorkflow](https://technet.microsoft.com/en-us/library/Gg398765(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2b0e6-164">[Remove-CsRgsWorkflow](https://technet.microsoft.com/en-us/library/Gg398765(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="2b0e6-165">[Set-CsRgsWorkflow](https://technet.microsoft.com/en-us/library/Gg425845(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2b0e6-165">[Set-CsRgsWorkflow](https://technet.microsoft.com/en-us/library/Gg425845(v=OCS.15))</span></span>

<span data-ttu-id="2b0e6-166">**[Lync Server 2013의 할당 되지 않은 번호 cmdlet](lync-server-2013-unassigned-number-cmdlets.md)**</span><span class="sxs-lookup"><span data-stu-id="2b0e6-166">**[Unassigned number cmdlets in Lync Server 2013](lync-server-2013-unassigned-number-cmdlets.md)**</span></span>

  - <span></span>  
    <span data-ttu-id="2b0e6-167">[Get-CsUnassignedNumber](https://technet.microsoft.com/en-us/library/Gg412792(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2b0e6-167">[Get-CsUnassignedNumber](https://technet.microsoft.com/en-us/library/Gg412792(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="2b0e6-168">[New-CsUnassignedNumber](https://technet.microsoft.com/en-us/library/Gg398651(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2b0e6-168">[New-CsUnassignedNumber](https://technet.microsoft.com/en-us/library/Gg398651(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="2b0e6-169">[제거-CsUnassignedNumber](https://technet.microsoft.com/en-us/library/Gg398209(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2b0e6-169">[Remove-CsUnassignedNumber](https://technet.microsoft.com/en-us/library/Gg398209(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="2b0e6-170">[Set-CsUnassignedNumber](https://technet.microsoft.com/en-us/library/Gg399033(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2b0e6-170">[Set-CsUnassignedNumber](https://technet.microsoft.com/en-us/library/Gg399033(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="2b0e6-171">[다운로드-CsAnnouncement](https://technet.microsoft.com/en-us/library/Gg398937(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2b0e6-171">[Get-CsAnnouncement](https://technet.microsoft.com/en-us/library/Gg398937(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="2b0e6-172">[새 CsAnnouncement](https://technet.microsoft.com/en-us/library/Gg398522(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2b0e6-172">[New-CsAnnouncement](https://technet.microsoft.com/en-us/library/Gg398522(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="2b0e6-173">[CsAnnouncement 제거](https://technet.microsoft.com/en-us/library/Gg412766(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2b0e6-173">[Remove-CsAnnouncement](https://technet.microsoft.com/en-us/library/Gg412766(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="2b0e6-174">[집합-CsAnnouncement](https://technet.microsoft.com/en-us/library/Gg425752(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2b0e6-174">[Set-CsAnnouncement](https://technet.microsoft.com/en-us/library/Gg425752(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="2b0e6-175">[가져오기-CsAnnouncementFile](https://technet.microsoft.com/en-us/library/Gg398472(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2b0e6-175">[Import-CsAnnouncementFile](https://technet.microsoft.com/en-us/library/Gg398472(v=OCS.15))</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="2b0e6-176">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2b0e6-176">See Also</span></span>


[<span data-ttu-id="2b0e6-177">Lync Server 2013의 엔터프라이즈 음성 cmdlet</span><span class="sxs-lookup"><span data-stu-id="2b0e6-177">Enterprise Voice cmdlets in Lync Server 2013</span></span>](lync-server-2013-enterprise-voice-cmdlets.md)  


[<span data-ttu-id="2b0e6-178">Lync Server PowerShell 블로그</span><span class="sxs-lookup"><span data-stu-id="2b0e6-178">Lync Server PowerShell Blog</span></span>](http://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

