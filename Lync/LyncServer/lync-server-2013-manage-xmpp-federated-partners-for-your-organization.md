---
title: 'Lync Server 2013: 조직의 XMPP 페더레이션 파트너 관리'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Manage XMPP federated partners for your organization
ms:assetid: 48681433-725d-457f-926b-f91d95bcf082
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552450(v=OCS.15)
ms:contentKeyID: 48679561
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1ea1e2993ed168ece718864f4167815e799605d4
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42028949"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="manage-xmpp-federated-partners-in-lync-server-2013"></a><span data-ttu-id="5a40c-102">Lync Server 2013에서 XMPP 페더레이션 파트너 관리</span><span class="sxs-lookup"><span data-stu-id="5a40c-102">Manage XMPP federated partners in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5a40c-103">_**마지막으로 수정 된 항목:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="5a40c-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="5a40c-104">이 내용은 예비 설명서 이며 변경 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5a40c-104">This is preliminary documentation and is subject to change.</span></span> <span data-ttu-id="5a40c-105">빈 항목은 자리 표시자로 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5a40c-105">Blank topics are included as placeholders.</span></span>

<span data-ttu-id="5a40c-106">XMPP 페더레이션 도메인의 사용자에 대한 지원을 관리하려면 다음을 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a40c-106">To manage support for users of XMPP federated domains, you need to do the following:</span></span>

  - <span data-ttu-id="5a40c-107">XMPP 페더레이션 도메인의 사용자를 지원하도록 하나 이상의 외부 액세스 정책을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="5a40c-107">Configure one or more external access policies to support users of XMPP federated domains.</span></span>

  - <span data-ttu-id="5a40c-108">페더레이션을 지원하도록 액세스 에지 구성 정책을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="5a40c-108">Configure Access Edge Configuration policy to support federation.</span></span>

  - <span data-ttu-id="5a40c-109">XMPP 페더레이션 파트너 정의를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="5a40c-109">Create XMPP Federated Partners definitions.</span></span>

  - <span data-ttu-id="5a40c-110">XMPP 페더레이션에 사용할 수 있는 협상 설정을 이해합니다.</span><span class="sxs-lookup"><span data-stu-id="5a40c-110">Understand negotiation settings available for XMPP federation.</span></span>

<span data-ttu-id="5a40c-111">이 섹션의 절차를 사용하여 이러한 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5a40c-111">To perform these tasks, use the procedures in this section.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="5a40c-112">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="5a40c-112">In This Section</span></span>

  - [<span data-ttu-id="5a40c-113">Lync Server 2013에서 XMPP 파트너 구성 만들기 또는 편집</span><span class="sxs-lookup"><span data-stu-id="5a40c-113">Create or edit XMPP partner configuration in Lync Server 2013</span></span>](lync-server-2013-create-or-edit-xmpp-partner-configuration.md)

  - [<span data-ttu-id="5a40c-114">Lync Server 2013의 XMPP 페더레이션 파트너에 대 한 협상 설정</span><span class="sxs-lookup"><span data-stu-id="5a40c-114">Negotiation settings for XMPP federated partners in Lync Server 2013</span></span>](lync-server-2013-negotiation-settings-for-xmpp-federated-partners.md)

  - [<span data-ttu-id="5a40c-115">Lync Server 2013의 XMPP 구성 예-Google 대화를 사용한 XMPP 페더레이션</span><span class="sxs-lookup"><span data-stu-id="5a40c-115">Example XMPP configuration in Lync Server 2013 – XMPP federation with Google Talk</span></span>](lync-server-2013-example-xmpp-configuration-–-xmpp-federation-with-google-talk.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

