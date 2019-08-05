---
title: 통화 대기
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.VoiceFeaCallParkMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b752617d-554d-470e-b17b-387403ac74ed
ROBOTS: NOINDEX, NOFOLLOW
description: 대기 중인 통화는 다른 사용자가 검색 하거나 시간 초과 될 때까지 통화가 보류 되는 임시 번호로 전송 됩니다. 파킹 된 통화를 위해 예약 하는 내선 번호 범위를 사용 하 여 표를 구성 해야 합니다. 이 내선 번호는 가상 내선 번호여야 합니다(즉, 이 번호에 할당된 사용자나 전화가 없어야 함). 통화 공원 응용 프로그램을 실행 하는 각 풀에는 하나 이상의 확장 범위가 있을 수 있습니다. 이러한 범위는 배포 전체에서 전역적으로 고유해야 합니다.
ms.openlocfilehash: d325b1dd2066bd35f6dc9003de4c026a7f925a72
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36191688"
---
# <a name="call-park"></a><span data-ttu-id="252aa-106">통화 대기</span><span class="sxs-lookup"><span data-stu-id="252aa-106">Call Park</span></span>

<span data-ttu-id="252aa-107">대기 중인 통화는 다른 사용자가 검색 하거나 시간 초과 될 때까지 통화가 보류 되는 임시 번호로 전송 됩니다. 파킹 된 통화를 위해 예약 하는 내선 번호 범위를 사용 하 여 표를 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="252aa-107">When a call is parked, it is transferred to a temporary number where the call is held until someone retrieves it or it times out. You need to configure a table with the ranges of extension numbers that you are reserving for parked calls.</span></span> <span data-ttu-id="252aa-108">이 내선 번호는 가상 내선 번호여야 합니다(즉, 이 번호에 할당된 사용자나 전화가 없어야 함).</span><span class="sxs-lookup"><span data-stu-id="252aa-108">These extensions need to be virtual extensions (that is, extensions that have no user or phone assigned to them).</span></span> <span data-ttu-id="252aa-109">통화 공원 응용 프로그램을 실행 하는 각 풀에는 하나 이상의 확장 범위가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="252aa-109">Each pool that runs the Call Park application can have one or more ranges of extensions.</span></span> <span data-ttu-id="252aa-110">이러한 범위는 배포 전체에서 전역적으로 고유해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="252aa-110">These ranges must be globally unique across your deployment.</span></span>

<span data-ttu-id="252aa-111">**통화 공원** 페이지에는 조직에 대해 정의 된 모든 통화 공원 번호 범위가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="252aa-111">The **Call Park** page displays a list of all the Call Park number ranges that are defined for your organization.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="252aa-112">수행할 수 있는 작업</span><span class="sxs-lookup"><span data-stu-id="252aa-112">Tasks you can perform</span></span>

<span data-ttu-id="252aa-113">**통화 대기** 페이지에서는 다음 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="252aa-113">You can perform the following tasks from the **Call Park** page:</span></span>

- <span data-ttu-id="252aa-114">새 번호 범위 만들기</span><span class="sxs-lookup"><span data-stu-id="252aa-114">Create a new number range</span></span>

- <span data-ttu-id="252aa-115">기존 번호 범위 변경</span><span class="sxs-lookup"><span data-stu-id="252aa-115">Change an existing number range</span></span>

- <span data-ttu-id="252aa-116">번호 범위 삭제</span><span class="sxs-lookup"><span data-stu-id="252aa-116">Delete a number range</span></span>

## <a name="ui-reference"></a><span data-ttu-id="252aa-117">UI 참조</span><span class="sxs-lookup"><span data-stu-id="252aa-117">UI Reference</span></span>

<span data-ttu-id="252aa-118">다음 목록에서는 페이지의 명령에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="252aa-118">The following list describes the commands on the page.</span></span>

- <span data-ttu-id="252aa-119">**새로운** 새 통화 공원 번호 범위를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="252aa-119">**New** Starts a new Call Park number range.</span></span>

- <span data-ttu-id="252aa-120">**편집** 선택한 숫자 범위를 편집용으로 열거나 목록에 있는 모든 숫자 범위를 선택 하거나 선택한 숫자 범위를 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="252aa-120">**Edit** Opens the selected number range for editing, selects all number ranges in the list, or deletes the selected number range.</span></span>

- <span data-ttu-id="252aa-121">**새로 고침** 숫자 범위 목록을 새로 고칩니다.</span><span class="sxs-lookup"><span data-stu-id="252aa-121">**Refresh** Refreshes the list of number ranges.</span></span>

<span data-ttu-id="252aa-122">다음 목록에서는 페이지의 필드에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="252aa-122">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="252aa-123">**이름** 숫자 범위를 식별 하는 고유 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="252aa-123">**Name** The unique name that identifies the number range.</span></span>

- <span data-ttu-id="252aa-124">**시작 범위** 범위의 시작 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="252aa-124">**Start range** The beginning number of the range.</span></span>

- <span data-ttu-id="252aa-125">**끝 범위** 범위의 끝 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="252aa-125">**End range** The ending number of the range.</span></span>

- <span data-ttu-id="252aa-126">**대상** 숫자 범위에 대 한 통화 공원 응용 프로그램을 호스트 하는 응용 프로그램 서비스의 FQDN (정규화 된 도메인 이름) 또는 서비스 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="252aa-126">**Destination** The fully qualified domain name (FQDN) or service ID of the Application service that hosts the Call Park application for the number range.</span></span>

<span data-ttu-id="252aa-127">통화 공원 기능 및 기능에 대 한 자세한 내용은 [비즈니스용 Skype의 통화 공원 계획](../../../plan-your-deployment/enterprise-voice-solution/call-park.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="252aa-127">For details about Call Park features and capabilities, see [Plan for Call Park in Skype for Business](../../../plan-your-deployment/enterprise-voice-solution/call-park.md).</span></span> <span data-ttu-id="252aa-128">통화 공원 번호 범위 작업에 대 한 자세한 내용은 [파킹 통화에 대 한 전화 번호 확장 구성을](https://technet.microsoft.com/library/fbf97624-9587-42a6-b276-1b69c574a74d.aspx)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="252aa-128">For details about working with Call Park number ranges, see [Configure Phone Number Extensions for Parking Calls](https://technet.microsoft.com/library/fbf97624-9587-42a6-b276-1b69c574a74d.aspx).</span></span>


