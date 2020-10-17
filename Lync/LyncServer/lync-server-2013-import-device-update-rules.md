---
title: 'Lync Server 2013: 장치 업데이트 규칙 가져오기'
description: 'Lync Server 2013: 장치 업데이트 규칙을 가져옵니다.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Import Device Update rules
ms:assetid: 919e9c87-912b-4bc9-92e7-5998fc2e0bf0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994056(v=OCS.15)
ms:contentKeyID: 51803967
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6a7b936a4b7be96332343e8f96134d5ba1b879be
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547854"
---
# <a name="import-device-update-rules-in-lync-server-2013"></a><span data-ttu-id="6e566-103">Lync Server 2013에서 장치 업데이트 규칙 가져오기</span><span class="sxs-lookup"><span data-stu-id="6e566-103">Import Device Update rules in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6e566-104">_**마지막으로 수정 된 항목:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="6e566-104">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="6e566-105">장치 업데이트 규칙은 Windows PowerShell 및 **가져오기-CsDeviceUpdate** cmdlet을 사용 해야만 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6e566-105">Device update rules can be imported only by using Windows PowerShell and the **Import-CsDeviceUpdate** cmdlet.</span></span> <span data-ttu-id="6e566-106">이 cmdlet은 Lync Server 2013 관리 셸 또는 Windows PowerShell의 원격 세션에서 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6e566-106">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="6e566-107">원격 Windows PowerShell을 사용 하 여 Lync Server에 연결 하는 방법에 대 한 자세한 내용은 Lync Server Windows PowerShell 블로그 문서 "빠른 시작: 원격 PowerShell을 사용 하 여 Microsoft Lync Server 2010 관리"를 참조 <A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A> 하세요.</span><span class="sxs-lookup"><span data-stu-id="6e566-107">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at <A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A>.</span></span>



</div>

<div>


<div>

## <a name="to-import-device-update-rules-to-a-single-web-server"></a><span data-ttu-id="6e566-108">단일 웹 서버로 장치 업데이트 규칙을 가져오려면</span><span class="sxs-lookup"><span data-stu-id="6e566-108">To import device update rules to a single web server</span></span>

  - <span data-ttu-id="6e566-109">다음 명령은 장치 업데이트 규칙을 웹 서버 atl-cs-001.litwareinc.com 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="6e566-109">The following command imports device update rules to the Web server atl-cs-001.litwareinc.com:</span></span>
    
        Import-CsDeviceUpdate -Identity "service:WebServer:atl-cs-001.litwareinc.com" -FileName C:\Updates\UCUpdates.cab

</div>

<div>

## <a name="to-import-device-update-rules-to-all-your-web-servers"></a><span data-ttu-id="6e566-110">모든 웹 서버에 대 한 장치 업데이트 규칙을 가져오려면</span><span class="sxs-lookup"><span data-stu-id="6e566-110">To import device update rules to all your web servers</span></span>

  - <span data-ttu-id="6e566-111">이 예에서는 조직에 배포 된 모든 웹 서버로 장치 업데이트 규칙을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="6e566-111">In this example, device update rules are imported to all the Web servers deployed in your organization.</span></span> <span data-ttu-id="6e566-112">이 명령을 사용 하려면 폴더 \\ \\ atl-fs-001.litwareinc.com \\ 업데이트를 공유 하 고 모든 웹 서버에서 사용할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e566-112">For this command to work, the folder \\\\atl-fs-001.litwareinc.com\\Updates must be shared and available to all the Web servers.</span></span>
    
        Get-CsService -WebServer | ForEach-Object {Import-CsDeviceUpdate -Identity $_.Identity -FileName \\atl-fs-001.litwareinc.com\Updates\UCUpdates.cab}

</div>

<span data-ttu-id="6e566-113">자세한 내용은 [가져오기-CsDeviceUpdate](https://docs.microsoft.com/powershell/module/skype/Import-CsDeviceUpdate) cmdlet에 대 한 도움말 항목을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="6e566-113">For details, see the Help topic for the [Import-CsDeviceUpdate](https://docs.microsoft.com/powershell/module/skype/Import-CsDeviceUpdate) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="6e566-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6e566-114">See Also</span></span>


[<span data-ttu-id="6e566-115">Lync Server 2013의 장치 업데이트 규칙에 대 한 정보 보기</span><span class="sxs-lookup"><span data-stu-id="6e566-115">View information about Device Update rules in Lync Server 2013</span></span>](lync-server-2013-view-information-about-device-update-rules.md)  
[<span data-ttu-id="6e566-116">Lync Server 2013에서 장치 업데이트 규칙 승인</span><span class="sxs-lookup"><span data-stu-id="6e566-116">Approve a Device Update rule in Lync Server 2013</span></span>](lync-server-2013-approve-a-device-update-rule.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

