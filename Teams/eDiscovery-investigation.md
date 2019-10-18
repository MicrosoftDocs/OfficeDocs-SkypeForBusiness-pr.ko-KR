---
title: Microsoft 팀의 콘텐츠 eDiscovery 조사 수행
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/12/2018
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
ms.reviewer: anach
search.appverid: MET150
description: 법률 소송 절차에 대해 전자적으로 저장 된 모든 정보를 제출 해야 하는 경우와 같이 eDiscovery를 preform 해야 할 경우 수행할 작업에 대해 알아보세요.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 42a9f9cc011d050e540eef3ff87d9cd839cc2819
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2019
ms.locfileid: "37569890"
---
<a name="conduct-an-ediscovery-investigation-of-content-in-microsoft-teams"></a><span data-ttu-id="da5f2-103">Microsoft 팀의 콘텐츠 eDiscovery 조사 수행</span><span class="sxs-lookup"><span data-stu-id="da5f2-103">Conduct an eDiscovery investigation of content in Microsoft Teams</span></span>
============================

<span data-ttu-id="da5f2-104">대규모 기업은 모든 ESI (전자적 저장 정보) 제출을 요구 하는 높은 벌칙 법률 소송 절차에 게 노출 되는 경우가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="da5f2-104">Large Enterprises are often exposed to high penalty legal proceedings that demand submission of all Electronically Stored Information (ESI).</span></span>

<span data-ttu-id="da5f2-105">모든 팀 1:1 또는 그룹 채팅은 각 사용자의 사서함으로 저널링 되며, 모든 채널 메시지가 팀을 나타내는 그룹 사서함으로 저널링 됩니다.</span><span class="sxs-lookup"><span data-stu-id="da5f2-105">All Teams 1:1 or group chats are journaled through to the respective users’ mailboxes, and all channel messages are journaled through to the group mailbox representing the team.</span></span> <span data-ttu-id="da5f2-106">업로드 되는 파일은 SharePoint Online 및 비즈니스용 OneDrive의 eDiscovery 기능에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="da5f2-106">Files uploaded are covered under the eDiscovery functionality for SharePoint Online and OneDrive for Business.</span></span>

1.  <span data-ttu-id="da5f2-107">Microsoft 팀 콘텐츠를 사용 하 여 eDiscovery 조사를 수행 하려면 [이](https://support.office.com/article/Manage-eDiscovery-cases-in-the-Office-365-Security-Compliance-Center-edea80d6-20a7-40fb-b8c4-5e8c8395f6da) 링크의 1 단계를 검토 합니다.</span><span class="sxs-lookup"><span data-stu-id="da5f2-107">To conduct an eDiscovery investigation with Microsoft Teams content, review step 1 in [this](https://support.office.com/article/Manage-eDiscovery-cases-in-the-Office-365-Security-Compliance-Center-edea80d6-20a7-40fb-b8c4-5e8c8395f6da) link.</span></span>

2.  <span data-ttu-id="da5f2-108">Microsoft 팀 데이터가 Excel eDiscovery 내보내기 출력에 IM 또는 대화로 표시 되며,을 탑재할 수 있습니다. PST에서 해당 메시지를 보려면 내보내기를 게시 합니다.</span><span class="sxs-lookup"><span data-stu-id="da5f2-108">Microsoft Teams data will appear as IM or Conversations in the Excel eDiscovery export output, and you can mount the .PST in Outlook to view those messages post export.</span></span>

    <span data-ttu-id="da5f2-109">를 탑재 하는 경우. PST 팀의 경우 대화 내용 아래의 팀 채팅 폴더에 모든 대화가 보관 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="da5f2-109">When mounting the .PST for the Team, note that all conversations are kept in the Team Chat folder under Conversation History.</span></span> <span data-ttu-id="da5f2-110">메시지 제목은 팀 및 채널에 맞춰 정렬 됩니다.</span><span class="sxs-lookup"><span data-stu-id="da5f2-110">The title of the message aligns to Team and Channel.</span></span> <span data-ttu-id="da5f2-111">아래 이미지를 검토 하 여 제조 사양 팀의 프로젝트 7 채널을 messaged 하는 Bob 으로부터이 메시지를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da5f2-111">From reviewing the image below, you can see this message from Bob who messaged the Project 7 channel of the Manufacturing Specs team.</span></span>

    ![Outlook의 사용자 사서함에 있는 팀 채팅 폴더 스크린샷](media/Conduct_an_eDiscovery_investigation_of_content_in_Microsoft_Teams_image1.png)

3.  <span data-ttu-id="da5f2-113">사용자의 사서함에서 개인 채팅을 보려면 대화 내용 아래의 팀 채팅 폴더에도 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da5f2-113">To see private chats in a user’s Mailbox, they are also located inside the Team Chat folder under Conversation History.</span></span>

## <a name="ediscovery-of-guest-to-guest-chats"></a><span data-ttu-id="da5f2-114">게스트 대 게스트 채팅 eDiscovery</span><span class="sxs-lookup"><span data-stu-id="da5f2-114">eDiscovery of guest-to-guest chats</span></span>

<span data-ttu-id="da5f2-115">사서함이 없으면 게스트 간 채팅 (가정용 테 넌 트 사용자가 없는 1xN 채팅)이 인덱싱되지 않으며 결과적으로 eDiscovery에 포함 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="da5f2-115">Without a mailbox, guest-to-guest chats (1xN chats in which there are no home tenant users) would not be indexed, and as a result, would not be included in eDiscovery.</span></span> <span data-ttu-id="da5f2-116">게스트 대 게스트 채팅에 eDiscovery 기능을 활용 하기 위해 클라우드 기반 사서함 (또는 팬텀 사서함)을 만들어 1xN 데이터를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="da5f2-116">To facilitate eDiscovery for guest-to-guest chats, a cloud-based mailbox (or phantom mailbox) is created to store the 1xN data.</span></span> <span data-ttu-id="da5f2-117">팀 채팅 데이터는 클라우드 기반 사서함에 저장 된 후 eDiscovery 및 준수 콘텐츠 검색을 위해 인덱싱됩니다.</span><span class="sxs-lookup"><span data-stu-id="da5f2-117">After the Teams chat data is stored in the cloud-based mailbox, it is indexed for eDiscovery and compliance content search.</span></span>

<span data-ttu-id="da5f2-118">다음 그림은 사서함이 없는 게스트 대 게스트 채팅에 대해 eDiscovery가 작동 하는 방식을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="da5f2-118">The following illustration shows how eDiscovery works for guest-to-guest chats in which there isn’t a mailbox.</span></span>

![비-게스트-사서함이 포함 된 채팅](media/conduct-an-ediscovery-investigation-of-content-in-microsoft-teams-image2.png)
