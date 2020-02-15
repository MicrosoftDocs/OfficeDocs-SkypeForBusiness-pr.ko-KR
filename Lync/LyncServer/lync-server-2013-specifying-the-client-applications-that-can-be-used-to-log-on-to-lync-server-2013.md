---
title: 'Lync Server 2013: Lync Server 2013에 로그온 하는 데 사용할 수 있는 클라이언트 응용 프로그램 지정'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Specifying the client applications that can be used to log on to Lync Server 2013
ms:assetid: d256a581-9a48-4d1a-82cc-2e1f520d7d2e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182591(v=OCS.15)
ms:contentKeyID: 48185450
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ea0083a28253f5b79e6124dc7733a3ea096f4509
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2020
ms.locfileid: "42006123"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="specifying-the-client-applications-that-can-be-used-to-log-on-to-lync-server-2013"></a><span data-ttu-id="dc47e-102">Lync Server 2013에 로그온 하는 데 사용할 수 있는 클라이언트 응용 프로그램 지정</span><span class="sxs-lookup"><span data-stu-id="dc47e-102">Specifying the client applications that can be used to log on to Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dc47e-103">_**마지막으로 수정 된 항목:** 2012-12-11_</span><span class="sxs-lookup"><span data-stu-id="dc47e-103">_**Topic Last Modified:** 2012-12-11_</span></span>

<span data-ttu-id="dc47e-104">Lync Server 2013에서는 사용자 환경에서 지원 되는 클라이언트 버전을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dc47e-104">Lync Server 2013 enables you to specify the version of clients that are supported in your environment.</span></span> <span data-ttu-id="dc47e-105">클라이언트 버전 정책을 사용 하면 여러 클라이언트 버전을 지 원하는 데 드는 비용을 줄일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dc47e-105">Using client version policies can help reduce the costs associated with supporting multiple client versions.</span></span> <span data-ttu-id="dc47e-106">이전 버전의 클라이언트가 상호 작용 하는 경우 이전 버전의 클라이언트에 의해 사용 가능한 기능을 제한할 수 있으므로 전반적인 사용자 환경도 향상 시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dc47e-106">It can also improve the overall user experience, because when earlier and later versions of clients interact, the available features can be limited by the earlier version of the client.</span></span>

<span data-ttu-id="dc47e-107">클라이언트 버전 제어에는 다음과 같은 세 가지 구성 요소가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dc47e-107">There are three components of client version control:</span></span>

  - <span data-ttu-id="dc47e-108">클라이언트 버전 구성 설정은 전역으로 또는 특정 사이트에 대해 클라이언트 버전 제어를 설정/해제 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dc47e-108">Client version configuration settings are used to turn client version control on or off, either globally or for particular sites.</span></span>

  - <span data-ttu-id="dc47e-109">클라이언트 버전 정책을 사용 하 여 규칙 집합을 전역적으로 할당 하거나 특정 사이트, 풀 또는 사용자 그룹에 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dc47e-109">Client version policies are used to assign a set of rules globally, or to a particular site, pool, or group of users.</span></span>

  - <span data-ttu-id="dc47e-110">클라이언트 버전 정책 규칙은 클라이언트 버전 정책을 구성 하며, 사용자가 특정 클라이언트 및 클라이언트 버전을 사용 하 여 로그온을 시도할 때 수행 해야 하는 작업을 정의 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dc47e-110">Client version policy rules make up a client version policy, and are used to define the actions that should be taken when users attempt to log on with specific clients and client versions.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="dc47e-111">익명 사용자는 사용자, 사이트 또는 서비스와 연결되지 않으므로 전역 수준 정책에만 영향을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="dc47e-111">Because anonymous users are not associated with a user, site, or service, anonymous users are affected by global-level policies only.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="dc47e-112">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="dc47e-112">In This Section</span></span>

  - [<span data-ttu-id="dc47e-113">Lync Server 2013의 클라이언트 버전 구성 설정</span><span class="sxs-lookup"><span data-stu-id="dc47e-113">Client version configuration settings in Lync Server 2013</span></span>](lync-server-2013-client-version-configuration-settings.md)

  - [<span data-ttu-id="dc47e-114">Lync Server 2013의 클라이언트 버전 정책</span><span class="sxs-lookup"><span data-stu-id="dc47e-114">Client version policies in Lync Server 2013</span></span>](lync-server-2013-client-version-policies.md)

  - [<span data-ttu-id="dc47e-115">Lync Server 2013의 클라이언트 버전 규칙</span><span class="sxs-lookup"><span data-stu-id="dc47e-115">Client version rules in Lync Server 2013</span></span>](lync-server-2013-client-version-rules.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="dc47e-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="dc47e-116">See Also</span></span>


[<span data-ttu-id="dc47e-117">Lync Server 2013에서 장치, 전화 및 클라이언트 응용 프로그램 관리</span><span class="sxs-lookup"><span data-stu-id="dc47e-117">Managing devices, phones, and client applications in Lync Server 2013</span></span>](lync-server-2013-managing-devices-phones-and-client-applications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

