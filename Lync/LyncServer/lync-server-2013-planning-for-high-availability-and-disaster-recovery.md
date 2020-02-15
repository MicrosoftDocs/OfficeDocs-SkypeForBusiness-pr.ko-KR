---
title: 'Lync Server 2013: 고가용성 및 재해 복구 계획'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for high availability and disaster recovery
ms:assetid: 15a72073-0336-45dd-b2a0-35e7522c6000
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204703(v=OCS.15)
ms:contentKeyID: 48183497
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 38a41585da7cb247dc955b3f4e18ee4812ef5a2a
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42036698"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-high-availability-and-disaster-recovery-in-lync-server-2013"></a><span data-ttu-id="47871-102">Lync Server 2013의 고가용성 및 재해 복구 계획</span><span class="sxs-lookup"><span data-stu-id="47871-102">Planning for high availability and disaster recovery in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="47871-103">_**마지막으로 수정 된 항목:** 2013-10-31_</span><span class="sxs-lookup"><span data-stu-id="47871-103">_**Topic Last Modified:** 2013-10-31_</span></span>

<span data-ttu-id="47871-104">Lync Server 2010에서와 마찬가지로 Lync Server 2013에서 대부분의 서버 역할에 대 한 기본 고가용성 체계는 풀링을 통한 서버 중복성을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="47871-104">As in Lync Server 2010, the main high availability scheme for most server roles in Lync Server 2013 is based on server redundancy via pooling.</span></span> <span data-ttu-id="47871-105">특정 서버 역할을 실행하는 서버에서 오류가 발생하면 같은 역할을 실행하는 풀의 다른 서버가 해당 서버의 부하를 대신 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="47871-105">If a server running a certain server role fails, the other servers in the pool running the same role take the load of that server.</span></span> <span data-ttu-id="47871-106">이는 프런트 엔드 서버, 에지 서버, 중재 서버 및 디렉터에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="47871-106">This applies to Front End Servers, Edge Servers, Mediation Servers, and Directors.</span></span>

<span data-ttu-id="47871-107">Lync Server 2013에서는 서버의 지리적 단일를 두 데이터 센터에 추가 하 여 프런트 엔드 풀에 대해 새 재해 복구 조치를 추가한 후 하나의 전체 풀이나 사이트에 대 한 서비스를 계속 해 서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47871-107">Lync Server 2013 adds new disaster recovery measures for Front End pools by introducing geographical dispersement of your servers into two data centers to provide continuation of service should one entire pool or site go down.</span></span>

<span data-ttu-id="47871-108">Lync Server 2013 또한 백 엔드 데이터베이스에 대 한 동기 SQL 미러링을 지원 하 여 백 엔드 서버의 고가용성을 향상 시킵니다.</span><span class="sxs-lookup"><span data-stu-id="47871-108">Lync Server 2013 also enhances Back End Server high availability, by supporting synchronous SQL mirroring for your Back End databases.</span></span>

<span data-ttu-id="47871-109">이 섹션에서는 이와 같은 주요 고가용성 및 재해 복구 기능에 대해 설명하고, 다른 서버 역할의 고가용성 및 재해 복구를 위해 수행할 수 있는 단계에 대해서도 다룹니다.</span><span class="sxs-lookup"><span data-stu-id="47871-109">This section explains these major high availability and disaster recovery features, and also covers what steps you can take for high availability and disaster recovery for your other server roles as well.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="47871-110">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="47871-110">In This Section</span></span>

  - [<span data-ttu-id="47871-111">Lync Server 2013의 프런트 엔드 풀 재해 복구</span><span class="sxs-lookup"><span data-stu-id="47871-111">Front End pool disaster recovery in Lync Server 2013</span></span>](lync-server-2013-front-end-pool-disaster-recovery.md)

  - [<span data-ttu-id="47871-112">Lync Server 2013의에 지 서버 재해 복구</span><span class="sxs-lookup"><span data-stu-id="47871-112">Edge Server disaster recovery in Lync Server 2013</span></span>](lync-server-2013-edge-server-disaster-recovery.md)

  - [<span data-ttu-id="47871-113">Lync Server 2013의 Enterprise Voice 복구 계획</span><span class="sxs-lookup"><span data-stu-id="47871-113">Planning for Enterprise Voice resiliency in Lync Server 2013</span></span>](lync-server-2013-planning-for-enterprise-voice-resiliency.md)

  - [<span data-ttu-id="47871-114">Lync Server 2013의 재해 복구를 위한 통화 관리 기능</span><span class="sxs-lookup"><span data-stu-id="47871-114">Call management features for disaster recovery in Lync Server 2013</span></span>](lync-server-2013-call-management-features-for-disaster-recovery.md)

  - [<span data-ttu-id="47871-115">Lync Server 2013에서 고가용성 및 재해 복구를 위한 영구 채팅 서버 구성</span><span class="sxs-lookup"><span data-stu-id="47871-115">Configuring Persistent Chat Server for high availability and disaster recovery in Lync Server 2013</span></span>](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md)

  - [<span data-ttu-id="47871-116">Lync Server 2010 대도시 사이트 복구</span><span class="sxs-lookup"><span data-stu-id="47871-116">Lync Server 2010 metropolitan site resiliency</span></span>](lync-server-2013-compatibility-with-lync-server-2010-metropolitan-site-resiliency.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

