---
title: 'Lync Server 2013: 음성 라우팅 테스트 사례 내보내기'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Export voice routing test cases
ms:assetid: 489ac472-1a35-4755-b390-48f7cdf31e94
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425957(v=OCS.15)
ms:contentKeyID: 48184050
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f4f366c286c332625779a7ebf45fecfa918ea16b
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48528355"
---
# <a name="export-voice-routing-test-cases-in-lync-server-2013"></a><span data-ttu-id="0a2ba-102">Lync Server 2013에서 음성 라우팅 테스트 사례 내보내기</span><span class="sxs-lookup"><span data-stu-id="0a2ba-102">Export voice routing test cases in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0a2ba-103">_**마지막으로 수정 된 항목:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="0a2ba-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="0a2ba-104">테스트 사례를 통해 조직에서 음성 경로를 테스트할 수 있습니다. 전화를 걸고 사용할 다이얼 플랜 및 음성 정책의 이러한 항목을 정의한 다음 Lync Server에서 해당 조건이 제공 되 면 주어진 번호를 PSTN 네트워크로 성공적으로 라우팅할 수 있는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0a2ba-104">Test cases provide a way for you to test voice routes in your organization: you define such things as the number to be dialed and the dial plan and voice policy to be employed, and Lync Server can then verify that, given those conditions, the supplied number can successfully be routed to the PSTN network.</span></span>

<span data-ttu-id="0a2ba-105">Lync Server 제어판을 사용 하 여 만들 수 있는 테스트 사례는 일반적으로 대/소문자를 처음 만든 후 실행 한 서버에만 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0a2ba-105">Test cases, which can be created by using Lync Server Control Panel, are typically saved only on the server where the case was originally created and run.</span></span> <span data-ttu-id="0a2ba-106">하지만 이러한 테스트 사례를 XML 파일(.vtest 확장명)로 내보내고 다른 서버에서 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0a2ba-106">However, these test cases can be exported as XML files (with the .vtest extension) and then imported on other servers.</span></span> <span data-ttu-id="0a2ba-107">이러한 방식을 통해 토폴로지의 여러 지점에 있는 서로 다른 컴퓨터에서 동일한 테스트를 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0a2ba-107">This enables you to run the same tests on different computers located at different points in your topology.</span></span>

<div>

## <a name="to-export-a-voice-routing-test-case"></a><span data-ttu-id="0a2ba-108">음성 라우팅 테스트 사례를 내보내려면</span><span class="sxs-lookup"><span data-stu-id="0a2ba-108">To export a voice routing test case</span></span>

1.  <span data-ttu-id="0a2ba-109">Lync Server 제어판에서 **음성 라우팅을** 클릭 하 고 **음성 라우팅 테스트**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="0a2ba-109">In Lync Server Control Panel, click **Voice Routing** and then click **Test Voice Routing**.</span></span>

2.  <span data-ttu-id="0a2ba-p102">**음성 라우팅 테스트** 탭에서 내보낼 테스트 사례를 선택합니다. 여러 테스트 사례를 선택하려면 내보낼 첫 번째 테스트 사례를 클릭한 후 Ctrl 키를 누른 상태로 내보낼 다른 테스트 사례를 계속 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0a2ba-p102">On the **Test Voice Routing** tab, select the test case (or test cases) to be exported. To select multiple test cases, click the first case to be exported, then hold down the Ctrl key and select the additional cases to be exported.</span></span>

3.  <span data-ttu-id="0a2ba-112">**동작**에서 **테스트 사례 내보내기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="0a2ba-112">Click **Action**, then click **Export test cases**.</span></span>

4.  <span data-ttu-id="0a2ba-p103">**다른 이름으로 저장** 대화 상자에서 내보낸 테스트 사례를 저장할 폴더를 선택하고 **파일 이름** 상자에 결과 XML 파일의 이름을 입력합니다. 여러 테스트 사례를 내보낼 경우 모든 테스트 사례가 단일 XML 파일로 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="0a2ba-p103">In the **Save As** dialog box, select a folder to store the exported test cases and type a name for the resulting XML file in the **File name** box. Note that if you are exporting multiple tests cases all of these test cases will be saved to a single XML file.</span></span>

5.  <span data-ttu-id="0a2ba-115">테스트 사례를 저장하려면 **저장**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="0a2ba-115">To save the test cases, click **Save**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="0a2ba-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0a2ba-116">See Also</span></span>


[<span data-ttu-id="0a2ba-117">Lync Server 2013에서 음성 라우팅 테스트 사례 가져오기</span><span class="sxs-lookup"><span data-stu-id="0a2ba-117">Import voice routing test cases in Lync Server 2013</span></span>](lync-server-2013-import-voice-routing-test-cases.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

