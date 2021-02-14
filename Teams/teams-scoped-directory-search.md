---
title: Microsoft Teams 범위 디렉터리 검색 사용
author: SerdarSoysal
ms.author: serdars
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
description: Microsoft Teams 범위 디렉터리 검색을 사용하여 디렉터리의 사용자 지정된 보기를 제공하는 방법을 배워 보십시오.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: e4f478bba8c396f0f20b95f69f56c2ded556224d
ms.sourcegitcommit: 2300595db7779da7a127ae9ee16e474452df02d3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/07/2021
ms.locfileid: "49779932"
---
# <a name="use-microsoft-teams-scoped-directory-search"></a><span data-ttu-id="85d8a-103">Microsoft Teams 범위 디렉터리 검색 사용</span><span class="sxs-lookup"><span data-stu-id="85d8a-103">Use Microsoft Teams scoped directory search</span></span>

<span data-ttu-id="85d8a-104">Microsoft Teams 범위 디렉터리 검색을 사용하면 조직에서 사용자가 조직의 다른 사용자를 찾고 통신하는 방법을 제어하는 가상 경계를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85d8a-104">Microsoft Teams scoped directory search allows organizations to create virtual boundaries that control how users can find and communicate with other users in their organization.</span></span> 

<span data-ttu-id="85d8a-105">Microsoft Teams를 사용하면 조직에서 사용자에게 디렉터리의 사용자 지정 보기를 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85d8a-105">Microsoft Teams lets organizations provide custom views of the directory to their users.</span></span> <span data-ttu-id="85d8a-106">Microsoft Teams는 정보 장벽 [정책을 사용하여](https://docs.microsoft.com/microsoft-365/compliance/information-barriers) 이러한 사용자 지정 보기를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="85d8a-106">Microsoft Teams uses [Information Barrier policies](https://docs.microsoft.com/microsoft-365/compliance/information-barriers) to support these custom views.</span></span> <span data-ttu-id="85d8a-107">정책을 사용하도록 설정하면 다른 사용자를 검색하여 반환된 결과(예: 채팅을 시작하거나 팀에 구성원을 추가하는 경우)는 구성된 정책에 따라 범위가 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="85d8a-107">Once the policies are enabled, the results returned by searches for other users (for example, to initiate a chat or to add members to a team) will be scoped according to the configured policies.</span></span> <span data-ttu-id="85d8a-108">범위가 지정한 검색이 적용된 경우 사용자는 팀을 검색하거나 검색할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="85d8a-108">Users will not be able to search or discover teams when scoped search is in effect.</span></span> 

> [!NOTE]
> <span data-ttu-id="85d8a-109">Exchange 하이브리드 환경에서 이 기능은 Exchange Online 사서함에서만 작동하며, 이 기능은 Exchange Online 사서함에서만 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="85d8a-109">In Exchange hybrid environments, this feature only works with Exchange Online mailboxes, and not with on-premises mailboxes.</span></span>

## <a name="when-should-you-use-scoped-directory-searches"></a><span data-ttu-id="85d8a-110">범위가 지정한 디렉터리 검색을 언제 사용해야 하나요?</span><span class="sxs-lookup"><span data-stu-id="85d8a-110">When should you use scoped directory searches?</span></span>

<span data-ttu-id="85d8a-111">범위가 지정한 디렉터리 검색의 이점이 있는 시나리오는 주소 책 정책 시나리오와 유사합니다.</span><span class="sxs-lookup"><span data-stu-id="85d8a-111">Scenarios that benefit from scoped directory searches are similar to address book policy scenarios.</span></span> <span data-ttu-id="85d8a-112">예를 들어 다음과 같은 상황에서 범위가 지정된 디렉터리 검색을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85d8a-112">For example, you may want to use scoped directory search in the following situations:</span></span>

- <span data-ttu-id="85d8a-113">조직의 테넌트 내에 별도로 유지하려는 여러 회사가 있는 경우</span><span class="sxs-lookup"><span data-stu-id="85d8a-113">Your organization has multiple companies within its tenant that you want to keep separate.</span></span> 
- <span data-ttu-id="85d8a-114">학교에서 교사와 학생 간의 채팅을 제한하려고 하는 경우</span><span class="sxs-lookup"><span data-stu-id="85d8a-114">Your school wants to limit chats between faculty and students.</span></span> 
 
<span data-ttu-id="85d8a-115">주소부 정책을 사용하는 방법에 대한 자세한 내용은 [Exchange Online에서 정보 장벽 정책을 읽어보아야 합니다.](https://docs.microsoft.com/microsoft-365/compliance/information-barriers)</span><span class="sxs-lookup"><span data-stu-id="85d8a-115">To learn how to use address book policies, read [Information Barrier policies in Exchange Online](https://docs.microsoft.com/microsoft-365/compliance/information-barriers).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="85d8a-116">주소부 정책은 디렉터리 관점에서 사용자의 가상 분리만 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="85d8a-116">Address book policies provide only a virtual separation of users from directory perspective.</span></span> <span data-ttu-id="85d8a-117">또한 새 주소 또는 업데이트된 주소부 정책을 적용하기 전에 이미 캐시된 모든 사용자 데이터는 최대 30일 동안 사용자에게 제공될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85d8a-117">It is also important to note that any user data that had already been cached, prior to the enforcement of new or updated address book policies, will remain available to users for up to 30 days.</span></span>

## <a name="turn-on-scoped-directory-search"></a><span data-ttu-id="85d8a-118">범위가 지정한 디렉터리 검색 켜기</span><span class="sxs-lookup"><span data-stu-id="85d8a-118">Turn on scoped directory search</span></span>

1. <span data-ttu-id="85d8a-119">정보 장벽 정책을 사용하여 가상 하위 조직으로 조직을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="85d8a-119">Use Information Barrier policies to configure your organization into virtual subgroups.</span></span> <span data-ttu-id="85d8a-120">자세한 내용은 정보 장벽 정책 [정의를 참조하세요.](https://docs.microsoft.com/microsoft-365/compliance/information-barriers-policies)</span><span class="sxs-lookup"><span data-stu-id="85d8a-120">For more information, see [Define Information Barrier policies](https://docs.microsoft.com/microsoft-365/compliance/information-barriers-policies).</span></span>

2. <span data-ttu-id="85d8a-121">Microsoft Teams 관리 센터에서 **전체 설정** Teams 설정을  >  **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="85d8a-121">In the Microsoft Teams admin center, select **Org-wide settings** > **Teams settings**.</span></span>

3. <span data-ttu-id="85d8a-122">검색 **아래에서** **ABP(Exchange** 주소 책 정책)를 사용하여 Teams의 범위 디렉터리 검색 옆에 있는 토글을 **켜십시오.**</span><span class="sxs-lookup"><span data-stu-id="85d8a-122">Under **Search**, next to **Scope directory search in Teams using an Exchange address book policy (ABP)**, turn the toggle **On**.</span></span>

    ![Microsoft Teams 관리 센터의 범위가 지정된 디렉터리 검색](media/teams-scoped-directory-search-image1.png)


> [!IMPORTANT]
> <span data-ttu-id="85d8a-124">이 변경을 복제하는 데 몇 시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85d8a-124">This change can take a few hours to replicate.</span></span>
