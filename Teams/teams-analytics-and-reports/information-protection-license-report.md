---
title: Microsoft Teams 보호 라이선스 보고서
author: anandab-msft
ms.author: anandab
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: ''
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: ''
ms.collection:
- M365-collaboration
description: 관리 센터의 Teams 정보 보호 라이선스 보고서를 사용하여 조직의 앱이 변경 알림 Microsoft Teams 구독 API를 사용하는 방법을 알아보는 방법을 알아보습니다.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: f5652ee503d6810a11f1b152dc0ea2dad23cf4df
ms.sourcegitcommit: 5c68298474d1782e69bde8c0940be7150cb93f6e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/23/2021
ms.locfileid: "53096887"
---
# <a name="microsoft-teams-information-protection-license-report"></a><span data-ttu-id="1ffc6-103">Microsoft Teams 보호 라이선스 보고서</span><span class="sxs-lookup"><span data-stu-id="1ffc6-103">Microsoft Teams information protection license report</span></span>

<span data-ttu-id="1ffc6-104">Teams 정보 보호 라이선스 보고서는 테넌트 [](/graph/api/resources/subscription?view=graph-rest-1.0) 수준에서 메시지 [](/graph/api/resources/webhooks?view=graph-rest-1.0) 생성, 업데이트 또는 삭제된 메시지 수신을 수신하기 위해 알림 이벤트를 변경하기 위해 구독한 앱(즉, /teams/getAllMessagesage 또는 /chats/getAllMessages)에 대한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="1ffc6-104">The Teams information protection license report gives insight into apps that have [subscribed](/graph/api/resources/subscription?view=graph-rest-1.0) to [change notification](/graph/api/resources/webhooks?view=graph-rest-1.0) events to listen to created, updated, or deleted messages at tenant level (that is, /teams/getAllMessage or /chats/getAllMessages).</span></span> <span data-ttu-id="1ffc6-105">메시지에 해당하는 변경 알림은 사용자에게 필요한 라이선스가 있는 경우만 성공적으로 [전송됩니다.](/graph/teams-licenses)</span><span class="sxs-lookup"><span data-stu-id="1ffc6-105">A change notification corresponding to the message is sent successfully only when the user has the [required license](/graph/teams-licenses).</span></span>  <span data-ttu-id="1ffc6-106">특정 사용자가 트리거한 변경 알림 수를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1ffc6-106">You can see how many change notifications was triggered by a given user.</span></span>


## <a name="view-the-information-protection-license-report"></a><span data-ttu-id="1ffc6-107">정보 보호 라이선스 보고서 보기</span><span class="sxs-lookup"><span data-stu-id="1ffc6-107">View the information protection license report</span></span>

<span data-ttu-id="1ffc6-108">이러한 정책을 관리하려면 전역 관리자 또는 Teams 서비스 관리자여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ffc6-108">You must be a Teams service admin to make these changes.</span></span> <span data-ttu-id="1ffc6-109">관리 역할 및 사용 권한 가져오기에 대한 내용은 [Teams 관리자 역할 사용](../using-admin-roles.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1ffc6-109">See [Use Teams administrator roles to manage Teams](../using-admin-roles.md) to read about getting admin roles and permissions.</span></span>

