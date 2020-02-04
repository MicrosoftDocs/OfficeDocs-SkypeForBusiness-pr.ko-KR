---
title: Microsoft Exchange Server 2013 보관을 사용 하도록 Lync Server 2013 구성
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Lync Server 2013 to use Exchange Server 2013 archiving
ms:assetid: 260346d1-edc8-4a0c-8ad2-6c2401c3c377
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ679896(v=OCS.15)
ms:contentKeyID: 49557731
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3b163b0ce3324455f8a80eca7be5c1423b302a3d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723188"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-microsoft-lync-server-2013-to-use-microsoft-exchange-server-2013-archiving"></a><span data-ttu-id="91779-102">Microsoft Exchange Server 2013 보관을 사용 하도록 Microsoft Lync Server 2013 구성</span><span class="sxs-lookup"><span data-stu-id="91779-102">Configuring Microsoft Lync Server 2013 to use Microsoft Exchange Server 2013 archiving</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="91779-103">_**마지막으로 수정한 주제:** 2014-06-24_</span><span class="sxs-lookup"><span data-stu-id="91779-103">_**Topic Last Modified:** 2014-06-24_</span></span>

<span data-ttu-id="91779-104">Microsoft Lync Server 2013는 관리자에 게 SQL Server 데이터베이스가 아닌 사용자의 Microsoft Exchange Server 2013 사서함에 인스턴트 메시지 및 웹 회의 증명서를 보관 하는 옵션을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="91779-104">Microsoft Lync Server 2013 gives administrators the option of having instant messaging and Web conferencing transcripts archived to a user's Microsoft Exchange Server 2013 mailbox rather than a SQL Server database.</span></span> <span data-ttu-id="91779-105">이 옵션을 사용 하도록 설정 하면 사용자의 사서함에 있는 제거 폴더에 대 한 증명서가 기록 됩니다.</span><span class="sxs-lookup"><span data-stu-id="91779-105">If you enable this option, transcripts are written to the Purges folder in the user's mailbox.</span></span> <span data-ttu-id="91779-106">제거 폴더는 복구 가능한 항목 폴더에 있는 숨겨진 폴더입니다.</span><span class="sxs-lookup"><span data-stu-id="91779-106">The Purges folder is a hidden folder found in the Recoverable Items folder.</span></span> <span data-ttu-id="91779-107">이 폴더는 최종 사용자에 게 표시 되지 않지만,이 폴더는 Exchange 검색 엔진을 기준으로 색인화 되며 Exchange 사서함 검색 및/또는 Microsoft SharePoint Server 2013를 사용 하 여 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91779-107">Although this folder is not visible to end-users, the folder is indexed by the Exchange search engine and can be discovered by using Exchange mailbox search and/or Microsoft SharePoint Server 2013.</span></span> <span data-ttu-id="91779-108">정보는 Exchange 원본 위치 유지 기능 (전자 메일 보관 및 기타 Exchange 통신을 담당 하는 경우)에서 사용 하는 동일한 폴더에 저장 되므로, 관리자는 단일 도구를 사용 하 여 다음에 보관 된 모든 전자 통신을 검색할 수 있습니다. 클릭할.</span><span class="sxs-lookup"><span data-stu-id="91779-108">Because information is stored in the same folder used by the Exchange In-Place Hold feature (responsible for archiving email and other Exchange communications), administrators can use a single tool to search for all the electronic communications archived for a user.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="91779-109">Lync 대화 보관을 완전히 사용 하지 않도록 설정 하려면 Lync 대화 내역도 사용 하지 않도록 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="91779-109">To completely disable archiving of Lync conversation, you must also disable Lync conversation history.</span></span> <span data-ttu-id="91779-110">자세한 내용은 Lync Server 2013, <A href="https://docs.microsoft.com/powershell/module/skype/New-CsClientPolicy">새 csclientpolicy</A>및 <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy">Set csclientpolicy</A> <A href="lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md">에서 내부 및 외부 통신 보관 관리</A>항목을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="91779-110">For more information, see the following topics: <A href="lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md">Managing the Archiving of internal and external communications in Lync Server 2013</A>, <A href="https://docs.microsoft.com/powershell/module/skype/New-CsClientPolicy">New-CsClientPolicy</A>, and <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy">Set-CsClientPolicy</A>.</span></span>



</div>

