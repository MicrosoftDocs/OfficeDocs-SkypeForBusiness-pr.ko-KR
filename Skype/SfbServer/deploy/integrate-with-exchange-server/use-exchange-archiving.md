---
title: 비즈니스용 Skype 서버가 보관을 사용하도록 Exchange Server 구성
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 260346d1-edc8-4a0c-8ad2-6c2401c3c377
description: '요약: Exchange Server 2016 또는 Exchange Server 2013 및 비즈니스용 Skype 서버에 대한 IM 기록을 구성합니다.'
ms.openlocfilehash: f051e5f3798b76b5e3943893d2a18e113ae8ab16
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49833898"
---
# <a name="configure-skype-for-business-server-to-use-exchange-server-archiving"></a><span data-ttu-id="d9642-103">비즈니스용 Skype 서버가 보관을 사용하도록 Exchange Server 구성</span><span class="sxs-lookup"><span data-stu-id="d9642-103">Configure Skype for Business Server to use Exchange Server archiving</span></span>

<span data-ttu-id="d9642-104">**요약:** Exchange Server 2016 또는 Exchange Server 2013 및 비즈니스용 Skype 서버에 대한 IM 기록을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="d9642-104">**Summary:** Configure IM transcripts for Exchange Server 2016 or Exchange Server 2013 and Skype for Business Server.</span></span>

<span data-ttu-id="d9642-105">관리자는 비즈니스용 Skype 서버를 통해 인스턴트 메시징 및 웹 회의 기록을 사용자 Exchange Server 2016 또는 Exchange Server 2013 사서함에 보관할 수 SQL Server 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9642-105">Skype for Business Server gives administrators the option of having instant messaging and Web conferencing transcripts archived to a user's Exchange Server 2016 or Exchange Server 2013 mailbox rather than a SQL Server database.</span></span> <span data-ttu-id="d9642-106">이 옵션을 사용하면 사용자의 사서함에 있는 제거 폴더에 기록이 기록됩니다.</span><span class="sxs-lookup"><span data-stu-id="d9642-106">If you enable this option, transcripts are written to the Purges folder in the user's mailbox.</span></span> <span data-ttu-id="d9642-107">제거 폴더는 복구할 수 있는 항목 폴더에 있는 숨겨진 폴더입니다.</span><span class="sxs-lookup"><span data-stu-id="d9642-107">The Purges folder is a hidden folder found in the Recoverable Items folder.</span></span> <span data-ttu-id="d9642-108">이 폴더는 최종 사용자에게 표시되지만 Exchange 검색 엔진에서 폴더를 인덱싱하며 Exchange 사서함 검색 및/또는 Microsoft SharePoint Server 2013을 사용하여 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9642-108">Although this folder is not visible to end users, the folder is indexed by the Exchange search engine and can be discovered by using Exchange mailbox search and/or Microsoft SharePoint Server 2013.</span></span> <span data-ttu-id="d9642-109">정보는 Exchange In-Place 보류 기능(전자 메일 및 기타 Exchange 통신 보관)에서 사용하는 폴더에 저장되어 있기 때문에 관리자는 단일 도구를 사용하여 사용자에 대해 보관된 모든 전자 통신을 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9642-109">Because information is stored in the same folder used by the Exchange In-Place Hold feature (responsible for archiving email and other Exchange communications), administrators can use a single tool to search for all the electronic communications archived for a user.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d9642-110">대화 보관을 완전히 사용하지 않도록 설정하려면 대화 기록도 사용하지 않도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9642-110">To completely disable conversation archiving, you must also disable conversation history.</span></span> <span data-ttu-id="d9642-111">자세한 내용은 다음 항목을 참조하십시오. 비즈니스용 [Skype](https://technet.microsoft.com/library/6c2cf941-3204-4f1a-a7e0-416c828056d9.aspx)서버에서 내부 및 외부 통신 보관 관리, [New-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/new-csclientpolicy?view=skype-ps)및 [Set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="d9642-111">For more information, see the following topics: [Managing the Archiving of internal and external communications in Skype for Business Server](https://technet.microsoft.com/library/6c2cf941-3204-4f1a-a7e0-416c828056d9.aspx), [New-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/new-csclientpolicy?view=skype-ps), and [Set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps).</span></span>

