---
title: Microsoft 팀에서 파일 공유
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: haagaraw
audience: admin
search.appverid: MET150
description: Microsoft 팀의 파일 공유 환경에 대해 알아보세요.
localization_priority: Normal
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 98935f7d8629e22b733b12f3f046ccb7af36b396
ms.sourcegitcommit: 70b80892a152f86a6d596f0f5b58cf391bc29098
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/15/2020
ms.locfileid: "45138384"
---
# <a name="sharing-files-in-microsoft-teams"></a><span data-ttu-id="15d94-103">Microsoft 팀에서 파일 공유</span><span class="sxs-lookup"><span data-stu-id="15d94-103">Sharing files in Microsoft Teams</span></span>

<span data-ttu-id="15d94-104">Microsoft 팀에서 사용자는 조직의 내부 및 외부에 있는 다른 팀 사용자와 콘텐츠를 공유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="15d94-104">In Microsoft Teams, users can share content with other Teams users within and outside their organization.</span></span> <span data-ttu-id="15d94-105">팀에서 공유 하는 작업은 SharePoint 및 OneDrive에서 구성 된 설정을 기반으로 하므로 SharePoint와 OneDrive에 대해 설정 하는 모든 작업은 팀의 공유를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="15d94-105">Sharing in Teams is based on the settings configured in SharePoint and OneDrive, so whatever you set up for SharePoint and OneDrive will control sharing in Teams as well.</span></span>

## <a name="overview"></a><span data-ttu-id="15d94-106">개요</span><span class="sxs-lookup"><span data-stu-id="15d94-106">Overview</span></span>

<span data-ttu-id="15d94-107">사용자는 OneDrive, 액세스 권한이 있는 팀 및 사이트, 컴퓨터에서 파일을 공유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="15d94-107">Users can share files from OneDrive, from teams and sites they have access to, and from their computer.</span></span> <span data-ttu-id="15d94-108">파일을 공유 하기 위해 사용자는 다음을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="15d94-108">To share a file, users can do the following:</span></span>

- <span data-ttu-id="15d94-109">채널에서 **첨부** (클립 아이콘)를 클릭 하 고 **최근**, **팀 및 채널**, **OneDrive**또는 **내 컴퓨터에서 업로드**를 선택 하 고 공유 하려는 파일을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="15d94-109">In a channel, click **Attach** (the paperclip icon), select **Recent**, **Browse Teams and Channels**, **OneDrive**, or **Upload from my computer**, and then choose the file they want to share.</span></span> <br> 
    <span data-ttu-id="15d94-110">![채널에서 파일을 공유 하는 방법을 보여 주는 스크린샷](media/share-files-channel.png)</span><span class="sxs-lookup"><span data-stu-id="15d94-110">![Screenshot showing sharing a file from a channel](media/share-files-channel.png)</span></span>
- <span data-ttu-id="15d94-111">채팅에서 **첨부** (클립 아이콘)를 클릭 하 고 **내 컴퓨터에서** **OneDrive** 또는 업로드를 선택한 다음 공유 하려는 파일을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="15d94-111">In a chat, click **Attach** (the paperclip icon), select  or **OneDrive** or **Upload from my computer**, and then choose the file they want to share.</span></span> <br>
    <span data-ttu-id="15d94-112">![채팅에서 파일을 공유 하는 것을 보여 주는 스크린샷](media/share-files-chat.png)</span><span class="sxs-lookup"><span data-stu-id="15d94-112">![Screenshot showing sharing a file from a chat](media/share-files-chat.png)</span></span>
- <span data-ttu-id="15d94-113">작성 상자에 공유 링크를 복사 하 여 붙여 넣습니다.</span><span class="sxs-lookup"><span data-stu-id="15d94-113">Copy and paste the sharing link in the compose box.</span></span><br>
    <span data-ttu-id="15d94-114">![작성 상자에 파일 미리 보기를 표시 하는 스크린샷](media/share-files-link.png)</span><span class="sxs-lookup"><span data-stu-id="15d94-114">![Screenshot showing file preview in the compose box](media/share-files-link.png)</span></span>

### <a name="what-you-need-to-know-about-the-file-sharing-experience"></a><span data-ttu-id="15d94-115">파일 공유 환경에 대해 알아야 할 사항</span><span class="sxs-lookup"><span data-stu-id="15d94-115">What you need to know about the file sharing experience</span></span>

### <a name="permissions-of-shared-files-and-sharing-links"></a><span data-ttu-id="15d94-116">공유 파일 및 공유 링크의 사용 권한</span><span class="sxs-lookup"><span data-stu-id="15d94-116">Permissions of shared files and sharing links</span></span>

