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
ms.openlocfilehash: 85a9a1d035994c143336abc83312fb56f67b927d
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42180631"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-microsoft-lync-server-2013-to-use-microsoft-exchange-server-2013-archiving"></a><span data-ttu-id="af65f-102">Microsoft Exchange Server 2013 보관을 사용 하도록 Microsoft Lync Server 2013 구성</span><span class="sxs-lookup"><span data-stu-id="af65f-102">Configuring Microsoft Lync Server 2013 to use Microsoft Exchange Server 2013 archiving</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="af65f-103">_**마지막으로 수정 된 항목:** 2014-06-24_</span><span class="sxs-lookup"><span data-stu-id="af65f-103">_**Topic Last Modified:** 2014-06-24_</span></span>

<span data-ttu-id="af65f-104">Microsoft Lync Server 2013에서는 관리자에 게 SQL Server 데이터베이스가 아닌 사용자의 Microsoft Exchange Server 2013 사서함에 인스턴트 메시징 및 웹 회의 기록 보관 옵션을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="af65f-104">Microsoft Lync Server 2013 gives administrators the option of having instant messaging and Web conferencing transcripts archived to a user's Microsoft Exchange Server 2013 mailbox rather than a SQL Server database.</span></span> <span data-ttu-id="af65f-105">이 옵션을 사용 하도록 설정 하면 사용자 사서함의 제거 폴더에 성적이 기록 됩니다.</span><span class="sxs-lookup"><span data-stu-id="af65f-105">If you enable this option, transcripts are written to the Purges folder in the user's mailbox.</span></span> <span data-ttu-id="af65f-106">제거 폴더는 복구 가능한 항목 폴더에 있는 숨겨진 폴더입니다.</span><span class="sxs-lookup"><span data-stu-id="af65f-106">The Purges folder is a hidden folder found in the Recoverable Items folder.</span></span> <span data-ttu-id="af65f-107">이 폴더가 최종 사용자에 게 표시 되지 않는 경우에도 폴더는 Exchange 검색 엔진에 의해 인덱싱되 며 Exchange 사서함 검색 및/또는 Microsoft SharePoint Server 2013을 사용 하 여 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af65f-107">Although this folder is not visible to end-users, the folder is indexed by the Exchange search engine and can be discovered by using Exchange mailbox search and/or Microsoft SharePoint Server 2013.</span></span> <span data-ttu-id="af65f-108">정보는 Exchange 원본 위치 유지 기능에서 사용 하는 것과 동일한 폴더에 저장 되므로 전자 메일 보관 및 기타 Exchange 통신을 담당 하는 관리자는 단일 도구를 사용 하 여에 대해 보관 된 모든 전자 통신을 검색할 수 있습니다. 가.</span><span class="sxs-lookup"><span data-stu-id="af65f-108">Because information is stored in the same folder used by the Exchange In-Place Hold feature (responsible for archiving email and other Exchange communications), administrators can use a single tool to search for all the electronic communications archived for a user.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="af65f-109">Lync 대화 보관을 완전히 사용 하지 않도록 설정 하려면 Lync 대화 기록도 사용 하지 않도록 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="af65f-109">To completely disable archiving of Lync conversation, you must also disable Lync conversation history.</span></span> <span data-ttu-id="af65f-110">자세한 내용은 Lync Server 2013, <A href="https://docs.microsoft.com/powershell/module/skype/New-CsClientPolicy">신규-csclientpolicy</A>및 <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy">Set csclientpolicy</A> <A href="lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md">에서 내부 및 외부 통신의 보관 관리</A>항목을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="af65f-110">For more information, see the following topics: <A href="lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md">Managing the Archiving of internal and external communications in Lync Server 2013</A>, <A href="https://docs.microsoft.com/powershell/module/skype/New-CsClientPolicy">New-CsClientPolicy</A>, and <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy">Set-CsClientPolicy</A>.</span></span>



</div>

<span data-ttu-id="af65f-111">Exchange 2013에 성적 보관용을 보관 하려면 두 서버 간에 서버 간 인증을 구성 하는 것으로 시작 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="af65f-111">In order to archive transcripts to Exchange 2013 you must begin by configuring server-to-server authentication between the two servers.</span></span> <span data-ttu-id="af65f-112">서버 간 인증이 수행 된 후에는 Microsoft Lync Server 2013에서 다음 작업을 수행할 수 있습니다 (설정 및 구성에 따라 이러한 작업을 모두 완료 하지 않아도 될 수 있음).</span><span class="sxs-lookup"><span data-stu-id="af65f-112">After server-to-server authentication is in place you can then carry out the following tasks in Microsoft Lync Server 2013 (note that, depending on your setup and configuration, you might not need to complete all of these tasks):</span></span>

