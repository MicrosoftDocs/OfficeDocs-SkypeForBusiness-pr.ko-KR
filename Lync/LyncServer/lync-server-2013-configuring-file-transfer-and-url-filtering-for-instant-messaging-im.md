---
title: IM (인스턴트 메시징)에 대 한 파일 전송 및 URL 필터링 구성
description: IM (인스턴트 메시징)에 대 한 파일 전송 및 URL 필터링 구성
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring file transfer and URL filtering for instant messaging (IM)
ms:assetid: 115a1a2c-599f-474c-a063-52f7144b5246
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520952(v=OCS.15)
ms:contentKeyID: 48183440
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 92f11c3f3bb924c1d92361c2635bfb37e1f03175
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48548354"
---
# <a name="configuring-file-transfer-and-url-filtering-for-instant-messaging-im-in-lync-server-2013"></a><span data-ttu-id="6f3ac-103">Lync Server 2013에서 IM (인스턴트 메시징)에 대 한 파일 전송 및 URL 필터링 구성</span><span class="sxs-lookup"><span data-stu-id="6f3ac-103">Configuring file transfer and URL filtering for instant messaging (IM) in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6f3ac-104">_**마지막으로 수정 된 항목:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="6f3ac-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="6f3ac-105">지능형 IM 필터 도구는 사용자 환경에 대 한 성능 저하를 최소화 하면서 가장 일반적인 형태의 바이러스 확산을 방지 하기 위해 Lync Server 2013 배포를 보호 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6f3ac-105">The Intelligent IM Filter tool helps protect your Lync Server 2013 deployment against the spread of the most common forms of viruses with minimal degradation to the user experience.</span></span> <span data-ttu-id="6f3ac-106">지능형 IM 필터를 사용하면 회사 방화벽 외부의 알 수 없는 끝점에서 보낸 잠재적으로 유해하거나 원치 않는 인스턴트 메시지를 차단하도록 필터를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6f3ac-106">Use Intelligent IM Filter to configure filters to block unsolicited or potentially harmful instant messages from unknown endpoints outside the corporate firewall.</span></span> <span data-ttu-id="6f3ac-107">특정 접두사가 포함된 하이퍼링크를 포함하는 인스턴트 메시지 및 특정 확장명의 파일과 같은 차단할 항목을 결정하는 데 사용할 조건을 지정하여 필터를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="6f3ac-107">You configure filters by specifying the criteria to be used to determine what should be blocked, such as instant messages containing hyperlinks with specific prefixes and files with specific extensions.</span></span>

<span data-ttu-id="6f3ac-108">지능형 IM 필터는 다음과 같은 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="6f3ac-108">Intelligent IM Filter provides the following:</span></span>

  - <span data-ttu-id="6f3ac-109">향상된 URL 필터링</span><span class="sxs-lookup"><span data-stu-id="6f3ac-109">Enhanced URL filtering.</span></span>

  - <span data-ttu-id="6f3ac-110">향상된 파일 전송 필터링</span><span class="sxs-lookup"><span data-stu-id="6f3ac-110">Enhanced file transfer filtering.</span></span>

<span data-ttu-id="6f3ac-111">지능형 IM 필터 구성에는 다음이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="6f3ac-111">Configuring Intelligent IM Filter includes the following:</span></span>

  - <span data-ttu-id="6f3ac-112">URL 필터링 구성</span><span class="sxs-lookup"><span data-stu-id="6f3ac-112">Configuring URL filtering.</span></span>

  - <span data-ttu-id="6f3ac-113">파일 전송 필터링 구성</span><span class="sxs-lookup"><span data-stu-id="6f3ac-113">Configuring file transfer filtering.</span></span>

<div>

## <a name="how-filtering-options-are-applied-to-instant-messages"></a><span data-ttu-id="6f3ac-114">필터링 옵션을 인스턴트 메시지에 적용하는 방법</span><span class="sxs-lookup"><span data-stu-id="6f3ac-114">How Filtering Options Are Applied to Instant Messages</span></span>

