---
title: 통화 파크 새로 만들기 또는 기존 데이터 편집
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
- ms.lync.lscp.VoiceFeaCallParkEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e834d485-d25a-4eec-9090-2b8534ecf65d
description: 통화 파크 번호 범위는 누군가가 통화를 재개하거나 시간이 지날 때까지 통화가 보전되는 임시 번호를 정의합니다.
ms.openlocfilehash: 1a85bacf1ebb13afd7302f8e1cf50c112c3139e6
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51095682"
---
# <a name="call-park-create-new-or-edit-existing"></a><span data-ttu-id="a05d1-103">통화 파킹: 새로 만들기 또는 기존 항목 편집</span><span class="sxs-lookup"><span data-stu-id="a05d1-103">Call Park: Create New or Edit Existing</span></span>

<span data-ttu-id="a05d1-104">통화 파크 번호 범위는 누군가가 통화를 재개하거나 시간이 지날 때까지 통화가 보전되는 임시 번호를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="a05d1-104">Call Park number ranges define the temporary numbers where parked calls are held until someone retrieves them or they time out.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="a05d1-105">UI 참조</span><span class="sxs-lookup"><span data-stu-id="a05d1-105">UI Reference</span></span>

<span data-ttu-id="a05d1-106">다음 목록에서는 페이지의 필드에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="a05d1-106">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="a05d1-107">**이름** 번호 범위를 식별하는 설명적인 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="a05d1-107">**Name** Type a descriptive name that identifies the number range.</span></span> <span data-ttu-id="a05d1-108">번호 범위를 저장한 후 이 이름은 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a05d1-108">After you save the number range, this name cannot be changed.</span></span>

