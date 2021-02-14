---
title: 모임 구성 새로 만들기 또는 기존 데이터 편집
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.ConfMeetingSettingEdit
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: e8fc19fa-6cd7-4f68-b90a-1c7e1b649abd
ROBOTS: NOINDEX, NOFOLLOW
description: 모임 구성 설정은 사용자가 예약한 회의에 대한 사용자 참가 환경을 정의합니다. 이러한 설정은 예약된 모임에만 적용됩니다. 클라이언트에서 모임 시작 옵션을 클릭하여 만든 Ad-Hoc 모임에는 적용되지 않습니다.
ms.openlocfilehash: 87d07100e7f9411f139711de3302ce384e71cb01
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49824818"
---
# <a name="meeting-configuration-create-new-or-edit-existing"></a><span data-ttu-id="c6e88-105">모임 구성: 새로 만들기 또는 기존 항목 편집</span><span class="sxs-lookup"><span data-stu-id="c6e88-105">Meeting Configuration: Create New or Edit Existing</span></span>

<span data-ttu-id="c6e88-106">모임 구성 설정은 사용자가 예약한 회의에 대한 사용자 참가 환경을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="c6e88-106">Meeting configuration settings define the user join experience for conferences scheduled by users.</span></span> <span data-ttu-id="c6e88-107">이러한 설정은 예약된 모임에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c6e88-107">These settings only apply to scheduled meetings.</span></span> <span data-ttu-id="c6e88-108">클라이언트에서 모임 시작 옵션을 클릭하여 만든 **Ad-Hoc 모임에는** 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c6e88-108">They do not apply to ad-hoc meetings created by clicking the **Meet Now** option in the client.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="c6e88-109">UI 참조</span><span class="sxs-lookup"><span data-stu-id="c6e88-109">UI Reference</span></span>

<span data-ttu-id="c6e88-110">다음 목록에서는 페이지의 필드에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="c6e88-110">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="c6e88-111">**범위** 만들거나 수정할 모임 구성의 범위(전역, 사이트 또는 풀)를 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="c6e88-111">**Scope** Identifies the scope of the meeting configuration that you are creating or modifying: global, site, or pool.</span></span>

- <span data-ttu-id="c6e88-112">**이름** 모임 구성의 이름은 기본적으로 지정되어 있으며 이름을 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c6e88-112">**Name** Meeting configurations are named by default, and the name cannot be changed.</span></span>

- <span data-ttu-id="c6e88-113">**PSTN 발신자 우회 대기실** PSTN(Public Switched Telephone Network) 전화 회선으로 전화 회의에 전화 접속하는 사용자를 자동으로 인정하려면 이 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c6e88-113">**PSTN callers bypass lobby** Select this check box to automatically admit users who are dialing in to the conference over a public switched telephone network (PSTN) phone line.</span></span> <span data-ttu-id="c6e88-114">PSTN 발신자들을 전화 회의 대기실로 라우팅하기 위해 이 확인란의 선택을 취소합니다. 전화 회의 발표자는 전화 회의에 대한 액세스 권한을 부여할 때까지 대기 중입니다.</span><span class="sxs-lookup"><span data-stu-id="c6e88-114">Clear this check box to route PSTN callers to the conference lobby, where they are on hold until a conference presenter grants them access to the conference.</span></span>

- <span data-ttu-id="c6e88-115">**발표자 지정** 회의에 참가할 때 자동으로 발표자로 지정된 사용자 범주(모임 이끌이 외에)를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c6e88-115">**Designate as presenter** Select the category of users (besides the meeting organizer) who are automatically designated as presenters when they join a conference.</span></span> <span data-ttu-id="c6e88-116">이 설정에 관계없이 회의가 예약될 때 발표자는 명시적으로 발표자로 지정하거나, 회의 중에 발표자로 명시적으로 승격될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c6e88-116">Regardless of this setting, presenters can be explicitly designated as presenters when the conference is scheduled, or they can be explicitly promoted to presenter during the conference.</span></span> <span data-ttu-id="c6e88-117">옵션은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c6e88-117">The options are:</span></span>

  - <span data-ttu-id="c6e88-118">**없음** 이끌이가 다른 사용자가 자동으로 발표자로 지정되지 않았다면 이 옵션을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c6e88-118">**None** Select this option if no one other than the organizer is automatically designated as a presenter.</span></span>

  - <span data-ttu-id="c6e88-119">**회사** 조직의 구성원만 발표자로 자동 지정하려면 이 옵션을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c6e88-119">**Company** Select this option to automatically designate only members of your organization as presenters.</span></span>

  - <span data-ttu-id="c6e88-120">**모든 사람** 모든 사람을 발표자로 자동 지정하려면 이 옵션을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c6e88-120">**Everyone** Select this option to automatically designate anyone to be a presenter.</span></span>

