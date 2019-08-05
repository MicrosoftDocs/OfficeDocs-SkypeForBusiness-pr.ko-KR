---
title: 통화 공원 새로 만들기 또는 기존 편집
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.VoiceFeaCallParkEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e834d485-d25a-4eec-9090-2b8534ecf65d
ROBOTS: NOINDEX, NOFOLLOW
description: 통화 공원 번호 범위는 사용자가 검색 하거나 시간 초과 될 때까지 파킹 된 통화가 대기 하는 임시 번호를 정의 합니다.
ms.openlocfilehash: 7257327081be46f343ef8aeb6076ad9a788f46bb
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36191691"
---
# <a name="call-park-create-new-or-edit-existing"></a><span data-ttu-id="e8c30-103">통화 대기: 새로 만들기 또는 기존 항목 편집</span><span class="sxs-lookup"><span data-stu-id="e8c30-103">Call Park: Create New or Edit Existing</span></span>

<span data-ttu-id="e8c30-104">통화 공원 번호 범위는 사용자가 검색 하거나 시간 초과 될 때까지 파킹 된 통화가 대기 하는 임시 번호를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8c30-104">Call Park number ranges define the temporary numbers where parked calls are held until someone retrieves them or they time out.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="e8c30-105">UI 참조</span><span class="sxs-lookup"><span data-stu-id="e8c30-105">UI Reference</span></span>

<span data-ttu-id="e8c30-106">다음 목록에서는 페이지의 필드에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="e8c30-106">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="e8c30-107">**이름** 숫자 범위를 식별 하는 설명적인 이름을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8c30-107">**Name** Type a descriptive name that identifies the number range.</span></span> <span data-ttu-id="e8c30-108">번호 범위를 저장 한 후에는이 이름을 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e8c30-108">After you save the number range, this name cannot be changed.</span></span>

- <span data-ttu-id="e8c30-109">**숫자 범위** 첫 번째 필드에 숫자 범위의 시작 번호를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8c30-109">**Number range** In the first field, type the beginning number of the number range.</span></span> <span data-ttu-id="e8c30-110">두 번째 필드에 숫자 범위의 끝 번호를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8c30-110">In the second field, type the ending number of the number range.</span></span>

  - <span data-ttu-id="e8c30-111">범위의 시작 번호는 범위의 마지막 번호보다 작거나 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8c30-111">The beginning number of the range must be less than or equal to the ending number of the range.</span></span>

  - <span data-ttu-id="e8c30-112">범위의 시작 번호 값 길이는 범위의 마지막 번호 길이와 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8c30-112">The value of the beginning number of the range must be the same length as the ending number of the range.</span></span>

  - <span data-ttu-id="e8c30-p103">번호 범위는 고유해야 합니다. 범위가 다른 범위와 겹쳐서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e8c30-p103">The number range must be unique. This range cannot overlap with any other range.</span></span>

  - <span data-ttu-id="e8c30-115">숫자 범위가 문자로 \* 시작 하는 경우 범위는 100 보다 커야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8c30-115">If the number range begins with the character \* or #, the range must be greater than 100.</span></span>

  - <span data-ttu-id="e8c30-116">유효한 값: 정규식 문자열과 일치 해야 합니다 ([\\* | #]? [ 1-9] \d{0,7}) | ([1-9] \d{0,8}).</span><span class="sxs-lookup"><span data-stu-id="e8c30-116">Valid values: Must match the regular expression string ([\\*|#]?[1-9]\d{0,7})|([1-9]\d{0,8}).</span></span> <span data-ttu-id="e8c30-117">즉, value는 문자 \* 또는 숫자 1부터 9까지 (첫 문자는 0이 될 수 없음)로 시작 하는 문자열 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8c30-117">This means the value must be a string beginning with either the character \* or # or a number 1 through 9 (the first character cannot be a zero).</span></span> <span data-ttu-id="e8c30-118">첫 번째 문자가 \* or # 이면 다음 문자는 1부터 9 까지의 숫자 (0이 될 수 없음) 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8c30-118">If the first character is \* or #, the following character must be a number 1 through 9 (it cannot be a zero).</span></span> <span data-ttu-id="e8c30-119">이후 문자는 0 ~ 9 개 까지의 추가 문자 (예: "#6000", "\*92000", "\*95551212", "915551212") 일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e8c30-119">Subsequent characters can be any number 0 through 9 up to seven additional characters (for example, "#6000", "\*92000", "\*95551212", and "915551212").</span></span> <span data-ttu-id="e8c30-120">첫 문자 \* 를 입력 하는 경우 첫 번째 문자는 1 ~ 9 (0이 될 수 없음) 다음에 최대 8 자 (예: 915551212; 41212; 300) 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8c30-120">If the first character is not \* or #, the first character must be a number 1 through 9 (it cannot be zero), followed by up to eight characters, each a number 0 through 9 (for example: 915551212;41212;300).</span></span>

  - <span data-ttu-id="e8c30-p105">풀당 번호는 5만 개까지 포함할 수 있습니다. 각 번호 범위에는 일반적으로 100개 이하의 번호가 포함되지만, 그보다 훨씬 커질 수도 있습니다(1만 개 이하의 번호 포함). 예를 들어 시작 번호를 "7000000"으로, 끝 번호를 "8000000"으로 지정하는 대신 시작 번호를 "7000000"으로, 끝 번호를 "7000100"으로 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e8c30-p105">You should not have more than a total of 50,000 numbers per pool. Each number range typically encompasses 100 or fewer numbers, but it can be much larger as long as it includes fewer than 10,000 numbers. For example, instead of specifying a starting number of "7000000" and an ending number of "8000000," consider specifying a starting number of "7000000" and an ending number of "7000100."</span></span>

- <span data-ttu-id="e8c30-124">**대상 서버의 FQDN** 통화 공원 응용 프로그램을 호스트 하는 응용 프로그램 서비스의 FQDN (정규화 된 도메인 이름) 또는 서비스 ID를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8c30-124">**FQDN of destination server** Select the fully qualified domain name (FQDN) or service ID of the Application service that hosts the Call Park application.</span></span> <span data-ttu-id="e8c30-125">숫자 범위의 시작 번호와 끝 번호로 지정 된 범위 내에 있는 모든 통화는이 서버 또는 풀로 라우팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="e8c30-125">All calls parked to numbers within the range specified by the start number and end number in the number range will be routed to this server or pool.</span></span>

<span data-ttu-id="e8c30-126">통화 공원 기능 및 기능에 대 한 자세한 내용은 [비즈니스용 Skype의 통화 공원 계획](../../../plan-your-deployment/enterprise-voice-solution/call-park.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e8c30-126">For details about Call Park features and capabilities, see [Plan for Call Park in Skype for Business](../../../plan-your-deployment/enterprise-voice-solution/call-park.md).</span></span> <span data-ttu-id="e8c30-127">통화 공원 번호 범위 작업에 대 한 자세한 내용은 [파킹 통화에 대 한 전화 번호 확장 구성을](https://technet.microsoft.com/library/fbf97624-9587-42a6-b276-1b69c574a74d.aspx)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e8c30-127">For details about working with Call Park number ranges, see [Configure Phone Number Extensions for Parking Calls](https://technet.microsoft.com/library/fbf97624-9587-42a6-b276-1b69c574a74d.aspx).</span></span>


