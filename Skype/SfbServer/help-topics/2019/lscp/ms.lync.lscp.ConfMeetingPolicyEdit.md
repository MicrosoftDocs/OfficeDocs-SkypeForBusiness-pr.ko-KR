---
title: 회의 정책 새로 만들기 또는 기존 편집
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ConfMeetingPolicyEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ebd2f120-b57a-4c94-9509-20e098f4b0f4
ROBOTS: NOINDEX, NOFOLLOW
description: 회의 정책은 사용자가 회의(모임이라고도 함) 중에 사용할 수 있는 기능을 정의합니다.
ms.openlocfilehash: 137802662241c4348f65ddb33e96d59a6c42a286
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36197100"
---
# <a name="conferencing-policy-create-new-or-edit-existing"></a><span data-ttu-id="cd56d-103">회의 정책: 새로 만들기 또는 기존 항목 편집</span><span class="sxs-lookup"><span data-stu-id="cd56d-103">Conferencing Policy: Create New or Edit Existing</span></span>

<span data-ttu-id="cd56d-104">회의 정책은 사용자가 회의(모임이라고도 함) 중에 사용할 수 있는 기능을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="cd56d-104">A Conferencing policy defines the features and capabilities that users have available during a conference (also known as meeting).</span></span>

## <a name="ui-reference"></a><span data-ttu-id="cd56d-105">UI 참조</span><span class="sxs-lookup"><span data-stu-id="cd56d-105">UI Reference</span></span>

<span data-ttu-id="cd56d-106">다음 목록에서는 페이지의 필드에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="cd56d-106">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="cd56d-107">**범위** 만들거나 수정 하는 회의 정책의 범위 (전역, 사이트 또는 사용자)를 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd56d-107">**Scope** Identifies the scope of the conferencing policy that you are creating or modifying: global, site, or user.</span></span>

- <span data-ttu-id="cd56d-108">**이름** 각 회의 정책에는 이름이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd56d-108">**Name** Each conferencing policy requires a name.</span></span> <span data-ttu-id="cd56d-109">전역 및 사이트 회의 정책은 기본적으로 명명 되며, 이름을 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="cd56d-109">Global and site conferencing policies are named by default, and the name cannot be changed.</span></span> <span data-ttu-id="cd56d-110">사용자 회의 정책의 경우 사용자 또는 사용자 그룹을 식별 하는 설명적인 이름을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd56d-110">For user conferencing policies, use a descriptive name that identifies the user or group of users.</span></span>

    > [!NOTE]
    > <span data-ttu-id="cd56d-111">회의 정책을 저장한 후에는 이름을 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="cd56d-111">After you save the conferencing policy, the name cannot be changed.</span></span>

- <span data-ttu-id="cd56d-112">**설명** 이 필드는 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="cd56d-112">**Description** This field is optional.</span></span> <span data-ttu-id="cd56d-113">이 기능을 사용 하 여 회의 정책에 대 한 추가 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd56d-113">Use it to provide additional details about the conferencing policy.</span></span>

- <span data-ttu-id="cd56d-114">**이끌이 정책** 이 섹션의 설정은 회의를 구성 하는 사용자에 게 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cd56d-114">**Organizer policy** The settings in this section apply to the user who organizes a conference.</span></span> <span data-ttu-id="cd56d-115">설정을 선택 하면 사용자가 지정 된 특성을 가진 회의를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd56d-115">If a setting is selected, the user can organize a conference that has the specified characteristic.</span></span> <span data-ttu-id="cd56d-116">설정이 선택 되어 있지 않으면 사용자가이 특성을 사용 하 여 회의를 구성할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="cd56d-116">If a setting is not selected, the user can't organize a conference with this characteristic.</span></span> <span data-ttu-id="cd56d-117">이러한 설정은 사용자가 다른 회의에서 참여자로 액세스할 수 있는 내용을 결정 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cd56d-117">These settings do not determine what the user has access to as a participant in other conferences.</span></span>

    <span data-ttu-id="cd56d-118">레이블 옆의 위쪽 화살표 또는 아래쪽 화살표를 클릭하여 섹션을 닫거나 엽니다.</span><span class="sxs-lookup"><span data-stu-id="cd56d-118">Click the up arrow or down arrow next to the label to close or open the section.</span></span>

