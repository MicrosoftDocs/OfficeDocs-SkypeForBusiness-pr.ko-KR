---
title: 허용된 구성원 선택
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: 범주를 올바르게 사용하여 영구 채팅방을 만들고 관리하는 것이 훨씬 더 쉽습니다. 영구 채팅 관리자는 각 범주에 대해 AllowedMembers 및 Creators를 정의할 수 있으며 범주에서 만든 모든 채팅방에 적용할 기본 채팅방 설정 및 동작을 정의할 수도 있습니다. 영구 채팅 관리자는 제어판 또는 cmdlet을 사용하여 범주를 Windows PowerShell 관리합니다.
ms.openlocfilehash: 47abbec64f6799a85f3f6123a898eeae00becbdb
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51107994"
---
# <a name="select-allowed-members"></a><span data-ttu-id="77d4d-105">허용된 구성원 선택</span><span class="sxs-lookup"><span data-stu-id="77d4d-105">Select Allowed Members</span></span>

<span data-ttu-id="77d4d-106">범주를 올바르게 사용하여 영구 채팅방을 만들고 관리하는 것이 훨씬 더 쉽습니다.</span><span class="sxs-lookup"><span data-stu-id="77d4d-106">Creating and managing Persistent Chat rooms is much easier with the correct use of categories.</span></span> <span data-ttu-id="77d4d-107">영구 채팅 관리자는 각 범주에 **대해 AllowedMembers** 및 **Creators를** 정의할 수 있으며 범주에서 만든 모든 채팅방에 적용할 기본 채팅방 설정 및 동작을 정의할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77d4d-107">A Persistent Chat Administrator can define **AllowedMembers** and **Creators** for each category, and can also define the default chat room settings and behaviors that will be applied to all chat rooms created in the category.</span></span> <span data-ttu-id="77d4d-108">영구 채팅 관리자는 제어판 또는 cmdlet을 사용하여 범주를 Windows PowerShell 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="77d4d-108">Persistent Chat Administrators create and manage categories by using the control panel or Windows PowerShell cmdlets.</span></span>

<span data-ttu-id="77d4d-109">범주의 작성자로 식별되는 사용자, OU(조직 구성 단위) 및 사용자 그룹은 해당 범주에서 대화방을 만들 수 있는 개인과 그룹입니다.</span><span class="sxs-lookup"><span data-stu-id="77d4d-109">Users, Organizational Units (OUs), and user groups that are identified as Creators of the category are the only individuals and groups that are allowed to create rooms in the category.</span></span> <span data-ttu-id="77d4d-110">범주를 만든 후 범주의 **AllowedMembers** 목록에서 사용자, US 및 사용자 그룹을 채팅방 관리자 및 구성원으로 선택하여 채팅방을 관리하고 채팅방에 참가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77d4d-110">After the category is created, they can choose users, OUs, and user groups from the category's **AllowedMembers** list as chat room managers and members to manage and participate in the room.</span></span>

## <a name="tasks-that-you-can-perform"></a><span data-ttu-id="77d4d-111">수행할 수 있는 작업</span><span class="sxs-lookup"><span data-stu-id="77d4d-111">Tasks that you can perform</span></span>

<span data-ttu-id="77d4d-112">허용된 구성원 선택 페이지에서는 **다음 작업을 수행할 수** 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77d4d-112">You can perform the following tasks on the **Select Allowed Members** page:</span></span>

- [<span data-ttu-id="77d4d-113">범주 구성</span><span class="sxs-lookup"><span data-stu-id="77d4d-113">Configure Categories</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-configure-categories)

- [<span data-ttu-id="77d4d-114">새 영구 채팅 서버 기능</span><span class="sxs-lookup"><span data-stu-id="77d4d-114">New Persistent Chat Server Features</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-new-persistent-chat-server-features)

<span data-ttu-id="77d4d-115">비즈니스용 Skype 서버 제어판을 사용하여 수행할 수 있는 다양한 절차에 대한 자세한 내용은 [Manage Skype for Business Server 2015를 참조하세요.](../../manage/manage.md)</span><span class="sxs-lookup"><span data-stu-id="77d4d-115">For details about the different procedures that you can perform by using the Skype for Business Server Control Panel, see [Manage Skype for Business Server 2015](../../manage/manage.md).</span></span>

## <a name="to-configure-categories-for-chat-rooms"></a><span data-ttu-id="77d4d-116">채팅방에 대해 범주를 구성하려면</span><span class="sxs-lookup"><span data-stu-id="77d4d-116">To configure categories for chat rooms</span></span>

<span data-ttu-id="77d4d-117">구성원 **자격의**  허용 구성원 섹션에서 범주에 속하는 채팅방의 구성원으로 추가될 수 있는 사용자 및 기타 Active Directory 도메인 서비스 계정(사용자, 메일 그룹, 조직 구성 단위 등)을 추가하거나 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="77d4d-117">In **Membership**, in the **Allowed members** section, add or remove users and other Active Directory Domain Services principals (users, distribution groups, organizational units, and so on) that are permitted to be added as members of chat rooms belonging to the category.</span></span> <span data-ttu-id="77d4d-118">특정 범주에서 허용된 계정은 방의 구성원만 디렉터리에서 방을 검색할 수 있도록 방이 숨겨져 있지 않은 한 해당 범주에서 방을 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77d4d-118">Principals permitted by a category can search for the rooms in the category (unless the room is hidden, in which case only members of the room can search for it in the directory).</span></span>


<span data-ttu-id="77d4d-119">영구 채팅 서버 기능에 대한 자세한 내용은 계획 설명서에서 [Overview of Persistent Chat Server를](/previous-versions/office/lync-server-2013/lync-server-2013-overview-of-persistent-chat-server) 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="77d4d-119">For details about Persistent Chat Server features and capabilities, see [Overview of Persistent Chat Server](/previous-versions/office/lync-server-2013/lync-server-2013-overview-of-persistent-chat-server) in the Planning documentation.</span></span> <span data-ttu-id="77d4d-120">영구 채팅 서버 구성을 사용하는 데 대한 자세한 내용은 배포 설명서의 [Configuring Persistent Chat Server](/previous-versions/office/lync-server-2013/lync-server-2013-configuring-persistent-chat-server) 및 작업 설명서의 [Managing Lync Server 2013, Persistent Chat Server를](/previous-versions/office/lync-server-2013/managing-lync-server-2013-persistent-chat-server) 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="77d4d-120">For details about working with Persistent Chat Server configurations, see [Configuring Persistent Chat Server](/previous-versions/office/lync-server-2013/lync-server-2013-configuring-persistent-chat-server) in the Deployment documentation and [Managing Lync Server 2013, Persistent Chat Server](/previous-versions/office/lync-server-2013/managing-lync-server-2013-persistent-chat-server) in the Operations documentation.</span></span>

## <a name="see-also"></a><span data-ttu-id="77d4d-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="77d4d-121">See also</span></span>

[<span data-ttu-id="77d4d-122">영구 채팅 구성원 이해</span><span class="sxs-lookup"><span data-stu-id="77d4d-122">Understanding Persistent Chat Membership</span></span>](/previous-versions/office/lync-server-2013/understanding-persistent-chat-membership)