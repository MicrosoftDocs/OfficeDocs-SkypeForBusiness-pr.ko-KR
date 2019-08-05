---
title: Active Directory 스키마 확장, 클래스 및 특성
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 579bfa5a-9443-46dd-9a8e-07d00ba2824d
description: 이 참조 섹션에는 다음 정보가 포함 됩니다.
ms.openlocfilehash: 5934c9ffab8055de86cdaf3bcf507fa9c806f245
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36196818"
---
# <a name="active-directory-schema-extensions-classes-and-attributes"></a><span data-ttu-id="ee021-103">Active Directory 스키마 확장, 클래스 및 특성</span><span class="sxs-lookup"><span data-stu-id="ee021-103">Active Directory schema extensions, classes, and attributes</span></span>
 
<span data-ttu-id="ee021-104">이 참조 섹션에는 다음 정보가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ee021-104">This reference section includes the following information:</span></span> 
  
- <span data-ttu-id="ee021-105">비즈니스용 Skype 서버용으로 새로 만들거나 변경 된 Active Directory 스키마 확장</span><span class="sxs-lookup"><span data-stu-id="ee021-105">Active Directory schema extensions that are new or changed for Skype for Business Server</span></span>
    
    <span data-ttu-id="ee021-106">Active Directory 스키마에는 Active Directory 포리스트에서 만들 수 있는 모든 개체 클래스의 형식 정의가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ee021-106">The Active Directory schema contains formal definitions of every object class that can be created in an Active Directory forest.</span></span> <span data-ttu-id="ee021-107">또한 스키마에는 Active Directory 개체에 있을 수 있는 모든 특성의 형식 정의가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ee021-107">The schema also contains formal definitions of every attribute that can exist on an Active Directory object.</span></span> <span data-ttu-id="ee021-108">Active Directory 글로벌 카탈로그에는 각 개체에 대 한 특성의 하위 집합을 비롯 하 여 포리스트의 모든 개체 복제본이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ee021-108">The Active Directory global catalog contains replicas of all the objects for the forest, along with a subset of the attributes for each object.</span></span> <span data-ttu-id="ee021-109">이 섹션에서는 비즈니스용 Skype 서버에서 새로 만들거나 변경 된 클래스 및 특성에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="ee021-109">This section describes the classes and attributes that are new or changed in Skype for Business Server.</span></span>
    
- <span data-ttu-id="ee021-110">비즈니스용 Skype 서버에서 사용 되는 모든 클래스에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="ee021-110">All the classes used by Skype for Business Server, with a description of each</span></span>
    
- <span data-ttu-id="ee021-111">비즈니스용 Skype 서버에서 사용 되는 모든 특성에 대 한 설명이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ee021-111">All the attributes used by Skype for Business Server, with a description of each</span></span>
    
- <span data-ttu-id="ee021-112">비즈니스용 Skype Server에 사용 되는 수업 목록으로, 각 속성에 포함 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ee021-112">A list of the classes used by Skype for Business Server, with the attributes each may contain</span></span>
    
- <span data-ttu-id="ee021-113">포리스트 준비 중에 만든 유니버설 서비스 및 관리 그룹 외에 전역 설정 및 개체</span><span class="sxs-lookup"><span data-stu-id="ee021-113">Global settings and objects, in addition to the universal service and administration groups that are created during forest preparation</span></span>
    
- <span data-ttu-id="ee021-114">도메인을 준비 하는 동안 도메인 루트 및 기본 제공 컨테이너에서 만들어진 Ace (액세스 제어 항목)</span><span class="sxs-lookup"><span data-stu-id="ee021-114">Access control entries (ACEs) that are created on the domain root and built-in containers during domain preparation</span></span>
    
- <span data-ttu-id="ee021-115">Grant_CsSetupPermission cmdlet에서 Active Directory OU (조직 구성 단위)에 대 한 변경 내용을 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="ee021-115">Changes that are made on an Active Directory organizational unit (OU) by the Grant_CsSetupPermission cmdlet.</span></span>
    
- <span data-ttu-id="ee021-116">Grant_CsOUPermission cmdlet에서 Active Directory OU에 대해 변경한 내용</span><span class="sxs-lookup"><span data-stu-id="ee021-116">Changes that are made on an Active Directory OU by the Grant_CsOUPermission cmdlet.</span></span>
    
## <a name="in-this-section"></a><span data-ttu-id="ee021-117">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="ee021-117">In This Section</span></span>

- [<span data-ttu-id="ee021-118">비즈니스용 Skype 서버의 스키마 변경</span><span class="sxs-lookup"><span data-stu-id="ee021-118">Schema changes in Skype for Business Server</span></span>](schema-changes.md)
    
- [<span data-ttu-id="ee021-119">비즈니스용 Skype 서버의 스키마 클래스 및 설명</span><span class="sxs-lookup"><span data-stu-id="ee021-119">Schema classes and descriptions in Skype for Business Server</span></span>](schema-classes-and-descriptions.md)
    
- [<span data-ttu-id="ee021-120">비즈니스용 Skype 서버의 스키마 특성 및 설명</span><span class="sxs-lookup"><span data-stu-id="ee021-120">Schema attributes and descriptions in Skype for Business Server</span></span>](schema-attributes-and-descriptions.md)
    
- [<span data-ttu-id="ee021-121">비즈니스용 Skype 서버에서 클래스별 스키마 특성</span><span class="sxs-lookup"><span data-stu-id="ee021-121">Schema attributes by class in Skype for Business Server</span></span>](schema-attributes-by-class.md)
    
- [<span data-ttu-id="ee021-122">비즈니스용 Skype 서버에서 포리스트 준비에의 한 변경 사항</span><span class="sxs-lookup"><span data-stu-id="ee021-122">Changes made by forest preparation in Skype for Business Server</span></span>](changes-made-by-forest-preparation.md)
    
- [<span data-ttu-id="ee021-123">비즈니스용 Skype 서버에서 도메인 준비에의 한 변경 사항</span><span class="sxs-lookup"><span data-stu-id="ee021-123">Changes made by domain preparation in Skype for Business Server</span></span>](changes-made-by-domain-preparation.md)
    
- [<span data-ttu-id="ee021-124">비즈니스용 Skype 서버에서-Cssetupsetuppermission 허용에의 한 변경 내용</span><span class="sxs-lookup"><span data-stu-id="ee021-124">Changes made by Grant-CsSetupPermission in Skype for Business Server</span></span>](changes-made-by-grant-cssetuppermission.md)
    
- [<span data-ttu-id="ee021-125">비즈니스용 Skype 서버에서 변경 사항 허용-CsOUPermission</span><span class="sxs-lookup"><span data-stu-id="ee021-125">Changes made by Grant-CsOUPermission in Skype for Business Server</span></span>](changes-made-by-grant-csoupermission.md)
    

