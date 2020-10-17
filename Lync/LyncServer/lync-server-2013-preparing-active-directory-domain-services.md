---
title: 'Lync Server 2013: Active Directory 도메인 서비스 준비'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Preparing Active Directory Domain Services for Lync Server 2013
ms:assetid: 7e126464-5d29-4013-9c44-0ccc2fbdea0f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398630(v=OCS.15)
ms:contentKeyID: 48184620
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cc8b5f4a5efc60456d874276b025ff7ca9806028
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48513315"
---
# <a name="preparing-active-directory-domain-services-for-lync-server-2013"></a><span data-ttu-id="5e90d-102">Lync Server 2013에 대한 Active Directory 도메인 서비스 준비</span><span class="sxs-lookup"><span data-stu-id="5e90d-102">Preparing Active Directory Domain Services for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5e90d-103">_**마지막으로 수정 된 항목:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="5e90d-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="5e90d-104">Lync Server 2013를 배포 하 고 작동 하기 전에 스키마를 확장 하 고 개체를 만들고 구성 하 여 Active Directory 도메인 서비스를 준비 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e90d-104">Before you deploy and operate Lync Server 2013, you must prepare Active Directory Domain Services by extending the schema and then creating and configuring objects.</span></span> <span data-ttu-id="5e90d-105">스키마 확장은 Lync Server에 필요한 Active Directory 클래스 및 특성을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e90d-105">The schema extensions add the Active Directory classes and attributes that are required by Lync Server.</span></span>

<span data-ttu-id="5e90d-106">이 섹션의 항목에서는 Lync Server 배포를 위해 AD DS를 준비 하는 방법 및 설정 및 OU (조직 구성 단위) 권한을 할당 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e90d-106">The topics in this section describe how to prepare AD DS for deploying Lync Server and how to assign setup and organizational unit (OU) permissions.</span></span> <span data-ttu-id="5e90d-107">Lync Server에 필요한 스키마 변경에 대 한 자세한 내용은 [Lync server 2013에서 사용 하는 Active Directory 스키마 확장, 클래스 및 특성](lync-server-2013-active-directory-schema-extensions-classes-and-attributes-used-by-lync-server.md)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="5e90d-107">For details about the schema changes required for Lync Server, see [Active Directory schema extensions, classes, and attributes used by Lync Server 2013](lync-server-2013-active-directory-schema-extensions-classes-and-attributes-used-by-lync-server.md).</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="5e90d-108">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="5e90d-108">In This Section</span></span>

  - [<span data-ttu-id="5e90d-109">Lync Server 2013에 대 한 Active Directory 인프라 요구 사항</span><span class="sxs-lookup"><span data-stu-id="5e90d-109">Active Directory infrastructure requirements for Lync Server 2013</span></span>](lync-server-2013-active-directory-infrastructure-requirements.md)

  - [<span data-ttu-id="5e90d-110">Lync Server 2013의 Active Directory 도메인 서비스 준비 개요</span><span class="sxs-lookup"><span data-stu-id="5e90d-110">Overview of Active Directory Domain Services preparation in Lync Server 2013</span></span>](lync-server-2013-overview-of-active-directory-domain-services-preparation.md)

  - [<span data-ttu-id="5e90d-111">Lync Server 2013에서 Active Directory 도메인 서비스 준비</span><span class="sxs-lookup"><span data-stu-id="5e90d-111">Preparing Active Directory Domain Services in Lync Server 2013</span></span>](lync-server-2013-preparing-active-directory-domain-services_1.md)

  - [<span data-ttu-id="5e90d-112">Lync Server 2013에서 잠긴 Active Directory 도메인 서비스 준비</span><span class="sxs-lookup"><span data-stu-id="5e90d-112">Preparing a locked-down Active Directory Domain Services in Lync Server 2013</span></span>](lync-server-2013-preparing-a-locked-down-active-directory-domain-services.md)

  - [<span data-ttu-id="5e90d-113">Lync Server 2013에서 사용 권한 부여</span><span class="sxs-lookup"><span data-stu-id="5e90d-113">Granting permissions in Lync Server 2013</span></span>](lync-server-2013-granting-permissions.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

