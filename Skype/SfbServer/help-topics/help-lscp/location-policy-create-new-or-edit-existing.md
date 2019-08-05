---
title: 위치 정책 새로 만들기 또는 기존 편집
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/24/2015
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.NcsLocEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d9b30b3b-570b-49a6-b2b4-46b0cf490153
description: 위치 정책을 구성하여 E9-1-1(고급 9-1-1)이 사용하도록 설정되는지 여부 및 사용되는 방법과, 사용자 및 연락처에 대해 위치 정보가 사용되는 방법을 결정할 수 있습니다.
ms.openlocfilehash: b0b1e16f7227100394dd132e52a17a3192ccab43
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36196381"
---
# <a name="location-policy-create-new-or-edit-existing"></a><span data-ttu-id="e3811-103">위치 정책: 새로 만들기 또는 기존 항목 편집</span><span class="sxs-lookup"><span data-stu-id="e3811-103">Location Policy: Create New or Edit Existing</span></span>

<span data-ttu-id="e3811-104">위치 정책을 구성하여 E9-1-1(고급 9-1-1)이 사용하도록 설정되는지 여부 및 사용되는 방법과, 사용자 및 연락처에 대해 위치 정보가 사용되는 방법을 결정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3811-104">You can configure Location policies to determine whether Enhanced 9-1-1 (E9-1-1) is enabled and how it is used, as well as how location information is used for users and contacts.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="e3811-105">UI 참조</span><span class="sxs-lookup"><span data-stu-id="e3811-105">UI Reference</span></span>

<span data-ttu-id="e3811-106">다음 목록에서는 페이지의 필드에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="e3811-106">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="e3811-107">**범위** 만들거나 수정 하는 위치 정책의 범위 (전역, 사이트 또는 사용자)를 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3811-107">**Scope** Identifies the scope of the location policy that you are creating or modifying: global, site, or user.</span></span>

- <span data-ttu-id="e3811-108">**이름** 각 위치 정책에는 이름이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3811-108">**Name** Each location policy requires a name.</span></span> <span data-ttu-id="e3811-109">전역 및 사이트 위치 정책은 기본적으로 명명 되며, 이름을 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e3811-109">Global and site location policies are named by default, and the name cannot be changed.</span></span> <span data-ttu-id="e3811-110">사용자 위치 정책의 경우 사용자 또는 사용자 그룹을 식별 하는 설명적인 이름을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3811-110">For user location policies, use a descriptive name that identifies the user or group of users.</span></span>

    > [!NOTE]
    > <span data-ttu-id="e3811-111">위치 정책을 저장한 후에는 이름을 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e3811-111">After you save the location policy, the name cannot be changed.</span></span>

- <span data-ttu-id="e3811-112">**향상 된 9-1-1 사용 (E9-1-1)** 이 위치 정책을 할당 하는 사용자에 대해 E9-1을 사용 하도록 설정 하려면이 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3811-112">**Enable Enhanced 9-1-1 (E9-1-1)** Select this check box to enable E9-1-1 for users who are assigned this location policy.</span></span>

- <span data-ttu-id="e3811-113">**위치** 사용자에 게 위치 정보를 묻는 메시지를 표시할지 여부를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3811-113">**Location** Specify whether users are prompted for location information:</span></span>

  - <span data-ttu-id="e3811-114">**필요 함** 클라이언트가 새 위치에 등록할 때 위치 정보를 입력 하 라는 메시지가 표시 되는 경우이 옵션을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3811-114">**Required** Select this option if users are to be prompted for location information when their client registers at a new location.</span></span> <span data-ttu-id="e3811-115">사용자는 위치 정보를 입력 하지 않고 메시지를 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3811-115">Users can dismiss the prompt without entering location information.</span></span>

  - <span data-ttu-id="e3811-116">**필요 하지 않음** 사용자에 게 위치 정보를 묻는 메시지를 표시 하지 않으려면이 옵션을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3811-116">**Not required** Select this option if users are not to be prompted for location information.</span></span>

  - <span data-ttu-id="e3811-117">고 **지** 사항 사용자에 게 위치 정보를 묻는 메시지가 표시 되지만 정보를 입력 하지 않고 메시지를 거절 하는 경우에는 고 지 사항 메시지가 표시 되는 경우이 옵션을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3811-117">**Disclaimer** Select this option if users are to be prompted for location information, but will see a disclaimer message if they decline the prompt without entering the information.</span></span> <span data-ttu-id="e3811-118">사용자는 비상 전화를 완료할 수 있지만, 다른 통화는 위치 정보를 입력할 때까지 불가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3811-118">Users can complete an emergency call but no other calls until they enter the location information.</span></span>

