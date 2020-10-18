---
title: 'Lync Server 2013: SQL Server에 대 한 배포 권한'
description: 'Lync Server 2013: SQL Server에 대 한 배포 권한'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment permissions for SQL Server
ms:assetid: 56ea0c02-bcf5-4d45-aa13-570531c29074
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398375(v=OCS.15)
ms:contentKeyID: 48184197
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: be5985bc8f3173b03d8969d3dd58cfbf8daf85f8
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48575724"
---
# <a name="deployment-permissions-for-sql-server-in-lync-server-2013"></a><span data-ttu-id="35ad6-103">Lync Server 2013의 SQL Server에 대 한 배포 권한</span><span class="sxs-lookup"><span data-stu-id="35ad6-103">Deployment permissions for SQL Server in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="35ad6-104">_**마지막으로 수정 된 항목:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="35ad6-104">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="35ad6-105">Microsoft SQL Server 2012에는 Lync Server 2013을 설치 및 배포할 때 특정 요구 사항이 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="35ad6-105">Microsoft SQL Server 2012 has specific requirements when installing and deploying Lync Server 2013.</span></span> <span data-ttu-id="35ad6-106">Windows 및 SQL Server에서는 보안을 다르게 정의 하기 때문에 Active Directory 도메인의 관리자로 로그인 하면 SQL Server에 대 한 사용 권한을 암시적으로 부여 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="35ad6-106">Because Windows and SQL Server define their security differently, logging in as an administrator in the Active Directory domain does not implicitly grant permissions for SQL Server.</span></span> <span data-ttu-id="35ad6-107">즉, 구성 중인 SQL Server 기반 서버에서 sysadmin 엔터티의 구성원이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="35ad6-107">You must also be a member of the sysadmin entity on the SQL Server-based server you are configuring.</span></span>

<div>

## <a name="permissions-required-for-database-and-lync-server-installation"></a><span data-ttu-id="35ad6-108">데이터베이스 및 Lync Server 설치에 필요한 사용 권한</span><span class="sxs-lookup"><span data-stu-id="35ad6-108">Permissions Required for Database and Lync Server Installation</span></span>

<span data-ttu-id="35ad6-109">다음 옵션은 Lync Server 2013 파일과 SQL Server 데이터베이스 설치에 대 한 세 가지 권한 및 그룹 구성원 연결에 대해 자세히 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="35ad6-109">The following options detail three permissions and group membership associations for installation of Lync Server 2013 files and SQL Server databases.</span></span> <span data-ttu-id="35ad6-110">조직의 요구 사항에 가장 적합한 시나리오를 선택하십시오.</span><span class="sxs-lookup"><span data-stu-id="35ad6-110">Choose the scenario that best meets the requirements of your organization.</span></span>

