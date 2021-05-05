---
title: Microsoft Teams를 사용한 Microsoft 365 Business Voice의 사용자 지정
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
f1.keywords:
- NOCSH
localization_priority: Priority
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- Teams_Business_Voice
search.appverid: MET150
description: 조직의 특정 요구사항에 맞게 Microsoft 365 Business Voice를 사용자 지정하는 방법에 대해 알아보세요.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9f72aac2f14e68022a673ee45585e9184814418f
ms.sourcegitcommit: 49cdcf344c63c805bcb6365804c6f5d1393e926a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2021
ms.locfileid: "52130227"
---
# <a name="customize-microsoft-365-business-voice"></a><span data-ttu-id="e8f1b-103">Microsoft 365 Business Voice 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="e8f1b-103">Customize Microsoft 365 Business Voice</span></span>

<span data-ttu-id="e8f1b-104">[Business Voice 설정 가이드](set-up-overview.md)가 기본 옵션과 함께 Business Voice를 설정하여 사용자가 바로 사용할 수 있도록 해줍니다.</span><span class="sxs-lookup"><span data-stu-id="e8f1b-104">The [Business Voice setup guide](set-up-overview.md) sets up Business Voice with basic options so you can use it right away.</span></span> <span data-ttu-id="e8f1b-105">규모가 작은 신규 기업이나 대규모 조직에서 시험 적용을 실행하는 경우에는 이들 옵션이 충분할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e8f1b-105">Those options might be enough if you're a small business just starting out or if you're running a pilot in your larger organization.</span></span> <span data-ttu-id="e8f1b-106">사용자는 새 전화 번호, 전화 메뉴 등을 제공받습니다.</span><span class="sxs-lookup"><span data-stu-id="e8f1b-106">You get the basics with new phone numbers and a call menu.</span></span>

<span data-ttu-id="e8f1b-107">그러나 비즈니스 요구 사항에 맞게 Business Voice를 사용자 지정하고 싶을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e8f1b-107">But you'll likely want to customize Business Voice to better meet your business needs.</span></span> <span data-ttu-id="e8f1b-108">예를 들어 아마도 기존의 전화 번호(번호 포팅)를 Business Voice로 이동하고자 할 확률이 높습니다.</span><span class="sxs-lookup"><span data-stu-id="e8f1b-108">For example, you'll probably want to move your existing phone numbers (called number porting) to Business Voice.</span></span>

| <span data-ttu-id="e8f1b-109">작업 </span><span class="sxs-lookup"><span data-stu-id="e8f1b-109">Task</span></span>                                                          | <span data-ttu-id="e8f1b-110">설명</span><span class="sxs-lookup"><span data-stu-id="e8f1b-110">Description</span></span>                                                                                          |
|---------------------------------------------------------------|------------------------------------------------------------------------------------------------------|
| [<span data-ttu-id="e8f1b-111">전화 번호를 Business Voice로 이동</span><span class="sxs-lookup"><span data-stu-id="e8f1b-111">Move phone numbers to Business Voice</span></span>](port-phone-numbers.md) | <span data-ttu-id="e8f1b-112">기존 전화 번호를 Business Voice로 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="e8f1b-112">Bring your existing phone numbers to Business Voice.</span></span>                                                 |
| [<span data-ttu-id="e8f1b-113">자동 전화 교환 설정</span><span class="sxs-lookup"><span data-stu-id="e8f1b-113">Set up auto attendants</span></span>](./create-a-phone-system-auto-attendant-smb.md)           | <span data-ttu-id="e8f1b-114">호출 메뉴를 더 추가하여 호출자가 사용자의 주요 전화 번호로 전화를 걸 때의 옵션을 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="e8f1b-114">Add more call menus to expand the options for callers who reach your main phone number.</span></span>        |
| [<span data-ttu-id="e8f1b-115">통화 정책 설정</span><span class="sxs-lookup"><span data-stu-id="e8f1b-115">Set up calling policies</span></span>](set-up-policies.md)                 | <span data-ttu-id="e8f1b-116">사용자가 비공개 통화를 할 수 있는지, 착신 전환, 호출 위임 등을 사용할 수 있는지를 컨트롤합니다.</span><span class="sxs-lookup"><span data-stu-id="e8f1b-116">Control whether users can do things like make private calls, use call forwarding, and delegate calls.</span></span>        |
| [<span data-ttu-id="e8f1b-117">추가 사용자 만들기</span><span class="sxs-lookup"><span data-stu-id="e8f1b-117">Create additional users</span></span>](create-users.md)                    | <span data-ttu-id="e8f1b-118">더 많은 사용자를 추가하고 새 전화 번호나 기존의 전화 번호를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="e8f1b-118">Add more users and assign new or existing phone numbers to them.</span></span>                                     |
| [<span data-ttu-id="e8f1b-119">통화 큐 설정</span><span class="sxs-lookup"><span data-stu-id="e8f1b-119">Set up call queues</span></span>](./create-a-phone-system-call-queue-smb.md)                   | <span data-ttu-id="e8f1b-120">호출자가 다음에 사용 가능한 에이전트를 위해 대기할 수 있는 큐를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="e8f1b-120">Create a queue where callers can wait for the next available agent.</span></span>                                  |