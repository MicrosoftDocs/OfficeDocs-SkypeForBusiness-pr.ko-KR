---
title: 'Lync Server 2013: 보관 관리'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing Lync Server 2013 Archiving
ms:assetid: 48c6cc8c-c2c1-4534-9a8a-fd5eb738076a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520990(v=OCS.15)
ms:contentKeyID: 48184003
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 474158ac4cd0aafa905c7694fd9a2f06e53eed94
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48498325"
---
# <a name="managing-lync-server-2013-archiving"></a><span data-ttu-id="28e3a-102">Lync Server 2013 보관 관리</span><span class="sxs-lookup"><span data-stu-id="28e3a-102">Managing Lync Server 2013 Archiving</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="28e3a-103">_**마지막으로 수정 된 항목:** 2012-10-10_</span><span class="sxs-lookup"><span data-stu-id="28e3a-103">_**Topic Last Modified:** 2012-10-10_</span></span>

<span data-ttu-id="28e3a-104">조직에 보관 기능을 배포할 때는 배포 중 초기 구성을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="28e3a-104">When you deploy Archiving for your organization, you specify the initial configuration during deployment.</span></span> <span data-ttu-id="28e3a-105">하지만 일부 경우에는 일상 관리 작업을 위해 또는 조직의 새로운 요구 사항을 충족하기 위해 보관 지원 구현 방식을 변경해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="28e3a-105">However, there may be times when you want to change how you implement archiving support for day-to-day management or to meet new requirements in your organization.</span></span> <span data-ttu-id="28e3a-106">예를 들어 조직 내 특정 사이트, 풀 또는 사용자에 대해 보관 지원을 다르게 설정해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="28e3a-106">For example, you may need to set up archiving support differently for a specific site, pool, or users within your organization.</span></span> <span data-ttu-id="28e3a-107">Lync Server 2013에 속한 사용자의 경우 보관 정책 및 구성을 만들고 사용자 지정 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="28e3a-107">For users homed on Lync Server 2013, you do this be creating and customizing archiving policies and configurations.</span></span> <span data-ttu-id="28e3a-108">Microsoft Exchange 통합을 사용 하는 경우 Exchange 2013 설정도 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="28e3a-108">If you use Microsoft Exchange integration, you must also configure Exchange 2013 settings.</span></span> <span data-ttu-id="28e3a-109">이 섹션에서는 보관 배포를 변경하기 위한 정보 및 절차를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="28e3a-109">This section provides information and procedures to enable you to make changes to your Archiving deployment.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="28e3a-110">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="28e3a-110">In This Section</span></span>

  - [<span data-ttu-id="28e3a-111">Lync Server 2013에서 보관이 작동 하는 방식</span><span class="sxs-lookup"><span data-stu-id="28e3a-111">How Archiving works in Lync Server 2013</span></span>](lync-server-2013-how-archiving-works.md)

  - [<span data-ttu-id="28e3a-112">Lync Server 2013에서 내부 및 외부 통신의 보관 관리</span><span class="sxs-lookup"><span data-stu-id="28e3a-112">Managing the Archiving of internal and external communications in Lync Server 2013</span></span>](lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md)

  - [<span data-ttu-id="28e3a-113">조직, 사이트 및 풀에 대 한 Lync Server 2013의 보관 구성 옵션 관리</span><span class="sxs-lookup"><span data-stu-id="28e3a-113">Managing Archiving configuration options in Lync Server 2013 for your organization, sites, and pools</span></span>](lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md)

  - [<span data-ttu-id="28e3a-114">Lync Server 2013에서 보관 데이터베이스 옵션 변경</span><span class="sxs-lookup"><span data-stu-id="28e3a-114">Changing Archiving database options in Lync Server 2013</span></span>](lync-server-2013-changing-archiving-database-options.md)

  - [<span data-ttu-id="28e3a-115">Lync Server 2013에서 보관 된 데이터 내보내기</span><span class="sxs-lookup"><span data-stu-id="28e3a-115">Exporting archived data from Lync Server 2013</span></span>](lync-server-2013-exporting-archived-data.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

