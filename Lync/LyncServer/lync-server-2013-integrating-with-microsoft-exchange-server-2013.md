---
title: 'Lync Server 2013: Microsoft Exchange Server 2013과 통합'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Integrating Lync Server 2013 and Exchange Server 2013
ms:assetid: 795dc1c6-524f-4012-8b66-103b55198044
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688098(v=OCS.15)
ms:contentKeyID: 49733697
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f1467f6a570f83908eb5809f9493303bdc91c169
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41725858"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="integrating-microsoft-lync-server-2013-and-microsoft-exchange-server-2013"></a><span data-ttu-id="8b9e0-102">Microsoft Lync Server 2013 및 Microsoft Exchange Server 2013 통합</span><span class="sxs-lookup"><span data-stu-id="8b9e0-102">Integrating Microsoft Lync Server 2013 and Microsoft Exchange Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8b9e0-103">_**마지막으로 수정한 주제:** 2014-07-09_</span><span class="sxs-lookup"><span data-stu-id="8b9e0-103">_**Topic Last Modified:** 2014-07-09_</span></span>

<span data-ttu-id="8b9e0-104">Exchange 및 Lync Server에는 통합 및 호환성에 대 한 긴 기록이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8b9e0-104">Exchange and Lync Server have a long history of integration and compatibility.</span></span> <span data-ttu-id="8b9e0-105">이러한 통합은 해당 클라이언트 응용 프로그램 내에서 가장 잘 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="8b9e0-105">This integration is most noticeable within their respective client application.</span></span> <span data-ttu-id="8b9e0-106">예를 들어 Lync 현재 상태 정보는 Microsoft Outlook에서 보고할 수 있습니다. 마찬가지로 Lync는 Outlook 일정을 사용 하 여 현재 상태 정보를 자동으로 업데이트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8b9e0-106">For example, Lync presence information can be reported in Microsoft Outlook; likewise, Lync can use Outlook calendar to automatically update that presence information.</span></span> <span data-ttu-id="8b9e0-107">예를 들어 Lync는 일정에 모임 일정이 표시 될 때마다 상태를 다른 용무 중으로 변경할 수 있습니다. Lync Server를 실행 하기 위해 Exchange를 실행할 필요는 없지만, 두 제품을 함께 사용 하는 것이 "더 나은" "epitomizes" 라는 용어의 정의를 함께 하는 것은 거의 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8b9e0-107">(For example, Lync can change your status to Busy any time your calendar shows that you have a meeting scheduled.) Although you do not have to run Exchange in order to run Lync Server (or vice-versa) there's little doubt that using the two products together epitomizes the very definition of the term "better together."</span></span>

