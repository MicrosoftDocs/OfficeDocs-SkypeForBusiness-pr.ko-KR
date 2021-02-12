---
title: Microsoft 365 다중 지역 사용 환경의 Teams 환경
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: snigdhav
audience: admin
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
- SPO_Content
ms.custom: seo-marvel-apr2020
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
description: 이 문서에서는 Microsoft 365 다중 지역 지원 환경에서 Teams를 사용하는 방법을 배워보게 됩니다.
ms.openlocfilehash: 43abe221c6159e6dfed1705f5cbc4839c1ce57db
ms.sourcegitcommit: 93d84e172cb4b19acde4b8bae9b77efe96c44c00
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/05/2021
ms.locfileid: "50122248"
---
# <a name="teams-experience-in-a-microsoft-365-multi-geo-enabled-tenancy"></a><span data-ttu-id="6d153-103">Microsoft 365 다중 지역 지원 테넌트의 Teams 환경</span><span class="sxs-lookup"><span data-stu-id="6d153-103">Teams experience in a Microsoft 365 Multi-Geo-enabled tenancy</span></span>

<span data-ttu-id="6d153-104">Microsoft Teams는 Microsoft 365 및 Office 365의 팀워크 허브인 그룹 채팅 소프트웨어입니다.</span><span class="sxs-lookup"><span data-stu-id="6d153-104">Microsoft Teams is group chat software, the hub for teamwork in Microsoft 365 and Office 365.</span></span> <span data-ttu-id="6d153-105">파일 환경을 위해 SharePoint Online 및 비즈니스용 OneDrive와 함께 Microsoft 365 그룹 서비스를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="6d153-105">It's powered by the Microsoft 365 Groups service along with SharePoint Online and OneDrive for Business for its files experience.</span></span> <span data-ttu-id="6d153-106">테넌트가 북아메리카, 유럽 및 오스트레일리아와 같은 여러 지리적 위치로 확장되는 비즈니스용 OneDrive/SharePoint Online 다중 지역 테넌트에서, 파일 공동 작업의 Teams 환경은 다중 지역 인식입니다.</span><span class="sxs-lookup"><span data-stu-id="6d153-106">In a OneDrive for Business/SharePoint Online Multi-Geo tenancy, in which the tenant is extended to many geographic locations such as North America, Europe, and Australia, the underlying files experience is Multi-Geo-aware, so the Teams experience with file collaboration is also Multi-Geo-aware.</span></span> <span data-ttu-id="6d153-107">이 기능은 Teams에서 네이티브 파일 환경의 여러 지리적 위치로 호스트되는 파일을 표면화할 수 있는 핵심 첨단 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="6d153-107">This functionality is a key leading-edge capability for Teams to surface files that are hosted across multiple Geos in its native files experience.</span></span> <span data-ttu-id="6d153-108">여기에는 OneNote 및 Wiki 파일도 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="6d153-108">This also includes OneNote and Wiki files.</span></span>

<span data-ttu-id="6d153-109">예를 들어 유럽을 위성 지역으로, 북아메리카를 중앙 지역으로 하는 Contoso 테넌트에서 유럽  위성 사용자는 파일이 유럽 데이터 위치에서 호스트되는 경우 미국은 테넌트의 중앙 위치인 경우 왼쪽 창의 파일 탭 아래에 OneDrive 파일을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6d153-109">For example, in a Contoso tenancy with Europe as a satellite Geo and North America as the central Geo, a European satellite user will see their OneDrive files under the **Files** tab in left pane, although the files are hosted in the Europe data location and the United States is the tenant’s central location.</span></span> <span data-ttu-id="6d153-110">또한 사용자는 최근 보기 블레이드에서 가장 최근에 사용한 파일에 **액세스할** 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6d153-110">Also, the user can access the most recently used files under the **Recent** view blade.</span></span> <span data-ttu-id="6d153-111">최근 파일에는 다른 지리적 위치에 있는 사용자로부터 공유된 파일이 포함되어 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6d153-111">Recent files may include files shared from users in other geo locations.</span></span> 

<span data-ttu-id="6d153-112">주어진 팀의 SharePoint 사이트도 다중 지역 인식입니다.</span><span class="sxs-lookup"><span data-stu-id="6d153-112">A given Team’s SharePoint site is also Multi-Geo-aware.</span></span> <span data-ttu-id="6d153-113">즉, 유럽 위성 사용자가 팀을 만드는 경우 해당 SharePoint 사이트가 유럽 위치에 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="6d153-113">That is, if a European satellite user is creating a Team, the corresponding SharePoint site will be created in the Europe location.</span></span> <span data-ttu-id="6d153-114">해당 팀과 연결된 파일은 해당 위치에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="6d153-114">The files that are associated with that Team will be kept at rest in that location.</span></span> <span data-ttu-id="6d153-115">새 파일을 업로드하거나 파일을 편집하는 등의 후속 환경은 해당 유럽 위치에 저장되어 해당 파일에 대한 데이터 주체의 약속을 유지하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6d153-115">Any subsequent experiences, such as uploading a new file or editing the file, will be stored in that European location, keeping the promise of data residency for those files.</span></span>

<span data-ttu-id="6d153-116">다중 지역 테넌트는 단일 글로벌 테넌트이기 때문에 @ 언급 중에 위성 사용자는 어디에 있든 전 세계 동료를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6d153-116">Because a Multi-Geo tenancy is a single global tenant, during @ mentions satellite users will be able to see their colleagues from across the globe, no matter where they are.</span></span>

<span data-ttu-id="6d153-117">Teams 환경 내의 채팅, 채널 메시지 및 모임 IM 메모/채팅의 대화는 다중 지역 인식이 아니며 모두 테넌트의 중앙 위치 내에만 보관됩니다.</span><span class="sxs-lookup"><span data-stu-id="6d153-117">Conversations in chats, channels messages, and meeting IM notes/chats within the Teams experience aren't Multi-Geo-aware and are all kept only inside the central location of the tenant.</span></span> <span data-ttu-id="6d153-118">일반적으로 채팅 대화는 데이터 레지전시 요구에 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6d153-118">Typically, chat conversations aren’t applied to data residency needs.</span></span> <span data-ttu-id="6d153-119">자세한 내용은 [Microsoft Teams의 데이터 위치를 참조하세요.](location-of-data-in-teams.md)</span><span class="sxs-lookup"><span data-stu-id="6d153-119">For more information, see [Location of data in Microsoft Teams](location-of-data-in-teams.md).</span></span>

<span data-ttu-id="6d153-120">다중 지역에 대한 자세한 내용은 Microsoft 다중 지역 기능 페이지를 [참조하세요.](https://aka.ms/multi-geo)</span><span class="sxs-lookup"><span data-stu-id="6d153-120">For more info about Multi-Geo, refer to the [Microsoft Multi-Geo capabilities page](https://aka.ms/multi-geo).</span></span>
