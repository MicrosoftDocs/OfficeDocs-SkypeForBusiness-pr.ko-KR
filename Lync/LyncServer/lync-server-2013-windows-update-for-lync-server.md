---
title: 'Lync Server 2013: Lync Server용 Windows Update'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Windows Update for Lync Server 2013
ms:assetid: fe26ab32-b1a9-421d-9227-506703d4b834
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn518337(v=OCS.15)
ms:contentKeyID: 62625495
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 57949b051468241e18d8a121e9d79bc1fdb378f7
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727398"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="windows-update-for-lync-server-2013"></a><span data-ttu-id="7be98-102">Lync Server 2013용 Windows Update</span><span class="sxs-lookup"><span data-stu-id="7be98-102">Windows Update for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7be98-103">_**마지막으로 수정한 주제:** 2013-12-05_</span><span class="sxs-lookup"><span data-stu-id="7be98-103">_**Topic Last Modified:** 2013-12-05_</span></span>

<span data-ttu-id="7be98-104">Windows Update Services를 사용 하 여 업데이트 및 보안 업데이트를 자주 확인 하 고 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="7be98-104">Frequently check for and apply updates and security updates using Windows Update Services.</span></span> <span data-ttu-id="7be98-105">이렇게 하면 공격자가 관리자 권한으로 Microsoft Lync Server 2013를 실행 하는 서버에 액세스할 수 있고 Lync Server 2013을 손상 시킬 수 있는 다른 시스템 구성 요소의 취약점이 방지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7be98-105">Doing so helps prevents vulnerabilities in other system components that might lead to attackers being able to gain access to servers running Microsoft Lync Server 2013 with administrator rights and thereby compromise Lync Server 2013.</span></span>

<span data-ttu-id="7be98-106">Microsoft SQL Server 2008 Express (64 비트 버전)에 대 한 업데이트는 각 Lync Server 2013 Standard Edition server (백 엔드 데이터베이스용) 및 다른 모든 Lync Server 2013 서버 역할 (로컬 구성 저장소의 경우)에서 실행 되며,이를 업그레이드 하지 않은 경우 SQL Server 2008 R2 Express 데이터베이스</span><span class="sxs-lookup"><span data-stu-id="7be98-106">Updates for Microsoft SQL Server 2008 Express (64-bit edition) runs on each Lync Server 2013 Standard Edition server (for the back-end database) and on all other Lync Server 2013 server roles (for the Local Configuration Store), unless you have upgraded these databases to SQL Server 2008 R2 Express.</span></span> <span data-ttu-id="7be98-107">프런트 엔드 풀, 모니터링 데이터베이스 및 보관 데이터베이스의 백 엔드 데이터베이스에 있는 SQL Server와 같이 루틴 보안 업데이트 유지 관리의 일부로 이러한 데이터베이스를 고려해 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7be98-107">You should consider these databases as part of routine security update maintenance, as should SQL Server on the back-end database of a Front End pool, the Monitoring database, and the Archiving database.</span></span>

<div>

## <a name="best-practice"></a><span data-ttu-id="7be98-108">모범 사례</span><span class="sxs-lookup"><span data-stu-id="7be98-108">Best Practice</span></span>

  - <span data-ttu-id="7be98-109">Windows Update를 사용 하 여 최신 상태로 유지</span><span class="sxs-lookup"><span data-stu-id="7be98-109">Keep current with Windows Update.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

