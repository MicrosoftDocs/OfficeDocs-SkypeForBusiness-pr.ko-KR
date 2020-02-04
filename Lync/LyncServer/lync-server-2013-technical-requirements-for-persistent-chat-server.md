---
title: 'Lync Server 2013: 영구 채팅 서버에 대 한 기술 요구 사항'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Technical requirements for Persistent Chat Server
ms:assetid: 692b7d99-1bc9-4c99-a050-2bc2be8688b2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398495(v=OCS.15)
ms:contentKeyID: 48184383
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0437f56c5eb5564eb4f85809aefd181c2cbd2eaf
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41746558"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="technical-requirements-for-persistent-chat-server-in-lync-server-2013"></a><span data-ttu-id="cd3a7-102">Lync Server 2013의 영구 채팅 서버에 대 한 기술 요구 사항</span><span class="sxs-lookup"><span data-stu-id="cd3a7-102">Technical requirements for Persistent Chat Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cd3a7-103">_**마지막으로 수정한 주제:** 2013-01-06_</span><span class="sxs-lookup"><span data-stu-id="cd3a7-103">_**Topic Last Modified:** 2013-01-06_</span></span>

<span data-ttu-id="cd3a7-104">영구 채팅 서버를 호스트 하는 각 컴퓨터는 다음 구성 요소를 사용 하 여 기존 Lync Server 2013 토폴로지에 액세스할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd3a7-104">Each computer that hosts Persistent Chat Server must have access to an existing Lync Server 2013 topology with the following components:</span></span>

  - <span data-ttu-id="cd3a7-105">**Lync Server 2013, 프런트 엔드 서버.**  프런트 엔드 서버는 SIP (세션 초기화 프로토콜) 라우팅의 기반 이므로 영구 채팅 서버를 실행 하는 컴퓨터와 영구 채팅 기능을 통해 통신 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd3a7-105">**Lync Server 2013, Front End Server.** The Front End Server is the foundation for Session Initiation Protocol (SIP) routing, which makes communication between computers running Persistent Chat Server and the Persistent Chat functionality possible.</span></span> <span data-ttu-id="cd3a7-106">영구 채팅 서버 배포를 시작 하기 전에 Lync server 2013, Standard Edition 또는 lync Server 프런트 엔드 풀 및 lync server를 실행 하는 다른 모든 내부 컴퓨터의 배포를 조직에 적절 하 게 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd3a7-106">Before you begin to deploy Persistent Chat Server, verify the deployment of Lync Server 2013, Standard Edition, or a Lync Server Front End pool and any other internal computers running Lync Server, as appropriate to your organization.</span></span>

<span data-ttu-id="cd3a7-107">다음 섹션에서는 영구 채팅 서버와 영구 채팅 데이터를 저장 하는 데이터베이스에 대 한 특정 요구 사항에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd3a7-107">The following sections describe the specific requirements for the Persistent Chat Server and the database that stores the Persistent Chat data.</span></span>

<div>

## <a name="persistent-chat-server-requirements"></a><span data-ttu-id="cd3a7-108">영구 채팅 서버 요구 사항</span><span class="sxs-lookup"><span data-stu-id="cd3a7-108">Persistent Chat Server Requirements</span></span>

<span data-ttu-id="cd3a7-109">Lync Server 및 최신 버전의 영구 채팅 서버 배포에 권장 되는 하드웨어에 대 한 자세한 내용은 지원 가능성 설명서의 [Lync server 2013에 대 한 서버 하드웨어 플랫폼](lync-server-2013-server-hardware-platforms.md) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="cd3a7-109">For details about the recommended hardware for deploying Lync Server and the latest version of Persistent Chat Server, see [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md) in the Supportability documentation.</span></span>

<span data-ttu-id="cd3a7-110">Lync Server 및 영구 채팅 서버에 대 한 서버 및 도구 운영 체제 지원에 대 한 자세한 내용은 지원 가능성 설명서의 [Lync server 2013에서 서버 및 도구 운영 체제 지원을](lync-server-2013-server-and-tools-operating-system-support.md) 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="cd3a7-110">For details about the server and tools operating system support for Lync Server and Persistent Chat Server, see [Server and tools operating system support in Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) in the Supportability documentation.</span></span>

<span data-ttu-id="cd3a7-111">영구 채팅 서버 배포에 필요한 추가 소프트웨어에 대 한 자세한 내용은 다음 표를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="cd3a7-111">For details about additional software required for deploying Persistent Chat Server, see the following table.</span></span>

### <a name="persistent-chat-server-software-prerequisites"></a><span data-ttu-id="cd3a7-112">영구 채팅 서버 소프트웨어 필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="cd3a7-112">Persistent Chat Server Software Prerequisites</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="cd3a7-113">소프트웨어</span><span class="sxs-lookup"><span data-stu-id="cd3a7-113">Software</span></span></th>
<th><span data-ttu-id="cd3a7-114">설명</span><span class="sxs-lookup"><span data-stu-id="cd3a7-114">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cd3a7-115">메시지 큐</span><span class="sxs-lookup"><span data-stu-id="cd3a7-115">Message Queuing</span></span></p></td>
<td><p><span data-ttu-id="cd3a7-116">영구 채팅 서버와 영구 채팅 준수 서비스 (배포 된 경우)에서 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd3a7-116">Used by the Persistent Chat Server and Persistent Chat Compliance service, if deployed.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="persistent-chat-server-database-requirements"></a><span data-ttu-id="cd3a7-117">영구 채팅 서버 데이터베이스 요구 사항</span><span class="sxs-lookup"><span data-stu-id="cd3a7-117">Persistent Chat Server Database Requirements</span></span>