- <span data-ttu-id="e3811-119">**E9에 위치 사용-1-1에만** 해당 비상 전화에만 위치 정보가 사용 되는 경우이 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3811-119">**Use location for E9-1-1 only** Select this check box if location information is to be used only for emergency calls.</span></span>

- <span data-ttu-id="e3811-120">**PSTN 사용** 이 프로필을 사용 하는 클라이언트에서 비상 전화를 라우팅하는 데 사용할 음성 경로를 결정 하는 데 사용 되는 PSTN (공용 전환 전화 네트워크) 사용량을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3811-120">**PSTN usage** Select the public switched telephone network (PSTN) usage that will be used to determine which voice route will be used for routing emergency calls from clients that use this profile.</span></span> <span data-ttu-id="e3811-121">이 사용과 관련 된 경로는 비상 전화 전용 SIP 트렁크 또는 가까운 공공 안전 응답 시점 (PSAP)으로 긴급 통화를 라우팅하는 비상 위치 Id 번호 (ELIN) 게이트웨이를 가리켜야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3811-121">The route associated with this usage should point to a SIP trunk dedicated to emergency calls or to an Emergency Location Identification Number (ELIN) gateway that routes emergency calls to the nearest Public Safety Answering Point (PSAP).</span></span> <span data-ttu-id="e3811-122">옵션은 **내부**, **지역**또는 **장거리**입니다.</span><span class="sxs-lookup"><span data-stu-id="e3811-122">Options are **Internal**, **Local**, or **Long distance**.</span></span>

- <span data-ttu-id="e3811-123">**E9-1-1 번 전화 번호** 비상 서비스에 접속 하는 번호를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3811-123">**E9-1-1 dial number** Specify the number that is dialed to reach emergency services.</span></span>

