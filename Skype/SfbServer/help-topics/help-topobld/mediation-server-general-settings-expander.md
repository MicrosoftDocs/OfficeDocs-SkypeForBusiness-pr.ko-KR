---
title: 중재 서버 일반 설정 확장기
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 4/14/2015
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.MediationServerGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0e0ad9f0-27d5-4975-ae88-0b8ff8a4c514
ms.openlocfilehash: 68ce332b0db24147121f66ed88725518abb2c464
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36190176"
---
# <a name="mediation-server-general-settings-expander"></a><span data-ttu-id="9ff28-102">중재 서버 일반 설정 확장기</span><span class="sxs-lookup"><span data-stu-id="9ff28-102">Mediation Server General Settings Expander</span></span>
 


## <a name="general-settings"></a><span data-ttu-id="9ff28-103">일반 설정</span><span class="sxs-lookup"><span data-stu-id="9ff28-103">General settings</span></span>

<span data-ttu-id="9ff28-104">중재 서버 풀 또는 중재 서버의 FQDN (정규화 된 도메인 이름)입니다.</span><span class="sxs-lookup"><span data-stu-id="9ff28-104">Fully qualified domain name (FQDN) of the Mediation Server pool or Mediation Server.</span></span> <span data-ttu-id="9ff28-105">값을 변경하려면 서버의 FQDN을 편집합니다.</span><span class="sxs-lookup"><span data-stu-id="9ff28-105">Edit the FQDN of the server to change the value.</span></span> <span data-ttu-id="9ff28-106">새 값과 일치하는 DNS(Domain Name System) 호스트(A) 레코드가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ff28-106">You must have a Domain Name System (DNS) host (A) record that coincides with the new value.</span></span>
  
<span data-ttu-id="9ff28-107">**연결** 섹션에서 edge 서버 또는 edge 서버 풀을 선택 하 여 조정 서버 풀 또는 중재 서버와 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ff28-107">In the **Associations** section, you select an Edge Server or Edge Server pool to associate with the Mediation Server pool or Mediation Server.</span></span> <span data-ttu-id="9ff28-108">중재 서버의 미디어 구성 요소가 외부 사용자 엔터프라이즈 음성에 사용할 가장자리를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ff28-108">You select the Edge that the Mediation Server's media components will use for External user Enterprise Voice.</span></span>
  
<span data-ttu-id="9ff28-109">현재 정의 된 Edge 서버가 없고 조정 서버를 Edge 서버와 연결 해야 하는 경우 새로 **만들기** 를 클릭 하 고 새 Edge 풀 정의 마법사에서 새 edge 서버 또는 Edge 서버 풀을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ff28-109">If you do not have an Edge Server currently defined and need to associate the Mediation Server with an Edge Server, click **New** and define the new Edge Server or Edge Server pool in the Define the New Edge pool wizard.</span></span>
  
## <a name="next-hop-settings"></a><span data-ttu-id="9ff28-110">다음 홉 설정</span><span class="sxs-lookup"><span data-stu-id="9ff28-110">Next hop settings</span></span>

<span data-ttu-id="9ff28-111">드롭다운 목록에서 정의 된 Enterprise Edition 프런트 엔드 풀 또는 Standard Edition 프런트 엔드 서버를 선택 하 여 다음 홉을 조정 서버 풀 또는 중재 서버로 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ff28-111">You specify the Mediation Server pool or Mediation Server next hop by selecting the defined Enterprise Edition Front End pool or Standard Edition Front End Server from the drop-down list.</span></span> <span data-ttu-id="9ff28-112">디렉터 또는 디렉터 풀은 중재 서버 풀 또는 중재 서버 다음 홉에 대해 유효한 선택이 아니므로 목록에 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9ff28-112">A Director or Director pool is not a valid selection for a Mediation Server pool or Mediation Server next hop, and will not appear in the list.</span></span> <span data-ttu-id="9ff28-113">**확인** 을 클릭 하 여 변경 내용을 적용 하 고 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ff28-113">Click **OK** to accept and save your changes.</span></span> <span data-ttu-id="9ff28-114">변경 내용을 취소하고 속성 페이지를 끝내려면 **취소**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="9ff28-114">Click **Cancel** to discard your changes and exit the properties page.</span></span>
  
## <a name="pstn-gateway-settings"></a><span data-ttu-id="9ff28-115">PSTN 게이트웨이 설정</span><span class="sxs-lookup"><span data-stu-id="9ff28-115">PSTN gateway settings</span></span>

1. <span data-ttu-id="9ff28-116">중재 서버 풀 또는 중재 서버와 연결 되는 PSTN 게이트웨이를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ff28-116">You define PSTN gateways that are associated with the Mediation Server pool or Mediation Server.</span></span> <span data-ttu-id="9ff28-117">이미 게이트웨이를 정의한 경우 중재 서버와 연결 하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ff28-117">If you have already defined gateways, they will be available to associate with the Mediation Server.</span></span> <span data-ttu-id="9ff28-118">중재 서버 배치를 사용하도록 설정하면 TLS(전송 계층 보안)를 사용하도록 풀 서버의 수신 대기 포트 범위를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="9ff28-118">If you enable the collocation of the Mediation Server, define the listening port range on the pool servers for Transport Layer Security (TLS).</span></span> <span data-ttu-id="9ff28-119">기본적으로 이 포트는 5067입니다.</span><span class="sxs-lookup"><span data-stu-id="9ff28-119">By default, this port is 5067.</span></span> <span data-ttu-id="9ff28-120">**TCP 포트 사용**을 선택하면 배치된 중재 서버의 TCP(Transmission Control Protocol) 포트를 정의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ff28-120">If you select **Enable TCP port**, you must define a Transmission Control Protocol (TCP) port for the collocated Mediation Server.</span></span> <span data-ttu-id="9ff28-121">이는 선택적 설정이며 이 설정이 필요한지 여부는 게이트웨이 또는 PSTN 요구 사항을 참조하여 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ff28-121">This is an optional setting, and you should refer to the requirements of your gateway or PSTN requirements to determine if you need this.</span></span> <span data-ttu-id="9ff28-122">기본적으로 TCP 포트 값은 5068입니다.</span><span class="sxs-lookup"><span data-stu-id="9ff28-122">By default, the TCP port value is 5068.</span></span>
    
2. <span data-ttu-id="9ff28-p105">배치된 중재 서버와 연결된 트렁크를 정의합니다. 이미 트렁크를 정의한 경우 해당 트렁크를 중재 서버와 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ff28-p105">Trunks that are associated with the collocated Mediation Server. If you have already defined trunks, they will be available to associate with the Mediation Server.</span></span> 
    
3. <span data-ttu-id="9ff28-125">중재 서버와 연결 된 트렁크가 두 개 이상 있는 경우 트렁크를 선택한 다음 **기본값 만들기**를 클릭 하 여 기본 트렁크를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ff28-125">If you have more than one trunk associated with a Mediation Server, you can specify a default trunk by selecting the trunk and then clicking **Make Default**.</span></span> <span data-ttu-id="9ff28-126">기본값으로 설정한 게이트웨이의 선택을 취소하려면 **기본값으로 설정 안 함**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="9ff28-126">To unselect a gateway as the default, click **Unmake Default**.</span></span> 
    