<span data-ttu-id="d9642-112">기록을 보관하려면 Exchange Server 비즈니스용 Skype 서버와 서버 간 인증을 구성해야 Exchange Server.</span><span class="sxs-lookup"><span data-stu-id="d9642-112">In order to archive transcripts to Exchange Server you must begin by configuring server-to-server authentication between Skype for Business Server and Exchange Server.</span></span> <span data-ttu-id="d9642-113">서버 대 서버 인증을 설정한 후 비즈니스용 Skype 서버에서 다음 작업을 수행할 수 있습니다(설정 및 구성에 따라 이러한 작업을 모두 완료하지 않을 수도 있습니다).</span><span class="sxs-lookup"><span data-stu-id="d9642-113">After server-to-server authentication is in place, you can then carry out the following tasks in Skype for Business Server (note that, depending on your setup and configuration, you might not need to complete all of these tasks):</span></span>

1. <span data-ttu-id="d9642-114">비즈니스용 Skype 서버 보관 구성 설정을 수정하여 Exchange 보관을 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9642-114">Enable Exchange archiving by modifying your Skype for Business Server archiving configuration settings.</span></span> <span data-ttu-id="d9642-115">이 단계는 모든 배포에 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="d9642-115">This step is required for all deployments.</span></span>

2. <span data-ttu-id="d9642-116">사용자에 대한 내부 및/또는 외부 통신에 대해 보관을 사용하도록 설정</span><span class="sxs-lookup"><span data-stu-id="d9642-116">Enable archiving for internal and/or external communications for your users.</span></span> <span data-ttu-id="d9642-117">이 단계는 모든 배포에 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="d9642-117">This step is required for all deployments.</span></span>

3. <span data-ttu-id="d9642-118">각 사용자에 대해 ExchangeArchivingPolicy 속성을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="d9642-118">Configure the ExchangeArchivingPolicy property for each user.</span></span> <span data-ttu-id="d9642-119">이 단계는 비즈니스용 Skype 서버와 비즈니스용 Skype Exchange Server 포리스트에 있는 경우만 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="d9642-119">This step is only required if Skype for Business Server and Exchange Server are located in different forests.</span></span>

## <a name="step-1-enabling-exchange-archiving"></a><span data-ttu-id="d9642-120">1단계: Exchange Archiving 사용</span><span class="sxs-lookup"><span data-stu-id="d9642-120">Step 1: Enabling Exchange Archiving</span></span>

<span data-ttu-id="d9642-121">비즈니스용 Skype 서버의 보관은 주로 보관 구성 설정을 사용하여 관리됩니다.</span><span class="sxs-lookup"><span data-stu-id="d9642-121">Archiving in Skype for Business Server is primarily managed by using the archiving configuration settings.</span></span> <span data-ttu-id="d9642-122">비즈니스용 Skype 서버를 설치하면 이러한 설정의 전역 컬렉션이 자동으로 하나 부여됩니다.</span><span class="sxs-lookup"><span data-stu-id="d9642-122">When you install Skype for Business Server you are automatically given a single, global collection of these settings.</span></span> <span data-ttu-id="d9642-123">관리자는 선택적으로 사이트 범위에서 보관 설정의 새 컬렉션을 만들 수 있습니다. 기본적으로 보관은 전역 설정에서 사용하도록 설정되지 않으며 이러한 설정에서는 Exchange 보관을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d9642-123">(Administrators can optionally create new collections of archiving settings at the site scope.) By default, archiving is not enabled in the global settings, nor is Exchange archiving enabled in these settings.</span></span> <span data-ttu-id="d9642-124">Exchange 보관을 사용하려면 관리자가 이러한 구성 설정에서 EnableArchiving 및 EnableExchangeArchiving 속성을 모두 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9642-124">In order to use Exchange archiving, administrators must configure both the EnableArchiving and the EnableExchangeArchiving properties in these configuration settings.</span></span> <span data-ttu-id="d9642-125">EnableArchiving 속성은 다음 세 가지 값 중 하나로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9642-125">The EnableArchiving property can be set to one of three possible values:</span></span>