1.  <span data-ttu-id="af65f-113">Lync Server 보관 구성 설정을 수정 하 여 Exchange 보관을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="af65f-113">Enable Exchange archiving by modifying your Lync Server archiving configuration settings.</span></span> <span data-ttu-id="af65f-114">이 단계는 모든 배포에 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="af65f-114">This step is required for all deployments.</span></span>

2.  <span data-ttu-id="af65f-115">사용자에 대 한 내부 및/또는 외부 통신에 대해 보관을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="af65f-115">Enable archiving for internal and/or external communications for your users.</span></span> <span data-ttu-id="af65f-116">이 단계는 모든 배포에 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="af65f-116">This step is required for all deployments.</span></span>

3.  <span data-ttu-id="af65f-117">각 사용자에 대해 ExchangeArchivingPolicy 속성을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="af65f-117">Configure the ExchangeArchivingPolicy property for each user.</span></span> <span data-ttu-id="af65f-118">이 단계는 Lync Server 및 Exchange 에서만 서로 다른 포리스트에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af65f-118">This step is only required in Lync Server and Exchange are located in different forests.</span></span>

<div>

## <a name="step-1-enabling-exchange-archiving"></a><span data-ttu-id="af65f-119">1 단계: Exchange 보관 사용</span><span class="sxs-lookup"><span data-stu-id="af65f-119">Step 1: Enabling Exchange Archiving</span></span>

<span data-ttu-id="af65f-120">Lync Server의 보관은 기본적으로 보관 구성 설정을 사용 하 여 관리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="af65f-120">Archiving in Lync Server is primarily managed by using the archiving configuration settings.</span></span> <span data-ttu-id="af65f-121">Lync Server 2013을 설치 하면 이러한 설정의 단일 전역 컬렉션이 자동으로 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="af65f-121">When you install Lync Server 2013 you are automatically given a single, global collection of these settings.</span></span> <span data-ttu-id="af65f-122">(필요에 따라 관리자가 사이트 범위에서 새 보관 설정 모음을 만들 수 있습니다.) 기본적으로는 전역 설정에서 보관을 사용 하도록 설정 되지 않으며, 이러한 설정에서 Exchange 보관을 사용 하도록 설정 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="af65f-122">(Administrators can optionally create new collections of archiving settings at the site scope.) By default, archiving is not enabled in the global settings, nor is Exchange archiving enabled in these settings.</span></span> <span data-ttu-id="af65f-123">Exchange 보관 관리자를 사용 하려면 이러한 구성 설정에서 EnableArchiving 및 EnableExchangeArchiving 속성을 모두 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="af65f-123">In order to use Exchange archiving administrators must configure both the EnableArchiving and the EnableExchangeArchiving properties in these configuration settings.</span></span> <span data-ttu-id="af65f-124">EnableArchiving 속성은 다음과 같은 세 가지 가능한 값 중 하나로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af65f-124">The EnableArchiving property can be set to one of three possible values:</span></span>

  - <span data-ttu-id="af65f-125">**없음**</span><span class="sxs-lookup"><span data-stu-id="af65f-125">**None**.</span></span> <span data-ttu-id="af65f-126">보관을 사용 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="af65f-126">Archiving is disabled.</span></span> <span data-ttu-id="af65f-127">이 값은 기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="af65f-127">This is the default value.</span></span> <span data-ttu-id="af65f-128">EnableArchiving이 없음으로 설정 되어 있으면 Lync Server 보관 데이터베이스 또는 Exchange 2013에 아무 것도 보관 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="af65f-128">If EnableArchiving is set to None then nothing will be archived in either your Lync Server archiving database or in Exchange 2013.</span></span>

  - <span data-ttu-id="af65f-129">**Imonly**</span><span class="sxs-lookup"><span data-stu-id="af65f-129">**ImOnly**.</span></span> <span data-ttu-id="af65f-130">인스턴트 메시지의 경우에만 보관 됩니다.</span><span class="sxs-lookup"><span data-stu-id="af65f-130">Only instant message transcripts are archived.</span></span> <span data-ttu-id="af65f-131">Exchange 보관을 사용 하도록 설정 된 경우 이러한 성적 증명서는 Exchange 2013에 보관 됩니다.</span><span class="sxs-lookup"><span data-stu-id="af65f-131">If Exchange archiving is enabled these transcripts will be archived in Exchange 2013.</span></span> <span data-ttu-id="af65f-132">Exchange 보관을 사용 하지 않는 경우 이러한 성적 증명서는 Lync Server에 보관 됩니다.</span><span class="sxs-lookup"><span data-stu-id="af65f-132">If Exchange archiving is disabled then these transcripts will be archived to Lync Server.</span></span>

  - <span data-ttu-id="af65f-133">**Imandwebconf**</span><span class="sxs-lookup"><span data-stu-id="af65f-133">**ImAndWebConf**.</span></span> <span data-ttu-id="af65f-134">인스턴트 메시지 성적 증명서와 웹 회의 기록도 모두 보관 됩니다.</span><span class="sxs-lookup"><span data-stu-id="af65f-134">Both instant message transcripts and Web conferencing transcripts are archived.</span></span> <span data-ttu-id="af65f-135">Exchange 보관을 사용 하도록 설정 된 경우 이러한 성적 증명서는 Exchange 2013에 보관 됩니다.</span><span class="sxs-lookup"><span data-stu-id="af65f-135">If Exchange archiving is enabled these transcripts will be archived in Exchange 2013.</span></span> <span data-ttu-id="af65f-136">Exchange 보관을 사용 하지 않는 경우 이러한 성적 증명서는 Lync Server에 보관 됩니다.</span><span class="sxs-lookup"><span data-stu-id="af65f-136">If Exchange archiving is disabled then these transcripts will be archived to Lync Server.</span></span>

