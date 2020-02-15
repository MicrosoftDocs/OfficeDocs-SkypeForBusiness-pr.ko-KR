---
title: 'Lync Server 2013: Exchange UM (통합 메시징) 지원'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Exchange Unified Messaging (UM) support
ms:assetid: 0da62b8d-7416-4fb8-a405-381ca805c53a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398179(v=OCS.15)
ms:contentKeyID: 48183405
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0e906b6194572d0ed7f797a2be64c7b66982436b
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42035080"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="exchange-unified-messaging-um-support-in-lync-server-2013"></a><span data-ttu-id="25c3c-102">Lync Server 2013의 Exchange UM (통합 메시징) 지원</span><span class="sxs-lookup"><span data-stu-id="25c3c-102">Exchange Unified Messaging (UM) support in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="25c3c-103">_**마지막으로 수정 된 항목:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="25c3c-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="25c3c-104">Lync Server 2013에서는 음성 메시징 및 전자 메일 메시징을 단일 메시징 인프라로 결합할 때 Exchange UM (통합 메시징)과의 통합을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="25c3c-104">Lync Server 2013 supports integration with Exchange Unified Messaging (UM) for combining voice messaging and email messaging into a single messaging infrastructure.</span></span> <span data-ttu-id="25c3c-105">Exchange 2013에서 Exchange UM은 사서함 서버에서 설치 되 고 실행 되는 Exchange UM 서비스와 클라이언트 액세스 서버에서 설치 되 고 실행 되는 UM 통화 라우터에 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="25c3c-105">In Exchange 2013, Exchange UM consists of the Exchange UM service, which is installed and runs on the Mailbox server, and the UM Call Router, which is installed and runs on the Client Access server.</span></span> <span data-ttu-id="25c3c-106">Lync Server 2013 Enterprise Voice 배포에서 Exchange UM은 음성 메시징 및 전자 메일 메시징을 전화 (Outlook Voice Access) 또는 컴퓨터에서 액세스할 수 있는 단일 저장소에 결합 합니다.</span><span class="sxs-lookup"><span data-stu-id="25c3c-106">For Lync Server 2013 Enterprise Voice deployments, Exchange UM combines voice messaging and email messaging into a single store that is accessible from a telephone (that is, Outlook Voice Access) or a computer.</span></span> <span data-ttu-id="25c3c-107">Exchange UM 및 Lync Server 2013는 회사 음성 사용자에 게 전화 응답, Outlook Voice Access 및 자동 전화 교환 서비스를 제공 하기 위해 함께 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="25c3c-107">Exchange UM and Lync Server 2013 work together to provide call answering, Outlook Voice Access, and auto attendant services to users of Enterprise Voice.</span></span>

<span data-ttu-id="25c3c-108">Exchange UM의 온-프레미스 배포와의 통합을 지 원하는 것 외에도 Lync Server 2013은 호스팅된 Exchange UM과의 통합을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="25c3c-108">In addition to the support for integration with on-premises deployments of Exchange UM, Lync Server 2013 supports integration with hosted Exchange UM.</span></span> <span data-ttu-id="25c3c-109">따라서 일부 또는 모든 사용자를 Microsoft Exchange Online 등의 호스팅된 Exchange 서비스 공급자로 마이그레이션하는 경우 해당 사용자에게 음성 메시지를 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25c3c-109">This enables you to provide voice messaging to your users if you migrate some or all of them to a hosted Exchange service provider such as Microsoft Exchange Online.</span></span>

<span data-ttu-id="25c3c-110">Lync Server 2013에서는 다음 버전을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="25c3c-110">Lync Server 2013 supports the following versions:</span></span>

  - <span data-ttu-id="25c3c-111">Microsoft Exchange 2013</span><span class="sxs-lookup"><span data-stu-id="25c3c-111">Microsoft Exchange 2013</span></span>

  - <span data-ttu-id="25c3c-112">Microsoft Exchange Server 2010 (필수) 또는 최신 서비스 팩 (권장)</span><span class="sxs-lookup"><span data-stu-id="25c3c-112">Microsoft Exchange Server 2010 (required) or with latest service pack (recommended)</span></span>

  - <span data-ttu-id="25c3c-113">Microsoft Exchange Server 2007 서비스 팩 1 (SP1) (필수) 또는 최신 서비스 팩 (권장)</span><span class="sxs-lookup"><span data-stu-id="25c3c-113">Microsoft Exchange Server 2007 with Service Pack 1 (SP1) (required) or latest service pack (recommended)</span></span>

<span data-ttu-id="25c3c-114">Exchange UM은 Lync Server 2013 또는 Lync Server 2013 데이터베이스와 함께 배치할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="25c3c-114">You cannot collocate Exchange UM with Lync Server 2013 or a Lync Server 2013 database.</span></span> <span data-ttu-id="25c3c-115">별도의 포리스트에 Exchange UM 및 Lync Server 2013을 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25c3c-115">You can install Exchange UM and Lync Server 2013 in separate forests.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="25c3c-116">Pbx는 모든 사용자에 게 계속 해 서 음성 메일 및 관련 서비스를 제공할 수 있으므로 PBX가 배포 된 Enterprise Voice 배포에는 Exchange UM이 필요 하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25c3c-116">Exchange UM may not be required for Enterprise Voice deployments that have a PBX deployed, because the PBX can continue to provide voice mail and related services to all users.</span></span> <span data-ttu-id="25c3c-117">예를 들어 PSTN (공중 전화망) 연결에 대 한 SIP 트렁크를 배포 하는 경우 pbx를 나중에 사용 중지 하는 경우 이전에 PBX 음성 메일 시스템을 사용한 사용자에 게 음성 메일을 제공 하도록 Exchange UM을 다시 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="25c3c-117">If you eventually retire the PBX (for example, if you deploy SIP trunking for public switched telephone network (PSTN) connectivity), you must reconfigure Exchange UM to provide voice mail to users who previously used the PBX voice mail system.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="25c3c-118">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="25c3c-118">In This Section</span></span>

  - [<span data-ttu-id="25c3c-119">Lync Server 2013의 온-프레미스 통합 메시징에 대 한 구성 요소 및 토폴로지</span><span class="sxs-lookup"><span data-stu-id="25c3c-119">Components and topologies for on-premises Unified Messaging in Lync Server 2013</span></span>](lync-server-2013-components-and-topologies-for-on-premises-unified-messaging.md)

  - [<span data-ttu-id="25c3c-120">Lync Server 2013의 호스팅된 Exchange UM 통합 지원</span><span class="sxs-lookup"><span data-stu-id="25c3c-120">Support for hosted Exchange UM integration in Lync Server 2013</span></span>](lync-server-2013-support-for-hosted-exchange-um-integration.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