<span data-ttu-id="91779-111">Exchange 2013에 대 한 성적 보관용을 보관 하려면 두 서버 간에 서버 간 인증을 구성 하는 것으로 시작 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="91779-111">In order to archive transcripts to Exchange 2013 you must begin by configuring server-to-server authentication between the two servers.</span></span> <span data-ttu-id="91779-112">서버 간 인증을 적용 한 후 Microsoft Lync Server 2013에서 다음 작업을 수행할 수 있습니다 (설정 및 구성에 따라 이러한 작업을 모두 완료할 필요는 없음).</span><span class="sxs-lookup"><span data-stu-id="91779-112">After server-to-server authentication is in place you can then carry out the following tasks in Microsoft Lync Server 2013 (note that, depending on your setup and configuration, you might not need to complete all of these tasks):</span></span>

1.  <span data-ttu-id="91779-113">Lync Server 보관 구성 설정을 수정 하 여 Exchange 보관을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="91779-113">Enable Exchange archiving by modifying your Lync Server archiving configuration settings.</span></span> <span data-ttu-id="91779-114">모든 배포에이 단계가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="91779-114">This step is required for all deployments.</span></span>

2.  <span data-ttu-id="91779-115">사용자에 대 한 내부 및/또는 외부 통신을 보관할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91779-115">Enable archiving for internal and/or external communications for your users.</span></span> <span data-ttu-id="91779-116">모든 배포에이 단계가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="91779-116">This step is required for all deployments.</span></span>

3.  <span data-ttu-id="91779-117">각 사용자에 대 한 ExchangeArchivingPolicy 속성을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="91779-117">Configure the ExchangeArchivingPolicy property for each user.</span></span> <span data-ttu-id="91779-118">이 단계는 Lync Server에만 필요 하며 Exchange는 서로 다른 포리스트에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91779-118">This step is only required in Lync Server and Exchange are located in different forests.</span></span>

<div>

## <a name="step-1-enabling-exchange-archiving"></a><span data-ttu-id="91779-119">1 단계: Exchange 보관 기능 설정</span><span class="sxs-lookup"><span data-stu-id="91779-119">Step 1: Enabling Exchange Archiving</span></span>

<span data-ttu-id="91779-120">Lync Server의 보관은 기본적으로 보관 구성 설정을 사용 하 여 관리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="91779-120">Archiving in Lync Server is primarily managed by using the archiving configuration settings.</span></span> <span data-ttu-id="91779-121">Lync Server 2013을 설치 하면 이러한 설정의 단일 전역 컬렉션이 자동으로 지정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="91779-121">When you install Lync Server 2013 you are automatically given a single, global collection of these settings.</span></span> <span data-ttu-id="91779-122">(관리자가 사이트 범위에서 선택적으로 새 보관 설정 모음을 만들 수 있습니다.) 기본적으로, 전역 설정에서는 보관을 사용할 수 없으며, 이러한 설정에서는 Exchange 보관도 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="91779-122">(Administrators can optionally create new collections of archiving settings at the site scope.) By default, archiving is not enabled in the global settings, nor is Exchange archiving enabled in these settings.</span></span> <span data-ttu-id="91779-123">Exchange 보관 관리자를 사용 하려면 이러한 구성 설정에서 EnableArchiving 및 EnableExchangeArchiving 속성을 모두 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="91779-123">In order to use Exchange archiving administrators must configure both the EnableArchiving and the EnableExchangeArchiving properties in these configuration settings.</span></span> <span data-ttu-id="91779-124">EnableArchiving 속성은 다음 세 가지 가능한 값 중 하나로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91779-124">The EnableArchiving property can be set to one of three possible values:</span></span>

  - <span data-ttu-id="91779-125">**없음**.</span><span class="sxs-lookup"><span data-stu-id="91779-125">**None**.</span></span> <span data-ttu-id="91779-126">보관을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="91779-126">Archiving is disabled.</span></span> <span data-ttu-id="91779-127">기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="91779-127">This is the default value.</span></span> <span data-ttu-id="91779-128">EnableArchiving이 없음으로 설정 된 경우에는 Lync Server 보관 데이터베이스나 Exchange 2013에 아무 것도 보관 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="91779-128">If EnableArchiving is set to None then nothing will be archived in either your Lync Server archiving database or in Exchange 2013.</span></span>

  - <span data-ttu-id="91779-129">**Imonly**.</span><span class="sxs-lookup"><span data-stu-id="91779-129">**ImOnly**.</span></span> <span data-ttu-id="91779-130">인스턴트 메시지 증명서만 보관 됩니다.</span><span class="sxs-lookup"><span data-stu-id="91779-130">Only instant message transcripts are archived.</span></span> <span data-ttu-id="91779-131">Exchange 보관을 사용 하는 경우 이러한 증명서는 Exchange 2013에 보관 됩니다.</span><span class="sxs-lookup"><span data-stu-id="91779-131">If Exchange archiving is enabled these transcripts will be archived in Exchange 2013.</span></span> <span data-ttu-id="91779-132">Exchange 보관을 사용 하지 않도록 설정 하면 이러한 증명서는 Lync Server에 보관 됩니다.</span><span class="sxs-lookup"><span data-stu-id="91779-132">If Exchange archiving is disabled then these transcripts will be archived to Lync Server.</span></span>

  - <span data-ttu-id="91779-133">**Imandwebconf**.</span><span class="sxs-lookup"><span data-stu-id="91779-133">**ImAndWebConf**.</span></span> <span data-ttu-id="91779-134">인스턴트 메시지 기록 및 웹 회의 기록 모두 보관 됩니다.</span><span class="sxs-lookup"><span data-stu-id="91779-134">Both instant message transcripts and Web conferencing transcripts are archived.</span></span> <span data-ttu-id="91779-135">Exchange 보관을 사용 하는 경우 이러한 증명서는 Exchange 2013에 보관 됩니다.</span><span class="sxs-lookup"><span data-stu-id="91779-135">If Exchange archiving is enabled these transcripts will be archived in Exchange 2013.</span></span> <span data-ttu-id="91779-136">Exchange 보관을 사용 하지 않도록 설정 하면 이러한 증명서는 Lync Server에 보관 됩니다.</span><span class="sxs-lookup"><span data-stu-id="91779-136">If Exchange archiving is disabled then these transcripts will be archived to Lync Server.</span></span>

