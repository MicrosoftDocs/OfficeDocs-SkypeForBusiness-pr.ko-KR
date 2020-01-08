---
title: 'Lync Server 2013: SQL Server에 대한 배포 권한'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deployment permissions for SQL Server
ms:assetid: 56ea0c02-bcf5-4d45-aa13-570531c29074
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398375(v=OCS.15)
ms:contentKeyID: 48184197
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ea0334c7070ae3aadb3191da4bf036a978878688
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982810"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-permissions-for-sql-server-in-lync-server-2013"></a><span data-ttu-id="c0423-102">Lync Server 2013의 SQL Server에 대한 배포 권한</span><span class="sxs-lookup"><span data-stu-id="c0423-102">Deployment permissions for SQL Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c0423-103">_**마지막으로 수정한 주제:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="c0423-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="c0423-104">Microsoft SQL Server 2012에는 Lync Server 2013를 설치 및 배포할 때 특정 요구 사항이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0423-104">Microsoft SQL Server 2012 has specific requirements when installing and deploying Lync Server 2013.</span></span> <span data-ttu-id="c0423-105">Windows 및 SQL Server는 보안을 다르게 정의 하기 때문에 Active Directory 도메인의 관리자로 로그인 하면 SQL Server에 대 한 사용 권한을 암시적으로 부여 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c0423-105">Because Windows and SQL Server define their security differently, logging in as an administrator in the Active Directory domain does not implicitly grant permissions for SQL Server.</span></span> <span data-ttu-id="c0423-106">또한 사용자가 구성 하는 SQL Server 기반 서버에서 sysadmin 엔터티의 구성원 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0423-106">You must also be a member of the sysadmin entity on the SQL Server-based server you are configuring.</span></span>

<div>

## <a name="permissions-required-for-database-and-lync-server-installation"></a><span data-ttu-id="c0423-107">데이터베이스 및 Lync Server 설치에 필요한 사용 권한</span><span class="sxs-lookup"><span data-stu-id="c0423-107">Permissions Required for Database and Lync Server Installation</span></span>

<span data-ttu-id="c0423-108">다음 옵션은 Lync Server 2013 파일 및 SQL Server 데이터베이스 설치에 대 한 세 가지 권한 및 그룹 구성원 자격 연결을 자세히 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0423-108">The following options detail three permissions and group membership associations for installation of Lync Server 2013 files and SQL Server databases.</span></span> <span data-ttu-id="c0423-109">조직의 요구 사항에 가장 잘 맞는 시나리오를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0423-109">Choose the scenario that best meets the requirements of your organization.</span></span>

