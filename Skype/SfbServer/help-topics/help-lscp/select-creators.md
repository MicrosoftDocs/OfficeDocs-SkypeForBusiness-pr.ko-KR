---
title: 생성자 선택
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
- ms.lync.lscp.SelectCreators
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f8d9ed6f-22ba-470e-b0b4-0da3cea5e961
description: 범주를 올바르게 사용하여 영구 채팅방을 만들고 관리하는 것이 훨씬 더 쉽습니다. 영구 채팅 관리자는 각 범주에 대해 AllowedMembers 및 Creators를 정의할 수 있으며 범주에서 만든 모든 채팅방에 적용되는 기본 채팅방 설정 및 동작을 정의할 수도 있습니다. 영구 채팅 관리자는 비즈니스용 Skype 서버 제어판 또는 cmdlet을 사용하여 Windows PowerShell 관리합니다.
ms.openlocfilehash: 7d98ff058251b8bd14eb37a0ae5ba633f5a99c48
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51107954"
---
# <a name="select-creators"></a><span data-ttu-id="7e602-105">생성자 선택</span><span class="sxs-lookup"><span data-stu-id="7e602-105">Select Creators</span></span>

<span data-ttu-id="7e602-106">범주를 올바르게 사용하여 영구 채팅방을 만들고 관리하는 것이 훨씬 더 쉽습니다.</span><span class="sxs-lookup"><span data-stu-id="7e602-106">Creating and managing Persistent Chat rooms is much easier with the correct use of categories.</span></span> <span data-ttu-id="7e602-107">영구 채팅 관리자는 각 범주에 **대해 AllowedMembers** 및 **Creators를** 정의할 수 있으며 범주에서 만든 모든 채팅방에 적용되는 기본 채팅방 설정 및 동작을 정의할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7e602-107">A Persistent Chat administrator can define **AllowedMembers** and **Creators** for each category, and can also define the default chat room settings and behaviors that will be applied to all chat rooms created in the category.</span></span> <span data-ttu-id="7e602-108">영구 채팅 관리자는 비즈니스용 Skype 서버 제어판 또는 cmdlet을 사용하여 Windows PowerShell 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="7e602-108">Persistent Chat administrators create and manage categories by using Skype for Business Server Control Panel or Windows PowerShell cmdlets.</span></span>

## <a name="tasks-that-you-can-perform"></a><span data-ttu-id="7e602-109">수행할 수 있는 작업</span><span class="sxs-lookup"><span data-stu-id="7e602-109">Tasks that you can perform</span></span>

<span data-ttu-id="7e602-110">**생성자 선택** 페이지에서는 다음 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7e602-110">You can perform the following tasks on the **Select Creators** page:</span></span>

- [<span data-ttu-id="7e602-111">범주 구성</span><span class="sxs-lookup"><span data-stu-id="7e602-111">Configure Categories</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-configure-categories)

- [<span data-ttu-id="7e602-112">새 영구 채팅 서버 기능</span><span class="sxs-lookup"><span data-stu-id="7e602-112">New Persistent Chat Server Features</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-new-persistent-chat-server-features)

<span data-ttu-id="7e602-113">비즈니스용 Skype 서버 제어판을 사용하여 수행할 수 있는 다양한 절차에 대한 자세한 내용은 [Manage Skype for Business Server 2015를 참조하세요.](../../manage/manage.md)</span><span class="sxs-lookup"><span data-stu-id="7e602-113">For details about the different procedures that you can perform by using the Skype for Business Server Control Panel, see [Manage Skype for Business Server 2015](../../manage/manage.md).</span></span>

## <a name="to-configure-categories-for-chat-rooms"></a><span data-ttu-id="7e602-114">채팅방에 대해 범주를 구성하려면</span><span class="sxs-lookup"><span data-stu-id="7e602-114">To configure categories for chat rooms</span></span>

<span data-ttu-id="7e602-115">구성원 **자격의** **작성자 섹션에서** 범주의 작성자와 연결된 사용자 및 기타 Active Directory 사용자를 추가하거나 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="7e602-115">In **Membership**, in the **Creators** section, add or remove users and other Active Directory principals associated with creators for the category.</span></span> <span data-ttu-id="7e602-116">작성자는 채팅방을 만들고 채팅방 관리자 및 구성원을 할당할 권한이 있는 사용자입니다.</span><span class="sxs-lookup"><span data-stu-id="7e602-116">A creator is a user who has permissions to create chat rooms and assign chat room managers and members.</span></span>



<span data-ttu-id="7e602-117">영구 채팅 서버 기능에 대한 자세한 내용은 계획 설명서에서 [Overview of Persistent Chat Server를](/previous-versions/office/lync-server-2013/lync-server-2013-overview-of-persistent-chat-server) 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="7e602-117">For details about Persistent Chat Server features and capabilities, see [Overview of Persistent Chat Server](/previous-versions/office/lync-server-2013/lync-server-2013-overview-of-persistent-chat-server) in the Planning documentation.</span></span> <span data-ttu-id="7e602-118">영구 채팅 서버 구성을 사용하는 데 대한 자세한 내용은 배포 설명서의 [Configuring Persistent Chat Server](/previous-versions/office/lync-server-2013/lync-server-2013-configuring-persistent-chat-server) 및 작업 설명서의 [Managing Lync Server 2013, Persistent Chat Server를](/previous-versions/office/lync-server-2013/managing-lync-server-2013-persistent-chat-server) 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="7e602-118">For details about working with Persistent Chat Server configurations, see [Configuring Persistent Chat Server](/previous-versions/office/lync-server-2013/lync-server-2013-configuring-persistent-chat-server) in the Deployment documentation and [Managing Lync Server 2013, Persistent Chat Server](/previous-versions/office/lync-server-2013/managing-lync-server-2013-persistent-chat-server) in the Operations documentation.</span></span>

## <a name="see-also"></a><span data-ttu-id="7e602-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7e602-119">See also</span></span>

[<span data-ttu-id="7e602-120">영구 채팅 구성원 이해</span><span class="sxs-lookup"><span data-stu-id="7e602-120">Understanding Persistent Chat Membership</span></span>](/previous-versions/office/lync-server-2013/understanding-persistent-chat-membership)

[<span data-ttu-id="7e602-121">범주를 사용하여 영구 채팅 서버 관리</span><span class="sxs-lookup"><span data-stu-id="7e602-121">Using Categories to Administer Persistent Chat Server</span></span>](/previous-versions/office/lync-server-2013/using-categories-to-administer-persistent-chat-server)

[<span data-ttu-id="7e602-122">범주 간 대화방 이동</span><span class="sxs-lookup"><span data-stu-id="7e602-122">Moving a Chat Room from One Category to Another</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-moving-a-chat-room-from-one-category-to-another)

[<span data-ttu-id="7e602-123">새 회의실 만들기 및 편집</span><span class="sxs-lookup"><span data-stu-id="7e602-123">Creating or Editing a New Room</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-creating-or-editing-a-new-room)