---
title: 통화 대기
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.VoiceFeaCallParkMain
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: b752617d-554d-470e-b17b-387403ac74ed
ROBOTS: NOINDEX, NOFOLLOW
description: 통화가 일시적인 번호로 전송됩니다. 이 번호는 누군가가 통화를 재개하거나 통화가 시간 외일 때까지 통화가 보전됩니다. 파킹된 통화를 위해 보존할 내선 번호 범위로 테이블을 구성해야 합니다. 이 내선 번호는 가상 내선 번호여야 합니다(즉 이 번호에 할당된 사용자나 전화가 없어야 함). 통화 파크 응용 프로그램을 실행하는 각 풀에는 하나 이상의 내선 범위가 있습니다. 이러한 범위는 배포 전체에서 전역적으로 고유해야 합니다.
ms.openlocfilehash: b7926c10424fd5902fdc43e6c0fccadb45e61f79
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51097074"
---
# <a name="call-park"></a><span data-ttu-id="828b0-106">Call Park</span><span class="sxs-lookup"><span data-stu-id="828b0-106">Call Park</span></span>

<span data-ttu-id="828b0-107">통화가 일시적인 번호로 전송됩니다. 이 번호는 누군가가 통화를 재개하거나 통화가 시간 외일 때까지 통화가 보전됩니다. 파킹된 통화를 위해 보존할 내선 번호 범위로 테이블을 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="828b0-107">When a call is parked, it is transferred to a temporary number where the call is held until someone retrieves it or it times out. You need to configure a table with the ranges of extension numbers that you are reserving for parked calls.</span></span> <span data-ttu-id="828b0-108">이 내선 번호는 가상 내선 번호여야 합니다(즉 이 번호에 할당된 사용자나 전화가 없어야 함).</span><span class="sxs-lookup"><span data-stu-id="828b0-108">These extensions need to be virtual extensions (that is, extensions that have no user or phone assigned to them).</span></span> <span data-ttu-id="828b0-109">통화 파크 응용 프로그램을 실행하는 각 풀에는 하나 이상의 내선 범위가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="828b0-109">Each pool that runs the Call Park application can have one or more ranges of extensions.</span></span> <span data-ttu-id="828b0-110">이러한 범위는 배포 전체에서 전역적으로 고유해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="828b0-110">These ranges must be globally unique across your deployment.</span></span>

<span data-ttu-id="828b0-111">통화 **파크 페이지에는** 조직에 대해 정의된 모든 통화 파크 번호 범위의 목록이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="828b0-111">The **Call Park** page displays a list of all the Call Park number ranges that are defined for your organization.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="828b0-112">수행할 수 있는 작업</span><span class="sxs-lookup"><span data-stu-id="828b0-112">Tasks you can perform</span></span>

<span data-ttu-id="828b0-113">**통화 대기** 페이지에서는 다음 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="828b0-113">You can perform the following tasks from the **Call Park** page:</span></span>

- <span data-ttu-id="828b0-114">새 번호 범위 만들기</span><span class="sxs-lookup"><span data-stu-id="828b0-114">Create a new number range</span></span>

- <span data-ttu-id="828b0-115">기존 번호 범위 변경</span><span class="sxs-lookup"><span data-stu-id="828b0-115">Change an existing number range</span></span>

- <span data-ttu-id="828b0-116">번호 범위 삭제</span><span class="sxs-lookup"><span data-stu-id="828b0-116">Delete a number range</span></span>

## <a name="ui-reference"></a><span data-ttu-id="828b0-117">UI 참조</span><span class="sxs-lookup"><span data-stu-id="828b0-117">UI Reference</span></span>

<span data-ttu-id="828b0-118">다음 목록에서는 페이지의 명령에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="828b0-118">The following list describes the commands on the page.</span></span>

- <span data-ttu-id="828b0-119">**새로 추가** 새 통화 파크 번호 범위를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="828b0-119">**New** Starts a new Call Park number range.</span></span>

- <span data-ttu-id="828b0-120">**편집** 편집할 선택한 번호 범위를 열거나 목록의 모든 번호 범위를 선택하거나 선택한 번호 범위를 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="828b0-120">**Edit** Opens the selected number range for editing, selects all number ranges in the list, or deletes the selected number range.</span></span>

- <span data-ttu-id="828b0-121">**새로 고침** 번호 범위 목록을 새로 고침합니다.</span><span class="sxs-lookup"><span data-stu-id="828b0-121">**Refresh** Refreshes the list of number ranges.</span></span>

<span data-ttu-id="828b0-122">다음 목록에서는 페이지의 필드에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="828b0-122">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="828b0-123">**이름** 번호 범위를 식별하는 고유 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="828b0-123">**Name** The unique name that identifies the number range.</span></span>

- <span data-ttu-id="828b0-124">**시작 범위** 범위의 시작 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="828b0-124">**Start range** The beginning number of the range.</span></span>

- <span data-ttu-id="828b0-125">**끝 범위** 범위의 끝 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="828b0-125">**End range** The ending number of the range.</span></span>

- <span data-ttu-id="828b0-126">**대상** 번호 범위에 대한 통화 파크 응용 프로그램을 호스팅하는 응용 프로그램 서비스의 FQDN(정식 도메인 이름) 또는 서비스 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="828b0-126">**Destination** The fully qualified domain name (FQDN) or service ID of the Application service that hosts the Call Park application for the number range.</span></span>

<span data-ttu-id="828b0-127">통화 파크 기능에 대한 자세한 내용은 [Plan for Call Park in Skype for Business을 참조하세요.](../../../plan-your-deployment/enterprise-voice-solution/call-park.md)</span><span class="sxs-lookup"><span data-stu-id="828b0-127">For details about Call Park features and capabilities, see [Plan for Call Park in Skype for Business](../../../plan-your-deployment/enterprise-voice-solution/call-park.md).</span></span> <span data-ttu-id="828b0-128">통화 파킹 번호 범위를 사용할 수 있는 자세한 내용은 [Configure Phone Number Extensions for Parking Calls을 참조합니다.](/previous-versions/office/lync-server-2013/lync-server-2013-configure-phone-number-extensions-for-parking-calls)</span><span class="sxs-lookup"><span data-stu-id="828b0-128">For details about working with Call Park number ranges, see [Configure Phone Number Extensions for Parking Calls](/previous-versions/office/lync-server-2013/lync-server-2013-configure-phone-number-extensions-for-parking-calls).</span></span>