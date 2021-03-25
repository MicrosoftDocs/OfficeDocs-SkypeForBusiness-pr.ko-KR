---
title: 회의 정책 새로 만들기 또는 기존 데이터 편집
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
- ms.lync.lscp.ConfMeetingPolicyEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ebd2f120-b57a-4c94-9509-20e098f4b0f4
description: 회의 정책은 사용자가 회의 중에 사용할 수 있는 기능(모임)을 정의합니다.
ms.openlocfilehash: 073019a46e2934f78ec0f20b8a7cb8e04c01bab9
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51121021"
---
# <a name="conferencing-policy-create-new-or-edit-existing"></a><span data-ttu-id="f8e68-103">회의 정책: 새로 만들기 또는 기존 항목 편집</span><span class="sxs-lookup"><span data-stu-id="f8e68-103">Conferencing Policy: Create New or Edit Existing</span></span>

<span data-ttu-id="f8e68-104">회의 정책은 사용자가 회의 중에 사용할 수 있는 기능(모임)을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="f8e68-104">A Conferencing policy defines the features and capabilities that users have available during a conference (also known as meeting).</span></span>

## <a name="ui-reference"></a><span data-ttu-id="f8e68-105">UI 참조</span><span class="sxs-lookup"><span data-stu-id="f8e68-105">UI Reference</span></span>

<span data-ttu-id="f8e68-106">다음 목록에서는 페이지의 필드에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f8e68-106">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="f8e68-107">**범위** 만들거나 수정할 회의 정책의 범위(전역, 사이트 또는 사용자)를 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="f8e68-107">**Scope** Identifies the scope of the conferencing policy that you are creating or modifying: global, site, or user.</span></span>

- <span data-ttu-id="f8e68-108">**이름** 각 회의 정책에는 이름이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="f8e68-108">**Name** Each conferencing policy requires a name.</span></span> <span data-ttu-id="f8e68-109">전역 및 사이트 회의 정책의 이름은 기본적으로 지정되고 이름은 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f8e68-109">Global and site conferencing policies are named by default, and the name cannot be changed.</span></span> <span data-ttu-id="f8e68-110">사용자 회의 정책의 경우 사용자 또는 사용자 그룹을 식별하는 설명적인 이름을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8e68-110">For user conferencing policies, use a descriptive name that identifies the user or group of users.</span></span>

    > [!NOTE]
    > <span data-ttu-id="f8e68-111">회의 정책을 저장한 후 이름을 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f8e68-111">After you save the conferencing policy, the name cannot be changed.</span></span>

- <span data-ttu-id="f8e68-112">**설명** 이 필드는 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="f8e68-112">**Description** This field is optional.</span></span> <span data-ttu-id="f8e68-113">회의 정책에 대한 추가 세부 정보를 제공하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f8e68-113">Use it to provide additional details about the conferencing policy.</span></span>

- <span data-ttu-id="f8e68-114">**이끌이 정책** 이 섹션의 설정은 회의를 주최하는 사용자에게 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="f8e68-114">**Organizer policy** The settings in this section apply to the user who organizes a conference.</span></span> <span data-ttu-id="f8e68-115">설정을 선택하면 사용자가 지정된 특성이 있는 회의를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f8e68-115">If a setting is selected, the user can organize a conference that has the specified characteristic.</span></span> <span data-ttu-id="f8e68-116">설정을 선택하지 않은 경우 사용자는 이 특성을 사용하여 회의를 구성할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f8e68-116">If a setting is not selected, the user can't organize a conference with this characteristic.</span></span> <span data-ttu-id="f8e68-117">이러한 설정은 사용자가 다른 회의의 참가자로 액세스할 수 있는 대상을 결정하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f8e68-117">These settings do not determine what the user has access to as a participant in other conferences.</span></span>

    <span data-ttu-id="f8e68-118">레이블 옆의 위쪽 화살표 또는 아래쪽 화살표를 클릭하여 섹션을 닫거나 니다.</span><span class="sxs-lookup"><span data-stu-id="f8e68-118">Click the up arrow or down arrow next to the label to close or open the section.</span></span>

