---
title: 'Lync Server 2013: 음성 라우팅 테스트'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Test voice routing
ms:assetid: d3aae909-fef6-440f-b144-0b62dc82bf5d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398915(v=OCS.15)
ms:contentKeyID: 48185444
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0ac9fdac24178bfec7ebce97cbdfdd15707913d1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40983508"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-voice-routing-in-lync-server-2013"></a><span data-ttu-id="05730-102">Lync Server 2013에서 음성 라우팅 테스트</span><span class="sxs-lookup"><span data-stu-id="05730-102">Test voice routing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="05730-103">_**마지막으로 수정한 주제:** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="05730-103">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="05730-104">Lync Server 제어판의 **음성 라우팅 탭 테스트** 를 사용 하 여 테스트 사례 시나리오를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05730-104">You can use the Lync Server Control Panel **Test Voice Routing** tab to configure test case scenarios.</span></span> <span data-ttu-id="05730-105">테스트 사례를 정의 하려면 지정 된 전화 번호를 테스트 하는 데 사용할 다이얼 플랜, 음성 정책, PSTN 사용 및 음성 경로를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="05730-105">To define a test case, you specify the dial plan, voice policy, PSTN usage, and voice route against which to test a specified phone number.</span></span>

<span data-ttu-id="05730-106">실제로 음성 라우팅 구성을 배포 하기 전에 다양 한 전화 번호를 테스트 하 여 예상 되는 결과를 확인 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="05730-106">Before you actually deploy your voice routing configuration, we recommend that you test it on various phone numbers to make sure that the results are what you're expecting.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="05730-107"><STRONG>테스트 사례 내보내기</STRONG> 및 <STRONG>테스트 사례 가져오기</STRONG> 명령을 사용 하 여 음성 라우팅 테스트 사례를 저장 하 고 다른 컴퓨터에서 사용 하도록 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05730-107">You can use the <STRONG>Export test cases</STRONG> and <STRONG>Import test cases</STRONG> commands to save voice routing test cases and import them for use on another computer.</span></span>



</div>

<div>


> [!WARNING]  
> <span data-ttu-id="05730-108">음성 라우팅 구성에서 다이얼 플랜, 음성 정책, 음성 경로, 전화 사용 등의 일부를 삭제 하는 경우에는 음성 라우팅 테스트 사례를 검토 하 고 업데이트 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="05730-108">If you delete any part of your voice routing configuration, such as a dial plan, voice policy, voice route, or phone usage, you should review and update your voice routing test cases.</span></span> <span data-ttu-id="05730-109">Lync Server 제어판은 변경 된 구성으로 인해 더 이상 유효 하지 않은 테스트 사례에 대 한 경고를 표시 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="05730-109">The Lync Server Control Panel will not alert you to test cases that are no longer valid due to changed configurations.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="05730-110">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="05730-110">In This Section</span></span>

  - [<span data-ttu-id="05730-111">Lync Server 2013에서 음성 라우팅 테스트 사례 만들기</span><span class="sxs-lookup"><span data-stu-id="05730-111">Create a voice routing test case in Lync Server 2013</span></span>](lync-server-2013-create-a-voice-routing-test-case.md)

  - [<span data-ttu-id="05730-112">Lync Server 2013에서 음성 라우팅 테스트 사례 내보내기</span><span class="sxs-lookup"><span data-stu-id="05730-112">Export voice routing test cases in Lync Server 2013</span></span>](lync-server-2013-export-voice-routing-test-cases.md)

  - [<span data-ttu-id="05730-113">Lync Server 2013에서 음성 라우팅 테스트 사례 가져오기</span><span class="sxs-lookup"><span data-stu-id="05730-113">Import voice routing test cases in Lync Server 2013</span></span>](lync-server-2013-import-voice-routing-test-cases.md)

  - [<span data-ttu-id="05730-114">Lync Server 2013에서 음성 라우팅 테스트 실행</span><span class="sxs-lookup"><span data-stu-id="05730-114">Running voice routing tests in Lync Server 2013</span></span>](lync-server-2013-running-voice-routing-tests.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

