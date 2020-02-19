---
title: 'Lync Server 2013: 음성 번호 정규화 및 라우팅 확인'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Validating voice number normalization and routing
ms:assetid: a6a825c7-6928-4e80-b7e9-803b7f7ebd13
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720922(v=OCS.15)
ms:contentKeyID: 63969633
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f92809d018bf8b69e6bc3fd5cc640c40836249de
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42113381"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="validating-voice-number-normalization-and-routing-in-lync-server-2013"></a><span data-ttu-id="938c5-102">Lync Server 2013에서 음성 번호 정규화 및 라우팅 확인</span><span class="sxs-lookup"><span data-stu-id="938c5-102">Validating voice number normalization and routing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="938c5-103">_**마지막으로 수정 된 항목:** 2014-05-19_</span><span class="sxs-lookup"><span data-stu-id="938c5-103">_**Topic Last Modified:** 2014-05-19_</span></span>

<span data-ttu-id="938c5-104">올바른 번호 정규화와 라우팅은 기능적인 엔터프라이즈 음성 환경에서 매우 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="938c5-104">Correct number normalization and routing is very important for functional Enterprise Voice environment.</span></span> <span data-ttu-id="938c5-105">특히 PBX (private branch exchange)에서 독립 실행형 Lync Server 환경으로 마이그레이션하는 동안, 모든 기존 전화 걸기 규칙을 표시 하 고 문서화 하 고, 적절 한 정규화 규칙, 음성 정책을 만드는 등의 작업을 수행 하는 것이 좋습니다. 전화 사용 및 경로</span><span class="sxs-lookup"><span data-stu-id="938c5-105">Especially during migrations from private branch exchange (PBX) to stand-alone Lync Server environment, one of the keys to successful migration is to reveal and document all existing dialing rules, and create appropriate normalization rules, voice policies, phone usages and routes.</span></span>

<span data-ttu-id="938c5-106">마이그레이션 중에는 번호 정규화와 라우팅을 확인 하는 것이 중요 하지만 시스템을 정상적으로 작동 하는 경우에도 가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="938c5-106">Validating number normalization and routing is important not only during migrations but also during normal, stable operation of the system.</span></span>

<span data-ttu-id="938c5-107">Lync server 전역 설정에 게시 된 현재 정규화 규칙 집합에 대해 견고한 테스트 사례 집합을 개발 하는 것부터 시작 하 여 매일이 유효성 검사를 수행 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="938c5-107">We recommend conducting this validation daily by using the Lync Server Control Panel, starting with developing a robust set of test cases against the current set of normalization rules that were published in the Lync Server global settings.</span></span> <span data-ttu-id="938c5-108">이러한 테스트 사례는 매일 실행 하 여 다이얼 플랜에 적용 되거나 커밋된 원치 않는 변경을 강조 표시 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="938c5-108">These test cases should be run daily to highlight any unwanted changes that were made and committed to the dial plan.</span></span>

<span data-ttu-id="938c5-109">Lync Server 제어판은 또한 음성 라우팅 및 Enterprise Voice number 정규화 규칙, 다이얼 플랜, 음성 정책 및 경로 변경에 대 한 구성 정보를 시각화, 테스트, 변경, 보관 및 공유 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="938c5-109">Lync Server Control Panel also helps you visualize, test, change, archive, and share configuration information about voice routing and in changing Enterprise Voice number normalization rules, dial plans, voice policy, and routes.</span></span> <span data-ttu-id="938c5-110">다음과 같은 추가 기능을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="938c5-110">It has additional features for doing the following:</span></span>

  - <span data-ttu-id="938c5-111">시스템 간에 음성 라우팅 데이터 내보내기 및 가져오기 또는 백업</span><span class="sxs-lookup"><span data-stu-id="938c5-111">Exporting and importing or backing up voice routing data between systems.</span></span>

  - <span data-ttu-id="938c5-112">구성 변경 내용을 라이브 시스템에 업로드 하기 전에 테스트</span><span class="sxs-lookup"><span data-stu-id="938c5-112">Testing configuration changes before uploading them to a live system.</span></span>

  - <span data-ttu-id="938c5-113">구성 테스트 사례를 만들고 실행 하 여 배포 된 시스템에 변경 내용을 커밋하기 전에 라우팅 데이터의 유용성을 보장 하는 데 도움을 주는 작업입니다.</span><span class="sxs-lookup"><span data-stu-id="938c5-113">Creating and running configuration test cases to help ensure the usability of routing data after you make changes to it, but before committing them the changes to a deployed system.</span></span>

  - <span data-ttu-id="938c5-114">필요한 정규식을 작성 하지 않고 숫자 정규화 규칙, 위치 프로필, 음성 정책 및 라우팅 데이터를 만들고 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="938c5-114">Creating and changing number normalization rules, location profiles, voice policy, and routing data without writing the necessary regular expressions.</span></span>

  - <span data-ttu-id="938c5-115">Lync Server Phone Edition과의 호환성을 위해 위치 프로필을 분석 합니다.</span><span class="sxs-lookup"><span data-stu-id="938c5-115">Analyzing a location profile for compatibility with the Lync Server Phone Edition.</span></span>

  - <span data-ttu-id="938c5-116">음성 라우팅 테스트에 대 한 자세한 내용은 [Lync Server 2013의 테스트 음성 라우팅](lync-server-2013-test-voice-routing.md) 에서 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="938c5-116">More information about voice routing tests can be found at [Test voice routing in Lync Server 2013](lync-server-2013-test-voice-routing.md)</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="938c5-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="938c5-117">See Also</span></span>


[<span data-ttu-id="938c5-118">Lync Server 2013에서 음성 라우팅 테스트</span><span class="sxs-lookup"><span data-stu-id="938c5-118">Test voice routing in Lync Server 2013</span></span>](lync-server-2013-test-voice-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

