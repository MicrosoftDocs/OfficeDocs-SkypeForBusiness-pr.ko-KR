---
title: IM (인스턴트 메시징)에 대 한 파일 전송 및 URL 필터링 구성
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring file transfer and URL filtering for instant messaging (IM)
ms:assetid: 115a1a2c-599f-474c-a063-52f7144b5246
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520952(v=OCS.15)
ms:contentKeyID: 48183440
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 97a9e39799815a86bc255b9aa58627df94eb3f81
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40983687"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-file-transfer-and-url-filtering-for-instant-messaging-im-in-lync-server-2013"></a><span data-ttu-id="b7aff-102">Lync Server 2013에서 IM (인스턴트 메시징)에 대 한 파일 전송 및 URL 필터링 구성</span><span class="sxs-lookup"><span data-stu-id="b7aff-102">Configuring file transfer and URL filtering for instant messaging (IM) in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b7aff-103">_**마지막으로 수정한 주제:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="b7aff-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="b7aff-104">지능형 IM 필터 도구는 사용자 환경에 대 한 성능 저하를 최소화 하 여 Lync Server 2013 배포를 가장 일반적인 바이러스 형태의 확산 으로부터 보호 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7aff-104">The Intelligent IM Filter tool helps protect your Lync Server 2013 deployment against the spread of the most common forms of viruses with minimal degradation to the user experience.</span></span> <span data-ttu-id="b7aff-105">지능형 IM 필터를 사용 하 여 필터를 구성 하 여 회사 방화벽 외부의 알 수 없는 끝점에서 원하지 않거나 위험한 인스턴트 메시지를 차단 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7aff-105">Use Intelligent IM Filter to configure filters to block unsolicited or potentially harmful instant messages from unknown endpoints outside the corporate firewall.</span></span> <span data-ttu-id="b7aff-106">특정 접두 번호와 특정 확장명의 파일에 대 한 하이퍼링크를 포함 하는 인스턴트 메시지와 같이 차단 되어야 하는 항목을 결정 하는 데 사용할 조건을 지정 하 여 필터를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7aff-106">You configure filters by specifying the criteria to be used to determine what should be blocked, such as instant messages containing hyperlinks with specific prefixes and files with specific extensions.</span></span>

<span data-ttu-id="b7aff-107">지능형 IM 필터는 다음을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7aff-107">Intelligent IM Filter provides the following:</span></span>

  - <span data-ttu-id="b7aff-108">향상 된 URL 필터링.</span><span class="sxs-lookup"><span data-stu-id="b7aff-108">Enhanced URL filtering.</span></span>

  - <span data-ttu-id="b7aff-109">향상 된 파일 전송 필터링.</span><span class="sxs-lookup"><span data-stu-id="b7aff-109">Enhanced file transfer filtering.</span></span>

<span data-ttu-id="b7aff-110">지능형 IM 필터 구성에는 다음이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7aff-110">Configuring Intelligent IM Filter includes the following:</span></span>

  - <span data-ttu-id="b7aff-111">URL 필터링 구성</span><span class="sxs-lookup"><span data-stu-id="b7aff-111">Configuring URL filtering.</span></span>

  - <span data-ttu-id="b7aff-112">파일 전송 필터링 구성</span><span class="sxs-lookup"><span data-stu-id="b7aff-112">Configuring file transfer filtering.</span></span>

<div>

## <a name="how-filtering-options-are-applied-to-instant-messages"></a><span data-ttu-id="b7aff-113">인스턴트 메시지에 필터링 옵션을 적용 하는 방법</span><span class="sxs-lookup"><span data-stu-id="b7aff-113">How Filtering Options Are Applied to Instant Messages</span></span>