<span data-ttu-id="91779-137">EnableExchangeArchiving 속성은 부울 값입니다. Exchange 보관을 사용 하도록 EnableExchangeArchiving ($True) 설정 하거나 EnableExchangeArchiving에서 False ($False)로 설정 하 여 Exchange 보관을 사용 하지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="91779-137">The EnableExchangeArchiving property is a Boolean value: set EnableExchangeArchiving to True ($True) to enable Exchange archiving or set EnableExchangeArchiving to False ($False) to disable Exchange archiving.</span></span> <span data-ttu-id="91779-138">예를 들어이 명령을 사용 하 여 메신저 대화를 보관 하 고 Exchange 보관을 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91779-138">For example, this command enables the archiving of instant messaging transcripts and also enables Exchange archiving:</span></span>

    Set-CsArchivingConfiguration -Identity "global" -EnableArchiving ImOnly -EnableExchangeArchiving $True

<span data-ttu-id="91779-139">Exchange 보관을 사용 하지 않도록 설정 하려면 다음과 같은 명령을 사용 합니다 (인스턴트 메시징 보관을 사용할 수 있도록 설정 하 고 Exchange로의 보관을 사용 하지 않도록 설정) (즉, 다음과 같이 Lync Server에 대 한 기록 저장).</span><span class="sxs-lookup"><span data-stu-id="91779-139">To disable Exchange archiving, use a command similar to the following, which enables instant messaging archiving but disables archiving to Exchange (in other words, transcripts will be archived to Lync Server):</span></span>

    Set-CsArchivingConfiguration -Identity "global" -EnableArchiving ImOnly -EnableExchangeArchiving $False

<div>


> [!NOTE]  
> <span data-ttu-id="91779-140">EnableArchiving 속성이 없음으로 설정 되어 있는 경우 Lync Server가 인스턴트 메시지 및 웹 회의 기록 메시지를 전혀 보관 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="91779-140">If the EnableArchiving property is set to None then Lync Server will not archive instant messaging and Web conferencing transcripts at all.</span></span> <span data-ttu-id="91779-141">이 경우 서버는 EnableExchangeArchiving에 대해 구성 된 값만 무시 합니다.</span><span class="sxs-lookup"><span data-stu-id="91779-141">In that case, the server will simply ignore the value configured for EnableExchangeArchiving.</span></span>



</div>