- <span data-ttu-id="cd56d-119">**최대 모임 크기** 회의에 허용 되는 최대 사용자 수입니다.</span><span class="sxs-lookup"><span data-stu-id="cd56d-119">**Maximum meeting size** the maximum number of users that are allowed at a conference.</span></span> <span data-ttu-id="cd56d-120">기본적으로 최대 회의 크기는 250입니다.</span><span class="sxs-lookup"><span data-stu-id="cd56d-120">By default, the maximum conference size is 250.</span></span>

- <span data-ttu-id="cd56d-121">**참가자가 익명 사용자를 초대할 수 있도록 허용** 사용자가 회의에 익명 사용자를 초대할 수 있도록 하려면이 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd56d-121">**Allow participants to invite anonymous users** Select this check box to allow users to invite anonymous users to conferences.</span></span> <span data-ttu-id="cd56d-122">익명 사용자는 조직의 Active Directory 도메인 서비스에 자격 증명이 없고 인증 되지 않은 사용자입니다.</span><span class="sxs-lookup"><span data-stu-id="cd56d-122">Anonymous users are users who do not have credentials in your organization's Active Directory Domain Services and who, therefore, are not authenticated.</span></span>

- <span data-ttu-id="cd56d-123">**기록** 중 참가자가 회의를 녹음할 수 있는지 여부를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd56d-123">**Recording** Specify whether or not participants can record conferences.</span></span> <span data-ttu-id="cd56d-124">옵션은 **없음** 또는 **기록 사용**입니다.</span><span class="sxs-lookup"><span data-stu-id="cd56d-124">The options are **None** or **Enable recording**.</span></span>

- <span data-ttu-id="cd56d-125">**페더레이션 및 익명 참가자가 녹화할 수 있도록 허용** 이 확인란을 선택 하면 인증 되지 않은 외부 참가자가 회의를 녹음할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd56d-125">**Allow federated and anonymous participants to record** Select this check box to allow external and unauthenticated participants to record conferences.</span></span>

- <span data-ttu-id="cd56d-126">**오디오/비디오** 참가자가 오디오 및 비디오를 사용할 수 있는지 여부를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd56d-126">**Audio/video** Specify whether participants can use audio and video:</span></span>

  - <span data-ttu-id="cd56d-127">**없음** 오디오 및 비디오 사용을 방지 하려면이 옵션을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd56d-127">**None** Select this option to prevent the use of audio and video.</span></span>

  - <span data-ttu-id="cd56d-128">**IP 오디오 사용** 오디오만 사용 하 고 비디오는 허용 하지 않으려면이 옵션을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd56d-128">**Enable IP audio** Select this option to allow the use of audio but not video.</span></span>

  - <span data-ttu-id="cd56d-129">**IP 오디오/비디오 사용** 오디오 및 비디오를 모두 허용 하려면이 옵션을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd56d-129">**Enable IP audio/video** Select this option to allow both audio and video.</span></span>

- <span data-ttu-id="cd56d-130">**PSTN 전화 접속 회의 사용** 오디오 **/비디오**에서 오디오를 사용 하도록 설정한 경우 사용자가 PSTN (공개 교환 전화 네트워크)을 사용 하 여 회의에 전화 접속할 수 있도록 하려면이 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd56d-130">**Enable PSTN dial-in conferencing** If you enabled audio in **Audio/video**, select this check box to allow users to dial in to conferences by using the public switched telephone network (PSTN).</span></span>

