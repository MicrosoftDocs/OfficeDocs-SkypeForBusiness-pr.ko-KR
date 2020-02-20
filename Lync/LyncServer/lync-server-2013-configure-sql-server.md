---
title: 'Lync Server 2013: SQL Server 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure SQL Server
ms:assetid: 84504918-cb4f-4b2f-be17-a70770b69025
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398669(v=OCS.15)
ms:contentKeyID: 48184699
ms.date: 01/22/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3d46a857f0f9ef55dc375b4d465205668fe5f79e
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145717"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-sql-server-in-lync-server-2013"></a><span data-ttu-id="c6714-102">Lync Server 2013에서 SQL Server 구성</span><span class="sxs-lookup"><span data-stu-id="c6714-102">Configure SQL Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c6714-103">_**마지막으로 수정 된 항목:** 2015-01-22_</span><span class="sxs-lookup"><span data-stu-id="c6714-103">_**Topic Last Modified:** 2015-01-22_</span></span>

<span data-ttu-id="c6714-104">배포 하는 각 데이터베이스에 대해 데이터베이스 서버에서 배치 된 수 있는 Lync Server 2013 배포의 모든 데이터베이스에 대해 단일 SQL Server 인스턴스를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c6714-104">For each database that you deploy, you can use a single SQL Server instance for all databases for your Lync Server 2013 deployment that can be collocated on a database server.</span></span> <span data-ttu-id="c6714-105">데이터베이스 배치에 대 한 자세한 내용은 지원 가능성 설명서에서 [Lync server 2013의 Supported server 배치](lync-server-2013-supported-server-collocation.md) 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="c6714-105">For details about database collocation, see [Supported server collocation in Lync Server 2013](lync-server-2013-supported-server-collocation.md) in the Supportability documentation.</span></span>

<span data-ttu-id="c6714-106">또한 토폴로지 작성기에서 데이터베이스를 설정 하는 단계를 완료 하거나 Windows PowerShell cmdlet을 사용 하 여 데이터베이스를 수동으로 만드는 방법 보다 각 SQL Server 인스턴스를 설치 하 고 사용 가능한 상태로 두어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6714-106">Additionally, each SQL Server instance must be installed and available prior to completing the steps in Topology Builder that set up the databases, or manually creating the databases with Windows PowerShell cmdlets.</span></span> <span data-ttu-id="c6714-107">SQL Server 지원 가능성에 대 한 자세한 내용은 [하드웨어 설정 (Lync Server 2013](lync-server-2013-hardware-setup.md))을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="c6714-107">For details about SQL Server supportability, see [Hardware setup for Lync Server 2013](lync-server-2013-hardware-setup.md).</span></span>

<div>

## <a name="to-install-microsoft-sql-server-2012"></a><span data-ttu-id="c6714-108">Microsoft SQL Server 2012을 설치 하려면</span><span class="sxs-lookup"><span data-stu-id="c6714-108">To install Microsoft SQL Server 2012</span></span>

  - <span data-ttu-id="c6714-109">Microsoft SQL Server 2012 설명서 <https://technet.microsoft.com/library/bb500395(v=sql.110).aspx>를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c6714-109">See the Microsoft SQL Server 2012 documentation at: <https://technet.microsoft.com/library/bb500395(v=sql.110).aspx>.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