<span data-ttu-id="6f3ac-115">지능형 IM 메시지 필터 도구를 배포 하기 전에 메시지가 Lync Server 2013 서버 간에 라우팅되는 방식으로 필터링 옵션을 적용 하는 방법을 이해 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f3ac-115">Before you deploy the Intelligent IM Message Filter tool, you need to understand how filtering options are applied as messages are routed from one Lync Server 2013 server to another.</span></span> <span data-ttu-id="6f3ac-116">필터링 옵션이 적용되는 방식은 두 서버가 같은 조직에 있는지 또는 서로 다른 조직에 있는지에 관계없이 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="6f3ac-116">The way these filtering options are applied is consistent, regardless of whether the servers are located in a single organization or across organizational boundaries.</span></span> <span data-ttu-id="6f3ac-117">이러한 일관성은 사용자 지정 공지 사항이나 경고 텍스트가 메시지에 삽입되고 서버 간에 전송되는 방식에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="6f3ac-117">This consistency applies to the way that the customized notice and warning texts are inserted into messages and sent across servers.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="6f3ac-118">인스턴트 메시지 필터를 사용할 경우 메시지의 URL을 처리하는 데 필요한 CPU 리소스 양이 늘어납니다.</span><span class="sxs-lookup"><span data-stu-id="6f3ac-118">The instant message filter increases the amount of CPU resources required to process URLs in a message.</span></span> <span data-ttu-id="6f3ac-119">이러한 CPU 수요 증가는 Lync Server의 성능에도 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6f3ac-119">This increase in CPU demand also affects the performance of Lync Server.</span></span>



</div>

<span data-ttu-id="6f3ac-120">Lync Server 제어판의 **IM 및 현재 상태** 그룹에 있는 **URL 필터** 페이지를 사용 하 여 하이퍼링크 일부 또는 전체를 차단 하거나 경고를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6f3ac-120">By using the **URL Filter** page in the **IM and Presence** group in Lync Server Control Panel, you can block some or all hyperlinks or configure a warning.</span></span> <span data-ttu-id="6f3ac-121">**하이퍼링크 접두사** 옵션 **경고 메시지 보내기**를 선택하면 하이퍼링크가 포함된 인스턴트 메시지의 시작 부분에 경고가 삽입됩니다.</span><span class="sxs-lookup"><span data-stu-id="6f3ac-121">The warning is inserted at the beginning of an instant message that contains a hyperlink when you choose the **Hyperlink prefix** option **Send warning message**.</span></span>

<span data-ttu-id="6f3ac-122">인스턴트 메시지가 서버 간에 전송될 때 다음과 같은 일반적인 지침이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="6f3ac-122">When an instant message travels from one server to another, the following general guidelines apply:</span></span>

  - <span data-ttu-id="6f3ac-p105">**URL 필터** 페이지에서 **파일 확장명이 있는 URL 차단** 확인란을 선택하거나 **하이퍼링크 접두사** 옵션 **하이퍼링크 차단**을 선택하여 서버에서 인스턴트 메시지를 차단하는 경우 오류 메시지가 클라이언트에 반환됩니다. 그러면 후속 서버에서 이 인스턴트 메시지를 받지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6f3ac-p105">If a server blocks an instant message (because you selected the **Block URLs with file extension** check box on the **URL Filter** page or because you chose the **Hyperlink prefix** option **Block hyperlinks**), an error message is returned to the client. Subsequent servers do not receive this instant message.</span></span>

  - <span data-ttu-id="6f3ac-p106">서버(서버 1)에서 활성 하이퍼링크가 포함된 인스턴트 메시지에 경고를 추가한 경우 이 인스턴트 메시지를 받는 후속 서버(서버 2)에서는 인스턴트 메시지에 있는 이 활성 하이퍼링크를 기반으로 다른 작업을 계속 수행할 수 있으며 인스턴트 메시지를 차단하거나 경고를 추가할 수 있습니다. 서버 2가 이 URL에 대한 경고를 추가하도록만 구성된 경우에는 서버 1에서 추가한 이전 경고가 제거되고 서버 2에 구성된 경고가 인스턴트 메시지 시작 부분에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="6f3ac-p106">If a server (Server1) adds a warning to an instant message that contains an active hyperlink, a subsequent server (Server2) that receives this instant message can still take a different action based on this active hyperlink present in the instant message and block the instant message or add a warning. If Server2 is configured only to add a warning for this URL, the earlier warning added by Server1 is removed, and the warning configured on Server2 is added to the beginning of the instant message.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="6f3ac-127">혼합 환경에서 Lync Server 2013을 실행 하는 경우에는 지능형 IM 필터 응용 프로그램을 사용 하는 데 필요한 최소 버전은 s p 1이 포함 된 Live Communications Server 2005입니다.</span><span class="sxs-lookup"><span data-stu-id="6f3ac-127">If you are running Lync Server 2013 in a mixed environment, Live Communications Server 2005 with SP1 is the minimum version required to use the Intelligent IM Filter application.</span></span> <span data-ttu-id="6f3ac-128">SP1이 없는 Live Communications Server 2005에서는 지능형 IM 필터가 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6f3ac-128">The Intelligent IM Filter is not supported on Live Communications Server 2005 without SP1.</span></span>



