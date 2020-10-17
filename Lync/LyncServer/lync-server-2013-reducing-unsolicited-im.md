---
title: 'Lync Server 2013: 원하지 않는 IM 줄이기'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Reducing unsolicited IM for Lync Server 2013
ms:assetid: d2998708-e699-4465-a918-e1d9ea4c49c3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn518335(v=OCS.15)
ms:contentKeyID: 62625493
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6e6b3b720e5c05051cd556af7d32e8293e95c315
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48512015"
---
# <a name="reducing-unsolicited-im-for-lync-server-2013"></a><span data-ttu-id="31ec1-102">Lync Server 2013에 대 한 원하지 않는 IM 줄이기</span><span class="sxs-lookup"><span data-stu-id="31ec1-102">Reducing unsolicited IM for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="31ec1-103">_**마지막으로 수정 된 항목:** 2013-12-05_</span><span class="sxs-lookup"><span data-stu-id="31ec1-103">_**Topic Last Modified:** 2013-12-05_</span></span>

<span data-ttu-id="31ec1-104">지능형 IM 필터 응용 프로그램은 사용자 환경을 최소화 하면서 가장 일반적인 바이러스에 대해 Microsoft Lync Server 2013 배포를 보호 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="31ec1-104">The Intelligent IM Filter application helps protect your Microsoft Lync Server 2013 deployment against the most common viruses with minimal degradation to the user experience.</span></span> <span data-ttu-id="31ec1-105">지능형 IM 필터는 다음과 같은 기능을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="31ec1-105">The Intelligent IM Filter provides the following:</span></span>

  - <span data-ttu-id="31ec1-106">향상 된 URL 필터링</span><span class="sxs-lookup"><span data-stu-id="31ec1-106">Enhanced URL filtering</span></span>

  - <span data-ttu-id="31ec1-107">향상 된 파일 전송 필터링</span><span class="sxs-lookup"><span data-stu-id="31ec1-107">Enhanced file transfer filtering</span></span>

<span data-ttu-id="31ec1-108">지능형 IM 필터를 사용하면 회사 방화벽 외부의 알 수 없는 끝점에서 보낸 잠재적으로 유해하거나 원치 않는 인스턴트 메시지를 차단하도록 필터를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="31ec1-108">Use Intelligent IM Filter to configure filters to block unsolicited or potentially harmful instant messages from unknown endpoints outside the corporate firewall.</span></span> <span data-ttu-id="31ec1-109">차단 해야 하는 작업을 결정 하는 데 사용할 기준을 지정 하 여 필터를 구성할 수 있습니다 (예: 하이퍼링크를 포함 하는 인스턴트 메시지 및 특정 확장명을 가진 파일).</span><span class="sxs-lookup"><span data-stu-id="31ec1-109">You configure filters by specifying the criteria to be used to determine what should be blocked, such as instant messages containing hyperlinks and files with specific extensions.</span></span>

<span data-ttu-id="31ec1-110">지능형 IM 메시지 필터 응용 프로그램을 배포 하기 전에 메시지가 Lync Server 2013 서버 간에 라우팅되는 경우 필터링 옵션을 적용 하는 방법을 이해 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="31ec1-110">Before you deploy the Intelligent IM Message Filter application, you should understand how filtering options are applied when messages are routed from one Lync Server 2013 server to another.</span></span> <span data-ttu-id="31ec1-111">필터링 옵션이 적용되는 방식은 두 서버가 같은 조직에 있는지 또는 서로 다른 조직에 있는지에 관계없이 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="31ec1-111">The way these filtering options are applied is consistent, regardless of whether the servers are located in a single organization or across organizational boundaries.</span></span> <span data-ttu-id="31ec1-112">이 일관성은 사용자 지정 된 알림 및 경고 텍스트가 메시지에 삽입 되 고 서버 간에 전송 되는 방식에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="31ec1-112">This consistency applies to the way that the customized notice, and warning texts are inserted into messages and sent across servers.</span></span>

<span data-ttu-id="31ec1-113">하이퍼링크를 포함 하는 인스턴트 메시지를 허용 하 되, 지능형 IM 필터를 사용 하려면 먼저 밑줄을 삽입 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="31ec1-113">The recommended filtering option is to allow instant messages with hyperlinks but require the Intelligent IM Filter to disable the link by inserting an underscore before it.</span></span> <span data-ttu-id="31ec1-114">이 옵션을 선택 하면 하이퍼링크를 포함 하는 각 인스턴트 메시지의 시작 부분에 표시 되는 사용자에 게 공지를 작성할 수 있는 추가 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="31ec1-114">If you choose this option, you have the additional option of composing a notice to users that appears at the beginning of each instant message that contains a hyperlink.</span></span>

<span data-ttu-id="31ec1-115">두 번째 필터링 옵션은 수정 되지 않은 하이퍼링크가 있는 인스턴트 메시지를 허용 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="31ec1-115">A second filtering option is to allow instant messages with unmodified hyperlinks.</span></span> <span data-ttu-id="31ec1-116">이 옵션을 선택 하면 각 메시지에 삽입 된 사용자에 게 경고를 작성할 수 있는 추가 옵션인 (권장) 옵션이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="31ec1-116">If you choose this option, you have the additional option (recommended) of composing a warning to users that is inserted in each message.</span></span>

<span data-ttu-id="31ec1-117">세 번째 옵션은 하이퍼링크를 포함 하는 모든 인스턴트 메시지를 차단 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="31ec1-117">A third option is to block all instant messages that contain hyperlinks.</span></span> <span data-ttu-id="31ec1-118">이 옵션을 선택 하면 서버가 사용자에 게 경고를 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="31ec1-118">If you choose this option, the server sends a warning to the user.</span></span> <span data-ttu-id="31ec1-119">이 경고를 작성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="31ec1-119">You must write this warning.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