- <span data-ttu-id="f8e68-119">**최대 모임 크기** 회의에서 허용되는 최대 사용자 수입니다.</span><span class="sxs-lookup"><span data-stu-id="f8e68-119">**Maximum meeting size** the maximum number of users that are allowed at a conference.</span></span> <span data-ttu-id="f8e68-120">기본적으로 최대 회의 크기는 250입니다.</span><span class="sxs-lookup"><span data-stu-id="f8e68-120">By default, the maximum conference size is 250.</span></span>

- <span data-ttu-id="f8e68-121">**참가자가 익명 사용자를 초대하도록 허용** 사용자가 회의에 익명 사용자를 초대할 수 있도록 허용하려면 이 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f8e68-121">**Allow participants to invite anonymous users** Select this check box to allow users to invite anonymous users to conferences.</span></span> <span data-ttu-id="f8e68-122">익명 사용자는 조직의 Active Directory 도메인 서비스에 자격 증명이 없는 사용자이며 따라서 인증되지 않은 사용자입니다.</span><span class="sxs-lookup"><span data-stu-id="f8e68-122">Anonymous users are users who do not have credentials in your organization's Active Directory Domain Services and who, therefore, are not authenticated.</span></span>

- <span data-ttu-id="f8e68-123">**기록** 참가자가 회의를 녹음할 수 있는지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="f8e68-123">**Recording** Specify whether or not participants can record conferences.</span></span> <span data-ttu-id="f8e68-124">옵션은 **없음** 또는 기록 **사용입니다.**</span><span class="sxs-lookup"><span data-stu-id="f8e68-124">The options are **None** or **Enable recording**.</span></span>

- <span data-ttu-id="f8e68-125">**페더더러 및 익명** 참가자가 녹음할 수 있도록 허용 외부 및 비인식 참가자가 회의를 녹음할 수 있도록 허용하려면 이 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f8e68-125">**Allow federated and anonymous participants to record** Select this check box to allow external and unauthenticated participants to record conferences.</span></span>

- <span data-ttu-id="f8e68-126">**오디오/비디오** 참가자가 오디오 및 비디오를 사용할 수 있는지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="f8e68-126">**Audio/video** Specify whether participants can use audio and video:</span></span>

  - <span data-ttu-id="f8e68-127">**없음** 오디오 및 비디오 사용을 방지하려면 이 옵션을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f8e68-127">**None** Select this option to prevent the use of audio and video.</span></span>

  - <span data-ttu-id="f8e68-128">**IP 오디오 사용** 오디오를 사용할 수 있지만 비디오는 사용할 수 있도록 허용하려면 이 옵션을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f8e68-128">**Enable IP audio** Select this option to allow the use of audio but not video.</span></span>

  - <span data-ttu-id="f8e68-129">**IP 오디오/비디오 사용** 오디오와 비디오를 모두 허용하려면 이 옵션을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f8e68-129">**Enable IP audio/video** Select this option to allow both audio and video.</span></span>

- <span data-ttu-id="f8e68-130">**PSTN 전화 접속** 회의 사용 오디오/비디오에서 오디오를 사용하도록 설정한 경우 사용자가 PSTN(Public Switched Telephone Network)을 사용하여 전화 회의에 전화를 걸 수 있도록 허용하려면 이 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f8e68-130">**Enable PSTN dial-in conferencing** If you enabled audio in **Audio/video**, select this check box to allow users to dial in to conferences by using the public switched telephone network (PSTN).</span></span>