<span data-ttu-id="8b9e0-108">이는 특히 Microsoft Lync Server 2013 및 Microsoft Exchange Server 2013의 릴리스를 사용 하는 경우에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8b9e0-108">This is especially true with the release of Microsoft Lync Server 2013 and Microsoft Exchange Server 2013.</span></span> <span data-ttu-id="8b9e0-109">통합 메시징 및 IM 및 현재 상태와 같은 기능 외에도 Microsoft Exchange Server 2010 및 Microsoft Lync Server 2010에는 있지만, 서버 제품의 2013 릴리스에는 여러 가지 새로운 기능이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8b9e0-109">In addition to features, such as unified messaging and IM and presence, that are found in Microsoft Exchange Server 2010 and Microsoft Lync Server 2010, the 2013 releases of the server products include a number of new capabilities.</span></span> <span data-ttu-id="8b9e0-110">이러한 기능에는 다음과 같은 항목이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8b9e0-110">These capabilities include such things as:</span></span>

  - <span data-ttu-id="8b9e0-111">**Lync 보관 통합**.</span><span class="sxs-lookup"><span data-stu-id="8b9e0-111">**Lync Archiving Integration**.</span></span> <span data-ttu-id="8b9e0-112">Lync Server 2013 관리자는 계속 해 서 인스턴트 메시징 및 웹 회의를 SQL Server에 보관 하는 옵션을 사용할 수 있습니다 (이 경우에는이 내용이 Lync Server 2010에 보관 되는 방식).</span><span class="sxs-lookup"><span data-stu-id="8b9e0-112">In Lync Server 2013 administrators still have the option of having instant messaging and Web conferencing transcripts archived to SQL Server (the same way these transcripts were archived in Lync Server 2010).</span></span> <span data-ttu-id="8b9e0-113">그렇지만, 관리자는 exchange 보관 통신을 사용 하는 것과 동일한 방법으로 개인 사용자 사서함에 기록 내용을 저장 하 여 Exchange 2013에 보관 된 것을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8b9e0-113">Alternatively, however, administrators can choose to have transcripts archived to Exchange 2013, storing those transcripts in the individual user mailboxes in the same way in which Exchange archives communications.</span></span> <span data-ttu-id="8b9e0-114">즉, Exchange 및 Lync Server 모두에서 모든 전자 통신을 위한 단일 리포지토리를 사용 하 여 필요한 경우 보관 된 통신을 검색 하 고 검색 하는 것이 훨씬 더 쉬워졌습니다.</span><span class="sxs-lookup"><span data-stu-id="8b9e0-114">That means a single repository for all your electronic communications (from both Exchange and Lync Server), which makes it much easier to search for and retrieve those archived communications should the need arise.</span></span>

  - <span data-ttu-id="8b9e0-115">**통합 된 대화 상대 저장소**.</span><span class="sxs-lookup"><span data-stu-id="8b9e0-115">**Unified Contact Store**.</span></span> <span data-ttu-id="8b9e0-116">Lync Server 2010에서 사용자는 Outlook과 Lync에서 별도의 연락처 목록을 유지 관리 해야 했습니다. 사실, 두 제품 모두에서 같은 연락처를 사용 하 고 Outlook과 Lync 용으로 중복 된 연락처 목록을 유지 해야 하는 것을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8b9e0-116">In Lync Server 2010, users had to maintain separate contact lists in Outlook and Lync; in fact, to ensure that you had the same contacts available in both products you had to maintain duplicate contact lists, one for Outlook and one for Lync.</span></span> <span data-ttu-id="8b9e0-117">그러나 Lync Server 2013에서는 사용자 연락처를 Exchange 2013 및 통합 대화 상대 저장소에 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8b9e0-117">With Lync Server 2013, however, user contacts can be stored in Exchange 2013 and the unified contact store.</span></span> <span data-ttu-id="8b9e0-118">단일 연락처 저장소를 사용 하면 모든 사용자가 Lync 2013, Outlook 2013, Outlook Web Access 2013에서 같은 연락처 집합을 사용할 수 있는 것과 동일한 연락처 집합을 유지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8b9e0-118">Using a single contact store enables users to maintain just one set of contacts, with that same set of contacts being available in Lync 2013, Outlook 2013, and Outlook Web Access 2013.</span></span>

  - <span data-ttu-id="8b9e0-119">**OWA에서 Lync 모임 예약**</span><span class="sxs-lookup"><span data-stu-id="8b9e0-119">**Lync Meeting Scheduling from OWA**.</span></span> <span data-ttu-id="8b9e0-120">Lync Server 2013 및 Exchange 2013 통합을 통해 사용자는 Outlook Web Access 2013에서 Lync 모임을 예약할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8b9e0-120">With Lync Server 2013 and Exchange 2013 integration, users can schedule Lync meetings from Outlook Web Access 2013.</span></span>

  - <span data-ttu-id="8b9e0-121">고해상도 **사진**.</span><span class="sxs-lookup"><span data-stu-id="8b9e0-121">**High resolution photos**.</span></span> <span data-ttu-id="8b9e0-122">Lync 2010는 연락처의 작은 사진만 표시할 수 있습니다. 이는 해당 사진이 Active Directory에 저장 되어 있고 Active Directory는 저장 된 사진에 48 픽셀 단위로 48 픽셀 크기의 제한을 부과 하기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="8b9e0-122">Lync 2010 could only display small photos of your contacts; that's because those photos were stored in Active Directory, and Active Directory imposes a 48 pixel by 48 pixel size limitation on stored photos.</span></span> <span data-ttu-id="8b9e0-123">그러나 Lync Server 2013에서 사진을 Microsoft Exchange에 저장할 수 있습니다. 이는 해상도가 고해상도 인 사진의 크기를 648 픽셀 단위로 648 픽셀 단위로 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="8b9e0-123">With Lync Server 2013, however, photos can be stored in Microsoft Exchange; that allows for high-resolution photos as large as 648 pixels by 648 pixels.</span></span> <span data-ttu-id="8b9e0-124">예상 대로, Lync 2013은 이러한 고해상도 사진을 표시할 수 있도록 업그레이드 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="8b9e0-124">As you might expect, Lync 2013 has been upgraded to allow for the display of these high-resolution photographs.</span></span>