</div>

<div>

## <a name="url-filtering"></a><span data-ttu-id="6f3ac-129">URL 필터링</span><span class="sxs-lookup"><span data-stu-id="6f3ac-129">URL Filtering</span></span>

<span data-ttu-id="6f3ac-p108">URL은 해당 하이퍼링크 접두사에 따라 필터링됩니다. 다음은 유효한 접두사의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="6f3ac-p108">URLs are filtered according to their hyperlink prefix. The following examples are valid prefixes:</span></span>

  - <span data-ttu-id="6f3ac-132">www \* .</span><span class="sxs-lookup"><span data-stu-id="6f3ac-132">www\*.</span></span>

  - <span data-ttu-id="6f3ac-133">ftp.</span><span class="sxs-lookup"><span data-stu-id="6f3ac-133">ftp.</span></span>

  - <span data-ttu-id="6f3ac-134">http</span><span class="sxs-lookup"><span data-stu-id="6f3ac-134">http:</span></span>

<span data-ttu-id="6f3ac-p109">URL 필터링을 수행하도록 인스턴트 메시지 필터를 구성하지 않은 경우 인스턴트 메시지에 포함된 모든 URL이 수정되지 않은 상태로 서버를 통해 전달됩니다. URL 필터링을 수행하도록 인스턴트 메시지 필터를 구성한 경우에는 **URL 필터 편집** 또는 **새 URL 필터** 대화 상자에서 선택한 옵션에 따라 인스턴트 메시지의 URL이 필터링됩니다.</span><span class="sxs-lookup"><span data-stu-id="6f3ac-p109">If you do not configure the instant message filter to perform any URL filtering, all URLs contained in instant messages are passed unmodified through the server. If you configure the instant message filter to perform URL filtering, URLs in instant messages are filtered according to the options that you select in the **Edit URL Filter** or **New URL Filter** dialog box.</span></span>

  - <span data-ttu-id="6f3ac-137">**URL 필터 사용**     이 옵션은 전역 배포 또는 선택한 사이트에 URL 필터링을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f3ac-137">**Enable URL filter**   This option enables URL filtering for the global deployment or for the site that you select.</span></span>

  - <span data-ttu-id="6f3ac-138">**파일 확장명**     을 사용 하 여 url 차단 인스턴트 메시지 필터는 파일 **형식 확장명** 에 나열 된 확장명을 가진 파일을 포함 하는 모든 활성 인트라넷 또는 인터넷 URL을 블록 **편집** 대화 상자에 차단 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f3ac-138">**Block URLs with file extension**   The instant message filter blocks any active intranet or Internet URL that contains a file with an extension listed under **File type extensions to block** in the **Edit File Filter** dialog box.</span></span> <span data-ttu-id="6f3ac-139">URL이 차단 되 면 보낸 사람에 게 오류 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6f3ac-139">When a URL is blocked, an error message is displayed to the sender.</span></span> <span data-ttu-id="6f3ac-140">이 옵션을 선택 하면 **파일 형식 확장명**에 정의 된 모든 파일 확장명에 대해 block으로 사용 되는 모든 필터링 옵션 보다 우선 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f3ac-140">When selected, this option takes precedence over all other filtering options for any file extensions defined under **File type extensions to block**.</span></span>
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="6f3ac-p111">표준 파일 이름의 파일 확장명만 필터링할 수 있습니다. 다른 이름에 포함된 파일 확장명에는 필터링이 적용되지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6f3ac-p111">Filtering of file extensions is limited to standard file names. Filtering may not work with file extensions embedded in other names.</span></span>

    
    </div>

