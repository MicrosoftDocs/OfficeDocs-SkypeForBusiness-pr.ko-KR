---
title: 권한이 부여 된 호스트 항목 제거
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Remove an authorized host entry
ms:assetid: 56a04140-347e-4eef-bede-0e858534f71e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204902(v=OCS.15)
ms:contentKeyID: 48184177
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cd64239460d76d63b28bb3a3abeb8c5cc8bb97d9
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44757139"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="remove-an-authorized-host-entry"></a><span data-ttu-id="10f78-102">권한이 부여 된 호스트 항목 제거</span><span class="sxs-lookup"><span data-stu-id="10f78-102">Remove an authorized host entry</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="10f78-103">_**마지막으로 수정 된 항목:** 2012-09-26_</span><span class="sxs-lookup"><span data-stu-id="10f78-103">_**Topic Last Modified:** 2012-09-26_</span></span>

<span data-ttu-id="10f78-104">이 항목에서는 Lync Server 2013의 *신뢰할 수 있는 응용 프로그램 항목* 으로 알려진 레거시 권한 부여 된 호스트 항목을 제거 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="10f78-104">This topic describes how to remove a legacy authorized host entry (known as a *trusted application entry* in Lync Server 2013).</span></span> <span data-ttu-id="10f78-105">원격 통화 제어를 Lync Server 2013 배포로 마이그레이션할 때 Office Communications Server 2007 R2 배포에서 모든 SIP/CSTA 게이트웨이 용으로 권한이 부여 된 기존 호스트 항목을 제거 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="10f78-105">You must remove existing authorized host entries for any SIP/CSTA gateways in your Office Communications Server 2007 R2 deployment when you migrate remote call control to a Lync Server 2013 deployment.</span></span> <span data-ttu-id="10f78-106">권한이 부여 된 기존 호스트 항목을 제거 하려면 Office Communications Server 2007 r 2에 포함 된 관리 도구를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="10f78-106">You must use the administrative tools included with Office Communications Server 2007 R2 to remove the existing authorized host entries.</span></span>

<div>

## <a name="to-remove-an-authorized-host-entry-in-an-office-communications-server-2007-r2-deployment"></a><span data-ttu-id="10f78-107">Office Communications Server 2007 R2 배포에서 권한이 부여 된 호스트 항목을 제거 하려면</span><span class="sxs-lookup"><span data-stu-id="10f78-107">To remove an authorized host entry in an Office Communications Server 2007 R2 deployment</span></span>

1.  <span data-ttu-id="10f78-108">Office Communications Server 2007 R2 관리 콘솔을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="10f78-108">Open the Office Communications Server 2007 R2 administrative console.</span></span>

2.  <span data-ttu-id="10f78-109">트리를 확장하고 권한이 부여된 호스트를 만든 풀을 마우스 오른쪽 단추로 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="10f78-109">Expand the tree and right-click the pool where the authorized host was created.</span></span>

3.  <span data-ttu-id="10f78-110">**속성**을 클릭한 다음 **프런트 엔드 속성**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="10f78-110">Click **Properties**, and then click **Front End Properties**.</span></span>

4.  <span data-ttu-id="10f78-111">**호스트 권한 부여** 탭을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="10f78-111">Click the **Host Authorization** tab.</span></span>

5.  <span data-ttu-id="10f78-112">서버를 클릭하고 **제거**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="10f78-112">Select a server, and then click **Remove**.</span></span>

6.  <span data-ttu-id="10f78-113">**속성**에서 **확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="10f78-113">In **Properties**, click **OK**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