1. <span data-ttu-id="1ffc6-110">관리 센터의 왼쪽 탐색에서 Microsoft Teams 보고서 **&**  >  **분석을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="1ffc6-110">In the left navigation of the Microsoft Teams admin center, select **Analytics & reports** > **Usage reports**.</span></span> <span data-ttu-id="1ffc6-111">보고서 보기 **탭의** **보고서에서** 정보 보호 **라이선스를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="1ffc6-111">On the **View reports** tab, under **Report**, select **Information Protection License**.</span></span>
2. <span data-ttu-id="1ffc6-112">날짜 **범위에서** 범위를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="1ffc6-112">Under **Date range**, select a range.</span></span>
3. <span data-ttu-id="1ffc6-113">**앱에서** 앱을 선택한 다음 보고서 실행 **을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="1ffc6-113">Under **Apps**, select an app and then select **Run report**.</span></span>

    <span data-ttu-id="1ffc6-114">![콜아웃이 Teams 관리 센터의 Teams 정보 보호 라이선스 보고서 스크린샷](../media/teams-info-protection-license-report-with-callouts.png "콜아웃이 Teams 관리 센터의 Teams 정보 보호 라이선스 보고서 스크린샷")</span><span class="sxs-lookup"><span data-stu-id="1ffc6-114">![Screenshot of the Teams information protection license report in the Teams admin center with callouts](../media/teams-info-protection-license-report-with-callouts.png "Screenshot of the Teams information protection license report in the Teams admin center with callouts")</span></span>

## <a name="interpret-the-report"></a><span data-ttu-id="1ffc6-115">보고서 해석</span><span class="sxs-lookup"><span data-stu-id="1ffc6-115">Interpret the report</span></span>