### <a name="permissions-and-group-membership-associations"></a><span data-ttu-id="c0423-110">사용 권한 및 그룹 구성원 자격 연결</span><span class="sxs-lookup"><span data-stu-id="c0423-110">Permissions and Group Membership Associations</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c0423-111">SQL Server 또는 Lync Server 2013 역할</span><span class="sxs-lookup"><span data-stu-id="c0423-111">SQL Server or Lync Server 2013 role</span></span></th>
<th><span data-ttu-id="c0423-112">역할-일반적인 SQL Server 사용 권한 및 그룹 구성원 자격</span><span class="sxs-lookup"><span data-stu-id="c0423-112">Role-Typical SQL Server permissions and group membership</span></span></th>
<th><span data-ttu-id="c0423-113">역할-일반적인 Lync Server 2013 사용 권한 및 그룹 구성원 자격</span><span class="sxs-lookup"><span data-stu-id="c0423-113">Role-typical Lync Server 2013 permissions and group membership</span></span></th>
<th><span data-ttu-id="c0423-114">사용 권한 결과</span><span class="sxs-lookup"><span data-stu-id="c0423-114">Permissions outcome</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c0423-115">Lync Server 2013 관리자</span><span class="sxs-lookup"><span data-stu-id="c0423-115">Lync Server 2013 administrator</span></span></p></td>
<td><p><span data-ttu-id="c0423-116">Sysadmins SQL Server 보안 그룹 및 SQL Server 로컬 관리자 그룹 구성원의 멤버 자격을 부여 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0423-116">Must be granted membership of sysadmins SQL Server security group and member of the SQL Server local Administrators group</span></span></p></td>
<td><p><span data-ttu-id="c0423-117">RTCUniversalServerAdmins 그룹의 구성원 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0423-117">Must be a member of the RTCUniversalServerAdmins group</span></span></p></td>
<td><p><span data-ttu-id="c0423-118">Lync Server 2013 관리자에는 Lync Server 2013 및 SQL Server 데이터베이스를 모두 설치할 수 있는 적절 한 사용 권한이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0423-118">Lync Server 2013 administrator has the proper permissions to install both Lync Server 2013 and SQL Server databases.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c0423-119">SQL Server 관리자</span><span class="sxs-lookup"><span data-stu-id="c0423-119">SQL Server administrator</span></span></p></td>
<td><p><span data-ttu-id="c0423-120">Sql server sysadmin 그룹 구성원 (또는 그와 동등한) 및 SQL Server 로컬 관리자 그룹의 구성원</span><span class="sxs-lookup"><span data-stu-id="c0423-120">SQL Server sysadmin group member (or equivalent) and member of the SQL Server local Administrators group</span></span></p></td>
<td><p><span data-ttu-id="c0423-121">RTCUniversalServerReadOnly 그룹의 구성원 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0423-121">Must be a member of the RTCUniversalServerReadOnly group</span></span></p></td>
<td><p><span data-ttu-id="c0423-122">SQL Server 관리자는 Lync Server 2013 및 SQL Server 데이터베이스를 모두 설치할 수 있는 적절 한 권한이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0423-122">SQL Server administrator has the proper permissions to install both Lync Server 2013 and SQL Server databases.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c0423-123">두 관리자 모두 설치 의무를 공유 하는 경우</span><span class="sxs-lookup"><span data-stu-id="c0423-123">Both administrators sharing installation duties</span></span></p></td>
<td><p><span data-ttu-id="c0423-124">SQL Server 관리자는 sysadmins 그룹 (또는 이와 동등한)의 구성원 및 SQL Server 로컬 관리자 그룹의 구성원입니다.</span><span class="sxs-lookup"><span data-stu-id="c0423-124">SQL Server administrator is member of sysadmins group (or equivalent) and member of the SQL Server local Administrators group</span></span></p></td>
<td><p><span data-ttu-id="c0423-125">Lync Server 2013 관리자가 RTCUniversalServerAdmins의 구성원입니다.</span><span class="sxs-lookup"><span data-stu-id="c0423-125">Lync Server 2013 administrator is member of RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="c0423-126">Lync Server 2013 관리자는 Lync Server 2013을 설치할 수 있지만 데이터베이스를 설치할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c0423-126">The Lync Server 2013 administrator can install Lync Server 2013, but cannot install the databases.</span></span> <span data-ttu-id="c0423-127">SQL Server 관리자는 lync server 2013 관리자가 제공 하는 Lync Server 관리 셸 및 Windows PowerShell cmdlet을 사용 하 여 데이터베이스를 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0423-127">The SQL Server administrator uses the Lync Server Management Shell and Windows PowerShell cmdlets provided by the Lync Server 2013 administrator to install the databases.</span></span> <span data-ttu-id="c0423-128">SQL Server 관리자가 사용 하는 Lync Server 2013 관리 셸이 프런트 엔드 서버에 설치 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0423-128">The Lync Server 2013 Management Shell used by the SQL Server administrator is installed on the Front End Server.</span></span> <span data-ttu-id="c0423-129">이렇게 하면 SQL Server 기반 서버에 Lync Server 2013 관리 도구를 설치할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c0423-129">This eliminates the need to install the Lync Server 2013 administrative tools on the SQL Server-based server.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