<span data-ttu-id="b7aff-114">지능형 IM 메시지 필터 도구를 배포 하기 전에 메시지가 하나의 Lync Server 2013 서버에서 다른 사용자에 게 라우팅될 때 필터링 옵션이 적용 되는 방식을 이해 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7aff-114">Before you deploy the Intelligent IM Message Filter tool, you need to understand how filtering options are applied as messages are routed from one Lync Server 2013 server to another.</span></span> <span data-ttu-id="b7aff-115">이러한 필터링 옵션이 적용 되는 방식에 따라 서버가 단일 조직에 있든 조직 경계를 넘어 지에 관계 없이 일관성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7aff-115">The way these filtering options are applied is consistent, regardless of whether the servers are located in a single organization or across organizational boundaries.</span></span> <span data-ttu-id="b7aff-116">이 일관성은 사용자 지정 된 알림 및 경고 텍스트를 메시지에 삽입 하 고 서버에서 보내는 방식에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7aff-116">This consistency applies to the way that the customized notice and warning texts are inserted into messages and sent across servers.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="b7aff-117">인스턴트 메시지 필터는 메시지에서 Url을 처리 하는 데 필요한 CPU 리소스의 양을 늘립니다.</span><span class="sxs-lookup"><span data-stu-id="b7aff-117">The instant message filter increases the amount of CPU resources required to process URLs in a message.</span></span> <span data-ttu-id="b7aff-118">이러한 CPU 수요 증가는 Lync Server의 성능에도 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b7aff-118">This increase in CPU demand also affects the performance of Lync Server.</span></span>



</div>

<span data-ttu-id="b7aff-119">Lync Server 제어판의 **메신저 대화 및 현재 상태** 그룹에 있는 **URL 필터** 페이지를 사용 하 여 일부 또는 전체 하이퍼링크를 차단 하거나 경고를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7aff-119">By using the **URL Filter** page in the **IM and Presence** group in Lync Server Control Panel, you can block some or all hyperlinks or configure a warning.</span></span> <span data-ttu-id="b7aff-120">**하이퍼링크 접두사** 옵션 **보내기 경고 메시지**를 선택 하면 하이퍼링크를 포함 하는 인스턴트 메시지의 시작 부분에 경고가 삽입 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7aff-120">The warning is inserted at the beginning of an instant message that contains a hyperlink when you choose the **Hyperlink prefix** option **Send warning message**.</span></span>

<span data-ttu-id="b7aff-121">인스턴트 메시지가 한 서버에서 다른 서버로 이동 하면 다음과 같은 일반적인 지침이 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7aff-121">When an instant message travels from one server to another, the following general guidelines apply:</span></span>

  - <span data-ttu-id="b7aff-122">서버에서 인스턴트 메시지를 차단 하는 경우 ( **Url 필터** 페이지에서 **파일 확장명으로 url 차단** 확인란을 선택 했거나 **하이퍼링크 접두사** 옵션 **차단 하이퍼링크**를 선택한 경우) 클라이언트에 오류 메시지가 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7aff-122">If a server blocks an instant message (because you selected the **Block URLs with file extension** check box on the **URL Filter** page or because you chose the **Hyperlink prefix** option **Block hyperlinks**), an error message is returned to the client.</span></span> <span data-ttu-id="b7aff-123">이후 서버는이 메신저 대화를 받을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b7aff-123">Subsequent servers do not receive this instant message.</span></span>

  - <span data-ttu-id="b7aff-124">서버 (Server1)가 활성 하이퍼링크를 포함 하는 인스턴트 메시지에 경고를 추가 하는 경우,이 인스턴트 메시지를 수신 하는 후속 서버 (Server2)는 메신저 대화에 표시 된이 활성 하이퍼링크에 따라 다른 작업을 수행 하 고 다음을 차단할 수 있습니다. 인스턴트 메시지를 표시 하거나 경고를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7aff-124">If a server (Server1) adds a warning to an instant message that contains an active hyperlink, a subsequent server (Server2) that receives this instant message can still take a different action based on this active hyperlink present in the instant message and block the instant message or add a warning.</span></span> <span data-ttu-id="b7aff-125">이 URL에 대 한 경고만 추가 하도록 Server2를 구성한 경우 Server1이 추가한 이전의 경고가 제거 되 고, Server2에 구성 된 경고가 인스턴트 메시지의 시작 부분에 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7aff-125">If Server2 is configured only to add a warning for this URL, the earlier warning added by Server1 is removed, and the warning configured on Server2 is added to the beginning of the instant message.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="b7aff-126">혼합 환경에서 Lync Server 2013을 실행 하는 경우 SP1이 포함 된 Live Communications Server 2005는 지능형 IM 필터 응용 프로그램을 사용 하는 데 필요한 최소 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="b7aff-126">If you are running Lync Server 2013 in a mixed environment, Live Communications Server 2005 with SP1 is the minimum version required to use the Intelligent IM Filter application.</span></span> <span data-ttu-id="b7aff-127">지능형 IM 필터는 SP1 없이 실시간 통신 서버 2005에서 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b7aff-127">The Intelligent IM Filter is not supported on Live Communications Server 2005 without SP1.</span></span>



