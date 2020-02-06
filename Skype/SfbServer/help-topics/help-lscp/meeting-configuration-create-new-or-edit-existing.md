---
title: 모임 구성 새로 만들기 또는 기존 편집
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/24/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.ConfMeetingSettingEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e8fc19fa-6cd7-4f68-b90a-1c7e1b649abd
description: 모임 구성 설정은 사용자가 예약하는 전화 회의의 사용자 참가 환경을 정의합니다. 이러한 설정은 예약된 모임에만 적용됩니다. 즉, 클라이언트에서 모임 시작 옵션을 클릭하여 만든 임시 모임의 경우 이러한 설정이 적용되지 않습니다.
ms.openlocfilehash: e7b3ac1858ed012d99af32c8910b6f9e6d69f6a2
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41822691"
---
# <a name="meeting-configuration-create-new-or-edit-existing"></a><span data-ttu-id="44531-105">모임 구성: 새로 만들기 또는 기존 항목 편집</span><span class="sxs-lookup"><span data-stu-id="44531-105">Meeting Configuration: Create New or Edit Existing</span></span>

<span data-ttu-id="44531-p102">모임 구성 설정은 사용자가 예약하는 전화 회의의 사용자 참가 환경을 정의합니다. 이러한 설정은 예약된 모임에만 적용됩니다. 즉, 클라이언트에서 **모임 시작** 옵션을 클릭하여 만든 임시 모임의 경우 이러한 설정이 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="44531-p102">Meeting configuration settings define the user join experience for conferences scheduled by users. These settings only apply to scheduled meetings. They do not apply to ad-hoc meetings created by clicking the **Meet Now** option in the client.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="44531-109">UI 참조</span><span class="sxs-lookup"><span data-stu-id="44531-109">UI Reference</span></span>

<span data-ttu-id="44531-110">다음 목록에서는 페이지의 필드에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="44531-110">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="44531-111">**범위** 만들거나 수정 하는 모임 구성의 범위 (전역, 사이트 또는 풀)를 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="44531-111">**Scope** Identifies the scope of the meeting configuration that you are creating or modifying: global, site, or pool.</span></span>

- <span data-ttu-id="44531-112">**이름** 모임 구성은 기본적으로 명명 되며, 이름을 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="44531-112">**Name** Meeting configurations are named by default, and the name cannot be changed.</span></span>

- <span data-ttu-id="44531-113">**PSTN 발신자가 대기실를 우회 함** PSTN (공공 전환 전화 네트워크) 전화선을 통해 회의에 전화를 거는 사용자가 자동으로 허용 되도록 하려면이 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="44531-113">**PSTN callers bypass lobby** Select this check box to automatically admit users who are dialing in to the conference over a public switched telephone network (PSTN) phone line.</span></span> <span data-ttu-id="44531-114">이 확인란의 선택을 취소 하면 전화 회의 발표자가 회의에 대 한 액세스 권한을 부여할 때까지 PSTN 호출자를 회의 대기실로 라우팅하고 해당 항목이 보류 됩니다.</span><span class="sxs-lookup"><span data-stu-id="44531-114">Clear this check box to route PSTN callers to the conference lobby, where they are on hold until a conference presenter grants them access to the conference.</span></span>

- <span data-ttu-id="44531-115">**발표자로 지정** 발표자가 전화 회의에 참가할 때 자동으로 지정 되는 사용자 범주 (모임 이끌이 외)를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="44531-115">**Designate as presenter** Select the category of users (besides the meeting organizer) who are automatically designated as presenters when they join a conference.</span></span> <span data-ttu-id="44531-116">이 설정에 관계 없이 발표자는 회의가 예정 된 경우 발표자로 명시적으로 지정 되거나, 회의가 진행 되는 동안 발표자에 게 명시적으로 승격 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44531-116">Regardless of this setting, presenters can be explicitly designated as presenters when the conference is scheduled, or they can be explicitly promoted to presenter during the conference.</span></span> <span data-ttu-id="44531-117">옵션은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="44531-117">The options are:</span></span>

  - <span data-ttu-id="44531-118">**없음** 주최자 이외의 다른 하나는 자동으로 발표자로 지정 되지 않은 경우이 옵션을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="44531-118">**None** Select this option if no one other than the organizer is automatically designated as a presenter.</span></span>

  - <span data-ttu-id="44531-119">**회사** 조직의 구성원만 발표자로 자동 지정 하려면이 옵션을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="44531-119">**Company** Select this option to automatically designate only members of your organization as presenters.</span></span>

  - <span data-ttu-id="44531-120">**모든 사용자** 발표자가 될 사람을 자동으로 지정 하려면이 옵션을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="44531-120">**Everyone** Select this option to automatically designate anyone to be a presenter.</span></span>

