---
title: 'Lync Server 2013: Enterprise Edition 구성원 서버 복원'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Restoring an Enterprise Edition member server
ms:assetid: d960b19c-2104-4719-b736-0d940f254d42
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202191(v=OCS.15)
ms:contentKeyID: 51541523
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 83f0283dc6525dbb75ce74809bd88f4e962a9aec
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40983137"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="restoring-an-enterprise-edition-member-server-in-lync-server-2013"></a><span data-ttu-id="eb07e-102">Lync Server 2013에서 Enterprise Edition 구성원 서버 복원</span><span class="sxs-lookup"><span data-stu-id="eb07e-102">Restoring an Enterprise Edition member server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="eb07e-103">_**마지막으로 수정한 주제:** 2013-02-18_</span><span class="sxs-lookup"><span data-stu-id="eb07e-103">_**Topic Last Modified:** 2013-02-18_</span></span>

<span data-ttu-id="eb07e-104">다음 서버 역할 중 하나를 실행 하는 서버가 실패 하는 경우이 항목의 절차에 따라 서버를 복원 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb07e-104">If a server running one of the following server roles fails, follow the procedure in this topic to restore the server.</span></span> <span data-ttu-id="eb07e-105">여러 서버가 독립적으로 작동 하지 않는 경우 각 서버에 대 한 절차를 따르세요.</span><span class="sxs-lookup"><span data-stu-id="eb07e-105">If multiple servers fail independently, follow the procedure for each server.</span></span>

  - <span data-ttu-id="eb07e-106">프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="eb07e-106">Front End Server</span></span>

  - <span data-ttu-id="eb07e-107">중재 서버</span><span class="sxs-lookup"><span data-stu-id="eb07e-107">Mediation Server</span></span>

  - <span data-ttu-id="eb07e-108">Director</span><span class="sxs-lookup"><span data-stu-id="eb07e-108">Director</span></span>

  - <span data-ttu-id="eb07e-109">영구적 채팅 서버</span><span class="sxs-lookup"><span data-stu-id="eb07e-109">Persistent Chat Server</span></span>

  - <span data-ttu-id="eb07e-110">Edge 서버</span><span class="sxs-lookup"><span data-stu-id="eb07e-110">Edge Server</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="eb07e-111">복원을 시작 하기 전에 시스템의 이미지 복사본을 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="eb07e-111">We recommend that you take an image copy of the system before you start restoration.</span></span> <span data-ttu-id="eb07e-112">복원 중에 문제가 발생 하는 경우이 이미지를 롤백 시점으로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eb07e-112">You can use this image as a rollback point, in case something goes wrong during restoration.</span></span> <span data-ttu-id="eb07e-113">운영 체제 및 SQL Server를 설치 하 고 인증서를 복원 하거나 reenroll 이미지 복사본을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eb07e-113">You might want to take the image copy after you install the operating system and SQL Server, and restore or reenroll the certificates.</span></span>



</div>

<div>

## <a name="to-restore-a-member-server"></a><span data-ttu-id="eb07e-114">구성원 서버를 복원 하려면</span><span class="sxs-lookup"><span data-stu-id="eb07e-114">To restore a member server</span></span>

1.  <span data-ttu-id="eb07e-115">실패 한 서버와 FQDN (정규화 된 도메인 이름)이 동일한 깨끗 한 새 서버를 사용 하 여 시작 하 고, 운영 체제를 설치한 다음, 인증서를 복원 하거나 reenroll.</span><span class="sxs-lookup"><span data-stu-id="eb07e-115">Start with a clean or new server that has the same fully qualified domain name (FQDN) as the failed server, install the operating system, and then restore or reenroll the certificates.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="eb07e-116">조직의 서버 배포 절차에 따라이 단계를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb07e-116">Follow your organization's server deployment procedures to perform this step.</span></span>

    
    </div>

2.  <span data-ttu-id="eb07e-117">RTCUniversalServerAdmins 그룹의 구성원 인 사용자 계정에서 복원 하려는 서버에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb07e-117">From a user account that is a member of the RTCUniversalServerAdmins group, log on to the server that you are restoring.</span></span>

3.  <span data-ttu-id="eb07e-118">Lync Server 설치 폴더 또는 미디어를 찾아 설치 \\\\Amd64\\Setup.exe에 있는 lync server 배포 마법사를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb07e-118">Browse to the Lync Server installation folder or media, and start the Lync Server Deployment Wizard located at \\setup\\amd64\\Setup.exe.</span></span>

4.  <span data-ttu-id="eb07e-119">배포 마법사의 지시에 따라 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb07e-119">Follow the Deployment Wizard to do the following:</span></span>
    
    1.  <span data-ttu-id="eb07e-120">**1 단계: 로컬 구성 저장소 설치** 를 실행 하 여 로컬 구성 파일을 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb07e-120">Run **Step 1: Install Local Configuration Store** to install the local configuration files.</span></span>
    
    2.  <span data-ttu-id="eb07e-121">**2 단계: lync Server 구성 요소 설치 또는 제거** 를 실행 하 여 lync server 서버 역할을 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb07e-121">Run **Step 2: Setup or Remove Lync Server Components** to install the Lync Server server role.</span></span>
    
    3.  <span data-ttu-id="eb07e-122">**3 단계: 인증서 요청, 설치 또는 할당** 을 실행 하 여 인증서를 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb07e-122">Run **Step 3: Request, Install or Assign Certificates** to assign the certificates.</span></span>
    
    4.  <span data-ttu-id="eb07e-123">서버에서 서비스를 시작 하려면 **4 단계: 서비스 시작** 을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb07e-123">Run **Step 4: Start Services** to start services on the server.</span></span>
    
    <span data-ttu-id="eb07e-124">배포 마법사를 실행 하는 방법에 대 한 자세한 내용은 복원할 서버 역할에 대 한 배포 설명서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="eb07e-124">For details about running the Deployment Wizard, see the Deployment documentation for the server role that you are restoring.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

