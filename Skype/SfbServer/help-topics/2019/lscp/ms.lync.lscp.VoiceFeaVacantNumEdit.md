---
title: 미지정 전화 번호 새로 만들기 또는 기존 기능 편집
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.VoiceFeaVacantNumEdit
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 58903e40-6b93-40d6-88f8-1201743cd9be
ROBOTS: NOINDEX, NOFOLLOW
description: 지정되지 않은 번호란 조직에 대해 유효하기는 하지만 사용자나 전화에 지정되지 않은 전화 번호입니다. 지정되지 않은 번호 테이블에는 지정되지 않은 번호에 대한 통화를 처리할 방법이 나와 있습니다.
ms.openlocfilehash: 9cef4ae8075bf4982ab9c3ddd857062d4fa1a824
ms.sourcegitcommit: c477aa1a7da0b6b9bea1f5d10f1395eef418bfdb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/10/2021
ms.locfileid: "50711735"
---
# <a name="unassigned-phone-number-create-new-or-edit-existing"></a><span data-ttu-id="0dd2e-104">지정되지 않은 전화 번호: 새로 만들기 또는 기존 항목 편집</span><span class="sxs-lookup"><span data-stu-id="0dd2e-104">Unassigned Phone Number: Create New or Edit Existing</span></span>

> [!NOTE]
> <span data-ttu-id="0dd2e-105">비즈니스용 Skype 2019를 Exchange 2013 또는 Exchange 2016과 통합하면 비즈니스용 Skype 서버 2019에서 Exchange UM을 계속 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0dd2e-105">Exchange UM remains available in Skype for Business Server 2019 when you integrate Skype for Business 2019 with Exchange 2013 or Exchange 2016.</span></span> <span data-ttu-id="0dd2e-106">Exchange 2019의 지원 변경으로 인해 Exchange UM 통합은 Cloud Voicemail 및 Cloud 자동 전화 교환 위해 강조되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0dd2e-106">Due to changes in support in Exchange 2019, Exchange UM integration is being de-emphasized in favor of Cloud Voicemail and Cloud Auto Attendant features.</span></span>

<span data-ttu-id="0dd2e-p103">지정되지 않은 번호란 조직에 대해 유효하기는 하지만 사용자나 전화에 지정되지 않은 전화 번호입니다. 지정되지 않은 번호 테이블에는 지정되지 않은 번호에 대한 통화를 처리할 방법이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0dd2e-p103">Unassigned numbers are phone numbers that are valid for your organization but are not assigned to a user or a phone. The unassigned number table identifies how you want calls to unassigned numbers to be treated.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0dd2e-p104">새 지정되지 않은 번호 범위 만들기 또는 기존 지정되지 않은 번호 범위 편집을 마친 후 **확인** 을 클릭하면 모든 번호 범위의 목록이 표시되는 **지정되지 않은 번호** 페이지로 돌아갑니다. **새 지정되지 않은 번호 범위** 페이지 또는 **지정되지 않은 번호 범위 편집** 페이지에서 수행한 변경 내용은 **지정되지 않은 번호** 페이지에서 **모두 커밋** 을 클릭해야 데이터베이스로 커밋됩니다.</span><span class="sxs-lookup"><span data-stu-id="0dd2e-p104">When you are finished creating a new unassigned number range or editing an existing one, click **OK** to return to the **Unassigned Number** page that lists all the number ranges. The changes you made on the **New Unassigned Number Range** page or the **Edit Unassigned Number Rage** page are not committed to the database until you click **Commit all** on the **Unassigned Number** page.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="0dd2e-111">UI 참조</span><span class="sxs-lookup"><span data-stu-id="0dd2e-111">UI Reference</span></span>

<span data-ttu-id="0dd2e-112">다음 목록에서는 페이지의 필드에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="0dd2e-112">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="0dd2e-113">**이름** 지정되지 않은 번호 범위를 식별하는 설명적인 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="0dd2e-113">**Name** Type a descriptive name that identifies the unassigned number range.</span></span> <span data-ttu-id="0dd2e-114">범위를 저장한 후 이 이름은 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0dd2e-114">After you save the range, this name cannot be changed.</span></span>

