---
title: 비즈니스용 Skype 서버용에 대 한 RBAC (역할 기반 액세스 제어)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d01fba36-eb7e-4de9-9bba-5102ae157820
description: 비즈니스용 Skype 서버에는 관리 작업을 위임할 수 있는 RBAC (역할 기반 액세스 제어) 그룹이 포함 되어 있으며 보안에 대 한 높은 표준도 유지 됩니다. 이러한 그룹은 포리스트 준비 중에 만들어집니다. 포리스트 준비에 대 한 자세한 내용은 비즈니스용 Skype 용 Active Directory 도메인 서비스 서버용을 참조 하세요. 포리스트 준비로 만든 특정 그룹에 대 한 자세한 내용은 배포 설명서의 비즈니스용 Skype 서버에서 포리스트 준비에의 한 변경 내용을 참조 하세요.
ms.openlocfilehash: d5f31d7c53c743e4b2d001b00abec7ec93ef8d91
ms.sourcegitcommit: c554b09527817dc3e06b10509f6668b42ccc5cb9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/17/2019
ms.locfileid: "36197988"
---
# <a name="role-based-access-control-rbac-for-skype-for-business-server"></a><span data-ttu-id="e74e0-106">비즈니스용 Skype 서버용에 대 한 RBAC (역할 기반 액세스 제어)</span><span class="sxs-lookup"><span data-stu-id="e74e0-106">Role-based access control (RBAC) for Skype for Business Server</span></span>
 
<span data-ttu-id="e74e0-107">비즈니스용 Skype 서버에는 관리 작업을 위임할 수 있는 RBAC (역할 기반 액세스 제어) 그룹이 포함 되어 있으며 보안에 대 한 높은 표준도 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e74e0-107">Skype for Business Server includes Role-Based Access Control (RBAC) groups to enable you to delegate administrative tasks while maintaining high standards for security.</span></span> <span data-ttu-id="e74e0-108">이러한 그룹은 포리스트 준비 중에 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="e74e0-108">These groups are created during forest preparation.</span></span> <span data-ttu-id="e74e0-109">포리스트 준비에 대 한 자세한 내용은 [비즈니스용 Skype 용 Active Directory 도메인 서비스 서버용](active-directory-domain-services.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e74e0-109">For details about forest preparation, see [Active Directory Domain Services for Skype for Business Server](active-directory-domain-services.md).</span></span> <span data-ttu-id="e74e0-110">포리스트 준비로 만든 특정 그룹에 대 한 자세한 내용은 배포 설명서의 [비즈니스용 Skype 서버에서 포리스트 준비에의 한 변경 내용을](../../schema-reference/active-directory-schema-extensions-classes-and-attributes/changes-made-by-forest-preparation.md) 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e74e0-110">For details about the specific groups created by forest preparation, see [Changes made by forest preparation in Skype for Business Server](../../schema-reference/active-directory-schema-extensions-classes-and-attributes/changes-made-by-forest-preparation.md) in the Deployment documentation.</span></span>
  
<span data-ttu-id="e74e0-111">RBAC를 사용 하면 여러 일반적인 관리 작업을 처리 하는 11 개의 미리 정의 된 역할을 포함 하 여 사용자를 미리 정의한 관리 역할에 할당 하는 관리 권한이 부여 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e74e0-111">With RBAC, administrative privilege is granted by assigning users to pre-defined administrative roles, including the 11 predefined roles that cover many common administrative tasks.</span></span> <span data-ttu-id="e74e0-112">각 역할은 해당 역할의 사용자가 실행할 수 있는 비즈니스용 Skype Server Management Shell cmdlet의 특정 목록과 연결 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e74e0-112">Each role is associated with a specific list of Skype for Business Server Management Shell cmdlets that users in that role are allowed to run.</span></span> <span data-ttu-id="e74e0-113">RBAC를 사용 하 여 사용자에 게 해당 작업에 필요한 관리 기능만 제공 하는 "최소 권한"의 원칙을 따를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e74e0-113">You can use RBAC to follow the principle of "least privilege," in which users are given only the administrative abilities that their jobs require.</span></span> 
  
<span data-ttu-id="e74e0-114">RBAC 역할에 대 한 자세한 내용은 [역할 기반 액세스 제어에 대 한 계획](https://docs.microsoft.com/lyncserver/lync-server-2013-planning-for-role-based-access-control)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e74e0-114">More details on RBAC roles can be found at [Planning for role-based access control](https://docs.microsoft.com/lyncserver/lync-server-2013-planning-for-role-based-access-control).</span></span>
