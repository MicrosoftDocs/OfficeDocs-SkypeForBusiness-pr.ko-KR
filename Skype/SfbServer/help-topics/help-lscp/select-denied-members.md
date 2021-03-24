---
title: 거부 구성원 선택
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
- ms.lync.lscp.SelectDeniedMembers
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c626b6b4-15f3-4a59-bb1d-55dc8c60f5cb
description: 영구 채팅 관리자는 채팅방 범주를 만들고 관리할 수 있습니다. 채팅방 범주를 만들고 관리하는 동안 영구 채팅 관리자는 특정 범주의 채팅방 구성원/작성자가 될 수 있는 보안 주체(Active Directory 도메인 서비스 그룹/컨테이너/사용자)를 구성할 수 있습니다. 영구 채팅 관리자는 범주에 DeniedMembers를 추가할 수 있으며 이러한 항목은 허용 목록에 대한 명시적 제외가 됩니다. DeniedMembers는 AllowedMembers에 있는 것을 대신합니다.
ms.openlocfilehash: 5a31716c2fae15c6216ed050b543673479415a76
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51107964"
---
# <a name="select-denied-members"></a><span data-ttu-id="d3356-106">거부 구성원 선택</span><span class="sxs-lookup"><span data-stu-id="d3356-106">Select Denied Members</span></span>

<span data-ttu-id="d3356-107">영구 채팅 관리자는 채팅방 범주를 만들고 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3356-107">A Persistent Chat Administrator can create and manage chat room categories.</span></span> <span data-ttu-id="d3356-108">채팅방 범주를 만들고 관리하는 동안 영구 채팅 관리자는 특정 범주의 채팅방 구성원/작성자가 될 수 있는 보안 주체(Active Directory 도메인 서비스 그룹/컨테이너/사용자)를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3356-108">As part of creating and managing chat room categories, a Persistent Chat Administrator can configure principals (Active Directory Domain Services groups/containers/users) that have access to be members/creators of chat rooms of a particular category.</span></span> <span data-ttu-id="d3356-109">영구 채팅 관리자는 범주에 DeniedMembers를 추가할 수 있으며 이러한 항목은 허용 목록에 대한 명시적 제외가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d3356-109">A Persistent Chat Administrator can also add DeniedMembers to a category and these become explicit exclusions to the allowed list.</span></span> <span data-ttu-id="d3356-110">DeniedMembers는 AllowedMembers에 있는 것을 대신합니다.</span><span class="sxs-lookup"><span data-stu-id="d3356-110">DeniedMembers override what's in AllowedMembers.</span></span>

## <a name="tasks-that-you-can-perform"></a><span data-ttu-id="d3356-111">수행할 수 있는 작업</span><span class="sxs-lookup"><span data-stu-id="d3356-111">Tasks that you can perform</span></span>

<span data-ttu-id="d3356-112">**거부 구성원 선택** 페이지에서는 다음 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3356-112">You can perform the following tasks on the **Select Denied Members** page:</span></span>

- [<span data-ttu-id="d3356-113">범주 구성</span><span class="sxs-lookup"><span data-stu-id="d3356-113">Configure Categories</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-configure-categories)

- [<span data-ttu-id="d3356-114">새 영구 채팅 서버 기능</span><span class="sxs-lookup"><span data-stu-id="d3356-114">New Persistent Chat Server Features</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-new-persistent-chat-server-features)

<span data-ttu-id="d3356-115">비즈니스용 Skype 서버 제어판을 사용하여 수행할 수 있는 다양한 절차에 대한 자세한 내용은 [Manage Skype for Business Server 2015를 참조하세요.](../../manage/manage.md)</span><span class="sxs-lookup"><span data-stu-id="d3356-115">For details about the different procedures that you can perform by using the Skype for Business Server Control Panel, see [Manage Skype for Business Server 2015](../../manage/manage.md).</span></span>

## <a name="to-configure-categories-for-chat-rooms"></a><span data-ttu-id="d3356-116">채팅방에 대해 범주를 구성하려면</span><span class="sxs-lookup"><span data-stu-id="d3356-116">To configure categories for chat rooms</span></span>

<span data-ttu-id="d3356-117">구성원 **자격의** **거부된** 구성원 섹션에서 방에서 거부되는 구성원과 연결된 사용자 및 기타 Active Directory 사용자를 추가하거나 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="d3356-117">In **Membership**, in the **Denied members** section, add or remove users and other Active Directory principals associated with members being denied from the room.</span></span>


<span data-ttu-id="d3356-118">영구 채팅 서버 기능에 대한 자세한 내용은 계획 설명서에서 [Overview of Persistent Chat Server를](/previous-versions/office/lync-server-2013/lync-server-2013-overview-of-persistent-chat-server) 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="d3356-118">For details about Persistent Chat Server features and capabilities, see [Overview of Persistent Chat Server](/previous-versions/office/lync-server-2013/lync-server-2013-overview-of-persistent-chat-server) in the Planning documentation.</span></span> <span data-ttu-id="d3356-119">영구 채팅 서버 구성을 사용하는 데 대한 자세한 내용은 배포 설명서의 [Configuring Persistent Chat Server](/previous-versions/office/lync-server-2013/lync-server-2013-configuring-persistent-chat-server) 및 작업 설명서의 [Managing Lync Server 2013, Persistent Chat Server를](/previous-versions/office/lync-server-2013/managing-lync-server-2013-persistent-chat-server) 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="d3356-119">For details about working with Persistent Chat Server configurations, see [Configuring Persistent Chat Server](/previous-versions/office/lync-server-2013/lync-server-2013-configuring-persistent-chat-server) in the Deployment documentation and [Managing Lync Server 2013, Persistent Chat Server](/previous-versions/office/lync-server-2013/managing-lync-server-2013-persistent-chat-server) in the Operations documentation.</span></span>

## <a name="see-also"></a><span data-ttu-id="d3356-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d3356-120">See also</span></span>

[<span data-ttu-id="d3356-121">영구 채팅 구성원 이해</span><span class="sxs-lookup"><span data-stu-id="d3356-121">Understanding Persistent Chat Membership</span></span>](/previous-versions/office/lync-server-2013/understanding-persistent-chat-membership)