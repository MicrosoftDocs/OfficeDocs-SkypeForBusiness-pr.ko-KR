---
title: 'Lync Server 2013: 분기 사이트 복구 기능'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Branch-site resiliency features
ms:assetid: 8e3feda5-9a38-4e3c-b808-af29f19c5eb9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398715(v=OCS.15)
ms:contentKeyID: 48184765
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5787f0fd07afcf0ca70a9c3b0f7c21e3525cfae7
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42150727"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="branch-site-resiliency-features-in-lync-server-2013"></a><span data-ttu-id="2d261-102">Lync Server 2013의 분기 사이트 복구 기능</span><span class="sxs-lookup"><span data-stu-id="2d261-102">Branch-site resiliency features in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2d261-103">_**마지막으로 수정 된 항목:** 2014-02-10_</span><span class="sxs-lookup"><span data-stu-id="2d261-103">_**Topic Last Modified:** 2014-02-10_</span></span>

<span data-ttu-id="2d261-104">분기 사이트 복구를 제공하는 경우, 중앙 사이트에 대한 분기 사이트의 WAN 연결이 실패하는 경우 또는 중앙 사이트에 연결할 수 없는 경우 다음 음성 기능은 계속해서 사용 가능해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d261-104">If you provide branch-site resiliency, if a branch site’s WAN connection to a central site fails or if the central site is unreachable, the following voice features should continue to be available:</span></span>

<div>


  - <span data-ttu-id="2d261-105">인바운드 및 아웃바운드 PSTN(공중 전화망) 통화</span><span class="sxs-lookup"><span data-stu-id="2d261-105">Inbound and outbound public switched telephone network (PSTN) calls</span></span>

  - <span data-ttu-id="2d261-106">같은 사이트에 있는 사용자 및 서로 다른 두 사이트 간의 엔터프라이즈 통화</span><span class="sxs-lookup"><span data-stu-id="2d261-106">Enterprise calls between users at both the same site and between two different sites</span></span>

  - <span data-ttu-id="2d261-107">통화 보류, 검색 및 전송을 포함한 기본적인 통화 처리</span><span class="sxs-lookup"><span data-stu-id="2d261-107">Basic call handling, including call hold, retrieval, and transfer</span></span>

  - <span data-ttu-id="2d261-108">두 사용자 간 인스턴트 메시징</span><span class="sxs-lookup"><span data-stu-id="2d261-108">Two-party instant messaging</span></span>

  - <span data-ttu-id="2d261-109">착신 전환, 끝점의 동시 신호 울림, 통화 위임 및 팀 호출 서비스: 위임자 및 대리인(예: 관리자와 관리자의 상위 관리자) 또는 모든 팀 구성원이 동일한 사이트에서 구성된 경우에만 해당</span><span class="sxs-lookup"><span data-stu-id="2d261-109">Call forwarding, simultaneous ringing of endpoints, call delegation, and team call services, but only if the delegator and delegate (for example, a manager and the manager’s administrator), or all team members, are configured at the same site</span></span>

  - <span data-ttu-id="2d261-110">CDR(통화 정보 기록)</span><span class="sxs-lookup"><span data-stu-id="2d261-110">Call detail records (CDRs)</span></span>

  - <span data-ttu-id="2d261-111">회의 자동 전화 교환을 사용한 PSTN 전화 접속 회의</span><span class="sxs-lookup"><span data-stu-id="2d261-111">PSTN dial-in conferencing with Conferencing Auto-Attendant</span></span>

  - <span data-ttu-id="2d261-112">음성 메일 기능: 음성 메일 다시 라우팅 설정을 구성한 경우.</span><span class="sxs-lookup"><span data-stu-id="2d261-112">Voice mail capabilities, if you configure voice mail rerouting settings.</span></span> <span data-ttu-id="2d261-113">자세한 내용은 [Lync Server 2013에 대 한 분기 사이트 복구 요구 사항을](lync-server-2013-branch-site-resiliency-requirements.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="2d261-113">(For details, see [Branch-site resiliency requirements for Lync Server 2013](lync-server-2013-branch-site-resiliency-requirements.md).)</span></span>

  - <span data-ttu-id="2d261-114">사용자 인증 및 권한 부여</span><span class="sxs-lookup"><span data-stu-id="2d261-114">User authentication and authorization</span></span>

<span data-ttu-id="2d261-115">다음 기능은 복구 솔루션이 분기 사이트에서 전체 규모의 Lync Server 배포 인 경우에만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d261-115">The following features will be available only if your resiliency solution is a full-scale Lync Server deployment at the branch site:</span></span>

  - <span data-ttu-id="2d261-116">IM, 웹 및 A/V 회의</span><span class="sxs-lookup"><span data-stu-id="2d261-116">IM, web, and A/V conferencing</span></span>

  - <span data-ttu-id="2d261-117">현재 상태 및 DND(방해 금지) 기반 라우팅(DND가 활성화된 내선의 경우 통화의 벨울림이 방지됨)</span><span class="sxs-lookup"><span data-stu-id="2d261-117">Presence and Do Not Disturb (DND)-based routing (where calls are prevented from ringing on extensions that have DND activated)</span></span>

  - <span data-ttu-id="2d261-118">착신 전환 설정 업데이트</span><span class="sxs-lookup"><span data-stu-id="2d261-118">Updating call forwarding settings</span></span>

  - <span data-ttu-id="2d261-119">응답 그룹 응용 프로그램 및 통화 대기 응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="2d261-119">Response Group application and Call Park application</span></span>

  - <span data-ttu-id="2d261-120">새 전화 및 클라이언트 프로 비전 (Active Directory 도메인 서비스가 분기 사이트에 있는 경우)</span><span class="sxs-lookup"><span data-stu-id="2d261-120">Provisioning new phones and clients, but only if Active Directory Domain Services is present at the branch site.</span></span>

  - <span data-ttu-id="2d261-121">E9-1-1(고급 9-1-1)</span><span class="sxs-lookup"><span data-stu-id="2d261-121">Enhanced 9-1-1 (E9-1-1)</span></span>
    
    <span data-ttu-id="2d261-122">E9-1이 배포 되 고 WAN 링크가 다운 되어 중앙 사이트의 SIP 트렁크를 사용할 수 없는 경우 Sba (survivable 분기 어플라이언스는 E9-1-1 통화를 로컬 분기 게이트웨이로 라우팅합니다.</span><span class="sxs-lookup"><span data-stu-id="2d261-122">If E9-1-1 is deployed, and the SIP trunk at the central site is not available because the WAN link is down, then the Survivable Branch Appliance will route E9-1-1 calls to the local branch gateway.</span></span> <span data-ttu-id="2d261-123">이 기능을 사용하도록 설정하려면 분기 사이트 사용자의 음성 정책이 WAN 오류 발생 시 통화를 로컬 게이트웨이로 라우팅해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d261-123">To enable this feature, the branch-site users’ voice policies should route calls to the local gateway in the event of WAN failure.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="2d261-124">SBA (sba (survivable branch)는 XMPP에서 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2d261-124">SBA (survivable branch office) is not supported for XMPP.</span></span> <span data-ttu-id="2d261-125">SBA 구성에 속한 사용자는 Im을 보내거나 XMPP 연락처를 사용 하 여 현재 상태를 볼 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2d261-125">Users homed in a SBA configurations will not be able to send IMs or see Presence with XMPP contacts.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

