---
title: 트렁크 설정 확장기
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.TrunkSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3d00e8f4-e599-4094-a4a1-34fd6e8a5580
ROBOTS: NOINDEX, NOFOLLOW
description: SIP 트렁크에 대한 설정을 편집하거나 수정하려면 다음을 수행합니다.
ms.openlocfilehash: 907348defb35ef872ce36f84e6e6cc7695921529
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51101784"
---
# <a name="trunk-settings-expander"></a><span data-ttu-id="16f39-103">트렁크 설정 확장기</span><span class="sxs-lookup"><span data-stu-id="16f39-103">Trunk Settings Expander</span></span>

<span data-ttu-id="16f39-104">SIP 트렁크에 대한 설정을 편집하거나 수정하려면 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="16f39-104">To edit or modify the settings for a SIP trunk, you do the following:</span></span>

 <span data-ttu-id="16f39-105">**트렁크 이름**: 배포의 SIP 트렁크를 고유하게 식별하는 필수 항목입니다.</span><span class="sxs-lookup"><span data-stu-id="16f39-105">**Trunk name** is a required entry and uniquely identifies the SIP trunk in the deployment.</span></span>

 <span data-ttu-id="16f39-106">**연결된 PSTN 게이트웨이**: 배포에서 정의된 기존 PSTN 게이트웨이를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="16f39-106">**Associated PSTN gateway**: Select an existing PSTN gateway that has been defined in the deployment.</span></span>

 <span data-ttu-id="16f39-p101">**IP/PSTN 게이트웨이용 수신 대기 포트**: 게이트웨이가 요청에 대해 수신 대기할 TCP/IP 포트를 나타냅니다. 게이트웨이의 공급업체에 따라 필요한 값은 다를 수 있지만 기본값은 포트 5067입니다.</span><span class="sxs-lookup"><span data-stu-id="16f39-p101">**Listening port for IP/PSTN gateway**: Indicates what TCP/IP port the gateway will be listening for requests on. The required value may differ, based on the vendor of the gateway, but the default is port 5067.</span></span>

 <span data-ttu-id="16f39-p102">**SIP 전송 프로토콜**: 사용되는 프로토콜은 TCP 또는 TLS입니다. TLS가 기본값입니다. 게이트웨이가 지원하는 프로토콜에 대해서는 게이트웨이 공급업체 설명서를 참조하십시오. 기본값은 TLS이며 게이트웨이에서 TLS를 지원하는 경우 기본값이 보다 안전한 선택으로 간주되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="16f39-p102">**SIP Transport Protocol**: The protocol used is either TCP or TLS. TLS is the default. Refer to the gateway vendor documentation for what you gateway supports. The default is TLS, and should be considered the more secure selection, if the gateway supports TLS.</span></span>

 <span data-ttu-id="16f39-113">**연결된 중재 서버:** SIP 트렁크와 연결하려면 배포에서 기존 중재 서버를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="16f39-113">**Associated Mediation Server**: Select an existing Mediation Server from the deployment to associate with the SIP trunk.</span></span>

> [!NOTE]
> <span data-ttu-id="16f39-114">루트 트렁크만 중재 서버에 연결될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="16f39-114">Only the root trunk can be associated with a Mediation Server.</span></span>

 <span data-ttu-id="16f39-115">**연결된 중재 서버 포트:** 필수 값으로, 중재 서버가 수신하도록 구성된 값으로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="16f39-115">**Associated Mediation Server port**: A required value, this is set to the value that the Mediation Server is configured to listen on.</span></span>

![트렁크 설정 확장기](../../../media/Trunk_Settings_Expander.jpg)

## <a name="see-also"></a><span data-ttu-id="16f39-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="16f39-117">See also</span></span>

[<span data-ttu-id="16f39-118">SIP 트렁크 배포 검사 목록</span><span class="sxs-lookup"><span data-stu-id="16f39-118">SIP Trunking Deployment Checklist</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-sip-trunk-deployment-checklist)

[<span data-ttu-id="16f39-119">SIP 트렁크에 대한 구성 요소 및 토폴로지</span><span class="sxs-lookup"><span data-stu-id="16f39-119">Components and Topologies for SIP Trunking</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-components-and-topologies-for-sip-trunking)