<span data-ttu-id="af65f-137">EnableExchangeArchiving 속성은 Boolean 값입니다. EnableExchangeArchiving를 True ($True)로 설정 하 여 exchange 보관을 사용 하거나 EnableExchangeArchiving를 False ($False)로 설정 하 여 Exchange 아카이빙를 사용 하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af65f-137">The EnableExchangeArchiving property is a Boolean value: set EnableExchangeArchiving to True ($True) to enable Exchange archiving or set EnableExchangeArchiving to False ($False) to disable Exchange archiving.</span></span> <span data-ttu-id="af65f-138">예를 들어이 명령을 사용 하면 인스턴트 메시징 성적 보관용 보관이 가능 하 고 Exchange 보관도 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af65f-138">For example, this command enables the archiving of instant messaging transcripts and also enables Exchange archiving:</span></span>

    Set-CsArchivingConfiguration -Identity "global" -EnableArchiving ImOnly -EnableExchangeArchiving $True

<span data-ttu-id="af65f-139">Exchange 보관을 사용 하지 않도록 설정 하려면 다음과 같은 명령을 사용 합니다 (예: 인스턴트 메시징 보관을 사용 하지만 Exchange로 보관을 사용 하지 않도록 설정 함) (즉, 다음의 경우에는 다음과 같이 Lync Server에 보관 됨).</span><span class="sxs-lookup"><span data-stu-id="af65f-139">To disable Exchange archiving, use a command similar to the following, which enables instant messaging archiving but disables archiving to Exchange (in other words, transcripts will be archived to Lync Server):</span></span>

    Set-CsArchivingConfiguration -Identity "global" -EnableArchiving ImOnly -EnableExchangeArchiving $False

<div>


> [!NOTE]  
> <span data-ttu-id="af65f-140">EnableArchiving 속성이 ' 없음 '으로 설정 되 면 Lync Server에서는 인스턴트 메시징 및 웹 회의 기록이 전혀 보관 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="af65f-140">If the EnableArchiving property is set to None then Lync Server will not archive instant messaging and Web conferencing transcripts at all.</span></span> <span data-ttu-id="af65f-141">이 경우 서버는 EnableExchangeArchiving에 대해 구성 된 값만 무시 합니다.</span><span class="sxs-lookup"><span data-stu-id="af65f-141">In that case, the server will simply ignore the value configured for EnableExchangeArchiving.</span></span>



</div>

<span data-ttu-id="af65f-142">Lync Server 제어판을 사용 하 여 Exchange 보관을 사용 하거나 사용 하지 않도록 설정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af65f-142">Exchange archiving can also be enabled (or disabled) by using the Lync Server Control Panel.</span></span> <span data-ttu-id="af65f-143">이렇게 하려면 다음 절차를 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="af65f-143">To do that, complete the following procedure:</span></span>