- <span data-ttu-id="e3811-124">**E9-1-1 다이얼 마스크** 사용자가 전화를 거는 번호를 지정 하 고 긴급 전화 번호로 번역 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3811-124">**E9-1-1 dial mask** Specify a number that a user dials, which is then translated into the emergency dial number.</span></span> <span data-ttu-id="e3811-125">예를 들어이 필드에 212 값을 입력 하 여 사용자가 212에서 비상 서비스에 연결할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3811-125">For example, enter a value of 212 in this field so that a user can dial 212 to reach emergency services.</span></span> <span data-ttu-id="e3811-126">이렇게 하면 대체 긴급 번호로 전화를 걸 수 있으며, 다른 비상 번호로 전화를 걸 수 있는 국가 또는 지역 사용자가 해당 국가나 지역 번호를 사용 하는 경우, 예를 들어 현재 거주 하 고 있는 국가 또는 지역입니다.</span><span class="sxs-lookup"><span data-stu-id="e3811-126">This allows for alternate emergency numbers to be dialed and still have the call reach emergency services (for example, if someone from a country or region with a different emergency number attempts to dial that country or region's number rather than the number for the country or region they are currently in).</span></span> <span data-ttu-id="e3811-127">세미콜론으로 값을 구분 하 여 여러 응급 전화 접속 마스크를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3811-127">You can define multiple emergency dial masks by separating the values with semicolons.</span></span> <span data-ttu-id="e3811-128">예를 들어 212; 414.</span><span class="sxs-lookup"><span data-stu-id="e3811-128">For example, 212;414.</span></span> <span data-ttu-id="e3811-129">문자열의 최대 길이는 100 자입니다.</span><span class="sxs-lookup"><span data-stu-id="e3811-129">The maximum length of the string is 100 characters.</span></span> <span data-ttu-id="e3811-130">각 문자는 0 ~ 9의 숫자 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3811-130">Each character must be a digit 0 through 9.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="e3811-131">전화 마스크는 통화 대기 번호 범위에 포함된 번호와 달라야 하는데, 이는 통화 대기 라우팅이 긴급 전화 문자열 변환보다 우선적으로 적용되기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="e3811-131">Make sure that the dial mask is not the same as a number in a call park number range, because call park routing takes precedence over emergency dial string conversion.</span></span> <span data-ttu-id="e3811-132">통화 공원 번호 범위를 보려면 왼쪽 탐색 모음에서 **음성 기능** 을 클릭 한 다음 **통화 공원**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3811-132">To see the Call Park number ranges, click **Voice Features** in the left navigation bar, and then click **Call Park**.</span></span>

- <span data-ttu-id="e3811-133">**알림 URI** 비상 통화가 이루어질 때 알림을 받을 SIP Uri를 하나 이상 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3811-133">**Notification URI** Specify one or more SIP URIs to be notified when an emergency call is made.</span></span> <span data-ttu-id="e3811-134">예를 들어, 긴급 통화가 발생할 때마다 보안 직원에 게 인스턴트 메시지를 알리려면 회사 보안 office의 SIP URI를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3811-134">For example, type the company security office's SIP URI to notify security staff with an instant message whenever an emergency call is made.</span></span> <span data-ttu-id="e3811-135">호출자의 위치를 사용할 수 있는 경우 해당 위치는 알림에 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e3811-135">If the caller's location is available, the location is included in the notification.</span></span> <span data-ttu-id="e3811-136">여러 SIP Uri를 쉼표로 구분 된 목록으로 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3811-136">You can specify multiple SIP URIs as a comma-separated list.</span></span> <span data-ttu-id="e3811-137">예를 들어 "sip: security@litwareinc.com", "sip: kmyer@litwareinc.com".</span><span class="sxs-lookup"><span data-stu-id="e3811-137">For example, "sip:security@litwareinc.com","sip:kmyer@litwareinc.com".</span></span> <span data-ttu-id="e3811-138">문자열의 길이는 1 ~ 256 자 여야 하며 "sip:" 접두사로 시작 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3811-138">The string must be from 1 to 256 characters in length and must begin with the prefix "sip:".</span></span> <span data-ttu-id="e3811-139">메일 그룹을 지정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3811-139">You can also specify distribution lists.</span></span>

- <span data-ttu-id="e3811-140">**컨퍼런스 URI** 제 3 자에 대 한 SIP URI (이 경우 전화 번호)를 비상 전화에 conferenced 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3811-140">**Conference URI** Specify the SIP URI (telephone number, in this case) for a third party to be conferenced in to emergency calls.</span></span> <span data-ttu-id="e3811-141">예를 들어, 긴급 통화가 이루어질 때 회사 보안 office의 전화 번호를 입력 하 여 전화를 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3811-141">For example, type the company security office's phone number so that they receive a call when an emergency call is made.</span></span> <span data-ttu-id="e3811-142">**컨퍼런스 모드** 에 대 한 설정에 따라 제 3 자가 참여 하거나 통화를 수신할 수 있는지 여부가 결정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e3811-142">The setting for **Conference mode** determines whether the third party can participate or just listen in to the call.</span></span> <span data-ttu-id="e3811-143">문자열의 길이는 1 ~ 256 자 여야 하며 sip: 라는 접두사로 시작 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3811-143">The string must be from 1 to 256 characters in length and must begin with the prefix sip:.</span></span>

- <span data-ttu-id="e3811-144">**컨퍼런스 모드** **컨퍼런스 URI**에 대 한 값을 지정한 경우이 필드를 다음 값 중 하나로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3811-144">**Conference mode** If you specified a value for **Conference URI**, set this field to one of the following values:</span></span>

  - <span data-ttu-id="e3811-145">**단방향** 제 3 자가 호출자와 PSAP 연산자 간의 호출만 수신 대기할 수 없도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3811-145">**One-way** Specifies that the third party can only listen in to the call between the caller and the PSAP operator.</span></span>

  - <span data-ttu-id="e3811-146">**양방향** 제 3 자가 호출자와 PSAP 연산자 간의 호출에 참가할 수 있도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3811-146">**Two-way** Specifies that the third party can participate in the call between the caller and the PSAP operator.</span></span>

<span data-ttu-id="e3811-147">Enterprise Voice 응급 서비스 기능 및 기능에 대 한 자세한 내용은 계획 설명서의 [E9-1-1 개요](https://technet.microsoft.com/library/c01e6774-bc9f-4c5b-a60b-478b7317b2b7.aspx) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e3811-147">For details about Enterprise Voice emergency service features and capabilities, see [Overview of E9-1-1](https://technet.microsoft.com/library/c01e6774-bc9f-4c5b-a60b-478b7317b2b7.aspx) in the Planning documentation.</span></span> <span data-ttu-id="e3811-148">위치 정책을 사용하는 방법에 대한 자세한 내용은 작업 설명서의 [Configuring Location Policy](https://technet.microsoft.com/library/14e41bcb-ea0a-49c2-99b3-1f61fc34416d.aspx)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e3811-148">For details about working with location policies, see [Configuring Location Policy](https://technet.microsoft.com/library/14e41bcb-ea0a-49c2-99b3-1f61fc34416d.aspx) in the Operations documentation.</span></span>


