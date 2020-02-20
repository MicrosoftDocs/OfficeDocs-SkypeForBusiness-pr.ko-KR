---
title: 'Lync Server 2013: Lync Server에서 사용 하는 Active Directory 스키마 확장, 클래스 및 특성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Active Directory schema extensions, classes, and attributes used by Lync Server 2013
ms:assetid: 579bfa5a-9443-46dd-9a8e-07d00ba2824d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398379(v=OCS.15)
ms:contentKeyID: 48184188
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e393c5c65e77f22763380563e61c30bcdb69b23a
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145056"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="active-directory-schema-extensions-classes-and-attributes-used-by-lync-server-2013"></a><span data-ttu-id="d5151-102">Lync Server 2013에서 사용 하는 Active Directory 스키마 확장, 클래스 및 특성</span><span class="sxs-lookup"><span data-stu-id="d5151-102">Active Directory schema extensions, classes, and attributes used by Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d5151-103">_**마지막으로 수정 된 항목:** 2012-06-19_</span><span class="sxs-lookup"><span data-stu-id="d5151-103">_**Topic Last Modified:** 2012-06-19_</span></span>

<span data-ttu-id="d5151-104">이 참조 섹션에서 다루는 내용은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d5151-104">This reference section includes the following information:</span></span>

  - <span data-ttu-id="d5151-105">Lync Server 2013에 대 한 새로운 기능 또는 변경 된 Active Directory 스키마 확장</span><span class="sxs-lookup"><span data-stu-id="d5151-105">Active Directory schema extensions that are new or changed for Lync Server 2013</span></span>
    
    <span data-ttu-id="d5151-106">Active Directory 스키마에는 Active Directory 포리스트에서 만들어질 수 있는 모든 개체 클래스에 대한 형식 정의가 들어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d5151-106">The Active Directory schema contains formal definitions of every object class that can be created in an Active Directory forest.</span></span> <span data-ttu-id="d5151-107">또한 Active Directory 개체에서 가능한 모든 특성에 대한 형식 정의도 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d5151-107">The schema also contains formal definitions of every attribute that can exist on an Active Directory object.</span></span> <span data-ttu-id="d5151-108">Active Directory 전역 카탈로그에는 포리스트의 모든 개체에 대한 복제본이 각 개체의 일부 특성과 함께 들어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d5151-108">The Active Directory global catalog contains replicas of all the objects for the forest, along with a subset of the attributes for each object.</span></span> <span data-ttu-id="d5151-109">이 섹션에서는 Lync Server 2013에서 새로 만들거나 변경한 클래스 및 특성에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="d5151-109">This section describes the classes and attributes that are new or changed in Lync Server 2013.</span></span>

  - <span data-ttu-id="d5151-110">Lync Server에서 사용 하는 모든 클래스에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="d5151-110">All the classes used by Lync Server, with a description of each</span></span>

  - <span data-ttu-id="d5151-111">Lync Server에서 사용 하는 모든 특성에 대 한 설명이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d5151-111">All the attributes used by Lync Server, with a description of each</span></span>

  - <span data-ttu-id="d5151-112">Lync Server에서 사용 하는 클래스 목록과 각 특성에 포함할 수 있는 특성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d5151-112">A list of the classes used by Lync Server, with the attributes each may contain</span></span>

  - <span data-ttu-id="d5151-113">포리스트 준비 도중 생성되는 유니버설 서비스 및 관리 그룹과 전역 설정 및 개체</span><span class="sxs-lookup"><span data-stu-id="d5151-113">Global settings and objects, in addition to the universal service and administration groups that are created during forest preparation</span></span>

  - <span data-ttu-id="d5151-114">도메인 준비 도중 도메인 루트 및 기본 제공 컨테이너에 대해 생성되는 ACE(액세스 제어 항목)</span><span class="sxs-lookup"><span data-stu-id="d5151-114">Access control entries (ACEs) that are created on the domain root and built-in containers during domain preparation</span></span>

  - <span data-ttu-id="d5151-115">Active Directory OU (조직 구성 단위) 권한 부여\_cmdlet에 의해 수행 된 변경 내용입니다.</span><span class="sxs-lookup"><span data-stu-id="d5151-115">Changes that are made on an Active Directory organizational unit (OU) by the Grant\_CsSetupPermission cmdlet.</span></span>

  - <span data-ttu-id="d5151-116">Active Directory OU에서 csoupermission cmdlet을 부여\_하 여 변경한 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="d5151-116">Changes that are made on an Active Directory OU by the Grant\_CsOUPermission cmdlet.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="d5151-117">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="d5151-117">In This Section</span></span>

  - [<span data-ttu-id="d5151-118">Lync Server 2013의 스키마 변경 내용</span><span class="sxs-lookup"><span data-stu-id="d5151-118">Schema changes in Lync Server 2013</span></span>](lync-server-2013-schema-changes-in-lync-server-2013.md)

  - [<span data-ttu-id="d5151-119">Lync Server 2013의 스키마 클래스 및 설명</span><span class="sxs-lookup"><span data-stu-id="d5151-119">Schema classes and descriptions in Lync Server 2013</span></span>](lync-server-2013-schema-classes-and-descriptions.md)

  - [<span data-ttu-id="d5151-120">Lync Server 2013의 스키마 특성 및 설명</span><span class="sxs-lookup"><span data-stu-id="d5151-120">Schema attributes and descriptions in Lync Server 2013</span></span>](lync-server-2013-schema-attributes-and-descriptions.md)

  - [<span data-ttu-id="d5151-121">Lync Server 2013의 클래스별 스키마 특성</span><span class="sxs-lookup"><span data-stu-id="d5151-121">Schema attributes by class in Lync Server 2013</span></span>](lync-server-2013-schema-attributes-by-class.md)

  - [<span data-ttu-id="d5151-122">Lync Server 2013에서 포리스트 준비로 인 한 변경 사항</span><span class="sxs-lookup"><span data-stu-id="d5151-122">Changes made by forest preparation in Lync Server 2013</span></span>](lync-server-2013-changes-made-by-forest-preparation.md)

  - [<span data-ttu-id="d5151-123">Lync Server 2013에서 도메인 준비로 인 한 변경 사항</span><span class="sxs-lookup"><span data-stu-id="d5151-123">Changes made by domain preparation in Lync Server 2013</span></span>](lync-server-2013-changes-made-by-domain-preparation.md)

  - [<span data-ttu-id="d5151-124">Lync Server 2013의 부여-CsSetupPermission에서 수행한 변경 내용</span><span class="sxs-lookup"><span data-stu-id="d5151-124">Changes made by Grant-CsSetupPermission in Lync Server 2013</span></span>](lync-server-2013-changes-made-by-https://docs.microsoft.com/powershell/module/skype/Grant-CsSetupPermission)

  - [<span data-ttu-id="d5151-125">Lync Server 2013의 부여-CsOUPermission에서 변경한 내용</span><span class="sxs-lookup"><span data-stu-id="d5151-125">Changes made by Grant-CsOUPermission in Lync Server 2013</span></span>](lync-server-2013-changes-made-by-https://docs.microsoft.com/powershell/module/skype/Grant-CsOUPermission)

</div>

</div>

<span> </span>

</div>

</div>

</div>