1.  <span data-ttu-id="af65f-144">제어판에서 **모니터링 및 보관**을 클릭 하 고 **보관 구성을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="af65f-144">In Control Panel, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>

2.  <span data-ttu-id="af65f-145">**보관 구성** 탭에서 수정할 보관 설정 컬렉션 (예: **전역** 모음)을 두 번 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="af65f-145">On the **Archiving Configuration** tab, double-click the collection of archiving settings to be modified (for example, the **Global** collection).</span></span>

3.  <span data-ttu-id="af65f-146">**보관 설정 편집** 창에서 **보관 설정** 드롭다운 목록을 클릭 하 고 메신저 대화 **세션 보관** (인스턴트 메시징 세션만 보관) 또는 **im 및 웹 회의 세션 보관** (인스턴트 메시징 및 웹 회의 세션을 모두 보관)을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="af65f-146">In the **Edit Archiving Setting** pane, click the **Archiving setting** dropdown list and select either **Archive IM sessions** (to archive just instant messaging sessions) or **Archive IM and web conferencing sessions** (to archive both instant messaging and Web conferencing sessions).</span></span>

4.  <span data-ttu-id="af65f-147">보관할 항목을 선택한 후 exchange **Server 통합** 확인란을 선택 하 여 exchange 보관을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="af65f-147">After choosing the items to be archived, select the **Exchange Server integration** checkbox to enable Exchange archiving.</span></span> <span data-ttu-id="af65f-148">Exchange 보관을 사용 하지 않도록 설정 하려면이 확인란의 선택을 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="af65f-148">To disable Exchange archiving, clear this checkbox.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="af65f-149">보관 <STRONG>설정을</STRONG> <STRONG>사용 하지 않도록</STRONG>설정 된 경우에는 <STRONG>Exchange Server 통합</STRONG> 확인란을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="af65f-149">The <STRONG>Exchange Server integration</STRONG> checkbox will not be available if the <STRONG>Archiving setting</STRONG> is set to <STRONG>Disable archiving</STRONG>.</span></span> <span data-ttu-id="af65f-150">보관을 먼저 사용 하도록 설정한 다음 Exchange 보관을 사용 하도록 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="af65f-150">You must enable archiving first and then enable Exchange archiving.</span></span>



</div>

<span data-ttu-id="af65f-151">Lync Server 2013 및 Exchange 2013이 동일한 포리스트에 있는 경우에는 개별 사용자에 대 한 보관을 수행 하 고, 또는 Exchange 2013에 전자 메일 계정을 가진 사용자에 대 한 경우에는 Exchange 원본 위치 유지 정책을 사용 하 여 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="af65f-151">If Lync Server 2013 and Exchange 2013 are located in the same forest then archiving for individual users (or at least for users who have email accounts on Exchange 2013) is managed by using Exchange In-Place Hold policies.</span></span> <span data-ttu-id="af65f-152">이전 버전의 Exchange에 있는 사용자가 있는 경우 해당 사용자에 대 한 보관은 Lync Server 보관 정책을 사용 하 여 관리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="af65f-152">If you have users who are homed on a previous version of Exchange then archiving for those users will be managed by using Lync Server archiving policies.</span></span> <span data-ttu-id="af65f-153">Exchange 2013에 계정이 있는 사용자만 Lync 노트를 Exchange에 보관할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af65f-153">Note that only users with accounts on Exchange 2013 can have their Lync transcripts archived to Exchange.</span></span>

<span data-ttu-id="af65f-154">Lync Server 2013 및 Exchange 2013이 서로 다른 포리스트에 있는 경우 개별 사용자에 대 한 보관은 각 개별 사용자 계정에 대해 ExchangeArchivingPolicy 속성을 구성 하 여 관리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="af65f-154">If Lync Server 2013 and Exchange 2013 are located in different forests then archiving for individual users is managed by configuring the ExchangeArchivingPolicy property for each individual user account.</span></span> <span data-ttu-id="af65f-155">자세한 내용은 3 단계를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="af65f-155">See Step 3 for more information.</span></span>

</div>

<div>

