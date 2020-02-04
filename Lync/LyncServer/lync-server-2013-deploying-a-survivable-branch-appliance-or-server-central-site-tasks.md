---
title: SBA(Survivable Branch Appliance) 또는 지속 가능 분기 서버 배포 - 중앙 사이트 작업
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying a Survivable Branch Appliance or Server - central site tasks
ms:assetid: 0f631a36-fc2e-41cd-8a0d-f27e84f4a89e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398189(v=OCS.15)
ms:contentKeyID: 48183422
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a9aa6d38ec873652feae6ef6a374ee5b771520b1
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41729628"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-a-survivable-branch-appliance-or-server-with-lync-server-2013---central-site-tasks"></a><span data-ttu-id="aaa9c-102">Lync Server 2013을 통해 SBA(Survivable Branch Appliance) 또는 지속 가능 분기 서버 배포 - 중앙 사이트 작업</span><span class="sxs-lookup"><span data-stu-id="aaa9c-102">Deploying a Survivable Branch Appliance or Server with Lync Server 2013 - central site tasks</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="aaa9c-103">_**마지막으로 수정한 주제:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="aaa9c-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="aaa9c-104">중앙 사이트에서이 섹션의 작업을 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="aaa9c-104">Complete the tasks in this section at the central site.</span></span> <span data-ttu-id="aaa9c-105">Survivable Branch 서버를 배포 하는 경우 첫 번째 작업을 건너뜁니다.</span><span class="sxs-lookup"><span data-stu-id="aaa9c-105">If you’re deploying a Survivable Branch Server, skip the first task.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="aaa9c-106">이 섹션의 작업을 수행 하기 전에 다음 조건이 충족 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="aaa9c-106">Before you perform the tasks in this section, the following conditions must be in place:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="aaa9c-107">중앙 사이트에서 Lync Server를 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="aaa9c-107">Lync Server must be set up at the central site.</span></span></P>
> <LI>
> <P><span data-ttu-id="aaa9c-108">지점 사이트의 설치 기술자를 RTCUniversalSBATechnicians 그룹에 추가 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="aaa9c-108">An installation technician at the branch site must be added to the RTCUniversalSBATechnicians group.</span></span></P></LI></UL><span data-ttu-id="aaa9c-109">또한 다음을 수행 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="aaa9c-109">In addition, we recommend that you do the following:</span></span>
> <UL>
> <LI>
> <P><span data-ttu-id="aaa9c-110">각 지점 사이트에 DHCP 서버를 배포 하 여 클라이언트가 IP 주소를 얻을 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="aaa9c-110">Deploy a DHCP server at each branch site to enable clients to obtain IP addresses.</span></span></P>
> <LI>
> <P><span data-ttu-id="aaa9c-111">각 지점 사이트에서 DHCP 서버를 배포 하는 대신 Survivable Branch 기기 또는 Survivable Branch 서버에서 lync server Management Shell cmdlet <STRONG>Set-CsRegistrarConfiguration – EnableDHCPServer $true</STRONG>를 사용 하 여이 서버를 사용할 수 있도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="aaa9c-111">As an alternative to deploying a DHCP server at each branch site, enable Lync Server DHCP on the Survivable Branch Appliance or Survivable Branch Server by using the Lync Server Management Shell cmdlet <STRONG>Set-CsRegistrarConfiguration –EnableDHCPServer $true</STRONG>.</span></span> <span data-ttu-id="aaa9c-112">자세한 내용은 계획 설명서의 <A href="lync-server-2013-branch-site-resiliency-requirements.md">Lync Server 2013의 지점 사이트 복원 요구 사항에 대 한</A> "하드웨어 및 소프트웨어 요구 사항" 섹션을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="aaa9c-112">For details, see the “Hardware and Software Requirements” section of <A href="lync-server-2013-branch-site-resiliency-requirements.md">Branch-site resiliency requirements for Lync Server 2013</A> in the Planning documentation.</span></span></P></LI></UL>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="aaa9c-113">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="aaa9c-113">In This Section</span></span>

  - [<span data-ttu-id="aaa9c-114">Lync Server 2013에서 Active Directory에 SBA(Survivable Branch Appliance) 추가</span><span class="sxs-lookup"><span data-stu-id="aaa9c-114">Add a Survivable Branch Appliance to Active Directory in Lync Server 2013</span></span>](lync-server-2013-add-a-survivable-branch-appliance-to-active-directory.md)

  - [<span data-ttu-id="aaa9c-115">Lync Server 2013에서 토폴로지에 분기 사이트 추가</span><span class="sxs-lookup"><span data-stu-id="aaa9c-115">Add branch sites to your topology in Lync Server 2013</span></span>](lync-server-2013-add-branch-sites-to-your-topology.md)

  - [<span data-ttu-id="aaa9c-116">Lync Server 2013에서 SBA(Survivable Branch Appliance) 또는 지속 가능 분기 서버 정의</span><span class="sxs-lookup"><span data-stu-id="aaa9c-116">Define a Survivable Branch Appliance or Server in Lync Server 2013</span></span>](lync-server-2013-define-a-survivable-branch-appliance-or-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