- <span data-ttu-id="d9642-126">**없음.**</span><span class="sxs-lookup"><span data-stu-id="d9642-126">**None**.</span></span> <span data-ttu-id="d9642-127">보관을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d9642-127">Archiving is disabled.</span></span> <span data-ttu-id="d9642-128">이 값은 기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="d9642-128">This is the default value.</span></span> <span data-ttu-id="d9642-129">EnableArchiving을 None으로 설정하면 비즈니스용 Skype 서버 보관 데이터베이스나 보관 데이터베이스에 보관되는 모든 것이 Exchange Server.</span><span class="sxs-lookup"><span data-stu-id="d9642-129">If EnableArchiving is set to None then nothing will be archived in either your Skype for Business Server archiving database or in Exchange Server.</span></span>

- <span data-ttu-id="d9642-130">**ImOnly**.</span><span class="sxs-lookup"><span data-stu-id="d9642-130">**ImOnly**.</span></span> <span data-ttu-id="d9642-131">인스턴트 메시지 기록만 보관됩니다.</span><span class="sxs-lookup"><span data-stu-id="d9642-131">Only instant message transcripts are archived.</span></span> <span data-ttu-id="d9642-132">Exchange 보관을 사용하도록 설정하면 이러한 기록이 보관된 Exchange Server.</span><span class="sxs-lookup"><span data-stu-id="d9642-132">If Exchange archiving is enabled, these transcripts will be archived in Exchange Server.</span></span> <span data-ttu-id="d9642-133">Exchange 보관을 사용하지 않도록 설정하면 이러한 기록이 비즈니스용 Skype 서버에 보관됩니다.</span><span class="sxs-lookup"><span data-stu-id="d9642-133">If Exchange archiving is disabled then these transcripts will be archived to Skype for Business Server.</span></span>

- <span data-ttu-id="d9642-134">**ImAndWebConf.**</span><span class="sxs-lookup"><span data-stu-id="d9642-134">**ImAndWebConf**.</span></span> <span data-ttu-id="d9642-135">인스턴트 메시지 기록과 웹 회의 기록이 모두 보관됩니다.</span><span class="sxs-lookup"><span data-stu-id="d9642-135">Both instant message transcripts and Web conferencing transcripts are archived.</span></span> <span data-ttu-id="d9642-136">Exchange 보관을 사용하도록 설정한 경우 이러한 기록은 보관된 Exchange Server.</span><span class="sxs-lookup"><span data-stu-id="d9642-136">If Exchange archiving is enabled these transcripts will be archived in Exchange Server.</span></span> <span data-ttu-id="d9642-137">Exchange 보관을 사용하지 않도록 설정하면 이러한 기록이 비즈니스용 Skype 서버에 보관됩니다.</span><span class="sxs-lookup"><span data-stu-id="d9642-137">If Exchange archiving is disabled then these transcripts will be archived to Skype for Business Server.</span></span>

<span data-ttu-id="d9642-138">EnableExchangeArchiving 속성은 Exchange 보관을 사용하도록 설정하려면 EnableExchangeArchiving을 True($True)로 설정하고 Exchange 보관을 사용하지 않도록 설정하려면 EnableExchangeArchiving을 False($False)로 설정하는 부울 값입니다.</span><span class="sxs-lookup"><span data-stu-id="d9642-138">The EnableExchangeArchiving property is a Boolean value: set EnableExchangeArchiving to True ($True) to enable Exchange archiving or set EnableExchangeArchiving to False ($False) to disable Exchange archiving.</span></span> <span data-ttu-id="d9642-139">예를 들어 다음 명령은 인스턴트 메시징 문자를 보관할 수 있도록 하지만 Exchange 보관도 사용할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9642-139">For example, this command enables the archiving of instant messaging transcripts and also enables Exchange archiving:</span></span>