## <a name="step-2-enabling-the-archiving-of-internal-andor-external-communications"></a><span data-ttu-id="af65f-156">2 단계: 내부 및/또는 외부 통신 보관을 사용 하도록 설정</span><span class="sxs-lookup"><span data-stu-id="af65f-156">Step 2: Enabling the Archiving of Internal and/or External Communications</span></span>

<span data-ttu-id="af65f-157">보관 (및 Exchange 보관)을 사용 하도록 설정한 후에는 적절 한 보관 정책을 수정 하 여 사용자 세션이 실제로 보관 되도록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="af65f-157">After you have enabled archiving (and Exchange archiving) you must then modify the appropriate archiving policies to ensure that user sessions are actually archived.</span></span> <span data-ttu-id="af65f-158">보관 (1 단계)을 사용 하면 Lync Server에서 인스턴트 메시징 및 웹 회의 기록 보관을 시작 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="af65f-158">Note that simply enabling archiving (Step 1) does not cause Lync Server to begin archiving instant messaging and Web conferencing transcripts.</span></span> <span data-ttu-id="af65f-159">대신 내부 및/또는 외부 보관을 사용 하도록 설정 하려면 보관 정책을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="af65f-159">Instead, you must use archiving policies to enable internal and/or external archiving.</span></span> <span data-ttu-id="af65f-160">Lync Server 2013을 설치 하면 다음 두 가지 속성을 포함 하는 단일 전역 보관 정책도 설치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="af65f-160">When you install Lync Server 2013 you also install a single, global archiving policy that contains two properties:</span></span>

  - <span data-ttu-id="af65f-161">**다음과 같이 archiveinternal**</span><span class="sxs-lookup"><span data-stu-id="af65f-161">**ArchiveInternal**.</span></span> <span data-ttu-id="af65f-162">True ($True)로 설정 하는 경우 조직에 Active Directory 계정이 있는 사용자만 포함 된 내부 통신 세션이 보관 됨을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="af65f-162">When set to True ($True) indicates that internal communication sessions involving only users who have Active Directory accounts in your organization) will be archived.</span></span>

  - <span data-ttu-id="af65f-163">**ArchiveExternal**</span><span class="sxs-lookup"><span data-stu-id="af65f-163">**ArchiveExternal**.</span></span> <span data-ttu-id="af65f-164">True ($True)로 설정 하면 내부 통신 세션 (조직에서 Active Directory 계정이 없는 사용자를 한 명 이상 포함 하는 세션)이 보관 됨을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="af65f-164">When set to True ($True) indicates that internal communication sessions (sessions involving at least one user who does not have an Active Directory account in your organization) will be archived.</span></span>

<span data-ttu-id="af65f-165">기본적으로 이러한 속성 값은 모두 False로 설정 되어 있으며 내부 및 외부 통신 세션은 보관 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="af65f-165">By default, both of these property values are set to False, meaning that neither internal nor external communication sessions are archived.</span></span> <span data-ttu-id="af65f-166">전역 정책을 수정 하려면 Lync Server 관리 셸 및 Grant-csarchivingpolicy cmdlet을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af65f-166">To modify the global policy, you can use the Lync Server Management Shell and the Set-CsArchivingPolicy cmdlet.</span></span> <span data-ttu-id="af65f-167">이 명령은 내부 및 외부 통신 세션의 보관을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="af65f-167">This command enables the archiving of both internal and external communication sessions:</span></span>

    Set-CsArchivingPolicy -Identity "global" -ArchiveInternal $True -ArchiveExternal $True

<span data-ttu-id="af65f-168">또는 Grant-csarchivingpolicy를 사용 하 여 사이트 범위 또는 사용자별 범위에서 새 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af65f-168">Alternatively, you can use the New-CsArchivingPolicy to create a new policy at either the site scope or the per-user scope.</span></span> <span data-ttu-id="af65f-169">예를 들어이 명령은 RedmondArchivingPolicy 라는 새 사용자별 보관 정책을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="af65f-169">For example, this command creates a new per-user archiving policy named RedmondArchivingPolicy:</span></span>

    New-CsArchivingPolicy -Identity "RedmondArchivingPolicy" -ArchiveInternal $True -ArchiveExternal $True

<span data-ttu-id="af65f-170">사용자별 정책을 만드는 경우 해당 사용자에 게 해당 정책을 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="af65f-170">If you create a per-user policy you will then need to assign that policy to the appropriate users.</span></span> <span data-ttu-id="af65f-171">예:</span><span class="sxs-lookup"><span data-stu-id="af65f-171">For example:</span></span>

    Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName  "RedmondArchivingPolicy"

