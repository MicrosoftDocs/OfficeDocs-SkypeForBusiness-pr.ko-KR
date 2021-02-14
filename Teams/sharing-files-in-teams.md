---
title: Microsoft Teams에서 파일 및 폴더 공유
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: haagaraw
audience: admin
search.appverid: MET150
localization_priority: Normal
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
description: Microsoft Teams의 파일 및 폴더 공유 경험에 대해 자세히 배워야 합니다.
ms.openlocfilehash: 5b6847c42f13701e289b2efaad4a5489351f339b
ms.sourcegitcommit: b68a7b5100fc2b47ae81f465d48d1ac2348c1744
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/11/2021
ms.locfileid: "49795781"
---
# <a name="sharing-files-in-microsoft-teams"></a><span data-ttu-id="8b4b7-103">Microsoft Teams에서 파일 공유</span><span class="sxs-lookup"><span data-stu-id="8b4b7-103">Sharing files in Microsoft Teams</span></span>

<span data-ttu-id="8b4b7-104">Microsoft Teams에서 사용자는 조직 내부 및 외부의 다른 Teams 사용자와 콘텐츠를 공유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8b4b7-104">In Microsoft Teams, users can share content with other Teams users within and outside their organization.</span></span> <span data-ttu-id="8b4b7-105">Teams에서 파일 및 폴더 공유는 SharePoint 및 OneDrive에 구성된 설정을 기반으로 하여 SharePoint 및 OneDrive에 대해 설정한 모든 것이 Teams의 공유에도 영향을 미치게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8b4b7-105">Sharing files and folders in Teams is based on the settings configured in SharePoint and OneDrive, so whatever you set up for SharePoint and OneDrive will affect sharing in Teams as well.</span></span>

## <a name="overview"></a><span data-ttu-id="8b4b7-106">개요</span><span class="sxs-lookup"><span data-stu-id="8b4b7-106">Overview</span></span>

<span data-ttu-id="8b4b7-107">사용자는 OneDrive, 액세스 권한이 있는 팀 및 사이트에서, 그리고 자신의 컴퓨터에서 파일을 공유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8b4b7-107">Users can share files from OneDrive, from teams and sites they have access to, and from their computer.</span></span> <span data-ttu-id="8b4b7-108">파일을 공유하기 위해 사용자는 다음을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8b4b7-108">To share a file, users can do the following:</span></span>

- <span data-ttu-id="8b4b7-109">채널에서 **첨부(종이클립** 아이콘)를 클릭하고 최근, Teams 및 **채널** 찾아보기, **OneDrive** 또는 내 컴퓨터에서 업로드를 선택한 다음 공유할 파일을 선택합니다. </span><span class="sxs-lookup"><span data-stu-id="8b4b7-109">In a channel, click **Attach** (the paperclip icon), select **Recent**, **Browse Teams and Channels**, **OneDrive**, or **Upload from my computer**, and then choose the file they want to share.</span></span> <br> 
    <span data-ttu-id="8b4b7-110">![채널에서 파일 공유를 보여주는 스크린샷](media/share-files-channel.png)</span><span class="sxs-lookup"><span data-stu-id="8b4b7-110">![Screenshot showing sharing a file from a channel](media/share-files-channel.png)</span></span>
- <span data-ttu-id="8b4b7-111">채팅에서 첨부(종이클립 아이콘)를 클릭하고 컴퓨터에서 **OneDrive** 또는 업로드를 클릭한 다음 공유할 파일을 선택합니다.  </span><span class="sxs-lookup"><span data-stu-id="8b4b7-111">In a chat, click **Attach** (the paperclip icon), select  or **OneDrive** or **Upload from my computer**, and then choose the file they want to share.</span></span> <br>
    <span data-ttu-id="8b4b7-112">![채팅에서 파일 공유를 보여주는 스크린샷](media/share-files-chat.png)</span><span class="sxs-lookup"><span data-stu-id="8b4b7-112">![Screenshot showing sharing a file from a chat](media/share-files-chat.png)</span></span>