- <span data-ttu-id="f8e68-131">**익명 참가자가 전화를** 걸 수 있도록 허용 사용자가 전화 회의에 전화를 걸 수 있도록 허용하고, 전화 접속 전화를 사용하여 사용자가 전화 회의에 참가할 수 있도록 허용하려면 이 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f8e68-131">**Allow anonymous participants to dial out** Select this check box if you allow users to dial in to conferences and you want to allow unauthenticated (anonymous) users to join a conference by using dial out phoning.</span></span> <span data-ttu-id="f8e68-132">전화 접속 전화를 사용하면 전화 회의 서버에서 사용자에게 전화를 걸고 사용자는 이 전화에 응답하여 회의에 참가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f8e68-132">With dial-out phoning, the conference server calls the user, and the user answers the phone to join the conference.</span></span>

- <span data-ttu-id="f8e68-133">**참가자가 전화를** 걸 수 Enterprise Voice 허용 오디오/비디오에서 오디오를 사용하도록 설정한 경우 전화 접속 전화를 사용하여 회의에 참가할 수 Enterprise Voice 수 있도록 허용하려면 이 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f8e68-133">**Allow participants not enabled for Enterprise Voice to dial out** If you enabled audio in **Audio/video**, select this check box to allow users who are not enabled for Enterprise Voice to join a conference by using dial-out phoning.</span></span> <span data-ttu-id="f8e68-134">전화 접속 전화를 통해 회의 서버가 사용자에게 전화를 걸면 사용자가 전화에 응답하여 전화 회의에 참가합니다.</span><span class="sxs-lookup"><span data-stu-id="f8e68-134">With dial-out phoning the conferencing server telephones the user, and then the user answers the phone to join the conference.</span></span>

- <span data-ttu-id="f8e68-135">**여러 비디오 스트림 허용** **오디오/비디오에서** 비디오를 사용하도록 설정한 경우 사용자가 갤러리 보기 비디오를 사용하여 회의를 구성할 수 있도록 허용하려면 이 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f8e68-135">**Allow multiple video streams** If you enabled video in **Audio/video**, select this check box to allow users to organize conferences with Gallery View video.</span></span> <span data-ttu-id="f8e68-136">이 확인란을 선택하면 사용자가 여러 비디오 스트림을 전송하는 회의를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f8e68-136">When this check box is selected, this setting allows users to organize conferences that send multiple video streams.</span></span> <span data-ttu-id="f8e68-137">이 확인란을 선택하지 않은 경우 사용자는 단일 비디오 스트림을 전송하는 회의만 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f8e68-137">When this check box is not selected, users can only organize conferences that send a single video stream.</span></span>

    > [!NOTE]
    > <span data-ttu-id="f8e68-138">이 옵션에 따라 회의에서 지원되는 비디오 스트림의 유형이 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="f8e68-138">This option determines the type of video stream supported by the conference.</span></span> <span data-ttu-id="f8e68-139">참가자가 여러 비디오 스트림을 받을 수 있는지 여부는 결정하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f8e68-139">It does not determine whether participants can receive multiple video streams.</span></span> <span data-ttu-id="f8e68-140">참가자가 여러 비디오 스트림을 사용하여 참가할 수 있도록 **설정** 옵션은 참가자가 여러 비디오 스트림을 받을 수 있는지 여부를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="f8e68-140">The **Enable participants to join with multiple video streams** option determines whether participants can receive multiple video streams.</span></span>

