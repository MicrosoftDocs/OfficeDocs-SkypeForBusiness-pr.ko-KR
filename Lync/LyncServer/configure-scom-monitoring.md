---
title: SCOM 모니터링 구성
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
TOCTitle: Configure SCOM monitoring
ms:assetid: 4003d225-2a33-448c-abd9-571750661140
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688033(v=OCS.15)
ms:contentKeyID: 49733624
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8e114d3f18e482c11a8e83c9d4308f3c5712932c
ms.sourcegitcommit: 30ed4457d7004ba732372fee11a6f0b1baf48e05
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/08/2020
ms.locfileid: "40983905"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-scom-monitoring"></a><span data-ttu-id="0a8ee-102">SCOM 모니터링 구성</span><span class="sxs-lookup"><span data-stu-id="0a8ee-102">Configure SCOM monitoring</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0a8ee-103">_**마지막으로 수정한 주제:** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="0a8ee-103">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="0a8ee-104">Microsoft Lync Server 2013으로 마이그레이션한 후에는 몇 가지 작업을 완료 하 여 Lync Server 2013에서 System Center Operations Manager와 작동 하도록 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0a8ee-104">After migrating to Microsoft Lync Server 2013, you must complete a few tasks to configure Lync Server 2013 to work with System Center Operations Manager.</span></span>

  - <span data-ttu-id="0a8ee-105">중앙 검색 논리를 관리 하도록 선택한 서버에 Lync Server 2010 업데이트를 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="0a8ee-105">Apply Lync Server 2010 updates to a server elected to manage the central discovery logic.</span></span>

  - <span data-ttu-id="0a8ee-106">중앙 검색 후보 서버 레지스트리 키를 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="0a8ee-106">Update the central discovery candidate server registry key.</span></span>

  - <span data-ttu-id="0a8ee-107">기본 System Center Operations Manager 관리 서버를 구성 하 여 후보 중앙 검색 노드를 재정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="0a8ee-107">Configure your primary System Center Operations Manager management server to override the candidate central discovery node.</span></span>

<span data-ttu-id="0a8ee-108">각 작업을 수행 하기 위한 지침은 아래에서 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="0a8ee-108">Instructions for carrying out each of these tasks are provided below.</span></span>

<span data-ttu-id="0a8ee-109">**중앙 검색 논리를 관리 하도록 선택한 서버에 Lync Server 2010 업데이트를 적용 합니다.**</span><span class="sxs-lookup"><span data-stu-id="0a8ee-109">**Apply Lync Server 2010 updates to a server elected to manage the central discovery logic.**</span></span>

1.  <span data-ttu-id="0a8ee-110">System Center Operations Manager 에이전트 파일이 설치 되어 있고 후보 검색 노드로 구성 된 서버를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0a8ee-110">Elect a server that has the System Center Operations Manager agent files installed and is configured as a candidate discovery node.</span></span>

2.  <span data-ttu-id="0a8ee-111">이 서버에 Lync Server 2010 업데이트를 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="0a8ee-111">Apply Lync Server 2010 updates to this server.</span></span> <span data-ttu-id="0a8ee-112">[Lync Server 2010 업데이트 적용](apply-lync-server-2010-updates.md)항목을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="0a8ee-112">See the topic [Apply Lync Server 2010 updates](apply-lync-server-2010-updates.md).</span></span>

<span data-ttu-id="0a8ee-113">**중앙 검색 후보 서버 레지스트리 키를 업데이트 합니다.**</span><span class="sxs-lookup"><span data-stu-id="0a8ee-113">**Update the central discovery candidate server registry key.**</span></span>

1.  <span data-ttu-id="0a8ee-114">중앙 검색 논리를 관리 하도록 선택한 서버에서 Windows PowerShell 명령 창을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="0a8ee-114">On the server elected to manage the central discovery logic, open a Windows PowerShell command window.</span></span>

2.  <span data-ttu-id="0a8ee-115">명령줄에 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="0a8ee-115">At the command line, type the following:</span></span>
    
       ```PowerShell
        New-Item -Path "HKLM:\Software\Microsoft\Real-Time Communications\Health"
       ```
    
       ```PowerShell
        New-Item -Path "HKLM:\Software\Microsoft\Real-Time Communications\Health\CentralDiscoveryCandidate"
       ```
    
    <div class="">
    

    > [!NOTE]  
    > <span data-ttu-id="0a8ee-116">레지스트리를 편집할 때마다 레지스트리 키가 이미 있는 경우 명령에 실패 하는 오류가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0a8ee-116">Whenever you edit the registry, you may experience an error that the command failed if the registry key already exists.</span></span> <span data-ttu-id="0a8ee-117">이 문제가 발생 하는 경우 오류를 무시 해도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0a8ee-117">If you experience this, you can safely ignore the error.</span></span>

    
    </div>

<span data-ttu-id="0a8ee-118">**후보 중앙 검색 감시자 노드를 재정의 하도록 기본 System Center Operations Manager 관리 서버를 구성 합니다.**</span><span class="sxs-lookup"><span data-stu-id="0a8ee-118">**Configure your primary System Center Operations Manager management server to override the candidate central discovery watcher node.**</span></span>

1.  <span data-ttu-id="0a8ee-119">System Center Operations Manager 콘솔이 설치 된 컴퓨터에서 **관리 팩 개체** 를 확장 한 다음 **개체**검색을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0a8ee-119">On a computer where the System Center Operations Manager console has been installed, expand **Management Pack Objects** and then select **Object Discoveries**.</span></span>

2.  <span data-ttu-id="0a8ee-120">**범위 변경을** 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="0a8ee-120">Click **Change Scope...**</span></span>

3.  <span data-ttu-id="0a8ee-121">**범위 관리 팩 개체** 페이지에서 **LS 검색 후보**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0a8ee-121">From the **Scope Management Pack Objects** page, select **LS Discovery Candidate**.</span></span>

4.  <span data-ttu-id="0a8ee-122">**LS 검색 후보 유효 값** 을 이전 절차에서 선택한 후보 서버의 이름으로 재정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="0a8ee-122">Override the **LS Discovery Candidate Effective Value** to the name of the candidate server elected in the earlier procedure.</span></span>

<span data-ttu-id="0a8ee-123">마지막으로, 변경 내용을 마무리 하려면 System Center Operations Manager 루트 관리 서버에서 상태 서비스를 다시 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="0a8ee-123">Lastly, to finalize your changes, restart the health service on the System Center Operations Manager Root Management Server.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

