---
title: 'Lync Server 2013: 기존 Lync Server 2013 Enterprise에 Lync Server 2013 Standard Edition 배포'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying Lync Server 2013 Standard Edition into an existing Lync Server 2013 Enterprise
ms:assetid: 05ea128d-6c94-49b3-b28b-477367196425
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398112(v=OCS.15)
ms:contentKeyID: 48183297
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4b344b3e4ffbeb5d429db2d7220be5bbca9fbed6
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030441"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-lync-server-2013-standard-edition-into-an-existing-lync-server-2013-enterprise"></a><span data-ttu-id="59015-102">Lync Server 2013 Standard Edition을 기존 Lync Server 2013 Enterprise에 배포</span><span class="sxs-lookup"><span data-stu-id="59015-102">Deploying Lync Server 2013 Standard Edition into an existing Lync Server 2013 Enterprise</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="59015-103">_**마지막으로 수정 된 항목:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="59015-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="59015-104">Standard Edition 서버를 기존 Enterprise Edition 배포에 배포 하는 것은 추가 서버 역할을 배포 하는 것과 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="59015-104">Deploying a Standard Edition server into an existing Enterprise Edition deployment is similar to deploying additional server roles.</span></span> <span data-ttu-id="59015-105">Standard Edition 서버를 다른 사이트에 배포 하 여 해당 사이트의 사용자가 WAN (광역 네트워크)을 통해 프런트 엔드 풀이 아닌 Standard Edition 서버에 배치할 수 있도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="59015-105">A Standard Edition server might be deployed to another site, allowing for users in that site to be homed on the Standard Edition server rather than the Front End pool across a wide area network (WAN).</span></span> <span data-ttu-id="59015-106">해당 사이트에서 새 사이트 및 서버를 설치 하는 절차는 [Lync Server 2013 설명서 배포](lync-server-2013-deploying-lync-server.md) 의 다른 섹션에 이미 정의 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="59015-106">The procedures for installing the new site and servers in that site are already defined in other sections of the [Deploying Lync Server 2013](lync-server-2013-deploying-lync-server.md) documentation.</span></span>

<div id="sectionSection0" class="section">

<span data-ttu-id="59015-107">**새 사이트를 정의하려면**</span><span class="sxs-lookup"><span data-stu-id="59015-107">**To define a new site**</span></span>

1.  <span data-ttu-id="59015-108">토폴로지 작성기 시작: **시작**, **모든 프로그램**, **Microsoft lync server 2013**을 차례로 클릭 한 다음 **Lync server 토폴로지 작성기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="59015-108">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="59015-109">콘솔 트리에서 **Lync Server 2013**를 마우스 오른쪽 단추로 클릭 한 다음 **새 중앙 사이트**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="59015-109">In the console tree, right-click **Lync Server 2013**, and then click **New Central Site**.</span></span>

3.  <span data-ttu-id="59015-110">**사이트 지정** 페이지에서 사이트 이름을 지정하고 원하는 경우 설명을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="59015-110">On the **Identify the site** page, give a name to the site and optionally enter a description.</span></span>

4.  <span data-ttu-id="59015-111">절차에 따라 사이트 토폴로지의 나머지 부분을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="59015-111">Follow the procedures for defining the rest of the site topology.</span></span> <span data-ttu-id="59015-112">자세한 내용은 [Lync Server 2013에서 토폴로지 정의 및 구성을](lync-server-2013-defining-and-configuring-the-topology.md)참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="59015-112">For details, see [Defining and configuring the topology in Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md).</span></span>

5.  <span data-ttu-id="59015-113">업데이트된 토폴로지를 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="59015-113">Publish the updated topology.</span></span> <span data-ttu-id="59015-114">자세한 내용은 Publish the [topology in The Lync Server 2013](lync-server-2013-publish-the-topology.md)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="59015-114">For details, see [Publish the topology in Lync Server 2013](lync-server-2013-publish-the-topology.md).</span></span>

6.  <span data-ttu-id="59015-115">Standard Edition 서버를 설정 하 고 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="59015-115">Set up and install a Standard Edition server.</span></span>
    
    <div>
    

    > [!Caution]  
    > <span data-ttu-id="59015-116">Standard Edition server만을 사용 하 여 환경을 배포한 경우에는 <STRONG>첫 번째 Standard edition Server 준비</STRONG> 링크를 사용 하 여 새 Standard edition 서버에 초기 데이터베이스 파일을 설치 하는 방법으로 Lync Server 배포 마법사에서 설치 프로세스를 시작 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="59015-116">If you have deployed an environment with only a Standard Edition server, you would have begun the setup process from the Lync Server Deployment Wizard by using the <STRONG>Prepare first Standard Edition server</STRONG> link to install the initial database files to the new Standard Edition server.</span></span> <span data-ttu-id="59015-117">기존 Lync Server 2013 배포에 Standard Edition server를 설치할 때는 해당 프로세스를 수행 <STRONG>하지 마십시오</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="59015-117"><STRONG>Do not</STRONG> follow that process when installing a Standard Edition server into an existing Lync Server 2013 deployment.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