</div>

<div>

## <a name="url-filtering"></a><span data-ttu-id="b7aff-128">URL 필터링</span><span class="sxs-lookup"><span data-stu-id="b7aff-128">URL Filtering</span></span>

<span data-ttu-id="b7aff-129">Url은 해당 하이퍼링크 접두사에 따라 필터링 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7aff-129">URLs are filtered according to their hyperlink prefix.</span></span> <span data-ttu-id="b7aff-130">다음 예는 유효한 접두사입니다.</span><span class="sxs-lookup"><span data-stu-id="b7aff-130">The following examples are valid prefixes:</span></span>

  - <span data-ttu-id="b7aff-131">www\*.</span><span class="sxs-lookup"><span data-stu-id="b7aff-131">www\*.</span></span>

  - <span data-ttu-id="b7aff-132">ftp.</span><span class="sxs-lookup"><span data-stu-id="b7aff-132">ftp.</span></span>

  - <span data-ttu-id="b7aff-133">http</span><span class="sxs-lookup"><span data-stu-id="b7aff-133">http:</span></span>

<span data-ttu-id="b7aff-134">URL 필터링을 수행 하도록 인스턴트 메시지 필터를 구성 하지 않으면 인스턴트 메시지에 포함 된 모든 Url이 서버를 통해 수정 되지 않은 상태로 전달 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7aff-134">If you do not configure the instant message filter to perform any URL filtering, all URLs contained in instant messages are passed unmodified through the server.</span></span> <span data-ttu-id="b7aff-135">URL 필터링을 수행 하도록 인스턴트 메시지 필터를 구성 하면 **Url 편집 필터** 또는 **새 url 필터** 대화 상자에서 선택한 옵션에 따라 인스턴트 메시지의 url이 필터링 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7aff-135">If you configure the instant message filter to perform URL filtering, URLs in instant messages are filtered according to the options that you select in the **Edit URL Filter** or **New URL Filter** dialog box.</span></span>

  - <span data-ttu-id="b7aff-136">**Url 필터**   사용이 옵션은 전역 배포 또는 선택한 사이트에 대 한 URL 필터링을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7aff-136">**Enable URL filter**   This option enables URL filtering for the global deployment or for the site that you select.</span></span>

  - <span data-ttu-id="b7aff-137">**파일 확장명**   을 사용 하 여 url 차단 **메신저 대화 필터는 파일** **형식 확장명** 아래에 확장명이 나열 된 파일을 포함 하는 활성 인트라넷 또는 인터넷 URL을 차단 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7aff-137">**Block URLs with file extension**   The instant message filter blocks any active intranet or Internet URL that contains a file with an extension listed under **File type extensions to block** in the **Edit File Filter** dialog box.</span></span> <span data-ttu-id="b7aff-138">URL이 차단 되 면 보낸 사람에 게 오류 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7aff-138">When a URL is blocked, an error message is displayed to the sender.</span></span> <span data-ttu-id="b7aff-139">이 옵션을 선택 하면 **파일 형식 확장명**아래에 정의 된 모든 파일 확장명에 대해 다른 모든 필터링 옵션 보다 우선적으로 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7aff-139">When selected, this option takes precedence over all other filtering options for any file extensions defined under **File type extensions to block**.</span></span>
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="b7aff-140">파일 확장명 필터링은 표준 파일 이름으로 제한 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7aff-140">Filtering of file extensions is limited to standard file names.</span></span> <span data-ttu-id="b7aff-141">다른 이름에 포함 된 파일 확장명에는 필터링이 작동 하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7aff-141">Filtering may not work with file extensions embedded in other names.</span></span>

    
    </div>

