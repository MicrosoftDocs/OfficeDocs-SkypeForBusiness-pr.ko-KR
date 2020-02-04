---
title: 지정 되지 않은 전화 번호 새로 만들기 또는 기존 편집
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.lscp.VoiceFeaVacantNumEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 58903e40-6b93-40d6-88f8-1201743cd9be
description: 지정되지 않은 번호란 조직에 대해 유효하기는 하지만 사용자나 전화에 지정되지 않은 전화 번호입니다. 지정되지 않은 번호 테이블에는 지정되지 않은 번호에 대한 통화를 처리할 방법이 나와 있습니다.
ms.openlocfilehash: e8a294273591969430abbbc450a37a5292fbe0c1
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41685671"
---
# <a name="unassigned-phone-number-create-new-or-edit-existing"></a><span data-ttu-id="c6c3b-104">미지정 전화 번호: 새로 만들기 또는 기존 항목 편집</span><span class="sxs-lookup"><span data-stu-id="c6c3b-104">Unassigned Phone Number: Create New or Edit Existing</span></span>

<span data-ttu-id="c6c3b-p102">지정되지 않은 번호란 조직에 대해 유효하기는 하지만 사용자나 전화에 지정되지 않은 전화 번호입니다. 지정되지 않은 번호 테이블에는 지정되지 않은 번호에 대한 통화를 처리할 방법이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c6c3b-p102">Unassigned numbers are phone numbers that are valid for your organization but are not assigned to a user or a phone. The unassigned number table identifies how you want calls to unassigned numbers to be treated.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c6c3b-107">지정 하지 않은 새 번호 범위 또는 기존 항목을 편집 하는 작업이 완료 되 면 **확인** 을 클릭 하 여 번호 범위가 모두 나열 된 지정 되지 **않은 번호** 페이지로 돌아갑니다.</span><span class="sxs-lookup"><span data-stu-id="c6c3b-107">When you are finished creating a new unassigned number range or editing an existing one, click **OK** to return to the **Unassigned Number** page that lists all the number ranges.</span></span> <span data-ttu-id="c6c3b-108">지정 하지 않은 번호 **범위** 페이지 또는 지정 하지 않은 번호 **Rage** 페이지에서 변경한 내용은 사용자가 지정 하지 **않은 번호** 페이지에서 **모두 커밋을** 클릭할 때까지 데이터베이스에 커밋되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c6c3b-108">The changes you made on the **New Unassigned Number Range** page or the **Edit Unassigned Number Rage** page are not committed to the database until you click **Commit all** on the **Unassigned Number** page.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="c6c3b-109">UI 참조</span><span class="sxs-lookup"><span data-stu-id="c6c3b-109">UI Reference</span></span>

<span data-ttu-id="c6c3b-110">다음 목록에서는 페이지의 필드에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="c6c3b-110">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="c6c3b-111">**이름** 지정 되지 않은 숫자 범위를 식별 하는 설명적인 이름을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6c3b-111">**Name** Type a descriptive name that identifies the unassigned number range.</span></span> <span data-ttu-id="c6c3b-112">범위를 저장 한 후에는이 이름을 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c6c3b-112">After you save the range, this name cannot be changed.</span></span>

