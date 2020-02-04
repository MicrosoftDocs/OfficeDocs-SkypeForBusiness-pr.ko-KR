---
title: 새 Lync Server 2013 중재 서버를 사용 하도록 음성 경로 변경
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Change voice routes to use the new Lync Server 2013 Mediation Server
ms:assetid: acd487b3-377c-46bf-9f71-fe6152002664
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205162(v=OCS.15)
ms:contentKeyID: 48185069
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 40f9bed4262adcabdb23e5b5b85e7de43292d18b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727558"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="change-voice-routes-to-use-the-new-lync-server-2013-mediation-server"></a><span data-ttu-id="915d0-102">새 Lync Server 2013 중재 서버를 사용 하도록 음성 경로 변경</span><span class="sxs-lookup"><span data-stu-id="915d0-102">Change voice routes to use the new Lync Server 2013 Mediation Server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="915d0-103">_**마지막으로 수정한 주제:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="915d0-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="915d0-104">이 절차는 레거시 Office Communications Server 2007 R2 중재 서버 대신 Lync Server 2013 조정 서버를 사용 하도록 음성 경로를 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="915d0-104">This procedure changes the voice routes to use the Lync Server 2013 Mediation Server, instead of the legacy Office Communications Server 2007 R2 Mediation Server.</span></span>

<div>

## <a name="to-change-the-voice-routes-to-use-the-new-mediation-server"></a><span data-ttu-id="915d0-105">새 중재 서버를 사용 하도록 음성 경로를 변경 하려면</span><span class="sxs-lookup"><span data-stu-id="915d0-105">To change the voice routes to use the new Mediation Server</span></span>

1.  <span data-ttu-id="915d0-106">Lync Server 2013 제어판</span><span class="sxs-lookup"><span data-stu-id="915d0-106">Lync Server 2013 Control Panel</span></span>

2.  <span data-ttu-id="915d0-107">왼쪽 창에서 **음성 라우팅과** **경로**를 차례로 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="915d0-107">In the left pane, select **Voice Routing** and then **Route**.</span></span>

3.  <span data-ttu-id="915d0-108">새로 **만들기를 클릭 하** 여 새 음성 경로를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="915d0-108">Click **New** to create a New Voice Route.</span></span>

4.  <span data-ttu-id="915d0-109">다음 필드를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="915d0-109">Fill in the following fields:</span></span>
    
      - <span data-ttu-id="915d0-110">**Name (이름**): 음성 경로의 설명적인 이름을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="915d0-110">**Name**: Type a descriptive name of the voice route.</span></span> <span data-ttu-id="915d0-111">이 문서에서는 **W15PSTNRoute**를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="915d0-111">For this document we will use **W15PSTNRoute**.</span></span>
    
      - <span data-ttu-id="915d0-112">**설명**: 음성 경로에 대 한 간단한 설명을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="915d0-112">**Description**: Type a short description of the voice route.</span></span>

5.  <span data-ttu-id="915d0-113">**연결 된 게이트웨이에**도달할 때까지 나머지 섹션을 모두 건너뜁니다.</span><span class="sxs-lookup"><span data-stu-id="915d0-113">Skip all remaining sections until you reach **Associated gateways**.</span></span> <span data-ttu-id="915d0-114">**추가**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="915d0-114">Click **Add**.</span></span> <span data-ttu-id="915d0-115">새 기본 게이트웨이를 선택 하 고 **확인을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="915d0-115">Select the new default gateway and click **OK**.</span></span>

6.  <span data-ttu-id="915d0-116">**연결 된 PSTN 용도**에서 **선택을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="915d0-116">Under **Associated PSTN Usages**, click **Select**.</span></span>

7.  <span data-ttu-id="915d0-117">**PSTN 사용 레코드 선택** 페이지에서 레코드 이름을 선택한 다음 **확인을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="915d0-117">From the **Select PSTN Usage Record** page, select a record name and then click **OK**.</span></span>

8.  <span data-ttu-id="915d0-118">**새 음성 경로** 페이지에서 **확인** 을 클릭 하 여 **음성 경로**를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="915d0-118">From the **New Voice Route** page, click **OK** to create the **Voice Route**.</span></span>

9.  <span data-ttu-id="915d0-119">**음성 라우팅** 페이지에서 **경로**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="915d0-119">From the **Voice Routing** page, select **Route**.</span></span>

10. <span data-ttu-id="915d0-120">새로 만든 경로를 목록의 맨 위로 이동한 다음 **Commit**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="915d0-120">Move the newly created route to the top of the list and then select **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