- <span data-ttu-id="f8e68-141">**데이터 공동 작업** 회의에서 데이터 공동 작업을 허용할지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="f8e68-141">**Data collaboration** Specify whether or not the conference allows data collaboration.</span></span> <span data-ttu-id="f8e68-142">옵션은 없음 또는 **데이터** 공동 **작업 사용입니다.**</span><span class="sxs-lookup"><span data-stu-id="f8e68-142">The options are **None** or **Enable data collaboration**.</span></span>

    <span data-ttu-id="f8e68-143">데이터 공동 작업에는 다음 설정이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="f8e68-143">The following settings apply to data collaboration:</span></span>

  - <span data-ttu-id="f8e68-144">**페더러드** 및 익명 참가자가 콘텐츠를 다운로드할 수 있도록 허용 데이터 공동 작업을 허용하는 경우 외부 및 확인되지 않은 사용자가 회의에서 슬라이드 또는 유인물과 같은 콘텐츠를 다운로드할 수 있도록 허용하려면 이 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f8e68-144">**Allow federated and anonymous participants to download content** If you allow data collaboration, select this check box to allow external and unauthenticated users to download content, such as slides or handouts, from a conference.</span></span>

  - <span data-ttu-id="f8e68-145">**참가자가 파일을 전송할 수 있도록 허용** 데이터 공동 작업을 허용하는 경우 회의 중에 모든 참가자에게 파일 전송을 허용하려면 이 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f8e68-145">**Allow participants to transfer files** If you allow data collaboration, select this check box to allow file transfers to all participants during a conference.</span></span>

  - <span data-ttu-id="f8e68-146">**주석 사용** 데이터 공동 작업을 허용하는 경우 참가자가 회의 중에 공유되는 콘텐츠에 대해 화면 주석을 만들 수 있도록 허용하려면 이 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f8e68-146">**Enable annotations** If you allow data collaboration, select this check box to allow participants to make on-screen annotations on content shared during the conference.</span></span>

  - <span data-ttu-id="f8e68-147">**PowerPoint 주석 사용** 주석을 허용하는 경우 참가자가 회의 중에 공유되는 PowerPoint 슬라이드에서 주석을 만들 수 있도록 허용하려면 이 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f8e68-147">**Enable PowerPoint annotations** If you allow annotation, select this check box to allow participants to make annotations in PowerPoint slides shared during the conference.</span></span>

  - <span data-ttu-id="f8e68-148">**설문 사용** 데이터 공동 작업을 허용하는 경우 참가자가 회의 중에 설문 조사를 진행할 수 있도록 허용하려면 이 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f8e68-148">**Enable polls** If you allow data collaboration, select this check box to allow participants to hold a poll during a conference.</span></span>

- <span data-ttu-id="f8e68-149">**응용 프로그램 공유** 회의에서 응용 프로그램 공유를 허용할지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="f8e68-149">**Application sharing** Specify whether or not the conference allows application sharing.</span></span> <span data-ttu-id="f8e68-150">응용 프로그램 공유 **사용 안 하도록 설정 또는** 응용 프로그램 공유 사용 **입니다.**</span><span class="sxs-lookup"><span data-stu-id="f8e68-150">The options are **Disable application sharing** or **Enable application sharing**.</span></span>

    <span data-ttu-id="f8e68-151">다음 설정은 응용 프로그램 공유에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="f8e68-151">The following settings apply to application sharing:</span></span>

  - <span data-ttu-id="f8e68-152">**참가자가 제어할 수 있도록 허용** 응용 프로그램 공유를 허용하는 경우 참가자가 회의 중에 공유되는 응용 프로그램 또는 데스크톱을 제어할 수 있도록 허용하려면 이 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f8e68-152">**Allow participants to take control** If you allow application sharing, select this check box to allow participants to take control of applications or desktops that are shared during the conference.</span></span>

  - <span data-ttu-id="f8e68-153">**페더러드** 및 익명 참가자가 제어하도록 허용 응용 프로그램 공유를 허용하는 경우 외부 및 비인식 참가자가 회의 중에 공유되는 응용 프로그램 또는 데스크톱을 제어할 수 있도록 허용하려면 이 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f8e68-153">**Allow federated and anonymous participants to take control** If you allow application sharing, select this check box to allow external and unauthenticated participants to take control of applications or desktops that are shared during the conference.</span></span>

