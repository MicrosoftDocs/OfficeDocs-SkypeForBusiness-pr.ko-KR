---
title: 'Lync Server 2013: RBAC (역할 기반 액세스 제어)'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Role-based access control (RBAC) for Lync Server 2013
ms:assetid: d01fba36-eb7e-4de9-9bba-5102ae157820
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn481134(v=OCS.15)
ms:contentKeyID: 59893872
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 46f0fd496c8aa42a1dc498df00288c807a7556cb
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42144574"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="role-based-access-control-rbac-for-lync-server-2013"></a><span data-ttu-id="d4b2d-102">Lync Server 2013의 RBAC (역할 기반 액세스 제어)</span><span class="sxs-lookup"><span data-stu-id="d4b2d-102">Role-based access control (RBAC) for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d4b2d-103">_**마지막으로 수정 된 항목:** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="d4b2d-103">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="d4b2d-104">Microsoft Lync Server 2013에는 RBAC (역할 기반 액세스 제어) 그룹이 포함 되어 있어 보안에 대 한 높은 표준을 유지 하면서 관리 작업을 위임할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d4b2d-104">Microsoft Lync Server 2013 includes Role-Based Access Control (RBAC) groups to enable you to delegate administrative tasks while maintaining high standards for security.</span></span> <span data-ttu-id="d4b2d-105">이러한 그룹은 포리스트 준비 중에 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="d4b2d-105">These groups are created during forest preparation.</span></span> <span data-ttu-id="d4b2d-106">포리스트 준비에 대 한 자세한 내용은 [Active Directory Domain Services For Lync Server 2013](lync-server-2013-active-directory-domain-services-for-lync-server.md)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="d4b2d-106">For details about forest preparation, see [Active Directory Domain Services for Lync Server 2013](lync-server-2013-active-directory-domain-services-for-lync-server.md).</span></span> <span data-ttu-id="d4b2d-107">포리스트 준비로 만든 특정 그룹에 대 한 자세한 내용은 배포 설명서의 [Lync Server 2013에서 포리스트 준비로 인 한 변경 사항](lync-server-2013-changes-made-by-forest-preparation.md) 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="d4b2d-107">For details about the specific groups created by forest preparation, see [Changes made by forest preparation in Lync Server 2013](lync-server-2013-changes-made-by-forest-preparation.md) in the Deployment documentation.</span></span>

<span data-ttu-id="d4b2d-108">RBAC를 사용하는 경우 대부분의 일반 관리 작업을 포함하는 11개의 미리 정의된 역할을 포함하여 사용자를 미리 정의된 관리 역할에 할당하여 관리 권한을 부여합니다.</span><span class="sxs-lookup"><span data-stu-id="d4b2d-108">With RBAC, administrative privilege is granted by assigning users to pre-defined administrative roles, including the 11 predefined roles that cover many common administrative tasks.</span></span> <span data-ttu-id="d4b2d-109">각 역할은 해당 역할의 사용자가 실행할 수 있는 Lync Server 관리 셸 cmdlet의 특정 목록과 연결 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d4b2d-109">Each role is associated with a specific list of Lync Server Management Shell cmdlets that users in that role are allowed to run.</span></span> <span data-ttu-id="d4b2d-110">RBAC를 사용하여 사용자에게 작업에 필요한 관리 기능만 제공되는 "최소 권한" 원칙을 따를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d4b2d-110">You can use RBAC to follow the principle of "least privilege," in which users are given only the administrative abilities that their jobs require.</span></span> <span data-ttu-id="d4b2d-111">자세한 내용은 계획 설명서의 [Lync Server 2013에서 역할 기반 액세스 제어 계획](lync-server-2013-planning-for-role-based-access-control.md) 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="d4b2d-111">For details, see [Planning for role-based access control in Lync Server 2013](lync-server-2013-planning-for-role-based-access-control.md) in the Planning documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

