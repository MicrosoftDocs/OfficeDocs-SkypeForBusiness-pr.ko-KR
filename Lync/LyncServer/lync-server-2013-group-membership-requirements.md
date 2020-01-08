---
title: 'Lync Server 2013: 그룹 구성원 자격 요구 사항'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Group membership requirements
ms:assetid: 01876843-8717-4e72-baf5-866ac8cceee6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204623(v=OCS.15)
ms:contentKeyID: 48183239
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6aed308674cc334cfb8f3d4f214ce7388ae89fea
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40985631"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="group-membership-requirements-for-lync-server-2013"></a><span data-ttu-id="55d79-102">Lync Server 2013에 대한 그룹 구성원 자격 요구 사항</span><span class="sxs-lookup"><span data-stu-id="55d79-102">Group membership requirements for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="55d79-103">_**마지막으로 수정한 주제:** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="55d79-103">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="55d79-104">다음 표에는 Lync Server 2013를 성공적으로 설치, 관리 및 문제 해결 하기 위해 사용자가 속해야 하는 그룹이 요약 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="55d79-104">The following table summarizes the group or groups that a person should belong to in order to successfully install, manage, and troubleshoot Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="55d79-105">Lync Server 2013 실행 파일</span><span class="sxs-lookup"><span data-stu-id="55d79-105">Lync Server 2013 Executable</span></span></th>
<th><span data-ttu-id="55d79-106">그룹 등록 필요</span><span class="sxs-lookup"><span data-stu-id="55d79-106">Group Membership Required</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="55d79-107"><strong>Setup.exe – Lync</strong> Server 2013 관리 도구의 설치를 시작 하는 실행 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="55d79-107"><strong>Setup.exe</strong> – Executable that starts the installation of the Lync Server 2013 administrative tools.</span></span></p></td>
<td><p><span data-ttu-id="55d79-108">실행 파일이 실행 되는 컴퓨터의 로컬 관리자 그룹의 구성원입니다.</span><span class="sxs-lookup"><span data-stu-id="55d79-108">Member of the Local Administrators group on the computer from which the executable is run.</span></span> <span data-ttu-id="55d79-109">Active Directory 도메인 서비스의 정보를 읽을 수 있는 Domain Users group의 구성원입니다.</span><span class="sxs-lookup"><span data-stu-id="55d79-109">Member of Domain Users group to read information in Active Directory Domain Services.</span></span> <span data-ttu-id="55d79-110">로컬 컴퓨터에 필요한 MSI 패키지의 자동 설치에는 프로그램 파일 디렉터리와 같은 보호 된 로컬 컴퓨터 리소스에 대 한 읽기 및 쓰기를 허용 하 고 보호 되는 권한이 필요 하기 때문에이 수준의 권한이 필요 합니다. 레지스트리 (예: 로컬 컴퓨터 하이브)</span><span class="sxs-lookup"><span data-stu-id="55d79-110">This level of permission is required because the automatic installation of required MSI packages on the local computer requires privileges that allow reading from and writing to protected local computer resources such as Program Files directories, and protected registry such as the Local Machine hive.</span></span></p>
<div>

