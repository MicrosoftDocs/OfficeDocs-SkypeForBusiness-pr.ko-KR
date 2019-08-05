---
title: Microsoft 팀 범위 디렉터리 검색 사용
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 06/21/2019
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: sbhatta
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
description: Microsoft 팀 범위 디렉터리 검색을 사용 하 여 디렉터리의 사용자 지정 된 보기를 제공 하는 방법에 대해 알아봅니다.
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 068a37af62ea31c53caed8c9dc22feec6fd60ec6
ms.sourcegitcommit: bd9b29cdaa183b1f5cc2d643a5a2d231a56a2c3f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "36184799"
---
# <a name="use-microsoft-teams-scoped-directory-search"></a><span data-ttu-id="59449-103">Microsoft 팀 범위 디렉터리 검색 사용</span><span class="sxs-lookup"><span data-stu-id="59449-103">Use Microsoft Teams scoped directory search</span></span>

<span data-ttu-id="59449-104">Microsoft 팀 범위 디렉터리 검색을 통해 조직에서 사용자가 조직의 다른 사용자를 찾고 통신 하는 방법을 제어 하는 가상 경계를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="59449-104">Microsoft Teams scoped directory search allows organizations to create virtual boundaries that control how users can find and communicate with other users in their organization.</span></span> 

<span data-ttu-id="59449-105">Microsoft 팀은 조직에서 사용자에 게 디렉터리에 대 한 사용자 지정 보기를 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="59449-105">Microsoft Teams lets organizations provide custom views of the directory to their users.</span></span> <span data-ttu-id="59449-106">Microsoft 팀은 [Exchange 주소록 정책을](https://docs.microsoft.com/exchange/address-books/address-book-policies/address-book-policies) 사용 하 여 이러한 사용자 지정 보기를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="59449-106">Microsoft Teams uses [Exchange address book policies](https://docs.microsoft.com/exchange/address-books/address-book-policies/address-book-policies) to support these custom views.</span></span> <span data-ttu-id="59449-107">정책을 사용 하도록 설정한 후에는 다른 사용자를 검색 하 여 반환 된 결과 (예: 채팅을 시작 하거나 팀에 구성원을 추가 하는 것)는 구성 된 정책에 따라 범위가 지정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="59449-107">Once the policies are enabled, the results returned by searches for other users (for example, to initiate a chat or to add members to a team) will be scoped according to the configured policies.</span></span> <span data-ttu-id="59449-108">범위 검색이 적용 되는 경우 사용자가 팀을 검색 하거나 검색할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="59449-108">Users will not be able to search or discover teams when scoped search is in effect.</span></span> 

## <a name="when-should-you-use-scoped-directory-searches"></a><span data-ttu-id="59449-109">범위 디렉터리 검색은 언제 사용 해야 하나요?</span><span class="sxs-lookup"><span data-stu-id="59449-109">When should you use scoped directory searches?</span></span>

<span data-ttu-id="59449-110">범위 디렉터리 검색에 도움이 되는 시나리오는 주소록 정책 시나리오와 유사 합니다.</span><span class="sxs-lookup"><span data-stu-id="59449-110">Scenarios that benefit from scoped directory searches are similar to address book policy scenarios.</span></span> <span data-ttu-id="59449-111">예를 들어 다음과 같은 경우 범위 디렉터리 검색을 사용 하는 것이 필요할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="59449-111">For example, you may want to use scoped directory search in the following situations:</span></span>

- <span data-ttu-id="59449-112">조직에 테 넌 트 내에 별도로 유지 하려는 회사가 여러 개 있습니다.</span><span class="sxs-lookup"><span data-stu-id="59449-112">Your organization has multiple companies within its tenant that you want to keep separate.</span></span> 
- <span data-ttu-id="59449-113">학교에서 교사와 학생 간의 채팅을 제한 하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="59449-113">Your school wants to limit chats between faculty and students.</span></span> 
 
<span data-ttu-id="59449-114">주소록 정책을 사용 하는 방법에 대 한 자세한 내용은 [Exchange Online에서 주소록 정책을](https://docs.microsoft.com/exchange/address-books/address-book-policies/address-book-policies)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="59449-114">To learn how to use address book policies, read [Address book policies in Exchange Online](https://docs.microsoft.com/exchange/address-books/address-book-policies/address-book-policies).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="59449-115">주소록 정책은 사용자의 가상 구분을 디렉터리 관점에서 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="59449-115">Address book policies provide only a virtual separation of users from directory perspective.</span></span> <span data-ttu-id="59449-116">사용자는 전체 전자 메일 주소를 제공 하 여 계속 해 서 다른 사람들과 통신을 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="59449-116">Users can still initiate communications with others by providing complete email addresses.</span></span> <span data-ttu-id="59449-117">또한 신규 또는 업데이트 된 주소록 정책을 적용 하기 전에 이미 캐싱된 사용자 데이터는 최대 30 일 동안 사용자가 사용할 수 있도록 유지 된다는 점에 유의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="59449-117">It is also important to note that any user data that had already been cached, prior to the enforcement of new or updated address book policies, will remain available to users for up to 30 days.</span></span>

## <a name="turn-on-scoped-directory-search"></a><span data-ttu-id="59449-118">범위 디렉터리 검색 설정</span><span class="sxs-lookup"><span data-stu-id="59449-118">Turn on scoped directory search</span></span>

1. <span data-ttu-id="59449-119">주소록 정책을 사용 하 여 조직을 가상 하위 그룹으로 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="59449-119">Use address book policies to configure your organization into virtual subgroups.</span></span> <span data-ttu-id="59449-120">자세한 내용은 [주소록 정책에 대 한 절차](https://docs.microsoft.com/exchange/address-books/address-book-policies/address-book-policies)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="59449-120">For more information, see [Procedures for address book policies](https://docs.microsoft.com/exchange/address-books/address-book-policies/address-book-policies).</span></span>

2. <span data-ttu-id="59449-121">Microsoft 팀 관리 센터에서 **조직 전체 설정** > **팀 설정을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="59449-121">In the Microsoft Teams admin center, select **Org-wide settings** > **Teams settings**.</span></span>

3. <span data-ttu-id="59449-122">**검색**에서 **Exchange 주소록 정책 (apb)을 사용 하는 팀의 범위 디렉터리 검색**옆에 있는 토글을 켭니다 \*\*\*\*.</span><span class="sxs-lookup"><span data-stu-id="59449-122">Under **Search**, next to **Scope directory search in Teams using an Exchange address book policy (APB)**, turn the toggle **On**.</span></span>

    ![Microsoft 팀 관리 센터의 범위 디렉터리 검색](media/teams-scoped-directory-search-image1.png)



