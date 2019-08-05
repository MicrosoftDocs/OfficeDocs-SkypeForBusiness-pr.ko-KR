---
title: Edge 인증서 업데이트
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
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
description: 이 부록에는 팀과 비즈니스용 Skype에 대 한 클라우드 통합의 일부로 edge 인증서를 업데이트 하는 단계에 대 한 자세한 단계가 포함 되어 있습니다.
ms.openlocfilehash: 1c3aaa8859db530ceccbebc68ae76f21e8d4a77f
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36185502"
---
# <a name="update-the-edge-certificate"></a><span data-ttu-id="eb497-103">Edge 인증서 업데이트</span><span class="sxs-lookup"><span data-stu-id="eb497-103">Update the edge certificate</span></span>

<span data-ttu-id="eb497-104">Edge 인증서 업데이트는 SipDomain1를 사용 하는 온-프레미스 환경에서 SipDomain2를 사용 하 여 클라우드 환경에 참가 하 고 두 개의 SIP 도메인에서 공유 된 주소 공간 환경에 적절 한 라우팅이 있는지 확인 하는 주요 단계입니다.</span><span class="sxs-lookup"><span data-stu-id="eb497-104">Updating the edge certificate is the key step to ensuring that an on-prem environment with SipDomain1 can join a cloud environment with SipDomain2 and ensure proper routing in a shared address space environment across the two SIP domains.</span></span> <span data-ttu-id="eb497-105">이 단계를 수행할 수 있는 컨텍스트에 대해 [팀 및 비즈니스용 Skype의 클라우드 통합](cloud-consolidation.md) 에 있는 14 단계를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="eb497-105">See step 14 in [Cloud consolidation for Teams and Skype for Business](cloud-consolidation.md) for context in which you might perform this step.</span></span> <span data-ttu-id="eb497-106">이 예제에서 SipDomain1는 AcquiredCompany입니다. <span>Com 및 SipDomain2는 originalcompany입니다. <span>com.</span><span class="sxs-lookup"><span data-stu-id="eb497-106">In our examples, SipDomain1 is AcquiredCompany.<span>com and SipDomain2 is OriginalCompany.<span>com.</span></span>

<span data-ttu-id="eb497-107">온-프레미스 환경의 모든 edge 서버에서 인증서의 SAN (주체 대체 이름)을 업데이트 하 여, 순수한 온라인 테 넌 트에 있는 모든 SIP 도메인을 포함 합니다 (onmicrosoft는 제외).<span> "sip." 라는 형태의 com 도메인 \<도메인> ".</span><span class="sxs-lookup"><span data-stu-id="eb497-107">The subject alternate name (SAN) of the certificate on all edge servers in the on-premises environment must be updated to include all SIP domains that exist in the pure online tenant (excluding any onmicrosoft.<span>com domains), in the form “sip.\<domain>”.</span></span>  <span data-ttu-id="eb497-108">이 예제에서는 sip입니다. OriginalCompany. <span>com.</span><span class="sxs-lookup"><span data-stu-id="eb497-108">In our example, this is sip.OriginalCompany.<span>com.</span></span> <span data-ttu-id="eb497-109">이 단계는 사용자를 클라우드로 마이그레이션하기 전에 수행 하는 것이 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb497-109">This step is critical to do before migrating any users to the cloud.</span></span>

<span data-ttu-id="eb497-110">**방법은**</span><span class="sxs-lookup"><span data-stu-id="eb497-110">**Steps:**</span></span>

1.  <span data-ttu-id="eb497-111">모든 기존 항목을 포함 하는 Edge에 대 한 새 외부에 지 인증서와 클라우드 환경 (\* onmicrosoft.com 도메인 제외)의 모든 SIP 도메인에 대 한 SAN의 추가 항목이 "SIP" 형식으로 가져옵니다. <DomainName>".</span><span class="sxs-lookup"><span data-stu-id="eb497-111">Obtain a new External Edge certificate for the edge that has all existing entries plus additional entries in the SAN for all SIP domains in the cloud environment (excluding \*.onmicrosoft.com domains) in the form “sip.<DomainName>”.</span></span>
2.  <span data-ttu-id="eb497-112">각 edge 서버에 인증서를 로컬로 설치 하 고 각 edge 서비스의 Skype Edge 서비스에 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb497-112">Install the certificate locally on each edge server and assign it to the Skype Edge service on each of the edge service.</span></span>  <span data-ttu-id="eb497-113">자세한 단계는 [비즈니스용 Skype 서버 2015의 Edge 배포 서비스](https://technet.microsoft.com/en-us/library/dn951368.aspx)에서 "외부에 지 인터페이스 인증서" 섹션을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="eb497-113">For detailed steps, see the section “External Edge interface certificates” in [Deploy Edge Service in Skype for Business Server 2015](https://technet.microsoft.com/en-us/library/dn951368.aspx).</span></span>
3.  <span data-ttu-id="eb497-114">각 edge 서버에서 Edge 서비스를 다시 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb497-114">Restart the Edge service on each of the edge servers.</span></span> <span data-ttu-id="eb497-115">다음 PowerShell 명령을 사용 하 여 단일 상자에 대해이 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eb497-115">You can do this for a single box with the following PowerShell commands:</span></span>

    ```
    Stop-CsWindowsService
    Start-CsWindowsService
    ```

## <a name="see-also"></a><span data-ttu-id="eb497-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="eb497-116">See also</span></span>

[<span data-ttu-id="eb497-117">팀 및 비즈니스용 Skype에 대 한 클라우드 통합</span><span class="sxs-lookup"><span data-stu-id="eb497-117">Cloud Consolidation for Teams and Skype for Business</span></span>](cloud-consolidation.md)