```powershell
Set-CsArchivingConfiguration -Identity "global" -EnableArchiving ImOnly -EnableExchangeArchiving $True
```

<span data-ttu-id="d9642-140">Exchange 보관을 사용하지 않도록 설정하기 위해 인스턴트 메시징 보관을 사용하지만 Exchange에 보관을 사용하지 않도록 설정하는 다음과 같은 명령을 사용하세요(즉, 기록은 비즈니스용 Skype 서버에 보관됨).</span><span class="sxs-lookup"><span data-stu-id="d9642-140">To disable Exchange archiving, use a command similar to the following, which enables instant messaging archiving but disables archiving to Exchange (in other words, transcripts will be archived to Skype for Business Server):</span></span>

```powershell
Set-CsArchivingConfiguration -Identity "global" -EnableArchiving ImOnly -EnableExchangeArchiving $False
```

> [!NOTE]
> <span data-ttu-id="d9642-141">EnableArchiving 속성을 None으로 설정하면 비즈니스용 Skype 서버에서 인스턴트 메시징 및 웹 회의 기록을 보관하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d9642-141">If the EnableArchiving property is set to None, then Skype for Business Server will not archive instant messaging and Web conferencing transcripts at all.</span></span> <span data-ttu-id="d9642-142">이 경우 서버는 EnableExchangeArchiving에 대해 구성된 값을 무시합니다.</span><span class="sxs-lookup"><span data-stu-id="d9642-142">In that case, the server will simply ignore the value configured for EnableExchangeArchiving.</span></span>

<span data-ttu-id="d9642-143">비즈니스용 Skype 서버를 사용하여 Exchange 보관을 사용하도록 설정하거나 사용하지 않도록 설정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9642-143">Exchange archiving can also be enabled (or disabled) by using the Skype for Business Server.</span></span> <span data-ttu-id="d9642-144">이렇게 하려면 다음 절차를 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="d9642-144">To do that, complete the following procedure:</span></span>

1. <span data-ttu-id="d9642-145">제어판에서 모니터링 및 보관을 클릭한 다음 보관 **구성을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="d9642-145">In Control Panel, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>

2. <span data-ttu-id="d9642-146">보관 **구성** 탭에서 수정할 보관 설정 컬렉션(예: **Global** 컬렉션)을 두 번 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d9642-146">On the **Archiving Configuration** tab, double-click the collection of archiving settings to be modified (for example, the **Global** collection).</span></span>

3. <span data-ttu-id="d9642-147">보관  설정 편집 창에서 보관 설정  드롭다운 목록을 클릭하고 **메신저** 세션 보관(인스턴트 메시징 세션만 보관) 또는 **메신저** 및 웹 회의 세션 보관(인스턴트 메시징 및 웹 회의 세션 모두 보관)을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d9642-147">In the **Edit Archiving Setting** pane, click the **Archiving setting** dropdown list and select either **Archive IM sessions** (to archive just instant messaging sessions) or **Archive IM and web conferencing sessions** (to archive both instant messaging and Web conferencing sessions).</span></span>

4. <span data-ttu-id="d9642-148">보관할 항목을 선택한 후 Exchange 보관을 **사용하도록 Exchange Server** 통합 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d9642-148">After choosing the items to be archived, select the **Exchange Server integration** checkbox to enable Exchange archiving.</span></span> <span data-ttu-id="d9642-149">Exchange 보관을 사용하지 않도록 설정하는 경우 이 확인란의 선택을 취소합니다.</span><span class="sxs-lookup"><span data-stu-id="d9642-149">To disable Exchange archiving, clear this checkbox.</span></span>

