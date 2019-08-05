---
title: 지정 되지 않은 전화 번호 새로 만들기 또는 기존 편집
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.VoiceFeaVacantNumEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 58903e40-6b93-40d6-88f8-1201743cd9be
ROBOTS: NOINDEX, NOFOLLOW
description: 지정되지 않은 번호란 조직에 대해 유효하기는 하지만 사용자나 전화에 지정되지 않은 전화 번호입니다. 지정되지 않은 번호 테이블에는 지정되지 않은 번호에 대한 통화를 처리할 방법이 나와 있습니다.
ms.openlocfilehash: 05b0d3efe383f2056ed49be7d8ebb811643cd02d
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36191670"
---
# <a name="unassigned-phone-number-create-new-or-edit-existing"></a><span data-ttu-id="0f15d-104">지정 되지 않은 전화 번호: 새로 만들기 또는 기존 편집</span><span class="sxs-lookup"><span data-stu-id="0f15d-104">Unassigned Phone Number: Create New or Edit Existing</span></span>

> [!NOTE]
> <span data-ttu-id="0f15d-105">Exchange UM은 비즈니스용 Skype 2019을 Exchange 2013 또는 Exchange 2016와 통합할 때 비즈니스용 Skype 서버 2019에서 계속 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f15d-105">Exchange UM remains available in Skype for Business Server 2019 when you integrate Skype for Business 2019 with Exchange 2013 or Exchange 2016.</span></span> <span data-ttu-id="0f15d-106">Exchange 2019에서 지원 되는 변경 사항으로 인해 클라우드 보이스 메일과 클라우드 자동 전화 교환 기능 때문에 Exchange UM 통합이 더욱 강조 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0f15d-106">Due to changes in support in Exchange 2019, Exchange UM integration is being de-emphasized in favor of Cloud Voicemail and Cloud Auto Attendant features.</span></span>

<span data-ttu-id="0f15d-p103">지정되지 않은 번호란 조직에 대해 유효하기는 하지만 사용자나 전화에 지정되지 않은 전화 번호입니다. 지정되지 않은 번호 테이블에는 지정되지 않은 번호에 대한 통화를 처리할 방법이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f15d-p103">Unassigned numbers are phone numbers that are valid for your organization but are not assigned to a user or a phone. The unassigned number table identifies how you want calls to unassigned numbers to be treated.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0f15d-109">지정 하지 않은 새 번호 범위 또는 기존 항목을 편집 하는 작업이 완료 되 면 **확인** 을 클릭 하 여 번호 범위가 모두 나열 된 지정 되지 **않은 번호** 페이지로 돌아갑니다.</span><span class="sxs-lookup"><span data-stu-id="0f15d-109">When you are finished creating a new unassigned number range or editing an existing one, click **OK** to return to the **Unassigned Number** page that lists all the number ranges.</span></span> <span data-ttu-id="0f15d-110">지정 하지 않은 번호 **범위** 페이지 또는 지정 하지 않은 번호 **Rage** 페이지에서 변경한 내용은 사용자가 지정 하지 **않은 번호** 페이지에서 **모두 커밋을** 클릭할 때까지 데이터베이스에 커밋되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0f15d-110">The changes you made on the **New Unassigned Number Range** page or the **Edit Unassigned Number Rage** page are not committed to the database until you click **Commit all** on the **Unassigned Number** page.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="0f15d-111">UI 참조</span><span class="sxs-lookup"><span data-stu-id="0f15d-111">UI Reference</span></span>

<span data-ttu-id="0f15d-112">다음 목록에서는 페이지의 필드에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="0f15d-112">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="0f15d-113">**이름** 지정 되지 않은 숫자 범위를 식별 하는 설명적인 이름을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f15d-113">**Name** Type a descriptive name that identifies the unassigned number range.</span></span> <span data-ttu-id="0f15d-114">범위를 저장 한 후에는이 이름을 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0f15d-114">After you save the range, this name cannot be changed.</span></span>

