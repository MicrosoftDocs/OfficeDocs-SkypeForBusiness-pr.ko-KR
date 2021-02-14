---
title: 에지 인증서 업데이트
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
description: 이 부록에는 Teams 및 비즈니스용 Skype에 대한 클라우드 통합의 일부로 에지 인증서를 업데이트하는 자세한 단계가 포함되어 있습니다.
ms.openlocfilehash: 3e6b151e340a0942b561edd2233795fad94c3a9e
ms.sourcegitcommit: 1a08ec9069332e19135312d35fc6a6c3247ce2d2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/11/2020
ms.locfileid: "41888607"
---
# <a name="update-the-edge-certificate"></a><span data-ttu-id="80d09-103">에지 인증서 업데이트</span><span class="sxs-lookup"><span data-stu-id="80d09-103">Update the edge certificate</span></span>

<span data-ttu-id="80d09-104">에지 인증서를 업데이트하는 것은 SipDomain1이 있는 프레미스 환경이 SipDomain2를 사용하여 클라우드 환경에 가입하고 두 SIP 도메인의 공유 주소 공간 환경에서 적절한 라우팅을 보장하기 위한 핵심 단계입니다.</span><span class="sxs-lookup"><span data-stu-id="80d09-104">Updating the edge certificate is the key step to ensuring that an on-prem environment with SipDomain1 can join a cloud environment with SipDomain2 and ensure proper routing in a shared address space environment across the two SIP domains.</span></span> <span data-ttu-id="80d09-105">이 단계를 수행할 수 있는 컨텍스트는 Teams 및 비즈니스용 [Skype에](cloud-consolidation.md) 대한 클라우드 통합의 14단계를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="80d09-105">See step 14 in [Cloud consolidation for Teams and Skype for Business](cloud-consolidation.md) for context in which you might perform this step.</span></span> <span data-ttu-id="80d09-106">이 예제에서 SipDomain1은 AcquiredCompany입니다. <span> com 및 SipDomain2는 OriginalCompany입니다. <span> com.</span><span class="sxs-lookup"><span data-stu-id="80d09-106">In our examples, SipDomain1 is AcquiredCompany.<span>com and SipDomain2 is OriginalCompany.<span>com.</span></span>

<span data-ttu-id="80d09-107">순수 온라인 테넌트에 있는 모든 SIP 도메인(onmicrosoft 제외)을 포함하려면, 모든 에지 환경의 모든 에지 서버에 있는 인증서의 SAN(주체 대체 이름)을 업데이트해야 합니다. <span> com 도메인)을 지정합니다. "sip" 형식입니다. \< domain>".</span><span class="sxs-lookup"><span data-stu-id="80d09-107">The subject alternate name (SAN) of the certificate on all edge servers in the on-premises environment must be updated to include all SIP domains that exist in the pure online tenant (excluding any onmicrosoft.<span>com domains), in the form “sip.\<domain>”.</span></span>  <span data-ttu-id="80d09-108">이 예제에서는 sip입니다. OriginalCompany. <span> com.</span><span class="sxs-lookup"><span data-stu-id="80d09-108">In our example, this is sip.OriginalCompany.<span>com.</span></span> <span data-ttu-id="80d09-109">이 단계는 사용자를 클라우드로 마이그레이션하기 전에 먼저 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="80d09-109">This step is critical to do before migrating any users to the cloud.</span></span>

<span data-ttu-id="80d09-110">**단계:**</span><span class="sxs-lookup"><span data-stu-id="80d09-110">**Steps:**</span></span>

1.  <span data-ttu-id="80d09-111">모든 기존 항목이 있는 에지용 새 외부 에지 인증서와 클라우드 환경의 모든 SIP 도메인(\*.onmicrosoft.com 도메인 제외)에 대한 SAN의 추가 항목을 "sip. "의 형태로 <DomainName> 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="80d09-111">Obtain a new External Edge certificate for the edge that has all existing entries plus additional entries in the SAN for all SIP domains in the cloud environment (excluding \*.onmicrosoft.com domains) in the form “sip.<DomainName>”.</span></span>
2.  <span data-ttu-id="80d09-112">인증서를 각 에지 서버에 로컬로 설치하고 각 에지 서비스의 Skype 에지 서비스에 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="80d09-112">Install the certificate locally on each edge server and assign it to the Skype Edge service on each of the edge service.</span></span>  <span data-ttu-id="80d09-113">자세한 단계는 비즈니스용 Skype 서버 [2015의](https://technet.microsoft.com/library/dn951368.aspx)에지 서비스 배포에서 "외부 에지 인터페이스 인증서" 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="80d09-113">For detailed steps, see the section “External Edge interface certificates” in [Deploy Edge Service in Skype for Business Server 2015](https://technet.microsoft.com/library/dn951368.aspx).</span></span>
3.  <span data-ttu-id="80d09-114">각 에지 서버에서 에지 서비스를 다시 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="80d09-114">Restart the Edge service on each of the edge servers.</span></span> <span data-ttu-id="80d09-115">다음 PowerShell 명령을 사용하여 단일 상자에 대해 이 작업을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="80d09-115">You can do this for a single box with the following PowerShell commands:</span></span>

    ```PowerShell
    Stop-CsWindowsService
    Start-CsWindowsService
    ```

## <a name="see-also"></a><span data-ttu-id="80d09-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="80d09-116">See also</span></span>

[<span data-ttu-id="80d09-117">Teams 및 비즈니스용 Skype를 위한 클라우드 통합</span><span class="sxs-lookup"><span data-stu-id="80d09-117">Cloud Consolidation for Teams and Skype for Business</span></span>](cloud-consolidation.md)