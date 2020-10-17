---
title: 'Lync Server 2013: Enterprise Edition 구성원 서버 복원'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Restoring an Enterprise Edition member server
ms:assetid: d960b19c-2104-4719-b736-0d940f254d42
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202191(v=OCS.15)
ms:contentKeyID: 51541523
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b958b10fc8c801d680cf17cac8fb493eae82df8d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48511451"
---
# <a name="restoring-an-enterprise-edition-member-server-in-lync-server-2013"></a><span data-ttu-id="2826b-102">Lync Server 2013에서 Enterprise Edition 구성원 서버 복원</span><span class="sxs-lookup"><span data-stu-id="2826b-102">Restoring an Enterprise Edition member server in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2826b-103">_**마지막으로 수정 된 항목:** 2013-02-18_</span><span class="sxs-lookup"><span data-stu-id="2826b-103">_**Topic Last Modified:** 2013-02-18_</span></span>

<span data-ttu-id="2826b-104">다음 서버 역할 중 하나를 실행 하는 서버가 실패 하면이 항목의 절차에 따라 서버를 복원 합니다.</span><span class="sxs-lookup"><span data-stu-id="2826b-104">If a server running one of the following server roles fails, follow the procedure in this topic to restore the server.</span></span> <span data-ttu-id="2826b-105">여러 서버가 개별적으로 실패하면 각 서버에 대해 절차를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="2826b-105">If multiple servers fail independently, follow the procedure for each server.</span></span>

  - <span data-ttu-id="2826b-106">Front End Server(프런트 엔드 서버)</span><span class="sxs-lookup"><span data-stu-id="2826b-106">Front End Server</span></span>

  - <span data-ttu-id="2826b-107">중재 서버</span><span class="sxs-lookup"><span data-stu-id="2826b-107">Mediation Server</span></span>

  - <span data-ttu-id="2826b-108">Director</span><span class="sxs-lookup"><span data-stu-id="2826b-108">Director</span></span>

  - <span data-ttu-id="2826b-109">영구적 채팅 서버</span><span class="sxs-lookup"><span data-stu-id="2826b-109">Persistent Chat Server</span></span>

  - <span data-ttu-id="2826b-110">에지 서버</span><span class="sxs-lookup"><span data-stu-id="2826b-110">Edge Server</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="2826b-111">복원을 시작 하기 전에 시스템의 이미지 복사본을 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="2826b-111">We recommend that you take an image copy of the system before you start restoration.</span></span> <span data-ttu-id="2826b-112">복원 중에 문제가 발생 하는 경우를 대비 하 여이 이미지를 롤백 지점으로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2826b-112">You can use this image as a rollback point, in case something goes wrong during restoration.</span></span> <span data-ttu-id="2826b-113">운영 체제 및 SQL Server를 설치 하 고 인증서를 복원 하거나 reenroll 후 이미지 복사본을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2826b-113">You might want to take the image copy after you install the operating system and SQL Server, and restore or reenroll the certificates.</span></span>



</div>

<div>

## <a name="to-restore-a-member-server"></a><span data-ttu-id="2826b-114">구성원 서버를 복원하려면</span><span class="sxs-lookup"><span data-stu-id="2826b-114">To restore a member server</span></span>

1.  <span data-ttu-id="2826b-115">오류가 발생 한 서버와 FQDN (정규화 된 도메인 이름)이 동일한 깨끗 한 서버 또는 새 서버로 시작 하 고, 운영 체제를 설치한 후 인증서를 복원 하거나 reenroll 합니다.</span><span class="sxs-lookup"><span data-stu-id="2826b-115">Start with a clean or new server that has the same fully qualified domain name (FQDN) as the failed server, install the operating system, and then restore or reenroll the certificates.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="2826b-116">조직의 서버 배포 절차에 따라 이 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="2826b-116">Follow your organization's server deployment procedures to perform this step.</span></span>

    
    </div>

2.  <span data-ttu-id="2826b-117">RTCUniversalServerAdmins 그룹의 구성원 인 사용자 계정에서 복원 중인 서버에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="2826b-117">From a user account that is a member of the RTCUniversalServerAdmins group, log on to the server that you are restoring.</span></span>

3.  <span data-ttu-id="2826b-118">Lync Server 설치 폴더 또는 미디어로 이동 하 여 \\ setup amd64Setup.exe에 있는 Lync Server 배포 마법사를 시작 합니다 \\ \\ .</span><span class="sxs-lookup"><span data-stu-id="2826b-118">Browse to the Lync Server installation folder or media, and start the Lync Server Deployment Wizard located at \\setup\\amd64\\Setup.exe.</span></span>

4.  <span data-ttu-id="2826b-119">배포 마법사에 따라 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="2826b-119">Follow the Deployment Wizard to do the following:</span></span>
    
    1.  <span data-ttu-id="2826b-120">**1단계: 로컬 구성 저장소 설치**를 실행하여 로컬 구성 파일을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="2826b-120">Run **Step 1: Install Local Configuration Store** to install the local configuration files.</span></span>
    
    2.  <span data-ttu-id="2826b-121">**2 단계: lync Server 구성 요소 설치 또는 제거** 를 실행 하 여 lync server 서버 역할을 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="2826b-121">Run **Step 2: Setup or Remove Lync Server Components** to install the Lync Server server role.</span></span>
    
    3.  <span data-ttu-id="2826b-122">**3단계: 인증서 요청, 설치 또는 지정**을 실행하여 인증서를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="2826b-122">Run **Step 3: Request, Install or Assign Certificates** to assign the certificates.</span></span>
    
    4.  <span data-ttu-id="2826b-123">**4단계: 서비스 시작**을 실행하여 서버에서 서비스를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="2826b-123">Run **Step 4: Start Services** to start services on the server.</span></span>
    
    <span data-ttu-id="2826b-124">배포 마법사를 실행 하는 방법에 대 한 자세한 내용은 복원 중인 서버 역할에 대 한 배포 설명서를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="2826b-124">For details about running the Deployment Wizard, see the Deployment documentation for the server role that you are restoring.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

