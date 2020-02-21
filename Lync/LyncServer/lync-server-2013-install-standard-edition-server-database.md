---
title: 'Lync Server 2013: Standard Edition Server 데이터베이스 설치'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Install Standard Edition server database
ms:assetid: 0bd3a804-aad6-48cb-981b-54725af032db
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398167(v=OCS.15)
ms:contentKeyID: 48183385
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 877a9b8519c6c0e8b0c3e4a92d190f5a55d8861e
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42197121"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="install-standard-edition-server-database-for-lync-server-2013"></a><span data-ttu-id="7e894-102">Lync Server 2013에 대 한 Standard Edition server 데이터베이스 설치</span><span class="sxs-lookup"><span data-stu-id="7e894-102">Install Standard Edition server database for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7e894-103">_**마지막으로 수정 된 항목:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="7e894-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="7e894-104">Standard Edition 서버를 인프라의 유일한 서버로 설정 하는 것은 **배포 마법사** 에서 초기 서버를 설정 하는 것이 기본적으로 선택 되어 있으므로 사용자를 가정 하는 다른 서버 설치와는 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="7e894-104">Setting up a Standard Edition server as the only server in your infrastructure that homes users differs from other server installations in that there is a selection in the **Deployment Wizard** specifically for setting up the initial server.</span></span>

<div>

## <a name="to-install-a-standard-edition-server"></a><span data-ttu-id="7e894-105">Standard Edition 서버를 설치하려면</span><span class="sxs-lookup"><span data-stu-id="7e894-105">To install a Standard Edition server</span></span>

1.  <span data-ttu-id="7e894-106">Standard Edition server를 설치할 서버에 로컬 관리자 또는 동등한 도메인으로 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e894-106">Log on to the server where you are going to install Standard Edition server as a local administrator or a domain equivalent.</span></span>

2.  <span data-ttu-id="7e894-107">Active Directory 도메인 서비스를 준비 하지 않은 경우 먼저 해당 절차를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e894-107">If you have not prepared Active Directory Domain Services, then first perform those procedures.</span></span> <span data-ttu-id="7e894-108">자세한 내용은 [Lync Server 2013에 대 한 Active Directory 도메인 서비스 준비](lync-server-2013-preparing-active-directory-domain-services.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="7e894-108">For details, see [Preparing Active Directory Domain Services for Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md).</span></span>

3.  <span data-ttu-id="7e894-109">Lync Server 배포 마법사에서 **첫 번째 Standard Edition Server 준비**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e894-109">In the Lync Server Deployment Wizard, click **Prepare first Standard Edition server**.</span></span>

4.  <span data-ttu-id="7e894-110">**단일 Standard Edition Server 준비** 페이지에서 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="7e894-110">On the **Prepare single Standard Edition Server** page, click **Next**.</span></span>

5.  <span data-ttu-id="7e894-111">**명령 실행** 페이지에서 SQL Server 2012 Express는 중앙 관리 저장소로 설치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7e894-111">On the **Executing Commands** page, the SQL Server 2012 Express is installed as the Central Management store.</span></span> <span data-ttu-id="7e894-112">또한 필요한 방화벽 규칙이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="7e894-112">Necessary firewall rules are created.</span></span> <span data-ttu-id="7e894-113">데이터베이스 및 필수 구성 요소 소프트웨어 설치가 완료되면 **마침**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="7e894-113">When the installation of the database and prerequisite software is completed, click **Finish**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="7e894-114">초기 설치는 시간이 오래 걸릴 수 있으며 명령 출력 요약 화면에 업데이트가 표시되지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7e894-114">The initial installation may take some time with no visible updates to the command output summary screen.</span></span> <span data-ttu-id="7e894-115">SQL Server Express가 설치 되었기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="7e894-115">This is due to the installation of the SQL Server Express.</span></span> <span data-ttu-id="7e894-116">데이터베이스 설치를 모니터링해야 하는 경우 작업 관리자를 사용하여 설치를 모니터링합니다.</span><span class="sxs-lookup"><span data-stu-id="7e894-116">If you need to monitor the installation of the database, use Task Manager to monitor the setup.</span></span>

    
    </div>

6.  <span data-ttu-id="7e894-117">Lync Server 배포 마법사 페이지에서 이전에 관리 도구를 설치 하지 않은 경우 **토폴로지 작성기 설치** 를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e894-117">On the Lync Server Deployment Wizard page, click **Install Topology Builder** if you have not previously installed the administrative tools.</span></span> <span data-ttu-id="7e894-118">자세한 내용은 [Install Lync Server 2013 관리 도구](lync-server-2013-install-lync-server-administrative-tools.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="7e894-118">For details, see [Install Lync Server 2013 administrative tools](lync-server-2013-install-lync-server-administrative-tools.md).</span></span>

7.  <span data-ttu-id="7e894-119">"Active Directory 준비", "첫 번째 Standard Edition 서버 준비" 및 "토폴로지 작성기 설치" 옆에 녹색 확인 표시가 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="7e894-119">Confirm that there are green check marks next to “Prepare Active Directory,” “Prepare first Standard Edition server,” and “Install Topology Builder.”</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

