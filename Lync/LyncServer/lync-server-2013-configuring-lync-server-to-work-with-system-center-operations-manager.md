---
title: System Center Operations Manager와 함께 작동 하도록 Lync Server 구성
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Lync Server to work with System Center Operations Manager
ms:assetid: b55a24ab-648b-4142-b3cd-3792860ba872
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205188(v=OCS.15)
ms:contentKeyID: 48185179
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 150b240fe0c2be769e407cacecd8440bd4596ae5
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48506235"
---
# <a name="configuring-lync-server-2013-to-work-with-system-center-operations-manager"></a><span data-ttu-id="f077a-102">System Center Operations Manager에서 작동 하도록 Lync Server 2013 구성</span><span class="sxs-lookup"><span data-stu-id="f077a-102">Configuring Lync Server 2013 to work with System Center Operations Manager</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f077a-103">_**마지막으로 수정 된 항목:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="f077a-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="f077a-104">System Center Operations Manager와 함께 작동 하도록 Microsoft Lync Server 2013 인프라를 구성 하려면 다음 세 가지 작업을 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f077a-104">In order to configure your Microsoft Lync Server 2013 infrastructure to work with System Center Operations Manager you must do three things:</span></span>

  - <span data-ttu-id="f077a-105">기본 System Center Operations Manager 관리 서버를 식별 하 고 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="f077a-105">Identify and configure your primary System Center Operations Manager management server.</span></span> <span data-ttu-id="f077a-106">관리 서버를 구성 하려면 SQL Server를 사용 하 여 백 엔드 데이터베이스를 설정 하는 것은 물론 System Center Operations Manager 2012 또는 System Center Operations Manager 2007 R2를 설치 하는 것이 여기에 해당 합니다.</span><span class="sxs-lookup"><span data-stu-id="f077a-106">Configuring the management server includes installing System Center Operations Manager 2012 or System Center Operations Manager 2007 R2, as well as setting up a back-end database using SQL Server.</span></span> <span data-ttu-id="f077a-107">사용 해야 하는 실제 SQL Server 버전은 사용 중인 System Center Operations Manager의 버전에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="f077a-107">The actual version of SQL Server that you need to be use depends on the version of System Center Operations Manager you are using.</span></span> <span data-ttu-id="f077a-108">자세한 내용은 [Lync server 2013에서 기본 관리 서버 구성을](lync-server-2013-configuring-the-primary-management-server.md)참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="f077a-108">For details, see [Configuring the primary management server in Lync Server 2013](lync-server-2013-configuring-the-primary-management-server.md).</span></span>

  - <span data-ttu-id="f077a-109">모니터링할 Lync Server 컴퓨터를 식별 하 고 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="f077a-109">Identify and configure the Lync Server computers that you want to monitor.</span></span> <span data-ttu-id="f077a-110">System Center Operations Manager를 사용 하 여 Lync Server 컴퓨터를 모니터링 하려면 System Center Operations Manager 에이전트 파일을 설치 하 고 각 서버가 프록시로 작동 하도록 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f077a-110">To monitor a Lync Server computer by using System Center Operations Manager you must install the System Center Operations Manager agent files, and configure each server to act as a proxy.</span></span>

  - <span data-ttu-id="f077a-111">Lync Server *감시자 노드로*작동할 컴퓨터를 식별 하 고 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="f077a-111">Identify and configure the computers that you want to act as Lync Server *watcher nodes*.</span></span> <span data-ttu-id="f077a-112">감시자 노드는 Lync Server 가상 트랜잭션을 주기적으로 실행 하는 컴퓨터로, 시스템에 로그온 하는 기능과 같은 주요 Lync Server 구성 요소를 확인 하는 Windows PowerShell cmdlet 이거나, 인스턴트 메시지를 교환 하는 기능이 정상적으로 작동 하는 컴퓨터입니다.</span><span class="sxs-lookup"><span data-stu-id="f077a-112">Watcher nodes are computers that periodically run Lync Server synthetic transactions, which are Windows PowerShell cmdlets that verify that key Lync Server components, such as the ability to log on to the system or the ability to exchange instant messages are working as expected.</span></span>

<span data-ttu-id="f077a-113">이 섹션의 항목에는 이러한 각 작업을 수행 하기 위한 지침이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f077a-113">The topics in this section contain instructions for carrying out each of these tasks.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="f077a-114">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="f077a-114">In This Section</span></span>

  - [<span data-ttu-id="f077a-115">Lync Server 2013에서 기본 관리 서버 구성</span><span class="sxs-lookup"><span data-stu-id="f077a-115">Configuring the primary management server in Lync Server 2013</span></span>](lync-server-2013-configuring-the-primary-management-server.md)

  - [<span data-ttu-id="f077a-116">Lync Server 2013 관리 팩 설치</span><span class="sxs-lookup"><span data-stu-id="f077a-116">Installing the Lync Server 2013 management packs</span></span>](lync-server-2013-installing-the-lync-server-2013-management-packs.md)

  - [<span data-ttu-id="f077a-117">Lync Server 2013에서 모니터링할 Lync Server 컴퓨터 구성</span><span class="sxs-lookup"><span data-stu-id="f077a-117">Configuring the Lync Server computers that will be monitored in Lync Server 2013</span></span>](lync-server-2013-configuring-the-lync-server-computers-that-will-be-monitored.md)

  - [<span data-ttu-id="f077a-118">Lync Server 2013에서 감시자 노드 설치 및 구성</span><span class="sxs-lookup"><span data-stu-id="f077a-118">Installing and configuring watcher nodes in Lync Server 2013</span></span>](lync-server-2013-installing-and-configuring-watcher-nodes.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

