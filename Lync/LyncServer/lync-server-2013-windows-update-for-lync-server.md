---
title: 'Lync Server 2013: Lync Server 용 Windows Update'
description: 'Lync Server 2013: Lync Server 용 Windows Update'
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
ms.openlocfilehash: fe4b6d201a35584fceae5628b91631b48b30faae
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48546064"
---
# <a name="windows-update-for-lync-server-2013"></a><span data-ttu-id="f0197-103">Lync Server 2013 용 Windows Update</span><span class="sxs-lookup"><span data-stu-id="f0197-103">Windows Update for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f0197-104">_**마지막으로 수정 된 항목:** 2013-12-05_</span><span class="sxs-lookup"><span data-stu-id="f0197-104">_**Topic Last Modified:** 2013-12-05_</span></span>

<span data-ttu-id="f0197-105">Windows Update Services를 통해 업데이트와 보안 업데이트를 자주 확인하고 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="f0197-105">Frequently check for and apply updates and security updates using Windows Update Services.</span></span> <span data-ttu-id="f0197-106">이렇게 하면 공격자가 관리자 권한으로 Microsoft Lync Server 2013을 실행 하는 서버에 액세스 하 고 Lync Server 2013를 손상 시킬 수 있는 다른 시스템 구성 요소의 취약성을 방지할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0197-106">Doing so helps prevents vulnerabilities in other system components that might lead to attackers being able to gain access to servers running Microsoft Lync Server 2013 with administrator rights and thereby compromise Lync Server 2013.</span></span>

<span data-ttu-id="f0197-107">Microsoft SQL Server 2008 Express (64 비트 버전)에 대 한 업데이트는 이러한 데이터베이스를 SQL Server 2008 R2 Express로 업그레이드 하지 않은 경우 백 엔드 데이터베이스용 각 Lync server 2013 Standard Edition 서버 및 다른 모든 Lync Server 2013 서버 역할 (로컬 구성 저장소)에서 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f0197-107">Updates for Microsoft SQL Server 2008 Express (64-bit edition) runs on each Lync Server 2013 Standard Edition server (for the back-end database) and on all other Lync Server 2013 server roles (for the Local Configuration Store), unless you have upgraded these databases to SQL Server 2008 R2 Express.</span></span> <span data-ttu-id="f0197-108">프런트 엔드 풀의 백 엔드 데이터베이스에 있는 SQL Server, 모니터링 데이터베이스 및 보관 데이터베이스와 같이 이러한 데이터베이스는 일상적인 보안 업데이트 유지 관리의 일부로 생각해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0197-108">You should consider these databases as part of routine security update maintenance, as should SQL Server on the back-end database of a Front End pool, the Monitoring database, and the Archiving database.</span></span>

<div>

## <a name="best-practice"></a><span data-ttu-id="f0197-109">유용한 정보</span><span class="sxs-lookup"><span data-stu-id="f0197-109">Best Practice</span></span>

  - <span data-ttu-id="f0197-110">Windows Update를 통해 최신 상태를 유지합니다.</span><span class="sxs-lookup"><span data-stu-id="f0197-110">Keep current with Windows Update.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

