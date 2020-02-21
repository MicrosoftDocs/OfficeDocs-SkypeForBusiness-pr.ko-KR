---
title: 'Lync Server 2013: 기존 중앙 관리 서버 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure an existing Central Management Server
ms:assetid: d715b24a-1256-4a7c-a5ef-1cee41d6b733
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205315(v=OCS.15)
ms:contentKeyID: 48185584
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 09c4102008eca37d79d2862a3ede8b1498899511
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42205154"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-an-existing-central-management-server-in-lync-server-2013"></a><span data-ttu-id="1e3ce-102">Lync Server 2013에서 기존 중앙 관리 서버 구성</span><span class="sxs-lookup"><span data-stu-id="1e3ce-102">Configure an existing Central Management Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1e3ce-103">_**마지막으로 수정 된 항목:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="1e3ce-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="1e3ce-104">기존 Lync Server 2013 배포에서 중앙 관리 서버를 다시 사용 하는 경우 아래에 설명 된 절차를 실행 하 여 Lync Server 제어판 및 Windows PowerShell이 올바르게 작동 하는지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1e3ce-104">If you reuse a Central Management Server from an existing Lync Server 2013 deployment, you must run the procedure described below to make sure that Lync Server Control Panel and Windows PowerShell function correctly.</span></span>

<div>

## <a name="to-configure-an-existing-central-management-server"></a><span data-ttu-id="1e3ce-105">기존 중앙 관리 서버를 구성 하려면</span><span class="sxs-lookup"><span data-stu-id="1e3ce-105">To configure an existing Central Management Server</span></span>

1.  <span data-ttu-id="1e3ce-106">**시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="1e3ce-106">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="1e3ce-107">**업데이트-CsAdminRole** cmdlet을 사용 하 여 중앙 관리 서버에 저장 된 RBAC (역할 기반 액세스 제어) 역할을 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="1e3ce-107">Use the **Update-CsAdminRole** cmdlet to update the role-based access control (RBAC) roles stored in the Central Management Server.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="1e3ce-108">오류가 있는 경우를 제외하고 출력되는 내용이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1e3ce-108">No output is expected unless there is an error.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

