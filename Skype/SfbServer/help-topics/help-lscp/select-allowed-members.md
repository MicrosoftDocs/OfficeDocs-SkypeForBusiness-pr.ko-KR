---
title: 허용 구성원 선택
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/24/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.SelectAllowedMembers
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e9e6df4a-e58a-4104-9f72-2f5c818353e1
description: 일관 된 채팅방을 만들고 관리 하는 것은 범주를 올바르게 사용 하는 것 보다 훨씬 더 쉽습니다. 영구 채팅 관리자는 각 범주에 대해 AllowedMembers 및 작성자를 정의할 수 있으며, 범주에서 만든 모든 채팅방에 적용 되는 기본 채팅방 설정 및 동작을 정의할 수도 있습니다. 영구 채팅 관리자는 제어판 또는 Windows PowerShell cmdlet을 사용 하 여 범주를 만들고 관리 합니다.
ms.openlocfilehash: ad371fada6bbb7e8c9a2620eb5ec533cc60a0673
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41822301"
---
# <a name="select-allowed-members"></a><span data-ttu-id="d38e8-105">허용 구성원 선택</span><span class="sxs-lookup"><span data-stu-id="d38e8-105">Select Allowed Members</span></span>

<span data-ttu-id="d38e8-106">일관 된 채팅방을 만들고 관리 하는 것은 범주를 올바르게 사용 하는 것 보다 훨씬 더 쉽습니다.</span><span class="sxs-lookup"><span data-stu-id="d38e8-106">Creating and managing Persistent Chat rooms is much easier with the correct use of categories.</span></span> <span data-ttu-id="d38e8-107">영구 채팅 관리자는 각 범주에 대해 **Allowedmembers** 및 **작성자** 를 정의할 수 있으며, 범주에서 만든 모든 채팅방에 적용 되는 기본 채팅방 설정 및 동작을 정의할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d38e8-107">A Persistent Chat Administrator can define **AllowedMembers** and **Creators** for each category, and can also define the default chat room settings and behaviors that will be applied to all chat rooms created in the category.</span></span> <span data-ttu-id="d38e8-108">영구 채팅 관리자는 제어판 또는 Windows PowerShell cmdlet을 사용 하 여 범주를 만들고 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="d38e8-108">Persistent Chat Administrators create and manage categories by using the control panel or Windows PowerShell cmdlets.</span></span>

<span data-ttu-id="d38e8-109">범주의 작성자로 식별되는 사용자, OU(조직 구성 단위), 사용자 그룹은 해당 범주에서 채팅방을 만들 수 있는 개인과 그룹입니다.</span><span class="sxs-lookup"><span data-stu-id="d38e8-109">Users, Organizational Units (OUs), and user groups that are identified as Creators of the category are the only individuals and groups that are allowed to create rooms in the category.</span></span> <span data-ttu-id="d38e8-110">범주가 만들어진 후에는 범주의 **Allowedmembers** 목록에서 사용자, ou 및 사용자 그룹을 선택 하 여 채팅방에 관리 하 고 참여할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d38e8-110">After the category is created, they can choose users, OUs, and user groups from the category's **AllowedMembers** list as chat room managers and members to manage and participate in the room.</span></span>

## <a name="tasks-that-you-can-perform"></a><span data-ttu-id="d38e8-111">수행할 수 있는 작업</span><span class="sxs-lookup"><span data-stu-id="d38e8-111">Tasks that you can perform</span></span>

<span data-ttu-id="d38e8-112">**허용 구성원 선택** 페이지에서는 다음 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d38e8-112">You can perform the following tasks on the **Select Allowed Members** page:</span></span>

