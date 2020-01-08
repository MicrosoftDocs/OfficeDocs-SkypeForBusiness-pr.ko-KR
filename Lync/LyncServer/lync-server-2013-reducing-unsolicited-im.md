---
title: 'Lync Server 2013: 원치 않는 메신저 대화 줄이기'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Reducing unsolicited IM for Lync Server 2013
ms:assetid: d2998708-e699-4465-a918-e1d9ea4c49c3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn518335(v=OCS.15)
ms:contentKeyID: 62625493
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5042c4400cdf16be650a3c2c74ed756f01d93114
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40985675"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="reducing-unsolicited-im-for-lync-server-2013"></a><span data-ttu-id="c5dd8-102">Lync Server 2013에 대해 원치 않는 메신저 대화 줄이기</span><span class="sxs-lookup"><span data-stu-id="c5dd8-102">Reducing unsolicited IM for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c5dd8-103">_**마지막으로 수정한 주제:** 2013-12-05_</span><span class="sxs-lookup"><span data-stu-id="c5dd8-103">_**Topic Last Modified:** 2013-12-05_</span></span>

<span data-ttu-id="c5dd8-104">지능형 IM 필터 응용 프로그램은 사용자 환경에 대 한 성능 저하를 최소화 하 여 가장 일반적인 바이러스에 대해 Microsoft Lync Server 2013 배포를 보호 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c5dd8-104">The Intelligent IM Filter application helps protect your Microsoft Lync Server 2013 deployment against the most common viruses with minimal degradation to the user experience.</span></span> <span data-ttu-id="c5dd8-105">지능형 IM 필터는 다음을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5dd8-105">The Intelligent IM Filter provides the following:</span></span>

  - <span data-ttu-id="c5dd8-106">향상 된 URL 필터링</span><span class="sxs-lookup"><span data-stu-id="c5dd8-106">Enhanced URL filtering</span></span>

  - <span data-ttu-id="c5dd8-107">향상 된 파일 전송 필터링</span><span class="sxs-lookup"><span data-stu-id="c5dd8-107">Enhanced file transfer filtering</span></span>

<span data-ttu-id="c5dd8-108">지능형 IM 필터를 사용 하 여 필터를 구성 하 여 회사 방화벽 외부의 알 수 없는 끝점에서 원하지 않거나 위험한 인스턴트 메시지를 차단 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5dd8-108">Use Intelligent IM Filter to configure filters to block unsolicited or potentially harmful instant messages from unknown endpoints outside the corporate firewall.</span></span> <span data-ttu-id="c5dd8-109">하이퍼링크 및 특정 확장명을 가진 파일을 포함 하는 인스턴트 메시지와 같이 차단 되어야 하는 항목을 결정 하는 데 사용할 조건을 지정 하 여 필터를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5dd8-109">You configure filters by specifying the criteria to be used to determine what should be blocked, such as instant messages containing hyperlinks and files with specific extensions.</span></span>

<span data-ttu-id="c5dd8-110">지능형 IM 메시지 필터 응용 프로그램을 배포 하기 전에, 메시지가 하나의 Lync Server 2013 서버에서 기타 서버로 라우팅될 때 필터링 옵션이 적용 되는 방식을 이해 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5dd8-110">Before you deploy the Intelligent IM Message Filter application, you should understand how filtering options are applied when messages are routed from one Lync Server 2013 server to another.</span></span> <span data-ttu-id="c5dd8-111">이러한 필터링 옵션이 적용 되는 방식에 따라 서버가 단일 조직에 있든 조직 경계를 넘어 지에 관계 없이 일관성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5dd8-111">The way these filtering options are applied is consistent, regardless of whether the servers are located in a single organization or across organizational boundaries.</span></span> <span data-ttu-id="c5dd8-112">이 일관성은 사용자 지정 된 알림 및 경고 텍스트를 메시지에 삽입 하 고 서버에서 보내는 방식에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c5dd8-112">This consistency applies to the way that the customized notice, and warning texts are inserted into messages and sent across servers.</span></span>

<span data-ttu-id="c5dd8-113">추천 필터링 옵션은 하이퍼링크를 사용 하는 인스턴트 메시지를 허용 하 되, 지능형 IM 필터를 사용 하 여 링크에 밑줄을 삽입 하는 것이 더 이상 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c5dd8-113">The recommended filtering option is to allow instant messages with hyperlinks but require the Intelligent IM Filter to disable the link by inserting an underscore before it.</span></span> <span data-ttu-id="c5dd8-114">이 옵션을 선택 하면 하이퍼링크를 포함 하는 각 인스턴트 메시지의 시작 부분에 표시 되는 사용자에 게 알림을 작성할 수 있는 추가 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5dd8-114">If you choose this option, you have the additional option of composing a notice to users that appears at the beginning of each instant message that contains a hyperlink.</span></span>

<span data-ttu-id="c5dd8-115">두 번째 필터링 옵션은 수정 되지 않은 하이퍼링크로 인스턴트 메시지를 허용 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="c5dd8-115">A second filtering option is to allow instant messages with unmodified hyperlinks.</span></span> <span data-ttu-id="c5dd8-116">이 옵션을 선택 하면 각 메시지에 삽입 된 사용자에 게 경고를 작성 하는 추가 옵션 (권장)이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5dd8-116">If you choose this option, you have the additional option (recommended) of composing a warning to users that is inserted in each message.</span></span>

<span data-ttu-id="c5dd8-117">세 번째 옵션은 하이퍼링크가 포함 된 모든 인스턴트 메시지를 차단 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="c5dd8-117">A third option is to block all instant messages that contain hyperlinks.</span></span> <span data-ttu-id="c5dd8-118">이 옵션을 선택 하면 서버는 사용자에 게 경고를 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="c5dd8-118">If you choose this option, the server sends a warning to the user.</span></span> <span data-ttu-id="c5dd8-119">이 경고를 작성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5dd8-119">You must write this warning.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

