---
title: 두 개 이상의 포리스트를 포함 하도록 AAD 연결 업데이트
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
description: 이 부록에는 팀 및 비즈니스용 Skype에 대 한 클라우드 통합의 일환으로 두 개 이상의 포리스트를 포함 하도록 AAD Connect를 업데이트 하기 위한 세부 단계가 포함 되어 있습니다.
ms.openlocfilehash: 3d3d72c14957f0ed8932d95fcd2dbe9ec9c1e37e
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41696063"
---
# <a name="update-aad-connect-to-include-more-than-one-forest"></a><span data-ttu-id="41887-103">두 개 이상의 포리스트를 포함 하도록 AAD 연결 업데이트</span><span class="sxs-lookup"><span data-stu-id="41887-103">Update AAD Connect to include more than one forest</span></span>

<span data-ttu-id="41887-104">Azure AD Connect는 [여러 포리스트에서 동기화를](https://docs.microsoft.com/en-us/azure/active-directory/connect/active-directory-aadconnect-topologies)지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="41887-104">Azure AD Connect supports [syncing from multiple forests](https://docs.microsoft.com/en-us/azure/active-directory/connect/active-directory-aadconnect-topologies).</span></span> <span data-ttu-id="41887-105">그러나 AAD에 대 한 Azure AD Connect 동기화 인스턴스만 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="41887-105">However, it supports only one instance of Azure AD Connect syncing to AAD.</span></span> <span data-ttu-id="41887-106">따라서 Azure AD가 한 포리스트에 이미 설치 되어 있는 경우에는 추가 포리스트에서 동기화 되도록 AAD 연결의 기존 인스턴스를 업데이트 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="41887-106">Therefore, in cases where Azure AD is already installed in one forest, the existing instance of AAD Connect must be updated to sync from the additional forest.</span></span>

 - <span data-ttu-id="41887-107">모든 id가 양쪽 포리스트에서 한 번만 표시 되는 경우, 즉 메일 사용이 가능한 연락처를 만들지 않은 경우에는 AAD Connect 마법사를 다시 실행 하 고 "동기화 옵션 사용자 지정"을 선택한 다음, **디렉터리 연결** 페이지에서 추가 포리스트 및 자격 증명의 이름을 입력할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41887-107">If all identities are represented only once across both forests (that is, you haven’t made any mail-enabled contacts), then you can simply re-run the AAD Connect wizard, choose “Customize synchronization options,” and then on the **Connect Your Directories** page, enter the name of the additional forest and creds.</span></span><br><br>
 <span data-ttu-id="41887-108">![디렉터리 연결 페이지](../media/cloud-consolidation-connect-your-directories.png)</span><span class="sxs-lookup"><span data-stu-id="41887-108">![The Connect your directories page](../media/cloud-consolidation-connect-your-directories.png)</span></span>
 - <span data-ttu-id="41887-109">그러나 사용자가 둘 이상의 디렉터리에 있고 데이터를 병합 하는 경우 (예: 다른 포리스트의 사용자에 게 해당 하는 포리스트에 대화 개체가 있는 경우) Azure AD Connect를 제거 하 고 다시 설치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="41887-109">However, if users can exist in more than one directory and you’ll be merging the data (for example, if contact objects exist in a forest corresponding to users in another forest), you will need to uninstall Azure AD Connect and re-install it.</span></span>  <span data-ttu-id="41887-110">포리스트 간 조인 규칙 조건은 첫 번째 설치 중에만 구성할 수 있기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="41887-110">This is because the cross-forest join rules condition can only be configured during the first install.</span></span> <span data-ttu-id="41887-111">이 작업은 다음 페이지에서 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="41887-111">This is done on the following page:</span></span><br><br>
 <span data-ttu-id="41887-112">![사용자를 고유 하 게 식별 하는 페이지](../media/cloud-consolidation-uniquely-identifying-your-users.png)</span><span class="sxs-lookup"><span data-stu-id="41887-112">![The Uniquely identifying your users page](../media/cloud-consolidation-uniquely-identifying-your-users.png)</span></span>


## <a name="see-also"></a><span data-ttu-id="41887-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="41887-113">See also</span></span>

[<span data-ttu-id="41887-114">팀 및 비즈니스용 Skype에 대 한 클라우드 통합</span><span class="sxs-lookup"><span data-stu-id="41887-114">Cloud Consolidation for Teams and Skype for Business</span></span>](cloud-consolidation.md)