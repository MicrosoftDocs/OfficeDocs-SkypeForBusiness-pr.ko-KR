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
description: '요약: 비즈니스용 Skype Online에서 오디오 회의 공급자에 대한 페더링을 구성하는 방법을 설명하는 정보를 제공합니다.'
ms.openlocfilehash: a19704327d1cf5591a1ebb3f62aa23f46fe09d10
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726888"
---
# <a name="configure-federation-for-an-audio-conferencing-provider-in-your-hybrid-deployment"></a><span data-ttu-id="06873-103">하이브리드 배포에서 오디오 회의 공급자에 대한 페더링 구성</span><span class="sxs-lookup"><span data-stu-id="06873-103">Configure federation for an audio conferencing provider in your hybrid deployment</span></span>

<span data-ttu-id="06873-104">**요약:** 비즈니스용 Skype Online에서 오디오 회의 공급자에 대한 페더링을 구성하는 방법을 배워야 합니다.</span><span class="sxs-lookup"><span data-stu-id="06873-104">**Summary:** Learn how to configure federation for an audio conferencing provider in Skype for Business Online.</span></span>

<span data-ttu-id="06873-105">하이브리드 배포에서 ACP(오디오 회의 공급자)를 사용하려면(온라인과의 경우) ACP 파트너와의 페더링을 허용 파트너 서버로 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="06873-105">If you want to use an Audio Conferencing Provider (ACP) in your hybrid deployment (on-premises with online), you need to configure federation between your on-premises deployment and the ACP partner as an Allowed Partner Server.</span></span> <span data-ttu-id="06873-106">ACP 파트너 도메인 및 에지 서버(액세스 프록시라고도 부를 수 있습니다)를 On-프레미스 배포에 대한 페더리된 도메인 목록에 추가하여 페더전을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06873-106">You can configure federation by adding the ACP partner domain and Edge server (this may also be called the Access Proxy) to the Federated Domains list for your on-premises deployment.</span></span> <span data-ttu-id="06873-107">그러면 ACP 파트너가 허용되는 페더러티 도메인 목록에 해당 에지 서버 풀의 FQDN을 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="06873-107">Your ACP partner then needs to add the FQDN of your on-premises Edge Server pool to their allowed federated domains list.</span></span> <span data-ttu-id="06873-108">ACP 공급자에게 문의하여 자세한 내용을 확인하십시오.</span><span class="sxs-lookup"><span data-stu-id="06873-108">Contact your ACP provider for additional details.</span></span> <span data-ttu-id="06873-109">그러면 ACP 파트너가 허용되는 페더러티 도메인 목록에 해당 에지 서버 풀의 FQDN을 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="06873-109">Your ACP partner then needs to add the FQDN of your on-premises Edge Server pool to their allowed federated domains list.</span></span>

- <span data-ttu-id="06873-110">**ACP 도메인 및 에지 서버를 허용된 페더리트 도메인으로 추가**</span><span class="sxs-lookup"><span data-stu-id="06873-110">**Adding the ACP Domain and Edge Server as an Allowed Federated Domain**</span></span>

    <span data-ttu-id="06873-111">ACP 도메인을 허용 파트너 서버(허용된 페더화 도메인)로 추가하려면 허용된 외부 도메인에 대한 지원 구성의 [단계를 따릅니다.](https://technet.microsoft.com/library/3ee6e175-986d-4c33-b03a-b9f93083dca6.aspx)</span><span class="sxs-lookup"><span data-stu-id="06873-111">To add the ACP domain as an Allowed Partner Server (allowed Federated Domain), follow the steps in [Configure Support for Allowed External Domains](https://technet.microsoft.com/library/3ee6e175-986d-4c33-b03a-b9f93083dca6.aspx).</span></span> <span data-ttu-id="06873-112">에지 서버의 경우 ACP 파트너의 에지 서버의 FQDN을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="06873-112">For the Edge Server, add the FQDN of the ACP partner's Edge Server.</span></span> <span data-ttu-id="06873-113">ACP 파트너에게 문의하여 해당 에지 서버의 FQDN을 얻어야 할 수 있습니다. ACP를 액세스 프록시로 참조할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06873-113">You may need to contact your ACP partner to obtain the FQDN for their Edge Server, which may also be referred to by your ACP as their Access Proxy.</span></span>

- <span data-ttu-id="06873-114">**ACP 파트너에게 에지 서버 풀의 FQDN 제공**</span><span class="sxs-lookup"><span data-stu-id="06873-114">**Providing the FQDN of your Edge Server Pool to the ACP partner**</span></span>

    <span data-ttu-id="06873-115">ACP 파트너는 에지 서버 풀의 FQDN을 허용된 페더티드 도메인으로 추가하여 허용 파트너 서버로 추가하도록 페더전을 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="06873-115">The ACP partner needs to configure federation to add your on-premises domain as an Allowed Partner Server by adding the FQDN of your Edge Server pool as an allowed Federated domain.</span></span>