> [!NOTE]
> <span data-ttu-id="d9642-150">보관 **Exchange Server** 사용 안함으로 설정된 경우  통합 확인란을 사용할 **수 없습니다.**</span><span class="sxs-lookup"><span data-stu-id="d9642-150">The **Exchange Server integration** checkbox will not be available if the **Archiving setting** is set to **Disable archiving**.</span></span> <span data-ttu-id="d9642-151">먼저 보관을 사용하도록 설정한 다음 Exchange 보관을 사용하도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9642-151">You must enable archiving first and then enable Exchange archiving.</span></span>

<span data-ttu-id="d9642-152">비즈니스용 Skype 서버 및 Exchange Server 포리스트에 있는 경우 Exchange In-Place 보류 정책을 사용하여 개별 사용자(또는 Exchange Server 계정이 있는 사용자)에 대한 보관을 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="d9642-152">If Skype for Business Server and Exchange Server are located in the same forest, then archiving for individual users (or at least for users who have email accounts on Exchange Server) is managed by using Exchange In-Place Hold policies.</span></span> <span data-ttu-id="d9642-153">이전 버전의 Exchange에 있는 사용자가 있는 경우 해당 사용자에 대한 보관은 비즈니스용 Skype 서버 보관 정책을 사용하여 관리됩니다.</span><span class="sxs-lookup"><span data-stu-id="d9642-153">If you have users who are homed on a previous version of Exchange then archiving for those users will be managed by using Skype for Business Server archiving policies.</span></span> <span data-ttu-id="d9642-154">Exchange Server 2016 또는 Exchange Server 2013에 계정이 있는 사용자만 비즈니스용 Skype 기록을 Exchange에 보관할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9642-154">Note that only users with accounts on Exchange Server 2016 or Exchange Server 2013 can have their Skype for Business transcripts archived to Exchange.</span></span>

<span data-ttu-id="d9642-155">비즈니스용 Skype 서버 및 Exchange Server 포리스트에 있는 경우 개별 사용자 계정에 대해 ExchangeArchivingPolicy 속성을 구성하여 개별 사용자에 대한 보관을 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="d9642-155">If Skype for Business Server and Exchange Server are located in different forests then archiving for individual users is managed by configuring the ExchangeArchivingPolicy property for each individual user account.</span></span> <span data-ttu-id="d9642-156">자세한 내용은 3단계를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d9642-156">See Step 3 for more information.</span></span>

## <a name="step-2-enabling-the-archiving-of-internal-andor-external-communications"></a><span data-ttu-id="d9642-157">2단계: 내부 및/또는 외부 통신 보관 사용</span><span class="sxs-lookup"><span data-stu-id="d9642-157">Step 2: Enabling the Archiving of Internal and/or External Communications</span></span>

<span data-ttu-id="d9642-158">보관 및 Exchange 보관을 사용하도록 설정한 후 적절한 보관 정책을 수정하여 사용자 세션이 실제로 보관되도록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9642-158">After you have enabled archiving (and Exchange archiving) you must then modify the appropriate archiving policies to ensure that user sessions are actually archived.</span></span> <span data-ttu-id="d9642-159">보관을 사용하도록 설정(1단계)만으로는 비즈니스용 Skype 서버가 메신저 및 웹 회의 기록 보관을 시작하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d9642-159">Note that simply enabling archiving (Step 1) does not cause Skype for Business Server to begin archiving instant messaging and Web conferencing transcripts.</span></span> <span data-ttu-id="d9642-160">대신 보관 정책을 사용하여 내부 및/또는 외부 보관을 사용하도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9642-160">Instead, you must use archiving policies to enable internal and/or external archiving.</span></span> <span data-ttu-id="d9642-161">비즈니스용 Skype 서버를 설치할 때 다음 두 속성이 포함된 단일 전역 보관 정책도 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="d9642-161">When you install Skype for Business Server you also install a single, global archiving policy that contains two properties:</span></span>