- <span data-ttu-id="8b4b7-113">공유 링크를 복사하여 작성 상자에 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="8b4b7-113">Copy and paste the sharing link in the compose box.</span></span><br>
    <span data-ttu-id="8b4b7-114">![작성 상자의 파일 미리 보기를 보여주는 스크린샷](media/share-files-link.png)</span><span class="sxs-lookup"><span data-stu-id="8b4b7-114">![Screenshot showing file preview in the compose box](media/share-files-link.png)</span></span>

### <a name="permissions-of-shared-files-and-sharing-links"></a><span data-ttu-id="8b4b7-115">공유 파일 및 공유 링크의 사용 권한</span><span class="sxs-lookup"><span data-stu-id="8b4b7-115">Permissions of shared files and sharing links</span></span>

<span data-ttu-id="8b4b7-116">사용자가 Teams 내에서 파일을 공유하는 경우 Microsoft 365에서와 마찬가지로 파일에 액세스할 수 있는 사용자를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8b4b7-116">When users share a file from within Teams, they can set who can access the file just like they do across Microsoft 365.</span></span> <span data-ttu-id="8b4b7-117">모든 사용자, 조직의 사용자, 기존 액세스 권한이 있는 사용자 또는 특정 사용자(1:1 채팅, 그룹 채팅 또는 채널에 사람 포함)에 대한 액세스 권한을 부여할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8b4b7-117">They can give access to anyone, people in your organization, people with existing access, or specific people (which can include the people in a 1:1 chat, group chat, or channel).</span></span>  <span data-ttu-id="8b4b7-118">파일이 공유되는 경우 파일 미리 보기는 온라인 열기, 다운로드 및 복사 링크와 같은 모든 파일 작업과 함께 메시지에서 사용할 **수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="8b4b7-118">When a file is shared, the file preview is available in the message, along with all file actions such as **Open online**, **Download**, and **Copy link**.</span></span> <span data-ttu-id="8b4b7-119">기본적으로 파일은 Teams에서 열립니다.</span><span class="sxs-lookup"><span data-stu-id="8b4b7-119">By default, the file opens in Teams.</span></span>

<span data-ttu-id="8b4b7-120">사용자가 채팅 또는 채널에서 파일을 공유하면 일부 또는 모든 받는 사람이 파일을 볼 수 있는 권한이 없는지 여부에 대한 알림을 수신하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8b4b7-120">When users share a file in a chat or channel, they're notified whether some or all recipients don't have permission to view the file.</span></span> <span data-ttu-id="8b4b7-121">이제 메시지에 나타나는 파일 미리 보기 옆에 있는 화살표를 클릭하여 공유하기 전에 파일에 대한 사용 권한을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8b4b7-121">They can change the permissions on the file before they share it by clicking the arrow next to the file preview that now appears in the message.</span></span>

![받는 사람에게 권한이 없는 경우 알림의 스크린샷](media/share-files-permissions.png)

## <a name="related-topics"></a><span data-ttu-id="8b4b7-123">관련 항목</span><span class="sxs-lookup"><span data-stu-id="8b4b7-123">Related topics</span></span>

[<span data-ttu-id="8b4b7-124">SharePoint Online 및 비즈니스용 OneDrive가 Microsoft Teams와 상호 작용하는 방법</span><span class="sxs-lookup"><span data-stu-id="8b4b7-124">How SharePoint Online and OneDrive for Business interact with Microsoft Teams</span></span>](sharepoint-onedrive-interact.md)

[<span data-ttu-id="8b4b7-125">사이트의 기본 링크 유형 변경</span><span class="sxs-lookup"><span data-stu-id="8b4b7-125">Change the default link type for a site</span></span>](https://docs.microsoft.com/sharepoint/change-default-sharing-link)

[<span data-ttu-id="8b4b7-126">팀의 게스트와 공동 작업</span><span class="sxs-lookup"><span data-stu-id="8b4b7-126">Collaborate with guests in a team</span></span>](https://docs.microsoft.com/microsoft-365/solutions/collaborate-as-team)