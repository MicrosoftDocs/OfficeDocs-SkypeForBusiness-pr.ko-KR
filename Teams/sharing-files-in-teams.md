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
description: Microsoft Teams의 파일 및 폴더 공유 환경에 대해 자세히 알아보습니다.
ms.openlocfilehash: 53997f4493a0217e980427ab0d1f85d64095b9c9
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117026"
---
# <a name="sharing-files-in-microsoft-teams"></a><span data-ttu-id="306cd-103">Microsoft Teams에서 파일 공유</span><span class="sxs-lookup"><span data-stu-id="306cd-103">Sharing files in Microsoft Teams</span></span>

<span data-ttu-id="306cd-104">Microsoft Teams에서 사용자는 조직 내 및 외부의 다른 Teams 사용자와 콘텐츠를 공유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="306cd-104">In Microsoft Teams, users can share content with other Teams users within and outside their organization.</span></span> <span data-ttu-id="306cd-105">Teams의 파일 및 폴더 공유는 SharePoint 및 OneDrive에 구성된 설정을 기반으로 하여 SharePoint 및 OneDrive에 대해 설정한 모든 것이 Teams의 공유에도 영향을 미치게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="306cd-105">Sharing files and folders in Teams is based on the settings configured in SharePoint and OneDrive, so whatever you set up for SharePoint and OneDrive will affect sharing in Teams as well.</span></span>

## <a name="overview"></a><span data-ttu-id="306cd-106">개요</span><span class="sxs-lookup"><span data-stu-id="306cd-106">Overview</span></span>

<span data-ttu-id="306cd-107">사용자는 OneDrive에서, 액세스할 수 있는 팀 및 사이트에서, 그리고 자신의 컴퓨터에서 파일을 공유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="306cd-107">Users can share files from OneDrive, from teams and sites they have access to, and from their computer.</span></span> <span data-ttu-id="306cd-108">파일을 공유하기 위해 사용자는 다음을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="306cd-108">To share a file, users can do the following:</span></span>

- <span data-ttu-id="306cd-109">채널에서 첨부(종이 립 아이콘)를 클릭하고 **최근,** 팀 및 채널 찾아보기 **,**  **OneDrive** 또는 내 컴퓨터에서 업로드를 선택한 다음 공유하려는 파일을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="306cd-109">In a channel, click **Attach** (the paperclip icon), select **Recent**, **Browse Teams and Channels**, **OneDrive**, or **Upload from my computer**, and then choose the file they want to share.</span></span> <br> 
    <span data-ttu-id="306cd-110">![채널에서 파일 공유를 보여주는 스크린샷](media/share-files-channel.png)</span><span class="sxs-lookup"><span data-stu-id="306cd-110">![Screenshot showing sharing a file from a channel](media/share-files-channel.png)</span></span>
- <span data-ttu-id="306cd-111">채팅에서 첨부(종이 립 아이콘)를 클릭하고 컴퓨터에서 **OneDrive** 또는 **업로드를** 선택한 다음 공유할 파일을 선택합니다. </span><span class="sxs-lookup"><span data-stu-id="306cd-111">In a chat, click **Attach** (the paperclip icon), select  or **OneDrive** or **Upload from my computer**, and then choose the file they want to share.</span></span> <br>
    <span data-ttu-id="306cd-112">![채팅에서 파일 공유를 보여주는 스크린샷](media/share-files-chat.png)</span><span class="sxs-lookup"><span data-stu-id="306cd-112">![Screenshot showing sharing a file from a chat](media/share-files-chat.png)</span></span>
- <span data-ttu-id="306cd-113">공유 링크를 복사하여 작성 상자에 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="306cd-113">Copy and paste the sharing link in the compose box.</span></span><br>
    <span data-ttu-id="306cd-114">![작성 상자에서 파일 미리 보기를 보여주는 스크린샷](media/share-files-link.png)</span><span class="sxs-lookup"><span data-stu-id="306cd-114">![Screenshot showing file preview in the compose box](media/share-files-link.png)</span></span>

### <a name="permissions-of-shared-files-and-sharing-links"></a><span data-ttu-id="306cd-115">공유 파일 및 공유 링크의 사용 권한</span><span class="sxs-lookup"><span data-stu-id="306cd-115">Permissions of shared files and sharing links</span></span>

<span data-ttu-id="306cd-116">사용자가 Teams 내에서 파일을 공유하는 경우 Microsoft 365에서처럼 파일에 액세스할 수 있는 사용자를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="306cd-116">When users share a file from within Teams, they can set who can access the file just like they do across Microsoft 365.</span></span> <span data-ttu-id="306cd-117">모든 사용자, 조직의 사용자, 기존 액세스 권한이 있는 사용자 또는 특정 사용자(1:1 채팅, 그룹 채팅 또는 채널에 있는 사용자 포함)에 대한 액세스 권한을 부여할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="306cd-117">They can give access to anyone, people in your organization, people with existing access, or specific people (which can include the people in a 1:1 chat, group chat, or channel).</span></span>  <span data-ttu-id="306cd-118">파일이 공유되는 경우 메시지에서 파일 미리 보기를 사용할 수 있으며, 온라인 열기, 다운로드 및 복사 링크와 같은 모든 파일 작업과 함께 사용할 수 **있습니다.**</span><span class="sxs-lookup"><span data-stu-id="306cd-118">When a file is shared, the file preview is available in the message, along with all file actions such as **Open online**, **Download**, and **Copy link**.</span></span> <span data-ttu-id="306cd-119">기본적으로 파일은 Teams에서 열립니다.</span><span class="sxs-lookup"><span data-stu-id="306cd-119">By default, the file opens in Teams.</span></span>

<span data-ttu-id="306cd-120">사용자가 채팅 또는 채널에서 파일을 공유하면 일부 또는 모든 받는 사람이 파일을 볼 수 있는 권한이 없는지 여부를 알림을 받는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="306cd-120">When users share a file in a chat or channel, they're notified whether some or all recipients don't have permission to view the file.</span></span> <span data-ttu-id="306cd-121">이제 메시지에 나타나는 파일 미리 보기 옆에 있는 화살표를 클릭하여 파일을 공유하기 전에 파일의 권한을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="306cd-121">They can change the permissions on the file before they share it by clicking the arrow next to the file preview that now appears in the message.</span></span>

![받는 사람이 권한이 없는 경우 알림 스크린샷](media/share-files-permissions.png)

## <a name="related-topics"></a><span data-ttu-id="306cd-123">관련 항목</span><span class="sxs-lookup"><span data-stu-id="306cd-123">Related topics</span></span>

[<span data-ttu-id="306cd-124">SharePoint Online 및 비즈니스용 OneDrive가 Microsoft Teams와 상호 작용하는 방법</span><span class="sxs-lookup"><span data-stu-id="306cd-124">How SharePoint Online and OneDrive for Business interact with Microsoft Teams</span></span>](sharepoint-onedrive-interact.md)

[<span data-ttu-id="306cd-125">사이트의 기본 링크 형식 변경</span><span class="sxs-lookup"><span data-stu-id="306cd-125">Change the default link type for a site</span></span>](/sharepoint/change-default-sharing-link)

[<span data-ttu-id="306cd-126">팀의 게스트와 공동 작업</span><span class="sxs-lookup"><span data-stu-id="306cd-126">Collaborate with guests in a team</span></span>](/microsoft-365/solutions/collaborate-as-team)