<span data-ttu-id="8b9e0-125">이러한 새로운 기능을 사용 하려면 Lync Server 2013 및 Exchange 2013이 모두 필요 하다는 점에 유의 하세요.</span><span class="sxs-lookup"><span data-stu-id="8b9e0-125">Keep in mind that these new features require the use of both Lync Server 2013 and Exchange 2013.</span></span> <span data-ttu-id="8b9e0-126">그 외에도, 이러한 새로운 기능을 최대한 활용 하려는 사용자는 Lync Server 2013 및 Exchange 2013에 계정이 있어야 하며 최신 버전의 클라이언트 소프트웨어 (예: Lync 2013)를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8b9e0-126">In addition to that, users who hope to take full advantage of these new capabilities must have accounts on Lync Server 2013 and Exchange 2013, and must be using the latest versions of the client software (e.g., Lync 2013).</span></span> <span data-ttu-id="8b9e0-127">예를 들어 Lync Server 2010에서 홈을 사용한 사용자는 통합 된 연락처 저장소를 사용할 수 없습니다. 마찬가지로, 고해상도 사진을 Lync 2010에 표시할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8b9e0-127">For example, the unified contact store is not available to users who have been homed on Lync Server 2010; likewise, high-resolution photos cannot be displayed in Lync 2010.</span></span>