- <span data-ttu-id="c6c3b-113">**숫자 범위** 첫 번째 필드에 지정 되지 않은 숫자 범위의 시작 번호를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6c3b-113">**Number range** In the first field, type the beginning number of the unassigned number range.</span></span> <span data-ttu-id="c6c3b-114">두 번째 필드에 범위의 끝 번호를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6c3b-114">In the second field, type the ending number of the range.</span></span>

  - <span data-ttu-id="c6c3b-115">범위의 시작 번호는 범위의 마지막 번호보다 작거나 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6c3b-115">The beginning number of the range must be less than or equal to the ending number of the range.</span></span>

  - <span data-ttu-id="c6c3b-116">범위의 시작 번호 또는 범위의 끝 번호에 내선 번호가 포함 된 경우, 시작 번호와 범위의 끝 번호에는 확장명이 포함 되어야 하 고, 내선 번호는 시작 번호와이 둘 다에 대해 동일 해야 합니다. 끝 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="c6c3b-116">If the beginning number of the range or the ending number of the range includes an extension number, both the beginning number and the ending number of the range must include an extension, and the extension number must be the same for both the beginning number and the ending number.</span></span>

  - <span data-ttu-id="c6c3b-117">번호는 정규식 (tel:)과 일치 해야 합니다 ( \+)? [1-9] \d{0,17}(; ext = [1-9] \d{0,9})?.</span><span class="sxs-lookup"><span data-stu-id="c6c3b-117">The number must match the regular expression (tel:)?(\+)?[1-9]\d{0,17}(;ext=[1-9]\d{0,9})?.</span></span> <span data-ttu-id="c6c3b-118">즉,이 숫자는 문자열 tel로 시작 될 수 있습니다 (해당 문자열을 자동으로 추가 하도록 지정 하지 않는 경우), 더하기 기호 (+), 숫자 1 ~ 9</span><span class="sxs-lookup"><span data-stu-id="c6c3b-118">This means the number may begin with the string tel: (if you don't specify that string it will be automatically added for you), a plus sign (+), and a digit 1 through 9.</span></span> <span data-ttu-id="c6c3b-119">전화 번호는 최대 17자리이며 ;ext= 뒤에 내선 번호가 오는 형식으로 내선 번호를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c6c3b-119">The phone number can be up to 17 digits and may be followed by an extension in the format ;ext= followed by the extension number.</span></span>

- <span data-ttu-id="c6c3b-120">**알림 서비스** **알림을** 선택 하면 알림 응용 프로그램에서 수신 전화 또는 **exchange um** 을 처리 하 여 Exchange um 자동 전화 교환이 수신 전화를 처리 하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6c3b-120">**Announcement service** Select **Announcement** to have the Announcement application handle the incoming call or **Exchange UM** to have an Exchange UM Auto Attendant handle the incoming call.</span></span>

- <span data-ttu-id="c6c3b-121">**알림 서비스**에 대 한 **알림을** 선택 하는 경우:</span><span class="sxs-lookup"><span data-stu-id="c6c3b-121">If you selected **Announcement** for **Announcement service**:</span></span>

  - <span data-ttu-id="c6c3b-122">**대상 서버의 FQDN** 지정 하지 않은이 범위의 번호로 들어오는 호출을 처리 하는 알림 응용 프로그램을 실행 하는 응용 프로그램 서비스의 서비스 ID를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6c3b-122">**FQDN of destination server** Select the service ID of the Application service that runs the Announcement application that will handle incoming calls to this range of unassigned numbers.</span></span>

  - <span data-ttu-id="c6c3b-123">**공지 사항** 지정 하지 않은이 번호 범위에 대해 재생할 공지 사항을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6c3b-123">**Announcement** Select the announcement to be played for this range of unassigned numbers.</span></span>

- <span data-ttu-id="c6c3b-124">**알림 서비스**용 **Exchange UM** 을 선택한 경우 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6c3b-124">If you selected **Exchange UM** for **Announcement service**:</span></span>

  - <span data-ttu-id="c6c3b-125">**자동 전화 교환 전화 번호** Exchange UM 자동 전화 교환의 전화 번호를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6c3b-125">**Auto Attendant phone number** Select the phone number for the Exchange UM Auto Attendant.</span></span>

<span data-ttu-id="c6c3b-126">알림 기능 및 기능에 대 한 자세한 내용은 계획 설명서의 비즈니스용 [Skype 2015에서 알림 신청에 대 한 계획](../../plan-your-deployment/enterprise-voice-solution/announcement.md) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c6c3b-126">For details about Announcement features and capabilities, see [Plan for the Announcement application in Skype for Business 2015](../../plan-your-deployment/enterprise-voice-solution/announcement.md) in the Planning documentation.</span></span> <span data-ttu-id="c6c3b-127">지정되지 않은 번호 범위를 사용하는 방법에 대한 자세한 내용은 작업 설명서에서 [Configure Routing of Unassigned Phone Numbers](https://technet.microsoft.com/library/a0650659-dce7-455f-8977-02454bbfa400.aspx)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c6c3b-127">For details about working with unassigned number ranges, see [Configure Routing of Unassigned Phone Numbers](https://technet.microsoft.com/library/a0650659-dce7-455f-8977-02454bbfa400.aspx) in the Operations documentation.</span></span>


