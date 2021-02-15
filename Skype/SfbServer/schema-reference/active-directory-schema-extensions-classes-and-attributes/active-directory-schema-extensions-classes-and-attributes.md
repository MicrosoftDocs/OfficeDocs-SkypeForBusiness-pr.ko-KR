---
title: Active Directory 스키마 확장, 클래스 및 속성
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 579bfa5a-9443-46dd-9a8e-07d00ba2824d
description: 이 참조 섹션에서 다루는 내용은 다음과 같습니다.
ms.openlocfilehash: 5c8a1ceb6b623466219cbd3df46ff2b39ccceb2c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831938"
---
# <a name="active-directory-schema-extensions-classes-and-attributes"></a><span data-ttu-id="bfb81-103">Active Directory 스키마 확장, 클래스 및 속성</span><span class="sxs-lookup"><span data-stu-id="bfb81-103">Active Directory schema extensions, classes, and attributes</span></span>
 
<span data-ttu-id="bfb81-104">이 참조 섹션에서 다루는 내용은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="bfb81-104">This reference section includes the following information:</span></span> 
  
- <span data-ttu-id="bfb81-105">비즈니스용 Skype 서버에 대해 새로 추가되거나 변경된 Active Directory schema 확장</span><span class="sxs-lookup"><span data-stu-id="bfb81-105">Active Directory schema extensions that are new or changed for Skype for Business Server</span></span>
    
    <span data-ttu-id="bfb81-106">Active Directory 스키마에는 Active Directory 포리스트에서 만들어질 수 있는 모든 개체 클래스에 대한 형식 정의가 들어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bfb81-106">The Active Directory schema contains formal definitions of every object class that can be created in an Active Directory forest.</span></span> <span data-ttu-id="bfb81-107">또한 Active Directory 개체에서 가능한 모든 특성에 대한 형식 정의도 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bfb81-107">The schema also contains formal definitions of every attribute that can exist on an Active Directory object.</span></span> <span data-ttu-id="bfb81-108">Active Directory 전역 카탈로그에는 포리스트의 모든 개체에 대한 복제본이 각 개체의 일부 특성과 함께 들어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bfb81-108">The Active Directory global catalog contains replicas of all the objects for the forest, along with a subset of the attributes for each object.</span></span> <span data-ttu-id="bfb81-109">이 섹션에서는 비즈니스용 Skype 서버에서 새로 추가되거나 변경된 클래스 및 특성에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="bfb81-109">This section describes the classes and attributes that are new or changed in Skype for Business Server.</span></span>
    
- <span data-ttu-id="bfb81-110">비즈니스용 Skype 서버에서 사용하는 모든 클래스(각 클래스에 대한 설명 포함)</span><span class="sxs-lookup"><span data-stu-id="bfb81-110">All the classes used by Skype for Business Server, with a description of each</span></span>
    
- <span data-ttu-id="bfb81-111">비즈니스용 Skype 서버에서 사용하는 모든 특성 및 각 특성에 대한 설명</span><span class="sxs-lookup"><span data-stu-id="bfb81-111">All the attributes used by Skype for Business Server, with a description of each</span></span>
    
- <span data-ttu-id="bfb81-112">비즈니스용 Skype 서버에서 사용하는 클래스 목록( 각 클래스에 포함될 수 있는 특성 포함)</span><span class="sxs-lookup"><span data-stu-id="bfb81-112">A list of the classes used by Skype for Business Server, with the attributes each may contain</span></span>
    
- <span data-ttu-id="bfb81-113">포리스트 준비 도중 생성되는 유니버설 서비스 및 관리 그룹과 전역 설정 및 개체</span><span class="sxs-lookup"><span data-stu-id="bfb81-113">Global settings and objects, in addition to the universal service and administration groups that are created during forest preparation</span></span>
    
- <span data-ttu-id="bfb81-114">도메인 준비 도중 도메인 루트 및 기본 제공 컨테이너에 대해 생성되는 ACE(액세스 제어 항목)</span><span class="sxs-lookup"><span data-stu-id="bfb81-114">Access control entries (ACEs) that are created on the domain root and built-in containers during domain preparation</span></span>
    
- <span data-ttu-id="bfb81-115">Active Directory OU(조직 구성 단위)에서 Grant_CsSetupPermission cmdlet으로 수행한 변경 내용</span><span class="sxs-lookup"><span data-stu-id="bfb81-115">Changes that are made on an Active Directory organizational unit (OU) by the Grant_CsSetupPermission cmdlet.</span></span>
    
- <span data-ttu-id="bfb81-116">Active Directory OU에서 Grant_CsOUPermission cmdlet으로 수행한 변경 내용</span><span class="sxs-lookup"><span data-stu-id="bfb81-116">Changes that are made on an Active Directory OU by the Grant_CsOUPermission cmdlet.</span></span>
    
## <a name="in-this-section"></a><span data-ttu-id="bfb81-117">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="bfb81-117">In This Section</span></span>

- [<span data-ttu-id="bfb81-118">비즈니스용 Skype 서버의 Schema 변경 사항</span><span class="sxs-lookup"><span data-stu-id="bfb81-118">Schema changes in Skype for Business Server</span></span>](schema-changes.md)
    
- [<span data-ttu-id="bfb81-119">비즈니스용 Skype 서버의 Schema 클래스 및 설명</span><span class="sxs-lookup"><span data-stu-id="bfb81-119">Schema classes and descriptions in Skype for Business Server</span></span>](schema-classes-and-descriptions.md)
    
- [<span data-ttu-id="bfb81-120">비즈니스용 Skype 서버의 Schema 특성 및 설명</span><span class="sxs-lookup"><span data-stu-id="bfb81-120">Schema attributes and descriptions in Skype for Business Server</span></span>](schema-attributes-and-descriptions.md)
    
- [<span data-ttu-id="bfb81-121">비즈니스용 Skype 서버의 클래스당 Schema 특성</span><span class="sxs-lookup"><span data-stu-id="bfb81-121">Schema attributes by class in Skype for Business Server</span></span>](schema-attributes-by-class.md)
    
- [<span data-ttu-id="bfb81-122">비즈니스용 Skype 서버에서 포리스트 준비로 변경한 내용</span><span class="sxs-lookup"><span data-stu-id="bfb81-122">Changes made by forest preparation in Skype for Business Server</span></span>](changes-made-by-forest-preparation.md)
    
- [<span data-ttu-id="bfb81-123">비즈니스용 Skype 서버에서 도메인 준비로 변경한 내용</span><span class="sxs-lookup"><span data-stu-id="bfb81-123">Changes made by domain preparation in Skype for Business Server</span></span>](changes-made-by-domain-preparation.md)
    
- [<span data-ttu-id="bfb81-124">비즈니스용 Skype Grant-CsSetupPermission 사용자에 의해 변경된 내용</span><span class="sxs-lookup"><span data-stu-id="bfb81-124">Changes made by Grant-CsSetupPermission in Skype for Business Server</span></span>](changes-made-by-grant-cssetuppermission.md)
    
- [<span data-ttu-id="bfb81-125">비즈니스용 Skype Grant-CsOUPermission 사용자에 의해 변경된 내용</span><span class="sxs-lookup"><span data-stu-id="bfb81-125">Changes made by Grant-CsOUPermission in Skype for Business Server</span></span>](changes-made-by-grant-csoupermission.md)
    

