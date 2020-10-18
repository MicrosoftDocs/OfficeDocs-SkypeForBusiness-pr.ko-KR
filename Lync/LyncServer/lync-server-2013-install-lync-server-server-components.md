---
title: 'Lync Server 2013: Lync Server 서버 구성 요소 설치'
description: 'Lync Server 2013: Lync Server 서버 구성 요소를 설치 합니다.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Install Lync Server server components
ms:assetid: 186aed6e-7adf-4a92-9f2e-f9a4de5ff202
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398239(v=OCS.15)
ms:contentKeyID: 48183528
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1930926f3a46be868d838abf646eb8702c9713a8
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48574124"
---
# <a name="install-server-components-for-lync-server-2013"></a><span data-ttu-id="78599-103">Lync Server 2013 용 서버 구성 요소 설치</span><span class="sxs-lookup"><span data-stu-id="78599-103">Install server components for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="78599-104">_**마지막으로 수정 된 항목:** 2014-05-05_</span><span class="sxs-lookup"><span data-stu-id="78599-104">_**Topic Last Modified:** 2014-05-05_</span></span>

<span data-ttu-id="78599-105">이 단계를 수행 하기 전에 로컬 관리자이 고 Active Directory의 RTCUniversalReadOnlyAdmins 그룹 구성원 인 도메인 사용자 계정을 사용 하 여 서버에 로그온 했는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="78599-105">Before following these steps, make sure you’re logged onto the server with a domain user account that’s both a local administrator and a member of the RTCUniversalReadOnlyAdmins group in Active Directory.</span></span>

<span data-ttu-id="78599-106">Lync Server 배포 마법사는 각 Lync server 역할에 필요한 구성 요소를 설치 하 고 서버를 활성화 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="78599-106">The Lync Server Deployment Wizard is used to install the needed components for each Lync server role and to activate the server.</span></span> <span data-ttu-id="78599-107">이 문서에서는 Lync 인프라에서 Standard Edition server 또는 프런트 엔드 서버를 배포 하는 단계를 안내 합니다.</span><span class="sxs-lookup"><span data-stu-id="78599-107">This article walks you through the steps of deploying a Standard Edition server or a Front End Server in your Lync infrastructure.</span></span>

<div>

## <a name="to-install-lync-server-components"></a><span data-ttu-id="78599-108">Lync Server 구성 요소를 설치하려면</span><span class="sxs-lookup"><span data-stu-id="78599-108">To install Lync Server components</span></span>

1.  <span data-ttu-id="78599-109">Lync Server 배포 마법사가 실행 되 고 있지 않으면 Lync를 설치할 서버에서 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="78599-109">If the Lync Server Deployment Wizard isn’t running, start it on the server you want to install Lync onto.</span></span>

2.  <span data-ttu-id="78599-110">**Lync Server 시스템 설치 또는 업데이트**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="78599-110">Click **Install or Update Lync Server System**.</span></span>

3.  <span data-ttu-id="78599-111">배포 마법사에서 **1 단계: 설치 로컬 구성 저장소** 에 녹색 확인 표시가 있는지 확인 합니다 (이 서버에는 저장소의 로컬 복사본이 성공적으로 설치 되어 있음).</span><span class="sxs-lookup"><span data-stu-id="78599-111">In the Deployment Wizard, confirm that **Step 1: Install Local Configuration Store** has a green check mark, which means that this server has a local copy of the store installed successfully.</span></span> <span data-ttu-id="78599-112">선택 하지 않은 경우 서버에 로컬 구성 저장소를 설치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="78599-112">If it’s not checked, you need to install the Local Configuration store on the server.</span></span> <span data-ttu-id="78599-113">[Lync Server 2013의 로컬 구성 저장소 설치](lync-server-2013-install-the-local-configuration-store.md) 의 단계를 수행 하 고 여기에 다시 방문 합니다.</span><span class="sxs-lookup"><span data-stu-id="78599-113">Follow the steps at [Install the Local Configuration store in Lync Server 2013](lync-server-2013-install-the-local-configuration-store.md) and then come back here.</span></span>

4.  <span data-ttu-id="78599-114">서버에 Lync Server 2013 구성 요소를 설치할 준비가 되 면 **2 단계: Lync Server 구성 요소 설치 또는 제거**옆에 있는 **실행** 을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="78599-114">When you’re ready to install the Lync Server 2013 components on your server, click **Run** next to **Step 2: Setup or Remove Lync Server Components**.</span></span>

5.  <span data-ttu-id="78599-115">**Lync Server 구성 요소 설정** 페이지에서 **다음** 을 클릭 하 여 게시 된 토폴로지에 정의 되어 있는 대로 구성 요소를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="78599-115">On the **Set Up Lync Server Components** page, click **Next** to set up components as defined in your published topology.</span></span>

6.  <span data-ttu-id="78599-116">**명령 실행** 페이지에는 설정 된 대로 명령 및 설치 정보에 대 한 요약이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="78599-116">The **Executing Commands** page will display a summary of commands and installation information as the set up takes place.</span></span> <span data-ttu-id="78599-117">작업이 완료 되 면 목록을 사용 하 여 보려는 로그를 선택한 다음 **로그 보기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="78599-117">When it’s done, you can use the list to select a log to view, and then click **View Log**.</span></span>

7.  <span data-ttu-id="78599-118">Lync Server 2013 구성 요소 설치가 완료 되 고 필요에 따라 로그를 검토 한 경우 **마침을** 클릭 하 여 설치에서이 단계를 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="78599-118">When Lync Server 2013 components setup is done, and you’ve reviewed the logs as needed, click **Finish** to complete this step in the installation.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="78599-119">서버를 다시 시작 하 라는 메시지가 표시 되는 경우 (Windows 데스크톱 환경을 설치 해야 하는 경우에 발생할 수 있음) 명확 하 게이 작업을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="78599-119">If you’re prompted to restart the server (which might happen if Windows Desktop Experience needed to be installed), definitely do that.</span></span> <span data-ttu-id="78599-120">컴퓨터를 백업 하 고 실행 하는 경우 위에 나열 된 3 단계부터 시작 하 여 이러한 단계를 다시 수행 해야 합니다 (기본적으로 배포 마법사에서 2 단계를 한 번 실행).</span><span class="sxs-lookup"><span data-stu-id="78599-120">When the computer is back up and running, you need to do these steps over again, starting from step three listed above (basically run Step 2 in the Deployment Wizard one more time).</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

