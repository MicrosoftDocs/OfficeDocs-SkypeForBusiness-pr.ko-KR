---
title: 'Lync Server 2013: 새로운 가상화 기능'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: New virtualization features
ms:assetid: edeb2c41-765e-47b8-8a2b-7a7ce09de2ad
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721926(v=OCS.15)
ms:contentKeyID: 49733861
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0e0fcd012470d21a713275fde6aabc29a864fe54
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981598"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="new-virtualization-features-in-lync-server-2013"></a><span data-ttu-id="96181-102">Lync Server 2013의 새로운 가상화 기능</span><span class="sxs-lookup"><span data-stu-id="96181-102">New virtualization features in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="96181-103">_**마지막으로 수정한 주제:** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="96181-103">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="96181-104">Lync Server 2013는 Windows server 2012, Windows Server 2012 R2 및 Windows Server 2008 R2 모두에서 가상화를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="96181-104">Lync Server 2013 supports virtualization on both Windows Server 2012, Windows Server 2012 R2, and Windows Server 2008 R2.</span></span> <span data-ttu-id="96181-105">Windows Server 2012 및 Windows Server 2012 R2 지원에는 단일 루트 I/o 가상화 (SR-IOV) 기능이 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="96181-105">Support on Windows Server 2012 and Windows Server 2012 R2 includes support for the Single Root I/O Virtualization (SR-IOV) capabilities.</span></span> <span data-ttu-id="96181-106">SR-IOV를 사용 하는 경우 실제 네트워크 어댑터의 가상 기능이 가상 컴퓨터에 직접 할당 됩니다.</span><span class="sxs-lookup"><span data-stu-id="96181-106">With SR-IOV, the virtual function of a physical network adapter is assigned directly to a virtual machine.</span></span> <span data-ttu-id="96181-107">이렇게 하면 네트워크 처리량이 증가 하 고 네트워크 트래픽을 처리 하는 데 필요한 호스트 CPU 오버 헤드가 감소 됩니다.</span><span class="sxs-lookup"><span data-stu-id="96181-107">This increases network throughput and reduces network latency while also reducing the host CPU overhead that is required for processing network traffic.</span></span> <span data-ttu-id="96181-108">SR-IOV를 활용 하려면 sr-iov를 지 원하는 BIOS가 있는 호스트 서버와 SR-IOV를 지 원하는 네트워크 어댑터를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="96181-108">To take advantage of SR-IOV, you must use a host server which has BIOS which supports SR-IOV, as well as use network adapters that support SR-IOV.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