<span data-ttu-id="6f3ac-143">인스턴트 메시지 대화에서 하이퍼링크가 처리되는 방식을 구성하려면 **하이퍼링크 접두사** 아래에서 다음 옵션 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6f3ac-143">To configure how hyperlinks are handled in instant message conversations, select one of the following options under **Hyperlink prefix**:</span></span>

  - <span data-ttu-id="6f3ac-144">**필터링**     안 함 메시지의 Url은 서버를 통해 전송 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6f3ac-144">**Do not filter**   URLs in messages are sent through the server.</span></span> <span data-ttu-id="6f3ac-145">이 옵션을 선택 하면 **허용 메시지** 상자가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="6f3ac-145">When you choose this option, the **Allow message** box appears.</span></span> <span data-ttu-id="6f3ac-146">**허용 메시지** 상자에서 하이퍼링크를 포함 하는 각 인스턴트 메시지의 시작 부분에 삽입 하려는 알림을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f3ac-146">In the **Allow message** box, specify the notice that you want to insert at the beginning of each instant message containing hyperlinks.</span></span> <span data-ttu-id="6f3ac-147">이 메시지는 최대 65535 자까지 구성 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6f3ac-147">This notice can consist of no more than 65535 characters.</span></span>

  - <span data-ttu-id="6f3ac-148">**하이퍼링크 차단**     액티브 하이퍼링크를 포함 하는 인스턴트 메시지 배달은 Lync Server에 의해 차단 되며 보낸 사람에 게 오류 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6f3ac-148">**Block hyperlinks**   Delivery of instant messages containing active hyperlinks is blocked by Lync Server, and an error message is displayed to the sender.</span></span>

  - <span data-ttu-id="6f3ac-149">**경고 메시지 보내기**     Lync Server에서는 인스턴트 메시지에 대 한 활성 하이퍼링크를 허용 하지만 경고는 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6f3ac-149">**Send warning message**   Lync Server permits active hyperlinks in instant messages, but it includes a warning.</span></span> <span data-ttu-id="6f3ac-150">이 옵션을 선택하면 **경고 메시지** 상자가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="6f3ac-150">When you choose this option, the **Warning message** box appears.</span></span> <span data-ttu-id="6f3ac-151">**경고 메시지** 상자에 유효한 하이퍼링크가 포함된 인스턴트 메시지에 포함할 경고를 입력해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f3ac-151">In the **Warning message** box, you must type the warning that you want to include with instant messages containing valid hyperlinks.</span></span> <span data-ttu-id="6f3ac-152">예를 들어 이 경고는 알 수 없는 링크를 클릭할 경우의 잠재적 위험을 알리거나 조직의 관련 정책 및 요구 사항을 나타낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6f3ac-152">For example, this warning might state the potential dangers of clicking an unknown link, or it might refer to your organization’s relevant policies and requirements.</span></span> <span data-ttu-id="6f3ac-153">경고는 최대 65535자까지 가능합니다.</span><span class="sxs-lookup"><span data-stu-id="6f3ac-153">The warning can be no more than 65535 characters.</span></span>

<span data-ttu-id="6f3ac-154">**하이퍼링크 차단** 또는 **경고 메시지 보내기**를 선택한 경우 다음 옵션을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6f3ac-154">If you select **Block hyperlinks** or **Send warning message**, the following options are available:</span></span>

  - <span data-ttu-id="6f3ac-155">**로컬 인트라넷 하이퍼링크 제외**     인스턴트 메시지 필터는 인터넷 Url만 차단 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f3ac-155">**Exclude local intranet hyperlinks**   The instant message filter blocks only Internet URLs.</span></span> <span data-ttu-id="6f3ac-156">인트라넷 내의 위치에 대 한 Url은 수정 되지 않은 상태로 서버를 통해 전달 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6f3ac-156">URLs for locations within your intranet are passed unmodified through the server.</span></span> <span data-ttu-id="6f3ac-157">그러나 Lync Server 통과를 실행 하는 개별 서버에 대 한 인트라넷 Url은 인트라넷 영역의 일부분으로 간주 되는 로컬 웹 사이트 유형에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="6f3ac-157">However, the intranet URLs that individual servers running Lync Server pass depend on which types of local websites are considered part of their intranet zone.</span></span> <span data-ttu-id="6f3ac-158">서버의 인트라넷 영역 설정을 확인 하려면 [Modify the DEFAULT URL filter in The Lync server 2013](lync-server-2013-modify-the-default-url-filter.md)의 "Internet Explorer에서 인트라넷 설정을 구성 하려면" 절차를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="6f3ac-158">To check a server’s intranet zone settings, see the “To configure your intranet settings in Internet Explorer” procedure in [Modify the default URL filter in Lync Server 2013](lync-server-2013-modify-the-default-url-filter.md).</span></span>

  - <span data-ttu-id="6f3ac-159">**이러한 하이퍼링크 접두사 필터링**     차단할 접두사를 선택 하려면 **선택을**클릭 한 다음 **하이퍼링크 접두사 선택**에서 **하이퍼링크 접두사** 목록에 접두사를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f3ac-159">**Filter these hyperlink prefixes**   To choose which prefixes you want to block, click **Select**, and then, in **Select Hyperlink Prefix**, add the prefixes to the **Hyperlink prefixes** list.</span></span>
    
    <span data-ttu-id="6f3ac-160">**href**를 제외한 모든 접두사는 마침표나 콜론 또는 뒤에 마침표가 오는 별표로 끝나야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f3ac-160">All prefixes except **href** must end with a period or a colon, or an asterisk followed by a period.</span></span> <span data-ttu-id="6f3ac-161">유효한 접두사는 별표 ()를 제외한 유효한 URL 문자 집합에 있는 모든 문자를 포함할 수 있습니다 \* .</span><span class="sxs-lookup"><span data-stu-id="6f3ac-161">Valid prefixes can contain any characters in the set of valid URL characters except the asterisk (\*).</span></span> <span data-ttu-id="6f3ac-162">유효한 URL 문자 집합은 \# \* +/0123456789 = @ABCDEFGHIJKLMNOPQRSTUVWXYZ ^ \_ \` ABCDEFGHIJKLMNOPQRSTUVWXYZ | ~입니다.</span><span class="sxs-lookup"><span data-stu-id="6f3ac-162">The set of valid URL characters is: \#\*+/0123456789=@ABCDEFGHIJKLMNOPQRSTUVWXYZ^\_\` abcdefghijklmnopqrstuvwxyz|~</span></span>

