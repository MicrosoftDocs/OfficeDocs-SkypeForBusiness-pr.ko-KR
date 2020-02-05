---
title: 하이브리드 배포에서 오디오 회의 공급자를 위한 페더레이션 구성
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
description: '요약: 비즈니스용 Skype Online에서 오디오 회의 공급자를 위한 페더레이션을 구성 하는 방법을 알아봅니다.'
ms.openlocfilehash: a19704327d1cf5591a1ebb3f62aa23f46fe09d10
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726888"
---
# <a name="configure-federation-for-an-audio-conferencing-provider-in-your-hybrid-deployment"></a><span data-ttu-id="dbbe5-103">하이브리드 배포에서 오디오 회의 공급자를 위한 페더레이션 구성</span><span class="sxs-lookup"><span data-stu-id="dbbe5-103">Configure federation for an audio conferencing provider in your hybrid deployment</span></span>

<span data-ttu-id="dbbe5-104">**요약:** 비즈니스용 Skype Online에서 오디오 회의 공급자를 위한 페더레이션을 구성 하는 방법을 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="dbbe5-104">**Summary:** Learn how to configure federation for an audio conferencing provider in Skype for Business Online.</span></span>

<span data-ttu-id="dbbe5-105">하이브리드 배포에서 ACP (오디오 회의 공급자)를 사용 하려는 경우 (온-프레미스 online) 온-프레미스 배포와 ACP 파트너 간의 페더레이션을 허용 된 파트너 서버로 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dbbe5-105">If you want to use an Audio Conferencing Provider (ACP) in your hybrid deployment (on-premises with online), you need to configure federation between your on-premises deployment and the ACP partner as an Allowed Partner Server.</span></span> <span data-ttu-id="dbbe5-106">온-프레미스 배포의 페더레이션 도메인 목록에 ACP 파트너 도메인 및에 지 서버 (액세스 프록시 라고도 함)를 추가 하 여 페더레이션을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dbbe5-106">You can configure federation by adding the ACP partner domain and Edge server (this may also be called the Access Proxy) to the Federated Domains list for your on-premises deployment.</span></span> <span data-ttu-id="dbbe5-107">그러면 ACP 파트너가 온-프레미스에 지 서버 풀의 FQDN을 허용 되는 페더레이션 도메인 목록에 추가 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dbbe5-107">Your ACP partner then needs to add the FQDN of your on-premises Edge Server pool to their allowed federated domains list.</span></span> <span data-ttu-id="dbbe5-108">자세한 내용은 ACP provider에 문의 하세요.</span><span class="sxs-lookup"><span data-stu-id="dbbe5-108">Contact your ACP provider for additional details.</span></span> <span data-ttu-id="dbbe5-109">그러면 ACP 파트너가 온-프레미스에 지 서버 풀의 FQDN을 허용 되는 페더레이션 도메인 목록에 추가 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dbbe5-109">Your ACP partner then needs to add the FQDN of your on-premises Edge Server pool to their allowed federated domains list.</span></span>

- <span data-ttu-id="dbbe5-110">**ACP 도메인 및에 지 서버를 허용 되는 페더레이션 도메인으로 추가**</span><span class="sxs-lookup"><span data-stu-id="dbbe5-110">**Adding the ACP Domain and Edge Server as an Allowed Federated Domain**</span></span>

    <span data-ttu-id="dbbe5-111">ACP 도메인을 허용 되는 파트너 서버 (페더레이션 도메인)로 추가 하려면 [허용 되는 외부 도메인에 대 한 지원 구성](https://technet.microsoft.com/library/3ee6e175-986d-4c33-b03a-b9f93083dca6.aspx)의 단계를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="dbbe5-111">To add the ACP domain as an Allowed Partner Server (allowed Federated Domain), follow the steps in [Configure Support for Allowed External Domains](https://technet.microsoft.com/library/3ee6e175-986d-4c33-b03a-b9f93083dca6.aspx).</span></span> <span data-ttu-id="dbbe5-112">에 지 서버의 FQDN을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="dbbe5-112">For the Edge Server, add the FQDN of the ACP partner's Edge Server.</span></span> <span data-ttu-id="dbbe5-113">해당에 지 서버에 대 한 FQDN을 가져오려면 ACP 파트너에 게 문의 하 여 액세스 프록시로 서이를 참조 해야 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dbbe5-113">You may need to contact your ACP partner to obtain the FQDN for their Edge Server, which may also be referred to by your ACP as their Access Proxy.</span></span>

- <span data-ttu-id="dbbe5-114">**에 지 서버 풀의 FQDN을 ACP 파트너에 게 제공**</span><span class="sxs-lookup"><span data-stu-id="dbbe5-114">**Providing the FQDN of your Edge Server Pool to the ACP partner**</span></span>

    <span data-ttu-id="dbbe5-115">ACP 파트너는 허용 되는 페더레이션 도메인으로에 지 서버 풀의 FQDN을 추가 하 여 온-프레미스 도메인이 허용 되는 파트너 서버로 추가 되도록 페더레이션을 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dbbe5-115">The ACP partner needs to configure federation to add your on-premises domain as an Allowed Partner Server by adding the FQDN of your Edge Server pool as an allowed Federated domain.</span></span>