- <span data-ttu-id="cd56d-131">**익명 참가자가 전화를 걸 수 있도록 허용** 사용자가 회의에 전화 접속할 수 있도록 허용 하 고 인증 되지 않은 (익명) 사용자가 전화 접속 phoning를 사용 하 여 컨퍼런스에 참가할 수 있도록 하려면이 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd56d-131">**Allow anonymous participants to dial out** Select this check box if you allow users to dial in to conferences and you want to allow unauthenticated (anonymous) users to join a conference by using dial out phoning.</span></span> <span data-ttu-id="cd56d-132">전화 걸기 phoning를 사용 하 여 회의 서버는 사용자에 게 전화를 걸고 사용자는 해당 휴대폰에 응답 하 여 회의에 참가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd56d-132">With dial-out phoning, the conference server calls the user, and the user answers the phone to join the conference.</span></span>

- <span data-ttu-id="cd56d-133">**엔터프라이즈 음성에 대해 참가자가 사용 하도록 설정 되지 않은 경우 전화를 걸 수 있도록 허용** 오디오 **/비디오**에서 오디오를 사용 하도록 설정한 경우에는이 확인란을 선택 하 여 Enterprise Voice를 사용할 수 없는 사용자가 전화 접속 phoning을 사용 하 여 회의에 참가할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd56d-133">**Allow participants not enabled for Enterprise Voice to dial out** If you enabled audio in **Audio/video**, select this check box to allow users who are not enabled for Enterprise Voice to join a conference by using dial-out phoning.</span></span> <span data-ttu-id="cd56d-134">전화 걸기 phoning를 사용 하 여 회의 서버에서 사용자에 게 전화를 걸고 사용자가 휴대폰에 응답 하 여 회의에 참가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd56d-134">With dial-out phoning the conferencing server telephones the user, and then the user answers the phone to join the conference.</span></span>

- <span data-ttu-id="cd56d-135">**여러 비디오 스트림 허용** **오디오/비디오**에서 비디오를 사용 하도록 설정한 경우 사용자가 갤러리 보기 비디오를 사용 하 여 회의를 구성할 수 있도록 하려면이 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd56d-135">**Allow multiple video streams** If you enabled video in **Audio/video**, select this check box to allow users to organize conferences with Gallery View video.</span></span> <span data-ttu-id="cd56d-136">이 확인란을 선택 하면이 설정을 사용 하 여 사용자가 여러 비디오 스트림을 보내는 회의를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd56d-136">When this check box is selected, this setting allows users to organize conferences that send multiple video streams.</span></span> <span data-ttu-id="cd56d-137">이 확인란을 선택 하지 않으면 사용자는 단일 비디오 스트림을 보내는 컨퍼런스만 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd56d-137">When this check box is not selected, users can only organize conferences that send a single video stream.</span></span>

    > [!NOTE]
    > <span data-ttu-id="cd56d-p110">이 옵션은 회의에 의해 지원되는 비디오 스트림 유형을 결정합니다. 그러나 참가자가 다중 비디오 스트림을 받을 수 있는지 여부는 결정하지 않습니다. 참가자가 다중 비디오 스트림을 받을 수 있는지 여부를 결정하는 옵션은 **참가자가 다중 비디오 스트림에 참가할 수 있도록 허용**입니다.</span><span class="sxs-lookup"><span data-stu-id="cd56d-p110">This option determines the type of video stream supported by the conference. It does not determine whether participants can receive multiple video streams. The **Enable participants to join with multiple video streams** option determines whether participants can receive multiple video streams.</span></span>

