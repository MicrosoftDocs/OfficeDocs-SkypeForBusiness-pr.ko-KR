---
title: 관리 센터를 사용하여 Microsoft 365 계정 만들기
description: 그래픽 사용자 인터페이스를 사용하려면 관리 센터를 사용하여 Microsoft Teams 룸 및 공동 작업 Microsoft Teams 리소스 계정을 Microsoft 365 있습니다.
ms.reviewer: payurevi
manager: serdars
audience: ITPro
keywords: 디바이스 계정 만들기, Microsoft 365 UI, Microsoft 365 관리 센터
ms.sitesec: library
ms.service: msteams
author: flinchbot
ms.author: mitressl
ms.topic: article
ms.localizationpriority: medium
ms.openlocfilehash: 1137f462b9c21455f3a65a87075fd653b5c081b9
ms.sourcegitcommit: f0ccafb7e9c2d382ab4545e085657e8129024f1d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/16/2020
ms.locfileid: "44268038"
---
# <a name="create-a-microsoft-365-resource-account-using-the-microsoft-365-admin-center"></a><span data-ttu-id="93c5d-104">Microsoft 365 관리 센터를 사용하여 Microsoft 365 리소스 계정 만들기</span><span class="sxs-lookup"><span data-stu-id="93c5d-104">Create a Microsoft 365 resource account using the Microsoft 365 admin center</span></span>

<span data-ttu-id="93c5d-105">Microsoft 365 리소스 계정은 Teams, 프로젝터 등 특정 리소스에 전용인 사서함 및 계정입니다.</span><span class="sxs-lookup"><span data-stu-id="93c5d-105">Microsoft 365 resource accounts are mailbox and Teams accounts that are dedicated to specific resources, such as a room, projector, and so on.</span></span> <span data-ttu-id="93c5d-106">이러한 리소스 계정은 사용자가 만들 때 정의한 규칙을 사용하여 모임 초대에 자동으로 응답할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="93c5d-106">These resource accounts can automatically respond to meeting invites using rules you define when they're created.</span></span> <span data-ttu-id="93c5d-107">예를 들어 회의실과 같은 공통 리소스가 있는 경우 일정 가용성에 따라 모임 초대를 자동으로 수락하거나 거부하는 해당 회의실에 대한 리소스 계정을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="93c5d-107">For example, if you have a common resource such as a conference room, you can set up a resource account for that conference room that will automatically accept or decline meeting invites depending on its calendar availability.</span></span>

<!-- The steps in this article show you how to set up a resource account using the Microsoft 365 admin center. If you'd rather use PowerShell to create resource accounts, [Create a resource account using the PowerShell](resource-account-ps.md). -->

[!INCLUDE [m365-teams-resource-account-difference](../includes/m365-teams-resource-account-difference.md)]

## <a name="licensing"></a><span data-ttu-id="93c5d-108">라이선싱</span><span class="sxs-lookup"><span data-stu-id="93c5d-108">Licensing</span></span>

<span data-ttu-id="93c5d-109">리소스 계정을 Microsoft 365 전에 필요한 라이선스 종류를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="93c5d-109">Before you create a Microsoft 365 resource account, check to see what kind of license it needs.</span></span> <span data-ttu-id="93c5d-110">리소스 계정을 사용하여 리소스를 예약하는 경우(즉, 모임에 리소스를 초대하고 초대를 자동으로 수락하거나 거부하는 경우) 리소스 계정에 라이선스를 할당할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="93c5d-110">If you'll only use a resource account to book a resource (that is, invite the resource to your meeting and have it automatically accept or decline the invitation), you don't need to assign a license to a resource account.</span></span> <span data-ttu-id="93c5d-111">다음 상황에서 리소스 계정에 라이선스를 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="93c5d-111">You'll need to assign a license to the resource account in the following situations:</span></span>