> [!TIP]  
> <span data-ttu-id="55d79-111">또한 Domain Admins 그룹에서 구성원 자격을 부여 하지 않으려는 사용자 또는 그룹에 게 설치 권한을 위임할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="55d79-111">You can also delegate setup permissions to users or groups to whom you do not want to grant membership in the Domain Admins group.</span></span> <span data-ttu-id="55d79-112">자세한 내용은 배포 설명서의 <A href="lync-server-2013-granting-setup-permissions.md">Lync Server 2013에서 설정에 대 한 사용 권한 부여</A> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="55d79-112">For details, see <A href="lync-server-2013-granting-setup-permissions.md">Granting setup permissions in Lync Server 2013</A> in the Deployment documentation.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="55d79-113"><strong>Update.exe – setup.exe</strong> 에서 호출 하는 경우 서버 역할에 대 한 소프트웨어 구성 요소 배포를 담당 합니다.</span><span class="sxs-lookup"><span data-stu-id="55d79-113"><strong>Deploy.exe</strong> – Called by setup.exe, deploy.exe is responsible for the deployment of the software components for the server roles.</span></span></p></td>
<td><p><span data-ttu-id="55d79-114">실행 파일이 실행 되는 컴퓨터의 로컬 관리자 그룹의 구성원입니다.</span><span class="sxs-lookup"><span data-stu-id="55d79-114">Member of the Local Administrators group on the computer from which the executable is run.</span></span> <span data-ttu-id="55d79-115">AD DS에서 정보를 읽을 수 있는 Domain Users group의 구성원입니다.</span><span class="sxs-lookup"><span data-stu-id="55d79-115">Member of Domain Users group to read information in AD DS.</span></span> <span data-ttu-id="55d79-116">로컬 컴퓨터에 필요한 MSI 패키지의 자동 설치에는 프로그램 파일 디렉터리와 같은 보호 된 로컬 컴퓨터 리소스에 대 한 읽기 및 쓰기를 허용 하 고 보호 되는 권한이 필요 하기 때문에이 수준의 권한이 필요 합니다. 레지스트리 (예: 로컬 컴퓨터 하이브)</span><span class="sxs-lookup"><span data-stu-id="55d79-116">This level of permission is required because the automatic installation of required MSI packages on the local computer requires privileges that allow reading from and writing to protected local computer resources such as Program Files directories, and protected registry such as the Local Machine hive.</span></span> <span data-ttu-id="55d79-117">중앙 관리 저장소를 읽으려면 RtcUniversalReadOnlyAdmins 그룹의 구성원 자격이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="55d79-117">Membership in RtcUniversalReadOnlyAdmins group is necessary to read the Central Management store.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="55d79-118">Windows Vista 운영 체제 또는 Windows 7 운영 체제를 실행 하는 경우에는 UAC (사용자 계정 컨트롤)가 설치를 진행 하 라는 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="55d79-118">If you are running the Windows Vista operating system or Windows 7 operating system, you will be prompted by User Account Control (UAC) to proceed with installation.</span></span> <span data-ttu-id="55d79-119">표준 사용자 계정으로 로그온 한 경우 소프트웨어를 설치할 수 있는 권한이 있는 계정에 대 한 메시지가 표시 되 면 자격 증명을 제공 하기 위해 로컬 관리자 그룹의 구성원 인 사용자가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="55d79-119">If you are logged on with a standard user account, you will need someone who is a member of the Local Administrators group to provide credentials when prompted for an account with permissions to install the software.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="55d79-120"><strong>Mage.exe – setup.exe</strong> 에서 호출 하는 경우 서버 역할의 배포 및 구성을 담당 합니다.</span><span class="sxs-lookup"><span data-stu-id="55d79-120"><strong>Bootstrapper.exe</strong> – Called by setup.exe, bootstrapper.exe is responsible for deployment and configuration of server roles.</span></span></p></td>
<td><p><span data-ttu-id="55d79-121">실행 파일이 실행 되는 컴퓨터의 로컬 관리자 그룹의 구성원입니다.</span><span class="sxs-lookup"><span data-stu-id="55d79-121">Member of the Local Administrators group on the computer from which the executable is run.</span></span> <span data-ttu-id="55d79-122">RTCUniversalServerAdmins 그룹의 구성원으로 서 부트스트래퍼를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="55d79-122">Member of the RTCUniversalServerAdmins group to run Bootstrapper.exe.</span></span> <span data-ttu-id="55d79-123">AD DS에서 정보를 읽을 수 있는 Domain Users group의 구성원입니다.</span><span class="sxs-lookup"><span data-stu-id="55d79-123">Member of Domain Users group to read information in AD DS.</span></span> <span data-ttu-id="55d79-124">로컬 컴퓨터에 필요한 MSI 패키지의 자동 설치에는 프로그램 파일 디렉터리와 같은 보호 된 로컬 컴퓨터 리소스에 대 한 읽기 및 쓰기를 허용 하 고 보호 되는 권한이 필요 하기 때문에이 수준의 권한이 필요 합니다. 레지스트리 (예: 로컬 컴퓨터 하이브)</span><span class="sxs-lookup"><span data-stu-id="55d79-124">This level of permission is required because the automatic installation of required MSI packages on the local computer requires privileges that allow reading from and writing to protected local computer resources such as Program Files directories, and protected registry such as the Local Machine hive.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="55d79-125"><strong>TopologyBuilder</strong> – 마법사 기반의 사용자 인터페이스를 사용 하 여 Lync Server 2013 토폴로지를 만들고, 보고, 조정 하 고, 유효성을 검사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="55d79-125"><strong>TopologyBuilder</strong> – Wizard-driven user interface to create, view, adjust, and validate Lync Server 2013 topologies.</span></span></p></td>
<td><p><span data-ttu-id="55d79-126">토폴로지를 보기 위해 실행 파일을 실행 하는 컴퓨터의 로컬 관리자 그룹의 구성원입니다.</span><span class="sxs-lookup"><span data-stu-id="55d79-126">Member of the Local Administrators group on the computer from which the executable is run to view the topology.</span></span> <span data-ttu-id="55d79-127">RTCUniversalServerAdmins 그룹의 구성원으로 구성 설정을 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="55d79-127">Member of the RTCUniversalServerAdmins group to change configuration settings.</span></span> <span data-ttu-id="55d79-128">RTCUniversalServerAdmins group 및 Domain Admins 그룹의 구성원 또는 RTCUniversalServerAdmins 그룹의 구성원 (그룹에 대리인 설정 권한이 부여 된 경우에만)을 사용 하 여 토폴로지를 게시 합니다.</span><span class="sxs-lookup"><span data-stu-id="55d79-128">Member of the RTCUniversalServerAdmins group and Domain Admins group, or member of the RTCUniversalServerAdmins group (only if the group has been granted delegate setup permissions), to publish the topology.</span></span> <span data-ttu-id="55d79-129">RTCUniversalServerAdmins 그룹의 구성원이 Domain Admins 그룹의 구성원이 아닌 토폴로지를 게시할 수 있도록 설정 권한을 위임 하는 방법에 대 한 자세한 내용은 배포 설명서의 <a href="lync-server-2013-granting-setup-permissions.md">Lync Server 2013에서 설정에 대 한 사용 권한 부여</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="55d79-129">For details about delegating setup permissions to allow members of the RTCUniversalServerAdmins group to publish the topology without being members of the Domain Admins group, see <a href="lync-server-2013-granting-setup-permissions.md">Granting setup permissions in Lync Server 2013</a> in the Deployment documentation.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="55d79-130"><strong>Adminuihost</strong> – Lync Server 2013을 관리 하기 위한 웹 기반 그래픽 사용자 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="55d79-130"><strong>AdminUIHost</strong> – Web-based graphical user interface for managing Lync Server 2013.</span></span></p></td>
<td><p><span data-ttu-id="55d79-131">특정 관리 작업에 할당 된 다른 RBAC (역할 기반 액세스 제어) 역할의 구성원 또는 CsAdministrator 그룹의 구성원입니다.</span><span class="sxs-lookup"><span data-stu-id="55d79-131">Member of CsAdministrator group or member of another role-based access control (RBAC) role to which the specific administrative task is assigned.</span></span> <span data-ttu-id="55d79-132">Lync Server 2013 제어판은 Lync Server 2013 관리 셸 cmdlet을 실행 하 여 구성 변경을 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="55d79-132">Lync Server 2013 Control Panel implements configuration changes by running Lync Server 2013 Management Shell cmdlets.</span></span> <span data-ttu-id="55d79-133">미리 정의 된 역할 및 cmdlet 구성원을 실행할 수 있도록 허용 된 목록은 계획 문서에서 <a href="lync-server-2013-planning-for-role-based-access-control.md">Lync Server 2013의 역할 기반 액세스 제어 계획</a> 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="55d79-133">For a list of predefined roles and the cmdlets members are permitted to run, see <a href="lync-server-2013-planning-for-role-based-access-control.md">Planning for role-based access control in Lync Server 2013</a> in the Planning documentation.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="55d79-134">Lync <strong>server 2013 모듈이 로드</strong> 된 명령줄 관리 도구를 사용 하 여 lync server 2013의 관리와 관련 된 cmdlet이 있는 PowerShell exe.</span><span class="sxs-lookup"><span data-stu-id="55d79-134"><strong>PowerShell.exe with the Lync Server 2013 module loaded</strong> – Command-line administrative tool with cmdlets specific to management of Lync Server 2013.</span></span></p></td>
<td><p><span data-ttu-id="55d79-135">CsAdministrator 그룹의 구성원 또는 특정 cmdlet이 할당 된 다른 RBAC 역할의 구성원입니다.</span><span class="sxs-lookup"><span data-stu-id="55d79-135">Member of CsAdministrator group or member of another RBAC role to which the specific cmdlet has been assigned.</span></span> <span data-ttu-id="55d79-136">미리 정의 된 역할 및 cmdlet 구성원을 실행할 수 있도록 허용 된 목록은 계획 문서에서 <a href="lync-server-2013-planning-for-role-based-access-control.md">Lync Server 2013의 역할 기반 액세스 제어 계획</a> 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="55d79-136">For a list of predefined roles and the cmdlets members are permitted to run, see <a href="lync-server-2013-planning-for-role-based-access-control.md">Planning for role-based access control in Lync Server 2013</a> in the Planning documentation.</span></span></p>
<p><span data-ttu-id="55d79-137">또는 cmdlet에 따라 다음 그룹 중 하나 이상의 구성원입니다.</span><span class="sxs-lookup"><span data-stu-id="55d79-137">Or, member of one or more of the following groups, depending on the cmdlet:</span></span></p>
<ul>
<li><p><span data-ttu-id="55d79-138">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="55d79-138">RTCUniversalServerAdmins</span></span></p></li>
<li><p><span data-ttu-id="55d79-139">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="55d79-139">RTCUniversalUserAdmins</span></span></p></li>
<li><p><span data-ttu-id="55d79-140">RTCUniversalReadOnlyAdmins</span><span class="sxs-lookup"><span data-stu-id="55d79-140">RTCUniversalReadOnlyAdmins</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