- <span data-ttu-id="f8e68-154">**참가자 정책** 이 섹션의 설정은 회의 또는 두 사용자 간 세션의 참가자로 사용자에게 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="f8e68-154">**Participant policy** The settings in this section apply to users as participants in a conference or two-party session.</span></span> <span data-ttu-id="f8e68-155">다음 설정은 사용자당 설정이기 때문에 회의 또는 두 사용자 세션의 한 사용자가 같은 회의 또는 두 사용자 간 세션의 다른 사용자와 다른 기능을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f8e68-155">Because the following settings are per-user settings, one user in a conference or two-party session may have different capabilities than another user in the same conference or two-party session.</span></span>

    <span data-ttu-id="f8e68-156">레이블 옆의 위쪽 화살표 또는 아래쪽 화살표를 클릭하여 섹션을 닫거나 니다.</span><span class="sxs-lookup"><span data-stu-id="f8e68-156">Click the up arrow or down arrow next to the label to close or open the section.</span></span>

- <span data-ttu-id="f8e68-157">사용자가 **회의 또는** 두 사용자 간 세션에 참가하는 동안 응용 프로그램 또는 데스크톱을 공유할 수 있도록 허용하려면 응용 프로그램 및 데스크톱 공유 사용 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f8e68-157">Select **Enable application and desktop sharing** to allow users to share applications or their desktop while participating in a conference or two-party session.</span></span> <span data-ttu-id="f8e68-158">사용자가 **회의 또는** 두 사용자 간 세션에 참가하는 동안 응용 프로그램 또는 데스크톱을 공유하지 못하게 하려면 응용 프로그램 및 데스크톱 공유 사용 안 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f8e68-158">Select **Disable application and desktop sharing** to prevent users from sharing applications or their desktop while participating in a conference or two-party session.</span></span>

- <span data-ttu-id="f8e68-159">**피어 투 피어 파일 전송 사용** 회의 또는 두 사용자 간 세션 중에 개인 간 파일 전송(즉, 모든 참가자가 참여하지 않는 파일 전송)을 허용하려면 이 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f8e68-159">**Enable peer-to-peer file transfer** Select this check box to allow person-to-person file transfers (that is, file transfers that do not involve all participants) during a conference or two-party session.</span></span>

- <span data-ttu-id="f8e68-160">**피어 투 피어 녹음 사용** 사용자가 두 사용자 세션을 녹음할 수 있도록 허용하려면 이 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f8e68-160">**Enable peer-to-peer recording** Select this check box to allow users to record two-party sessions.</span></span>

- <span data-ttu-id="f8e68-161">**참가자가 여러 비디오 스트림에 참가할 수 있도록 설정** 참가자가 갤러리 보기 비디오를 허용하는 회의에서 비디오를 받을 수 있도록 허용하려면 이 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f8e68-161">**Enable participants to join with multiple video streams** Select this check box to allow participants to receive Gallery View video in conferences that allow it.</span></span> <span data-ttu-id="f8e68-162">이 옵션을 선택하지 않으면 참가자는 회의에서 허용하는 대상에 관계없이 단일 비디오 스트림만 수신할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f8e68-162">If this option is not selected, participants can only receive a single video stream regardless of what the conference allows.</span></span>

    > [!NOTE]
    > <span data-ttu-id="f8e68-163">Allow **multiple video streams(여러 비디오** 스트림 허용)는 회의에서 여러 비디오 스트림을 허용할지 여부를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="f8e68-163">The **Allow multiple video streams** determines whether a conference allows multiple video streams.</span></span>

<span data-ttu-id="f8e68-164">회의 기능에 대한 자세한 내용은 계획 설명서에서 [Overview of Conferencing를](/previous-versions/office/lync-server-2013/lync-server-2013-overview-of-conferencing) 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="f8e68-164">For details about conferencing features and capabilities, see [Overview of Conferencing](/previous-versions/office/lync-server-2013/lync-server-2013-overview-of-conferencing) in the Planning documentation.</span></span> <span data-ttu-id="f8e68-165">회의 정책 작업에 대한 자세한 내용은 작업 설명서에서 [Conferencing Policies을](/previous-versions/office/lync-server-2013/lync-server-2013-conferencing-policies) 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="f8e68-165">For details about working with conferencing policies, see [Conferencing Policies](/previous-versions/office/lync-server-2013/lync-server-2013-conferencing-policies) in the Operations documentation.</span></span>