<span data-ttu-id="b7aff-142">인스턴트 메시지 대화에서 하이퍼링크를 처리 하는 방법을 구성 하려면 **하이퍼링크 접두사**에서 다음 옵션 중 하나를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7aff-142">To configure how hyperlinks are handled in instant message conversations, select one of the following options under **Hyperlink prefix**:</span></span>

  - <span data-ttu-id="b7aff-143">\*\*\*\*   메시지의 url을 필터링 하지 마세요. 서버를 통해 전송 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7aff-143">**Do not filter**   URLs in messages are sent through the server.</span></span> <span data-ttu-id="b7aff-144">이 옵션을 선택 하면 **허용 메시지** 상자가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7aff-144">When you choose this option, the **Allow message** box appears.</span></span> <span data-ttu-id="b7aff-145">**허용 메시지** 상자에서 하이퍼링크를 포함 하는 각 인스턴트 메시지의 시작 부분에 삽입할 알림을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7aff-145">In the **Allow message** box, specify the notice that you want to insert at the beginning of each instant message containing hyperlinks.</span></span> <span data-ttu-id="b7aff-146">이 알림 메시지는 65535 자를 초과할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b7aff-146">This notice can consist of no more than 65535 characters.</span></span>

  - <span data-ttu-id="b7aff-147">**블록 하이퍼링크**   액티브 하이퍼링크를 포함 하는 인스턴트 메시지 배달이 Lync Server에 의해 차단 되 고 보낸 사람에 게 오류 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7aff-147">**Block hyperlinks**   Delivery of instant messages containing active hyperlinks is blocked by Lync Server, and an error message is displayed to the sender.</span></span>

  - <span data-ttu-id="b7aff-148">**경고 메시지**   보내기 Lync Server는 인스턴트 메시지에 활성 하이퍼링크를 허용 하지만 경고가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7aff-148">**Send warning message**   Lync Server permits active hyperlinks in instant messages, but it includes a warning.</span></span> <span data-ttu-id="b7aff-149">이 옵션을 선택 하면 **경고 메시지** 상자가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="b7aff-149">When you choose this option, the **Warning message** box appears.</span></span> <span data-ttu-id="b7aff-150">**경고 메시지** 상자에서 유효한 하이퍼링크가 포함 된 인스턴트 메시지에 포함할 경고를 입력 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7aff-150">In the **Warning message** box, you must type the warning that you want to include with instant messages containing valid hyperlinks.</span></span> <span data-ttu-id="b7aff-151">예를 들어이 경고는 알 수 없는 링크를 클릭 했을 때 발생할 수 있는 위험에 대해 명시 하거나 조직의 관련 정책 및 요구 사항을 지칭 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7aff-151">For example, this warning might state the potential dangers of clicking an unknown link, or it might refer to your organization’s relevant policies and requirements.</span></span> <span data-ttu-id="b7aff-152">이 경고는 65535 자를 초과할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b7aff-152">The warning can be no more than 65535 characters.</span></span>

<span data-ttu-id="b7aff-153">**하이퍼링크 차단** 또는 **경고 메시지 보내기를**선택 하면 다음 옵션을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7aff-153">If you select **Block hyperlinks** or **Send warning message**, the following options are available:</span></span>

  - <span data-ttu-id="b7aff-154">**로컬 인트라넷 하이퍼링크**   제외 인스턴트 메시지 필터는 인터넷 url만 차단 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7aff-154">**Exclude local intranet hyperlinks**   The instant message filter blocks only Internet URLs.</span></span> <span data-ttu-id="b7aff-155">인트라넷 내의 위치에 대 한 Url은 서버를 통해 수정 되지 않은 상태로 전달 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7aff-155">URLs for locations within your intranet are passed unmodified through the server.</span></span> <span data-ttu-id="b7aff-156">그러나 Lync Server 통과를 실행 하는 개별 서버에 대 한 인트라넷 Url은 해당 인트라넷 영역의 일부로 간주 되는 로컬 웹 사이트 종류에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="b7aff-156">However, the intranet URLs that individual servers running Lync Server pass depend on which types of local websites are considered part of their intranet zone.</span></span> <span data-ttu-id="b7aff-157">서버의 인트라넷 영역 설정을 확인 하려면 [Lync server 2013의 기본 URL 필터 수정](lync-server-2013-modify-the-default-url-filter.md)에서 "Internet Explorer에서 인트라넷 설정을 구성 하려면" 절차를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b7aff-157">To check a server’s intranet zone settings, see the “To configure your intranet settings in Internet Explorer” procedure in [Modify the default URL filter in Lync Server 2013](lync-server-2013-modify-the-default-url-filter.md).</span></span>

  - <span data-ttu-id="b7aff-158">**이러한 하이퍼링크 접두사**   를 필터링 하 여 차단 하려는 접두 번호를 선택 하 고 **선택을**클릭 한 다음 **하이퍼링크 접두사 선택**에서 **하이퍼링크 접두사** 목록에 접두사를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7aff-158">**Filter these hyperlink prefixes**   To choose which prefixes you want to block, click **Select**, and then, in **Select Hyperlink Prefix**, add the prefixes to the **Hyperlink prefixes** list.</span></span>
    
    <span data-ttu-id="b7aff-159">**Href** 를 제외한 모든 접두사는 마침표 또는 콜론으로 끝나야 하며, 별표 뒤에는 마침표가와 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7aff-159">All prefixes except **href** must end with a period or a colon, or an asterisk followed by a period.</span></span> <span data-ttu-id="b7aff-160">유효한 접두사는 별표 (\*)를 제외한 유효한 URL 문자 집합에 있는 모든 문자를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7aff-160">Valid prefixes can contain any characters in the set of valid URL characters except the asterisk (\*).</span></span> <span data-ttu-id="b7aff-161">유효한 URL 문자 집합: \# \*+/0123456789 = @ABCDEFGHIJKLMNOPQRSTUVWXYZ ^\_ \` ABCDEFGHIJKLMNOPQRSTUVWXYZ | ~</span><span class="sxs-lookup"><span data-stu-id="b7aff-161">The set of valid URL characters is: \#\*+/0123456789=@ABCDEFGHIJKLMNOPQRSTUVWXYZ^\_\` abcdefghijklmnopqrstuvwxyz|~</span></span>

