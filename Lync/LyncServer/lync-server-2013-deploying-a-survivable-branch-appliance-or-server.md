---
title: 'Lync Server 2013: Sba (survivable Branch 기기 또는 서버 배포'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying a Survivable Branch Appliance or Server
ms:assetid: cb780c14-dc5f-41ba-8092-f20ae905bd16
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398849(v=OCS.15)
ms:contentKeyID: 48185643
ms.date: 12/11/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 258f53cf16287b29c739c5a232376fa629b401f6
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48531355"
---
# <a name="deploying-a-survivable-branch-appliance-or-server-with-lync-server-2013"></a><span data-ttu-id="2d5f5-102">Lync Server 2013을 사용 하 여 Sba (survivable 분기 어플라이언스 또는 서버 배포</span><span class="sxs-lookup"><span data-stu-id="2d5f5-102">Deploying a Survivable Branch Appliance or Server with Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2d5f5-103">_**마지막으로 수정 된 항목:** 2014-12-10_</span><span class="sxs-lookup"><span data-stu-id="2d5f5-103">_**Topic Last Modified:** 2014-12-10_</span></span>

<span data-ttu-id="2d5f5-104">복구 가능한 Enterprise Voice는 중앙 사이트에 대 한 링크를 사용할 수 없는 경우 분기 사이트의 복구 기능을 제공 하는 지속적인 엔터프라이즈 음성 서비스를 분기할 수 있음을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d5f5-104">Resilient Enterprise Voice refers to branch-site resiliency, that is, the ability to provide continuous Enterprise Voice service to branch site users in the event that the link to the central site becomes unavailable.</span></span>

<span data-ttu-id="2d5f5-105">중소 규모의 분기 사이트 (25 ~ 1000 명의 사용자가 있는 분기 사이트)의 경우 기본 제공 PSTN 게이트웨이 또는 SIP 트렁크를 전화 서비스 공급자에 게 사용 하 여 PSTN (공중 전화망) 통화를 종료 하는 Sba (survivable Branch 기기를 배포 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="2d5f5-105">For small and medium-sized branch sites (branch sites with 25 to 1,000 users), we recommend deploying a Survivable Branch Appliance, which will terminate public switched telephone network (PSTN) calls by using its built-in PSTN gateway or a SIP trunk to a telephone service provider.</span></span> <span data-ttu-id="2d5f5-106">Sba (survivable 분기 기기는 Windows Server 2008 R2 운영 체제, Lync Server 2013 등록자, 중재 서버 소프트웨어 및 PSTN 게이트웨이를 단일 기기 섀시에 실행 하는 블레이드 서버가 포함 된 타사 장치입니다.</span><span class="sxs-lookup"><span data-stu-id="2d5f5-106">A Survivable Branch Appliance is a third-party device that includes a blade server running the Windows Server 2008 R2 operating system, Lync Server 2013 Registrar, Mediation Server software, and a PSTN gateway, all in a single appliance chassis.</span></span>

<span data-ttu-id="2d5f5-107">5000 사용자에 게 1000이 고 복구 가능한 WAN이 없는 분기 사이트의 경우에는 Sba (survivable 분기 서버를 PSTN 게이트웨이 또는 SIP 트렁크에 연결 하 여 전화 서비스 공급자에 게 제공 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="2d5f5-107">For branch sites with 1,000 to 5,000 users and no resilient WAN, we recommend a Survivable Branch Server connected to either a PSTN gateway or a SIP trunk to a telephone service provider.</span></span> <span data-ttu-id="2d5f5-108">Sba (survivable 분기 서버는 등록자 및 중재 서버 소프트웨어가 설치 되어 있는 Windows Server 기반 컴퓨터입니다.</span><span class="sxs-lookup"><span data-stu-id="2d5f5-108">A Survivable Branch Server is a Windows Server-based computer that has Registrar and Mediation Server software installed on it.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="2d5f5-109">5000 개 보다 많은 사용자와 전용 Lync Server 관리자가 포함 된 분기 사이트의 경우에는 중앙 사이트와는 별도로 전체 Lync Server 2013 배포를 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="2d5f5-109">For branch sites with more than 5,000 users and dedicated Lync Server administrators, we recommend a full Lync Server 2013 deployment, separate from that of the central site.</span></span><BR><span data-ttu-id="2d5f5-110">필수 구성 요소 및 계획 고려 사항을 포함 하 여 조직의 분기 사이트에 대 한 최상의 복구 솔루션을 선택 하는 방법에 대 한 자세한 내용은 계획 설명서에서 <A href="lync-server-2013-branch-site-resiliency-requirements.md">Lync Server 2013에 대 한 분기 사이트 복구 요구 사항</A> 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="2d5f5-110">For details about choosing the best resiliency solution for the branch sites in your organization, including prerequisites and planning considerations, see <A href="lync-server-2013-branch-site-resiliency-requirements.md">Branch-site resiliency requirements for Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="2d5f5-111">Lync Server Sba (survivable Branch 기기에 속한 사용자는 새 채팅방을 만들거나 기존 채팅방에 대 한 대화방 카드를 볼 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2d5f5-111">Users who are homed on a Lync Server Survivable Branch Appliance are unable to create new chat rooms or view the room card for existing rooms.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="2d5f5-112">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="2d5f5-112">In This Section</span></span>

  - [<span data-ttu-id="2d5f5-113">Lync Server 2013을 사용 하 여 Sba (survivable 분기 어플라이언스 또는 서버 배포-중앙 사이트 작업</span><span class="sxs-lookup"><span data-stu-id="2d5f5-113">Deploying a Survivable Branch Appliance or Server with Lync Server 2013 - central site tasks</span></span>](lync-server-2013-deploying-a-survivable-branch-appliance-or-server-central-site-tasks.md)

  - [<span data-ttu-id="2d5f5-114">Lync Server 2013-분기 사이트 작업을 사용 하 여 Sba (survivable Branch 기기 또는 서버 배포</span><span class="sxs-lookup"><span data-stu-id="2d5f5-114">Deploy a Survivable Branch Appliance or Server with Lync Server 2013 - branch site task</span></span>](lync-server-2013-deploy-a-survivable-branch-appliance-or-server-branch-site-task.md)

  - [<span data-ttu-id="2d5f5-115">Lync Server 2013에서 분기 사이트 복구를 위한 사용자 구성</span><span class="sxs-lookup"><span data-stu-id="2d5f5-115">Configuring users for branch site resiliency in Lync Server 2013</span></span>](lync-server-2013-configuring-users-for-branch-site-resiliency.md)

  - [<span data-ttu-id="2d5f5-116">Lync Server 2013의 Sba (survivable 분기 어플라이언스 또는 서버에 있는 개인 사용자</span><span class="sxs-lookup"><span data-stu-id="2d5f5-116">Home users on a Survivable Branch Appliance or Server in Lync Server 2013</span></span>](lync-server-2013-home-users-on-a-survivable-branch-appliance-or-server.md)

  - [<span data-ttu-id="2d5f5-117">부록: Lync Server 2013의 Sba (survivable 분기 기기 및 서버</span><span class="sxs-lookup"><span data-stu-id="2d5f5-117">Appendices: Survivable Branch Appliances and Servers in Lync Server 2013</span></span>](lync-server-2013-appendices-survivable-branch-appliances-and-servers.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="2d5f5-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2d5f5-118">See Also</span></span>


[<span data-ttu-id="2d5f5-119">Lync Server 2013 배포</span><span class="sxs-lookup"><span data-stu-id="2d5f5-119">Deploying Lync Server 2013</span></span>](lync-server-2013-deploying-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

