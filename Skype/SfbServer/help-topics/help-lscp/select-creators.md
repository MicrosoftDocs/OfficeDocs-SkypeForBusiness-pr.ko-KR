---
title: 생성자 선택
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/24/2015
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.SelectCreators
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f8d9ed6f-22ba-470e-b0b4-0da3cea5e961
description: 일관 된 채팅방을 만들고 관리 하는 것은 범주를 올바르게 사용 하는 것 보다 훨씬 더 쉽습니다. 영구 채팅 관리자는 각 범주에 대해 AllowedMembers 및 작성자를 정의할 수 있으며, 범주에서 만든 모든 채팅방에 적용 되는 기본 채팅방 설정 및 동작을 정의할 수도 있습니다. 영구 채팅 관리자 비즈니스용 Skype Server 제어판 또는 Windows PowerShell cmdlet을 사용 하 여 범주를 만들고 관리 합니다.
ms.openlocfilehash: 6fc3feb4465f1ad55d369ed736ea277853aadc13
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36196450"
---
# <a name="select-creators"></a><span data-ttu-id="44151-105">생성자 선택</span><span class="sxs-lookup"><span data-stu-id="44151-105">Select Creators</span></span>

<span data-ttu-id="44151-106">일관 된 채팅방을 만들고 관리 하는 것은 범주를 올바르게 사용 하는 것 보다 훨씬 더 쉽습니다.</span><span class="sxs-lookup"><span data-stu-id="44151-106">Creating and managing Persistent Chat rooms is much easier with the correct use of categories.</span></span> <span data-ttu-id="44151-107">영구 채팅 관리자는 각 범주에 대해 **Allowedmembers** 및 **작성자** 를 정의할 수 있으며, 범주에서 만든 모든 채팅방에 적용 되는 기본 채팅방 설정 및 동작을 정의할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44151-107">A Persistent Chat administrator can define **AllowedMembers** and **Creators** for each category, and can also define the default chat room settings and behaviors that will be applied to all chat rooms created in the category.</span></span> <span data-ttu-id="44151-108">영구 채팅 관리자 비즈니스용 Skype Server 제어판 또는 Windows PowerShell cmdlet을 사용 하 여 범주를 만들고 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="44151-108">Persistent Chat administrators create and manage categories by using Skype for Business Server Control Panel or Windows PowerShell cmdlets.</span></span>

## <a name="tasks-that-you-can-perform"></a><span data-ttu-id="44151-109">수행할 수 있는 작업</span><span class="sxs-lookup"><span data-stu-id="44151-109">Tasks that you can perform</span></span>

<span data-ttu-id="44151-110">**생성자 선택** 페이지에서는 다음 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44151-110">You can perform the following tasks on the **Select Creators** page:</span></span>

- [<span data-ttu-id="44151-111">Configure Categories</span><span class="sxs-lookup"><span data-stu-id="44151-111">Configure Categories</span></span>](https://technet.microsoft.com/library/4547f514-f0c0-404d-890f-092ddeeac852.aspx)

- [<span data-ttu-id="44151-112">New Persistent Chat Server Features</span><span class="sxs-lookup"><span data-stu-id="44151-112">New Persistent Chat Server Features</span></span>](https://technet.microsoft.com/library/c3ec6f33-6261-4bf5-aa31-baa8ab2a87d8.aspx)

<span data-ttu-id="44151-113">비즈니스용 Skype 서버 제어판을 사용 하 여 수행할 수 있는 다양 한 절차에 대 한 자세한 내용은 비즈니스용 [Skype 서버 2015 관리](../../manage/manage.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="44151-113">For details about the different procedures that you can perform by using the Skype for Business Server Control Panel, see [Manage Skype for Business Server 2015](../../manage/manage.md).</span></span>

## <a name="to-configure-categories-for-chat-rooms"></a><span data-ttu-id="44151-114">채팅방에 대한 범주를 구성하려면</span><span class="sxs-lookup"><span data-stu-id="44151-114">To configure categories for chat rooms</span></span>

<span data-ttu-id="44151-115">**멤버 자격**의 **작성자** 섹션에서 해당 범주에 대 한 작성자와 연결 된 사용자 및 기타 Active Directory 보안 주체를 추가 하거나 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="44151-115">In **Membership**, in the **Creators** section, add or remove users and other Active Directory principals associated with creators for the category.</span></span> <span data-ttu-id="44151-116">작성자는 채팅방을 만들고 채팅방 관리자 및 구성원을 지정할 권한이 있는 사용자입니다.</span><span class="sxs-lookup"><span data-stu-id="44151-116">A creator is a user who has permissions to create chat rooms and assign chat room managers and members.</span></span>



<span data-ttu-id="44151-117">영구 채팅 서버 기능 및 기능에 대 한 자세한 내용은 계획 설명서의 [영구 채팅 서버 개요](https://technet.microsoft.com/library/23f7c886-304d-495a-ae70-3cbb44241acd.aspx) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="44151-117">For details about Persistent Chat Server features and capabilities, see [Overview of Persistent Chat Server](https://technet.microsoft.com/library/23f7c886-304d-495a-ae70-3cbb44241acd.aspx) in the Planning documentation.</span></span> <span data-ttu-id="44151-118">영구 채팅 서버 구성을 사용 하는 방법에 대 한 자세한 내용은 배포 설명서의 [영구 채팅 서버 구성](https://technet.microsoft.com/library/d90a4049-b268-4e8e-9f24-0cef08c8d9ed.aspx) 및 운영 설명서의 [Lync Server 2013, 영구 채팅 서버 관리](https://technet.microsoft.com/library/82befdc6-5d32-45f1-bfd7-aaedffed1ab8.aspx) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="44151-118">For details about working with Persistent Chat Server configurations, see [Configuring Persistent Chat Server](https://technet.microsoft.com/library/d90a4049-b268-4e8e-9f24-0cef08c8d9ed.aspx) in the Deployment documentation and [Managing Lync Server 2013, Persistent Chat Server](https://technet.microsoft.com/library/82befdc6-5d32-45f1-bfd7-aaedffed1ab8.aspx) in the Operations documentation.</span></span>

## <a name="see-also"></a><span data-ttu-id="44151-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="44151-119">See also</span></span>

[<span data-ttu-id="44151-120">Understanding Persistent Chat Membership</span><span class="sxs-lookup"><span data-stu-id="44151-120">Understanding Persistent Chat Membership</span></span>](https://technet.microsoft.com/library/900392d6-6e9f-4dae-93d6-39d7474409ef.aspx)

[<span data-ttu-id="44151-121">범주를 사용 하 여 영구 채팅 서버 관리</span><span class="sxs-lookup"><span data-stu-id="44151-121">Using Categories to Administer Persistent Chat Server</span></span>](https://technet.microsoft.com/library/dfcb3ad1-da90-467e-b08c-f4e68673b7b5.aspx)

[<span data-ttu-id="44151-122">채팅방을 한 범주에서 다른 범주로 이동</span><span class="sxs-lookup"><span data-stu-id="44151-122">Moving a Chat Room from One Category to Another</span></span>](https://technet.microsoft.com/library/7e93b8f6-5a18-4476-a432-3918e01bcfa6.aspx)

[<span data-ttu-id="44151-123">새 채팅방 만들기 또는 편집</span><span class="sxs-lookup"><span data-stu-id="44151-123">Creating or Editing a New Room</span></span>](https://technet.microsoft.com/library/aa8f4349-cfd9-4036-9c4d-de8fb2c4c8a4.aspx)