</div>

<div>

## <a name="file-transfer-filtering"></a><span data-ttu-id="b7aff-162">파일 전송 필터링</span><span class="sxs-lookup"><span data-stu-id="b7aff-162">File Transfer Filtering</span></span>

<span data-ttu-id="b7aff-163">필터 전송 필터링은 인스턴트 메시지와 컨퍼런스 모두에 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b7aff-163">Filter transfer filtering affects both instant messages and conferences.</span></span> <span data-ttu-id="b7aff-164">회의를 위해 이러한 설정은 Office Live Meeting 2007 클라이언트 및 멀티미디어 재생 기능의 유인물 기능에 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b7aff-164">For conferences, these settings affect the handout feature in the Office Live Meeting 2007 client and multimedia playback features.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="b7aff-165">Lync 서버는 또한 파일 전송 설정 옵션을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7aff-165">Lync Server also offers file transfer setting options.</span></span> <span data-ttu-id="b7aff-166">이 서버 쪽 옵션이 Lync Server에서 사용할 수 있는 클라이언트측 컨트롤 외에도 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7aff-166">This server-side option is offered in addition to the client-side controls available in Lync Server.</span></span>



</div>

<span data-ttu-id="b7aff-167">인스턴트 메시지 대화 중에는 Office Live Meeting 2007 클라이언트의 유인물 기능을 사용 하는 경우와 모든 파일 형식에 대 한 멀티미디어 재생 기능에 대 한 파일 전송을 필터링 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7aff-167">You can filter file transfers during instant message conversations, when you are using the handout feature in the Office Live Meeting 2007 client, and for multimedia playback features for all file types.</span></span> <span data-ttu-id="b7aff-168">파일 전송을 제어 하는 다음 옵션을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7aff-168">You can set the following options to control file transfers:</span></span>

  - <span data-ttu-id="b7aff-169">**파일 필터**   사용이 옵션은 전역 배포 또는 선택한 사이트에 대 한 파일 필터링을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7aff-169">**Enable file filter**   This option enables file filtering for the global deployment or for the site that you select.</span></span>
    
    <span data-ttu-id="b7aff-170">파일 필터를 사용 하도록 설정 하는 경우 **파일 전송**에서 다음 옵션 중 하나를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7aff-170">When you enable the file filter, you can choose one of the following options in **File transfer**:</span></span>
    
      - <span data-ttu-id="b7aff-171">**특정 파일 형식**   차단 차단할 파일 확장명 목록을 지정 하 여 서버에서 필터링 하는 파일 전송 요청을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7aff-171">**Block specific file types**   You specify which file transfer requests are filtered by the server by specifying a list of file extensions to block.</span></span> <span data-ttu-id="b7aff-172">목록에 있는 항목에는 모든 표준 문자를 포함할 수 있지만 와일드 카드 문자\*()는 포함 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b7aff-172">Entries in the list can contain all standard characters, but not the wildcard character (\*).</span></span> <span data-ttu-id="b7aff-173">Office Live Meeting 2007 클라이언트에서 유인물 기능을 사용할 수 있지만,이 확장명을 가진 모든 파일을 업로드 하거나 다운로드할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b7aff-173">In the Office Live Meeting 2007 client the handout feature is enabled, but any file with this extension cannot be uploaded or downloaded.</span></span> <span data-ttu-id="b7aff-174">**Url** 필터 탭에 나열 된 url 필터의 설정에서 **파일 확장명으로 url 차단** 확인란을 선택 하면 url 필터는 같은 목록을 사용 하 여 이러한 파일 확장명을 포함 하는 활성 하이퍼링크를 차단 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7aff-174">If you select the **Block URLs with file extension** check box on the settings for a URL filter listed on the **URL Filter** tab, the URL filter uses this same list to block active hyperlinks that contain any of these file extensions.</span></span> <span data-ttu-id="b7aff-175">차단 하려는 파일 형식을 선택 하려면 **선택을**클릭 한 다음 **파일 형식 선택**에서 파일 형식 확장명을 **선택한 파일 형식 확장명** 목록에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7aff-175">To choose which file types you want to block, click **Select**, and then, in **Select File Type**, add the file type extensions to the **Selected file type extensions** list.</span></span>
    
      - <span data-ttu-id="b7aff-176">**모든 서버 차단**   파일 전송 요청이 포함 된 모든 인스턴트 메시지를 삭제 하 고 요청을 보낸 사람에 게 오류 메시지를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7aff-176">**Block All**   The server drops all instant messages that contain file transfer requests and returns an error message to the sender of the request.</span></span> <span data-ttu-id="b7aff-177">Office Live Meeting 2007 클라이언트의 유인물 기능을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b7aff-177">The handout feature in the Office Live Meeting 2007 client is disabled.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="b7aff-178">파일 확장명 필터링은 표준 파일 이름으로 제한 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7aff-178">Filtering of file extensions is limited to standard file names.</span></span> <span data-ttu-id="b7aff-179">다른 이름에 포함 된 파일 확장명에는 필터링이 작동 하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7aff-179">Filtering may not work with file extensions embedded in other names.</span></span>



