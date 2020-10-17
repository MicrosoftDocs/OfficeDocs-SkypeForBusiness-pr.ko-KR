---
title: 'Lync Server 2013: 서버 및 응용 프로그램 강화 및 보호'
description: 'Lync Server 2013: 서버 및 응용 프로그램을 강화 하 고 보호 합니다.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Hardening and protecting servers and applications for Lync Server 2013
ms:assetid: 9ca2b233-26f1-4d72-96e7-81a82c727806
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn518331(v=OCS.15)
ms:contentKeyID: 62625491
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ed1205439208dfdadf5396b976d5d4876fb0aa24
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48567444"
---
# <a name="hardening-and-protecting-servers-and-applications-for-lync-server-2013"></a><span data-ttu-id="6eac2-103">Lync Server 2013에 대 한 서버 및 응용 프로그램 강화 및 보호</span><span class="sxs-lookup"><span data-stu-id="6eac2-103">Hardening and protecting servers and applications for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6eac2-104">_**마지막으로 수정 된 항목:** 2013-12-05_</span><span class="sxs-lookup"><span data-stu-id="6eac2-104">_**Topic Last Modified:** 2013-12-05_</span></span>

<span data-ttu-id="6eac2-105">특정 구성 요소에 대 한 모범 사례에 따라 운영 체제 및 응용 프로그램을 강화 하 고 보호 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6eac2-105">You should harden and protect your operating system and applications according to best practices for that specific component.</span></span> <span data-ttu-id="6eac2-106">이 섹션에서는 응용 프로그램 서버를 강화 하 고 그룹 정책을 사용 하 여 보안 잠금을을 구현 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="6eac2-106">This section describes how to harden application servers and use Group Policy to implement security lockdowns.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="6eac2-107">Microsoft Lync Server 2013 배포에 사용 되는 데이터베이스를 강화 하 고 보호할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6eac2-107">You can also harden and protect the databases used for you Microsoft Lync Server 2013 deployment.</span></span> <span data-ttu-id="6eac2-108">자세한 내용은 <A href="lync-server-2013-hardening-and-protecting-databases.md">Lync Server 2013의 데이터베이스 보안 강화 및 보호</A>를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="6eac2-108">For details, see <A href="lync-server-2013-hardening-and-protecting-databases.md">Hardening and protecting the databases of Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="securing-application-servers"></a><span data-ttu-id="6eac2-109">응용 프로그램 서버 보안</span><span class="sxs-lookup"><span data-stu-id="6eac2-109">Securing Application Servers</span></span>

<span data-ttu-id="6eac2-110">응용 프로그램 서버의 경우 운영 체제와 응용 프로그램을 강화 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6eac2-110">For applications servers, the operating system and the application should be hardened.</span></span> <span data-ttu-id="6eac2-111">예를 들어 Microsoft Internet Security and 가속화 (ISA) 서버 2006을 실행 하기 위한 Windows Server 2008 컴퓨터는 운영 체제와 응용 프로그램 측면에서 강화 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6eac2-111">For example, a Windows Server 2008 computer dedicated to running Microsoft Internet Security and Acceleration (ISA) Server 2006 should be hardened from the operating system and from the application perspective.</span></span> <span data-ttu-id="6eac2-112">서버에서 실행 되 고 제공 하는 서비스 수를 최소화 하는 것은 주요 목표입니다.</span><span class="sxs-lookup"><span data-stu-id="6eac2-112">Minimizing the number of services running and provided by the server should be a primary goal.</span></span>

</div>

<div>

## <a name="securing-virtual-servers"></a><span data-ttu-id="6eac2-113">가상 서버 보안</span><span class="sxs-lookup"><span data-stu-id="6eac2-113">Securing Virtual Servers</span></span>

