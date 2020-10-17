---
title: 'Lync Server 2013: 디렉터 설정'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up the Director
ms:assetid: 408b76f7-6fdd-4e50-8a3e-e87db12c1394
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425915(v=OCS.15)
ms:contentKeyID: 48183951
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f884fc2b4477a0b9c4e4f4a6e376a99f894dce1e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48497565"
---
# <a name="setting-up-the-director-in-lync-server-2013"></a><span data-ttu-id="862a7-102">Lync Server 2013에서 디렉터 설정</span><span class="sxs-lookup"><span data-stu-id="862a7-102">Setting up the Director in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="862a7-103">_**마지막으로 수정 된 항목:** 2014-05-05_</span><span class="sxs-lookup"><span data-stu-id="862a7-103">_**Topic Last Modified:** 2014-05-05_</span></span>

<span data-ttu-id="862a7-104">에 지 서버를 배포 하 여 외부 사용자에 대 한 액세스를 사용 하도록 설정 하는 경우에는 디렉터를 배포 하는 옵션이 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="862a7-104">If you’re enabling access for external users by deploying Edge Servers, one option is to deploy a Director.</span></span> <span data-ttu-id="862a7-105">디렉터는 사용자 요청을 인증 하는 Microsoft Lync Server 2013를 실행 하는 서버 이며, 사용자 계정은 그렇지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="862a7-105">A Director is a server running Microsoft Lync Server 2013 that authenticates user requests, but doesn’t home any user accounts.</span></span> <span data-ttu-id="862a7-106">이제는 이것이 요구 사항은 아니지만 성능에 대해 걱정 하 고 인증 요청을 합리화 하려는 경우에는 매우 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="862a7-106">Now, this isn’t a requirement, but it is very helpful if you’re worried about performance and want to help streamline authentication requests.</span></span> <span data-ttu-id="862a7-107">조직에서이를 결정 하는 것이 좋습니다. 디렉터 또는 디렉터 풀을 설정 하는 단계는 Enterprise Edition 프런트 엔드 풀 또는 Standard Edition 서버를 설정 하는 것과 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="862a7-107">If you decide this is a good idea for your organization, the steps to set up a Director or a Director pool are similar to setting up either an Enterprise Edition Front End pool or Standard Edition server.</span></span> <span data-ttu-id="862a7-108">토폴로지 작성기에서 디렉터를 정의한 후에는이 섹션의 단계를 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="862a7-108">After you’ve defined your Director(s) in Topology Builder, you’ll need to perform the steps in this section.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="862a7-109">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="862a7-109">In This Section</span></span>

  - [<span data-ttu-id="862a7-110">Lync Server 2013에서 로컬 구성 저장소 설치</span><span class="sxs-lookup"><span data-stu-id="862a7-110">Install the Local Configuration store in Lync Server 2013</span></span>](lync-server-2013-install-the-local-configuration-store.md)

  - [<span data-ttu-id="862a7-111">디렉터에 Lync Server 2013 설치</span><span class="sxs-lookup"><span data-stu-id="862a7-111">Install Lync Server 2013 on the Director</span></span>](lync-server-2013-install-lync-server-on-the-director.md)

  - [<span data-ttu-id="862a7-112">Lync Server 2013에서 디렉터에 대 한 인증서 구성</span><span class="sxs-lookup"><span data-stu-id="862a7-112">Configure certificates for the Director in Lync Server 2013</span></span>](lync-server-2013-configure-certificates-for-the-director.md)

  - [<span data-ttu-id="862a7-113">Lync Server 2013의 디렉터에서 서비스 시작</span><span class="sxs-lookup"><span data-stu-id="862a7-113">Start services on the Director in Lync Server 2013</span></span>](lync-server-2013-start-services-on-the-director.md)

  - [<span data-ttu-id="862a7-114">Lync Server 2013에서 디렉터 테스트</span><span class="sxs-lookup"><span data-stu-id="862a7-114">Test the Director in Lync Server 2013</span></span>](lync-server-2013-test-the-director.md)

  - [<span data-ttu-id="862a7-115">Lync Server 2013에서 디렉터를 사용 하도록 자동 클라이언트 Sign-In 구성</span><span class="sxs-lookup"><span data-stu-id="862a7-115">Configure Automatic Client Sign-In to use the Director in Lync Server 2013</span></span>](lync-server-2013-configure-automatic-client-sign-in-to-use-the-director.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