<span data-ttu-id="91779-142">Lync Server 제어판을 사용 하 여 Exchange 보관을 사용 하거나 사용 하지 않도록 설정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91779-142">Exchange archiving can also be enabled (or disabled) by using the Lync Server Control Panel.</span></span> <span data-ttu-id="91779-143">이렇게 하려면 다음 절차를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="91779-143">To do that, complete the following procedure:</span></span>

1.  <span data-ttu-id="91779-144">제어판에서 **모니터링 및 보관**을 클릭 한 다음 **구성을 보관**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="91779-144">In Control Panel, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>

2.  <span data-ttu-id="91779-145">**보관 구성** 탭에서 수정할 보관 설정 모음 (예: **전역** 컬렉션)을 두 번 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="91779-145">On the **Archiving Configuration** tab, double-click the collection of archiving settings to be modified (for example, the **Global** collection).</span></span>

3.  <span data-ttu-id="91779-146">**보관 설정 편집** 창에서 **보관 설정** 드롭다운 목록을 클릭 하 고 **im 세션** 보관 (인스턴트 메시징 세션만 보관) 또는 **im 및 웹 회의 세션** 보관 (인스턴트 메시징 및 웹 회의 세션을 보관 하려면)을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="91779-146">In the **Edit Archiving Setting** pane, click the **Archiving setting** dropdown list and select either **Archive IM sessions** (to archive just instant messaging sessions) or **Archive IM and web conferencing sessions** (to archive both instant messaging and Web conferencing sessions).</span></span>

4.  <span data-ttu-id="91779-147">보관할 항목을 선택한 후 exchange **Server 통합** 확인란을 선택 하 여 exchange 보관을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="91779-147">After choosing the items to be archived, select the **Exchange Server integration** checkbox to enable Exchange archiving.</span></span> <span data-ttu-id="91779-148">Exchange 보관을 사용 하지 않도록 설정 하려면이 확인란의 선택을 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="91779-148">To disable Exchange archiving, clear this checkbox.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="91779-149">보관 <STRONG>설정이</STRONG> <STRONG>보관을 사용 하지 않도록</STRONG>설정 되어 있는 경우 <STRONG>Exchange Server 통합</STRONG> 확인란을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="91779-149">The <STRONG>Exchange Server integration</STRONG> checkbox will not be available if the <STRONG>Archiving setting</STRONG> is set to <STRONG>Disable archiving</STRONG>.</span></span> <span data-ttu-id="91779-150">보관을 먼저 설정한 다음 Exchange 보관을 사용 하도록 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="91779-150">You must enable archiving first and then enable Exchange archiving.</span></span>



</div>

<span data-ttu-id="91779-151">Lync Server 2013 및 Exchange 2013이 동일한 포리스트에 있는 경우 Exchange 원본 위치 유지 정책을 사용 하 여 개별 사용자 (또는 최소한 Exchange 2013의 전자 메일 계정이 있는 사용자에 대해) 보관을 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="91779-151">If Lync Server 2013 and Exchange 2013 are located in the same forest then archiving for individual users (or at least for users who have email accounts on Exchange 2013) is managed by using Exchange In-Place Hold policies.</span></span> <span data-ttu-id="91779-152">이전 버전의 Exchange에서 거주 하는 사용자가 있는 경우 해당 사용자에 대 한 보관은 Lync Server 보관 정책을 사용 하 여 관리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="91779-152">If you have users who are homed on a previous version of Exchange then archiving for those users will be managed by using Lync Server archiving policies.</span></span> <span data-ttu-id="91779-153">Exchange 2013에 계정이 있는 사용자만 자신의 Lync 성적을 Exchange에 보관할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91779-153">Note that only users with accounts on Exchange 2013 can have their Lync transcripts archived to Exchange.</span></span>

<span data-ttu-id="91779-154">Lync Server 2013 및 Exchange 2013이 서로 다른 포리스트에 있는 경우 개별 사용자 계정에 대해 ExchangeArchivingPolicy 속성을 구성 하 여 개인 사용자의 보관을 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="91779-154">If Lync Server 2013 and Exchange 2013 are located in different forests then archiving for individual users is managed by configuring the ExchangeArchivingPolicy property for each individual user account.</span></span> <span data-ttu-id="91779-155">자세한 내용은 3 단계를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="91779-155">See Step 3 for more information.</span></span>

</div>

<div>

