---
title: 'Lync Server 2013: 토폴로지를 게시 하기 위한 요구 사항'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Requirements to publish a topology
ms:assetid: 841cdf5d-d884-414d-ab50-3bb681b622ed
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg195733(v=OCS.15)
ms:contentKeyID: 48184688
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c9f4186a351876b874a8b84963f9923369511f65
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48511825"
---
# <a name="requirements-to-publish-a-topology-in-lync-server-2013"></a><span data-ttu-id="2f72d-102">Lync Server 2013의 토폴로지 게시 요구 사항</span><span class="sxs-lookup"><span data-stu-id="2f72d-102">Requirements to publish a topology in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2f72d-103">_**마지막으로 수정 된 항목:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="2f72d-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="2f72d-104">이 항목에서는 토폴로지 작성기 또는 Lync Server 2013 관리 셸 명령줄 인터페이스를 사용 하 여 토폴로지를 게시 하는 것과 관련 된 인프라 및 소프트웨어 요구 사항에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f72d-104">This topic describes the infrastructure and software requirements that are specific to publishing a topology, whether by using Topology Builder or the Lync Server 2013 Management Shell command-line interface.</span></span> <span data-ttu-id="2f72d-105">이러한 요구 사항은 모든 Lync Server 2013 관리 도구에 적용 되는 일반적인 운영 체제, 소프트웨어 및 사용 권한 요구 사항 외에도 해당 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2f72d-105">These requirements are in addition to the general operating system, software, and permissions requirements applicable to all Lync Server 2013 administrative tools.</span></span> <span data-ttu-id="2f72d-106">토폴로지를 게시 하기 전에 모든 관리 도구 요구 사항을 충족 하는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f72d-106">Make sure that you satisfy all administrative tools requirements before you publish a topology.</span></span>

  - <span data-ttu-id="2f72d-107">Active Directory 도메인 서비스 준비 단계가 이미 완료 되도록 만들려는 Lync Server 2013 배포의 동일한 도메인 또는 포리스트에 가입 된 컴퓨터에서 토폴로지 작성기를 실행 해야 하며, 해당 컴퓨터의 관리 도구를 사용 하 여 토폴로지를 성공적으로 게시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f72d-107">You must run Topology Builder on a computer that is joined to the same domain or forest of the Lync Server 2013 deployment you are creating so that Active Directory Domain Services preparation steps are already completed, enabling you to use the administrative tools on that computer to successfully publish your topology.</span></span>

  - <span data-ttu-id="2f72d-p102">토폴로지에 정의된 컴퓨터는 에지 서버를 제외하고 도메인 및 AD DS에 참여해야 합니다. 하지만 토폴로지를 게시할 때 컴퓨터가 온라인 상태일 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2f72d-p102">The computers defined in the topology must be joined to the domain, except for Edge Servers, and in AD DS. However, the computers do not need to be online when you publish the topology.</span></span>

  - <span data-ttu-id="2f72d-110">풀에 대한 파일 공유를 만들고 원격 사용자에게 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f72d-110">The file share for the pool must be created and available to remote users.</span></span>

  - <span data-ttu-id="2f72d-111">Enterprise Edition 프런트 엔드 풀을 게시 하려면 SQL Server 기반 백 엔드 서버가 서버를 배포할 도메인에 가입 하 고, 온라인 상태 이며, 원격 사용자가 사용할 수 있도록 적절 한 방화벽 규칙을 사용 하 여 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f72d-111">In order to publish an Enterprise Edition Front End pool, the SQL Server-based Back End Server must be joined to the domain in which you are deploying the servers, online, and configured with the appropriate firewall rules to make it available to remote users.</span></span> <span data-ttu-id="2f72d-112">방화벽 예외 지정에 대 한 자세한 내용은 [Lync server 2013을 사용 하 여 SQL Server에 대 한 방화벽 요구 사항 이해](lync-server-2013-understanding-firewall-requirements-for-sql-server.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="2f72d-112">For details about specifying firewall exceptions, see [Understanding firewall requirements for SQL Server with Lync Server 2013](lync-server-2013-understanding-firewall-requirements-for-sql-server.md).</span></span> <span data-ttu-id="2f72d-113">SQL Server 구성에 대 한 자세한 내용은 [CONFIGURE Sql Server For Lync server 2013](lync-server-2013-configure-sql-server-for-lync-server.md)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="2f72d-113">For other details about configuring SQL Server, see [Configure SQL Server for Lync Server 2013](lync-server-2013-configure-sql-server-for-lync-server.md).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="2f72d-114">Standard Edition 서버에는 게시 된 구성을 허용 하는 배치 된 데이터베이스가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f72d-114">Standard Edition server has a collocated database that will accept the published configuration.</span></span> <span data-ttu-id="2f72d-115">먼저 Lync Server 배포 마법사에서 <STRONG>최초 Standard Edition server 설치 준비</STRONG> 작업을 실행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f72d-115">You must first run the <STRONG>Prepare first Standard Edition server</STRONG> setup task in the Lync Server Deployment Wizard.</span></span>

    
    </div>

<div>

## <a name="see-also"></a><span data-ttu-id="2f72d-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2f72d-116">See Also</span></span>


[<span data-ttu-id="2f72d-117">Lync Server 2013에서 토폴로지 게시</span><span class="sxs-lookup"><span data-stu-id="2f72d-117">Publish the topology in Lync Server 2013</span></span>](lync-server-2013-publish-the-topology.md)  
[<span data-ttu-id="2f72d-118">Lync Server 2013에서 설치 권한 위임</span><span class="sxs-lookup"><span data-stu-id="2f72d-118">Delegate setup permissions in Lync Server 2013</span></span>](lync-server-2013-delegate-setup-permissions.md)  


[<span data-ttu-id="2f72d-119">Lync Server 2013의 관리 도구 소프트웨어 요구 사항</span><span class="sxs-lookup"><span data-stu-id="2f72d-119">Administrative tools software requirements in Lync Server 2013</span></span>](lync-server-2013-administrative-tools-software-requirements.md)  
[<span data-ttu-id="2f72d-120">Lync Server 2013의 서버 및 도구 운영 체제 지원</span><span class="sxs-lookup"><span data-stu-id="2f72d-120">Server and tools operating system support in Lync Server 2013</span></span>](lync-server-2013-server-and-tools-operating-system-support.md)  


[<span data-ttu-id="2f72d-121">Lync Server 2013의 설정 및 관리에 필요한 관리자 권한 및 사용 권한</span><span class="sxs-lookup"><span data-stu-id="2f72d-121">Administrator rights and permissions required for setup and administration of Lync Server 2013</span></span>](lync-server-2013-administrator-rights-and-permissions-required-for-setup-and-administration.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

