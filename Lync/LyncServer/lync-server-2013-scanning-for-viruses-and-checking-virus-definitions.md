---
title: 'Lync Server 2013: 바이러스 검사 및 바이러스 정의 확인'
description: 'Lync Server 2013: 바이러스를 검색 하 고 바이러스 정의를 확인 합니다.'
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
ms.openlocfilehash: c06b08b5e902857e95cdefc206cdbfa860ef748c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48578654"
---
# <a name="scanning-for-viruses-and-checking-virus-definitions-in-lync-server-2013"></a><span data-ttu-id="8c6e0-103">Lync Server 2013에서 바이러스 검사 및 바이러스 정의 확인</span><span class="sxs-lookup"><span data-stu-id="8c6e0-103">Scanning for viruses and checking virus definitions in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8c6e0-104">_**마지막으로 수정 된 항목:** 2014-05-01_</span><span class="sxs-lookup"><span data-stu-id="8c6e0-104">_**Topic Last Modified:** 2014-05-01_</span></span>

<span data-ttu-id="8c6e0-105">IM 수준 바이러스 백신 제품을 설치 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="8c6e0-105">We highly recommend installing an IM-level antivirus product.</span></span> <span data-ttu-id="8c6e0-106">IM은 조직 전체에서 바이러스 및 악성 소프트웨어를 빠르게 분배 하기 위해 잘 알려진 출처입니다.</span><span class="sxs-lookup"><span data-stu-id="8c6e0-106">IM is a well-known source for quickly spreading both virus and malicious software throughout an organization.</span></span> <span data-ttu-id="8c6e0-107">Lync Server에 대 한 Microsoft Forefront® Security에서는 바이러스, 악성 소프트웨어, 파일 및 키워드 필터 보호와 Office Communications Server와의 원활한 통합을 통해 다중 엔진 검색 기능을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c6e0-107">Microsoft Forefront® Security for Lync Server provides multi-engine scanning with virus, malicious software, file and keyword filter protection and seamless integration with Office Communications Server.</span></span>

<span data-ttu-id="8c6e0-108">Lync Server에 대 한 Forefront 보안 외에도 파일 수준 바이러스 백신 솔루션을 설치 하 여 서버의 파일 시스템을 보호 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="8c6e0-108">In addition to Forefront Security for Lync Server, we also highly recommend installing a file-level, antivirus solution to protect the server’s file system.</span></span>

<span data-ttu-id="8c6e0-109">스캐너 엔진 및 바이러스 정의를 업데이트 된 상태로 유지 하는 것이 매우 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c6e0-109">Keeping scanner engines and virus definitions updated is very important.</span></span> <span data-ttu-id="8c6e0-110">업데이트 상태를 구성 하 고 모니터링 하면 최신 검색 정보를 사용 하 여 Office Communications Server와 파일 시스템을 모두 보호 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c6e0-110">Configuring and monitoring the health of the updates makes sure that the most current scanning information is being used to protect both Office Communications Server and file-system.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="8c6e0-111">Lync server 2013을 실행 하는 서버에서 타사 파일 수준 바이러스 백신 소프트웨어를 사용 하는 경우 lync server에 대해 Forefront Security을 설치 하는 경우에는이를 방지 하기 위해 Lync 서버 및 Lync Server를 설치한 폴더를 검사 하지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c6e0-111">When using a third-party, file-level antivirus software on a server that runs Lync Server 2013 and Forefront Security for Lync Server, make sure that the folders in which Forefront Security for Lync Server and the Lync Server are installed are not scanned, to prevent their corruption.</span></span> <span data-ttu-id="8c6e0-112">전체 제외 항목 목록은를 참조 하세요 <A class=uri href="https://support.microsoft.com/kb/943620">https://support.microsoft.com/kb/943620</A> .</span><span class="sxs-lookup"><span data-stu-id="8c6e0-112">For the full list of exclusions, see <A class=uri href="https://support.microsoft.com/kb/943620">https://support.microsoft.com/kb/943620</A>.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

