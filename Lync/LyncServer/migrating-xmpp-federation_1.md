---
title: XMPP 페더레이션 마이그레이션
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Migrating XMPP federation
ms:assetid: 7368ee8f-a201-4d3a-b4e8-68396b156d4d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688093(v=OCS.15)
ms:contentKeyID: 49733692
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b9764554cf9984ceb35878b87032194a51aec3b7
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40983627"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrating-xmpp-federation"></a><span data-ttu-id="90069-102">XMPP 페더레이션 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="90069-102">Migrating XMPP federation</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="90069-103">_**마지막으로 수정한 주제:** 2012-10-16_</span><span class="sxs-lookup"><span data-stu-id="90069-103">_**Topic Last Modified:** 2012-10-16_</span></span>

<span data-ttu-id="90069-104">이전 버전의 Office 통신 서버는 XMPP 배포와 페더레이션 할 수 있는 별도의 서버 역할로 배포 될 수 있는 확장 가능한 메시징 및 현재 상태 프로토콜 (XMPP) 게이트웨이를 제공 했습니다.</span><span class="sxs-lookup"><span data-stu-id="90069-104">Previous versions of Office Communications Server provided an extensible messaging and presence protocol (XMPP) gateway that could be deployed as a separate server role to allow federating with XMPP deployments.</span></span> <span data-ttu-id="90069-105">Lync Server 2013에서는 XMPP 기능을 기능으로 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="90069-105">In Lync Server 2013, the XMPP functionality can be deployed as a feature.</span></span> <span data-ttu-id="90069-106">XMPP 기능은 Lync Server 2013 Edge 서버에서 실행 되는 XMPP 프록시로, Lync Server 2013 프런트 엔드 서버에서 실행 되는 XMPP 게이트웨이 등 두 가지 부분으로 설치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="90069-106">XMPP functionality is installed in two parts: as an XMPP proxy that runs on the Lync Server 2013 Edge Server, and the XMPP Gateway that runs on the Lync Server 2013 Front End Server.</span></span>

<span data-ttu-id="90069-107">마이그레이션 측면에서 Office Communications Server 2007 R2 사용자 계정은 Lync Server 2013 풀로 이동 하 고 계속 해 서 Office Communications Server 2007 R2 XMPP 게이트웨이를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="90069-107">From a migration perspective, a Office Communications Server 2007 R2 user account can be moved to a Lync Server 2013 pool and continue to use the Office Communications Server 2007 R2 XMPP gateway.</span></span> <span data-ttu-id="90069-108">이는 XMPP 페더레이션 파트너가 Lync Server 2013에서 구성 되지 않은 경우에만 가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="90069-108">This is possible only when the XMPP federated partner is not configured in Lync Server 2013.</span></span>

<span data-ttu-id="90069-109">요약 하자면, office communications server를 Office communications server 2007 R2 XMPP 게이트웨이와 함께 배포 하 고 레거시 Office Communications Server 2007 R2 사용자에 대해 XMPP 페더레이션을 사용 하도록 설정 되어 있는 경우 XMPP 페더레이션을 Lync Server 2013로 마이그레이션합니다.</span><span class="sxs-lookup"><span data-stu-id="90069-109">In summary, if Office Communications Server has been deployed with the Office Communications Server 2007 R2 XMPP Gateway and XMPP federation has been enabled for legacy Office Communications Server 2007 R2 users, to migrate the XMPP federation to Lync Server 2013:</span></span>

1.  <span data-ttu-id="90069-110">Lync Server 2013 풀을 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="90069-110">Deploy a Lync Server 2013 pool.</span></span>

2.  <span data-ttu-id="90069-111">Lync Server 2013 Edge 서버를 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="90069-111">Deploy a Lync Server 2013 Edge server.</span></span>

3.  <span data-ttu-id="90069-112">모든 사용자를 Lync Server 2013 풀로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="90069-112">Move all users to the Lync Server 2013 pool.</span></span>

4.  <span data-ttu-id="90069-113">Edge 서버용 XMPP 액세스 정책 및 인증서를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="90069-113">Create XMPP access policies and certificates for the Edge Server.</span></span>

5.  <span data-ttu-id="90069-114">Lync Server 2013에서 XMPP 페더레이션을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="90069-114">Enable XMPP federation in Lync Server 2013.</span></span> 

6.  <span data-ttu-id="90069-115">Lync Server 2013 XMPP 게이트웨이를 가리키도록 DNS 항목을 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="90069-115">Update the DNS entries to point to the Lync Server 2013 XMPP Gateway.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