- <span data-ttu-id="d9642-162">**ArchiveInternal**.</span><span class="sxs-lookup"><span data-stu-id="d9642-162">**ArchiveInternal**.</span></span> <span data-ttu-id="d9642-163">True($True)로 설정하면 조직에 Active Directory 계정이 있는 사용자만 관련된 내부 통신 세션이 보관됩니다.</span><span class="sxs-lookup"><span data-stu-id="d9642-163">When set to True ($True) indicates that internal communication sessions involving only users who have Active Directory accounts in your organization) will be archived.</span></span>

- <span data-ttu-id="d9642-164">**ArchiveExternal**.</span><span class="sxs-lookup"><span data-stu-id="d9642-164">**ArchiveExternal**.</span></span> <span data-ttu-id="d9642-165">True($True)로 설정하면 내부 통신 세션(조직에 Active Directory 계정이 없는 사용자 한명 이상이 관련된 세션)이 보관됩니다.</span><span class="sxs-lookup"><span data-stu-id="d9642-165">When set to True ($True) indicates that internal communication sessions (sessions involving at least one user who does not have an Active Directory account in your organization) will be archived.</span></span>

<span data-ttu-id="d9642-166">기본적으로 이러한 속성 값은 모두 False로 설정되어 내부 및 외부 통신 세션이 모두 보관되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d9642-166">By default, both of these property values are set to False, meaning that neither internal nor external communication sessions are archived.</span></span> <span data-ttu-id="d9642-167">글로벌 정책을 수정하려면 비즈니스용 Skype 서버 관리 셸 및 Set-CsArchivingPolicy 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9642-167">To modify the global policy, you can use the Skype for Business Server Management Shell and the Set-CsArchivingPolicy cmdlet.</span></span> <span data-ttu-id="d9642-168">이 명령은 내부 및 외부 통신 세션을 모두 보관할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9642-168">This command enables the archiving of both internal and external communication sessions:</span></span>

```powershell
Set-CsArchivingPolicy -Identity "global" -ArchiveInternal $True -ArchiveExternal $True
```

<span data-ttu-id="d9642-169">또는 사이트 범위 또는 사용자 New-CsArchivingPolicy 새 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9642-169">Alternatively, you can use the New-CsArchivingPolicy to create a new policy at either the site scope or the per-user scope.</span></span> <span data-ttu-id="d9642-170">예를 들어 다음 명령은 RedmondArchivingPolicy라는 새 사용자당 보관 정책을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d9642-170">For example, this command creates a new per-user archiving policy named RedmondArchivingPolicy:</span></span>

```powershell
New-CsArchivingPolicy -Identity "RedmondArchivingPolicy" -ArchiveInternal $True -ArchiveExternal $True
```

<span data-ttu-id="d9642-171">사용자당 정책을 만드는 경우 해당 정책을 적절한 사용자에게 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9642-171">If you create a per-user policy you will then need to assign that policy to the appropriate users.</span></span> <span data-ttu-id="d9642-172">예제:</span><span class="sxs-lookup"><span data-stu-id="d9642-172">For example:</span></span>

```powershell
Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName  "RedmondArchivingPolicy"
```