<span data-ttu-id="af65f-172">또한 Lync Server 제어판을 사용 하 여 보관 정책을 관리할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af65f-172">Archiving policies can also be managed by using the Lync Server Control Panel.</span></span> <span data-ttu-id="af65f-173">제어판에서 **모니터링 및 보관** 을 클릭 하 고 **보관 정책을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="af65f-173">Within the Control Panel, click **Monitoring and Archiving** and then click **Archiving Policy**.</span></span> <span data-ttu-id="af65f-174">기존 정책을 수정 하려면 정책 (예: 전역)을 두 번 클릭 하 고 **보관 정책 편집** 창에서 필요에 따라 **내부 통신 보관** 및 **외부 통신 보관** 확인란을 선택 하거나 선택을 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="af65f-174">To modify an existing policy, double-click the policy (e.g., Global) and then, in the **Edit Archiving Policy** pane, select or clear the **Archive internal communications** and the **Archive external communications** checkboxes as needed.</span></span> <span data-ttu-id="af65f-175">새 보관 정책을 만들려면 **새로 만들기** 를 클릭 하 고 **사이트 정책** 또는 **사용자 정책을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="af65f-175">To create a new archiving policy, click **New** and then select either **Site policy** or **User policy**.</span></span> <span data-ttu-id="af65f-176">새 사용자 정책을 만드는 경우 **사용자** 탭에서 해당 하는 사용자 계정에 액세스 하 여 사용자를 새 정책에 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="af65f-176">If you create a new user policy then you must access the appropriate user accounts (from the **Users** tab) and assign those users the new policy.</span></span>

</div>

<div>

## <a name="step-3-configuring-the-exchangearchivingpolicy-property"></a><span data-ttu-id="af65f-177">3 단계: ExchangeArchivingPolicy 속성 구성</span><span class="sxs-lookup"><span data-stu-id="af65f-177">Step 3: Configuring the ExchangeArchivingPolicy Property</span></span>

<span data-ttu-id="af65f-178">Lync Server 2013 및 Exchange 2013이 서로 다른 포리스트에 있는 경우 보관 구성 설정에서 단순히 Exchange 보관을 사용 하도록 설정 하는 것 만으로는 충분 하지 않습니다. 이로 인해 인스턴트 메시징 및 웹 회의 기록이 Exchange에 보관 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="af65f-178">If Lync Server 2013 and Exchange 2013 are located in different forests then it is not enough to simply enable Exchange archiving in the archiving configuration settings; that will not result in instant messaging and Web conferencing transcripts being archived in Exchange.</span></span> <span data-ttu-id="af65f-179">대신 관련 Lync Server 사용자 계정 각각에 대해 ExchangeArchivingPolicy 속성을 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="af65f-179">Instead, you must also configure the ExchangeArchivingPolicy property on each of the relevant Lync Server user accounts.</span></span> <span data-ttu-id="af65f-180">이 속성은 다음과 같은 네 가지 값 중 하나로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af65f-180">This property can be set to one of four possible values:</span></span>

1.  <span data-ttu-id="af65f-181">않은.</span><span class="sxs-lookup"><span data-stu-id="af65f-181">Uninitialized.</span></span> <span data-ttu-id="af65f-182">사용자의 Exchange 사서함에 대해 구성 된 원본 위치 유지 설정에 따라 보관이 수행 됨을 나타냅니다. 사용자 사서함에 원본 위치 유지를 사용 하도록 설정 하지 않은 경우 사용자에 게 Lync Server에 보관 된 메시징 및 웹 회의 기록이 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="af65f-182">Indicates that archiving will be based on the In-Place Hold settings configured for the user's Exchange mailbox; if In-Place Hold has not been enabled on the user's mailbox then the user will have his or her messaging and Web conferencing transcripts archived in Lync Server.</span></span>

2.  <span data-ttu-id="af65f-183">**UseLyncArchivingPolicy**</span><span class="sxs-lookup"><span data-stu-id="af65f-183">**UseLyncArchivingPolicy**.</span></span> <span data-ttu-id="af65f-184">사용자의 인스턴트 메시징 및 웹 회의 기록이 Exchange가 아닌 Lync Server에 보관 되어야 함을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="af65f-184">Indicates that the user's instant messaging and Web conferencing transcripts should be archived in Lync Server rather than in Exchange.</span></span>