- <span data-ttu-id="93c5d-112">**Teams 모임** 리소스(예: Microsoft Teams 룸 콘솔, 공동 작업 표시줄 등)가 모임에 참가하여 참석자들이 해당 Teams 비디오 및 오디오를 표시하는 데 사용할 수 있도록 하려는 경우 미팅룸 라이선스가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="93c5d-112">**Teams meeting** If you want the resource (such as a Microsoft Teams Rooms console, collaboration bar, and so on) to join a Teams meeting so attendees can use it to present video and audio through it, you need a Meeting Room license.</span></span> 
- <span data-ttu-id="93c5d-113">**PSTN 호출** 리소스가 외부 전화 번호(공용 전환 전화 네트워크 또는 PSTN 호출)에 대한 통화를 걸거나 받으려 하는 경우 Microsoft 365 전화 시스템 또는 Microsoft 365 Business Voice 라이선스가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="93c5d-113">**PSTN calls** If you want the resource to make or receive calls to or from an external phone numbers (called a Public Switched Telephone Network or PSTN call), you need a Microsoft 365 Phone System or Microsoft 365 Business Voice license.</span></span>

<span data-ttu-id="93c5d-114">미팅룸, 전화 시스템 및 Business Voice 라이선스에 대한 자세한 내용은 추가 Microsoft Teams 라이선스를 [참조하세요.](../teams-add-on-licensing/microsoft-teams-add-on-licensing.md)</span><span class="sxs-lookup"><span data-stu-id="93c5d-114">For more information about Meeting Room, Phone System, and Business Voice licenses, see [Microsoft Teams add-on licenses](../teams-add-on-licensing/microsoft-teams-add-on-licensing.md)</span></span>

## <a name="create-a-resource-account-in-the-microsoft-365-admin-center"></a><a href="" id="create-device-acct-m365-admin-ctr"></a><span data-ttu-id="93c5d-115">관리 센터에서 Microsoft 365 계정 만들기</span><span class="sxs-lookup"><span data-stu-id="93c5d-115">Create a resource account in the Microsoft 365 admin center</span></span>

1. <span data-ttu-id="93c5d-116">방문하여 Microsoft 365 로그인https://admin.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="93c5d-116">Sign in to Microsoft 365 by visiting https://admin.microsoft.com</span></span>
2. <span data-ttu-id="93c5d-117">테넌트에 대한 관리자 Microsoft 365 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="93c5d-117">Provide the admin credentials for your Microsoft 365 tenant.</span></span> <span data-ttu-id="93c5d-118">이렇게 하면 관리 센터로 Microsoft 365 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="93c5d-118">This will take you to your Microsoft 365 admin center.</span></span>

:::image type="content" source="../media/collaboration-bar-m365-admin-center.png" alt-text="Microsoft 365 관리 센터":::
3. <span data-ttu-id="93c5d-120">관리 센터에서 왼쪽  패널의 리소스로 이동한 다음(먼저 모든 표시를 **선택해야 할 수 있습니다)로** 이동한 다음, & 를 선택합니다. </span><span class="sxs-lookup"><span data-stu-id="93c5d-120">In the admin center, navigate to **Resources** in the left panel (you might need to select **Show all** first), and then select **Rooms & equipment**.</span></span>

:::image type="content" source="../media/collaboration-bar-m365-resources-rooms.png" alt-text="Microsoft 365 관리 센터 - 리소스":::
4. <span data-ttu-id="93c5d-122">리소스 **사서함 추가를 선택하여** 새 룸 계정을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="93c5d-122">Select **Add a resource mailbox** to create a new room account.</span></span> <span data-ttu-id="93c5d-123">계정에 대한 표시 이름 및 전자 메일 주소를 입력하고 **추가를** 선택한 다음 **닫기 를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="93c5d-123">Enter a display name and email address for the account, select **Add**, and then select **Close**.</span></span> <span data-ttu-id="93c5d-124">모든 리소스 계정에 대한 이름 규칙을 표준화하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="93c5d-124">We recommend you standardize on a naming convention for all of your resource accounts.</span></span>

