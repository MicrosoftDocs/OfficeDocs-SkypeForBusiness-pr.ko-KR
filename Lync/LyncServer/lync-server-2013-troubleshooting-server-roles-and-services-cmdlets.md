---
title: 'Lync Server 2013: 서버 역할 및 서비스 cmdlet 문제 해결'
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
ms.openlocfilehash: 6bb8c4504674e5459fbbb0e7529ea4e6c4ad7a8f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744998"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="troubleshooting-server-roles-and-services-cmdlets-in-lync-server-2013"></a><span data-ttu-id="3dce7-102">Lync Server 2013에서 서버 역할 및 서비스 cmdlet 문제 해결</span><span class="sxs-lookup"><span data-stu-id="3dce7-102">Troubleshooting server roles and services cmdlets in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3dce7-103">_**마지막으로 수정한 주제:** 2012-08-27_</span><span class="sxs-lookup"><span data-stu-id="3dce7-103">_**Topic Last Modified:** 2012-08-27_</span></span>

<span data-ttu-id="3dce7-104">문제 해결 cmdlet은 Microsoft Lync Server 2013이 예상 대로 작동 하는지 확인 하는 다양 한 방법을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="3dce7-104">The troubleshooting cmdlets provide different ways to verify that Microsoft Lync Server 2013 is working as expected.</span></span> <span data-ttu-id="3dce7-105">예를 들어 CsHealthMonitoringConfiguration cmdlet을 사용 하면 레지스트라 및 디렉터 풀의 테스트 계정을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3dce7-105">For example, the CsHealthMonitoringConfiguration cmdlets enable you to set up test accounts for Registrar and Director pools.</span></span> <span data-ttu-id="3dce7-106">그런 다음 해당 테스트 계정을 사용 하 여 사용자가 시스템에 로그인 하거나 인스턴트 메시지를 교환 하거나 PSTN (공개 통신 네트워크)에 있는 휴대폰으로 전화 하는 등의 일반적인 작업을 성공적으로 완료할 수 있는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3dce7-106">In turn, you can then use those test accounts to verify that users are able to successfully complete common tasks such as logging on to the system, exchanging instant messages, or making calls to a phone located on the public switched telephone network (PSTN).</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="3dce7-107">Cmdlet에 대 한 자세한 내용은의 Lync Server&nbsp;Windows PowerShell 블로그를 참조 <A href="http://go.microsoft.com/fwlink/p/?linkid=263432">http://go.microsoft.com/fwlink/p/?linkId=263432</A>하세요.</span><span class="sxs-lookup"><span data-stu-id="3dce7-107">For additional information about cmdlets, see the Lync Server&nbsp;Windows PowerShell Blog at <A href="http://go.microsoft.com/fwlink/p/?linkid=263432">http://go.microsoft.com/fwlink/p/?linkId=263432</A>.</span></span> <span data-ttu-id="3dce7-108">각 블로그 및 해당 URL의 콘텐츠는 예 고 없이 변경 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3dce7-108">The content of each blog and its URL are subject to change without notice.</span></span>



</div>

<div>

## <a name="server-roles-and-services-cmdlets"></a><span data-ttu-id="3dce7-109">서버 역할 및 서비스 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="3dce7-109">Server Roles and Services Cmdlets</span></span>

<span data-ttu-id="3dce7-110">다음은 서버 역할 및 서비스 문제 해결에 직접 관련 된 cmdlet의 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="3dce7-110">The following is a list of cmdlets that relate directly to troubleshooting server roles and services:</span></span>

