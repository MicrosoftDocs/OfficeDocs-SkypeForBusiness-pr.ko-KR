---
title: 'Lync Server 2013: SQL Server에 대한 시스템 요구 사항'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: System requirements for SQL Server
ms:assetid: 9c235085-cbfa-4e9e-9cec-3f5749039a6b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205112(v=OCS.15)
ms:contentKeyID: 48184904
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4d8e8bb923fd10d505eb9e1b02b0b0ee31612d40
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975354"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="system-requirements-for-sql-server-in-lync-server-2013"></a><span data-ttu-id="351ed-102">Lync Server 2013의 SQL Server에 대한 시스템 요구 사항</span><span class="sxs-lookup"><span data-stu-id="351ed-102">System requirements for SQL Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="351ed-103">_**마지막으로 수정한 주제:** 2013-10-25_</span><span class="sxs-lookup"><span data-stu-id="351ed-103">_**Topic Last Modified:** 2013-10-25_</span></span>

<span data-ttu-id="351ed-104">Enterprise Edition server를 배포 하기 전에 하드웨어 요구 사항을 충족 하는 전용 컴퓨터에 Microsoft SQL Server 2008 R2 또는 Microsoft SQL Server 2012을 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="351ed-104">Before you deploy Enterprise Edition server, install Microsoft SQL Server 2008 R2 or Microsoft SQL Server 2012 on a dedicated computer that meets the hardware requirements.</span></span> <span data-ttu-id="351ed-105">하드웨어 요구 사항에 대 한 자세한 내용은 지원 가능성 설명서의 [Lync server 2013에 대 한 서버 하드웨어 플랫폼](lync-server-2013-server-hardware-platforms.md) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="351ed-105">For details about hardware requirements, see [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md) in the Supportability documentation.</span></span> <span data-ttu-id="351ed-106">소프트웨어 요구 사항에 대 한 자세한 내용은 지원 가능성 설명서의 [Lync Server 2013에서 데이터베이스 소프트웨어 지원을](lync-server-2013-database-software-support.md) 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="351ed-106">For details about software requirements, see [Database software support in Lync Server 2013](lync-server-2013-database-software-support.md) in the Supportability documentation.</span></span> <span data-ttu-id="351ed-107">배포에 필요한 권한에 대 한 자세한 내용은 [Lync server 2013에서 SQL Server에 대 한 배포 권한을](lync-server-2013-deployment-permissions-for-sql-server.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="351ed-107">For information about the permissions necessary for deployment, see [Deployment permissions for SQL Server in Lync Server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).</span></span>

<span data-ttu-id="351ed-108">프런트 엔드 풀을 만들기 전에 SQL Server 구성 관리자를 사용 하 여 서버에 대 한 포트를 정의 하 고 Windows 방화벽에서 포트를 열어 특정 포트를 통해 Lync Server 2013에서 SQL Server에 액세스할 수 있도록 Windows 방화벽을 구성 해야 합니다. 고급 보안.</span><span class="sxs-lookup"><span data-stu-id="351ed-108">Before you create the Front End pool, you must also configure Windows Firewall to allow Lync Server 2013 access to SQL Server over specific ports by defining ports for the server using SQL Server Configuration Manager and opening ports in Windows Firewall with Advanced Security.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

