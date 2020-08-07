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
description: Microsoft 팀 범위 디렉터리 검색을 사용 하 여 디렉터리의 사용자 지정 된 보기를 제공 하는 방법에 대해 알아봅니다.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: d4152a2ac9ee50372dbc0fdb423d0d85c3026433
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/06/2020
ms.locfileid: "46584077"
---
# <a name="use-microsoft-teams-scoped-directory-search"></a><span data-ttu-id="8f8d9-103">Microsoft Teams 범위 디렉터리 검색 사용</span><span class="sxs-lookup"><span data-stu-id="8f8d9-103">Use Microsoft Teams scoped directory search</span></span>

<span data-ttu-id="8f8d9-104">Microsoft 팀 범위 디렉터리 검색을 통해 조직에서 사용자가 조직의 다른 사용자를 찾고 통신 하는 방법을 제어 하는 가상 경계를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f8d9-104">Microsoft Teams scoped directory search allows organizations to create virtual boundaries that control how users can find and communicate with other users in their organization.</span></span> 

<span data-ttu-id="8f8d9-105">Microsoft 팀은 조직에서 사용자에 게 디렉터리에 대 한 사용자 지정 보기를 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f8d9-105">Microsoft Teams lets organizations provide custom views of the directory to their users.</span></span> <span data-ttu-id="8f8d9-106">Microsoft 팀은 [정보 장벽 정책을](https://docs.microsoft.com/microsoft-365/compliance/information-barriers) 사용 하 여 이러한 사용자 지정 보기를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f8d9-106">Microsoft Teams uses [Information Barrier policies](https://docs.microsoft.com/microsoft-365/compliance/information-barriers) to support these custom views.</span></span> <span data-ttu-id="8f8d9-107">정책을 사용 하도록 설정한 후에는 다른 사용자를 검색 하 여 반환 된 결과 (예: 채팅을 시작 하거나 팀에 구성원을 추가 하는 것)는 구성 된 정책에 따라 범위가 지정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8f8d9-107">Once the policies are enabled, the results returned by searches for other users (for example, to initiate a chat or to add members to a team) will be scoped according to the configured policies.</span></span> <span data-ttu-id="8f8d9-108">범위 검색이 적용 되는 경우 사용자가 팀을 검색 하거나 검색할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8f8d9-108">Users will not be able to search or discover teams when scoped search is in effect.</span></span> 

> [!NOTE]
> <span data-ttu-id="8f8d9-109">Exchange 하이브리드 환경에서이 기능은 온-프레미스 사서함이 아닌 Exchange Online 사서함 에서만 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f8d9-109">In Exchange hybrid environments, this feature only works with Exchange Online mailboxes, and not with on-premises mailboxes.</span></span>

## <a name="when-should-you-use-scoped-directory-searches"></a><span data-ttu-id="8f8d9-110">범위 디렉터리 검색은 언제 사용 해야 하나요?</span><span class="sxs-lookup"><span data-stu-id="8f8d9-110">When should you use scoped directory searches?</span></span>

<span data-ttu-id="8f8d9-111">범위 디렉터리 검색에 도움이 되는 시나리오는 주소록 정책 시나리오와 유사 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f8d9-111">Scenarios that benefit from scoped directory searches are similar to address book policy scenarios.</span></span> <span data-ttu-id="8f8d9-112">예를 들어 다음과 같은 경우 범위 디렉터리 검색을 사용 하는 것이 필요할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f8d9-112">For example, you may want to use scoped directory search in the following situations:</span></span>

- <span data-ttu-id="8f8d9-113">조직의 테넌트 내에 별도로 유지하려는 여러 회사가 있는 경우</span><span class="sxs-lookup"><span data-stu-id="8f8d9-113">Your organization has multiple companies within its tenant that you want to keep separate.</span></span> 
- <span data-ttu-id="8f8d9-114">학교에서 교사와 학생 간의 채팅을 제한하려고 하는 경우</span><span class="sxs-lookup"><span data-stu-id="8f8d9-114">Your school wants to limit chats between faculty and students.</span></span> 
 
<span data-ttu-id="8f8d9-115">주소록 정책을 사용 하는 방법에 대 한 자세한 [내용은 Exchange Online에서 정보 장벽 정책을](https://docs.microsoft.com/microsoft-365/compliance/information-barriers)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8f8d9-115">To learn how to use address book policies, read [Information Barrier policies in Exchange Online](https://docs.microsoft.com/microsoft-365/compliance/information-barriers).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8f8d9-116">주소록 정책은 사용자의 가상 구분을 디렉터리 관점에서 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f8d9-116">Address book policies provide only a virtual separation of users from directory perspective.</span></span> <span data-ttu-id="8f8d9-117">사용자는 전체 전자 메일 주소를 제공 하 여 계속 해 서 다른 사람들과 통신을 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f8d9-117">Users can still initiate communications with others by providing complete email addresses.</span></span> <span data-ttu-id="8f8d9-118">또한 신규 또는 업데이트 된 주소록 정책을 적용 하기 전에 이미 캐싱된 사용자 데이터는 최대 30 일 동안 사용자가 사용할 수 있도록 유지 된다는 점에 유의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f8d9-118">It is also important to note that any user data that had already been cached, prior to the enforcement of new or updated address book policies, will remain available to users for up to 30 days.</span></span>

## <a name="turn-on-scoped-directory-search"></a><span data-ttu-id="8f8d9-119">범위 디렉터리 검색 설정</span><span class="sxs-lookup"><span data-stu-id="8f8d9-119">Turn on scoped directory search</span></span>

1. <span data-ttu-id="8f8d9-120">정보 장벽 정책을 사용 하 여 조직을 가상 하위 그룹으로 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f8d9-120">Use Information Barrier policies to configure your organization into virtual subgroups.</span></span> <span data-ttu-id="8f8d9-121">자세한 내용은 [정보 장벽 정책 정의](https://docs.microsoft.com/microsoft-365/compliance/information-barriers-policies)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8f8d9-121">For more information, see [Define Information Barrier policies](https://docs.microsoft.com/microsoft-365/compliance/information-barriers-policies).</span></span>

2. <span data-ttu-id="8f8d9-122">Microsoft 팀 관리 센터에서 **조직 전체 설정**  >  **팀 설정을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f8d9-122">In the Microsoft Teams admin center, select **Org-wide settings** > **Teams settings**.</span></span>

3. <span data-ttu-id="8f8d9-123">**검색**에서 **Exchange 주소록 정책 (abp)을 사용 하는 팀의 범위 디렉터리 검색** **옆에 있는 토글을**켭니다.</span><span class="sxs-lookup"><span data-stu-id="8f8d9-123">Under **Search**, next to **Scope directory search in Teams using an Exchange address book policy (ABP)**, turn the toggle **On**.</span></span>

    ![Microsoft 팀 관리 센터의 범위 디렉터리 검색](media/teams-scoped-directory-search-image1.png)


> [!IMPORTANT]
> <span data-ttu-id="8f8d9-125">이 변경 사항을 복제 하는 데 몇 시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f8d9-125">This change can take a few hours to replicate.</span></span>
