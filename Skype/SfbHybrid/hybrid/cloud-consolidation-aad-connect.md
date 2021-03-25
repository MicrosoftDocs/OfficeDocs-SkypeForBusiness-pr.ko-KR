---
title: 여러 포리스트를 포함하도록 AAD Connect를 업데이트
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
ms.topic: article
ms.prod: skype-for-business-itpro
search.appverid: MET150
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
audience: ITPro
f1.keywords:
- NOCSH
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
description: 이 부록에는 Teams 및 비즈니스용 Skype에 대한 클라우드 통합의 일부로 두 개 이상의 포리스트를 포함하기 위해 AAD Connect를 업데이트하는 자세한 단계가 포함되어 있습니다.
ms.openlocfilehash: 19b761f3b64caf7afad7d37a51ae391e23d6b5ef
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120377"
---
# <a name="update-aad-connect-to-include-more-than-one-forest"></a><span data-ttu-id="2f0b6-103">여러 포리스트를 포함하도록 AAD Connect를 업데이트</span><span class="sxs-lookup"><span data-stu-id="2f0b6-103">Update AAD Connect to include more than one forest</span></span>

<span data-ttu-id="2f0b6-104">Azure AD Connect는 여러 [포리스트에서 동기화를 지원합니다.](/azure/active-directory/connect/active-directory-aadconnect-topologies)</span><span class="sxs-lookup"><span data-stu-id="2f0b6-104">Azure AD Connect supports [syncing from multiple forests](/azure/active-directory/connect/active-directory-aadconnect-topologies).</span></span> <span data-ttu-id="2f0b6-105">그러나 AAD와 동기화하는 Azure AD Connect 인스턴스는 하나만 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="2f0b6-105">However, it supports only one instance of Azure AD Connect syncing to AAD.</span></span> <span data-ttu-id="2f0b6-106">따라서 Azure AD가 이미 하나의 포리스트에 설치되어 있는 경우 추가 포리스트에서 동기화하기 위해 AAD Connect의 기존 인스턴스를 업데이트해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f0b6-106">Therefore, in cases where Azure AD is already installed in one forest, the existing instance of AAD Connect must be updated to sync from the additional forest.</span></span>

 - <span data-ttu-id="2f0b6-107">모든 ID가 두 포리스트에서 한 번만 표시되면(즉, 메일 사용이 가능한 연락처를 지정하지 않은 경우) AAD 연결 마법사를 다시 실행하고 "동기화 옵션 사용자 지정"을 선택한 다음 **Connect Your Directories** 페이지에서 추가 포리스트 및 creds의 이름을 입력할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f0b6-107">If all identities are represented only once across both forests (that is, you haven’t made any mail-enabled contacts), then you can simply re-run the AAD Connect wizard, choose “Customize synchronization options,” and then on the **Connect Your Directories** page, enter the name of the additional forest and creds.</span></span><br><br>
 <span data-ttu-id="2f0b6-108">![The Connect your directories page](../media/cloud-consolidation-connect-your-directories.png)</span><span class="sxs-lookup"><span data-stu-id="2f0b6-108">![The Connect your directories page](../media/cloud-consolidation-connect-your-directories.png)</span></span>
 - <span data-ttu-id="2f0b6-109">그러나 사용자가 두 개 이상의 디렉터리에 있을 수 있으며 데이터를 통합할 경우(예: 연락처 개체가 다른 포리스트의 사용자에 해당하는 포리스트에 있는 경우) Azure AD Connect를 제거하고 다시 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f0b6-109">However, if users can exist in more than one directory and you’ll be merging the data (for example, if contact objects exist in a forest corresponding to users in another forest), you will need to uninstall Azure AD Connect and re-install it.</span></span>  <span data-ttu-id="2f0b6-110">이는 포리스트 간 조인 규칙 조건은 첫 번째 설치 중에만 구성할 수 있기 때문에입니다.</span><span class="sxs-lookup"><span data-stu-id="2f0b6-110">This is because the cross-forest join rules condition can only be configured during the first install.</span></span> <span data-ttu-id="2f0b6-111">이 완료는 다음 페이지에서 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="2f0b6-111">This is done on the following page:</span></span><br><br>
 <span data-ttu-id="2f0b6-112">![사용자 고유 식별 페이지](../media/cloud-consolidation-uniquely-identifying-your-users.png)</span><span class="sxs-lookup"><span data-stu-id="2f0b6-112">![The Uniquely identifying your users page](../media/cloud-consolidation-uniquely-identifying-your-users.png)</span></span>


## <a name="see-also"></a><span data-ttu-id="2f0b6-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2f0b6-113">See also</span></span>

[<span data-ttu-id="2f0b6-114">Teams 및 비즈니스용 Skype를 위한 클라우드 통합</span><span class="sxs-lookup"><span data-stu-id="2f0b6-114">Cloud Consolidation for Teams and Skype for Business</span></span>](cloud-consolidation.md)