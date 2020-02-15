---
title: SCOM 모니터링 구성
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Configure SCOM monitoring
ms:assetid: 4003d225-2a33-448c-abd9-571750661140
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688033(v=OCS.15)
ms:contentKeyID: 49733624
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8266097035a284c966ad62672515cb2a64444339
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2020
ms.locfileid: "42006644"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-scom-monitoring"></a><span data-ttu-id="848db-102">SCOM 모니터링 구성</span><span class="sxs-lookup"><span data-stu-id="848db-102">Configure SCOM monitoring</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="848db-103">_**마지막으로 수정 된 항목:** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="848db-103">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="848db-104">Microsoft Lync Server 2013로 마이그레이션한 후에는 몇 가지 작업을 완료 하 여 Lync Server 2013에서 System Center Operations Manager와 함께 작동 하도록 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="848db-104">After migrating to Microsoft Lync Server 2013, you must complete a few tasks to configure Lync Server 2013 to work with System Center Operations Manager.</span></span>

  - <span data-ttu-id="848db-105">중앙 검색 논리를 관리 하도록 선택한 서버에 Lync Server 2010 업데이트를 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="848db-105">Apply Lync Server 2010 updates to a server elected to manage the central discovery logic.</span></span>

  - <span data-ttu-id="848db-106">중앙 검색 후보 서버 레지스트리 키를 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="848db-106">Update the central discovery candidate server registry key.</span></span>

  - <span data-ttu-id="848db-107">기본 System Center Operations Manager 관리 서버를 구성 하 여 후보 중앙 검색 노드를 재정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="848db-107">Configure your primary System Center Operations Manager management server to override the candidate central discovery node.</span></span>

<span data-ttu-id="848db-108">이러한 각 작업의 수행 지침은 아래에 제공되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="848db-108">Instructions for carrying out each of these tasks are provided below.</span></span>

<span data-ttu-id="848db-109">**중앙 검색 논리를 관리 하도록 선택한 서버에 Lync Server 2010 업데이트를 적용 합니다.**</span><span class="sxs-lookup"><span data-stu-id="848db-109">**Apply Lync Server 2010 updates to a server elected to manage the central discovery logic.**</span></span>

1.  <span data-ttu-id="848db-110">System Center Operations Manager 에이전트 파일을 설치하고 후보 검색 노드로 구성할 서버를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="848db-110">Elect a server that has the System Center Operations Manager agent files installed and is configured as a candidate discovery node.</span></span>

2.  <span data-ttu-id="848db-111">Lync Server 2010 업데이트를이 서버에 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="848db-111">Apply Lync Server 2010 updates to this server.</span></span> <span data-ttu-id="848db-112">[Lync Server 2010 업데이트 적용](apply-lync-server-2010-updates.md)항목을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="848db-112">See the topic [Apply Lync Server 2010 updates](apply-lync-server-2010-updates.md).</span></span>

<span data-ttu-id="848db-113">**중앙 검색 후보 서버 레지스트리 키를 업데이트합니다.**</span><span class="sxs-lookup"><span data-stu-id="848db-113">**Update the central discovery candidate server registry key.**</span></span>

1.  <span data-ttu-id="848db-114">중앙 검색 논리를 관리 하도록 선택한 서버에서 Windows PowerShell 명령 창을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="848db-114">On the server elected to manage the central discovery logic, open a Windows PowerShell command window.</span></span>

2.  <span data-ttu-id="848db-115">명령줄에 다음을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="848db-115">At the command line, type the following:</span></span>
    
       ```PowerShell
        New-Item -Path "HKLM:\Software\Microsoft\Real-Time Communications\Health"
       ```
    
       ```PowerShell
        New-Item -Path "HKLM:\Software\Microsoft\Real-Time Communications\Health\CentralDiscoveryCandidate"
       ```
    
    <div class="">
    

    > [!NOTE]  
    > <span data-ttu-id="848db-p102">레지스트리를 편집할 때마다 레지스트리 키가 이미 있으면 명령이 실패했다는 오류가 발생할 수 있습니다. 이 문제가 발생할 경우 오류를 무시해도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="848db-p102">Whenever you edit the registry, you may experience an error that the command failed if the registry key already exists. If you experience this, you can safely ignore the error.</span></span>

    
    </div>

<span data-ttu-id="848db-118">**기본 System Center Operations Manager 관리 서버를 구성 하 여 후보 중앙 검색 감시자 노드를 재정의 합니다.**</span><span class="sxs-lookup"><span data-stu-id="848db-118">**Configure your primary System Center Operations Manager management server to override the candidate central discovery watcher node.**</span></span>

1.  <span data-ttu-id="848db-119">System Center Operations Manager 콘솔이 설치된 컴퓨터에서 **관리 팩 개체**를 확장한 후 **개체 검색**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="848db-119">On a computer where the System Center Operations Manager console has been installed, expand **Management Pack Objects** and then select **Object Discoveries**.</span></span>

2.  <span data-ttu-id="848db-120">**범위 변경...** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="848db-120">Click **Change Scope...**</span></span>

3.  <span data-ttu-id="848db-121">**관리 팩 개체 범위 지정** 페이지에서 **LS 검색 후보**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="848db-121">From the **Scope Management Pack Objects** page, select **LS Discovery Candidate**.</span></span>

4.  <span data-ttu-id="848db-122">**LS 검색 후보 유효 값**을 이전 절차에서 선택한 후보 서버의 이름으로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="848db-122">Override the **LS Discovery Candidate Effective Value** to the name of the candidate server elected in the earlier procedure.</span></span>

<span data-ttu-id="848db-123">마지막으로 변경 내용을 마무리하기 위해 System Center Operations Manager 루트 관리 서버에서 상태 관리 서비스를 다시 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="848db-123">Lastly, to finalize your changes, restart the health service on the System Center Operations Manager Root Management Server.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