</div>

<div>

## <a name="file-transfer-filtering"></a><span data-ttu-id="6f3ac-163">파일 전송 필터링</span><span class="sxs-lookup"><span data-stu-id="6f3ac-163">File Transfer Filtering</span></span>

<span data-ttu-id="6f3ac-p116">파일 전송 필터링은 인스턴트 메시지와 전화 회의 둘 다에 영향을 줍니다. 전화 회의 경우 이러한 설정은 Office Live Meeting 2007 클라이언트의 참고 파일 기능 및 멀티미디어 재생 기능에 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6f3ac-p116">Filter transfer filtering affects both instant messages and conferences. For conferences, these settings affect the handout feature in the Office Live Meeting 2007 client and multimedia playback features.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="6f3ac-166">또한 Lync Server에서는 파일 전송 설정 옵션도 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f3ac-166">Lync Server also offers file transfer setting options.</span></span> <span data-ttu-id="6f3ac-167">이 서버 쪽 옵션은 Lync Server에서 사용할 수 있는 클라이언트 쪽 컨트롤과 함께 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6f3ac-167">This server-side option is offered in addition to the client-side controls available in Lync Server.</span></span>



</div>

<span data-ttu-id="6f3ac-p118">인스턴트 메시지 대화 중에, Office Live Meeting 2007 클라이언트에서 참고 파일 기능을 사용할 때, 그리고 모든 파일 형식의 멀티미디어 재생 기능에 대해 파일 전송을 필터링할 수 있습니다. 다음 옵션을 설정하여 파일 전송을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6f3ac-p118">You can filter file transfers during instant message conversations, when you are using the handout feature in the Office Live Meeting 2007 client, and for multimedia playback features for all file types. You can set the following options to control file transfers:</span></span>

  - <span data-ttu-id="6f3ac-170">**파일 필터 사용**     이 옵션은 전역 배포 또는 선택한 사이트에 대해 파일 필터링을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f3ac-170">**Enable file filter**   This option enables file filtering for the global deployment or for the site that you select.</span></span>
    
    <span data-ttu-id="6f3ac-171">파일 필터를 사용하도록 선택한 경우 **파일 전송**에서 다음 옵션 중 하나를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6f3ac-171">When you enable the file filter, you can choose one of the following options in **File transfer**:</span></span>
    
      - <span data-ttu-id="6f3ac-172">**특정 파일 형식 차단**     차단할 파일 확장명 목록을 지정 하 여 서버에 의해 필터링 되는 파일 전송 요청을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f3ac-172">**Block specific file types**   You specify which file transfer requests are filtered by the server by specifying a list of file extensions to block.</span></span> <span data-ttu-id="6f3ac-173">목록의 항목에는 와일드 카드 문자 ()가 아니라 모든 표준 문자를 포함할 수 있습니다 \* .</span><span class="sxs-lookup"><span data-stu-id="6f3ac-173">Entries in the list can contain all standard characters, but not the wildcard character (\*).</span></span> <span data-ttu-id="6f3ac-174">Office Live Meeting 2007 클라이언트에서 유인물 기능을 사용할 수 있지만이 확장명을 포함 하는 모든 파일을 업로드 하거나 다운로드할 수도 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6f3ac-174">In the Office Live Meeting 2007 client the handout feature is enabled, but any file with this extension cannot be uploaded or downloaded.</span></span> <span data-ttu-id="6f3ac-175">**Url 필터** 탭에 나열 된 url 필터에 대 한 설정에서 **파일 확장명으로 url 차단** 확인란을 선택한 경우 url 필터는이 목록에서 이러한 확장명을 포함 하는 활성 하이퍼링크를 차단 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f3ac-175">If you select the **Block URLs with file extension** check box on the settings for a URL filter listed on the **URL Filter** tab, the URL filter uses this same list to block active hyperlinks that contain any of these file extensions.</span></span> <span data-ttu-id="6f3ac-176">차단할 파일 형식을 선택 하려면 **선택을**클릭 하 고 **파일 형식 선택**에서 **선택한 파일 형식 확장명** 목록에 파일 형식 확장명을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f3ac-176">To choose which file types you want to block, click **Select**, and then, in **Select File Type**, add the file type extensions to the **Selected file type extensions** list.</span></span>
    
      - <span data-ttu-id="6f3ac-177">**모두 차단**     서버는 파일 전송 요청을 포함 하는 모든 인스턴트 메시지를 삭제 하 고 요청을 보낸 사람에 게 오류 메시지를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f3ac-177">**Block All**   The server drops all instant messages that contain file transfer requests and returns an error message to the sender of the request.</span></span> <span data-ttu-id="6f3ac-178">Office Live Meeting 2007 클라이언트의 유인물 기능이 사용 하지 않도록 설정 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6f3ac-178">The handout feature in the Office Live Meeting 2007 client is disabled.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="6f3ac-p121">표준 파일 이름의 파일 확장명만 필터링할 수 있습니다. 다른 이름에 포함된 파일 확장명에는 필터링이 적용되지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6f3ac-p121">Filtering of file extensions is limited to standard file names. Filtering may not work with file extensions embedded in other names.</span></span>