- <span data-ttu-id="0dd2e-115">**번호 범위** 첫 번째 필드에 미지정 번호 범위의 시작 번호를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="0dd2e-115">**Number range** In the first field, type the beginning number of the unassigned number range.</span></span> <span data-ttu-id="0dd2e-116">두 번째 필드에 범위의 끝 번호를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="0dd2e-116">In the second field, type the ending number of the range.</span></span>

  - <span data-ttu-id="0dd2e-117">범위의 시작 번호는 범위의 끝 번호보다 작거나 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0dd2e-117">The beginning number of the range must be less than or equal to the ending number of the range.</span></span>

  - <span data-ttu-id="0dd2e-118">범위의 시작 번호나 끝 번호에 내선 번호가 포함된 경우에는 범위의 시작 번호와 끝 번호 둘 다에 내선 번호가 포함되어야 하며, 내선 번호는 시작 번호와 끝 번호에 대해 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0dd2e-118">If the beginning number of the range or the ending number of the range includes an extension number, both the beginning number and the ending number of the range must include an extension, and the extension number must be the same for both the beginning number and the ending number.</span></span>

  - <span data-ttu-id="0dd2e-119">이 숫자는 정규식( `tel:` )?( \+ )?과 일치해야 합니다. [1-9]\d {0,17} (;ext=[1-9]\d {0,9} )?.</span><span class="sxs-lookup"><span data-stu-id="0dd2e-119">The number must match the regular expression (`tel:`)?(\+)?[1-9]\d{0,17}(;ext=[1-9]\d{0,9})?.</span></span> <span data-ttu-id="0dd2e-120">즉, 숫자는 문자열 'tel:'으로 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0dd2e-120">This means the number may begin with the string 'tel:'.</span></span> <span data-ttu-id="0dd2e-121">해당 문자열을 지정하지 않으면 더하기 기호(+) 및 숫자 1-9와 같이 자동으로 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="0dd2e-121">If you don't specify that string, it will be automatically added for you, such as a plus sign (+), and a digit 1 through 9.</span></span> <span data-ttu-id="0dd2e-122">전화 번호는 최대 17자리이며 ;ext= 뒤에 내선 번호가 오는 형식으로 내선 번호를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0dd2e-122">The phone number can be up to 17 digits and may be followed by an extension in the format ;ext= followed by the extension number.</span></span>

- <span data-ttu-id="0dd2e-123">**공지 서비스** 알림 **응용** 프로그램에서 수신 전화를 처리하거나 **Exchange UM을** 처리하여 Exchange UM이 수신 호출을 처리하게 자동 전화 교환 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0dd2e-123">**Announcement service** Select **Announcement** to have the Announcement application handle the incoming call or **Exchange UM** to have an Exchange UM Auto Attendant handle the incoming call.</span></span>

- <span data-ttu-id="0dd2e-124">**알림 서비스** 에 대해 **알림** 을 선택한 경우 다음 옵션을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="0dd2e-124">If you selected **Announcement** for **Announcement service**:</span></span>

  - <span data-ttu-id="0dd2e-125">**대상 서버의 FQDN** 이 지정되지 않은 번호 범위에 대한 수신 전화를 처리할 알림 응용 프로그램을 실행하는 응용 프로그램 서비스의 서비스 ID를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0dd2e-125">**FQDN of destination server** Select the service ID of the Application service that runs the Announcement application that will handle incoming calls to this range of unassigned numbers.</span></span>

  - <span data-ttu-id="0dd2e-126">**공지** 이 범위의 미지정 번호에 대해 재생할 공지 사항을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0dd2e-126">**Announcement** Select the announcement to be played for this range of unassigned numbers.</span></span>

- <span data-ttu-id="0dd2e-127">**알림 서비스** 에 대해 **Exchange UM** 을 선택한 경우 다음 옵션을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="0dd2e-127">If you selected **Exchange UM** for **Announcement service**:</span></span>

  - <span data-ttu-id="0dd2e-128">**자동 전화 교환 번호** Exchange UM 연결의 전화 번호를 자동 전화 교환.</span><span class="sxs-lookup"><span data-stu-id="0dd2e-128">**Auto Attendant phone number** Select the phone number for the Exchange UM Auto Attendant.</span></span>

<span data-ttu-id="0dd2e-129">공지 사항 기능에 대한 자세한 내용은 계획 설명서에서 [Plan for the Announcement application in Skype for Business을](../../../plan-your-deployment/enterprise-voice-solution/announcement.md) 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="0dd2e-129">For details about Announcement features and capabilities, see [Plan for the Announcement application in Skype for Business](../../../plan-your-deployment/enterprise-voice-solution/announcement.md) in the Planning documentation.</span></span> <span data-ttu-id="0dd2e-130">지정되지 않은 번호 범위를 사용하는 방법에 대한 자세한 내용은 작업 설명서에서 [Configure Routing of Unassigned Phone Numbers](https://technet.microsoft.com/library/a0650659-dce7-455f-8977-02454bbfa400.aspx)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="0dd2e-130">For details about working with unassigned number ranges, see [Configure Routing of Unassigned Phone Numbers](https://technet.microsoft.com/library/a0650659-dce7-455f-8977-02454bbfa400.aspx) in the Operations documentation.</span></span>