<span data-ttu-id="6eac2-114">가상 서버 스냅숏에는 서버의 데이터 디스크 복사본이 포함 되며 메모리 내 데이터의 덤프도 포함 되며, 둘 다 공격이 발생할 수 있는 중요 한 암호화 데이터를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6eac2-114">Virtual server snapshots contain copies of the server’s data disks and also contain dumps of in-memory data, both of which can contain sensitive cryptographic data that might lead to attacks.</span></span> <span data-ttu-id="6eac2-115">가상화를 사용 하 여 구현 되는 프로덕션 서버의 경우 모든 서버 스냅숏을 사용 하지 않도록 설정 하거나 매우 통제 된 방식으로 관리 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6eac2-115">For production servers implemented using virtualization, you should disable all server snapshots or manage them in a very controlled manner.</span></span> <span data-ttu-id="6eac2-116">Hyper-v 가상 서버를 보호 하는 방법에 대 한 자세한 내용은:의 Hyper-v 보안 가이드를 참조 하세요 [https://go.microsoft.com/fwlink/p/?LinkId=214176](https://go.microsoft.com/fwlink/p/?linkid=214176) .</span><span class="sxs-lookup"><span data-stu-id="6eac2-116">For details about securing Hyper-V virtual servers, see the Hyper-V Security Guide at: [https://go.microsoft.com/fwlink/p/?LinkId=214176](https://go.microsoft.com/fwlink/p/?linkid=214176).</span></span>

</div>

<div>

## <a name="group-policy"></a><span data-ttu-id="6eac2-117">그룹 정책</span><span class="sxs-lookup"><span data-stu-id="6eac2-117">Group Policy</span></span>

<span data-ttu-id="6eac2-118">Windows Server 2008 및 Windows Server 2008 R2에서 그룹 정책은 디렉터리 기반 데스크톱 구성 관리를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="6eac2-118">In Windows Server 2008 and Windows Server 2008 R2, Group Policy provides directory-based desktop configuration management.</span></span> <span data-ttu-id="6eac2-119">그룹 정책을 사용 하 여 다음에 대 한 GPO (그룹 정책 개체) 내에서 컴퓨터 및 사용자 설정을 정의 하 여 보안 잠금을를 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6eac2-119">You can use Group Policy to implement security lockdowns by defining Computer and User settings within a Group Policy object (GPO) for the following:</span></span>

  - <span data-ttu-id="6eac2-120">레지스트리 기반 정책</span><span class="sxs-lookup"><span data-stu-id="6eac2-120">Registry-based policies</span></span>

  - <span data-ttu-id="6eac2-121">보안</span><span class="sxs-lookup"><span data-stu-id="6eac2-121">Security</span></span>

  - <span data-ttu-id="6eac2-122">소프트웨어 설치</span><span class="sxs-lookup"><span data-stu-id="6eac2-122">Software installation</span></span>

  - <span data-ttu-id="6eac2-123">스크립트</span><span class="sxs-lookup"><span data-stu-id="6eac2-123">Scripts</span></span>

  - <span data-ttu-id="6eac2-124">폴더 리디렉션</span><span class="sxs-lookup"><span data-stu-id="6eac2-124">Folder redirection</span></span>

  - <span data-ttu-id="6eac2-125">원격 설치 서비스</span><span class="sxs-lookup"><span data-stu-id="6eac2-125">Remote installation services</span></span>

<span data-ttu-id="6eac2-126">관리자가 이러한 설정을 구성 하는 데 사용할 수 있는 사용자 인터페이스를 제공 하기 위해 관리 템플릿은 운영 체제 릴리스, 서비스 팩 릴리스 및 일부 응용 프로그램 (Lync Server 2013 포함)과 함께 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6eac2-126">To provide a user interface for the administrator to configure these settings, administrative templates are shipped with operating system releases, service pack releases, and some applications, including Lync Server 2013.</span></span>

<span data-ttu-id="6eac2-127">Communicator .adm 파일은 Lync Server 2013와 함께 제공 되는 관리 템플릿으로,% windir% inf 디렉터리에 설치 되어 \\ \\ 있으며, 그룹 정책 설정에 대 한 인터페이스를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="6eac2-127">The Communicator.adm file is an administrative template that ships with Lync Server 2013, is installed to the %windir%\\inf\\ directory, and provides an interface to the Group Policy settings.</span></span> <span data-ttu-id="6eac2-128">Communicator의 각 설정은 응용 프로그램 동작에 영향을 주는 레지스트리 설정에 해당 합니다.</span><span class="sxs-lookup"><span data-stu-id="6eac2-128">Each setting in Communicator.adm corresponds to a setting in the registry that affects application behavior.</span></span>

<span data-ttu-id="6eac2-129">이 설정은 Active Directory 사용자 및 컴퓨터 콘솔과 GPMC (그룹 정책 관리 콘솔)에서 사용할 수 있는 GPedit.dll에서 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6eac2-129">The settings can be accessed from GPedit.dll, which is available from the Active Directory Users and Computers console and the Group Policy Management Console (GPMC).</span></span>

</div>

<div>

## <a name="group-policy-security-settings"></a><span data-ttu-id="6eac2-130">그룹 정책 보안 설정</span><span class="sxs-lookup"><span data-stu-id="6eac2-130">Group Policy Security Settings</span></span>

<span data-ttu-id="6eac2-131">그룹 정책 GPedit.dll에서 액세스 한 컴퓨터 구성/Windows 설정/보안 설정 아래에 GPO에 대 한 보안 설정이 들어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6eac2-131">Group Policy contains security settings for a GPO under Computer Configuration/Windows Settings/Security Settings when accessed from GPedit.dll.</span></span> <span data-ttu-id="6eac2-132">보안 템플릿을 가져와서 GPO에 대 한 보안 설정을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6eac2-132">You can import security templates to configure security settings for the GPO.</span></span> <span data-ttu-id="6eac2-133">의 Windows Server 2008 보안 가이드 [https://go.microsoft.com/fwlink/p/?LinkId=145186](https://go.microsoft.com/fwlink/p/?linkid=145186) 및 Windows server 2008 R2 보안 준수 관리 도구 키트에는 [https://go.microsoft.com/fwlink/p/?LinkId=211882](https://go.microsoft.com/fwlink/p/?linkid=211882) 사용자의 요구를 충족 하기 위해 수정할 수 있는 다양 한 샘플 서식 파일이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6eac2-133">The Windows Server 2008 Security Guide at [https://go.microsoft.com/fwlink/p/?LinkId=145186](https://go.microsoft.com/fwlink/p/?linkid=145186) and the Windows Server 2008 R2 Security Compliance Management Toolkit at [https://go.microsoft.com/fwlink/p/?LinkId=211882](https://go.microsoft.com/fwlink/p/?linkid=211882) contain a number of sample templates that you can modify to meet your needs.</span></span>

</div>

<div>

## <a name="best-practices"></a><span data-ttu-id="6eac2-134">모범 사례</span><span class="sxs-lookup"><span data-stu-id="6eac2-134">Best Practices</span></span>

  - <span data-ttu-id="6eac2-135">모든 서버 운영 체제 및 응용 프로그램을 강화 합니다.</span><span class="sxs-lookup"><span data-stu-id="6eac2-135">Harden all server operating systems and applications.</span></span>

  - <span data-ttu-id="6eac2-136">서버 스냅숏을 보호 하 고 모든 가상 서버의 보안을 향상 시킵니다.</span><span class="sxs-lookup"><span data-stu-id="6eac2-136">Protect server snapshots and enhance the security of all virtual servers.</span></span>

  - <span data-ttu-id="6eac2-137">그룹 정책을 사용 하 여 보안 잠금을을 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="6eac2-137">Use Group Policy to implement security lockdowns.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