</div>

</div>

</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="6f3ac-181">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="6f3ac-181">In This Section</span></span>

  - [<span data-ttu-id="6f3ac-182">Lync Server 2013에서 기본 파일 전송 필터 수정</span><span class="sxs-lookup"><span data-stu-id="6f3ac-182">Modify the default file transfer filter in Lync Server 2013</span></span>](lync-server-2013-modify-the-default-file-transfer-filter.md)

  - [<span data-ttu-id="6f3ac-183">특정 사이트에 대해 Lync Server 2013에서 새 파일 전송 필터 만들기</span><span class="sxs-lookup"><span data-stu-id="6f3ac-183">Create a new file transfer filter in Lync Server 2013 for a specific site</span></span>](lync-server-2013-create-a-new-file-transfer-filter-for-a-specific-site.md)

  - [<span data-ttu-id="6f3ac-184">Lync Server 2013의 기본 URL 필터 수정</span><span class="sxs-lookup"><span data-stu-id="6f3ac-184">Modify the default URL filter in Lync Server 2013</span></span>](lync-server-2013-modify-the-default-url-filter.md)

  - [<span data-ttu-id="6f3ac-185">Lync Server 2013에서 새 URL 필터 만들기 IM 대화의 하이퍼링크를 처리 하려면</span><span class="sxs-lookup"><span data-stu-id="6f3ac-185">Create a new URL filter in Lync Server 2013 to handle hyperlinks in IM conversations</span></span>](lync-server-2013-create-a-new-url-filter-to-handle-hyperlinks-in-im-conversations.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="6f3ac-186">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6f3ac-186">See Also</span></span>


[<span data-ttu-id="6f3ac-187">Lync Server 2013에서 IM 및 현재 상태 설정 관리</span><span class="sxs-lookup"><span data-stu-id="6f3ac-187">Managing IM and presence settings in Lync Server 2013</span></span>](lync-server-2013-managing-im-and-presence-settings.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