<span data-ttu-id="15d94-117">사용자가 OneDrive 또는 팀과 채널에서 파일을 공유할 때 [조직 수준에서 설정 된 기본 사용 권한과](https://docs.microsoft.com/sharepoint/change-default-sharing-link)함께 모든 받는 사람에 게 액세스 권한이 부여 됩니다.</span><span class="sxs-lookup"><span data-stu-id="15d94-117">When users share a file by browsing to it in OneDrive or teams and channels, all recipients are granted access along with the [default permission that's set at the organization level](https://docs.microsoft.com/sharepoint/change-default-sharing-link).</span></span>

<span data-ttu-id="15d94-118">사용자가 공유 링크를 복사 하 여 붙여 넣으면 해당 공유 링크에 설정 된 사용 권한이 유지 되 고 SharePoint URL이 파일 이름으로 짧아집니다.</span><span class="sxs-lookup"><span data-stu-id="15d94-118">When a user copies and pastes a sharing link, the permissions set on that sharing link are honored and the SharePoint URL is shortened to the file name.</span></span> <span data-ttu-id="15d94-119">즉, 팀은 파일 이름만 사용 하 여 파일에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="15d94-119">In other words, Teams uses just the file name to link to a file.</span></span>

<span data-ttu-id="15d94-120">사용자가 팀 내에서 파일을 공유 하는 경우 Microsoft 365에서와 마찬가지로 파일에 액세스할 수 있는 사용자를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="15d94-120">When users share a file from within Teams, they can set who can access the file just like they do across Microsoft 365.</span></span> <span data-ttu-id="15d94-121">이러한 사용자는 조직의 모든 사용자, 기존 액세스 권한이 있는 사용자 또는 특정 사용자 (1:1 채팅, 그룹 채팅 또는 채널에 사람을 포함할 수 있음)에 대 한 액세스 권한을 부여할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="15d94-121">They can give access to anyone, people in your organization, people with existing access, or specific people (which can include the people in a 1:1 chat, group chat, or channel).</span></span>  <span data-ttu-id="15d94-122">파일을 공유 하는 경우에는 메시지에서 파일 미리 보기를 사용할 수 있으며, **온라인 열기**, **다운로드**, **복사 링크**등의 모든 파일 작업을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="15d94-122">When a file is shared, the file preview is available in the message, along with all file actions such as **Open online**, **Download**, and **Copy link**.</span></span> <span data-ttu-id="15d94-123">기본적으로 파일은 팀에서 열립니다.</span><span class="sxs-lookup"><span data-stu-id="15d94-123">By default, the file opens in Teams.</span></span> <span data-ttu-id="15d94-124">경우에 따라 공유 링크는 사용자가 메시지를 보낼 때 파일 미리 보기로 전환 되지 않았을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="15d94-124">Sometimes, the sharing link may not have converted to a file preview by the time a user sends the message.</span></span> <span data-ttu-id="15d94-125">시스템에서 파일 미리 보기를 생성 하지만이 시나리오에서는 공유 링크가 파일 이름 으로만 단축 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="15d94-125">The file preview will be generated by the system, but in this scenario, the sharing link won't be shortened to the only the file name.</span></span>

<span data-ttu-id="15d94-126">사용자가 채팅 또는 채널에서 파일을 공유 하는 경우 일부 또는 모든 받는 사람이 파일을 볼 수 있는 권한이 없는지에 대 한 알림이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="15d94-126">When users share a file in a chat or channel, they're notified whether some or all recipients don't have permission to view the file.</span></span> <span data-ttu-id="15d94-127">메시지에 표시 되는 파일 미리 보기 옆에 있는 화살표를 클릭 하 여 공유 하기 전에 해당 파일에 대 한 사용 권한을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="15d94-127">They can change the permissions on the file before they share it by clicking the arrow next to the file preview that now appears in the message.</span></span>

![받는 사람에 게 사용 권한이 없는 경우 알림 스크린샷](media/share-files-permissions.png)

### <a name="copy-a-sharing-link-in-teams"></a><span data-ttu-id="15d94-129">팀에서 공유 링크 복사</span><span class="sxs-lookup"><span data-stu-id="15d94-129">Copy a sharing link in Teams</span></span>

<span data-ttu-id="15d94-130">사용자는 Microsoft 365에서와 마찬가지로 SharePoint 공유 링크를 복사 하 고 공유 권한을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="15d94-130">Users can copy a SharePoint sharing link and change sharing permissions just like they do across Microsoft 365.</span></span> <span data-ttu-id="15d94-131">사용자는 조직의 모든 사용자, 기존 액세스 권한이 있는 사용자 또는 특정 사용자에 게 액세스 권한을 부여할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="15d94-131">They can give access to anyone, people in your organization, people with existing access, or specific people.</span></span> <span data-ttu-id="15d94-132">링크의 기본 권한은 SharePoint 사이트 수준 사용 권한이이를 재정의 하지 않는 한 조직 수준의 기본 사용 권한 집합과 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="15d94-132">The default permission of the link is the same as the default permission set at the organization level unless SharePoint site level permissions override it.</span></span>

## <a name="configure-sharing-in-onedrive-and-sharepoint"></a><span data-ttu-id="15d94-133">OneDrive 및 SharePoint에서 공유 구성</span><span class="sxs-lookup"><span data-stu-id="15d94-133">Configure sharing in OneDrive and SharePoint</span></span>

<span data-ttu-id="15d94-134">공유 구성 방법, 공유 설정 및 해제 방법을 비롯 하 여 OneDrive 및 SharePoint에서 파일을 공유 하는 방법에 대 한 자세한 내용은 다음을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="15d94-134">For more information about sharing files in OneDrive and SharePoint, including how to configure sharing and how to turn sharing on and off, see:</span></span>

- <span data-ttu-id="15d94-135">[외부 공유 개요](https://docs.microsoft.com/sharepoint/external-sharing-overview) -사용자가 공유 하는 항목 및 상대에 따라 공유할 때 발생 하는 상황을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="15d94-135">[External sharing overview](https://docs.microsoft.com/sharepoint/external-sharing-overview) - describes what happens when users share, depending on what they're sharing and with whom.</span></span>

- <span data-ttu-id="15d94-136">[공유 설정 관리](https://docs.microsoft.com/sharepoint/turn-external-sharing-on-or-off) -전역 및 sharepoint 관리자가 Sharepoint 및 OneDrive에 대 한 조직 수준의 공유 설정을 변경 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="15d94-136">[Manage sharing settings](https://docs.microsoft.com/sharepoint/turn-external-sharing-on-or-off) - describes how global and SharePoint admins can change their organization-level sharing settings for SharePoint and OneDrive.</span></span>

- <span data-ttu-id="15d94-137">[사이트에 대해 외부 공유 설정 또는 해제](https://docs.microsoft.com/sharepoint/change-external-sharing-site) -전역 및 SharePoint 관리자가 사이트에 대해 외부 공유를 설정 하거나 해제 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="15d94-137">[Turn external sharing on or off for a site](https://docs.microsoft.com/sharepoint/change-external-sharing-site) – describes how global and SharePoint admins can turn external sharing on or off for a site.</span></span>

- <span data-ttu-id="15d94-138">[사이트의 기본 링크 종류 변경](https://docs.microsoft.com/sharepoint/change-default-sharing-link) -기본 링크 종류를 더 엄격 하 게 설정 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="15d94-138">[Change the default link type for a site](https://docs.microsoft.com/sharepoint/change-default-sharing-link) - describes how to set the default link type so that it's more restrictive.</span></span>

## <a name="more-information"></a><span data-ttu-id="15d94-139">추가 정보</span><span class="sxs-lookup"><span data-stu-id="15d94-139">More information</span></span>

- [<span data-ttu-id="15d94-140">SharePoint Online 및 비즈니스용 OneDrive가 Microsoft 팀과 상호 작용 하는 방법</span><span class="sxs-lookup"><span data-stu-id="15d94-140">How SharePoint Online and OneDrive for Business interact with Microsoft Teams</span></span>](sharepoint-onedrive-interact.md)

- [<span data-ttu-id="15d94-141">SharePoint 및 팀: 함께 개선</span><span class="sxs-lookup"><span data-stu-id="15d94-141">SharePoint and Teams: better together</span></span>](https://techcommunity.microsoft.com/t5/Microsoft-SharePoint-Blog/SharePoint-and-Teams-Better-Together/ba-p/189593)

- [<span data-ttu-id="15d94-142">OneDrive 파일 및 폴더 공유</span><span class="sxs-lookup"><span data-stu-id="15d94-142">Share OneDrive files and folders</span></span>](https://support.office.com/article/Share-OneDrive-files-and-folders-9fcc2f7d-de0c-4cec-93b0-a82024800c07#OS_Type=OneDrive_-_Business)

- [<span data-ttu-id="15d94-143">SharePoint 파일 또는 폴더 공유</span><span class="sxs-lookup"><span data-stu-id="15d94-143">Share SharePoint files or folders</span></span>](https://support.office.com/article/share-sharepoint-files-or-folders-1fe37332-0f9a-4719-970e-d2578da4941c)
