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
description: 영구 채팅 관리자는 채팅방 범주를 만들고 관리할 수 있습니다. 영구 채팅 관리자는 채팅방 범주 만들기 및 관리의 일부로 특정 범주의 채팅방 구성원/작성자가 될 수 있는 보안 주체(Active Directory 도메인 서비스 그룹/컨테이너/사용자)를 구성할 수 있습니다. 영구 채팅 관리자는 범주에 DeniedMembers를 추가할 수 있으며 이러한 항목은 허용 목록에 대한 명시적 제외가 됩니다. DeniedMembers는 AllowedMembers에 있는 것을 저버림합니다.
ms.openlocfilehash: c5f942723937fe2da28025fba5da1fc7ee121c83
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814578"
---
# <a name="select-denied-members"></a><span data-ttu-id="44602-106">거부 구성원 선택</span><span class="sxs-lookup"><span data-stu-id="44602-106">Select Denied Members</span></span>

<span data-ttu-id="44602-107">영구 채팅 관리자는 채팅방 범주를 만들고 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44602-107">A Persistent Chat Administrator can create and manage chat room categories.</span></span> <span data-ttu-id="44602-108">영구 채팅 관리자는 채팅방 범주 만들기 및 관리의 일부로 특정 범주의 채팅방 구성원/작성자가 될 수 있는 보안 주체(Active Directory 도메인 서비스 그룹/컨테이너/사용자)를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44602-108">As part of creating and managing chat room categories, a Persistent Chat Administrator can configure principals (Active Directory Domain Services groups/containers/users) that have access to be members/creators of chat rooms of a particular category.</span></span> <span data-ttu-id="44602-109">영구 채팅 관리자는 범주에 DeniedMembers를 추가할 수 있으며 이러한 항목은 허용 목록에 대한 명시적 제외가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="44602-109">A Persistent Chat Administrator can also add DeniedMembers to a category and these become explicit exclusions to the allowed list.</span></span> <span data-ttu-id="44602-110">DeniedMembers는 AllowedMembers에 있는 것을 저버림합니다.</span><span class="sxs-lookup"><span data-stu-id="44602-110">DeniedMembers override what's in AllowedMembers.</span></span>

## <a name="tasks-that-you-can-perform"></a><span data-ttu-id="44602-111">수행할 수 있는 작업</span><span class="sxs-lookup"><span data-stu-id="44602-111">Tasks that you can perform</span></span>

<span data-ttu-id="44602-112">**거부 구성원 선택** 페이지에서는 다음 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44602-112">You can perform the following tasks on the **Select Denied Members** page:</span></span>

- [<span data-ttu-id="44602-113">범주 구성</span><span class="sxs-lookup"><span data-stu-id="44602-113">Configure Categories</span></span>](https://technet.microsoft.com/library/4547f514-f0c0-404d-890f-092ddeeac852.aspx)

- [<span data-ttu-id="44602-114">새 영구 채팅 서버 기능</span><span class="sxs-lookup"><span data-stu-id="44602-114">New Persistent Chat Server Features</span></span>](https://technet.microsoft.com/library/c3ec6f33-6261-4bf5-aa31-baa8ab2a87d8.aspx)

<span data-ttu-id="44602-115">비즈니스용 Skype 서버 제어판을 사용하여 수행할 수 있는 다양한 절차에 대한 자세한 내용은 비즈니스용 [Skype 서버 2015를 참조하세요.](../../manage/manage.md)</span><span class="sxs-lookup"><span data-stu-id="44602-115">For details about the different procedures that you can perform by using the Skype for Business Server Control Panel, see [Manage Skype for Business Server 2015](../../manage/manage.md).</span></span>

## <a name="to-configure-categories-for-chat-rooms"></a><span data-ttu-id="44602-116">채팅방에 대해 범주를 구성하려면</span><span class="sxs-lookup"><span data-stu-id="44602-116">To configure categories for chat rooms</span></span>

<span data-ttu-id="44602-117">구성원 **자격의** **거부된** 구성원 섹션에서 방에서 거부되는 구성원과 관련된 사용자 및 기타 Active Directory 사용자를 추가하거나 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="44602-117">In **Membership**, in the **Denied members** section, add or remove users and other Active Directory principals associated with members being denied from the room.</span></span>


<span data-ttu-id="44602-118">영구 채팅 서버 기능에 대한 자세한 내용은 계획 설명서에서 영구 채팅 [서버](https://technet.microsoft.com/library/23f7c886-304d-495a-ae70-3cbb44241acd.aspx) 개요를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="44602-118">For details about Persistent Chat Server features and capabilities, see [Overview of Persistent Chat Server](https://technet.microsoft.com/library/23f7c886-304d-495a-ae70-3cbb44241acd.aspx) in the Planning documentation.</span></span> <span data-ttu-id="44602-119">영구 채팅 서버 구성을 사용하는 데 대한 [](https://technet.microsoft.com/library/d90a4049-b268-4e8e-9f24-0cef08c8d9ed.aspx) 자세한 내용은 배포 설명서에서 영구 채팅 서버 구성 및 작업 설명서에서 [Lync Server 2013, 영구](https://technet.microsoft.com/library/82befdc6-5d32-45f1-bfd7-aaedffed1ab8.aspx) 채팅 서버 관리를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="44602-119">For details about working with Persistent Chat Server configurations, see [Configuring Persistent Chat Server](https://technet.microsoft.com/library/d90a4049-b268-4e8e-9f24-0cef08c8d9ed.aspx) in the Deployment documentation and [Managing Lync Server 2013, Persistent Chat Server](https://technet.microsoft.com/library/82befdc6-5d32-45f1-bfd7-aaedffed1ab8.aspx) in the Operations documentation.</span></span>

## <a name="see-also"></a><span data-ttu-id="44602-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="44602-120">See also</span></span>

[<span data-ttu-id="44602-121">영구 채팅 구성원 이해</span><span class="sxs-lookup"><span data-stu-id="44602-121">Understanding Persistent Chat Membership</span></span>](https://technet.microsoft.com/library/900392d6-6e9f-4dae-93d6-39d7474409ef.aspx)
