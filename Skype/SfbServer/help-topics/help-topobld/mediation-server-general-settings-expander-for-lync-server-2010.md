---
title: Lync Server 2010에 대한 중재 서버 일반 설정 확장기
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.MediationServerGeneralSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 48e434c1-0c3c-4502-9441-c0a3c340f51f
description: 이 대화 상자에서 중재 서버의 속성을 편집 합니다. 대화 상자 왼쪽에는 일반 설정, 다음 홉 설정 및 PSTN 게이트웨이 설정으로 이동할 수 있는 빠른 링크 집합이 있습니다. 각 섹션에는 다음과 같은 설정이 있습니다.
ms.openlocfilehash: 19687f8d6a97a9174782c094f80c5b52d6973caf
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/23/2020
ms.locfileid: "48215159"
---
# <a name="mediation-server-general-settings-expander-for-lync-server-2010"></a><span data-ttu-id="6f79b-105">Lync Server 2010에 대한 중재 서버 일반 설정 확장기</span><span class="sxs-lookup"><span data-stu-id="6f79b-105">Mediation Server General Settings Expander for Lync Server 2010</span></span>

<span data-ttu-id="6f79b-106">이 대화 상자에서 중재 서버의 속성을 편집 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f79b-106">You edit the properties of the Mediation Servers in this dialog.</span></span> <span data-ttu-id="6f79b-107">대화 상자 왼쪽에는 일반 설정, 다음 홉 설정 및 PSTN 게이트웨이 설정으로 이동할 수 있는 빠른 링크 집합이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6f79b-107">Along the left side is a set of quick links to take you to settings for General settings, Next hop settings, and PSTN gateway settings.</span></span> <span data-ttu-id="6f79b-108">각 섹션에는 다음과 같은 설정이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6f79b-108">In each section are the following settings:</span></span>

 <span data-ttu-id="6f79b-109">**일반**:</span><span class="sxs-lookup"><span data-stu-id="6f79b-109">**General**:</span></span>

- <span data-ttu-id="6f79b-110">**FQDN**: 중재 서버의 정규화 된 도메인 이름을 편집 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f79b-110">**FQDN**: You edit the fully qualified domain name of the Mediation Server</span></span>

- <span data-ttu-id="6f79b-111">**연결**:에 **지 풀 연결 (미디어 구성 요소)** 확인란을 선택 하 고 중재 서버가 외부 액세스를 위한 미디어 경로로 사용할에 지 서버 또는에 지 풀을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f79b-111">**Associations**: Select the **Associate Edge pool (for media components)** check box and select an Edge Server or Edge pool for the Mediation Server to use as the media path for external access.</span></span>

  <span data-ttu-id="6f79b-112">**다음 홉**:</span><span class="sxs-lookup"><span data-stu-id="6f79b-112">**Next hop**:</span></span>

- <span data-ttu-id="6f79b-113">**다음 홉 선택**: 배포와 통신 하는 데 사용할 중재 서버의 경로로 사용할 프런트 엔드 서버 또는 프런트 엔드 풀을 목록에서 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f79b-113">**Next hop selection**: Select from a list the Front End Server or Front End pool to use as the path for the Mediation Server to use for communicating with your deployment.</span></span>

  <span data-ttu-id="6f79b-114">**PSTN 게이트웨이**:</span><span class="sxs-lookup"><span data-stu-id="6f79b-114">**PSTN gateway**:</span></span>

  <span data-ttu-id="6f79b-115">**중재 서버 PSTN 게이트웨이**</span><span class="sxs-lookup"><span data-stu-id="6f79b-115">**Mediation Server PSTN gateway**:</span></span>

- <span data-ttu-id="6f79b-116">**수신 대기 포트**: 중재 서버가 수신 대기 하는 포트를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f79b-116">**Listening ports**: Define the ports that the Mediation Server will listen on.</span></span> <span data-ttu-id="6f79b-117">**TLS**(전송 계층 보안) 또는 **TCP**(Transport Control Protocol)용 포트를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6f79b-117">You can define a port for **TLS** or transport layer security, or **TCP**, or transport control protocol.</span></span> <span data-ttu-id="6f79b-118">TCP에 대한 포트 항목을 사용할 수 있도록 하려면 **TCP 포트 사용** 확인란을 선택해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f79b-118">For the port entry for TCP to be available, you must select the check box for **Enable TCP port**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="6f79b-119">공중 전화망(PSTN) 게이트웨이의 설명서 및 구성 설정을 참조하여 포트 값 TLS 또는 TCP나 둘 다를 사용하도록 설정하고 정의해야 하는지 여부를 확인하십시오.</span><span class="sxs-lookup"><span data-stu-id="6f79b-119">Refer to the documentation and configuration settings for your public switched telephone network (PSTN) gateway to determine if you need to enable and define port values TLS, TCP or both.</span></span> <span data-ttu-id="6f79b-120">TLS는 중재 서버와 PSTN 게이트웨이 간의 트래픽을 암호화 하는 인증서를 사용 하는 보다 안전한 프로토콜입니다.</span><span class="sxs-lookup"><span data-stu-id="6f79b-120">TLS is a more secure protocol, using certificates to encrypt the traffic between the Mediation Server and the PSTN gateway.</span></span> <span data-ttu-id="6f79b-121">일부 PSTN 게이트웨이에서는 TLS가 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6f79b-121">Not all PSTN gateways support TLS.</span></span>

- <span data-ttu-id="6f79b-122">배포에 대해 정의 및 구성된 SIP 트렁크 및 게이트웨이 목록이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6f79b-122">A listing of SIP trunks and the gateways that are defined and configured for your deployment is listed.</span></span> <span data-ttu-id="6f79b-123">항목이 없는 경우에는 배포에 대해 구성된 SIP 트렁크 또는 PSTN 게이트웨이가 없는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="6f79b-123">If no entries are present, there are no SIP trunks or PSTN gateways configured for your deployment.</span></span> <span data-ttu-id="6f79b-124">토폴로지 작성기의 **공유 구성 요소** 에 트렁크 및 게이트웨이를 정의 하 고 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f79b-124">You define and configure trunks and gateways under **Shared Components** in Topology Builder.</span></span>

## <a name="see-also"></a><span data-ttu-id="6f79b-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6f79b-125">See also</span></span>

[<span data-ttu-id="6f79b-126">SIP 트렁크 개요</span><span class="sxs-lookup"><span data-stu-id="6f79b-126">Overview of SIP Trunking</span></span>](https://technet.microsoft.com/library/204f2c21-436f-4b2d-93ea-d6db98fa2952.aspx)

[<span data-ttu-id="6f79b-127">PSTN 게이트웨이 배포 옵션</span><span class="sxs-lookup"><span data-stu-id="6f79b-127">PSTN Gateway Deployment Options</span></span>](https://technet.microsoft.com/library/d1ab4f74-18aa-40c7-a8cf-ec806cf6e28a.aspx)