- <span data-ttu-id="c6e88-121">**기본적으로 할당된 회의 유형** 이 설정은 이끌이의 할당된 회의를 사용하여 Outlook 회의 추가 기능에서 항상 회의를 예약하는지 여부를 제어합니다. 즉, 예약된 회의의 참가 URL과 오디오 정보가 항상 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="c6e88-121">**Assigned conference type by default** This setting controls whether the Outlook Conferencing Addin always schedules conferences by using the organizer's assigned conference, which means that scheduled conferences always have the same join URL and audio information.</span></span> <span data-ttu-id="c6e88-122">예약된 회의에서 항상 동일한 참가 URL을 사용하려면 이 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c6e88-122">Select this check box to have scheduled conferences always use the same join URL.</span></span> <span data-ttu-id="c6e88-123">각 회의에 대해 다른 참가 URL을 사용하게 하여 이 확인란의 선택을 취소합니다.</span><span class="sxs-lookup"><span data-stu-id="c6e88-123">Clear this check box to use a different join URL for each conference.</span></span>

- <span data-ttu-id="c6e88-124">**기본적으로 익명 사용자 지정** 익명(즉, 확인되지 않은) 사용자가 기본적으로 회의에 참석할 수 있는 경우 이 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c6e88-124">**Admit anonymous users by default** Select this check box if anonymous (that is, unauthenticated) users are allowed to attend conferences by default.</span></span> <span data-ttu-id="c6e88-125">익명 사용자가 기본적으로 회의에 참석할 수 없는 경우 이 확인란의 선택을 취소합니다.</span><span class="sxs-lookup"><span data-stu-id="c6e88-125">Clear this check box if anonymous users are not allowed to attend conferences by default.</span></span>

- <span data-ttu-id="c6e88-126">**로고 URL** 사용자 지정 회의 초대에 사용할 이미지가 있는 URL을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="c6e88-126">**Logo URL** Type the URL that has the image to be used for custom conference invitations.</span></span>

- <span data-ttu-id="c6e88-127">**도움말 URL** 사용자가 회의 참가에 대한 지원을 받을 수 있는 웹 사이트의 URL을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="c6e88-127">**Help URL** Type the URL for a website where users can obtain assistance for joining the conference.</span></span>

- <span data-ttu-id="c6e88-128">**법적 텍스트 URL** 회의에 대한 법적 정보 및 고지 사항은 있는 웹 사이트의 URL을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="c6e88-128">**Legal text URL** Type the URL for a website that has the legal information and disclaimers for the conference.</span></span>

- <span data-ttu-id="c6e88-129">**사용자 지정 발자국 텍스트** 사용자 지정 전화 회의 초대에 사용할 텍스트를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="c6e88-129">**Custom footer text** Type the text to be used on custom conference invitations.</span></span>

<span data-ttu-id="c6e88-130">모임 구성 작업에 대한 자세한 내용은 작업 설명서에서 [모임](https://technet.microsoft.com/library/ce6773c1-a0d5-4405-8e32-33a6f3a46a1a.aspx) 구성 설정 컬렉션 만들기 또는 수정을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="c6e88-130">For details about working with meeting configurations, see [Create a or modify a Collection of Meeting Configuration Settings](https://technet.microsoft.com/library/ce6773c1-a0d5-4405-8e32-33a6f3a46a1a.aspx) in the Operations documentation.</span></span> <span data-ttu-id="c6e88-131">대규모 모임에 대한 모임 구성을 설정하는 자세한 내용은 계획 설명서에서 대규모 모임에 대한 지원 설정(Setting [Up Support for Large Meetings)을](https://technet.microsoft.com/library/8e22d34b-b395-408d-9d48-8f2a3abe9513.aspx) 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="c6e88-131">For details about setting meeting configurations for large meetings, see [Setting Up Support for Large Meetings](https://technet.microsoft.com/library/8e22d34b-b395-408d-9d48-8f2a3abe9513.aspx) in the Planning documentation.</span></span>