<span data-ttu-id="3dce7-111">**서버 역할 및 서비스 문제 해결**</span><span class="sxs-lookup"><span data-stu-id="3dce7-111">**Troubleshooting Server Roles and Services**</span></span>

  - <span></span>  
    <span data-ttu-id="3dce7-112">[Get-Cs오디오/Estserviceapplication](https://technet.microsoft.com/en-us/library/Gg412984(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="3dce7-112">[Get-CsAudioTestServiceApplication](https://technet.microsoft.com/en-us/library/Gg412984(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="3dce7-113">[Set-Cs| Rootestserviceapplication](https://technet.microsoft.com/en-us/library/Gg398907(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="3dce7-113">[Set-CsAudioTestServiceApplication](https://technet.microsoft.com/en-us/library/Gg398907(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="3dce7-114">[Get-CsHealthMonitoringConfiguration](https://technet.microsoft.com/en-us/library/Gg398667(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="3dce7-114">[Get-CsHealthMonitoringConfiguration](https://technet.microsoft.com/en-us/library/Gg398667(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="3dce7-115">[새로운 CsHealthMonitoringConfiguration](https://technet.microsoft.com/en-us/library/Gg398718(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="3dce7-115">[New-CsHealthMonitoringConfiguration](https://technet.microsoft.com/en-us/library/Gg398718(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="3dce7-116">[제거-CsHealthMonitoringConfiguration](https://technet.microsoft.com/en-us/library/Gg425794(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="3dce7-116">[Remove-CsHealthMonitoringConfiguration](https://technet.microsoft.com/en-us/library/Gg425794(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="3dce7-117">[Set-CsHealthMonitoringConfiguration](https://technet.microsoft.com/en-us/library/Gg425847(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="3dce7-117">[Set-CsHealthMonitoringConfiguration](https://technet.microsoft.com/en-us/library/Gg425847(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="3dce7-118">[Get-CsDiagnosticConfiguration](https://technet.microsoft.com/en-us/library/Gg413034(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="3dce7-118">[Get-CsDiagnosticConfiguration](https://technet.microsoft.com/en-us/library/Gg413034(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="3dce7-119">[새로운 CsDiagnosticConfiguration](https://technet.microsoft.com/en-us/library/Gg398733(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="3dce7-119">[New-CsDiagnosticConfiguration](https://technet.microsoft.com/en-us/library/Gg398733(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="3dce7-120">[제거-CsDiagnosticConfiguration](https://technet.microsoft.com/en-us/library/Gg412853(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="3dce7-120">[Remove-CsDiagnosticConfiguration](https://technet.microsoft.com/en-us/library/Gg412853(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="3dce7-121">[Set-CsDiagnosticConfiguration](https://technet.microsoft.com/en-us/library/Gg425734(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="3dce7-121">[Set-CsDiagnosticConfiguration](https://technet.microsoft.com/en-us/library/Gg425734(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="3dce7-122">[새로운 CsDiagnosticsFilter](https://technet.microsoft.com/en-us/library/Gg413009(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="3dce7-122">[New-CsDiagnosticsFilter](https://technet.microsoft.com/en-us/library/Gg413009(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="3dce7-123">[Get-CsDiagnosticHeaderConfiguration](https://technet.microsoft.com/en-us/library/Gg412774(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="3dce7-123">[Get-CsDiagnosticHeaderConfiguration](https://technet.microsoft.com/en-us/library/Gg412774(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="3dce7-124">[New-CsDiagnosticHeaderConfiguration](https://technet.microsoft.com/en-us/library/Gg398350(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="3dce7-124">[New-CsDiagnosticHeaderConfiguration](https://technet.microsoft.com/en-us/library/Gg398350(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="3dce7-125">[제거-CsDiagnosticHeaderConfiguration](https://technet.microsoft.com/en-us/library/Gg398941(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="3dce7-125">[Remove-CsDiagnosticHeaderConfiguration](https://technet.microsoft.com/en-us/library/Gg398941(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="3dce7-126">[Set-CsDiagnosticHeaderConfiguration](https://technet.microsoft.com/en-us/library/Gg399045(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="3dce7-126">[Set-CsDiagnosticHeaderConfiguration](https://technet.microsoft.com/en-us/library/Gg399045(v=OCS.15))</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

