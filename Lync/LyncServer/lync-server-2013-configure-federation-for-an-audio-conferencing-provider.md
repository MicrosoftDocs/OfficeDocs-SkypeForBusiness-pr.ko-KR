---
title: 'Lync Server 2013: 오디오 회의 공급자를 위한 페더레이션 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure federation for an audio conferencing provider
ms:assetid: 08dedcce-0d3f-45da-8282-cf2634a41665
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn510996(v=OCS.15)
ms:contentKeyID: 60595883
ms.date: 07/24/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cebbac17955f812bf07a368064156b57b0c0ddd9
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48537095"
---
# <a name="configure-federation-for-an-audio-conferencing-provider-in-lync-server-2013"></a><span data-ttu-id="f5e79-102">Lync Server 2013에서 오디오 회의 공급자를 위한 페더레이션 구성</span><span class="sxs-lookup"><span data-stu-id="f5e79-102">Configure federation for an audio conferencing provider in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f5e79-103">_**마지막으로 수정 된 항목:** 2014-07-24_</span><span class="sxs-lookup"><span data-stu-id="f5e79-103">_**Topic Last Modified:** 2014-07-24_</span></span>

<span data-ttu-id="f5e79-104">하이브리드 배포에서 ACP (오디오 회의 공급자)를 사용 하려는 경우 (Lync Online을 사용 하는 Lync Server 온-프레미스), 온-프레미스 Lync 배포와 ACP 파트너 간의 페더레이션을 허용 된 파트너 서버로 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f5e79-104">If you want to use an Audio Conferencing Provider (ACP) in your hybrid deployment (Lync Server on-premises with Lync Online), you need to configure federation between your on-premises Lync deployment and the ACP partner as an Allowed Partner Server.</span></span> <span data-ttu-id="f5e79-105">온-프레미스 배포의 페더레이션 도메인 목록에 ACP 파트너 도메인 및에 지 서버 (액세스 프록시 라고도 함)를 추가 하 여 페더레이션을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5e79-105">You can configure federation by adding the ACP partner domain and Edge server (this may also be called the Access Proxy) to the Federated Domains list for your on-premises deployment.</span></span> <span data-ttu-id="f5e79-106">그러면 ACP 파트너가 온-프레미스에 지 서버 풀의 FQDN을 허용 되는 페더레이션 도메인 목록에 추가 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f5e79-106">Your ACP partner then needs to add the FQDN of your on-premises Edge Server pool to their allowed federated domains list.</span></span> <span data-ttu-id="f5e79-107">추가 detailsYour ACP 파트너에 대 한 ACP provider에 문의 하 여 온-프레미스에 지 서버 풀의 FQDN을 허용 되는 페더레이션 도메인 목록에 추가 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f5e79-107">Contact your ACP provider for additional detailsYour ACP partner then needs to add the FQDN of your on-premises Edge Server pool to their allowed federated domains list.</span></span>

  - <span data-ttu-id="f5e79-108">**ACP 도메인 및에 지 서버를 허용 되는 페더레이션 도메인으로 추가**</span><span class="sxs-lookup"><span data-stu-id="f5e79-108">**Adding the ACP Domain and Edge Server as an Allowed Federated Domain**</span></span>
    
    <span data-ttu-id="f5e79-109">ACP 도메인을 허용 되는 파트너 서버 (페더레이션 도메인)로 추가 하려면 [Lync Server 2013에서 허용 되는 외부 도메인에 대 한 지원 구성](lync-server-2013-configure-support-for-allowed-external-domains.md)의 단계를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="f5e79-109">To add the ACP domain as an Allowed Partner Server (allowed Federated Domain), follow the steps in [Configure support for allowed external domains in Lync Server 2013](lync-server-2013-configure-support-for-allowed-external-domains.md).</span></span> <span data-ttu-id="f5e79-110">에 지 서버의 FQDN을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="f5e79-110">For the Edge Server, add the FQDN of the ACP partner’s Edge Server.</span></span> <span data-ttu-id="f5e79-111">해당에 지 서버에 대 한 FQDN을 가져오려면 ACP 파트너에 게 문의 하 여 액세스 프록시로 서이를 참조 해야 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5e79-111">You may need to contact your ACP partner to obtain the FQDN for their Edge Server, which may also be referred to by your ACP as their Access Proxy.</span></span>

  - <span data-ttu-id="f5e79-112">**에 지 서버 풀의 FQDN을 ACP 파트너에 게 제공 합니다.**</span><span class="sxs-lookup"><span data-stu-id="f5e79-112">**Provide the FQDN of your Edge Server Pool to the ACP partner**</span></span>
    
    <span data-ttu-id="f5e79-113">ACP 파트너는 허용 되는 페더레이션 도메인으로에 지 서버 풀의 FQDN을 추가 하 여 온-프레미스 도메인이 허용 되는 파트너 서버로 추가 되도록 페더레이션을 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f5e79-113">The ACP partner needs to configure federation to add your on-premises domain as an Allowed Partner Server by adding the FQDN of your Edge Server pool as an allowed Federated domain.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