- <span data-ttu-id="a05d1-109">**번호 범위** 첫 번째 필드에 번호 범위의 시작 번호를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="a05d1-109">**Number range** In the first field, type the beginning number of the number range.</span></span> <span data-ttu-id="a05d1-110">두 번째 필드에 번호 범위의 끝 번호를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="a05d1-110">In the second field, type the ending number of the number range.</span></span>

  - <span data-ttu-id="a05d1-111">범위의 시작 번호는 범위의 마지막 번호보다 작거나 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a05d1-111">The beginning number of the range must be less than or equal to the ending number of the range.</span></span>

  - <span data-ttu-id="a05d1-112">범위의 시작 번호 값 길이는 범위의 마지막 번호 길이와 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a05d1-112">The value of the beginning number of the range must be the same length as the ending number of the range.</span></span>

  - <span data-ttu-id="a05d1-113">번호 범위는 고유해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a05d1-113">The number range must be unique.</span></span> <span data-ttu-id="a05d1-114">이 범위는 다른 범위와 겹칠 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a05d1-114">This range cannot overlap with any other range.</span></span>

  - <span data-ttu-id="a05d1-115">숫자 범위가 문자나 #로 시작하는 경우 범위는 \* 100보다 커야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a05d1-115">If the number range begins with the character \* or #, the range must be greater than 100.</span></span>

  - <span data-ttu-id="a05d1-116">유효한 값: 정규식 문자열([ \\ \*|#]?[ 1-9]\d {0,7} )| ([1-9]\d {0,8} ).</span><span class="sxs-lookup"><span data-stu-id="a05d1-116">Valid values: Must match the regular expression string ([\\*|#]?[1-9]\d{0,7})|([1-9]\d{0,8}).</span></span> <span data-ttu-id="a05d1-117">즉, 값은 문자나 #으로 시작되는 문자열 또는 1에서 9까지의 숫자(첫 번째 문자는 \* 0일 수 없습니다.)입니다.</span><span class="sxs-lookup"><span data-stu-id="a05d1-117">This means the value must be a string beginning with either the character \* or # or a number 1 through 9 (the first character cannot be a zero).</span></span> <span data-ttu-id="a05d1-118">첫 문자가 또는 #이면 다음 문자는 1에서 9까지의 숫자가 되어야 합니다. 0이 될 \* 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a05d1-118">If the first character is \* or #, the following character must be a number 1 through 9 (it cannot be a zero).</span></span> <span data-ttu-id="a05d1-119">이후 문자는 "#6000", \* "92000", " \* 95551212" 및 "915551212"과 같은 최대 7개의 추가 문자까지 0에서 9까지의 숫자를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a05d1-119">Subsequent characters can be any number 0 through 9 up to seven additional characters (for example, "#6000", "\*92000", "\*95551212", and "915551212").</span></span> <span data-ttu-id="a05d1-120">첫 번째 문자가 또는 #이 아니면 첫 번째 문자는 1에서 9까지의 숫자가 되어야 합니다(0일 수 없습니다). 그 다음에 0에서 9까지의 숫자를 입력할 수 있습니다(예: \* 915551212;41212;300).</span><span class="sxs-lookup"><span data-stu-id="a05d1-120">If the first character is not \* or #, the first character must be a number 1 through 9 (it cannot be zero), followed by up to eight characters, each a number 0 through 9 (for example: 915551212;41212;300).</span></span>

  - <span data-ttu-id="a05d1-121">풀당 숫자는 총 50,000개 이상이면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a05d1-121">You should not have more than a total of 50,000 numbers per pool.</span></span> <span data-ttu-id="a05d1-122">각 번호 범위에는 일반적으로 100개 이하의 숫자가 포함되지만 숫자가 10,000개 미만인 경우 훨씬 클 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a05d1-122">Each number range typically encompasses 100 or fewer numbers, but it can be much larger as long as it includes fewer than 10,000 numbers.</span></span> <span data-ttu-id="a05d1-123">예를 들어 시작 번호를 "7000000"로, 끝 번호를 "8000000"으로 지정하는 대신 시작 번호를 "7000000"로, 끝 번호를 "7000100"으로 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a05d1-123">For example, instead of specifying a starting number of "7000000" and an ending number of "8000000," consider specifying a starting number of "7000000" and an ending number of "7000100."</span></span>

- <span data-ttu-id="a05d1-124">**대상 서버의 FQDN** 통화 파크 응용 프로그램을 호스팅하는 응용 프로그램 서비스의 FQDN(FQDN) 또는 서비스 ID를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a05d1-124">**FQDN of destination server** Select the fully qualified domain name (FQDN) or service ID of the Application service that hosts the Call Park application.</span></span> <span data-ttu-id="a05d1-125">번호 범위의 시작 번호와 끝 번호로 지정된 범위 내의 번호로 예약된 모든 통화는 이 서버 또는 풀로 라우팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="a05d1-125">All calls parked to numbers within the range specified by the start number and end number in the number range will be routed to this server or pool.</span></span>

<span data-ttu-id="a05d1-126">통화 파크 기능에 대한 자세한 내용은 [Plan for Call Park in Skype for Business 2015을 참조하세요.](../../plan-your-deployment/enterprise-voice-solution/call-park.md)</span><span class="sxs-lookup"><span data-stu-id="a05d1-126">For details about Call Park features and capabilities, see [Plan for Call Park in Skype for Business 2015](../../plan-your-deployment/enterprise-voice-solution/call-park.md).</span></span> <span data-ttu-id="a05d1-127">통화 파킹 번호 범위를 사용할 수 있는 자세한 내용은 [Configure Phone Number Extensions for Parking Calls을 참조합니다.](/previous-versions/office/lync-server-2013/lync-server-2013-configure-phone-number-extensions-for-parking-calls)</span><span class="sxs-lookup"><span data-stu-id="a05d1-127">For details about working with Call Park number ranges, see [Configure Phone Number Extensions for Parking Calls](/previous-versions/office/lync-server-2013/lync-server-2013-configure-phone-number-extensions-for-parking-calls).</span></span>