<span data-ttu-id="d9642-173">보관 정책은 비즈니스용 Skype 서버 제어판을 사용하여 관리할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9642-173">Archiving policies can also be managed by using the Skype for Business Server Control Panel.</span></span> <span data-ttu-id="d9642-174">제어판에서 모니터링  및 보관을 클릭한 다음 보관 **정책을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="d9642-174">Within the Control Panel, click **Monitoring and Archiving** and then click **Archiving Policy**.</span></span> <span data-ttu-id="d9642-175">기존 정책을 수정하려면 정책(예: 전역)을 두 번 클릭한 다음 보관 정책 편집 창에서 보관  내부 통신 및  보관 외부 통신 보관 확인란을 선택하거나 선택을 취소합니다. </span><span class="sxs-lookup"><span data-stu-id="d9642-175">To modify an existing policy, double-click the policy (e.g., Global) and then, in the **Edit Archiving Policy** pane, select or clear the **Archive internal communications** and the **Archive external communications** checkboxes as needed.</span></span> <span data-ttu-id="d9642-176">새 보관 정책을 만들려면 새로  만들기를 클릭한  다음 사이트 정책 또는 사용자 정책을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="d9642-176">To create a new archiving policy, click **New** and then select either **Site policy** or **User policy**.</span></span> <span data-ttu-id="d9642-177">새 사용자 정책을 만드는 경우 적절한 사용자 계정(사용자  탭)에 액세스하고 해당 사용자에게 새 정책을 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9642-177">If you create a new user policy then you must access the appropriate user accounts (from the **Users** tab) and assign those users the new policy.</span></span>

## <a name="step-3-configuring-the-exchangearchivingpolicy-property"></a><span data-ttu-id="d9642-178">3단계: ExchangeArchivingPolicy 속성 구성</span><span class="sxs-lookup"><span data-stu-id="d9642-178">Step 3: Configuring the ExchangeArchivingPolicy Property</span></span>

<span data-ttu-id="d9642-179">비즈니스용 Skype 서버 및 Exchange Server 다른 포리스트에 있는 경우 단순히 보관 구성 설정에서 Exchange 보관을 사용하도록 설정하는 것만으로는 충분하지 않습니다. 이 경우 인스턴트 메시징 및 웹 회의 기록이 Exchange에 보관되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d9642-179">If Skype for Business Server and Exchange Server are located in different forests, then it is not enough to simply enable Exchange archiving in the archiving configuration settings; that will not result in instant messaging and Web conferencing transcripts being archived in Exchange.</span></span> <span data-ttu-id="d9642-180">대신 각 관련 비즈니스용 Skype 서버 사용자 계정에 대해 ExchangeArchivingPolicy 속성도 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9642-180">Instead, you must also configure the ExchangeArchivingPolicy property on each of the relevant Skype for Business Server user accounts.</span></span> <span data-ttu-id="d9642-181">이 속성은 다음 네 가지 값 중 하나로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9642-181">This property can be set to one of four possible values:</span></span>

1. <span data-ttu-id="d9642-182">**Uninitialized**.</span><span class="sxs-lookup"><span data-stu-id="d9642-182">**Uninitialized**.</span></span> <span data-ttu-id="d9642-183">보관은 사용자의 Exchange 사서함에 대해 구성된 In-Place 보류 설정을 기반으로 하도록 나타냅니다. In-Place 사서함에서 보류를 사용하도록 설정하지 않은 경우 사용자는 자신의 메시징 및 웹 회의 기록을 비즈니스용 Skype 서버에 보관하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d9642-183">Indicates that archiving will be based on the In-Place Hold settings configured for the user's Exchange mailbox; if In-Place Hold has not been enabled on the user's mailbox then the user will have his or her messaging and Web conferencing transcripts archived in Skype for Business Server.</span></span>

2. <span data-ttu-id="d9642-184">**UseLyncArchivingPolicy**.</span><span class="sxs-lookup"><span data-stu-id="d9642-184">**UseLyncArchivingPolicy**.</span></span> <span data-ttu-id="d9642-185">사용자의 인스턴트 메시징 및 웹 회의 기록은 Exchange가 아닌 비즈니스용 Skype 서버에 보관해야 한다고 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="d9642-185">Indicates that the user's instant messaging and Web conferencing transcripts should be archived in Skype for Business Server rather than in Exchange.</span></span>

