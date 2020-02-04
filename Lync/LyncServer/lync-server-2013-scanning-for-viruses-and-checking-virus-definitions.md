---
title: 'Lync Server 2013: 바이러스 검색 및 바이러스 정의 확인'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Scanning for viruses and checking virus definitions
ms:assetid: 287c0f43-82d1-4c1d-b08f-77112fcb5bfa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720909(v=OCS.15)
ms:contentKeyID: 63969589
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fb36ec86c5e9d30e6a215a89748a02e5ef355b73
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41732648"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="scanning-for-viruses-and-checking-virus-definitions-in-lync-server-2013"></a><span data-ttu-id="79206-102">Lync Server 2013에서 바이러스를 검사 하 고 바이러스 정의를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="79206-102">Scanning for viruses and checking virus definitions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="79206-103">_**마지막으로 수정한 주제:** 2014-05-01_</span><span class="sxs-lookup"><span data-stu-id="79206-103">_**Topic Last Modified:** 2014-05-01_</span></span>

<span data-ttu-id="79206-104">IM 수준 바이러스 백신 제품을 설치 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="79206-104">We highly recommend installing an IM-level antivirus product.</span></span> <span data-ttu-id="79206-105">IM은 조직 전체에서 바이러스와 악성 소프트웨어를 신속 하 게 분배 하는 데 잘 알려진 원본입니다.</span><span class="sxs-lookup"><span data-stu-id="79206-105">IM is a well-known source for quickly spreading both virus and malicious software throughout an organization.</span></span> <span data-ttu-id="79206-106">Lync Server에 대 한 Microsoft Forefront® 보안은 바이러스, 악성 소프트웨어, 파일 및 키워드 필터 보호 및 Office Communications Server와의 원활한 통합으로 다중 엔진 검색을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="79206-106">Microsoft Forefront® Security for Lync Server provides multi-engine scanning with virus, malicious software, file and keyword filter protection and seamless integration with Office Communications Server.</span></span>

<span data-ttu-id="79206-107">Lync Server에 대 한 Forefront 보안 외에도, 서버 파일 시스템을 보호 하기 위해 파일 수준 바이러스 백신 솔루션을 설치 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="79206-107">In addition to Forefront Security for Lync Server, we also highly recommend installing a file-level, antivirus solution to protect the server’s file system.</span></span>

<span data-ttu-id="79206-108">스캐너 엔진과 바이러스 정의를 업데이트 된 상태로 유지 하는 것이 매우 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="79206-108">Keeping scanner engines and virus definitions updated is very important.</span></span> <span data-ttu-id="79206-109">업데이트 상태를 구성 하 고 모니터링 하면 Office 통신 서버와 파일 시스템을 보호 하기 위해 최신 스캐닝 정보를 사용 하 고 있는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79206-109">Configuring and monitoring the health of the updates makes sure that the most current scanning information is being used to protect both Office Communications Server and file-system.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="79206-110">Lync server 2013 및 Lync Server에 대 한 Forefront Security를 실행 하는 서버에서 타사의 파일 수준 바이러스 백신 소프트웨어를 사용 하는 경우 Lync Server 및 Lync server 용 Forefront Security이 설치 되어 있는 폴더가 검사 되지 않도록 해야 합니다. 손상 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="79206-110">When using a third-party, file-level antivirus software on a server that runs Lync Server 2013 and Forefront Security for Lync Server, make sure that the folders in which Forefront Security for Lync Server and the Lync Server are installed are not scanned, to prevent their corruption.</span></span> <span data-ttu-id="79206-111">제외의 전체 목록은를 참조 <A class=uri href="http://support.microsoft.com/kb/943620">http://support.microsoft.com/kb/943620</A>하세요.</span><span class="sxs-lookup"><span data-stu-id="79206-111">For the full list of exclusions, see <A class=uri href="http://support.microsoft.com/kb/943620">http://support.microsoft.com/kb/943620</A>.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

