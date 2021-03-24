---
title: 위치 정책 새로 만들기 또는 기존 데이터 편집
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.NcsLocEdit
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: d9b30b3b-570b-49a6-b2b4-46b0cf490153
ROBOTS: NOINDEX, NOFOLLOW
description: 위치 정책을 구성하여 E9-1-1(Enhanced 9-1-1)을 사용할 수 있는지 여부와 사용 방법과 사용자 및 연락처에 위치 정보가 사용되는 방법을 결정할 수 있습니다.
ms.openlocfilehash: 63e2f323bf2a1fb70cfb28ff7b308676cf432629
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51100314"
---
# <a name="location-policy-create-new-or-edit-existing"></a><span data-ttu-id="3f4b8-103">위치 정책: 새로 만들기 또는 기존 항목 편집</span><span class="sxs-lookup"><span data-stu-id="3f4b8-103">Location Policy: Create New or Edit Existing</span></span>

<span data-ttu-id="3f4b8-104">위치 정책을 구성하여 E9-1-1(Enhanced 9-1-1)을 사용할 수 있는지 여부와 사용 방법과 사용자 및 연락처에 위치 정보가 사용되는 방법을 결정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3f4b8-104">You can configure Location policies to determine whether Enhanced 9-1-1 (E9-1-1) is enabled and how it is used, as well as how location information is used for users and contacts.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="3f4b8-105">UI 참조</span><span class="sxs-lookup"><span data-stu-id="3f4b8-105">UI Reference</span></span>

<span data-ttu-id="3f4b8-106">다음 목록에서는 페이지의 필드에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="3f4b8-106">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="3f4b8-107">**범위** 만들거나 수정할 위치 정책의 범위(전역, 사이트 또는 사용자)를 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="3f4b8-107">**Scope** Identifies the scope of the location policy that you are creating or modifying: global, site, or user.</span></span>

- <span data-ttu-id="3f4b8-108">**이름** 각 위치 정책에는 이름이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="3f4b8-108">**Name** Each location policy requires a name.</span></span> <span data-ttu-id="3f4b8-109">전역 및 사이트 위치 정책의 이름은 기본적으로 지정되고 이름은 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3f4b8-109">Global and site location policies are named by default, and the name cannot be changed.</span></span> <span data-ttu-id="3f4b8-110">사용자 위치 정책의 경우 사용자 또는 사용자 그룹을 식별하는 설명적인 이름을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="3f4b8-110">For user location policies, use a descriptive name that identifies the user or group of users.</span></span>

    > [!NOTE]
    > <span data-ttu-id="3f4b8-111">위치 정책을 저장한 후에는 이름을 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3f4b8-111">After you save the location policy, the name cannot be changed.</span></span>

- <span data-ttu-id="3f4b8-112">**E9-1-1(고급 9-1-1) 사용** 이 위치 정책이 할당된 사용자에 대해 E9-1-1을 사용하도록 설정하려면 이 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3f4b8-112">**Enable Enhanced 9-1-1 (E9-1-1)** Select this check box to enable E9-1-1 for users who are assigned this location policy.</span></span>

- <span data-ttu-id="3f4b8-113">**위치** 사용자에게 위치 정보를 입력하라는 메시지를 표시하는지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="3f4b8-113">**Location** Specify whether users are prompted for location information:</span></span>

  - <span data-ttu-id="3f4b8-114">**필수** 클라이언트가 새 위치에 등록될 때 사용자에게 위치 정보를 입력하라는 메시지가 표시될 경우 이 옵션을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3f4b8-114">**Required** Select this option if users are to be prompted for location information when their client registers at a new location.</span></span> <span data-ttu-id="3f4b8-115">사용자는 위치 정보를 입력하지 않고 프롬프트를 해지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3f4b8-115">Users can dismiss the prompt without entering location information.</span></span>

  - <span data-ttu-id="3f4b8-116">**필요하지 않습니다.** 사용자에게 위치 정보를 입력하라는 메시지가 표시되지 않는 경우 이 옵션을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3f4b8-116">**Not required** Select this option if users are not to be prompted for location information.</span></span>

  - <span data-ttu-id="3f4b8-117">**고지 조항** 사용자에게 위치 정보를 입력하라는 메시지가 표시되지만 정보를 입력하지 않고 메시지를 거부하는 경우 고지 메시지가 표시될 경우 이 옵션을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3f4b8-117">**Disclaimer** Select this option if users are to be prompted for location information, but will see a disclaimer message if they decline the prompt without entering the information.</span></span> <span data-ttu-id="3f4b8-118">사용자는 위치 정보를 입력할 때까지 긴급 통화를 완료할 수 있지만 다른 통화는 완료할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3f4b8-118">Users can complete an emergency call but no other calls until they enter the location information.</span></span>

