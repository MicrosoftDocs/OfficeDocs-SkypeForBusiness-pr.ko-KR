---
title: 'Lync Server 2013: 시스템 요구 사항 확인'
description: 'Lync Server 2013: 시스템 요구 사항 확인'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Determining your system requirements
ms:assetid: 620e81e2-42df-4eda-8498-bd56a14aa0e1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398438(v=OCS.15)
ms:contentKeyID: 48184286
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5ceca8eabb234ae7fd483372ff5e611664ecc4fa
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48569494"
---
# <a name="determining-your-system-requirements-for-lync-server-2013"></a><span data-ttu-id="a6f49-103">Lync Server 2013에 대 한 시스템 요구 사항 확인</span><span class="sxs-lookup"><span data-stu-id="a6f49-103">Determining your system requirements for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a6f49-104">_**마지막으로 수정 된 항목:** 2014-01-02_</span><span class="sxs-lookup"><span data-stu-id="a6f49-104">_**Topic Last Modified:** 2014-01-02_</span></span>

<span data-ttu-id="a6f49-105">Lync Server를 실행 하는 모든 서버는 특정 최소 시스템 요구 사항을 충족 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6f49-105">All servers running Lync Server must meet certain minimum system requirements.</span></span> <span data-ttu-id="a6f49-106">Lync Server에 대 한 시스템 요구 사항에는 서버 하드웨어, 각 서버에 설치할 운영 체제, 그리고 서버에 설치 해야 하는 Windows 업데이트 및 기타 소프트웨어와 같은 관련 소프트웨어 요구 사항이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6f49-106">System requirements for Lync Server include the server hardware, the operating system to be installed on each server, and related software requirements, such as the Windows updates and other software that must be installed on the servers.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="a6f49-107">Lync Server는 64 비트 버전 에서만 사용할 수 있으며 64 비트 하드웨어 및 64 비트 버전의 Windows Server가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6f49-107">Lync Server is available only in a 64-bit edition, which requires 64-bit hardware and a 64-bit edition of Windows Server.</span></span> <span data-ttu-id="a6f49-108">이 예외는 32 비트 버전에서 사용할 수 있는 Microsoft Lync Server 2013, 계획 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="a6f49-108">The exception is the Microsoft Lync Server 2013, Planning Tool, which is available in a 32-bit edition.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="a6f49-109">Active Directory 지원, 지원 되는 토폴로지, 서버 위치 및 기타 지원 가능성 문제에 대 한 자세한 내용은 <A href="lync-server-2013-supportability.md">Lync server 2013의 지원 가능성</A>을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="a6f49-109">For details about Active Directory support, supported topologies, server collocation, and other supportability issues, see <A href="lync-server-2013-supportability.md">Supportability for Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="a6f49-110">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="a6f49-110">In This Section</span></span>

  - [<span data-ttu-id="a6f49-111">Lync Server 2013 용 서버 하드웨어 플랫폼</span><span class="sxs-lookup"><span data-stu-id="a6f49-111">Server hardware platforms for Lync Server 2013</span></span>](lync-server-2013-server-hardware-platforms.md)

  - [<span data-ttu-id="a6f49-112">Lync Server 2013의 서버 및 도구 운영 체제 지원</span><span class="sxs-lookup"><span data-stu-id="a6f49-112">Server and tools operating system support in Lync Server 2013</span></span>](lync-server-2013-server-and-tools-operating-system-support.md)

  - [<span data-ttu-id="a6f49-113">Lync Server 2013의 데이터베이스 소프트웨어 지원</span><span class="sxs-lookup"><span data-stu-id="a6f49-113">Database software support in Lync Server 2013</span></span>](lync-server-2013-database-software-support.md)

  - [<span data-ttu-id="a6f49-114">Lync Server 2013의 추가 소프트웨어 요구 사항</span><span class="sxs-lookup"><span data-stu-id="a6f49-114">Additional software requirements for Lync Server 2013</span></span>](lync-server-2013-additional-software-requirements.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="a6f49-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a6f49-115">See Also</span></span>


[<span data-ttu-id="a6f49-116">Lync Server 2013의 클라이언트 및 장치 하드웨어 지원</span><span class="sxs-lookup"><span data-stu-id="a6f49-116">Client and device hardware support in Lync Server 2013</span></span>](lync-server-2013-client-and-device-hardware-support.md)  
[<span data-ttu-id="a6f49-117">Lync Server 2013의 지원 가능성</span><span class="sxs-lookup"><span data-stu-id="a6f49-117">Supportability for Lync Server 2013</span></span>](lync-server-2013-supportability.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