|<span data-ttu-id="1ffc6-116">콜아웃</span><span class="sxs-lookup"><span data-stu-id="1ffc6-116">Callout</span></span> |<span data-ttu-id="1ffc6-117">설명</span><span class="sxs-lookup"><span data-stu-id="1ffc6-117">Description</span></span>  |
|--------|-------------|
|<span data-ttu-id="1ffc6-118">**1**</span><span class="sxs-lookup"><span data-stu-id="1ffc6-118">**1**</span></span>   |<span data-ttu-id="1ffc6-119">정보 보호 라이선스 보고서는 지난 7일, 30일 또는 90일 동안의 추세를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1ffc6-119">The information protection license report can be viewed for trends over the last 7 days, 30, or 90 days.</span></span> |
|<span data-ttu-id="1ffc6-120">**2**</span><span class="sxs-lookup"><span data-stu-id="1ffc6-120">**2**</span></span>   |<span data-ttu-id="1ffc6-121">앱 이름은 날짜 범위에서 선택한 지난 n일 동안 메시지의 알림 이벤트를 변경하기 위해 구독한 모든 앱의 목록을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="1ffc6-121">App name will display a list of all apps that have subscribed to change notification events of messages in the last n days as selected in the date range.</span></span> |
|<span data-ttu-id="1ffc6-122">**3**</span><span class="sxs-lookup"><span data-stu-id="1ffc6-122">**3**</span></span>   |<span data-ttu-id="1ffc6-123">이 표에서는 선택한 앱에 대한 사용자당 사용량을 분석할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1ffc6-123">The table gives you a breakdown of usage per user for the selected app.</span></span><ul><li><span data-ttu-id="1ffc6-124">**표시 이름은** 사용자의 표시 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="1ffc6-124">**Display name** is the display name of the user.</span></span> <span data-ttu-id="1ffc6-125">관리자 센터의 사용자 세부 정보 페이지로 이동하려면 표시 Microsoft Teams 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="1ffc6-125">Select the display name to go to the user's details page in the Microsoft Teams admin center.</span></span></li><li><span data-ttu-id="1ffc6-126">**필수 라이선스가** 있는 경우 사용자가 정의한 필수 라이선스 중 하나(여기)[ https://docs.microsoft.com/en-us/graph/teams-licenses ]가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1ffc6-126">**Has Required License** is yes if the user has one of the required licenses as defined (here)[https://docs.microsoft.com/en-us/graph/teams-licenses].</span></span> <span data-ttu-id="1ffc6-127">사용자에게 필요한 라이선스가 없는 경우  Microsoft 관리 센터에서 사용자의 라이선스 세부 정보 페이지로 이동하는 라이선스할당 링크가 표시됩니다(사용자 활성 >  >   사용자 이름 선택).</span><span class="sxs-lookup"><span data-stu-id="1ffc6-127">If the user does not have the required license, the _Assign license_ link is displayed which navigated to the user's license detail page in the Microsoft admin center (**Users** > **Active Users** > select username).</span></span></li><li><span data-ttu-id="1ffc6-128">**라이선스 보호 이벤트는** 해당 사용자가 생성, 업데이트 또는 삭제한 메시지에 대해 앱에 전송된 고유 변경 알림 이벤트의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="1ffc6-128">**License Protected Events** is the number of unique change notification events sent to the app against a message which was created, updated or deleted by that user.</span></span></li></ul> |
|<span data-ttu-id="1ffc6-129">**4**</span><span class="sxs-lookup"><span data-stu-id="1ffc6-129">**4**</span></span>   |<span data-ttu-id="1ffc6-130">오프라인 분석을 위해 보고서를 CSV 파일로 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1ffc6-130">Export the report to a CSV file for offline analysis.</span></span> <span data-ttu-id="1ffc6-131">내보내기를 **Excel** 및 **다운로드 탭을** 선택합니다. **다운로드를** 선택하여 준비가되면 보고서를 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="1ffc6-131">Select **Export to Excel**, and then the **Downloads** tab. Select **Download** to download the report when it's ready.</span></span> |
|<span data-ttu-id="1ffc6-132">**5**</span><span class="sxs-lookup"><span data-stu-id="1ffc6-132">**5**</span></span>   |<span data-ttu-id="1ffc6-133">오프라인 분석을 위해 보고서를 CSV 파일로 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1ffc6-133">Export the report to a CSV file for offline analysis.</span></span> <span data-ttu-id="1ffc6-134">내보내기를 **Excel** 및 **다운로드 탭을** 선택합니다. **다운로드를** 선택하여 준비가되면 보고서를 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="1ffc6-134">Select **Export to Excel**, and then the **Downloads** tab. Select **Download** to download the report when it's ready.</span></span> <span data-ttu-id="1ffc6-135">보고서에서 보고서를 Excel 사용자의 사용자 **ID** 및 전자 메일  주소를 나타내는 ID 및 전자 메일 열도 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="1ffc6-135">When you view the report in Excel, you'll also see an **Id** and **email** column, which represents the User ID and email address of the user.</span></span> |

## <a name="make-the-user-specific-data-anonymous"></a><span data-ttu-id="1ffc6-136">사용자별 데이터를 익명으로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="1ffc6-136">Make the user-specific data anonymous</span></span>

<span data-ttu-id="1ffc6-137">사용자 활동 보고서의 Teams 익명으로 만들기 위해 전역 관리자로 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ffc6-137">To make the data in the Teams user activity report anonymous, you have to be a global administrator.</span></span> <span data-ttu-id="1ffc6-138">그러면 보고서 및 내보내기에서 표시 이름, 전자 메일 및 Azure AD ID와 같은 식별 가능한 정보가 숨겨지게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1ffc6-138">This will hide identifiable information such as display name, email, and Azure AD ID in reports and their exports.</span></span>

1. <span data-ttu-id="1ffc6-139">Microsoft 365 관리 센터 또는 설정 또는 설정  탭에서 보고서를 \>  **선택합니다.** </span><span class="sxs-lookup"><span data-stu-id="1ffc6-139">In the Microsoft 365 admin center, go to **Settings** \> **Org Settings**, and under the **Services** tab, choose **Reports**.</span></span>
    
2. <span data-ttu-id="1ffc6-140">보고서를 **선택한** 다음 익명 식별자 **표시를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="1ffc6-140">Select **Reports**, and then choose to **Display anonymous identifiers**.</span></span> <span data-ttu-id="1ffc6-141">이 설정은 Microsoft 365 관리 센터 관리 센터의 Microsoft 365 관리 센터 모두 Teams 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="1ffc6-141">This setting gets applied both to the usage reports in the Microsoft 365 admin center and the Teams admin center.</span></span>
  
3. <span data-ttu-id="1ffc6-142">변경 **내용 저장 을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="1ffc6-142">Select **Save changes**.</span></span>
