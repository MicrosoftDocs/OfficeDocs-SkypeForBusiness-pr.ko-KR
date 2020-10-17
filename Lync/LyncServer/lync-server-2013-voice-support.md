---
title: Lync Server 2013 음성 지원
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Voice support
ms:assetid: d151caa8-2ee4-4bfa-be53-428570aae1ea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398896(v=OCS.15)
ms:contentKeyID: 48185436
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: af65dd046dfcb902a827d7a61dd1c45f4cbe73d6
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48535425"
---
# <a name="voice-support-in-lync-server-2013"></a><span data-ttu-id="e449f-102">Lync Server 2013의 음성 지원</span><span class="sxs-lookup"><span data-stu-id="e449f-102">Voice support in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e449f-103">_**마지막으로 수정 된 항목:** 2012-06-29_</span><span class="sxs-lookup"><span data-stu-id="e449f-103">_**Topic Last Modified:** 2012-06-29_</span></span>

<span data-ttu-id="e449f-104">배포에 프런트 엔드 풀이 포함 된 경우 Microsoft에서 제공 하는 VoIP (Voice over IP) 솔루션에 대 한 지원을 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e449f-104">If your deployment includes a Front End pool, you can deploy support for Enterprise Voice, the Voice over IP (VoIP) solution offered by Microsoft.</span></span> <span data-ttu-id="e449f-105">VoIP (Voice over IP)는 전통적인 PBX 기반 전화 통신에 대 한 소프트웨어 기반 대안입니다.</span><span class="sxs-lookup"><span data-stu-id="e449f-105">Voice over IP (VoIP) is a software-based alternative to traditional PBX-based telephony.</span></span> <span data-ttu-id="e449f-106">VoIP 통화 환경은 전통적인 전화 통신 환경과 유사 하지만 엔터프라이즈 음성에는 다양 한 통신 및 공동 작업을 가능 하 게 하는 기능이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e449f-106">Although the VoIP call experience is similar to the traditional telephony experience, Enterprise Voice includes features that enable richer communication and collaboration.</span></span> <span data-ttu-id="e449f-107">예를 들어, Enterprise Voice deployment를 구성 하 여 Lync 2013 및 Lync Phone Edition 사용자가 조직의 주소록에 있는 연락처에 대 한 향상 된 현재 상태 정보 또는 위치 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e449f-107">For example, your Enterprise Voice deployment can be configured to make it possible for Lync 2013 and Lync Phone Edition users to view enhanced presence information or location information for contacts in your organization’s address book.</span></span> <span data-ttu-id="e449f-108">일부 Lync server 2013 기능은 다른 Lync Server 2013 작업 및 Exchange UM (통합 메시징)과의 통합을 통해 사용 하도록 설정 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e449f-108">Some Lync Server 2013 features are enabled through integration with other Lync Server 2013 workloads and with Exchange Unified Messaging (UM).</span></span> <span data-ttu-id="e449f-109">Enterprise Voice에서 사용할 수 있는 기능 및 배포를 계획 하는 방법에 대 한 자세한 내용은 계획 설명서의 [Lync Server 2013에서 Enterprise Voice 계획](lync-server-2013-planning-for-enterprise-voice.md) 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="e449f-109">For details about the features and functionality available with Enterprise Voice and how to plan for deployment, see [Planning for Enterprise Voice in Lync Server 2013](lync-server-2013-planning-for-enterprise-voice.md) in the Planning documentation.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="e449f-110">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="e449f-110">In This Section</span></span>

  - [<span data-ttu-id="e449f-111">Lync Server 2013의 SIP 트렁크 지원</span><span class="sxs-lookup"><span data-stu-id="e449f-111">SIP trunking support in Lync Server 2013</span></span>](lync-server-2013-sip-trunking-support.md)

  - [<span data-ttu-id="e449f-112">Lync Server 2013의 직접 SIP 연결 지원</span><span class="sxs-lookup"><span data-stu-id="e449f-112">Direct SIP connections support in Lync Server 2013</span></span>](lync-server-2013-direct-sip-connections-support.md)

  - [<span data-ttu-id="e449f-113">Lync Server 2013의 Exchange UM (통합 메시징) 지원</span><span class="sxs-lookup"><span data-stu-id="e449f-113">Exchange Unified Messaging (UM) support in Lync Server 2013</span></span>](lync-server-2013-exchange-unified-messaging-um-support.md)

  - [<span data-ttu-id="e449f-114">Lync Server 2013의 E9-1-1 지원</span><span class="sxs-lookup"><span data-stu-id="e449f-114">E9-1-1 support in Lync Server 2013</span></span>](lync-server-2013-e9-1-1-support.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

