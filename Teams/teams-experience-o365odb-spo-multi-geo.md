---
title: Microsoft 365 또는 Office 365 OneDrive 및 SharePoint Online 다중 테 넌 시/지역에서의 팀 환경 사용
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: snigdhav
audience: admin
description: 이 문서에서는 Microsoft 365 또는 Office 365 OneDrive 및 SharePoint Online 다중 지리 테 넌 시 팀을 사용 하는 방법에 대해 알아봅니다.
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
ms.openlocfilehash: 1fdfd99494b8f65c448a2b1183a183b8cf7477af
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/06/2020
ms.locfileid: "46583245"
---
<a name="teams-experience-in-a-microsoft-365-or-office-365-onedrive-and-sharepoint-online-multi-geo-enabled-tenancy"></a><span data-ttu-id="ab65b-103">Microsoft 365 또는 Office 365 OneDrive 및 SharePoint Online 다중 테 넌 시/지역에서의 팀 환경 사용</span><span class="sxs-lookup"><span data-stu-id="ab65b-103">Teams experience in a Microsoft 365 or Office 365 OneDrive and SharePoint Online Multi-Geo-enabled tenancy</span></span>
===========================================

<span data-ttu-id="ab65b-104">Microsoft 팀은 Microsoft 365 및 Office 365에서 팀워크 용 허브가 그룹 채팅 소프트웨어입니다.</span><span class="sxs-lookup"><span data-stu-id="ab65b-104">Microsoft Teams is group chat software, the hub for teamwork in Microsoft 365 and Office 365.</span></span> <span data-ttu-id="ab65b-105">SharePoint Online 및 비즈니스용 OneDrive와 함께 Microsoft 365 Groups 서비스에서 파일 환경을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab65b-105">It is powered by the Microsoft 365 Groups service along with SharePoint Online and OneDrive for Business for its files experience.</span></span> <span data-ttu-id="ab65b-106">테 넌 트가 북미, 유럽, 호주 등의 여러 지리적 위치로 확장 되는 비즈니스용 OneDrive/SharePoint Online의 경우 기본 파일 환경이 다중 지역 인지 때문에 파일 공동 작업을 통해 팀이 다중 지역으로 인식 될 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab65b-106">In a OneDrive for Business/SharePoint Online Multi-Geo tenancy, in which the tenant is extended to many geographic locations such as North America, Europe, and Australia, the underlying files experience is Multi-Geo aware, so the Teams experience with file collaboration is also Multi-Geo aware.</span></span> <span data-ttu-id="ab65b-107">이는 원시 파일 환경에서 여러 Geos에 의해 호스팅되는 파일을 팀에 게 제공 하는 주요 최고의 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="ab65b-107">This is a key leading-edge capability for Teams to surface files hosted across multiple Geos in its native files experience.</span></span>

<span data-ttu-id="ab65b-108">예를 들어 유럽 지역, 영국, 중앙 Geo 인 Contoso의 테 넌 트에서 유럽 위성 사용자는 파일 탭의 왼쪽 창에 있는 OneDrive 파일을 볼 수 있지만,이는 유럽 데이터 위치에서 호스팅되므로 미국에는 테 넌 트의 중앙 위치를 나타내는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="ab65b-108">For example, in a Contoso tenancy with Europe as a satellite Geo and North America as the central Geo, a European satellite user will see his or her OneDrive files under the Files tab in left pane, although the files are hosted in the Europe data location and the United States is the tenant’s central location.</span></span> <span data-ttu-id="ab65b-109">또한 사용자는 최근 보기 블레이드에서 최근에 사용한 파일에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab65b-109">Also, the user can access the most recently used files under the Recent view blade.</span></span> <span data-ttu-id="ab65b-110">최근 파일에는 다른 Geos의 사용자가 사용자와 공유 하는 파일이 포함 되어 있을 수 있으며, 테 넌 트가 확장 된 다른 지리적 위치에서 마스터 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab65b-110">Recent files may include files shared with the user from users in other Geos and might be mastered in other Geo locations that the tenant is extended to.</span></span> 

<span data-ttu-id="ab65b-111">지정 된 팀의 그룹 사이트도 다중 지역에서 인식 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ab65b-111">A given Team’s group site is also Multi-Geo aware.</span></span> <span data-ttu-id="ab65b-112">즉, 유럽 위성 사용자가 팀을 만드는 경우 해당 그룹 사이트가 유럽 위치에 만들어지고 해당 팀 그룹과 연결 된 파일이 해당 위치에 그대로 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ab65b-112">That is, if a European satellite user is creating a Team, the corresponding Groups site will be created in the Europe location and the files associated with that Team group will be kept at rest in that location.</span></span> <span data-ttu-id="ab65b-113">새 파일을 업로드 하거나 파일을 편집 하는 등의 모든 후속 환경은 해당 파일에 대 한 데이터 영주권의 약속을 유지 하면서 해당 유럽 위치를 대상으로 지정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ab65b-113">Any subsequent experiences, such as uploading a new file or editing the file, will be targeted to that European location, keeping the promise of data residency for those files.</span></span> <span data-ttu-id="ab65b-114">이는 기본 foundation Microsoft 365 그룹이 다중 지리적으로 인식 되는 것이 가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab65b-114">This is all made possible by the underlying foundation Microsoft 365 Groups becoming Multi-Geo aware.</span></span>

<span data-ttu-id="ab65b-115">다중 지역 거주자는 단일 전역 테 넌 트 이므로, @ 멘 션은 위성 사용자가 거주 하는 위치에 관계 없이 전세계의 동료를 볼 수 있게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ab65b-115">Because a Multi-Geo tenancy is a single global tenant, during @ mentions satellite users will be able to see their colleagues from across the globe, no matter where they reside.</span></span> 

<span data-ttu-id="ab65b-116">팀 경험 내에 있는 채팅 및 모임 메신저 대화 노트의 대화는 다중 지역 인식 되지 않으며, 테 넌 트의 중앙 위치 내 에서만 유지 된다는 점에 유의 하세요.</span><span class="sxs-lookup"><span data-stu-id="ab65b-116">Note that conversations in chats and meeting IM notes within the Teams experience are not Multi-Geo aware and are all kept only inside the central location of the tenant.</span></span> <span data-ttu-id="ab65b-117">일반적으로 채팅 대화는 데이터 영주권 요구 사항에는 적용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ab65b-117">Typically, chat conversations aren’t applied to data residency needs.</span></span>

<span data-ttu-id="ab65b-118">다중 지역에 대 한 자세한 내용은 [Microsoft 다중 지역 기능 페이지](https://aka.ms/multi-geo)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ab65b-118">For more information about Multi-Geo, refer to the [Microsoft Multi-Geo capabilities page](https://aka.ms/multi-geo).</span></span>