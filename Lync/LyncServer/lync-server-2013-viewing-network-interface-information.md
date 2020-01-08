---
title: 'Lync Server 2013: 네트워크 인터페이스 정보 보기'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Viewing network interface information
ms:assetid: e7dbb1ec-62b3-48be-a419-c493df5740e6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721916(v=OCS.15)
ms:contentKeyID: 49733850
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f15cf34c7a6743fdd3dbf23558e0c747a1c237bd
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979922"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="viewing-network-interface-information-in-lync-server-2013"></a><span data-ttu-id="d30a0-102">Lync Server 2013에서 네트워크 인터페이스 정보 보기</span><span class="sxs-lookup"><span data-stu-id="d30a0-102">Viewing network interface information in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d30a0-103">_**마지막으로 수정한 주제:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="d30a0-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="d30a0-104">Windows PowerShell 및 **CsNetworkInterface** cmdlet을 사용 하 여 네트워크 인터페이스 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d30a0-104">You can view network interface information by using Windows PowerShell and the **Get-CsNetworkInterface** cmdlet.</span></span> <span data-ttu-id="d30a0-105">Lync Server 2013 관리 셸에서 또는 Windows PowerShell의 원격 세션에서이 cmdlet을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d30a0-105">You can run this cmdlet from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="d30a0-106">원격 Windows PowerShell을 사용 하 여 Lync Server에 연결 하는 방법에 대 한 자세한 내용은 Lync Server Windows PowerShell 블로그 문서 "빠른 시작: 원격 PowerShell을 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)사용 하 여 Microsoft Lync Server 2010 관리"를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d30a0-106">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-view-network-interface-information"></a><span data-ttu-id="d30a0-107">네트워크 인터페이스 정보를 보려면</span><span class="sxs-lookup"><span data-stu-id="d30a0-107">To view network interface information</span></span>

  - <span data-ttu-id="d30a0-108">네트워크 인터페이스 정보를 보려면 Lync Server 관리 셸에서 다음 명령을 입력 한 다음 enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="d30a0-108">To view network interface information, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
        Get-CsNetworkInterface
    
    <span data-ttu-id="d30a0-109">이 명령은 각 네트워크 인터페이스에 대해 다음과 같은 정보를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="d30a0-109">This command returns information similar to the following for each network interface:</span></span>
    
        Identity              : dc.vdomain.com/Primary/1
        ComputerFqdn          : dc.vdomain.com
        IPAddress             : 0.0.0.0
        IPv6Address           :
        Interface             : Primary
        InterfaceNumber       : 1
        ConfiguredFqdn        :
        ConfiguredIPAddress   :
        ConfiguredIPv6Address :
    
    <span data-ttu-id="d30a0-110">자세한 내용은 [Get-help CsNetworkInterface](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterface)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d30a0-110">For details, see [Get-CsNetworkInterface](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterface).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

