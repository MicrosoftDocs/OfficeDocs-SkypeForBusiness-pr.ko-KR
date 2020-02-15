---
title: 'Lync Server 2013: 지원 되는 하이브리드 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Supported hybrid configurations
ms:assetid: 5d456d6c-ad71-420c-b6d8-4d9cd0324f86
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945633(v=OCS.15)
ms:contentKeyID: 51541482
ms.date: 05/10/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f268d76c33e3a76c909d164eb63d6ad3c1eb29c8
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029809"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="supported-lync-server-2013-hybrid-configurations"></a><span data-ttu-id="abdd3-102">지원 되는 Lync Server 2013 하이브리드 구성</span><span class="sxs-lookup"><span data-stu-id="abdd3-102">Supported Lync Server 2013 hybrid configurations</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="abdd3-103">_**마지막으로 수정 된 항목:** 2016-05-10_</span><span class="sxs-lookup"><span data-stu-id="abdd3-103">_**Topic Last Modified:** 2016-05-10_</span></span>

<span data-ttu-id="abdd3-104">온-프레미스와 온라인 모두에서 Microsoft Exchange Server 2010 및 Microsoft Exchange Server 2013 및 SharePoint Server와의 통합을 위해 Lync Server 2013 배포를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="abdd3-104">You can configure Lync Server 2013 deployments for integration with both Microsoft Exchange Server 2010 and Microsoft Exchange Server 2013 and SharePoint Server, both on-premises and online.</span></span> <span data-ttu-id="abdd3-105">별도로 지정 되지 않은 경우 모든 클라이언트에서 다음 표에 나열 된 기능을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="abdd3-105">The features listed in the following table are supported with all clients unless otherwise specified.</span></span> <span data-ttu-id="abdd3-106">클라이언트 지원에 대 한 자세한 내용은 [비즈니스용 Skype online에](http://go.microsoft.com/fwlink/p/?linkid=281902)대 한 클라이언트의 Lync Server 2013 및 비즈니스용 skype online 클라이언트 비교 테이블 [에 대 한 클라이언트 비교 표](lync-server-2013-desktop-client-comparison-tables.md) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="abdd3-106">For more information about client support, see [Client comparison tables for Lync Server 2013](lync-server-2013-desktop-client-comparison-tables.md) and Skype for Business Online client comparison tables at [Clients for Skype for Business Online](http://go.microsoft.com/fwlink/p/?linkid=281902).</span></span>

<div>

## <a name="integration-with-exchange-server"></a><span data-ttu-id="abdd3-107">Exchange Server와의 통합</span><span class="sxs-lookup"><span data-stu-id="abdd3-107">Integration with Exchange Server</span></span>

<span data-ttu-id="abdd3-108">다음 표에서는 Microsoft Exchange Server와 통합 될 때 하이브리드 배포에서 지원 되는 기능을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="abdd3-108">The following table lists the features supported in a hybrid deployment when integrated with Microsoft Exchange Server.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th><span data-ttu-id="abdd3-109">Exchange 온-프레미스</span><span class="sxs-lookup"><span data-stu-id="abdd3-109">Exchange on-premises</span></span></th>
<th><span data-ttu-id="abdd3-110">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="abdd3-110">Exchange Online</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="abdd3-111"><strong>Lync Server 2013 온-프레미스</strong></span><span class="sxs-lookup"><span data-stu-id="abdd3-111"><strong>Lync Server 2013 on-premises</strong></span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="abdd3-112">Outlook에서 IM/현재 상태</span><span class="sxs-lookup"><span data-stu-id="abdd3-112">IM/Presence in Outlook</span></span></p>
<p><span data-ttu-id="abdd3-113">자세한 내용은 <a href="lync-server-2013-im-and-presence.md">Lync Server 2013에서 IM 및 현재 상태</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="abdd3-113">For more information, see <a href="lync-server-2013-im-and-presence.md">IM and presence in Lync Server 2013</a></span></span></p></li>
<li><p><span data-ttu-id="abdd3-114">Outlook을 통해 온라인 모임 예약 및 참가</span><span class="sxs-lookup"><span data-stu-id="abdd3-114">Schedule and join online meetings through Outlook</span></span></p>
<p><span data-ttu-id="abdd3-115">자세한 내용은 <a href="lync-server-2013-integrating-with-microsoft-exchange-server-2013.md">Microsoft Lync Server 2013 및 Microsoft Exchange Server 2013 통합</a> 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="abdd3-115">For more information, see <a href="lync-server-2013-integrating-with-microsoft-exchange-server-2013.md">Integrating Microsoft Lync Server 2013 and Microsoft Exchange Server 2013</a></span></span></p></li>
<li><p><span data-ttu-id="abdd3-116">Outlook Web App에서 IM/현재 상태</span><span class="sxs-lookup"><span data-stu-id="abdd3-116">IM/Presence in Outlook Web App</span></span></p>
<p><span data-ttu-id="abdd3-117">자세한 내용은 <a href="lync-server-2013-configuring-lync-server-in-a-cross-premises-environment.md">크로스-프레미스 환경에서 Microsoft Lync Server 2013 구성</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="abdd3-117">For more information, see <a href="lync-server-2013-configuring-lync-server-in-a-cross-premises-environment.md">Configuring Microsoft Lync Server 2013 in a cross-premises environment</a></span></span></p></li>
<li><p><span data-ttu-id="abdd3-118">Outlook Web App을 통해 온라인 모임 예약 및 참가</span><span class="sxs-lookup"><span data-stu-id="abdd3-118">Schedule and join online meetings through Outlook Web App</span></span></p></li>
<li><p><span data-ttu-id="abdd3-119">모바일 클라이언트의 IM/현재 상태</span><span class="sxs-lookup"><span data-stu-id="abdd3-119">IM/Presence in Mobile Clients</span></span></p></li>
<li><p><span data-ttu-id="abdd3-120">모바일 클라이언트에서 온라인 모임 참가</span><span class="sxs-lookup"><span data-stu-id="abdd3-120">Join online meetings in Mobile clients</span></span></p>
<p><span data-ttu-id="abdd3-121">자세한 내용은 <a href="lync-server-2013-deploying-mobility.md">Lync Server 2013에서 모바일 기능 배포</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="abdd3-121">For more information, see <a href="lync-server-2013-deploying-mobility.md">Deploying mobility in Lync Server 2013</a></span></span></p></li>
<li><p><span data-ttu-id="abdd3-122">Outlook 일정 약속 있음/없음 정보를 기반으로 상태 게시</span><span class="sxs-lookup"><span data-stu-id="abdd3-122">Publish status based on Outlook calendar free/busy information</span></span></p></li>
<li><p><span data-ttu-id="abdd3-123">연락처 목록 (통합 연락처 저장소를 통해)</span><span class="sxs-lookup"><span data-stu-id="abdd3-123">Contact List (via Unified Contact Store)</span></span></p>
<p><span data-ttu-id="abdd3-124">자세한 내용은 <a href="lync-server-2013-configuring-lync-server-to-use-the-unified-contact-store.md">통합 연락처 저장소를 사용 하도록 Microsoft Lync Server 2013 구성을</a> 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="abdd3-124">For more information, see <a href="lync-server-2013-configuring-lync-server-to-use-the-unified-contact-store.md">Configuring Microsoft Lync Server 2013 to use the unified contact store</a></span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="abdd3-125">Exchange 2013이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="abdd3-125">Requires Exchange 2013.</span></span><BR><span data-ttu-id="abdd3-126">Lync 2013 데스크톱 클라이언트는 필수입니다.</span><span class="sxs-lookup"><span data-stu-id="abdd3-126">A Lync 2013 desktop client is required.</span></span>


</div></li>
<li><p><span data-ttu-id="abdd3-127">Lync 2013 클라이언트 및 Lync Web App의 고해상도 연락처 사진</span><span class="sxs-lookup"><span data-stu-id="abdd3-127">High-resolution Contact Photo in Lync 2013 client and Lync Web App.</span></span></p>
<p><span data-ttu-id="abdd3-128">자세한 내용은 <a href="lync-server-2013-configuring-the-use-of-high-resolution-photos.md">Microsoft Lync Server 2013에서 고해상도 사진 사용 구성</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="abdd3-128">For more information, see <a href="lync-server-2013-configuring-the-use-of-high-resolution-photos.md">Configuring the use of high-resolution photos in Microsoft Lync Server 2013</a></span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="abdd3-129">Exchange 2013이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="abdd3-129">Requires Exchange 2013.</span></span>


</div></li>
<li><p><span data-ttu-id="abdd3-130">모임 위임</span><span class="sxs-lookup"><span data-stu-id="abdd3-130">Meeting delegation</span></span></p>
<p><span data-ttu-id="abdd3-131">두 사용자가 같은 포리스트의 온라인에 있거나 둘 다 온-프레미스에 있는 경우에만 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="abdd3-131">Supported only when both users are homed online in the same forest, or both are homed on-premises.</span></span></p></li>
<li><p><span data-ttu-id="abdd3-132">부재 중 대화 기록 및 통화 로그가 사용자의 exchange 사서함에 기록 됨</span><span class="sxs-lookup"><span data-stu-id="abdd3-132">Missed Conversations history and Call Logs are written to user’s exchange mailbox</span></span></p></li>
<li><p><span data-ttu-id="abdd3-133">Exchange의 콘텐츠 (IM 및 모임) 보관</span><span class="sxs-lookup"><span data-stu-id="abdd3-133">Archiving Content (IM and Meeting) in Exchange</span></span></p>
<p><span data-ttu-id="abdd3-134">자세한 내용은 <a href="lync-server-2013-deployment-checklist-for-archiving.md">배포 검사 목록을 Lync Server 2013에서 보관</a> 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="abdd3-134">For more information, see <a href="lync-server-2013-deployment-checklist-for-archiving.md">Deployment checklist for Archiving in Lync Server 2013</a></span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="abdd3-135">Exchange 2013이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="abdd3-135">Requires Exchange 2013.</span></span>


</div></li>
<li><p><span data-ttu-id="abdd3-136">보관 된 콘텐츠 검색</span><span class="sxs-lookup"><span data-stu-id="abdd3-136">Search archived content</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="abdd3-137">Exchange 2013이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="abdd3-137">Requires Exchange 2013.</span></span>


</div></li>
<li><p><span data-ttu-id="abdd3-138">음성 사서함</span><span class="sxs-lookup"><span data-stu-id="abdd3-138">Voice mail</span></span></p>
<p><span data-ttu-id="abdd3-139">자세한 내용은 <a href="lync-server-2013-deploying-on-premises-exchange-um-to-provide-lync-server-2013-voice-mail.md">Lync Server 2013 음성 메일을 제공 하도록 온-프레미스 EXCHANGE UM 배포</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="abdd3-139">For more information, see <a href="lync-server-2013-deploying-on-premises-exchange-um-to-provide-lync-server-2013-voice-mail.md">Deploying on-premises Exchange UM to provide Lync Server 2013 voice mail</a></span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="abdd3-140">Outlook에서 IM/현재 상태</span><span class="sxs-lookup"><span data-stu-id="abdd3-140">IM/Presence in Outlook</span></span></p>
<p><span data-ttu-id="abdd3-141">자세한 내용은 <a href="lync-server-2013-configuring-on-premises-lync-server-integration-with-exchange-online.md">Exchange Online과 온-프레미스 Lync Server 2013 통합 구성</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="abdd3-141">For more information, see <a href="lync-server-2013-configuring-on-premises-lync-server-integration-with-exchange-online.md">Configuring on-premises Lync Server 2013 integration with Exchange Online</a></span></span></p></li>
<li><p><span data-ttu-id="abdd3-142">Outlook을 통해 온라인 모임 예약 및 참가</span><span class="sxs-lookup"><span data-stu-id="abdd3-142">Schedule and join online meeting through Outlook</span></span></p></li>
<li><p><span data-ttu-id="abdd3-143">OWA의 IM/현재 상태</span><span class="sxs-lookup"><span data-stu-id="abdd3-143">IM/Presence in OWA</span></span></p>
<p><span data-ttu-id="abdd3-144">자세한 내용은 <a href="lync-server-2013-configuring-on-premises-lync-server-integration-with-exchange-online.md">Exchange Online과 온-프레미스 Lync Server 2013 통합 구성</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="abdd3-144">For more information, see <a href="lync-server-2013-configuring-on-premises-lync-server-integration-with-exchange-online.md">Configuring on-premises Lync Server 2013 integration with Exchange Online</a></span></span></p></li>
<li><p><span data-ttu-id="abdd3-145">Outlook Web App에서 온라인 모임 예약 및 참가</span><span class="sxs-lookup"><span data-stu-id="abdd3-145">Schedule and join online meeting from Outlook Web App</span></span></p>
<p><span data-ttu-id="abdd3-146">자세한 내용은 <a href="lync-server-2013-configuring-on-premises-lync-server-integration-with-exchange-online.md">Exchange Online과 온-프레미스 Lync Server 2013 통합 구성</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="abdd3-146">For more information, see <a href="lync-server-2013-configuring-on-premises-lync-server-integration-with-exchange-online.md">Configuring on-premises Lync Server 2013 integration with Exchange Online</a></span></span></p></li>
<li><p><span data-ttu-id="abdd3-147">모바일 클라이언트의 IM/현재 상태</span><span class="sxs-lookup"><span data-stu-id="abdd3-147">IM/Presence in Mobile Clients</span></span></p></li>
<li><p><span data-ttu-id="abdd3-148">모바일 클라이언트에서 온라인 모임 참가</span><span class="sxs-lookup"><span data-stu-id="abdd3-148">Join online meeting in Mobile clients</span></span></p></li>
<li><p><span data-ttu-id="abdd3-149">Outlook 일정 약속 있음/없음 정보를 기반으로 상태 게시</span><span class="sxs-lookup"><span data-stu-id="abdd3-149">Publish status based on Outlook calendar free/busy information</span></span></p></li>
<li><p><span data-ttu-id="abdd3-150">연락처 목록 (통합 연락처 저장소를 통해)</span><span class="sxs-lookup"><span data-stu-id="abdd3-150">Contact List (via Unified Contact Store).</span></span> <span data-ttu-id="abdd3-151">자세한 내용은 <a href="lync-server-2013-configuring-lync-server-to-use-the-unified-contact-store.md">통합 연락처 저장소를 사용 하도록 Microsoft Lync Server 2013 구성을</a> 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="abdd3-151">For more information, see <a href="lync-server-2013-configuring-lync-server-to-use-the-unified-contact-store.md">Configuring Microsoft Lync Server 2013 to use the unified contact store</a></span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="abdd3-152">Lync Server 2013 전용</span><span class="sxs-lookup"><span data-stu-id="abdd3-152">Lync Server 2013 only.</span></span> <span data-ttu-id="abdd3-153">Lync 2013 데스크톱 클라이언트는 필수입니다.</span><span class="sxs-lookup"><span data-stu-id="abdd3-153">A Lync 2013 desktop client is required.</span></span>


</div></li>
<li><p><span data-ttu-id="abdd3-154">Lync 2013 클라이언트 및 Lync Web App의 고해상도 연락처 사진</span><span class="sxs-lookup"><span data-stu-id="abdd3-154">High-resolution Contact Photo in Lync 2013 client and Lync Web App.</span></span></p>
<p><span data-ttu-id="abdd3-155">자세한 내용은 <a href="lync-server-2013-configuring-the-use-of-high-resolution-photos.md">Microsoft Lync Server 2013에서 고해상도 사진 사용 구성</a>를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="abdd3-155">For more information, see <a href="lync-server-2013-configuring-the-use-of-high-resolution-photos.md">Configuring the use of high-resolution photos in Microsoft Lync Server 2013</a>.</span></span></p></li>
<li><p><span data-ttu-id="abdd3-156">모임 위임</span><span class="sxs-lookup"><span data-stu-id="abdd3-156">Meeting delegation</span></span></p>
<p><span data-ttu-id="abdd3-157">두 사용자가 같은 포리스트의 온라인에 있거나 둘 다 온-프레미스에 있는 경우에만 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="abdd3-157">Supported only when both users are homed online in the same forest, or both are homed on-premises.</span></span></p></li>
<li><p><span data-ttu-id="abdd3-158">부재 중 대화 기록 및 통화 로그가 사용자의 exchange 사서함에 기록 됨</span><span class="sxs-lookup"><span data-stu-id="abdd3-158">Missed Conversations history and Call Logs are written to user’s exchange mailbox</span></span></p></li>
<li><p><span data-ttu-id="abdd3-159">Exchange의 콘텐츠 (IM 및 모임)를 보관 합니다.</span><span class="sxs-lookup"><span data-stu-id="abdd3-159">Archiving Content (IM and Meeting) in Exchange.</span></span></p>
<p><span data-ttu-id="abdd3-160">자세한 내용은 <a href="lync-server-2013-deployment-checklist-for-archiving.md">배포 검사 목록을 Lync Server 2013에서 보관</a> 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="abdd3-160">For more information, see <a href="lync-server-2013-deployment-checklist-for-archiving.md">Deployment checklist for Archiving in Lync Server 2013</a></span></span></p></li>
<li><p><span data-ttu-id="abdd3-161">보관 된 콘텐츠를 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="abdd3-161">Search archived content.</span></span> <span data-ttu-id="abdd3-162">자세한 내용은 <a href="http://go.microsoft.com/fwlink/p/?linkid=285448">Configure Exchange For SharePoint EDiscovery Center</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="abdd3-162">For more information, see at <a href="http://go.microsoft.com/fwlink/p/?linkid=285448">Configure Exchange for SharePoint eDiscovery Center</a></span></span></p></li>
<li><p><span data-ttu-id="abdd3-163">음성 사서함</span><span class="sxs-lookup"><span data-stu-id="abdd3-163">Voice mail.</span></span> <span data-ttu-id="abdd3-164">자세한 내용은 <a href="lync-server-2013-providing-lync-server-users-voice-mail-on-hosted-exchange-um.md">Lync Server 2013 users 사용자에 게 호스팅된 EXCHANGE UM에 대 한 음성 메일 제공</a> 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="abdd3-164">For more information, see <a href="lync-server-2013-providing-lync-server-users-voice-mail-on-hosted-exchange-um.md">Providing Lync Server 2013 users voice mail on hosted Exchange UM</a></span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="abdd3-165"><strong>Lync Online</strong></span><span class="sxs-lookup"><span data-stu-id="abdd3-165"><strong>Lync Online</strong></span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="abdd3-166">Outlook의 IM 및 현재 상태</span><span class="sxs-lookup"><span data-stu-id="abdd3-166">IM and Presence in Outlook</span></span></p></li>
<li><p><span data-ttu-id="abdd3-167">Outlook을 통해 온라인 모임 예약 및 참가</span><span class="sxs-lookup"><span data-stu-id="abdd3-167">Schedule and join online meetings through Outlook</span></span></p></li>
<li><p><span data-ttu-id="abdd3-168">모바일 클라이언트의 IM/현재 상태</span><span class="sxs-lookup"><span data-stu-id="abdd3-168">IM/Presence in Mobile clients</span></span></p></li>
<li><p><span data-ttu-id="abdd3-169">부재 중 대화 기록 및 통화 로그가 사용자의 exchange 사서함에 기록 됨</span><span class="sxs-lookup"><span data-stu-id="abdd3-169">Missed Conversations history and Call Logs are written to user’s exchange mailbox</span></span></p></li>
<li><p><span data-ttu-id="abdd3-170">Lync 2013 클라이언트의 고해상도 대화 상대 사진입니다.</span><span class="sxs-lookup"><span data-stu-id="abdd3-170">High-resolution Contact Photo in Lync 2013 client.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="abdd3-171">Microsoft Exchange Server 2013이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="abdd3-171">Requires Microsoft Exchange Server 2013.</span></span> <span data-ttu-id="abdd3-172">사용자가 비즈니스용 Skype Online에 있는 경우이 기능은 Lync Web App에서 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="abdd3-172">This is not supported in Lync Web App when users are homed on Skype for Business Online.</span></span>


</div></li>
<li><p><span data-ttu-id="abdd3-173">모바일 클라이언트에서 온라인 모임 참가</span><span class="sxs-lookup"><span data-stu-id="abdd3-173">Join online meeting in Mobile clients</span></span></p></li>
<li><p><span data-ttu-id="abdd3-174">Outlook 일정 약속 있음/없음 정보를 기반으로 상태 게시</span><span class="sxs-lookup"><span data-stu-id="abdd3-174">Publish status based on Outlook calendar free/busy information</span></span></p></li>
<li><p><span data-ttu-id="abdd3-175">모임 위임</span><span class="sxs-lookup"><span data-stu-id="abdd3-175">Meeting delegation</span></span></p>
<p><span data-ttu-id="abdd3-176">두 사용자가 같은 포리스트의 온라인에 있거나 둘 다 온-프레미스에 있는 경우에만 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="abdd3-176">Supported only when both users are homed online in the same forest, or both are homed on-premises.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="abdd3-177">Outlook에서 IM/현재 상태</span><span class="sxs-lookup"><span data-stu-id="abdd3-177">IM/Presence in Outlook</span></span></p></li>
<li><p><span data-ttu-id="abdd3-178">Outlook을 통해 온라인 모임 예약 및 참가</span><span class="sxs-lookup"><span data-stu-id="abdd3-178">Schedule and join online meetings through Outlook</span></span></p></li>
<li><p><span data-ttu-id="abdd3-179">Outlook Web App에서 IM/현재 상태</span><span class="sxs-lookup"><span data-stu-id="abdd3-179">IM/Presence in Outlook Web App</span></span></p></li>
<li><p><span data-ttu-id="abdd3-180">Outlook Web App에서 온라인 모임 예약 및 참가</span><span class="sxs-lookup"><span data-stu-id="abdd3-180">Schedule and join online meeting from Outlook Web App</span></span></p></li>
<li><p><span data-ttu-id="abdd3-181">모바일 클라이언트의 IM/현재 상태</span><span class="sxs-lookup"><span data-stu-id="abdd3-181">IM/Presence in Mobile Clients</span></span></p></li>
<li><p><span data-ttu-id="abdd3-182">모바일 클라이언트에서 온라인 모임 참가</span><span class="sxs-lookup"><span data-stu-id="abdd3-182">Join online meeting in Mobile clients</span></span></p></li>
<li><p><span data-ttu-id="abdd3-183">Outlook 일정 약속 있음/없음 정보를 기반으로 상태 게시</span><span class="sxs-lookup"><span data-stu-id="abdd3-183">Publish status based on Outlook calendar free/busy information</span></span></p></li>
<li><p><span data-ttu-id="abdd3-184">부재 중 대화 기록 및 통화 로그가 사용자의 exchange 사서함에 기록 됨</span><span class="sxs-lookup"><span data-stu-id="abdd3-184">Missed Conversations history and Call Logs are written to user’s exchange mailbox</span></span></p></li>
<li><p><span data-ttu-id="abdd3-185">연락처 목록 (통합 연락처 저장소를 통해)</span><span class="sxs-lookup"><span data-stu-id="abdd3-185">Contact List (via Unified Contact Store)</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="abdd3-186">Lync Server 2013 클라이언트 필요</span><span class="sxs-lookup"><span data-stu-id="abdd3-186">Lync Server 2013 client Required</span></span>


</div></li>
<li><p><span data-ttu-id="abdd3-187">Lync 2013 클라이언트 및 Lync 웹 응용 프로그램의 고해상도 연락처 사진</span><span class="sxs-lookup"><span data-stu-id="abdd3-187">High-resolution Contact Photo in Lync 2013 client and Lync Web App</span></span></p></li>
<li><p><span data-ttu-id="abdd3-188">모임 위임</span><span class="sxs-lookup"><span data-stu-id="abdd3-188">Meeting delegation</span></span></p>
<p><span data-ttu-id="abdd3-189">두 사용자가 같은 포리스트의 온라인에 있거나 둘 다 온-프레미스에 있는 경우에만 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="abdd3-189">Supported only when both users are homed online in the same forest, or both are homed on-premises.</span></span></p></li>
<li><p><span data-ttu-id="abdd3-190">Exchange의 콘텐츠 (IM 및 모임) 보관</span><span class="sxs-lookup"><span data-stu-id="abdd3-190">Archiving Content (IM and Meeting) in Exchange</span></span></p></li>
<li><p><span data-ttu-id="abdd3-191">보관 된 콘텐츠 검색</span><span class="sxs-lookup"><span data-stu-id="abdd3-191">Search archived content</span></span></p></li>
<li><p><span data-ttu-id="abdd3-192">Voicemail</span><span class="sxs-lookup"><span data-stu-id="abdd3-192">Voicemail</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="integration-with-sharepoint"></a><span data-ttu-id="abdd3-193">SharePoint와의 통합</span><span class="sxs-lookup"><span data-stu-id="abdd3-193">Integration with SharePoint</span></span>

<span data-ttu-id="abdd3-194">다음 표에서는 SharePoint와 통합할 때 Lync Server 2013 하이브리드 배포에서 지원 되는 기능을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="abdd3-194">The following table lists the features supported in a Lync Server 2013 hybrid deployment when integrated with SharePoint.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th><span data-ttu-id="abdd3-195">SharePoint 온-프레미스</span><span class="sxs-lookup"><span data-stu-id="abdd3-195">SharePoint on-premises</span></span></th>
<th><span data-ttu-id="abdd3-196">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="abdd3-196">SharePoint Online</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="abdd3-197"><strong>Lync Server 2013 온-프레미스</strong></span><span class="sxs-lookup"><span data-stu-id="abdd3-197"><strong>Lync Server 2013 on-premises</strong></span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="abdd3-198">기술 검색</span><span class="sxs-lookup"><span data-stu-id="abdd3-198">Skills search</span></span></p></li>
<li><p><span data-ttu-id="abdd3-199">SharePoint의 현재 상태</span><span class="sxs-lookup"><span data-stu-id="abdd3-199">Presence in SharePoint</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="abdd3-200">SharePoint의 현재 상태</span><span class="sxs-lookup"><span data-stu-id="abdd3-200">Presence in SharePoint</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="abdd3-201"><strong>Lync Online</strong></span><span class="sxs-lookup"><span data-stu-id="abdd3-201"><strong>Lync Online</strong></span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="abdd3-202">SharePoint의 현재 상태</span><span class="sxs-lookup"><span data-stu-id="abdd3-202">Presence in SharePoint</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="abdd3-203">SharePoint의 현재 상태</span><span class="sxs-lookup"><span data-stu-id="abdd3-203">Presence in SharePoint</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