## <a name="step-2-enabling-the-archiving-of-internal-andor-external-communications"></a><span data-ttu-id="91779-156">2 단계: 내부 및/또는 외부 통신의 아카이빙 사용</span><span class="sxs-lookup"><span data-stu-id="91779-156">Step 2: Enabling the Archiving of Internal and/or External Communications</span></span>

<span data-ttu-id="91779-157">보관 (및 Exchange 보관)을 사용 하도록 설정한 후에는 사용자 세션이 실제로 보관 되도록 적절 한 보관 정책을 수정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="91779-157">After you have enabled archiving (and Exchange archiving) you must then modify the appropriate archiving policies to ensure that user sessions are actually archived.</span></span> <span data-ttu-id="91779-158">간단 하 게 보관 (1 단계)을 사용 하도록 설정 하면 Lync Server가 인스턴트 메시지 및 웹 회의 기록 보관을 시작 하는 것이 발생 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="91779-158">Note that simply enabling archiving (Step 1) does not cause Lync Server to begin archiving instant messaging and Web conferencing transcripts.</span></span> <span data-ttu-id="91779-159">대신 보관 정책을 사용 하 여 내부 및/또는 외부 보관을 사용 하도록 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="91779-159">Instead, you must use archiving policies to enable internal and/or external archiving.</span></span> <span data-ttu-id="91779-160">Lync Server 2013을 설치할 때 다음 두 가지 속성이 포함 된 하나의 전역 보관 정책만 설치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="91779-160">When you install Lync Server 2013 you also install a single, global archiving policy that contains two properties:</span></span>

  - <span data-ttu-id="91779-161">**ArchiveInternal**.</span><span class="sxs-lookup"><span data-stu-id="91779-161">**ArchiveInternal**.</span></span> <span data-ttu-id="91779-162">True ($True)로 설정 하는 경우 조직에서 Active Directory 계정이 있는 사용자만 포함 하는 내부 통신 세션을 보관 하는 것을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="91779-162">When set to True ($True) indicates that internal communication sessions involving only users who have Active Directory accounts in your organization) will be archived.</span></span>

  - <span data-ttu-id="91779-163">**ArchiveExternal**.</span><span class="sxs-lookup"><span data-stu-id="91779-163">**ArchiveExternal**.</span></span> <span data-ttu-id="91779-164">True ($True)로 설정 되 면 내부 통신 세션 (조직에서 Active Directory 계정이 없는 사용자가 하나 이상 포함 된 세션)이 보관 됨을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="91779-164">When set to True ($True) indicates that internal communication sessions (sessions involving at least one user who does not have an Active Directory account in your organization) will be archived.</span></span>

<span data-ttu-id="91779-165">기본적으로 이러한 속성 값은 모두 False로 설정 되며,이는 내부 및 외부 통신 세션도 보관 되지 않는다는 의미입니다.</span><span class="sxs-lookup"><span data-stu-id="91779-165">By default, both of these property values are set to False, meaning that neither internal nor external communication sessions are archived.</span></span> <span data-ttu-id="91779-166">전역 정책을 수정 하려면 Lync Server 관리 셸과 CsArchivingPolicy cmdlet을 사용 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="91779-166">To modify the global policy, you can use the Lync Server Management Shell and the Set-CsArchivingPolicy cmdlet.</span></span> <span data-ttu-id="91779-167">이 명령을 사용 하 여 내부 및 외부 통신 세션을 모두 보관할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91779-167">This command enables the archiving of both internal and external communication sessions:</span></span>

    Set-CsArchivingPolicy -Identity "global" -ArchiveInternal $True -ArchiveExternal $True

<span data-ttu-id="91779-168">또는 New-CsArchivingPolicy를 사용 하 여 사이트 범위 또는 사용자 단위 범위에서 새 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91779-168">Alternatively, you can use the New-CsArchivingPolicy to create a new policy at either the site scope or the per-user scope.</span></span> <span data-ttu-id="91779-169">예를 들어이 명령은 RedmondArchivingPolicy 이라는 새 사용자별 보관 정책을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="91779-169">For example, this command creates a new per-user archiving policy named RedmondArchivingPolicy:</span></span>

    New-CsArchivingPolicy -Identity "RedmondArchivingPolicy" -ArchiveInternal $True -ArchiveExternal $True

