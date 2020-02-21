---
title: 'Lync Server 2013: 외부 사용자 액세스 배포'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying external user access
ms:assetid: d40c9574-c16b-4fe6-b848-21ae0b7e4f0e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398918(v=OCS.15)
ms:contentKeyID: 48185495
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 960f5d895f821e8d9bbc6fa71f451ee455d88388
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42198331"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deploying-external-user-access-in-lync-server-2013"></a><span data-ttu-id="9e8d2-102">Lync Server 2013에서 외부 사용자 액세스 배포</span><span class="sxs-lookup"><span data-stu-id="9e8d2-102">Deploying external user access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9e8d2-103">_**마지막으로 수정 된 항목:** 2013-09-23_</span><span class="sxs-lookup"><span data-stu-id="9e8d2-103">_**Topic Last Modified:** 2013-09-23_</span></span>

<span data-ttu-id="9e8d2-104">Microsoft Lync Server 2013에 대 한에 지 구성 요소를 배포 하면 인증 및 익명 원격 사용자, 페더레이션 파트너 (XMPP 파트너 포함)를 포함 하 여 조직의 내부 네트워크에 로그인 되지 않은 외부 사용자가 가능 합니다. Lync Server를 사용 하 여 조직 내 다른 사용자와 통신 하기 위한 공용 IM (인스턴트 메시징) 서비스의 모바일 클라이언트 및 사용자</span><span class="sxs-lookup"><span data-stu-id="9e8d2-104">Deploying edge components for Microsoft Lync Server 2013 makes it possible for external users who are not logged into your organization’s internal network, including authenticated and anonymous remote users, federated partners (including XMPP partners), mobile clients and users of public instant messaging (IM) services, to communicate with other users in your organization using Lync Server.</span></span> <span data-ttu-id="9e8d2-105">Lync Server 2013에 대 한 배포 및 구성 프로세스는 Lync Server 2010와 크게 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="9e8d2-105">The deployment and configuration processes for Lync Server 2013 are not significantly different from Lync Server 2010.</span></span> <span data-ttu-id="9e8d2-106">설치 및 관리에 대 한 도구는 Lync Server 2010와 거의 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e8d2-106">The tools for installation and administration are much the same as in Lync Server 2010.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="9e8d2-107">Microsoft Lync Server 2013&nbsp;Edge Server 설치 및 구성은 내부 팀과의 상당한 양의 계획 및 조정 (예:-보안, 네트워킹, 방화벽, DNS (domain name system), 부하 분산 및 PKI (공개 키 인프라) 고려 사항 포함)을 필요로 하는 복잡 한 프로세스 일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e8d2-107">Microsoft Lync Server 2013&nbsp;Edge Server installation and configuration can be a complex process requiring a potentially significant amount of planning and coordination with your internal teams, including – but not limited to – security, networking, firewall, domain name system (DNS), load balancer, and public key infrastructure (PKI) considerations.</span></span> <span data-ttu-id="9e8d2-108">외부 액세스 구성 요소를 배포 하기 전에 제공 되는 계획 프로세스 및 설명서를 검토 하 고 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="9e8d2-108">It is strongly recommended that you review and use the planning process and documentation provided before deploying your external access components.</span></span> <span data-ttu-id="9e8d2-109">이렇게 하면 배포 프로세스를 진행할 때 원치 않는 변경 및 문제의 횟수와 빈도를 제한 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9e8d2-109">This will assist in limiting the number and frequency of undesired changes and problems as you proceed through the deployment process.</span></span> <span data-ttu-id="9e8d2-110">외부 사용자 액세스를 계획 하는 방법에 대 한 자세한 내용은 <A href="lync-server-2013-planning-for-external-user-access.md">Lync Server 2013의 외부 사용자 액세스 계획</A>을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="9e8d2-110">For information on planning you external user access, see <A href="lync-server-2013-planning-for-external-user-access.md">Planning for external user access in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="9e8d2-111">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="9e8d2-111">In This Section</span></span>

  - [<span data-ttu-id="9e8d2-112">Lync Server 2013의 외부 사용자 액세스에 대 한 배포 검사 목록</span><span class="sxs-lookup"><span data-stu-id="9e8d2-112">Deployment checklist for external user access in Lync Server 2013</span></span>](lync-server-2013-deployment-checklist-for-external-user-access.md)

  - [<span data-ttu-id="9e8d2-113">Lync Server 2013의 외부 사용자 액세스 구성 요소에 대 한 시스템 요구 사항</span><span class="sxs-lookup"><span data-stu-id="9e8d2-113">System requirements for external user access components for Lync Server 2013</span></span>](lync-server-2013-system-requirements-for-external-user-access-components.md)

  - [<span data-ttu-id="9e8d2-114">Lync Server 2013에 대 한 경계 네트워크에 서버 설치 준비</span><span class="sxs-lookup"><span data-stu-id="9e8d2-114">Preparing for installation of servers in the perimeter network for Lync Server 2013</span></span>](lync-server-2013-preparing-for-installation-of-servers-in-the-perimeter-network.md)

  - [<span data-ttu-id="9e8d2-115">Lync Server 2013에서에 지 및 디렉터 토폴로지 구축</span><span class="sxs-lookup"><span data-stu-id="9e8d2-115">Building an edge and Director topology in Lync Server 2013</span></span>](lync-server-2013-building-an-edge-and-director-topology.md)

  - <span data-ttu-id="9e8d2-116">[Lync Server 2013에서 디렉터 설정](lync-server-2013-setting-up-the-director.md) (선택 사항)</span><span class="sxs-lookup"><span data-stu-id="9e8d2-116">[Setting up the Director in Lync Server 2013](lync-server-2013-setting-up-the-director.md) (optional)</span></span>

  - [<span data-ttu-id="9e8d2-117">Lync Server 2013에서에 지 서버 설정</span><span class="sxs-lookup"><span data-stu-id="9e8d2-117">Setting up Edge Servers in Lync Server 2013</span></span>](lync-server-2013-setting-up-edge-servers.md)

  - [<span data-ttu-id="9e8d2-118">Lync Server 2013에 대 한 역방향 프록시 서버 설정</span><span class="sxs-lookup"><span data-stu-id="9e8d2-118">Setting up reverse proxy servers for Lync Server 2013</span></span>](lync-server-2013-setting-up-reverse-proxy-servers.md)

  - [<span data-ttu-id="9e8d2-119">Lync Server 2013에서 외부 사용자 액세스에 대 한 지원 구성</span><span class="sxs-lookup"><span data-stu-id="9e8d2-119">Configuring support for external user access in Lync Server 2013</span></span>](lync-server-2013-configuring-support-for-external-user-access.md)

  - [<span data-ttu-id="9e8d2-120">Lync Server 2013의 Lync-Skype 연결을 위한 프로 비전 가이드</span><span class="sxs-lookup"><span data-stu-id="9e8d2-120">Provisioning guide for Lync-Skype connectivity in Lync Server 2013</span></span>](lync-server-2013-provisioning-guide-for-lync-skype-connectivity.md)

  - [<span data-ttu-id="9e8d2-121">Lync Server 2013에서 SIP 페더레이션, XMPP 페더레이션 및 공용 인스턴트 메시징 구성</span><span class="sxs-lookup"><span data-stu-id="9e8d2-121">Configuring SIP federation, XMPP federation and public instant messaging in Lync Server 2013</span></span>](lync-server-2013-configuring-sip-federation-xmpp-federation-and-public-instant-messaging.md)

  - [<span data-ttu-id="9e8d2-122">Lync Server 2013에서 모바일 기능 배포</span><span class="sxs-lookup"><span data-stu-id="9e8d2-122">Deploying mobility in Lync Server 2013</span></span>](lync-server-2013-deploying-mobility.md)

  - [<span data-ttu-id="9e8d2-123">Lync Server 2013에서에 지 배포 확인</span><span class="sxs-lookup"><span data-stu-id="9e8d2-123">Verifying your edge deployment in Lync Server 2013</span></span>](lync-server-2013-verifying-your-edge-deployment.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