</div>

</div>

</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="b7aff-180">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="b7aff-180">In This Section</span></span>

  - [<span data-ttu-id="b7aff-181">Lync Server 2013의 기본 파일 전송 필터 수정</span><span class="sxs-lookup"><span data-stu-id="b7aff-181">Modify the default file transfer filter in Lync Server 2013</span></span>](lync-server-2013-modify-the-default-file-transfer-filter.md)

  - [<span data-ttu-id="b7aff-182">특정 사이트에 대 한 Lync Server 2013에서 새 파일 전송 필터 만들기</span><span class="sxs-lookup"><span data-stu-id="b7aff-182">Create a new file transfer filter in Lync Server 2013 for a specific site</span></span>](lync-server-2013-create-a-new-file-transfer-filter-for-a-specific-site.md)

  - [<span data-ttu-id="b7aff-183">Lync Server 2013의 기본 URL 필터 수정</span><span class="sxs-lookup"><span data-stu-id="b7aff-183">Modify the default URL filter in Lync Server 2013</span></span>](lync-server-2013-modify-the-default-url-filter.md)

  - [<span data-ttu-id="b7aff-184">Lync Server 2013에서 새 URL 필터를 만들어 메신저 대화의 하이퍼링크 처리</span><span class="sxs-lookup"><span data-stu-id="b7aff-184">Create a new URL filter in Lync Server 2013 to handle hyperlinks in IM conversations</span></span>](lync-server-2013-create-a-new-url-filter-to-handle-hyperlinks-in-im-conversations.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="b7aff-185">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b7aff-185">See Also</span></span>


[<span data-ttu-id="b7aff-186">Lync Server 2013에서 메신저 및 현재 상태 설정 관리</span><span class="sxs-lookup"><span data-stu-id="b7aff-186">Managing IM and presence settings in Lync Server 2013</span></span>](lync-server-2013-managing-im-and-presence-settings.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

