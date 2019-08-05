---
title: Lync Server 2010의 중재 서버 일반 설정 확장기
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.MediationServerGeneralSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 48e434c1-0c3c-4502-9441-c0a3c340f51f
description: 이 대화 상자에서 중재 서버의 속성을 편집 합니다. 왼쪽에는 일반 설정, 다음 홉 설정, PSTN 게이트웨이 설정에 대 한 설정으로 이동 하는 빠른 링크 집합이 있습니다. 각 섹션에는 다음 설정이 있습니다.
ms.openlocfilehash: ce58f0c64a458864c91bfd63f8b1d0f905d5374d
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36190179"
---
# <a name="mediation-server-general-settings-expander-for-lync-server-2010"></a><span data-ttu-id="6e250-105">Lync Server 2010의 중재 서버 일반 설정 확장기</span><span class="sxs-lookup"><span data-stu-id="6e250-105">Mediation Server General Settings Expander for Lync Server 2010</span></span>

<span data-ttu-id="6e250-106">이 대화 상자에서 중재 서버의 속성을 편집 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e250-106">You edit the properties of the Mediation Servers in this dialog.</span></span> <span data-ttu-id="6e250-107">왼쪽에는 일반 설정, 다음 홉 설정, PSTN 게이트웨이 설정에 대 한 설정으로 이동 하는 빠른 링크 집합이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6e250-107">Along the left side is a set of quick links to take you to settings for General settings, Next hop settings, and PSTN gateway settings.</span></span> <span data-ttu-id="6e250-108">각 섹션에는 다음 설정이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6e250-108">In each section are the following settings:</span></span>

 <span data-ttu-id="6e250-109">**일반**:</span><span class="sxs-lookup"><span data-stu-id="6e250-109">**General**:</span></span>

- <span data-ttu-id="6e250-110">**FQDN**: 중재 서버의 정규화 된 도메인 이름을 편집 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e250-110">**FQDN**: You edit the fully qualified domain name of the Mediation Server</span></span>

- <span data-ttu-id="6e250-111">**연결**: **edge 풀 연결 (미디어 구성 요소의 경우)** 확인란을 선택 하 고 중재 서버에 대 한 edge 서버 또는 edge 풀을 선택 하 여 외부 액세스를 위한 미디어 경로로 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e250-111">**Associations**: Select the **Associate Edge pool (for media components)** check box and select an Edge Server or Edge pool for the Mediation Server to use as the media path for external access.</span></span>

  <span data-ttu-id="6e250-112">**다음 홉**:</span><span class="sxs-lookup"><span data-stu-id="6e250-112">**Next hop**:</span></span>

- <span data-ttu-id="6e250-113">**다음 홉 선택**: 목록에서 배포와 통신 하는 데 사용할 중재 서버의 경로로 사용할 프런트 엔드 서버 또는 프런트 엔드 풀을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e250-113">**Next hop selection**: Select from a list the Front End Server or Front End pool to use as the path for the Mediation Server to use for communicating with your deployment.</span></span>

  <span data-ttu-id="6e250-114">**PSTN 게이트웨이**:</span><span class="sxs-lookup"><span data-stu-id="6e250-114">**PSTN gateway**:</span></span>

  <span data-ttu-id="6e250-115">**중재 서버 PSTN 게이트웨이**:</span><span class="sxs-lookup"><span data-stu-id="6e250-115">**Mediation Server PSTN gateway**:</span></span>

- <span data-ttu-id="6e250-116">**수신 대기 포트**: 중재 서버가 수신 대기 하는 포트를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e250-116">**Listening ports**: Define the ports that the Mediation Server will listen on.</span></span> <span data-ttu-id="6e250-117">**TLS** 또는 전송 계층 보안, **TCP**또는 전송 제어 프로토콜에 대 한 포트를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6e250-117">You can define a port for **TLS** or transport layer security, or **TCP**, or transport control protocol.</span></span> <span data-ttu-id="6e250-118">TCP에 대 한 포트 항목을 사용 하려면 **tcp 포트 사용**확인란을 선택 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e250-118">For the port entry for TCP to be available, you must select the check box for **Enable TCP port**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="6e250-119">포트 값 TLS, TCP 또는 둘 다를 사용 하도록 설정 하 고 정의 해야 하는지 여부는 공용 전환 통신 네트워크 (PSTN) 게이트웨이에 대 한 설명서 및 구성 설정을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="6e250-119">Refer to the documentation and configuration settings for your public switched telephone network (PSTN) gateway to determine if you need to enable and define port values TLS, TCP or both.</span></span> <span data-ttu-id="6e250-120">TLS는 중재 서버와 PSTN 게이트웨이 간의 트래픽을 암호화 하는 인증서를 사용 하 여 보다 안전한 프로토콜입니다.</span><span class="sxs-lookup"><span data-stu-id="6e250-120">TLS is a more secure protocol, using certificates to encrypt the traffic between the Mediation Server and the PSTN gateway.</span></span> <span data-ttu-id="6e250-121">일부 PSTN 게이트웨이가 TLS를 지원 하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6e250-121">Not all PSTN gateways support TLS.</span></span>

- <span data-ttu-id="6e250-122">배포에 대해 정의 되 고 구성 되는 SIP trunks 목록과 게이트웨이가 나열 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e250-122">A listing of SIP trunks and the gateways that are defined and configured for your deployment is listed.</span></span> <span data-ttu-id="6e250-123">항목이 없는 경우에는 배포에 대해 구성 된 SIP trunks 또는 PSTN 게이트웨이를 포함 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6e250-123">If no entries are present, there are no SIP trunks or PSTN gateways configured for your deployment.</span></span> <span data-ttu-id="6e250-124">토폴로지 작성기에서 **공유 구성 요소** 아래에 trunks 및 게이트웨이를 정의 하 고 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e250-124">You define and configure trunks and gateways under **Shared Components** in Topology Builder.</span></span>

## <a name="see-also"></a><span data-ttu-id="6e250-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6e250-125">See also</span></span>

[<span data-ttu-id="6e250-126">SIP 트렁크 개요</span><span class="sxs-lookup"><span data-stu-id="6e250-126">Overview of SIP Trunking</span></span>](https://technet.microsoft.com/library/204f2c21-436f-4b2d-93ea-d6db98fa2952.aspx)

[<span data-ttu-id="6e250-127">PSTN 게이트웨이 배포 옵션</span><span class="sxs-lookup"><span data-stu-id="6e250-127">PSTN Gateway Deployment Options</span></span>](https://technet.microsoft.com/library/d1ab4f74-18aa-40c7-a8cf-ec806cf6e28a.aspx)
