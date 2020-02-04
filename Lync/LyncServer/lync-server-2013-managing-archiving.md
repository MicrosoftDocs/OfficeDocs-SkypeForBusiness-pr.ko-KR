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
ms.openlocfilehash: b3bb7ecac5204fc42b44e919dbbab8e9b720acc7
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41738868"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-lync-server-2013-archiving"></a><span data-ttu-id="58ded-102">Lync Server 2013 보관 관리</span><span class="sxs-lookup"><span data-stu-id="58ded-102">Managing Lync Server 2013 Archiving</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="58ded-103">_**마지막으로 수정한 주제:** 2012-10-10_</span><span class="sxs-lookup"><span data-stu-id="58ded-103">_**Topic Last Modified:** 2012-10-10_</span></span>

<span data-ttu-id="58ded-104">조직의 보관을 배포 하는 경우 배포 중에 초기 구성을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="58ded-104">When you deploy Archiving for your organization, you specify the initial configuration during deployment.</span></span> <span data-ttu-id="58ded-105">그러나 일일 관리에 대 한 보관 지원을 구현 하는 방법이 나 조직의 새로운 요구 사항을 충족 하는 방법을 변경 해야 하는 경우가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58ded-105">However, there may be times when you want to change how you implement archiving support for day-to-day management or to meet new requirements in your organization.</span></span> <span data-ttu-id="58ded-106">예를 들어 조직 내 특정 사이트, 풀 또는 사용자에 대해 보관 지원을 다르게 설정 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58ded-106">For example, you may need to set up archiving support differently for a specific site, pool, or users within your organization.</span></span> <span data-ttu-id="58ded-107">Lync Server 2013에 속한 사용자의 경우, 보관 정책 및 구성을 만들고 사용자 지정 하는 것이 가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="58ded-107">For users homed on Lync Server 2013, you do this be creating and customizing archiving policies and configurations.</span></span> <span data-ttu-id="58ded-108">Microsoft Exchange 통합을 사용 하는 경우 Exchange 2013 설정도 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="58ded-108">If you use Microsoft Exchange integration, you must also configure Exchange 2013 settings.</span></span> <span data-ttu-id="58ded-109">이 섹션에서는 보관 배포를 변경 하는 데 사용할 수 있는 정보와 절차에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="58ded-109">This section provides information and procedures to enable you to make changes to your Archiving deployment.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="58ded-110">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="58ded-110">In This Section</span></span>

  - [<span data-ttu-id="58ded-111">Lync Server 2013에서 보관 하는 방식</span><span class="sxs-lookup"><span data-stu-id="58ded-111">How Archiving works in Lync Server 2013</span></span>](lync-server-2013-how-archiving-works.md)

  - [<span data-ttu-id="58ded-112">Lync Server 2013의 내부 및 외부 통신 보관 관리</span><span class="sxs-lookup"><span data-stu-id="58ded-112">Managing the Archiving of internal and external communications in Lync Server 2013</span></span>](lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md)

  - [<span data-ttu-id="58ded-113">조직, 사이트 및 풀에 대 한 Lync Server 2013의 보관 구성 옵션 관리</span><span class="sxs-lookup"><span data-stu-id="58ded-113">Managing Archiving configuration options in Lync Server 2013 for your organization, sites, and pools</span></span>](lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md)

  - [<span data-ttu-id="58ded-114">Lync Server 2013에서 데이터베이스 보관 옵션 변경</span><span class="sxs-lookup"><span data-stu-id="58ded-114">Changing Archiving database options in Lync Server 2013</span></span>](lync-server-2013-changing-archiving-database-options.md)

  - [<span data-ttu-id="58ded-115">Lync Server 2013에서 보관 된 데이터 내보내기</span><span class="sxs-lookup"><span data-stu-id="58ded-115">Exporting archived data from Lync Server 2013</span></span>](lync-server-2013-exporting-archived-data.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