<span data-ttu-id="8b9e0-128">이 설명서는 Lync Server 2013 및 Exchange 2013 통합에 대 한 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="8b9e0-128">This documentation provides information on integrating Lync Server 2013 and Exchange 2013.</span></span> <span data-ttu-id="8b9e0-129">보관 통합 및 통합 된 연락처 저장소와 같은 새로운 기능을 사용 하는 방법에 대 한 단계별 정보를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="8b9e0-129">including step-by-step information on enabling new features such archiving Integration and the unified contact store.</span></span> <span data-ttu-id="8b9e0-130">이 설명서에서는 이러한 두 제품의 초기 설정 및 구성에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="8b9e0-130">What this documentation does not do is discuss the initial setup and configuration of these two products.</span></span> <span data-ttu-id="8b9e0-131">Lync Server 2013 배포에 대 한 자세한 내용은 Lync Server 2013 기술 센터를 [http://go.microsoft.com/fwlink/p/?LinkId=246127](http://go.microsoft.com/fwlink/p/?linkid=246127)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8b9e0-131">For details about deploying Lync Server 2013 see the Lync Server 2013 Tech Center at [http://go.microsoft.com/fwlink/p/?LinkId=246127](http://go.microsoft.com/fwlink/p/?linkid=246127).</span></span> <span data-ttu-id="8b9e0-132">Exchange 2013 배포에 대 한 자세한 내용은의 Exchange 2013 기술 센터 [http://go.microsoft.com/fwlink/p/?LinkId=268528](http://go.microsoft.com/fwlink/p/?linkid=268528)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8b9e0-132">For details about deploying Exchange 2013 see the Exchange 2013 Tech Center at [http://go.microsoft.com/fwlink/p/?LinkId=268528](http://go.microsoft.com/fwlink/p/?linkid=268528).</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="8b9e0-133">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="8b9e0-133">In This Section</span></span>

[<span data-ttu-id="8b9e0-134">Microsoft Lync Server 2013 및 Microsoft Exchange Server 2013 통합을 위한 필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="8b9e0-134">Prerequisites for integrating Microsoft Lync Server 2013 and Microsoft Exchange Server 2013</span></span>](lync-server-2013-prerequisites-for-integrating-with-exchange-server-2013.md)

[<span data-ttu-id="8b9e0-135">Microsoft Lync Server 2013 및 Microsoft Exchange Server 2013에서 파트너 응용 프로그램 구성</span><span class="sxs-lookup"><span data-stu-id="8b9e0-135">Configuring partner applications in Microsoft Lync Server 2013 and Microsoft Exchange Server 2013</span></span>](lync-server-2013-configuring-partner-applications-in-lync-server-2013-and-exchange-server-2013.md)

[<span data-ttu-id="8b9e0-136">Microsoft Exchange Server 2013 보관을 사용 하도록 Microsoft Lync Server 2013 구성</span><span class="sxs-lookup"><span data-stu-id="8b9e0-136">Configuring Microsoft Lync Server 2013 to use Microsoft Exchange Server 2013 archiving</span></span>](configuring-lync-server-2013-to-use-microsoft-exchange-server-2013-archiving.md)

[<span data-ttu-id="8b9e0-137">Microsoft SharePoint Server 2013에서 보관 된 Microsoft Lync Server 2013 데이터를 검색 하도록 구성</span><span class="sxs-lookup"><span data-stu-id="8b9e0-137">Configuring Microsoft SharePoint Server 2013 to search for archived Microsoft Lync Server 2013 data</span></span>](lync-server-2013-configuring-microsoft-sharepoint-server-2013-to-search-for-archived-lync-server-2013-data.md)

[<span data-ttu-id="8b9e0-138">통합 된 대화 상대 저장소를 사용 하도록 Microsoft Lync Server 2013 구성</span><span class="sxs-lookup"><span data-stu-id="8b9e0-138">Configuring Microsoft Lync Server 2013 to use the unified contact store</span></span>](lync-server-2013-configuring-lync-server-to-use-the-unified-contact-store.md)

[<span data-ttu-id="8b9e0-139">Microsoft Lync Server 2013에서 고해상도 사진 사용 구성</span><span class="sxs-lookup"><span data-stu-id="8b9e0-139">Configuring the use of high-resolution photos in Microsoft Lync Server 2013</span></span>](lync-server-2013-configuring-the-use-of-high-resolution-photos.md)

[<span data-ttu-id="8b9e0-140">Microsoft Lync Server 2013 음성 메일용 Microsoft Exchange Server 2013 통합 메시징 구성</span><span class="sxs-lookup"><span data-stu-id="8b9e0-140">Configuring Microsoft Exchange Server 2013 Unified Messaging for Microsoft Lync Server 2013 voice mail</span></span>](lync-server-2013-configuring-microsoft-exchange-server-2013-unified-messaging-for-lync-server-2013-voice-mail.md)

[<span data-ttu-id="8b9e0-141">Microsoft Lync Server 2013 및 Microsoft Outlook Web App 2013 통합</span><span class="sxs-lookup"><span data-stu-id="8b9e0-141">Integrating Microsoft Lync Server 2013 and Microsoft Outlook Web App 2013</span></span>](lync-server-2013-integrating-lync-server-and-outlook-web-app-2013.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