- <span data-ttu-id="3f4b8-119">**E9-1-1에만 위치 사용** 위치 정보를 긴급 통화에만 사용하려면 이 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3f4b8-119">**Use location for E9-1-1 only** Select this check box if location information is to be used only for emergency calls.</span></span>

- <span data-ttu-id="3f4b8-120">**PSTN 사용** 이 프로필을 사용하는 클라이언트의 긴급 통화를 라우팅하는 데 사용할 음성 경로를 결정하는 데 사용할 PSTN(공용 전화망) 사용을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3f4b8-120">**PSTN usage** Select the public switched telephone network (PSTN) usage that will be used to determine which voice route will be used for routing emergency calls from clients that use this profile.</span></span> <span data-ttu-id="3f4b8-121">이 사용법과 연결된 경로는 긴급 통화 전용 SIP 트렁크 또는 긴급 통화를 가장 가까운 PSAP(Public Safety Answering Point)로 라우팅하는 ELIN(Emergency Location Identification Number) 게이트웨이를 연결해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f4b8-121">The route associated with this usage should point to a SIP trunk dedicated to emergency calls or to an Emergency Location Identification Number (ELIN) gateway that routes emergency calls to the nearest Public Safety Answering Point (PSAP).</span></span> <span data-ttu-id="3f4b8-122">옵션은 **내부,** **로컬 또는** **장거리입니다.**</span><span class="sxs-lookup"><span data-stu-id="3f4b8-122">Options are **Internal**, **Local**, or **Long distance**.</span></span>

- <span data-ttu-id="3f4b8-123">**E9-1-1 전화 번호** 응급 서비스에 연결하기 위해 전화를 걸 번호를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="3f4b8-123">**E9-1-1 dial number** Specify the number that is dialed to reach emergency services.</span></span>

