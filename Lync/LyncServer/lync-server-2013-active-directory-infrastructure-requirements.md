---
title: 'Lync Server 2013: Active Directory 인프라 요구 사항'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Active Directory infrastructure requirements
ms:assetid: c2086f7b-662f-4179-ab99-2c0311ebd903
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412955(v=OCS.15)
ms:contentKeyID: 48185318
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: de375bd11a0cf515745b0a64fb4aef7aa32113d9
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145066"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="active-directory-infrastructure-requirements-for-lync-server-2013"></a><span data-ttu-id="97f61-102">Lync Server 2013에 대 한 Active Directory 인프라 요구 사항</span><span class="sxs-lookup"><span data-stu-id="97f61-102">Active Directory infrastructure requirements for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="97f61-103">_**마지막으로 수정 된 항목:** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="97f61-103">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="97f61-104">Lync Server 2013에 대 한 Active Directory 도메인 서비스 준비 프로세스를 시작 하기 전에 Active Directory 인프라가 다음 필수 구성 요소를 충족 하는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="97f61-104">Before you start the process of preparing Active Directory Domain Services for Lync Server 2013, make sure that your Active Directory infrastructure meets the following prerequisites:</span></span>

  - <span data-ttu-id="97f61-105">Lync Server를 배포 하는 포리스트에서 모든 글로벌 카탈로그 서버를 포함 하는 모든 도메인 컨트롤러는 다음 운영 체제 중 하나를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="97f61-105">All domain controllers (which include all global catalog servers) in the forest where you deploy Lync Server run one of the following operating systems:</span></span>
    
      - <span data-ttu-id="97f61-106">Windows Server 2012 R2 운영 체제</span><span class="sxs-lookup"><span data-stu-id="97f61-106">Windows Server 2012 R2 operating system</span></span>
    
      - <span data-ttu-id="97f61-107">Windows Server 2012 운영 체제</span><span class="sxs-lookup"><span data-stu-id="97f61-107">Windows Server 2012 operating system</span></span>
    
      - <span data-ttu-id="97f61-108">Windows Server 2008 R2 운영 체제</span><span class="sxs-lookup"><span data-stu-id="97f61-108">Windows Server 2008 R2 operating system</span></span>
    
      - <span data-ttu-id="97f61-109">Windows Server 2008 운영 체제</span><span class="sxs-lookup"><span data-stu-id="97f61-109">Windows Server 2008 operating system</span></span>
    
      - <span data-ttu-id="97f61-110">Windows Server 2008 Enterprise 32 비트</span><span class="sxs-lookup"><span data-stu-id="97f61-110">Windows Server 2008 Enterprise 32-Bit</span></span>
    
      - <span data-ttu-id="97f61-111">32비트 또는 64비트 버전의 Windows Server 2003 R2 운영 체제</span><span class="sxs-lookup"><span data-stu-id="97f61-111">32-bit or 64-bit versions of the Windows Server 2003 R2 operating system</span></span>
    
      - <span data-ttu-id="97f61-112">32 비트 또는 64 비트 버전의 Windows Server 2003 운영 체제</span><span class="sxs-lookup"><span data-stu-id="97f61-112">32-bit or 64-bit versions of the Windows Server 2003 operating system</span></span>

  - <span data-ttu-id="97f61-113">Lync Server를 배포 하는 모든 도메인은 Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2, Windows Server 2008 또는 Windows Server 2003 이상의 도메인 기능 수준으로 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="97f61-113">All domains in which you deploy Lync Server are raised to a domain functional level of Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2, Windows Server 2008, or at least Windows Server 2003.</span></span>

  - <span data-ttu-id="97f61-114">Lync Server를 배포 하는 포리스트는 Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2, Windows Server 2008 또는 Windows Server 2003 이상에 해당 하는 포리스트 기능 수준으로 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="97f61-114">The forest in which you deploy Lync Server is raised to a forest functional level of Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2, Windows Server 2008, or at least Windows Server 2003.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="97f61-115">도메인 또는 포리스트 기능 수준을 변경 하려면 TechNet 라이브러리에서 "도메인 및 포리스트 기능 수준 올리기"를 참조 하세요 <A href="https://go.microsoft.com/fwlink/p/?linkid=263775">https://go.microsoft.com/fwlink/p/?LinkId=263775</A>.</span><span class="sxs-lookup"><span data-stu-id="97f61-115">To change your domain or forest functional level, see "Raising domain and forest functional levels" in the TechNet Library at <A href="https://go.microsoft.com/fwlink/p/?linkid=263775">https://go.microsoft.com/fwlink/p/?LinkId=263775</A>.</span></span>

    
    </div>

  - <span data-ttu-id="97f61-116">글로벌 카탈로그는 Lync Server 컴퓨터나 사용자를 배포 하는 모든 도메인에 배포 됩니다.</span><span class="sxs-lookup"><span data-stu-id="97f61-116">A global catalog is deployed in every domain where you deploy Lync Server computers or users.</span></span>

<span data-ttu-id="97f61-117">Lync Server 2013는 windows Server 2012 R2, Windows Server 2012, Windows server 2008 R2, Windows Server 2008 및 Windows Server 2003 운영 체제의 유니버설 그룹을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="97f61-117">Lync Server 2013 supports the universal groups in the Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2, Windows Server 2008, and Windows Server 2003 operating systems.</span></span> <span data-ttu-id="97f61-118">유니버설 그룹의 구성원은 도메인 트리 또는 포리스트에 있는 도메인의 다른 그룹 및 계정을 포함할 수 있고 도메인 트리 또는 포리스트에 있는 도메인의 사용 권한이 할당될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97f61-118">Members of universal groups can include other groups and accounts from any domain in the domain tree or forest and can be assigned permissions in any domain in the domain tree or forest.</span></span> <span data-ttu-id="97f61-119">관리자 위임과 함께 유니버설 그룹을 지원 하면 Lync Server 배포를 간편 하 게 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97f61-119">Universal group support, combined with administrator delegation, simplifies the management of a Lync Server deployment.</span></span> <span data-ttu-id="97f61-120">예를 들어 한 도메인을 다른 도메인에 추가하지 않아도 관리자가 둘 다 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97f61-120">For example, it is not necessary to add one domain to another to enable an administrator to manage both.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

