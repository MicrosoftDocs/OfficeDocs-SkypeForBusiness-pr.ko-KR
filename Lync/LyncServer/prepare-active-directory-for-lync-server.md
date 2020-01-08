---
title: Lync Server에 대해 Active Directory 준비
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Prepare Active Directory for Lync Server
ms:assetid: 54cd597d-0c2d-479c-8c52-1babc53f71dc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688059(v=OCS.15)
ms:contentKeyID: 49733653
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5ff5be6fbf3849c51979f3cf94dbc36d14e5b282
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40983717"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="prepare-active-directory-for-lync-server"></a><span data-ttu-id="eb825-102">Lync Server에 대해 Active Directory 준비</span><span class="sxs-lookup"><span data-stu-id="eb825-102">Prepare Active Directory for Lync Server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="eb825-103">_**마지막으로 수정한 주제:** 2012-09-17_</span><span class="sxs-lookup"><span data-stu-id="eb825-103">_**Topic Last Modified:** 2012-09-17_</span></span>

<span data-ttu-id="eb825-104">Lync server 2010을 함께 사용 하는 상태에서 Lync 서버 2013를 배포 하기 전에 몇 가지 추가 Active Directory 작업을 수행 하 여 Lync Server 2013의 스키마, 포리스트 및 도메인을 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb825-104">Prior to deploying Lync Server 2013 in a coexistence state with Lync Server 2010, you must perform some additional Active Directory tasks to configure the schema, forest, and domain for Lync Server 2013.</span></span> <span data-ttu-id="eb825-105">스키마 확장에서는 Lync Server 2013에 필요한 Active Directory 클래스 및 특성을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb825-105">The schema extensions add the Active Directory classes and attributes that are required by Lync Server 2013.</span></span> <span data-ttu-id="eb825-106">자세한 내용은 [Lync Server 2013에 대 한 Active Directory 도메인 서비스 준비](lync-server-2013-preparing-active-directory-domain-services.md)항목을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="eb825-106">For additional information, see the topic [Preparing Active Directory Domain Services for Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md).</span></span>

<span data-ttu-id="eb825-107">**Lync Server 2013의 Active Directory를 준비 하려면**</span><span class="sxs-lookup"><span data-stu-id="eb825-107">**To prepare Active Directory for Lync Server 2013**</span></span>

1.  <span data-ttu-id="eb825-108">Lync Server 2013 프런트 엔드 서버에서 Lync Server 2013 설치 프로그램을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb825-108">On the Lync Server 2013 Front End Server, run Lync Server 2013 Setup.</span></span>

2.  <span data-ttu-id="eb825-109">**Active Directory 준비**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb825-109">Select **Prepare Active Directory**.</span></span>
    
    <span data-ttu-id="eb825-110">![Lync server 2013 배포 마법사, 시작 페이지](images/JJ205265.5f88ae18-9c3c-42ea-a91a-836ecf5d515f(OCS.15).jpg "Lync Server 2013 배포 마법사, 시작 페이지")</span><span class="sxs-lookup"><span data-stu-id="eb825-110">![Lync Server 2013 Deployment Wizard, Welcome page](images/JJ205265.5f88ae18-9c3c-42ea-a91a-836ecf5d515f(OCS.15).jpg "Lync Server 2013 Deployment Wizard, Welcome page")</span></span>

3.  <span data-ttu-id="eb825-111">1 ~ 5 단계를 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb825-111">Complete steps 1 through 5.</span></span>
    
    <span data-ttu-id="eb825-112">![배포 마법사, Active Directory Prearation](images/JJ205265.eddd9e94-fa70-453f-8810-b99a2bf0844a(OCS.15).jpg "배포 마법사, active directory Prearation")</span><span class="sxs-lookup"><span data-stu-id="eb825-112">![Deployment Wizard, Active Directory Prearation](images/JJ205265.eddd9e94-fa70-453f-8810-b99a2bf0844a(OCS.15).jpg "Deployment Wizard, Active Directory Prearation")</span></span>

</div>

<span> </span>

</div>

</div>

</div>

