---
title: 비즈니스용 Skype 서버용 RBAC(역할 기반 액세스 제어)
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d01fba36-eb7e-4de9-9bba-5102ae157820
description: 비즈니스용 Skype 서버에는 보안에 Role-Based 높은 표준을 유지하면서 관리 작업을 위임할 수 있는 RBAC(액세스 제어) 그룹이 포함되어 있습니다. 이러한 그룹은 포리스트 준비 중에 만들어집니다. 포리스트 준비에 대한 자세한 내용은 비즈니스용 Skype 서버용 Active Directory 도메인 서비스를 참조하십시오. 포리스트 준비로 만든 특정 그룹에 대한 자세한 내용은 배포 설명서에서 비즈니스용 Skype 서버의 포리스트 준비에서 변경한 내용을 참조하십시오.
ms.openlocfilehash: 9d3c453d4e7c3057c03f99cf2ff31b5fe17ae0bb
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832108"
---
# <a name="role-based-access-control-rbac-for-skype-for-business-server"></a><span data-ttu-id="610e8-106">비즈니스용 Skype 서버용 RBAC(역할 기반 액세스 제어)</span><span class="sxs-lookup"><span data-stu-id="610e8-106">Role-based access control (RBAC) for Skype for Business Server</span></span>
 
<span data-ttu-id="610e8-107">비즈니스용 Skype 서버에는 보안에 Role-Based 높은 표준을 유지하면서 관리 작업을 위임할 수 있는 RBAC(액세스 제어) 그룹이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="610e8-107">Skype for Business Server includes Role-Based Access Control (RBAC) groups to enable you to delegate administrative tasks while maintaining high standards for security.</span></span> <span data-ttu-id="610e8-108">이러한 그룹은 포리스트 준비 중에 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="610e8-108">These groups are created during forest preparation.</span></span> <span data-ttu-id="610e8-109">포리스트 준비에 대한 자세한 내용은 비즈니스용 [Skype 서버용 Active Directory 도메인 서비스를 참조하십시오.](active-directory-domain-services.md)</span><span class="sxs-lookup"><span data-stu-id="610e8-109">For details about forest preparation, see [Active Directory Domain Services for Skype for Business Server](active-directory-domain-services.md).</span></span> <span data-ttu-id="610e8-110">포리스트 준비로 만든 특정 그룹에 대한 자세한 내용은 배포 설명서에서 비즈니스용 Skype 서버의 포리스트 [준비에서 변경한](../../schema-reference/active-directory-schema-extensions-classes-and-attributes/changes-made-by-forest-preparation.md) 내용을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="610e8-110">For details about the specific groups created by forest preparation, see [Changes made by forest preparation in Skype for Business Server](../../schema-reference/active-directory-schema-extensions-classes-and-attributes/changes-made-by-forest-preparation.md) in the Deployment documentation.</span></span>
  
<span data-ttu-id="610e8-111">RBAC를 사용하는 경우 대부분의 일반 관리 작업을 포함하는 11개의 미리 정의된 역할을 포함하여 사용자를 미리 정의된 관리 역할에 할당하여 관리 권한을 부여합니다.</span><span class="sxs-lookup"><span data-stu-id="610e8-111">With RBAC, administrative privilege is granted by assigning users to pre-defined administrative roles, including the 11 predefined roles that cover many common administrative tasks.</span></span> <span data-ttu-id="610e8-112">각 역할은 해당 역할의 사용자가 실행할 수 있는 비즈니스용 Skype 서버 관리 셸 cmdlet의 특정 목록과 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="610e8-112">Each role is associated with a specific list of Skype for Business Server Management Shell cmdlets that users in that role are allowed to run.</span></span> <span data-ttu-id="610e8-113">RBAC를 사용하여 사용자에게 작업에 필요한 관리 기능만 제공되는 "최소 권한" 원칙을 따를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="610e8-113">You can use RBAC to follow the principle of "least privilege," in which users are given only the administrative abilities that their jobs require.</span></span> 
  
<span data-ttu-id="610e8-114">RBAC 역할에 대한 자세한 내용은 역할 기반 액세스 제어 [계획에서 찾을 수 있습니다.](https://docs.microsoft.com/lyncserver/lync-server-2013-planning-for-role-based-access-control)</span><span class="sxs-lookup"><span data-stu-id="610e8-114">More details on RBAC roles can be found at [Planning for role-based access control](https://docs.microsoft.com/lyncserver/lync-server-2013-planning-for-role-based-access-control).</span></span>
