---
title: 'Lync Server 2013: 새로운 가상화 기능'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: New virtualization features
ms:assetid: edeb2c41-765e-47b8-8a2b-7a7ce09de2ad
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721926(v=OCS.15)
ms:contentKeyID: 49733861
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7e0b7b6d0d4af8d5aa922262004cf14d33757f42
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42216664"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="new-virtualization-features-in-lync-server-2013"></a><span data-ttu-id="9cf08-102">Lync Server 2013의 새로운 가상화 기능</span><span class="sxs-lookup"><span data-stu-id="9cf08-102">New virtualization features in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9cf08-103">_**마지막으로 수정 된 항목:** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="9cf08-103">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="9cf08-104">Lync Server 2013는 windows Server 2012, Windows Server 2012 R2 및 Windows Server 2008 r 2에서 가상화를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="9cf08-104">Lync Server 2013 supports virtualization on both Windows Server 2012, Windows Server 2012 R2, and Windows Server 2008 R2.</span></span> <span data-ttu-id="9cf08-105">Windows Server 2012 및 Windows Server 2012 r에 대 한 지원에는 단일 루트 i/o 가상화 (sr-iov) 기능이 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9cf08-105">Support on Windows Server 2012 and Windows Server 2012 R2 includes support for the Single Root I/O Virtualization (SR-IOV) capabilities.</span></span> <span data-ttu-id="9cf08-106">SR-IOV를 사용하면 실제 네트워크 어댑터의 가상 기능이 가상 컴퓨터에 직접 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="9cf08-106">With SR-IOV, the virtual function of a physical network adapter is assigned directly to a virtual machine.</span></span> <span data-ttu-id="9cf08-107">따라서 네트워크 처리량이 증가하고 네트워크 대기 시간이 감소되며, 이와 동시에 네트워크 트래픽을 처리하는 데 필요한 호스트 CPU 오버헤드는 감소합니다.</span><span class="sxs-lookup"><span data-stu-id="9cf08-107">This increases network throughput and reduces network latency while also reducing the host CPU overhead that is required for processing network traffic.</span></span> <span data-ttu-id="9cf08-108">SR-IOV를 활용하려면 SR-IOV를 지원하는 BIOS가 설치된 호스트 서버와 SR-IOV를 지원하는 네트워크 어댑터를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9cf08-108">To take advantage of SR-IOV, you must use a host server which has BIOS which supports SR-IOV, as well as use network adapters that support SR-IOV.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