<span data-ttu-id="cd3a7-118">영구 채팅 서버는 채팅 기록, 구성, 사용자 프로 비전 데이터를 저장 하기 위해 영구 채팅 데이터베이스를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd3a7-118">Persistent Chat Server uses the Persistent Chat database to store chat history, configuration, and user provisioning data.</span></span> <span data-ttu-id="cd3a7-119">필요에 따라 지속적인 채팅 준수 데이터베이스를 사용 하 여 규정 준수 데이터를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd3a7-119">Optionally, it uses the Persistent Chat compliance database to store compliance data.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="cd3a7-120">Mgc (지속적인 채팅 데이터베이스) 및 mgccomp (준수 데이터베이스)는 SQL Server의 동일한 인스턴스나 다른 SQL 서버에 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd3a7-120">The Persistent Chat database (mgc) and the compliance database (mgccomp) can be located in the same instance of SQL Server or on different SQL Servers.</span></span>



</div>

<span data-ttu-id="cd3a7-121">데이터베이스 서버 플랫폼을 준비 하려면 각 컴퓨터가 하드웨어 요구 사항을 충족 하는지 확인 한 다음 필수 구성 요소 소프트웨어를 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd3a7-121">To prepare a database server platform, be sure that each computer meets the hardware requirements, and then install the prerequisite software.</span></span>

<span data-ttu-id="cd3a7-122">영구 채팅 데이터베이스 서버의 서버 플랫폼에는 Lync Server 백 엔드 데이터베이스 서버와 동일한 하드웨어가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd3a7-122">The server platform for the Persistent Chat database servers requires the same hardware as the Lync Server back-end database server.</span></span> <span data-ttu-id="cd3a7-123">자세한 내용은 지원 가능성 설명서의 [Lync server 2013에 대 한 서버 하드웨어 플랫폼](lync-server-2013-server-hardware-platforms.md) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="cd3a7-123">For details, see [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md) in the Supportability documentation.</span></span>

<span data-ttu-id="cd3a7-124">데이터베이스 서버에서 다음 소프트웨어 응용 프로그램 중 하나가 설치 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd3a7-124">On the database server, be sure that one of the following software applications is installed:</span></span>

  - <span data-ttu-id="cd3a7-125">Microsoft SQL Server 2012.</span><span class="sxs-lookup"><span data-stu-id="cd3a7-125">Microsoft SQL Server 2012.</span></span> <span data-ttu-id="cd3a7-126">Microsoft SQL Server 2012을 설치 하는 방법에 대 한 자세한 내용은에서 [http://go.microsoft.com/fwlink/p/?LinkID=248559](http://go.microsoft.com/fwlink/p/?linkid=248559)"SQL Server 2012 설치"를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="cd3a7-126">For details about how to install Microsoft SQL Server 2012, see "Install SQL Server 2012" at [http://go.microsoft.com/fwlink/p/?LinkID=248559](http://go.microsoft.com/fwlink/p/?linkid=248559).</span></span>

  - <span data-ttu-id="cd3a7-127">Microsoft SQL Server 2008 R2.</span><span class="sxs-lookup"><span data-stu-id="cd3a7-127">Microsoft SQL Server 2008 R2.</span></span> <span data-ttu-id="cd3a7-128">Microsoft SQL Server 2008 R2를 설치 하는 방법에 대 한 자세한 내용은에서 [http://go.microsoft.com/fwlink/?LinkId=275702](http://go.microsoft.com/fwlink/?linkid=275702)"Sql server 설치 (sql Server 2008 R2)"를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="cd3a7-128">For details about how to install Microsoft SQL Server 2008 R2, see "SQL Server Installation (SQL Server 2008 R2)" at [http://go.microsoft.com/fwlink/?LinkId=275702](http://go.microsoft.com/fwlink/?linkid=275702).</span></span>

</div>

<div>

## <a name="persistent-chat-server-certificate-requirements"></a><span data-ttu-id="cd3a7-129">영구 채팅 서버 인증서 요구 사항</span><span class="sxs-lookup"><span data-stu-id="cd3a7-129">Persistent Chat Server Certificate Requirements</span></span>

<span data-ttu-id="cd3a7-130">인증서를 획득 하 고 SQL Server 데이터베이스를 만들고 파일 저장소를 만드는 방법에 대 한 자세한 내용은 배포 설명서에서 [Lync Server 2013 배포](lync-server-2013-deploying-lync-server.md) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="cd3a7-130">For details about acquiring certificates, creating the SQL Server database, and creating file stores, see [Deploying Lync Server 2013](lync-server-2013-deploying-lync-server.md) in the Deployment documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

