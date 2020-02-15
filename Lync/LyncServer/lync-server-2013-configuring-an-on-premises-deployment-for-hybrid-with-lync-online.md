---
title: Lync Online을 사용 하 여 하이브리드에 대 한 온-프레미스 배포 구성
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring an on-premises deployment for hybrid with Lync Online
ms:assetid: c26addb0-2936-4eea-9071-3ab95825154b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205237(v=OCS.15)
ms:contentKeyID: 48185321
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 58fc02c6416f1a0d1b60a5c1cdcf3c91c940c82c
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029699"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-an-on-premises-deployment-for-hybrid-with-lync-online"></a><span data-ttu-id="4989d-102">Lync Online을 사용 하 여 하이브리드에 대 한 온-프레미스 배포 구성</span><span class="sxs-lookup"><span data-stu-id="4989d-102">Configuring an on-premises deployment for hybrid with Lync Online</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4989d-103">_**마지막으로 수정 된 항목:** 2014-05-28_</span><span class="sxs-lookup"><span data-stu-id="4989d-103">_**Topic Last Modified:** 2014-05-28_</span></span>

<span data-ttu-id="4989d-104">하이브리드 배포는 일부 사용자가 온-프레미스에 있고 일부 사용자는 온라인 상태이 고 일부 사용자는 user@contoso.com와 같은 동일한 도메인을 공유 하는 배포입니다.</span><span class="sxs-lookup"><span data-stu-id="4989d-104">A hybrid deployment is a deployment in which some users are homed on-premises and some users are homed online, but all users share the same domain, such as user@contoso.com.</span></span> <span data-ttu-id="4989d-105">이 섹션에서는 하이브리드 배포에 필요한 응용 프로그램을 배포한 다음 배포를 구성 하 여 사용 하도록 설정 하는 과정을 안내 합니다.</span><span class="sxs-lookup"><span data-stu-id="4989d-105">This section guides you through deploying the applications required for a hybrid deployment, and then configuring your deployment to enable it.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="4989d-106">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="4989d-106">In This Section</span></span>

  - [<span data-ttu-id="4989d-107">Lync Server 2013 하이브리드 환경 개요</span><span class="sxs-lookup"><span data-stu-id="4989d-107">Overview of the Lync Server 2013 hybrid environment</span></span>](lync-server-2013-overview-of-the-lync-server-hybrid-environment.md)

  - [<span data-ttu-id="4989d-108">Lync Server 2013 하이브리드 환경을 준비 및 배포 하기 위한 단계</span><span class="sxs-lookup"><span data-stu-id="4989d-108">Steps to prepare and deploy Lync Server 2013 hybrid environment</span></span>](lync-server-2013-steps-to-prepare-and-deploy-lync-server-hybrid-environment.md)

  - [<span data-ttu-id="4989d-109">Lync Online을 사용 하 여 Lync Server 2013의 페더레이션 구성</span><span class="sxs-lookup"><span data-stu-id="4989d-109">Configure federation of Lync Server 2013 with Lync Online</span></span>](lync-server-2013-configure-federation-with-lync-online.md)

  - [<span data-ttu-id="4989d-110">Lync Server 2013에서 오디오 회의 공급자를 위한 페더레이션 구성</span><span class="sxs-lookup"><span data-stu-id="4989d-110">Configure federation for an audio conferencing provider in Lync Server 2013</span></span>](lync-server-2013-configure-federation-for-an-audio-conferencing-provider.md)

  - [<span data-ttu-id="4989d-111">Lync Server 2013에서 사용자를 Lync Online으로 이동</span><span class="sxs-lookup"><span data-stu-id="4989d-111">Move users to Lync Online in Lync Server 2013</span></span>](lync-server-2013-move-users-to-lync-online.md)

  - [<span data-ttu-id="4989d-112">하이브리드 Lync Server 2013 배포에서 사용자 관리</span><span class="sxs-lookup"><span data-stu-id="4989d-112">Administering users in a hybrid Lync Server 2013 deployment</span></span>](lync-server-2013-administering-users-in-a-hybrid-deployment.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