> [!NOTE]
> <span data-ttu-id="93c5d-125">기본적으로 리소스 계정은 다음 설정으로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="93c5d-125">By default, resource accounts are set up with the following settings.</span></span> <span data-ttu-id="93c5d-126">변경하려는 경우 닫기  를 선택하기 전에 일주 옵션 설정을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="93c5d-126">If you want to change them, select **Set scheduling options** before you select **Close**.</span></span> <span data-ttu-id="93c5d-127">나중에 변경하려는 경우 리소스 룸 & 장비로 이동한 다음, 리소스 계정을 선택한 다음 예약 옵션에서  >   **편집을 선택합니다.** </span><span class="sxs-lookup"><span data-stu-id="93c5d-127">If you want to change them later, navigate to **Resources** > **Rooms & equipment**, select the resource account and then select **Edit** under **Booking options**.</span></span>
>
> - <span data-ttu-id="93c5d-128">반복 모임 허용</span><span class="sxs-lookup"><span data-stu-id="93c5d-128">Allow repeat meetings</span></span>
> - <span data-ttu-id="93c5d-129">다음 제한을 초과하여 모임을 자동으로 거부합니다.</span><span class="sxs-lookup"><span data-stu-id="93c5d-129">Automatically decline meetings outside of the following limits</span></span>
>   - <span data-ttu-id="93c5d-130">예약 기간(일): 180</span><span class="sxs-lookup"><span data-stu-id="93c5d-130">Booking window (days): 180</span></span>
>   - <span data-ttu-id="93c5d-131">최대 기간(시간): 24</span><span class="sxs-lookup"><span data-stu-id="93c5d-131">Maximum duration (hours): 24</span></span>
> - <span data-ttu-id="93c5d-132">모임 요청 자동 수락</span><span class="sxs-lookup"><span data-stu-id="93c5d-132">Auto accept meeting requests</span></span>

:::image type="content" source="../media/collaboration-bars-admin-resources.png" alt-text="Microsoft 365 관리 센터 - 리소스 추가":::
5. <span data-ttu-id="93c5d-134">관리 센터의 **사용자** 섹션으로 이동하고 활성 사용자 **목록에서** 방금 만든 방이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="93c5d-134">Navigate to the **Users** section in admin center and, in the **Active users** list, you will see the room you just created.</span></span>

:::image type="content" source="../media/collaboration-bars-M3565-admin-active-users.png" alt-text="Microsoft 365 관리 센터 - 활성 사용자 보기":::
6. <span data-ttu-id="93c5d-136">룸의 이름에서 선택하고 오른쪽에 계정 속성 패널이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="93c5d-136">Select on the name of the room and an account properties panel will appear on the right.</span></span>

:::image type="content" source="../media/collaboration-bar-m365-admin-center-active-user-settings.png" alt-text="Microsoft 365 관리 센터 - 사용자 속성":::
7. <span data-ttu-id="93c5d-138">이제 리소스 계정에 암호를 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="93c5d-138">Now you need to assign a password to the resource account.</span></span> <span data-ttu-id="93c5d-139">패널에서 계정 속성 및 몇 가지 선택적 작업을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="93c5d-139">In the panel, you can see the account properties and several optional actions.</span></span> <span data-ttu-id="93c5d-140">암호를  변경하려면 사용자 이름 아래에서 암호 재설정 키 아이콘을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="93c5d-140">Select the **Reset password** key icon under the username to change the password.</span></span> <span data-ttu-id="93c5d-141">이 사용자에게 처음 로그인할 때 암호를 **변경하도록 선택을 선택하지 않습니다.**</span><span class="sxs-lookup"><span data-stu-id="93c5d-141">Unselect **Require this user to change their password when they first sign in**.</span></span> <span data-ttu-id="93c5d-142">디바이스 로그인 프로세스를 통해 암호를 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="93c5d-142">It is not possible to change the password via the device sign-in process.</span></span> <span data-ttu-id="93c5d-143">다시 **설정 을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="93c5d-143">Select **Reset**.</span></span>

:::image type="content" source="../media/collaboration-bar-m365-admin-center-active-user-password.png" alt-text="Microsoft 365 관리 센터 - 암호 재설정":::
8. <span data-ttu-id="93c5d-145">라이선스 및 **앱 섹션에서**  디바이스가 설치된 국가 또는 지역에 위치 선택을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="93c5d-145">In the **Licenses and Apps** section, set **Select location** to the country or region where the device will be installed.</span></span> <span data-ttu-id="93c5d-146">아래로 스크롤하여 할당할 라이선스 옆에 있는 상자(예: 미팅룸)를 선택한 다음 변경 내용 저장을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="93c5d-146">Scroll down and check the box next to the license to be assigned - such as Meeting Room - and then select **Save changes**.</span></span> <span data-ttu-id="93c5d-147">라이선스는 조직에 따라 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="93c5d-147">The license may vary depending on your organization.</span></span>

:::image type="content" source="../media/collaboration-bar-m365-admin-center-active-user-assign-license.png" alt-text="Microsoft 365 관리 센터 - 라이선스 할당":::