<span data-ttu-id="91779-170">사용자별 정책을 만든 경우 해당 사용자에 게 해당 정책을 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="91779-170">If you create a per-user policy you will then need to assign that policy to the appropriate users.</span></span> <span data-ttu-id="91779-171">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="91779-171">For example:</span></span>

    Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName  "RedmondArchivingPolicy"

<span data-ttu-id="91779-172">또한, Lync Server 제어판을 사용 하 여 보관 정책을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91779-172">Archiving policies can also be managed by using the Lync Server Control Panel.</span></span> <span data-ttu-id="91779-173">제어판에서 **모니터링 및 보관** 을 클릭 한 다음 **보관 정책을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="91779-173">Within the Control Panel, click **Monitoring and Archiving** and then click **Archiving Policy**.</span></span> <span data-ttu-id="91779-174">기존 정책을 수정 하려면 정책을 두 번 클릭 하 고 (예: 전역) **보관 정책 편집** 창에서 **내부 통신 보관** 및 **외부 통신 보관** 확인란을 필요에 따라 선택 하거나 선택을 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="91779-174">To modify an existing policy, double-click the policy (e.g., Global) and then, in the **Edit Archiving Policy** pane, select or clear the **Archive internal communications** and the **Archive external communications** checkboxes as needed.</span></span> <span data-ttu-id="91779-175">새 보관 정책을 만들려면 **새로 만들기** 를 클릭 한 다음 **사이트 정책** 또는 **사용자 정책을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="91779-175">To create a new archiving policy, click **New** and then select either **Site policy** or **User policy**.</span></span> <span data-ttu-id="91779-176">새 사용자 정책을 만드는 경우 **사용자** 탭에서 해당 사용자 계정에 액세스 하 여 새 정책을 해당 사용자에 게 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="91779-176">If you create a new user policy then you must access the appropriate user accounts (from the **Users** tab) and assign those users the new policy.</span></span>

</div>

<div>

## <a name="step-3-configuring-the-exchangearchivingpolicy-property"></a><span data-ttu-id="91779-177">3 단계: ExchangeArchivingPolicy 속성 구성</span><span class="sxs-lookup"><span data-stu-id="91779-177">Step 3: Configuring the ExchangeArchivingPolicy Property</span></span>

<span data-ttu-id="91779-178">Lync Server 2013 및 Exchange 2013가 서로 다른 포리스트에 있는 경우에는 보관 구성 설정에서 Exchange 보관을 사용 하도록 설정 하는 것 만으로는 충분 하지 않습니다. 이로 인해 인스턴트 메시지와 웹 회의에 대 한 증명서는 Exchange에 보관 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="91779-178">If Lync Server 2013 and Exchange 2013 are located in different forests then it is not enough to simply enable Exchange archiving in the archiving configuration settings; that will not result in instant messaging and Web conferencing transcripts being archived in Exchange.</span></span> <span data-ttu-id="91779-179">대신 관련 Lync Server 사용자 계정 각각에 대해 ExchangeArchivingPolicy 속성을 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="91779-179">Instead, you must also configure the ExchangeArchivingPolicy property on each of the relevant Lync Server user accounts.</span></span> <span data-ttu-id="91779-180">이 속성은 다음 네 가지 가능한 값 중 하나로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91779-180">This property can be set to one of four possible values:</span></span>

1.  <span data-ttu-id="91779-181">초기화.</span><span class="sxs-lookup"><span data-stu-id="91779-181">Uninitialized.</span></span> <span data-ttu-id="91779-182">보관이 사용자의 Exchange 사서함에 대해 구성 된 원본 위치 유지 설정을 기반으로 함을 나타냅니다. 사용자의 사서함에 원본 위치 유지가 사용 하도록 설정 되어 있지 않으면 사용자에 게 Lync Server에 메신저 대화 및 웹 회의 기록 보관이 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="91779-182">Indicates that archiving will be based on the In-Place Hold settings configured for the user's Exchange mailbox; if In-Place Hold has not been enabled on the user's mailbox then the user will have his or her messaging and Web conferencing transcripts archived in Lync Server.</span></span>

2.  <span data-ttu-id="91779-183">**UseLyncArchivingPolicy**.</span><span class="sxs-lookup"><span data-stu-id="91779-183">**UseLyncArchivingPolicy**.</span></span> <span data-ttu-id="91779-184">사용자의 인스턴트 메시지 및 웹 회의 내용 작성을 Exchange가 아닌 Lync Server에 보관 해야 함을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="91779-184">Indicates that the user's instant messaging and Web conferencing transcripts should be archived in Lync Server rather than in Exchange.</span></span>

