---
title: 'Lync Server 2013: 서버 역할 및 서비스 cmdlet 문제 해결'
description: 'Lync Server 2013: 서버 역할 및 서비스 cmdlet 문제 해결'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Troubleshooting server roles and services cmdlets
ms:assetid: 03be4cae-bf35-40b2-8e02-477b64afa4c9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg415628(v=OCS.15)
ms:contentKeyID: 48183268
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c524ca800445e6b23175ba13621b52c71bc4335f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48548914"
---
# <a name="troubleshooting-server-roles-and-services-cmdlets-in-lync-server-2013"></a><span data-ttu-id="afd71-103">Lync Server 2013의 서버 역할 및 서비스 cmdlet 문제 해결</span><span class="sxs-lookup"><span data-stu-id="afd71-103">Troubleshooting server roles and services cmdlets in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="afd71-104">_**마지막으로 수정 된 항목:** 2012-08-27_</span><span class="sxs-lookup"><span data-stu-id="afd71-104">_**Topic Last Modified:** 2012-08-27_</span></span>

<span data-ttu-id="afd71-105">문제 해결 cmdlet은 Microsoft Lync Server 2013이 예상 대로 작동 하는지 확인 하는 다양 한 방법을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="afd71-105">The troubleshooting cmdlets provide different ways to verify that Microsoft Lync Server 2013 is working as expected.</span></span> <span data-ttu-id="afd71-106">예를 들어 CsHealthMonitoringConfiguration cmdlet를 사용하면 등록자 및 디렉터 풀에 대해 테스트 계정을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="afd71-106">For example, the CsHealthMonitoringConfiguration cmdlets enable you to set up test accounts for Registrar and Director pools.</span></span> <span data-ttu-id="afd71-107">그런 후에 이러한 테스트 계정을 통해 사용자가 시스템 로그온, 인스턴트 메시지 교환, 공중 전화망(PSTN)의 전화에 전화 걸기 등의 일반 작업을 제대로 완료할 수 있는지를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="afd71-107">In turn, you can then use those test accounts to verify that users are able to successfully complete common tasks such as logging on to the system, exchanging instant messages, or making calls to a phone located on the public switched telephone network (PSTN).</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="afd71-108">Cmdlet에 대 한 자세한 내용은 Lync Server &nbsp; Windows PowerShell 블로그를 참조 <A href="https://go.microsoft.com/fwlink/p/?linkid=263432">https://go.microsoft.com/fwlink/p/?linkId=263432</A> 하세요.</span><span class="sxs-lookup"><span data-stu-id="afd71-108">For additional information about cmdlets, see the Lync Server&nbsp;Windows PowerShell Blog at <A href="https://go.microsoft.com/fwlink/p/?linkid=263432">https://go.microsoft.com/fwlink/p/?linkId=263432</A>.</span></span> <span data-ttu-id="afd71-109">각 블로그의 콘텐츠와 해당 URL은 사전 통지 없이 변경될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="afd71-109">The content of each blog and its URL are subject to change without notice.</span></span>



</div>

<div>

## <a name="server-roles-and-services-cmdlets"></a><span data-ttu-id="afd71-110">서버 역할 및 서비스 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="afd71-110">Server Roles and Services Cmdlets</span></span>

<span data-ttu-id="afd71-111">다음은 서버 역할 및 서비스 문제 해결과 직접적으로 관련된 cmdlet 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="afd71-111">The following is a list of cmdlets that relate directly to troubleshooting server roles and services:</span></span>

<span data-ttu-id="afd71-112">**서버 역할 및 서비스 문제 해결**</span><span class="sxs-lookup"><span data-stu-id="afd71-112">**Troubleshooting Server Roles and Services**</span></span>

  - <span></span>  
    <span data-ttu-id="afd71-113">[Get-CsAudioTestServiceApplication](https://technet.microsoft.com/library/Gg412984(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="afd71-113">[Get-CsAudioTestServiceApplication](https://technet.microsoft.com/library/Gg412984(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="afd71-114">[설정-CsAudioTestServiceApplication](https://technet.microsoft.com/library/Gg398907(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="afd71-114">[Set-CsAudioTestServiceApplication](https://technet.microsoft.com/library/Gg398907(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="afd71-115">[Get-cshealthmonitoringconfiguration](https://technet.microsoft.com/library/Gg398667(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="afd71-115">[Get-CsHealthMonitoringConfiguration](https://technet.microsoft.com/library/Gg398667(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="afd71-116">[Get-cshealthmonitoringconfiguration](https://technet.microsoft.com/library/Gg398718(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="afd71-116">[New-CsHealthMonitoringConfiguration](https://technet.microsoft.com/library/Gg398718(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="afd71-117">[Get-cshealthmonitoringconfiguration을 제거 합니다.](https://technet.microsoft.com/library/Gg425794(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="afd71-117">[Remove-CsHealthMonitoringConfiguration](https://technet.microsoft.com/library/Gg425794(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="afd71-118">[Get-cshealthmonitoringconfiguration](https://technet.microsoft.com/library/Gg425847(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="afd71-118">[Set-CsHealthMonitoringConfiguration](https://technet.microsoft.com/library/Gg425847(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="afd71-119">[Get-csdiagnosticconfiguration](https://technet.microsoft.com/library/Gg413034(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="afd71-119">[Get-CsDiagnosticConfiguration](https://technet.microsoft.com/library/Gg413034(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="afd71-120">[Get-csdiagnosticconfiguration](https://technet.microsoft.com/library/Gg398733(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="afd71-120">[New-CsDiagnosticConfiguration](https://technet.microsoft.com/library/Gg398733(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="afd71-121">[Get-csdiagnosticconfiguration을 제거 합니다.](https://technet.microsoft.com/library/Gg412853(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="afd71-121">[Remove-CsDiagnosticConfiguration](https://technet.microsoft.com/library/Gg412853(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="afd71-122">[Get-csdiagnosticconfiguration](https://technet.microsoft.com/library/Gg425734(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="afd71-122">[Set-CsDiagnosticConfiguration](https://technet.microsoft.com/library/Gg425734(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="afd71-123">[New-csdiagnosticsfilter](https://technet.microsoft.com/library/Gg413009(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="afd71-123">[New-CsDiagnosticsFilter](https://technet.microsoft.com/library/Gg413009(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="afd71-124">[Get-csdiagnosticheaderconfiguration](https://technet.microsoft.com/library/Gg412774(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="afd71-124">[Get-CsDiagnosticHeaderConfiguration](https://technet.microsoft.com/library/Gg412774(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="afd71-125">[Get-csdiagnosticheaderconfiguration](https://technet.microsoft.com/library/Gg398350(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="afd71-125">[New-CsDiagnosticHeaderConfiguration](https://technet.microsoft.com/library/Gg398350(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="afd71-126">[Get-csdiagnosticheaderconfiguration을 제거 합니다.](https://technet.microsoft.com/library/Gg398941(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="afd71-126">[Remove-CsDiagnosticHeaderConfiguration](https://technet.microsoft.com/library/Gg398941(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="afd71-127">[Get-csdiagnosticheaderconfiguration](https://technet.microsoft.com/library/Gg399045(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="afd71-127">[Set-CsDiagnosticHeaderConfiguration](https://technet.microsoft.com/library/Gg399045(v=OCS.15))</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