- <span data-ttu-id="cd56d-141">**데이터 공동 작업** 회의가 데이터 공동 작업을 허용 하는지 여부를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd56d-141">**Data collaboration** Specify whether or not the conference allows data collaboration.</span></span> <span data-ttu-id="cd56d-142">이 옵션은 **없음** 또는 **데이터 공동 작업을 사용**합니다.</span><span class="sxs-lookup"><span data-stu-id="cd56d-142">The options are **None** or **Enable data collaboration**.</span></span>

    <span data-ttu-id="cd56d-143">데이터 공동 작업에는 다음 설정이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="cd56d-143">The following settings apply to data collaboration:</span></span>

  - <span data-ttu-id="cd56d-144">**페더레이션 및 익명 참가자가 콘텐츠를 다운로드할 수 있도록 허용** 데이터 공동 작업을 허용 하는 경우이 확인란을 선택 하면 외부 및 인증 되지 않은 사용자가 컨퍼런스에서 슬라이드 또는 유인물 등의 콘텐츠를 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd56d-144">**Allow federated and anonymous participants to download content** If you allow data collaboration, select this check box to allow external and unauthenticated users to download content, such as slides or handouts, from a conference.</span></span>

  - <span data-ttu-id="cd56d-145">**참가자가 파일을 전송할 수 있도록 허용** 데이터 공동 작업을 허용 하는 경우이 확인란을 선택 하 여 회의 중에 모든 참가자에 게 파일 전송을 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd56d-145">**Allow participants to transfer files** If you allow data collaboration, select this check box to allow file transfers to all participants during a conference.</span></span>

  - <span data-ttu-id="cd56d-146">**주석 사용** 데이터 공동 작업을 허용 하는 경우 참가자가 회의 중에 공유 되는 콘텐츠에 화면 주석을 만들 수 있도록 허용 하려면이 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd56d-146">**Enable annotations** If you allow data collaboration, select this check box to allow participants to make on-screen annotations on content shared during the conference.</span></span>

  - <span data-ttu-id="cd56d-147">**PowerPoint 주석 사용** 주석을 허용 하는 경우 참가자가 회의 중에 PowerPoint 슬라이드에서 공유 된 주석을 만들 수 있도록 허용 하려면이 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd56d-147">**Enable PowerPoint annotations** If you allow annotation, select this check box to allow participants to make annotations in PowerPoint slides shared during the conference.</span></span>

  - <span data-ttu-id="cd56d-148">**설문 사용** 데이터 공동 작업을 허용 하는 경우이 확인란을 선택 하 여 참가자가 회의 중에 폴링을 보류할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd56d-148">**Enable polls** If you allow data collaboration, select this check box to allow participants to hold a poll during a conference.</span></span>

- <span data-ttu-id="cd56d-149">**응용 프로그램 공유** 회의에서 응용 프로그램을 공유할 수 있는지 여부를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd56d-149">**Application sharing** Specify whether or not the conference allows application sharing.</span></span> <span data-ttu-id="cd56d-150">이 옵션은 **응용 프로그램 공유를 사용 하지 않거나** **응용 프로그램 공유를 사용 하도록 설정**합니다.</span><span class="sxs-lookup"><span data-stu-id="cd56d-150">The options are **Disable application sharing** or **Enable application sharing**.</span></span>

    <span data-ttu-id="cd56d-151">응용 프로그램 공유에는 다음 설정이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="cd56d-151">The following settings apply to application sharing:</span></span>

  - <span data-ttu-id="cd56d-152">**참가자가 제어권을 가질 수 있도록 허용** 응용 프로그램 공유를 허용 하는 경우 참가자가 회의 중에 공유 하는 응용 프로그램 또는 데스크톱을 제어할 수 있도록 허용 하려면이 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd56d-152">**Allow participants to take control** If you allow application sharing, select this check box to allow participants to take control of applications or desktops that are shared during the conference.</span></span>

  - <span data-ttu-id="cd56d-153">**페더레이션 및 익명 참가자가 제어권을 가질 수 있도록 허용** 응용 프로그램 공유를 허용 하는 경우이 확인란을 선택 하 여 외부 사용자 및 인증 되지 않은 참가자가 회의 중에 공유 하는 응용 프로그램 또는 데스크톱을 제어할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd56d-153">**Allow federated and anonymous participants to take control** If you allow application sharing, select this check box to allow external and unauthenticated participants to take control of applications or desktops that are shared during the conference.</span></span>