- <span data-ttu-id="3f4b8-124">**E9-1-1 다이얼 마스크** 사용자가 전화를 걸 번호를 지정하면 해당 번호가 긴급 전화 번호로 변환됩니다.</span><span class="sxs-lookup"><span data-stu-id="3f4b8-124">**E9-1-1 dial mask** Specify a number that a user dials, which is then translated into the emergency dial number.</span></span> <span data-ttu-id="3f4b8-125">예를 들어 사용자가 응급 서비스에 연결하기 위해 212로 전화를 걸 수 있도록 이 필드에 값 212를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="3f4b8-125">For example, enter a value of 212 in this field so that a user can dial 212 to reach emergency services.</span></span> <span data-ttu-id="3f4b8-126">이렇게 하면 대체 긴급 번호로 전화를 걸 수 있으며 통화가 긴급 서비스에 연결됩니다(예: 다른 긴급 번호가 있는 국가나 지역의 누군가가 현재 있는 국가 또는 지역의 번호가 아닌 해당 국가 또는 지역 번호로 전화를 걸려 시도하는 경우).</span><span class="sxs-lookup"><span data-stu-id="3f4b8-126">This allows for alternate emergency numbers to be dialed and still have the call reach emergency services (for example, if someone from a country or region with a different emergency number attempts to dial that country or region's number rather than the number for the country or region they are currently in).</span></span> <span data-ttu-id="3f4b8-127">예를 들어 응급 번호가 다른 국가의 사용자가 외국에서 그 나라의 번호 대신 자신의 국가에서 사용되는 번호로 전화를 거는 경우에 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="3f4b8-127">You can define multiple emergency dial masks by separating the values with semicolons.</span></span> <span data-ttu-id="3f4b8-128">예: 212;414.</span><span class="sxs-lookup"><span data-stu-id="3f4b8-128">For example, 212;414.</span></span> <span data-ttu-id="3f4b8-129">문자열의 최대 길이는 100자입니다.</span><span class="sxs-lookup"><span data-stu-id="3f4b8-129">The maximum length of the string is 100 characters.</span></span> <span data-ttu-id="3f4b8-130">각 문자는 0부터 9까지의 숫자여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f4b8-130">Each character must be a digit 0 through 9.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="3f4b8-131">전화 마스크는 통화 대기 번호 범위에 포함된 번호와 달라야 하는데, 이는 통화 대기 라우팅이 긴급 전화 문자열 변환보다 우선적으로 적용되기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="3f4b8-131">Make sure that the dial mask is not the same as a number in a call park number range, because call park routing takes precedence over emergency dial string conversion.</span></span> <span data-ttu-id="3f4b8-132">통화 파크 번호 범위를 보려면 왼쪽 탐색 모음에서 **음성** 기능을 클릭한 다음 통화 **파크 를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="3f4b8-132">To see the Call Park number ranges, click **Voice Features** in the left navigation bar, and then click **Call Park**.</span></span>

- <span data-ttu-id="3f4b8-133">**알림 URI** 긴급 통화가 걸려 오면 알림을 하게 될 하나 이상의 SIP URIS를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="3f4b8-133">**Notification URI** Specify one or more SIP URIs to be notified when an emergency call is made.</span></span> <span data-ttu-id="3f4b8-134">예를 들어 회사 보안 사무소의 SIP URI를 입력하여 긴급 통화가 걸릴 때마다 보안 직원에게 인스턴트 메시지를 알릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3f4b8-134">For example, type the company security office's SIP URI to notify security staff with an instant message whenever an emergency call is made.</span></span> <span data-ttu-id="3f4b8-135">발신자 위치를 사용할 수 있는 경우 해당 위치가 알림에 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="3f4b8-135">If the caller's location is available, the location is included in the notification.</span></span> <span data-ttu-id="3f4b8-136">여러 SIP URIS를 콤보로 구분된 목록으로 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3f4b8-136">You can specify multiple SIP URIs as a comma-separated list.</span></span> <span data-ttu-id="3f4b8-137">예를 들어 "sip:security@litwareinc.com","sip:kmyer@litwareinc.com"를 예로 들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3f4b8-137">For example, "sip:security@litwareinc.com","sip:kmyer@litwareinc.com".</span></span> <span data-ttu-id="3f4b8-138">이 문자열은 1자에서 256자까지의 길이로 시작해야 하며 "sip:" prefix로 시작해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f4b8-138">The string must be from 1 to 256 characters in length and must begin with the prefix "sip:".</span></span> <span data-ttu-id="3f4b8-139">메일 목록을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3f4b8-139">You can also specify distribution lists.</span></span>

- <span data-ttu-id="3f4b8-140">**회의 URI** 긴급 통화에 전화 회의할 제3자에 대한 SIP URI(전화 번호, 이 경우)를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="3f4b8-140">**Conference URI** Specify the SIP URI (telephone number, in this case) for a third party to be conferenced in to emergency calls.</span></span> <span data-ttu-id="3f4b8-141">예를 들어 긴급 통화가 걸려 오면 전화를 받을 수 있도록 회사 보안 사무소의 전화 번호를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="3f4b8-141">For example, type the company security office's phone number so that they receive a call when an emergency call is made.</span></span> <span data-ttu-id="3f4b8-142">전화 회의 모드 **설정에** 따라 제3자만 통화에 참가할 수 있는지 아니면 통화를 들을 수 있는지가 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="3f4b8-142">The setting for **Conference mode** determines whether the third party can participate or just listen in to the call.</span></span> <span data-ttu-id="3f4b8-143">이 문자열은 1자에서 256자 사이여야 하며 접두사 sip:로 시작해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f4b8-143">The string must be from 1 to 256 characters in length and must begin with the prefix sip:.</span></span>

- <span data-ttu-id="3f4b8-144">**회의 모드** 회의 **URI** 값을 지정한 경우 이 필드를 다음 값 중 하나로 설정하십시오.</span><span class="sxs-lookup"><span data-stu-id="3f4b8-144">**Conference mode** If you specified a value for **Conference URI**, set this field to one of the following values:</span></span>

  - <span data-ttu-id="3f4b8-145">**단방형** 제3자가 발신자 및 PSAP 운영자 간의 통화만 들을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3f4b8-145">**One-way** Specifies that the third party can only listen in to the call between the caller and the PSAP operator.</span></span>

  - <span data-ttu-id="3f4b8-146">**양면** 제3자가 발신자 및 PSAP 운영자 간의 통화에 참가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3f4b8-146">**Two-way** Specifies that the third party can participate in the call between the caller and the PSAP operator.</span></span>

<span data-ttu-id="3f4b8-147">응급 서비스 Enterprise Voice 기능에 대한 자세한 내용은 계획 설명서에서 [Overview of E9-1-1를](/previous-versions/office/lync-server-2013/lync-server-2013-overview-of-e9-1-1) 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="3f4b8-147">For details about Enterprise Voice emergency service features and capabilities, see [Overview of E9-1-1](/previous-versions/office/lync-server-2013/lync-server-2013-overview-of-e9-1-1) in the Planning documentation.</span></span> <span data-ttu-id="3f4b8-148">위치 정책을 사용하는 방법에 대한 자세한 내용은 작업 설명서에서 [Configuring Location Policy](/previous-versions/office/lync-server-2013/lync-server-2013-viewing-location-policy-information)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="3f4b8-148">For details about working with location policies, see [Configuring Location Policy](/previous-versions/office/lync-server-2013/lync-server-2013-viewing-location-policy-information) in the Operations documentation.</span></span>