3.  <span data-ttu-id="91779-185">**Noarchiving**.</span><span class="sxs-lookup"><span data-stu-id="91779-185">**NoArchiving**.</span></span> <span data-ttu-id="91779-186">사용자의 인스턴트 메시지 및 웹 회의 내용에 대 한 보관이 금지 됨을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="91779-186">Indicates that the user's instant messaging and Web conferencing transcripts should not be archived at all.</span></span> <span data-ttu-id="91779-187">이 설정은 사용자에 게 할당 된 모든 Lync Server 보관 정책 보다 우선 합니다.</span><span class="sxs-lookup"><span data-stu-id="91779-187">Note that this setting overrides any Lync Server archiving policies assigned to the user.</span></span>

4.  <span data-ttu-id="91779-188">**ArchivingToExchange**.</span><span class="sxs-lookup"><span data-stu-id="91779-188">**ArchivingToExchange**.</span></span> <span data-ttu-id="91779-189">사용자의 사서함에 할당 되지 않은 원본 위치 유지 설정에 관계 없이 사용자의 인스턴트 메시지 및 웹 회의 기록에 대해 Exchange에 보관 해야 함을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="91779-189">Indicates that the user's instant messaging and Web conferencing transcripts should be archived to Exchange regardless of the In-Place Hold settings that have (or have not) been assigned to the user's mailbox.</span></span>

<span data-ttu-id="91779-190">예를 들어 인스턴트 메시지와 웹 회의 기록 내용이 항상 Exchange에 보관 되도록 사용자 계정을 구성 하려면 Lync Server 관리 셸에서와 유사한 명령을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91779-190">For example, to configure a user account so that instant messaging and Web conferencing transcripts are always archived to Exchange you can use a command similar to this from the Lync Server Management Shell:</span></span>

    Set-CsUser -Identity "Ken Myer" -ExchangeArchivingPolicy ArchivingToExchange

<span data-ttu-id="91779-191">사용자 그룹에 대해 동일한 보관 정책을 설정 하려는 경우 (예: 지정 된 등록자 풀에 속한 모든 사용자) 다음과 같은 명령을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91779-191">If you want to set the same archiving policy for a group of users (for example, all the users homed on a specified Registrar pool) you can use a command similar to this:</span></span>

    Get-CsUser -Filter {RegistrarPool -eq "atl-cs-001.litwareinc.com"} | Set-CsUser -ExchangeArchivingPolicy ArchivingToExchange

<span data-ttu-id="91779-192">ExchangeArchivingPolicy 속성의 값을 구성 하려면 Lync Server Management Shell (및 Windows PowerShell)을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="91779-192">Note that you must use the Lync Server Management Shell (and Windows PowerShell) in order to configure value of the ExchangeArchivingPolicy property.</span></span> <span data-ttu-id="91779-193">이 속성은 Lync Server 제어판의 관리자에 게 노출 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="91779-193">This property is not exposed to administrators in the Lync Server Control Panel.</span></span>

<span data-ttu-id="91779-194">특정 보관 정책을 할당 한 모든 사용자의 목록을 보려면 ExchangeArchivingPolicy 속성을 설정한 모든 사용자의 Active Directory 표시 이름을 반환 하는 다음과 유사한 명령을 사용할 수 있습니다... 초기화 되지 않음:</span><span class="sxs-lookup"><span data-stu-id="91779-194">If you would like to view a list of all the users who have been assigned a specific archiving policy then you can use a command similar to the following, which returns the Active Directory display name of all the users who have had the ExchangeArchivingPolicy property set to Uninitialized:</span></span>

    Get-CsUser | Where-Object {$_.ExchangeArchivingPolicy -eq "Uninitialized"} | Select-Object DisplayName

<span data-ttu-id="91779-195">마찬가지로이 명령은 ExchangeArchivingPolicy 속성이 UseLyncArchivingPolicy로 설정 되지 않은 사용자의 표시 이름을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="91779-195">Likewise, this command returns the display name of the users who have not have the ExchangeArchivingPolicy property set to UseLyncArchivingPolicy:</span></span>

    Get-CsUser | Where-Object {$_.ExchangeArchivingPolicy -ne "UseLyncArchivingPolicy"} | Select-Object DisplayName

</div>

</div>

<span> </span>

</div>

</div>

</div>

