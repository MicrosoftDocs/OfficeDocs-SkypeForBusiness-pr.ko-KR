---
title: Lync Online과의 하이브리드 방식 배포용으로 온-프레미스 배포 구성
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring an on-premises deployment for hybrid with Lync Online
ms:assetid: c26addb0-2936-4eea-9071-3ab95825154b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205237(v=OCS.15)
ms:contentKeyID: 48185321
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f63620dc86a0249556d94491ec690989fa1dc835
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984585"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-an-on-premises-deployment-for-hybrid-with-lync-online"></a><span data-ttu-id="e6d3f-102">Lync Online과의 하이브리드 방식 배포용으로 온-프레미스 배포 구성</span><span class="sxs-lookup"><span data-stu-id="e6d3f-102">Configuring an on-premises deployment for hybrid with Lync Online</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e6d3f-103">_**마지막으로 수정한 주제:** 2014-05-28_</span><span class="sxs-lookup"><span data-stu-id="e6d3f-103">_**Topic Last Modified:** 2014-05-28_</span></span>

<span data-ttu-id="e6d3f-104">하이브리드 배포는 일부 사용자가 온-프레미스이 고 일부 사용자는 온라인 상태 이지만 모든 사용자가 같은 도메인 (예: user@contoso.com)을 공유 하는 배포입니다.</span><span class="sxs-lookup"><span data-stu-id="e6d3f-104">A hybrid deployment is a deployment in which some users are homed on-premises and some users are homed online, but all users share the same domain, such as user@contoso.com.</span></span> <span data-ttu-id="e6d3f-105">이 섹션에서는 하이브리드 배포에 필요한 응용 프로그램을 배포한 다음 배포를 사용 하도록 구성 하는 방법을 안내 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6d3f-105">This section guides you through deploying the applications required for a hybrid deployment, and then configuring your deployment to enable it.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="e6d3f-106">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="e6d3f-106">In This Section</span></span>

  - [<span data-ttu-id="e6d3f-107">Lync Server 2013 하이브리드 환경 개요</span><span class="sxs-lookup"><span data-stu-id="e6d3f-107">Overview of the Lync Server 2013 hybrid environment</span></span>](lync-server-2013-overview-of-the-lync-server-hybrid-environment.md)

  - [<span data-ttu-id="e6d3f-108">Lync Server 2013 하이브리드 환경을 준비 및 배포하기 위한 단계</span><span class="sxs-lookup"><span data-stu-id="e6d3f-108">Steps to prepare and deploy Lync Server 2013 hybrid environment</span></span>](lync-server-2013-steps-to-prepare-and-deploy-lync-server-hybrid-environment.md)

  - [<span data-ttu-id="e6d3f-109">Lync Online을 사용 하 여 Lync Server 2013의 페더레이션 구성</span><span class="sxs-lookup"><span data-stu-id="e6d3f-109">Configure federation of Lync Server 2013 with Lync Online</span></span>](lync-server-2013-configure-federation-with-lync-online.md)

  - [<span data-ttu-id="e6d3f-110">Lync Server 2013에서 오디오 회의 공급자에 대 한 페더레이션 구성</span><span class="sxs-lookup"><span data-stu-id="e6d3f-110">Configure federation for an audio conferencing provider in Lync Server 2013</span></span>](lync-server-2013-configure-federation-for-an-audio-conferencing-provider.md)

  - [<span data-ttu-id="e6d3f-111">Lync Server 2013에서 Lync Online으로 사용자 이동</span><span class="sxs-lookup"><span data-stu-id="e6d3f-111">Move users to Lync Online in Lync Server 2013</span></span>](lync-server-2013-move-users-to-lync-online.md)

  - [<span data-ttu-id="e6d3f-112">하이브리드 Lync Server 2013 배포에서 사용자 관리</span><span class="sxs-lookup"><span data-stu-id="e6d3f-112">Administering users in a hybrid Lync Server 2013 deployment</span></span>](lync-server-2013-administering-users-in-a-hybrid-deployment.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