3. <span data-ttu-id="d9642-186">**NoArchiving**.</span><span class="sxs-lookup"><span data-stu-id="d9642-186">**NoArchiving**.</span></span> <span data-ttu-id="d9642-187">사용자의 인스턴트 메시징 및 웹 회의 기록을 보관하지 말아야 한다고 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="d9642-187">Indicates that the user's instant messaging and Web conferencing transcripts should not be archived at all.</span></span> <span data-ttu-id="d9642-188">이 설정은 사용자에게 할당된 비즈니스용 Skype 서버 보관 정책을 다시 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d9642-188">Note that this setting overrides any Skype for Business Server archiving policies assigned to the user.</span></span>

4. <span data-ttu-id="d9642-189">**ArchivingToExchange**.</span><span class="sxs-lookup"><span data-stu-id="d9642-189">**ArchivingToExchange**.</span></span> <span data-ttu-id="d9642-190">사용자의 사서함에 할당되거나 할당되지 않은 In-Place 보류 설정에 관계없이 사용자의 인스턴트 메시징 및 웹 회의 기록을 Exchange에 보관해야 한다고 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="d9642-190">Indicates that the user's instant messaging and Web conferencing transcripts should be archived to Exchange regardless of the In-Place Hold settings that have (or have not) been assigned to the user's mailbox.</span></span>

<span data-ttu-id="d9642-191">예를 들어 인스턴트 메시징 및 웹 회의 기록이 항상 Exchange에 보관하도록 사용자 계정을 구성하려면 비즈니스용 Skype 서버 관리 셸에서 다음과 같은 명령을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9642-191">For example, to configure a user account so that instant messaging and Web conferencing transcripts are always archived to Exchange you can use a command similar to this from the Skype for Business Server Management Shell:</span></span>

```powershell
Set-CsUser -Identity "Ken Myer" -ExchangeArchivingPolicy ArchivingToExchange
```

<span data-ttu-id="d9642-192">사용자 그룹에 대해 동일한 보관 정책을 설정하려는 경우(예: 지정된 등록자 풀에 있는 모든 사용자) 다음과 같은 명령을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9642-192">If you want to set the same archiving policy for a group of users (for example, all the users homed on a specified Registrar pool) you can use a command similar to this:</span></span>

```powershell
Get-CsUser -Filter {RegistrarPool -eq "atl-cs-001.litwareinc.com"} | Set-CsUser -ExchangeArchivingPolicy ArchivingToExchange
```

<span data-ttu-id="d9642-193">ExchangeArchivingPolicy 속성의 값을 구성하려면 비즈니스용 Skype 서버 관리 셸(및 Windows PowerShell)을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9642-193">Note that you must use the Skype for Business Server Management Shell (and Windows PowerShell) in order to configure value of the ExchangeArchivingPolicy property.</span></span> <span data-ttu-id="d9642-194">이 속성은 비즈니스용 Skype 서버의 관리자에게 노출되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d9642-194">This property is not exposed to administrators in the Skype for Business Server.</span></span>

<span data-ttu-id="d9642-195">특정 보관 정책이 할당된 모든 사용자의 목록을 보고자 하는 경우 ExchangeArchivingPolicy 속성이 Uninitialized로 설정된 모든 사용자의 Active Directory 표시 이름을 반환하는 다음과 같은 명령을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9642-195">If you would like to view a list of all the users who have been assigned a specific archiving policy then you can use a command similar to the following, which returns the Active Directory display name of all the users who have had the ExchangeArchivingPolicy property set to Uninitialized:</span></span>

```powershell
Get-CsUser | Where-Object {$_.ExchangeArchivingPolicy -eq "Uninitialized"} | Select-Object DisplayName
```

<span data-ttu-id="d9642-196">마찬가지로 이 명령은 ExchangeArchivingPolicy 속성이 UseLyncArchivingPolicy로 설정되지 않은 사용자의 표시 이름을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="d9642-196">Likewise, this command returns the display name of the users who have not have the ExchangeArchivingPolicy property set to UseLyncArchivingPolicy:</span></span>

```powershell
Get-CsUser | Where-Object {$_.ExchangeArchivingPolicy -ne "UseLyncArchivingPolicy"} | Select-Object DisplayName
```


