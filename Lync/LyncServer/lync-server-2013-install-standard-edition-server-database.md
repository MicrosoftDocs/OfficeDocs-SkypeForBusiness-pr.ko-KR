---
title: 'Lync Server 2013: Standard Edition 서버 데이터베이스 설치'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Install Standard Edition server database
ms:assetid: 0bd3a804-aad6-48cb-981b-54725af032db
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398167(v=OCS.15)
ms:contentKeyID: 48183385
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5cad6f67dbf1bfff1ee16dbd7455b02d904aac0d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979112"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="install-standard-edition-server-database-for-lync-server-2013"></a><span data-ttu-id="a26d9-102">Lync Server 2013에 대한 Standard Edition 서버 데이터베이스 설치</span><span class="sxs-lookup"><span data-stu-id="a26d9-102">Install Standard Edition server database for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a26d9-103">_**마지막으로 수정한 주제:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="a26d9-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="a26d9-104">표준 버전 서버를 인프라의 유일한 서버로 설정 하는 것은 **배포 마법사** 에서 초기 서버 설정에 대 한 선택이 있기 때문에 사용자가 다른 서버 설치와 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="a26d9-104">Setting up a Standard Edition server as the only server in your infrastructure that homes users differs from other server installations in that there is a selection in the **Deployment Wizard** specifically for setting up the initial server.</span></span>

<div>

## <a name="to-install-a-standard-edition-server"></a><span data-ttu-id="a26d9-105">스탠더드 버전 서버를 설치 하려면</span><span class="sxs-lookup"><span data-stu-id="a26d9-105">To install a Standard Edition server</span></span>

1.  <span data-ttu-id="a26d9-106">Standard Edition server를 로컬 관리자 또는 동등한 도메인으로 설치할 서버에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="a26d9-106">Log on to the server where you are going to install Standard Edition server as a local administrator or a domain equivalent.</span></span>

2.  <span data-ttu-id="a26d9-107">Active Directory 도메인 서비스를 준비 하지 않은 경우 먼저 해당 절차를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="a26d9-107">If you have not prepared Active Directory Domain Services, then first perform those procedures.</span></span> <span data-ttu-id="a26d9-108">자세한 내용은 [Lync Server 2013에 대 한 Active Directory 도메인 서비스 준비](lync-server-2013-preparing-active-directory-domain-services.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a26d9-108">For details, see [Preparing Active Directory Domain Services for Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md).</span></span>

3.  <span data-ttu-id="a26d9-109">Lync Server 배포 마법사에서 **첫 번째 Standard Edition Server 준비**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a26d9-109">In the Lync Server Deployment Wizard, click **Prepare first Standard Edition server**.</span></span>

4.  <span data-ttu-id="a26d9-110">**단일 Standard Edition Server 준비** 페이지에서 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a26d9-110">On the **Prepare single Standard Edition Server** page, click **Next**.</span></span>

5.  <span data-ttu-id="a26d9-111">**명령 실행** 페이지에서 SQL Server 2012 Express가 중앙 관리 저장소로 설치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a26d9-111">On the **Executing Commands** page, the SQL Server 2012 Express is installed as the Central Management store.</span></span> <span data-ttu-id="a26d9-112">필요한 방화벽 규칙이 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a26d9-112">Necessary firewall rules are created.</span></span> <span data-ttu-id="a26d9-113">데이터베이스 설치 및 필수 소프트웨어 소프트웨어가 완료 되 면 **마침을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a26d9-113">When the installation of the database and prerequisite software is completed, click **Finish**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a26d9-114">초기 설치에는 명령 출력 요약 화면에 표시 되는 업데이트 없이 시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a26d9-114">The initial installation may take some time with no visible updates to the command output summary screen.</span></span> <span data-ttu-id="a26d9-115">이는 SQL Server Express의 설치 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="a26d9-115">This is due to the installation of the SQL Server Express.</span></span> <span data-ttu-id="a26d9-116">데이터베이스 설치를 모니터링 해야 하는 경우 작업 관리자를 사용 하 여 설정을 모니터링 합니다.</span><span class="sxs-lookup"><span data-stu-id="a26d9-116">If you need to monitor the installation of the database, use Task Manager to monitor the setup.</span></span>

    
    </div>

6.  <span data-ttu-id="a26d9-117">Lync Server 배포 마법사 페이지에서 이전에 관리 도구를 설치 하지 않은 경우 **토폴로지 작성기 설치** 를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a26d9-117">On the Lync Server Deployment Wizard page, click **Install Topology Builder** if you have not previously installed the administrative tools.</span></span> <span data-ttu-id="a26d9-118">자세한 내용은 [Lync Server 2013 관리 도구 설치](lync-server-2013-install-lync-server-administrative-tools.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a26d9-118">For details, see [Install Lync Server 2013 administrative tools](lync-server-2013-install-lync-server-administrative-tools.md).</span></span>

7.  <span data-ttu-id="a26d9-119">"Active Directory 준비", "첫 번째 Standard Edition server 준비" 및 "토폴로지 작성기 설치" 옆에 녹색 확인 표시가 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="a26d9-119">Confirm that there are green check marks next to “Prepare Active Directory,” “Prepare first Standard Edition server,” and “Install Topology Builder.”</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

