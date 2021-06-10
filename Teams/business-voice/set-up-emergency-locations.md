---
title: 비상 Microsoft 365 Business Voice 설정
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
f1.keywords:
- NOCSH
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- Teams_Business_Voice
search.appverid: MET150
description: 응급 위치를 설정하는 방법을 Microsoft 365 Business Voice.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9fab5fead952837e2fb272819a600381252bcbf8
ms.sourcegitcommit: 32e3bb588abcbeded2d885483384c06706b280eb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2021
ms.locfileid: "52282535"
---
# <a name="step-1-set-up-a-business-voice-emergency-location"></a><span data-ttu-id="e83fc-103">1단계: 비즈니스 음성 긴급 위치 설정</span><span class="sxs-lookup"><span data-stu-id="e83fc-103">Step 1: Set up a Business Voice emergency location</span></span>

<span data-ttu-id="e83fc-104">응급 위치는 조직의 누군가가 화재, 경찰 또는 구급차와 같은 응급 서비스를 호출할 때 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="e83fc-104">An emergency location is used when someone in your organization calls emergency services such as fire, police, or ambulance.</span></span> <span data-ttu-id="e83fc-105">사용자가 긴급 서비스를 호출하면 조직의 긴급 주소로 구성된 주소가 서비스로 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="e83fc-105">When a person calls an emergency service, the address that's configured as your organization's emergency address is sent to the service.</span></span> <span data-ttu-id="e83fc-106">이 단계에서는 조직의 기본 긴급 위치를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="e83fc-106">This step sets up the primary emergency location for your organization.</span></span> <span data-ttu-id="e83fc-107">이 위치는 나중에 회사의 주 전화 번호와 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="e83fc-107">This location will be associated with your company's main phone number in a later step.</span></span>

<span data-ttu-id="e83fc-108">다른 도시에 홈 오피스 또는 사무실과 같은 여러 위치에 사용자가 있는 경우 추가 긴급 위치를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e83fc-108">If you have users in multiple locations, such as home offices or offices in other cities, you can configure additional emergency locations.</span></span> <span data-ttu-id="e83fc-109">특정 위치 내에서 특정 위치를 구성할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e83fc-109">You can even configure specific places within a location.</span></span> <span data-ttu-id="e83fc-110">장소는 다른 건물, 바닥, 사무실 또는 사용자가 위치에 있을 수 있는 다른 장소일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e83fc-110">Places can be different buildings, floors, offices, or other places where users may be at a location.</span></span> <span data-ttu-id="e83fc-111">비즈니스 음성의 초기 설정을 완료한 후 추가 위치 및 장소를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e83fc-111">Additional locations and places can be added after you complete your initial setup of Business Voice.</span></span>

## <a name="add-an-emergency-location"></a><span data-ttu-id="e83fc-112">긴급 위치 추가</span><span class="sxs-lookup"><span data-stu-id="e83fc-112">Add an emergency location</span></span>

1. <span data-ttu-id="e83fc-113">Microsoft Teams 관리자 센터를 열고 전역 관리자인 사용자와 로그인합니다(일반적으로 등록하는 데 사용한 계정 Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e83fc-113">Open the Microsoft Teams admin center and log in with a user that is a Global admin (this is usually the account you used to sign up for Microsoft 365).</span></span>
1. <span data-ttu-id="e83fc-114">왼쪽 탐색 창에서 위치 <a href="https://admin.teams.microsoft.com/locations" target="_blank"> **긴급**  >  **주소로 이동합니다.**</a></span><span class="sxs-lookup"><span data-stu-id="e83fc-114">In the left navigation pane, go to <a href="https://admin.teams.microsoft.com/locations" target="_blank">**Locations** > **Emergency addresses**</a>.</span></span>
1. <span data-ttu-id="e83fc-115">**추가** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="e83fc-115">Click **Add**.</span></span>
1. <span data-ttu-id="e83fc-116">위치에 대한 이름 및 설명을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="e83fc-116">Enter a name and description for the location.</span></span>
1. <span data-ttu-id="e83fc-117">국가 또는 지역을 선택한 다음 주소를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="e83fc-117">Select the country or region, and then enter the address.</span></span>

   > [!NOTE]
   > <span data-ttu-id="e83fc-118">벨기에, 프랑스, 독일, 아일랜드, 네덜란드 및 스페인의 경우 전화 번호를 Microsoft 365 Office 365 전화 번호를 획득하는 데 사용되는 긴급 위치에 설정된 주소가 전화 번호의 영역 코드와 일치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e83fc-118">In Belgium, France, Germany, Ireland, Netherlands, and Spain, it's important to understand that to successfully activate a phone number in Microsoft 365 or Office 365, the address set up in the emergency location, which is used to acquire the number, must match the phone number's area code.</span></span>

1. <span data-ttu-id="e83fc-119">주소를 찾을 수 없는 경우 주소를 수동으로 편집하려는 경우 수동으로 주소 **편집을 를 입력합니다.**</span><span class="sxs-lookup"><span data-stu-id="e83fc-119">If the address isn't found and you want to manually edit the address, turn on **Edit the address manually**.</span></span>
1. <span data-ttu-id="e83fc-120">**저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="e83fc-120">Click **Save**.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="e83fc-121">다음 단계: 전화 번호 설정</span><span class="sxs-lookup"><span data-stu-id="e83fc-121">Next step: Set up phone numbers</span></span>](set-up-phone-numbers.md)
