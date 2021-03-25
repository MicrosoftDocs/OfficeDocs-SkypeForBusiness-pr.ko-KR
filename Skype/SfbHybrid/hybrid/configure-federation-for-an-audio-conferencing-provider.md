---
title: 하이브리드 배포에서 오디오 회의 공급자에 대한 페더링 구성
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
ms.custom: ''
description: '요약: 비즈니스용 Skype Online에서 오디오 회의 공급자에 대한 페더링을 구성하는 방법을 설명하는 방법을 제공합니다.'
ms.openlocfilehash: 5d9c49299452f579cd7c58adf54facb09f0b8a21
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51118977"
---
# <a name="configure-federation-for-an-audio-conferencing-provider-in-your-hybrid-deployment"></a><span data-ttu-id="09559-103">하이브리드 배포에서 오디오 회의 공급자에 대한 페더링 구성</span><span class="sxs-lookup"><span data-stu-id="09559-103">Configure federation for an audio conferencing provider in your hybrid deployment</span></span>

<span data-ttu-id="09559-104">**요약:** 비즈니스용 Skype Online에서 오디오 회의 공급자에 대한 페더링을 구성하는 방법을 배워야 합니다.</span><span class="sxs-lookup"><span data-stu-id="09559-104">**Summary:** Learn how to configure federation for an audio conferencing provider in Skype for Business Online.</span></span>

<span data-ttu-id="09559-105">하이브리드 배포에서 ACP(오디오 회의 공급자)를 사용하려는 경우(온라인과의 사내에서) 페더링을 구성하려면 사내 배포와 ACP 파트너 간의 페더링을 허용 파트너 서버로 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="09559-105">If you want to use an Audio Conferencing Provider (ACP) in your hybrid deployment (on-premises with online), you need to configure federation between your on-premises deployment and the ACP partner as an Allowed Partner Server.</span></span> <span data-ttu-id="09559-106">ACP 파트너 도메인 및 에지 서버(액세스 프록시라고도 부를 수 있습니다)를 On-프레미스 배포에 대한 페더전된 도메인 목록에 추가하여 페더더전을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09559-106">You can configure federation by adding the ACP partner domain and Edge server (this may also be called the Access Proxy) to the Federated Domains list for your on-premises deployment.</span></span> <span data-ttu-id="09559-107">그런 다음 ACP 파트너는 허용되는 페더티된 도메인 목록에 사내 에지 서버 풀의 FQDN을 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="09559-107">Your ACP partner then needs to add the FQDN of your on-premises Edge Server pool to their allowed federated domains list.</span></span> <span data-ttu-id="09559-108">추가 세부 정보는 ACP 공급자에 문의하십시오.</span><span class="sxs-lookup"><span data-stu-id="09559-108">Contact your ACP provider for additional details.</span></span> <span data-ttu-id="09559-109">그런 다음 ACP 파트너는 허용되는 페더티된 도메인 목록에 사내 에지 서버 풀의 FQDN을 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="09559-109">Your ACP partner then needs to add the FQDN of your on-premises Edge Server pool to their allowed federated domains list.</span></span>

- <span data-ttu-id="09559-110">**ACP 도메인 및 에지 서버를 허용된 페더러트 도메인으로 추가**</span><span class="sxs-lookup"><span data-stu-id="09559-110">**Adding the ACP Domain and Edge Server as an Allowed Federated Domain**</span></span>

    <span data-ttu-id="09559-111">ACP 도메인을 허용된 파트너 서버(허용된 페더화 도메인)로 추가하려면 [Configure Support for Allowed External Domains의 단계를 따릅니다.](/previous-versions/office/lync-server-2013/lync-server-2013-configure-support-for-allowed-external-domains)</span><span class="sxs-lookup"><span data-stu-id="09559-111">To add the ACP domain as an Allowed Partner Server (allowed Federated Domain), follow the steps in [Configure Support for Allowed External Domains](/previous-versions/office/lync-server-2013/lync-server-2013-configure-support-for-allowed-external-domains).</span></span> <span data-ttu-id="09559-112">에지 서버의 경우 ACP 파트너의 에지 서버의 FQDN을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="09559-112">For the Edge Server, add the FQDN of the ACP partner's Edge Server.</span></span> <span data-ttu-id="09559-113">ACP 파트너에게 문의하여 에지 서버의 FQDN을 얻어야 할 수 있습니다. ACP를 액세스 프록시로도 지칭할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09559-113">You may need to contact your ACP partner to obtain the FQDN for their Edge Server, which may also be referred to by your ACP as their Access Proxy.</span></span>

- <span data-ttu-id="09559-114">**ACP 파트너에게 에지 서버 풀의 FQDN 제공**</span><span class="sxs-lookup"><span data-stu-id="09559-114">**Providing the FQDN of your Edge Server Pool to the ACP partner**</span></span>

    <span data-ttu-id="09559-115">ACP 파트너는 에지 서버 풀의 FQDN을 허용된 페더티드 도메인으로 추가하여 허용 파트너 서버로 사내 도메인을 추가하도록 페더ATION을 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="09559-115">The ACP partner needs to configure federation to add your on-premises domain as an Allowed Partner Server by adding the FQDN of your Edge Server pool as an allowed Federated domain.</span></span>