### <a name="permissions-and-group-membership-associations"></a><span data-ttu-id="35ad6-111">사용 권한 및 그룹 구성원 연결</span><span class="sxs-lookup"><span data-stu-id="35ad6-111">Permissions and Group Membership Associations</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="35ad6-112">SQL Server 또는 Lync Server 2013 역할</span><span class="sxs-lookup"><span data-stu-id="35ad6-112">SQL Server or Lync Server 2013 role</span></span></th>
<th><span data-ttu-id="35ad6-113">역할의 일반적인 SQL Server 사용 권한 및 그룹 구성원</span><span class="sxs-lookup"><span data-stu-id="35ad6-113">Role-Typical SQL Server permissions and group membership</span></span></th>
<th><span data-ttu-id="35ad6-114">역할-일반적인 Lync Server 2013 사용 권한 및 그룹 구성원 자격</span><span class="sxs-lookup"><span data-stu-id="35ad6-114">Role-typical Lync Server 2013 permissions and group membership</span></span></th>
<th><span data-ttu-id="35ad6-115">사용 권한의 결과</span><span class="sxs-lookup"><span data-stu-id="35ad6-115">Permissions outcome</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="35ad6-116">Lync Server 2013 관리자</span><span class="sxs-lookup"><span data-stu-id="35ad6-116">Lync Server 2013 administrator</span></span></p></td>
<td><p><span data-ttu-id="35ad6-117">SQL Server 로컬 Administrators 그룹 구성원 및 sysadmins SQL Server 보안 그룹 구성원 자격이 부여되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="35ad6-117">Must be granted membership of sysadmins SQL Server security group and member of the SQL Server local Administrators group</span></span></p></td>
<td><p><span data-ttu-id="35ad6-118">RTCUniversalServerAdmins 그룹 구성원이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="35ad6-118">Must be a member of the RTCUniversalServerAdmins group</span></span></p></td>
<td><p><span data-ttu-id="35ad6-119">Lync Server 2013 관리자에 게 Lync Server 2013 및 SQL Server 데이터베이스를 모두 설치할 수 있는 적절 한 권한이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="35ad6-119">Lync Server 2013 administrator has the proper permissions to install both Lync Server 2013 and SQL Server databases.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="35ad6-120">SQL Server 관리자</span><span class="sxs-lookup"><span data-stu-id="35ad6-120">SQL Server administrator</span></span></p></td>
<td><p><span data-ttu-id="35ad6-121">SQL Server sysadmin 그룹 구성원이거나 그와 동등한 권한을 가져야 하며, SQL Server 로컬 Administrators 그룹 구성원이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="35ad6-121">SQL Server sysadmin group member (or equivalent) and member of the SQL Server local Administrators group</span></span></p></td>
<td><p><span data-ttu-id="35ad6-122">RTCUniversalServerReadOnly 그룹 구성원이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="35ad6-122">Must be a member of the RTCUniversalServerReadOnly group</span></span></p></td>
<td><p><span data-ttu-id="35ad6-123">SQL Server 관리자에 게 Lync Server 2013 및 SQL Server 데이터베이스를 모두 설치할 수 있는 적절 한 권한이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="35ad6-123">SQL Server administrator has the proper permissions to install both Lync Server 2013 and SQL Server databases.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="35ad6-124">설치 작업을 공유하는 두 관리자 모두</span><span class="sxs-lookup"><span data-stu-id="35ad6-124">Both administrators sharing installation duties</span></span></p></td>
<td><p><span data-ttu-id="35ad6-125">SQL Server 관리자가 sysadmins 그룹 구성원이거나 그와 동등한 권한을 가져야 하며, SQL Server 로컬 Administrators 그룹 구성원이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="35ad6-125">SQL Server administrator is member of sysadmins group (or equivalent) and member of the SQL Server local Administrators group</span></span></p></td>
<td><p><span data-ttu-id="35ad6-126">Lync Server 2013 관리자가 RTCUniversalServerAdmins의 구성원 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="35ad6-126">Lync Server 2013 administrator is member of RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="35ad6-127">Lync Server 2013 관리자는 Lync Server 2013를 설치할 수 있지만 데이터베이스를 설치할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="35ad6-127">The Lync Server 2013 administrator can install Lync Server 2013, but cannot install the databases.</span></span> <span data-ttu-id="35ad6-128">SQL Server 관리자는 lync server 2013 관리자가 제공 하는 Lync 서버 관리 셸 및 Windows PowerShell cmdlet을 사용 하 여 데이터베이스를 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="35ad6-128">The SQL Server administrator uses the Lync Server Management Shell and Windows PowerShell cmdlets provided by the Lync Server 2013 administrator to install the databases.</span></span> <span data-ttu-id="35ad6-129">SQL Server 관리자가 사용 하는 Lync Server 2013 관리 셸이 프런트 엔드 서버에 설치 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="35ad6-129">The Lync Server 2013 Management Shell used by the SQL Server administrator is installed on the Front End Server.</span></span> <span data-ttu-id="35ad6-130">이를 통해 SQL Server 기반 서버에 Lync Server 2013 관리 도구를 설치할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="35ad6-130">This eliminates the need to install the Lync Server 2013 administrative tools on the SQL Server-based server.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

