---
title: Teams 환경의 Microsoft 365 환경
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
description: 이 문서에서는 다중 지역 지원 환경에서 Teams Microsoft 365 방법을 알아보고 있습니다.
ms.openlocfilehash: a1b86cf83a0eabde81331e5311561aa1600d3c7e
ms.sourcegitcommit: ca2230a981a1e3c03437d1ecb8727d66ad6967f9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2021
ms.locfileid: "51760541"
---
# <a name="teams-experience-in-a-microsoft-365-multi-geo-enabled-tenancy"></a><span data-ttu-id="74da2-103">Teams 사용 테넌트에서 Microsoft 365 환경 제공</span><span class="sxs-lookup"><span data-stu-id="74da2-103">Teams experience in a Microsoft 365 Multi-Geo-enabled tenancy</span></span>

<span data-ttu-id="74da2-104">Microsoft Teams 그룹 채팅 소프트웨어, 팀워크 및 Microsoft 365 허브 Office 365.</span><span class="sxs-lookup"><span data-stu-id="74da2-104">Microsoft Teams is group chat software, the hub for teamwork in Microsoft 365 and Office 365.</span></span> <span data-ttu-id="74da2-105">이 서비스는 Microsoft 365 Online과 함께 SharePoint 그룹 서비스를 통해 비즈니스용 OneDrive 환경을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="74da2-105">It's powered by the Microsoft 365 Groups service along with SharePoint Online and OneDrive for Business for its files experience.</span></span> <span data-ttu-id="74da2-106">테넌트가 북아메리카, 유럽 및 오스트레일리아와 같은 여러 지리적 위치로 확장되는 비즈니스용 OneDrive SharePoint Online Multi-Geo/Teams 테넌트에서 파일 공동 작업 환경도 다중 지역 인식입니다.</span><span class="sxs-lookup"><span data-stu-id="74da2-106">In a OneDrive for Business/SharePoint Online Multi-Geo tenancy, in which the tenant is extended to many geographic locations such as North America, Europe, and Australia, the underlying files experience is Multi-Geo-aware, so the Teams experience with file collaboration is also Multi-Geo-aware.</span></span> <span data-ttu-id="74da2-107">이 기능은 네이티브 파일 환경의 여러 Teams 호스트되는 파일을 표면에 저장하기 위한 핵심 첨단 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="74da2-107">This functionality is a key leading-edge capability for Teams to surface files that are hosted across multiple Geos in its native files experience.</span></span> <span data-ttu-id="74da2-108">여기에는 OneNote 및 위키 파일이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="74da2-108">This also includes OneNote and Wiki files.</span></span>

<span data-ttu-id="74da2-109">예를 들어 유럽과의 Contoso 테넌트에서 유럽을 중앙 지역으로, 북아메리카를 중앙 지오로  지정하면 유럽 위성 사용자가 왼쪽 OneDrive 파일 탭 아래에 해당 파일 파일을 볼 수 있습니다. 이 파일은 유럽 데이터 위치에 호스트되어 있으며 미국은 테넌트의 중앙 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="74da2-109">For example, in a Contoso tenancy with Europe as a satellite Geo and North America as the central Geo, a European satellite user will see their OneDrive files under the **Files** tab in left pane, although the files are hosted in the Europe data location and the United States is the tenant’s central location.</span></span> <span data-ttu-id="74da2-110">또한 사용자는 최근 보기 블레이드에서 가장 최근에 사용한 파일에 **액세스할 수** 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74da2-110">Also, the user can access the most recently used files under the **Recent** view blade.</span></span> <span data-ttu-id="74da2-111">최근 파일에는 다른 지리적 위치에 있는 사용자로부터 공유된 파일이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74da2-111">Recent files may include files shared from users in other geo locations.</span></span> 

<span data-ttu-id="74da2-112">주어진 팀의 SharePoint 사이트도 다중 지역 인식입니다.</span><span class="sxs-lookup"><span data-stu-id="74da2-112">A given Team’s SharePoint site is also Multi-Geo-aware.</span></span> <span data-ttu-id="74da2-113">즉, 유럽 위성 사용자가 팀을 만드는 경우 해당 SharePoint 사이트가 유럽 위치에 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="74da2-113">That is, if a European satellite user is creating a Team, the corresponding SharePoint site will be created in the Europe location.</span></span> <span data-ttu-id="74da2-114">해당 팀과 연결된 파일은 해당 위치에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="74da2-114">The files that are associated with that Team will be kept at rest in that location.</span></span> <span data-ttu-id="74da2-115">새 파일을 업로드하거나 파일을 편집하는 등의 후속 환경은 해당 유럽 위치에 저장되어 해당 파일에 대한 데이터 잔재를 약속합니다.</span><span class="sxs-lookup"><span data-stu-id="74da2-115">Any subsequent experiences, such as uploading a new file or editing the file, will be stored in that European location, keeping the promise of data residency for those files.</span></span>

<span data-ttu-id="74da2-116">다중 지역 테넌트는 단일 글로벌 테넌트이기 때문에 위성 사용자가 어디에 있든 전 세계에서 동료를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74da2-116">Because a Multi-Geo tenancy is a single global tenant, during @ mentions satellite users will be able to see their colleagues from across the globe, no matter where they are.</span></span>

<span data-ttu-id="74da2-117">채팅, 채널 메시지, 모임 IM 노트/채팅 Teams 환경 내의 대화는 다중 지역 인식이 아니며 모두 테넌트의 중앙 위치 내에만 보관됩니다.</span><span class="sxs-lookup"><span data-stu-id="74da2-117">Conversations in chats, channels messages, and meeting IM notes/chats within the Teams experience aren't Multi-Geo-aware and are all kept only inside the central location of the tenant.</span></span> <span data-ttu-id="74da2-118">일반적으로 채팅 대화는 데이터 레지스전시 요구에 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="74da2-118">Typically, chat conversations aren’t applied to data residency needs.</span></span> <span data-ttu-id="74da2-119">자세한 내용은 의 데이터 위치를 [Microsoft Teams.](location-of-data-in-teams.md)</span><span class="sxs-lookup"><span data-stu-id="74da2-119">For more information, see [Location of data in Microsoft Teams](location-of-data-in-teams.md).</span></span>

<span data-ttu-id="74da2-120">다중 지역 지원은 Teams [로드맵에](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=70783)Microsoft 365 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74da2-120">Multi-Geo support for Teams is on the [Microsoft 365 roadmap](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=70783).</span></span>

<span data-ttu-id="74da2-121">Multi-Geo에 대한 자세한 내용은 [Microsoft Multi-Geo 기능 페이지를 참조하세요.](https://aka.ms/multi-geo)</span><span class="sxs-lookup"><span data-stu-id="74da2-121">For more info about Multi-Geo, refer to the [Microsoft Multi-Geo capabilities page](https://aka.ms/multi-geo).</span></span>
