---
title: 'Lync Server 2013: Lync Server에서 사용하는 Active Directory 스키마 확장, 클래스 및 속성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Active Directory schema extensions, classes, and attributes used by Lync Server 2013
ms:assetid: 579bfa5a-9443-46dd-9a8e-07d00ba2824d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398379(v=OCS.15)
ms:contentKeyID: 48184188
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3dc883c1c85acbe41bec6a25467e50800c036996
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979251"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="active-directory-schema-extensions-classes-and-attributes-used-by-lync-server-2013"></a><span data-ttu-id="f9c46-102">Lync Server 2013에서 사용하는 Active Directory 스키마 확장, 클래스 및 속성</span><span class="sxs-lookup"><span data-stu-id="f9c46-102">Active Directory schema extensions, classes, and attributes used by Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f9c46-103">_**마지막으로 수정한 주제:** 2012-06-19_</span><span class="sxs-lookup"><span data-stu-id="f9c46-103">_**Topic Last Modified:** 2012-06-19_</span></span>

<span data-ttu-id="f9c46-104">이 참조 섹션에는 다음 정보가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f9c46-104">This reference section includes the following information:</span></span>

  - <span data-ttu-id="f9c46-105">Lync Server 2013의 신규 또는 변경 된 Active Directory 스키마 확장</span><span class="sxs-lookup"><span data-stu-id="f9c46-105">Active Directory schema extensions that are new or changed for Lync Server 2013</span></span>
    
    <span data-ttu-id="f9c46-106">Active Directory 스키마에는 Active Directory 포리스트에서 만들 수 있는 모든 개체 클래스의 형식 정의가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f9c46-106">The Active Directory schema contains formal definitions of every object class that can be created in an Active Directory forest.</span></span> <span data-ttu-id="f9c46-107">또한 스키마에는 Active Directory 개체에 있을 수 있는 모든 특성의 형식 정의가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f9c46-107">The schema also contains formal definitions of every attribute that can exist on an Active Directory object.</span></span> <span data-ttu-id="f9c46-108">Active Directory 글로벌 카탈로그에는 각 개체에 대 한 특성의 하위 집합을 비롯 하 여 포리스트의 모든 개체 복제본이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f9c46-108">The Active Directory global catalog contains replicas of all the objects for the forest, along with a subset of the attributes for each object.</span></span> <span data-ttu-id="f9c46-109">이 섹션에서는 Lync Server 2013에서 새로 만들거나 변경한 클래스 및 특성에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="f9c46-109">This section describes the classes and attributes that are new or changed in Lync Server 2013.</span></span>

  - <span data-ttu-id="f9c46-110">Lync Server에 사용 되는 모든 클래스에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="f9c46-110">All the classes used by Lync Server, with a description of each</span></span>

  - <span data-ttu-id="f9c46-111">Lync Server에서 사용 하는 모든 특성에 대 한 설명이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f9c46-111">All the attributes used by Lync Server, with a description of each</span></span>

  - <span data-ttu-id="f9c46-112">Lync Server에서 사용 하는 클래스 목록으로, 각 특성이 포함할 수 있는 특성</span><span class="sxs-lookup"><span data-stu-id="f9c46-112">A list of the classes used by Lync Server, with the attributes each may contain</span></span>

  - <span data-ttu-id="f9c46-113">포리스트 준비 중에 만든 유니버설 서비스 및 관리 그룹 외에 전역 설정 및 개체</span><span class="sxs-lookup"><span data-stu-id="f9c46-113">Global settings and objects, in addition to the universal service and administration groups that are created during forest preparation</span></span>

  - <span data-ttu-id="f9c46-114">도메인을 준비 하는 동안 도메인 루트 및 기본 제공 컨테이너에서 만들어진 Ace (액세스 제어 항목)</span><span class="sxs-lookup"><span data-stu-id="f9c46-114">Access control entries (ACEs) that are created on the domain root and built-in containers during domain preparation</span></span>

  - <span data-ttu-id="f9c46-115">Cssetuppermission cmdlet 권한을 부여\_하 여 ACTIVE Directory OU (조직 구성 단위)에 대 한 변경 내용입니다.</span><span class="sxs-lookup"><span data-stu-id="f9c46-115">Changes that are made on an Active Directory organizational unit (OU) by the Grant\_CsSetupPermission cmdlet.</span></span>

  - <span data-ttu-id="f9c46-116">Csoupermission cmdlet을 부여\_하 여 ACTIVE Directory OU에 대 한 변경 내용을 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="f9c46-116">Changes that are made on an Active Directory OU by the Grant\_CsOUPermission cmdlet.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="f9c46-117">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="f9c46-117">In This Section</span></span>

  - [<span data-ttu-id="f9c46-118">Lync Server 2013의 스키마 변경 사항</span><span class="sxs-lookup"><span data-stu-id="f9c46-118">Schema changes in Lync Server 2013</span></span>](lync-server-2013-schema-changes-in-lync-server-2013.md)

  - [<span data-ttu-id="f9c46-119">Lync Server 2013의 스키마 클래스 및 설명</span><span class="sxs-lookup"><span data-stu-id="f9c46-119">Schema classes and descriptions in Lync Server 2013</span></span>](lync-server-2013-schema-classes-and-descriptions.md)

  - [<span data-ttu-id="f9c46-120">Lync Server 2013의 스키마 특성 및 설명</span><span class="sxs-lookup"><span data-stu-id="f9c46-120">Schema attributes and descriptions in Lync Server 2013</span></span>](lync-server-2013-schema-attributes-and-descriptions.md)

  - [<span data-ttu-id="f9c46-121">Lync Server 2013의 클래스별 스키마 특성</span><span class="sxs-lookup"><span data-stu-id="f9c46-121">Schema attributes by class in Lync Server 2013</span></span>](lync-server-2013-schema-attributes-by-class.md)

  - [<span data-ttu-id="f9c46-122">Lync Server 2013의 포리스트 준비에의 한 변경 사항</span><span class="sxs-lookup"><span data-stu-id="f9c46-122">Changes made by forest preparation in Lync Server 2013</span></span>](lync-server-2013-changes-made-by-forest-preparation.md)

  - [<span data-ttu-id="f9c46-123">Lync Server 2013에서 도메인 준비에의 한 변경 사항</span><span class="sxs-lookup"><span data-stu-id="f9c46-123">Changes made by domain preparation in Lync Server 2013</span></span>](lync-server-2013-changes-made-by-domain-preparation.md)

  - [<span data-ttu-id="f9c46-124">Lync Server 2013의 허용-Cssetupsetuppermission에의 한 변경 내용</span><span class="sxs-lookup"><span data-stu-id="f9c46-124">Changes made by Grant-CsSetupPermission in Lync Server 2013</span></span>](lync-server-2013-changes-made-by-https://docs.microsoft.com/powershell/module/skype/Grant-CsSetupPermission)

  - [<span data-ttu-id="f9c46-125">Lync Server 2013의 허용-CsOUPermission에의 한 변경 내용</span><span class="sxs-lookup"><span data-stu-id="f9c46-125">Changes made by Grant-CsOUPermission in Lync Server 2013</span></span>](lync-server-2013-changes-made-by-https://docs.microsoft.com/powershell/module/skype/Grant-CsOUPermission)

</div>

</div>

<span> </span>

</div>

</div>

</div>

