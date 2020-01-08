---
title: 'Lync Server 2013: 비디오 계획 및 배포'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Planning and deploying video
ms:assetid: dadfb7f3-dfd6-4847-b137-17dacafd7368
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205307(v=OCS.15)
ms:contentKeyID: 48185558
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: feac758dcc8547128c9b3684bc74dd6b69599d5f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40985320"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-and-deploying-video-in-lync-server-2013"></a><span data-ttu-id="74b4e-102">Lync Server 2013에서 비디오 계획 및 배포</span><span class="sxs-lookup"><span data-stu-id="74b4e-102">Planning and deploying video in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="74b4e-103">_**마지막으로 수정한 주제:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="74b4e-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="74b4e-104">Lync Server 2013에는 다음과 같은 새로운 비디오 기능이 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="74b4e-104">Lync Server 2013 introduces the following new video features:</span></span>

  - <span data-ttu-id="74b4e-105">**Hd 영상**   사용자는 2-파티 통화와 단체 회의에서 최고 hd (고화질) (즉, 1920 x 1080)에 대 한 해상도를 경험할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74b4e-105">**HD video**   Users can experience resolutions up to full high definition (HD) (that is, 1920 x 1080) in two-party calls and multiparty conferences.</span></span>

  - <span data-ttu-id="74b4e-106">**갤러리 보기**   두 명 이상이 있는 비디오 컨퍼런스에서는 사용자가 회의 참가자의 비디오를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74b4e-106">**Gallery View**   In video conferences that have more than two people, users can see videos of participants in the conference.</span></span> <span data-ttu-id="74b4e-107">회의에 다섯 명 이상의 참가자가 있는 경우 가장 활발 한 참가자의 비디오만 맨 위 행에 표시 되 고 다른 참가자에 게 사진이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="74b4e-107">If the conference has more than five participants, video of only the most active participants appears in the top row, and a photo appears for the other participants.</span></span>

  - <span data-ttu-id="74b4e-108">**H-264**   비디오 코덱이 Lync 2013 클라이언트에서 비디오를 인코딩하기 위한 기본입니다.</span><span class="sxs-lookup"><span data-stu-id="74b4e-108">**H.264 video**   The H.264 video codec is now the default for encoding video on Lync 2013 clients.</span></span> <span data-ttu-id="74b4e-109">H-264 비디오는 더 다양 한 해상도와 프레임 속도를 지원 하 고 비디오 확장성을 개선 합니다.</span><span class="sxs-lookup"><span data-stu-id="74b4e-109">H.264 video supports a greater range of resolutions and frame rates, and improves video scalability.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="74b4e-110">Lync Server 2013는 이전 버전의 Lync와의 상호 운용성을 위한 VC1 코덱을 여전히 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="74b4e-110">Lync Server 2013 still supports the VC1 codec for interoperability with previous versions of Lync.</span></span> <span data-ttu-id="74b4e-111">새 비디오 코덱에 대 한 자세한 내용과 배경 정보는 Jeff Schertz의 블로그 문서, "Lync 2013의 영상 상호 운용성"을 참조 하세요 <A class=uri href="http://blog.schertz.name/2012/07/video-interoperability-in-lync-2013/">http://blog.schertz.name/2012/07/video-interoperability-in-lync-2013/</A>.</span><span class="sxs-lookup"><span data-stu-id="74b4e-111">For details and background information about the new video codec, see Jeff Schertz's Blog article, "Video Interoperability in Lync 2013," at <A class=uri href="http://blog.schertz.name/2012/07/video-interoperability-in-lync-2013/">http://blog.schertz.name/2012/07/video-interoperability-in-lync-2013/</A>.</span></span>

    
    </div>

<span data-ttu-id="74b4e-112">이 섹션에서는 Lync Server 2013에서 비디오 대역폭을 관리 하는 방법과 비디오 기능을 구성 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="74b4e-112">This section describes how to manage bandwidth for video in Lync Server 2013 and how to configure video features.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="74b4e-113">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="74b4e-113">In This Section</span></span>

  - [<span data-ttu-id="74b4e-114">Lync Server 2013에서 비디오 대역폭 구성</span><span class="sxs-lookup"><span data-stu-id="74b4e-114">Configuring video bandwidth in Lync Server 2013</span></span>](lync-server-2013-configuring-video-bandwidth.md)

  - [<span data-ttu-id="74b4e-115">Lync Server 2013에서 갤러리 보기 구성</span><span class="sxs-lookup"><span data-stu-id="74b4e-115">Configuring Gallery View in Lync Server 2013</span></span>](lync-server-2013-configuring-gallery-view.md)

  - [<span data-ttu-id="74b4e-116">Lync Server 2013에 대 한 비디오 구성 예제 시나리오</span><span class="sxs-lookup"><span data-stu-id="74b4e-116">Configuring video example scenarios for Lync Server 2013</span></span>](lync-server-2013-configuring-video-example-scenarios.md)

  - [<span data-ttu-id="74b4e-117">Lync Server 2013에서 비디오 회의에 대 한 상호 운용성 고려 사항</span><span class="sxs-lookup"><span data-stu-id="74b4e-117">Interoperability considerations for video conferencing in Lync Server 2013</span></span>](lync-server-2013-interoperability-considerations-for-video-conferencing.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