3.  <span data-ttu-id="af65f-185">**Noarchiving**</span><span class="sxs-lookup"><span data-stu-id="af65f-185">**NoArchiving**.</span></span> <span data-ttu-id="af65f-186">사용자의 인스턴트 메시징 및 웹 회의 성적 증명서를 전혀 보관 하지 않아야 함을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="af65f-186">Indicates that the user's instant messaging and Web conferencing transcripts should not be archived at all.</span></span> <span data-ttu-id="af65f-187">이 설정은 사용자에 게 할당 된 모든 Lync Server 보관 정책 보다 우선 합니다.</span><span class="sxs-lookup"><span data-stu-id="af65f-187">Note that this setting overrides any Lync Server archiving policies assigned to the user.</span></span>

4.  <span data-ttu-id="af65f-188">**ArchivingToExchange**</span><span class="sxs-lookup"><span data-stu-id="af65f-188">**ArchivingToExchange**.</span></span> <span data-ttu-id="af65f-189">사용자의 사서함에 할당 된 원본 위치 유지 설정에 관계 없이 사용자의 인스턴트 메시징 및 웹 회의 진행 상태를 Exchange에 보관 해야 함을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="af65f-189">Indicates that the user's instant messaging and Web conferencing transcripts should be archived to Exchange regardless of the In-Place Hold settings that have (or have not) been assigned to the user's mailbox.</span></span>

<span data-ttu-id="af65f-190">예를 들어 인스턴트 메시징 및 웹 회의 기록이 항상 Exchange에 보관 되도록 사용자 계정을 구성 하려면 Lync Server 관리 셸에서 이와 유사한 명령을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af65f-190">For example, to configure a user account so that instant messaging and Web conferencing transcripts are always archived to Exchange you can use a command similar to this from the Lync Server Management Shell:</span></span>

    Set-CsUser -Identity "Ken Myer" -ExchangeArchivingPolicy ArchivingToExchange

<span data-ttu-id="af65f-191">사용자 그룹 (예: 지정 된 등록자 풀에 있는 모든 사용자)에 대해 같은 보관 정책을 설정 하려는 경우 다음과 같은 명령을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af65f-191">If you want to set the same archiving policy for a group of users (for example, all the users homed on a specified Registrar pool) you can use a command similar to this:</span></span>

    Get-CsUser -Filter {RegistrarPool -eq "atl-cs-001.litwareinc.com"} | Set-CsUser -ExchangeArchivingPolicy ArchivingToExchange

<span data-ttu-id="af65f-192">ExchangeArchivingPolicy 속성 값을 구성 하려면 Lync Server 관리 셸 (및 Windows PowerShell)을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="af65f-192">Note that you must use the Lync Server Management Shell (and Windows PowerShell) in order to configure value of the ExchangeArchivingPolicy property.</span></span> <span data-ttu-id="af65f-193">이 속성은 Lync Server 제어판의 관리자에 게 노출 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="af65f-193">This property is not exposed to administrators in the Lync Server Control Panel.</span></span>

<span data-ttu-id="af65f-194">특정 보관 정책이 할당 된 모든 사용자의 목록을 보려면 ExchangeArchivingPolicy 속성이 설정 된 모든 사용자의 Active Directory 표시 이름을 반환 하는 다음과 같은 명령을 사용할 수 있습니다 (선택 사항). 초기화 되지 않음:</span><span class="sxs-lookup"><span data-stu-id="af65f-194">If you would like to view a list of all the users who have been assigned a specific archiving policy then you can use a command similar to the following, which returns the Active Directory display name of all the users who have had the ExchangeArchivingPolicy property set to Uninitialized:</span></span>

    Get-CsUser | Where-Object {$_.ExchangeArchivingPolicy -eq "Uninitialized"} | Select-Object DisplayName

<span data-ttu-id="af65f-195">마찬가지로이 명령은 ExchangeArchivingPolicy 속성을 UseLyncArchivingPolicy로 설정 하지 않은 사용자의 표시 이름을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="af65f-195">Likewise, this command returns the display name of the users who have not have the ExchangeArchivingPolicy property set to UseLyncArchivingPolicy:</span></span>

    Get-CsUser | Where-Object {$_.ExchangeArchivingPolicy -ne "UseLyncArchivingPolicy"} | Select-Object DisplayName

</div>

</div>

<span> </span>

</div>

</div>

</div>