- <span data-ttu-id="0f15d-115">**숫자 범위** 첫 번째 필드에 지정 되지 않은 숫자 범위의 시작 번호를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f15d-115">**Number range** In the first field, type the beginning number of the unassigned number range.</span></span> <span data-ttu-id="0f15d-116">두 번째 필드에 범위의 끝 번호를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f15d-116">In the second field, type the ending number of the range.</span></span>

  - <span data-ttu-id="0f15d-117">범위의 시작 번호는 범위의 마지막 번호보다 작거나 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f15d-117">The beginning number of the range must be less than or equal to the ending number of the range.</span></span>

  - <span data-ttu-id="0f15d-118">범위의 시작 번호 또는 범위의 끝 번호에 내선 번호가 포함 된 경우, 시작 번호와 범위의 끝 번호에는 확장명이 포함 되어야 하 고, 내선 번호는 시작 번호와이 둘 다에 대해 동일 해야 합니다. 끝 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="0f15d-118">If the beginning number of the range or the ending number of the range includes an extension number, both the beginning number and the ending number of the range must include an extension, and the extension number must be the same for both the beginning number and the ending number.</span></span>

  - <span data-ttu-id="0f15d-119">번호는 정규식 (tel:)과 일치 해야 합니다 ( \+)? [1-9] \d{0,17}(; ext = [1-9] \d{0,9})?.</span><span class="sxs-lookup"><span data-stu-id="0f15d-119">The number must match the regular expression (tel:)?(\+)?[1-9]\d{0,17}(;ext=[1-9]\d{0,9})?.</span></span> <span data-ttu-id="0f15d-120">즉,이 숫자는 문자열 tel로 시작 될 수 있습니다 (해당 문자열을 자동으로 추가 하도록 지정 하지 않는 경우), 더하기 기호 (+), 숫자 1 ~ 9</span><span class="sxs-lookup"><span data-stu-id="0f15d-120">This means the number may begin with the string tel: (if you don't specify that string it will be automatically added for you), a plus sign (+), and a digit 1 through 9.</span></span> <span data-ttu-id="0f15d-121">전화 번호는 최대 17자리이며 ;ext= 뒤에 내선 번호가 오는 형식으로 내선 번호를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f15d-121">The phone number can be up to 17 digits and may be followed by an extension in the format ;ext= followed by the extension number.</span></span>

- <span data-ttu-id="0f15d-122">**알림 서비스** **알림을** 선택 하면 알림 응용 프로그램에서 수신 전화 또는 **exchange um** 을 처리 하 여 Exchange um 자동 전화 교환이 수신 전화를 처리 하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f15d-122">**Announcement service** Select **Announcement** to have the Announcement application handle the incoming call or **Exchange UM** to have an Exchange UM Auto Attendant handle the incoming call.</span></span>

- <span data-ttu-id="0f15d-123">**알림 서비스**에 대 한 **알림을** 선택 하는 경우:</span><span class="sxs-lookup"><span data-stu-id="0f15d-123">If you selected **Announcement** for **Announcement service**:</span></span>

  - <span data-ttu-id="0f15d-124">**대상 서버의 FQDN** 지정 하지 않은이 범위의 번호로 들어오는 호출을 처리 하는 알림 응용 프로그램을 실행 하는 응용 프로그램 서비스의 서비스 ID를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f15d-124">**FQDN of destination server** Select the service ID of the Application service that runs the Announcement application that will handle incoming calls to this range of unassigned numbers.</span></span>

  - <span data-ttu-id="0f15d-125">**공지 사항** 지정 하지 않은이 번호 범위에 대해 재생할 공지 사항을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f15d-125">**Announcement** Select the announcement to be played for this range of unassigned numbers.</span></span>

- <span data-ttu-id="0f15d-126">**알림 서비스**용 **Exchange UM** 을 선택한 경우 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f15d-126">If you selected **Exchange UM** for **Announcement service**:</span></span>

  - <span data-ttu-id="0f15d-127">**자동 전화 교환 전화 번호** Exchange UM 자동 전화 교환의 전화 번호를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f15d-127">**Auto Attendant phone number** Select the phone number for the Exchange UM Auto Attendant.</span></span>

<span data-ttu-id="0f15d-128">알림 기능 및 기능에 대 한 자세한 내용은 계획 설명서의 비즈니스용 [Skype에서 알림 신청 계획](../../../plan-your-deployment/enterprise-voice-solution/announcement.md) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="0f15d-128">For details about Announcement features and capabilities, see [Plan for the Announcement application in Skype for Business](../../../plan-your-deployment/enterprise-voice-solution/announcement.md) in the Planning documentation.</span></span> <span data-ttu-id="0f15d-129">지정되지 않은 번호 범위를 사용하는 방법에 대한 자세한 내용은 작업 설명서에서 [Configure Routing of Unassigned Phone Numbers](https://technet.microsoft.com/library/a0650659-dce7-455f-8977-02454bbfa400.aspx)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0f15d-129">For details about working with unassigned number ranges, see [Configure Routing of Unassigned Phone Numbers](https://technet.microsoft.com/library/a0650659-dce7-455f-8977-02454bbfa400.aspx) in the Operations documentation.</span></span>