- <span data-ttu-id="cd56d-154">**참가자 정책** 이 섹션의 설정은 사용자에 게 컨퍼런스 또는 2-파티 세션의 참여자로 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cd56d-154">**Participant policy** The settings in this section apply to users as participants in a conference or two-party session.</span></span> <span data-ttu-id="cd56d-155">다음 설정은 사용자별 설정 이므로 컨퍼런스 또는 2-타사 세션의 한 사용자는 동일한 컨퍼런스 또는 2-타사 세션의 다른 사용자와 다른 기능을 가질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd56d-155">Because the following settings are per-user settings, one user in a conference or two-party session may have different capabilities than another user in the same conference or two-party session.</span></span>

    <span data-ttu-id="cd56d-156">레이블 옆의 위쪽 화살표 또는 아래쪽 화살표를 클릭하여 섹션을 닫거나 엽니다.</span><span class="sxs-lookup"><span data-stu-id="cd56d-156">Click the up arrow or down arrow next to the label to close or open the section.</span></span>

- <span data-ttu-id="cd56d-p114">사용자가 회의 또는 두 사용자 간의 세션에 참가하는 동안 응용 프로그램이나 데스크톱을 공유하도록 허용하려면 **응용 프로그램 및 데스크톱 공유 사용**을 선택합니다. 사용자가 회의 또는 두 사용자 간의 세션에 참가하는 동안 응용 프로그램이나 데스크톱을 공유하지 못하도록 하려면 **응용 프로그램 및 데스크톱 공유 사용 안 함**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="cd56d-p114">Select **Enable application and desktop sharing** to allow users to share applications or their desktop while participating in a conference or two-party session. Select **Disable application and desktop sharing** to prevent users from sharing applications or their desktop while participating in a conference or two-party session.</span></span>

- <span data-ttu-id="cd56d-159">**피어 투 피어 파일 전송 사용** 이 확인란을 선택 하 여 사용자 간 파일 전송 (즉, 모든 참가자를 포함 하지 않는 파일 전송)을 컨퍼런스 또는 2-파티 세션 중에 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd56d-159">**Enable peer-to-peer file transfer** Select this check box to allow person-to-person file transfers (that is, file transfers that do not involve all participants) during a conference or two-party session.</span></span>

- <span data-ttu-id="cd56d-160">**피어 투 피어 기록 사용** 이 확인란을 선택 하면 사용자가 제 2 자 세션을 녹화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd56d-160">**Enable peer-to-peer recording** Select this check box to allow users to record two-party sessions.</span></span>

- <span data-ttu-id="cd56d-161">**참가자가 여러 비디오 스트림에 참가할 수 있도록 설정** 참가자가이를 허용 하는 회의에서 갤러리 보기 비디오를 받도록 허용 하려면이 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd56d-161">**Enable participants to join with multiple video streams** Select this check box to allow participants to receive Gallery View video in conferences that allow it.</span></span> <span data-ttu-id="cd56d-162">이 옵션을 선택 하지 않은 경우 참가자는 회의가 허용 하는 내용에 관계 없이 단일 비디오 스트림만 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd56d-162">If this option is not selected, participants can only receive a single video stream regardless of what the conference allows.</span></span>

    > [!NOTE]
    > <span data-ttu-id="cd56d-163">회의에서 다중 비디오 스트림을 허용하는지 여부는 **다중 비디오 스트림 허용**에 따라 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="cd56d-163">The **Allow multiple video streams** determines whether a conference allows multiple video streams.</span></span>

<span data-ttu-id="cd56d-p116">회의 기능에 대한 자세한 내용은 계획 설명서의 [Overview of Conferencing](https://technet.microsoft.com/library/5bb90e69-3d4f-4d59-a1ee-2550de84439f.aspx)를 참조하세요. 회의 정책 사용에 대한 자세한 내용은 작업 설명서의 [Conferencing Policies](https://technet.microsoft.com/library/8f92eb7c-ee66-4df6-a726-4bff93b122cb.aspx)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="cd56d-p116">For details about conferencing features and capabilities, see [Overview of Conferencing](https://technet.microsoft.com/library/5bb90e69-3d4f-4d59-a1ee-2550de84439f.aspx) in the Planning documentation. For details about working with conferencing policies, see [Conferencing Policies](https://technet.microsoft.com/library/8f92eb7c-ee66-4df6-a726-4bff93b122cb.aspx) in the Operations documentation.</span></span>