- [<span data-ttu-id="d38e8-113">Configure Categories</span><span class="sxs-lookup"><span data-stu-id="d38e8-113">Configure Categories</span></span>](https://technet.microsoft.com/library/4547f514-f0c0-404d-890f-092ddeeac852.aspx)

- [<span data-ttu-id="d38e8-114">New Persistent Chat Server Features</span><span class="sxs-lookup"><span data-stu-id="d38e8-114">New Persistent Chat Server Features</span></span>](https://technet.microsoft.com/library/c3ec6f33-6261-4bf5-aa31-baa8ab2a87d8.aspx)

<span data-ttu-id="d38e8-115">비즈니스용 Skype 서버 제어판을 사용 하 여 수행할 수 있는 다양 한 절차에 대 한 자세한 내용은 비즈니스용 [Skype 서버 2015 관리](../../manage/manage.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d38e8-115">For details about the different procedures that you can perform by using the Skype for Business Server Control Panel, see [Manage Skype for Business Server 2015](../../manage/manage.md).</span></span>

## <a name="to-configure-categories-for-chat-rooms"></a><span data-ttu-id="d38e8-116">채팅방에 대한 범주를 구성하려면</span><span class="sxs-lookup"><span data-stu-id="d38e8-116">To configure categories for chat rooms</span></span>

<span data-ttu-id="d38e8-117">**구성원 자격**의 허용 된 **구성원** 섹션에서 사용자 및 기타 Active Directory 도메인 서비스 주체 (사용자, 메일 그룹, 조직 구성 단위 등)를 추가 하거나 제거 하 여 범주에 속하는 채팅방의 구성원으로 추가할 수 있도록 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d38e8-117">In **Membership**, in the **Allowed members** section, add or remove users and other Active Directory Domain Services principals (users, distribution groups, organizational units, and so on) that are permitted to be added as members of chat rooms belonging to the category.</span></span> <span data-ttu-id="d38e8-118">특정 범주에서 허용된 계정은 채팅방의 구성원만 디렉터리에서 채팅방을 검색할 수 있도록 채팅방이 숨겨져 있지 않은 한 해당 범주에서 채팅방을 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d38e8-118">Principals permitted by a category can search for the rooms in the category (unless the room is hidden, in which case only members of the room can search for it in the directory).</span></span>


<span data-ttu-id="d38e8-119">영구 채팅 서버 기능 및 기능에 대 한 자세한 내용은 계획 설명서의 [영구 채팅 서버 개요](https://technet.microsoft.com/library/23f7c886-304d-495a-ae70-3cbb44241acd.aspx) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d38e8-119">For details about Persistent Chat Server features and capabilities, see [Overview of Persistent Chat Server](https://technet.microsoft.com/library/23f7c886-304d-495a-ae70-3cbb44241acd.aspx) in the Planning documentation.</span></span> <span data-ttu-id="d38e8-120">영구 채팅 서버 구성을 사용 하는 방법에 대 한 자세한 내용은 배포 설명서의 [영구 채팅 서버 구성](https://technet.microsoft.com/library/d90a4049-b268-4e8e-9f24-0cef08c8d9ed.aspx) 및 운영 설명서의 [Lync Server 2013, 영구 채팅 서버 관리](https://technet.microsoft.com/library/82befdc6-5d32-45f1-bfd7-aaedffed1ab8.aspx) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d38e8-120">For details about working with Persistent Chat Server configurations, see [Configuring Persistent Chat Server](https://technet.microsoft.com/library/d90a4049-b268-4e8e-9f24-0cef08c8d9ed.aspx) in the Deployment documentation and [Managing Lync Server 2013, Persistent Chat Server](https://technet.microsoft.com/library/82befdc6-5d32-45f1-bfd7-aaedffed1ab8.aspx) in the Operations documentation.</span></span>

## <a name="see-also"></a><span data-ttu-id="d38e8-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d38e8-121">See also</span></span>

[<span data-ttu-id="d38e8-122">Understanding Persistent Chat Membership</span><span class="sxs-lookup"><span data-stu-id="d38e8-122">Understanding Persistent Chat Membership</span></span>](https://technet.microsoft.com/library/900392d6-6e9f-4dae-93d6-39d7474409ef.aspx)
