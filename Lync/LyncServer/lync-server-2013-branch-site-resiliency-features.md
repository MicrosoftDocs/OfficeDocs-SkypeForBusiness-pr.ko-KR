---
title: 'Lync Server 2013: 분기 사이트 복구 기능'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Branch-site resiliency features
ms:assetid: 8e3feda5-9a38-4e3c-b808-af29f19c5eb9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398715(v=OCS.15)
ms:contentKeyID: 48184765
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5e452dc297a79525b587d13aa58ed1e1270d41aa
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40985650"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="branch-site-resiliency-features-in-lync-server-2013"></a><span data-ttu-id="7b39b-102">Lync Server 2013의 분기 사이트 복구 기능</span><span class="sxs-lookup"><span data-stu-id="7b39b-102">Branch-site resiliency features in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7b39b-103">_**마지막으로 수정한 주제:** 2014-02-10_</span><span class="sxs-lookup"><span data-stu-id="7b39b-103">_**Topic Last Modified:** 2014-02-10_</span></span>

<span data-ttu-id="7b39b-104">지점 사이트의 탄력성을 제공 하는 경우 중앙 사이트에 대 한 지점 사이트의 WAN 연결이 실패 하거나 중앙 사이트에 연결할 수 없는 경우 다음 음성 기능을 계속 사용할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7b39b-104">If you provide branch-site resiliency, if a branch site’s WAN connection to a central site fails or if the central site is unreachable, the following voice features should continue to be available:</span></span>

<div>


  - <span data-ttu-id="7b39b-105">인바운드와 아웃 바운드 공공 전화 네트워크 (PSTN) 통화</span><span class="sxs-lookup"><span data-stu-id="7b39b-105">Inbound and outbound public switched telephone network (PSTN) calls</span></span>

  - <span data-ttu-id="7b39b-106">동일한 사이트와 두 개의 다른 사이트 간 사용자 간 엔터프라이즈 통화</span><span class="sxs-lookup"><span data-stu-id="7b39b-106">Enterprise calls between users at both the same site and between two different sites</span></span>

  - <span data-ttu-id="7b39b-107">통화 대기, 검색, 전송을 포함 한 기본 통화 처리</span><span class="sxs-lookup"><span data-stu-id="7b39b-107">Basic call handling, including call hold, retrieval, and transfer</span></span>

  - <span data-ttu-id="7b39b-108">2-타사 인스턴트 메시지</span><span class="sxs-lookup"><span data-stu-id="7b39b-108">Two-party instant messaging</span></span>

  - <span data-ttu-id="7b39b-109">대리인 및 대리인 (예: 관리자 및 관리자의 관리자) 또는 모든 팀 구성원을 같은 사이트에 구성 하는 경우에만 착신 전환, 끝점의 동시 연결, 통화 위임, 팀 호출 서비스 등이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b39b-109">Call forwarding, simultaneous ringing of endpoints, call delegation, and team call services, but only if the delegator and delegate (for example, a manager and the manager’s administrator), or all team members, are configured at the same site</span></span>

  - <span data-ttu-id="7b39b-110">CDRs (통화 정보 기록)</span><span class="sxs-lookup"><span data-stu-id="7b39b-110">Call detail records (CDRs)</span></span>

  - <span data-ttu-id="7b39b-111">회의 자동 전화 교환을 사용 하는 PSTN 전화 접속 회의</span><span class="sxs-lookup"><span data-stu-id="7b39b-111">PSTN dial-in conferencing with Conferencing Auto-Attendant</span></span>

  - <span data-ttu-id="7b39b-112">음성 메일 기능-음성 메일 다시 라우팅 설정을 구성 하는 경우</span><span class="sxs-lookup"><span data-stu-id="7b39b-112">Voice mail capabilities, if you configure voice mail rerouting settings.</span></span> <span data-ttu-id="7b39b-113">자세한 내용은 [Lync Server 2013에 대 한 지점 사이트 복원 요구 사항을](lync-server-2013-branch-site-resiliency-requirements.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="7b39b-113">(For details, see [Branch-site resiliency requirements for Lync Server 2013](lync-server-2013-branch-site-resiliency-requirements.md).)</span></span>

  - <span data-ttu-id="7b39b-114">사용자 인증 및 권한 부여</span><span class="sxs-lookup"><span data-stu-id="7b39b-114">User authentication and authorization</span></span>

<span data-ttu-id="7b39b-115">다음 기능은 복원 솔루션이 지점 사이트의 전체 규모 Lync Server 배포 인 경우에만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b39b-115">The following features will be available only if your resiliency solution is a full-scale Lync Server deployment at the branch site:</span></span>

  - <span data-ttu-id="7b39b-116">메신저 대화, 웹 및 A/V 회의</span><span class="sxs-lookup"><span data-stu-id="7b39b-116">IM, web, and A/V conferencing</span></span>

  - <span data-ttu-id="7b39b-117">현재 상태 및 DND (방해 금지) 기반 라우팅 (호출이 DND를 사용 하 여 확장에서 연결을 차단 하는 경우)</span><span class="sxs-lookup"><span data-stu-id="7b39b-117">Presence and Do Not Disturb (DND)-based routing (where calls are prevented from ringing on extensions that have DND activated)</span></span>

  - <span data-ttu-id="7b39b-118">착신 전환 설정 업데이트</span><span class="sxs-lookup"><span data-stu-id="7b39b-118">Updating call forwarding settings</span></span>

  - <span data-ttu-id="7b39b-119">응답 그룹 응용 프로그램 및 통화 공원 응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="7b39b-119">Response Group application and Call Park application</span></span>

  - <span data-ttu-id="7b39b-120">Active Directory 도메인 서비스가 지점 사이트에 있는 경우에만 새 전화 및 클라이언트를 프로 비전 합니다.</span><span class="sxs-lookup"><span data-stu-id="7b39b-120">Provisioning new phones and clients, but only if Active Directory Domain Services is present at the branch site.</span></span>

  - <span data-ttu-id="7b39b-121">향상 된 9-1-1 (E9-1-1)</span><span class="sxs-lookup"><span data-stu-id="7b39b-121">Enhanced 9-1-1 (E9-1-1)</span></span>
    
    <span data-ttu-id="7b39b-122">E9가 배포 되 고 중앙 사이트의 SIP 트렁크를 사용할 수 없는 경우 WAN 링크가 작동 하지 않는 경우 Survivable Branch 기기는 E9-1-1 통화를 로컬 분기 게이트웨이에 라우팅합니다.</span><span class="sxs-lookup"><span data-stu-id="7b39b-122">If E9-1-1 is deployed, and the SIP trunk at the central site is not available because the WAN link is down, then the Survivable Branch Appliance will route E9-1-1 calls to the local branch gateway.</span></span> <span data-ttu-id="7b39b-123">이 기능을 사용 하도록 설정 하려면 지점 사이트 사용자의 음성 정책에서 WAN 장애가 발생 하는 경우 로컬 게이트웨이로 호출을 라우팅 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7b39b-123">To enable this feature, the branch-site users’ voice policies should route calls to the local gateway in the event of WAN failure.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="7b39b-124">SBA (survivable 지사)는 XMPP에 대해 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7b39b-124">SBA (survivable branch office) is not supported for XMPP.</span></span> <span data-ttu-id="7b39b-125">SBA 구성에 속한 사용자는 Im을 보내거나 XMPP 연락처를 사용 하 여 현재 상태를 볼 수 없게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7b39b-125">Users homed in a SBA configurations will not be able to send IMs or see Presence with XMPP contacts.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