- <span data-ttu-id="44531-121">**기본적으로 회의 유형 지정** 이 설정은 Outlook 회의 추가 기능에서 항상 이끌이 지정 된 회의를 사용 하 여 회의가 예약 되는지 여부를 제어 하며,이는 예약 된 회의에 항상 동일한 연결 URL 및 오디오 정보가 있음을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="44531-121">**Assigned conference type by default** This setting controls whether the Outlook Conferencing Addin always schedules conferences by using the organizer's assigned conference, which means that scheduled conferences always have the same join URL and audio information.</span></span> <span data-ttu-id="44531-122">예약 된 회의가 항상 동일한 참가 URL을 사용 하도록 하려면이 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="44531-122">Select this check box to have scheduled conferences always use the same join URL.</span></span> <span data-ttu-id="44531-123">각 회의에 대해 다른 참가 URL을 사용 하려면이 확인란의 선택을 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="44531-123">Clear this check box to use a different join URL for each conference.</span></span>

- <span data-ttu-id="44531-124">**익명 사용자가 기본적으로** 허용 익명 (인증 되지 않은) 사용자가 기본적으로 회의에 참가할 수 있도록 허용 된 경우이 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="44531-124">**Admit anonymous users by default** Select this check box if anonymous (that is, unauthenticated) users are allowed to attend conferences by default.</span></span> <span data-ttu-id="44531-125">익명 사용자가 기본적으로 회의에 참가할 수 없는 경우이 확인란의 선택을 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="44531-125">Clear this check box if anonymous users are not allowed to attend conferences by default.</span></span>

- <span data-ttu-id="44531-126">**로고 URL** 사용자 지정 회의 초대에 사용할 이미지가 있는 URL을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="44531-126">**Logo URL** Type the URL that has the image to be used for custom conference invitations.</span></span>

- <span data-ttu-id="44531-127">**도움말 URL** 사용자가 전화 회의 참가에 대 한 지원을 받을 수 있는 웹 사이트의 URL을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="44531-127">**Help URL** Type the URL for a website where users can obtain assistance for joining the conference.</span></span>

- <span data-ttu-id="44531-128">**Legal 텍스트 URL** 전화 회의에 대 한 법적 정보 및 법적 고 지 사항을 포함 하는 웹 사이트의 URL을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="44531-128">**Legal text URL** Type the URL for a website that has the legal information and disclaimers for the conference.</span></span>

- <span data-ttu-id="44531-129">**사용자 지정 바닥글 텍스트** 사용자 지정 회의 초대에 사용할 텍스트를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="44531-129">**Custom footer text** Type the text to be used on custom conference invitations.</span></span>

<span data-ttu-id="44531-p107">모임 구성을 사용하는 방법에 대한 자세한 내용은 작업 설명서의 [Create a or modify a Collection of Meeting Configuration Settings](https://technet.microsoft.com/library/ce6773c1-a0d5-4405-8e32-33a6f3a46a1a.aspx)을 참조하세요. 대규모 모임에 대해 모임 구성을 설정하는 방법에 대한 자세한 내용은 계획 설명서의 [Setting Up Support for Large Meetings](https://technet.microsoft.com/library/8e22d34b-b395-408d-9d48-8f2a3abe9513.aspx)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="44531-p107">For details about working with meeting configurations, see [Create a or modify a Collection of Meeting Configuration Settings](https://technet.microsoft.com/library/ce6773c1-a0d5-4405-8e32-33a6f3a46a1a.aspx) in the Operations documentation. For details about setting meeting configurations for large meetings, see [Setting Up Support for Large Meetings](https://technet.microsoft.com/library/8e22d34b-b395-408d-9d48-8f2a3abe9513.aspx) in the Planning documentation.</span></span>


