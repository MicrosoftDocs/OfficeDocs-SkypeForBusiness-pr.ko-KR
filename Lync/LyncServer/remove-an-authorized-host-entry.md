---
title: 권한이 부여 된 호스트 항목 제거
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Remove an authorized host entry
ms:assetid: 56a04140-347e-4eef-bede-0e858534f71e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204902(v=OCS.15)
ms:contentKeyID: 48184177
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 849617676305cc2d7308c0c8b1a48bef327f3c87
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727188"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="remove-an-authorized-host-entry"></a><span data-ttu-id="1cdd4-102">권한이 부여 된 호스트 항목 제거</span><span class="sxs-lookup"><span data-stu-id="1cdd4-102">Remove an authorized host entry</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1cdd4-103">_**마지막으로 수정한 주제:** 2012-09-26_</span><span class="sxs-lookup"><span data-stu-id="1cdd4-103">_**Topic Last Modified:** 2012-09-26_</span></span>

<span data-ttu-id="1cdd4-104">이 항목에서는 레거시 권한 있는 호스트 항목 (Lync Server 2013에서 *신뢰할 수 있는 응용 프로그램 항목* 이라고 함)을 제거 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="1cdd4-104">This topic describes how to remove a legacy authorized host entry (known as a *trusted application entry* in Lync Server 2013).</span></span> <span data-ttu-id="1cdd4-105">원격 통화 제어를 Lync Server 2013 배포로 마이그레이션할 때 Office Communications Server 2007 R2 배포의 모든 SIP/CSTA 게이트웨이에 대 한 기존 권한이 있는 호스트 항목을 제거 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1cdd4-105">You must remove existing authorized host entries for any SIP/CSTA gateways in your Office Communications Server 2007 R2 deployment when you migrate remote call control to a Lync Server 2013 deployment.</span></span> <span data-ttu-id="1cdd4-106">Office Communications Server 2007 R2에 포함 된 관리 도구를 사용 하 여 기존의 권한 있는 호스트 항목을 제거 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1cdd4-106">You must use the administrative tools included with Office Communications Server 2007 R2 to remove the existing authorized host entries.</span></span>

<div>

## <a name="to-remove-an-authorized-host-entry-in-an-office-communications-server-2007-r2-deployment"></a><span data-ttu-id="1cdd4-107">Office Communications Server 2007 R2 배포에서 권한이 부여 된 호스트 항목을 제거 하려면</span><span class="sxs-lookup"><span data-stu-id="1cdd4-107">To remove an authorized host entry in an Office Communications Server 2007 R2 deployment</span></span>

1.  <span data-ttu-id="1cdd4-108">Office Communications Server 2007 R2 관리 콘솔을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="1cdd4-108">Open the Office Communications Server 2007 R2 administrative console.</span></span>

2.  <span data-ttu-id="1cdd4-109">트리를 확장 하 고 권한 있는 호스트가 만들어진 풀을 마우스 오른쪽 단추로 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="1cdd4-109">Expand the tree and right-click the pool where the authorized host was created.</span></span>

3.  <span data-ttu-id="1cdd4-110">**속성**을 클릭 한 다음 **프런트 엔드 속성**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="1cdd4-110">Click **Properties**, and then click **Front End Properties**.</span></span>

4.  <span data-ttu-id="1cdd4-111">**호스트 인증** 탭을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="1cdd4-111">Click the **Host Authorization** tab.</span></span>

5.  <span data-ttu-id="1cdd4-112">서버를 선택 하 고 **제거**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="1cdd4-112">Select a server, and then click **Remove**.</span></span>

6.  <span data-ttu-id="1cdd4-113">**속성**에서 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="1cdd4-113">In **Properties**, click **OK**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

