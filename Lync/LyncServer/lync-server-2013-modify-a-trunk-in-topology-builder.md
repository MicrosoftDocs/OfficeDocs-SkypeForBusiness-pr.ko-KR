---
title: 'Lync Server 2013: 토폴로지 작성기에서 트렁크 수정'
description: 'Lync Server 2013: 토폴로지 작성기에서 트렁크를 수정 합니다.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Modify a trunk in Topology Builder
ms:assetid: 81055a82-c6f8-47b2-9779-223b1d842f36
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688110(v=OCS.15)
ms:contentKeyID: 49733709
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5f453997664dbe3048a7aa915732b4d95a932dd9
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48550484"
---
# <a name="modify-a-trunk-in-topology-builder-in-lync-server-2013"></a><span data-ttu-id="cc9ec-103">Lync Server 2013의 토폴로지 작성기에서 트렁크 수정</span><span class="sxs-lookup"><span data-stu-id="cc9ec-103">Modify a trunk in Topology Builder in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cc9ec-104">_**마지막으로 수정 된 항목:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="cc9ec-104">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="cc9ec-105">다음 단계에 따라 트렁크의 대체 바이패스 식별자 및 대체 미디어 IP 주소를 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="cc9ec-105">Follow these steps to modify the alternate media IP address and alternate bypass identifier of a trunk.</span></span>

<div>

## <a name="to-modify-the-alternate-media-ip-address-of-a-trunk"></a><span data-ttu-id="cc9ec-106">트렁크의 대체 미디어 IP 주소를 수정하려면</span><span class="sxs-lookup"><span data-stu-id="cc9ec-106">To Modify the Alternate Media IP Address of a Trunk</span></span>

1.  <span data-ttu-id="cc9ec-107">**시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="cc9ec-107">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="cc9ec-108">Set-CsPstnGateway cmdlet을 실행 하 고 Lync Server 관리 셸에서 AlternateBypassId 필드를 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc9ec-108">Run the Set-CsPstnGateway cmdlet and modify the AlternateBypassId field in the Lync Server Management Shell.</span></span>
    
        Set-CsPstnGateway -Identity "PstnGateway:<peer FQDN> -RepresentativeMediaIP <IP address>

</div>

<div>

## <a name="to-modify-the-alternate-bypassid-of-a-trunk"></a><span data-ttu-id="cc9ec-109">트렁크의 대체 바이패스 ID를 수정하려면</span><span class="sxs-lookup"><span data-stu-id="cc9ec-109">To Modify the Alternate BypassID of a Trunk</span></span>

1.  <span data-ttu-id="cc9ec-110">**시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="cc9ec-110">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="cc9ec-111">Set-CsPstnGateway cmdlet을 실행 하 고 Lync Server 관리 셸에서 AlternateBypassId 필드를 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc9ec-111">Run the Set-CsPstnGateway cmdlet and modify the AlternateBypassId field in the Lync Server Management Shell.</span></span>
    
        Set-CsPstnGateway -Identity "PstnGateway:<peer FQDN> -AlternateBypassID <identifier>

</div>

</div>

<span> </span>

</div>

</div>

</div>

