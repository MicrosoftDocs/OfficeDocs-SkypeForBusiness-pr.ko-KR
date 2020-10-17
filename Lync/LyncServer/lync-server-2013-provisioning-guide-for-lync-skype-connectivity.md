---
title: 'Lync Server 2013: Lync-Skype 연결을 위한 프로 비전 가이드'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Provisioning guide for Lync-Skype connectivity
ms:assetid: 69adda9b-5b72-4538-9be6-079b2f462e09
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn440173(v=OCS.15)
ms:contentKeyID: 57793363
ms.date: 11/26/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 073d7c583c6d159e1b262421e441a56c9d081928
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48513165"
---
# <a name="provisioning-guide-for-lync-skype-connectivity-in-lync-server-2013"></a><span data-ttu-id="94628-102">Lync Server 2013의 Lync-Skype 연결에 대 한 프로 비전 가이드</span><span class="sxs-lookup"><span data-stu-id="94628-102">Provisioning guide for Lync-Skype connectivity in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="94628-103">_**마지막으로 수정 된 항목:** 2014-11-26_</span><span class="sxs-lookup"><span data-stu-id="94628-103">_**Topic Last Modified:** 2014-11-26_</span></span>

<span data-ttu-id="94628-104">Lync Server 2013는 Skype와의 연결을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="94628-104">Lync Server 2013 supports connectivity with Skype.</span></span> <span data-ttu-id="94628-105">이 연결은 Lync 2013 사용자가 Skype 사용자의 Microsoft 계정 (MSA)을 사용 하 여 Skype 연락처를 추가할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="94628-105">This connectivity enables your Lync 2013 users to add Skype contacts by using the Skype user’s Microsoft Account (MSA).</span></span> <span data-ttu-id="94628-106">또한 Skype 클라이언트는 대화 상대 목록에 Lync 사용자를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="94628-106">Skype clients can also add Lync users to their contact list.</span></span> <span data-ttu-id="94628-107">Lync Server에서 관리적으로 설정 된 정책에 따라 Lync 및 Skype 사용자는 인스턴트 메시징을 사용 하 여 통신 하 고, 서로의 현재 상태를 확인 하 고, 오디오 및 비디오 통화를 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="94628-107">Based on policies administratively set in Lync Server, Lync and Skype users will be able to communicate using instant messaging, see each other’s presence, and initiate audio and video calls.</span></span> <span data-ttu-id="94628-108">Lync-Skype 연결은 Lync Online의 기능 이기도 하며 Microsoft 365 관리 센터 내의 Lync 관리 센터에서 Lync Online 고객에 대해 사용 하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="94628-108">Lync-Skype connectivity is also a feature of Lync Online, and can be enabled for Lync Online customers from the Lync Administration Center within the Microsoft 365 admin center.</span></span>

<div>

> [!IMPORTANT]  
> <span data-ttu-id="94628-109">Lync Server가 공용 im (인스턴트 메시징 연결)을 사용 하 여 Windows Messenger에 연결 되도록 이미 구성 되어 있는 경우 배포가 이미 Lync-Skype 연결을 위해 구성 된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="94628-109">If Lync Server is already configured to connect with Windows Messenger by using Public Instant Messaging Connectivity (PIC), your deployment is already configured for Lync-Skype connectivity.</span></span> <span data-ttu-id="94628-110">기존 Messenger PIC 항목 이름을 Skype로 변경 하는 것이 고려할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="94628-110">The only change you may want to consider is to rename your existing Messenger PIC entry as Skype.</span></span> <span data-ttu-id="94628-111">자세한 내용은이 가이드 뒷부분에 나오는 Lync의 Skype PIC 공급자 설정 구성을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="94628-111">For details, see Configure the Skype PIC provider setting for Lync later in this guide.</span></span>

</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="94628-112">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="94628-112">In This Section</span></span>

  - [<span data-ttu-id="94628-113">Lync Online 고객에 대 한 Lync Server 2013의 Lync-Skype 연결에 대 한 참고 사항</span><span class="sxs-lookup"><span data-stu-id="94628-113">Note about Lync-Skype connectivity in Lync Server 2013 for Lync Online customers</span></span>](lync-server-2013-note-about-lync-skype-connectivity-for-lync-on.md)

  - [<span data-ttu-id="94628-114">Lync Server 2013에서 Lync Server 공용 IM 연결 프로 비전 사이트 액세스</span><span class="sxs-lookup"><span data-stu-id="94628-114">Accessing the Lync Server public IM connectivity provisioning site from Lync Server 2013</span></span>](lync-server-2013-accessing-the-lync-server-public-im-connectivity-provisioning-site.md)

  - [<span data-ttu-id="94628-115">Lync Server 2013에서 Lync-Skype 연결 사용</span><span class="sxs-lookup"><span data-stu-id="94628-115">Enabling Lync-Skype connectivity in Lync Server 2013</span></span>](lync-server-2013-enabling-lync-skype-connectivity.md)

  - [<span data-ttu-id="94628-116">최종 사용자로 Lync Server 2013에서 Lync-Skype 연결 사용</span><span class="sxs-lookup"><span data-stu-id="94628-116">Using Lync-Skype connectivity in Lync Server 2013 as an end user</span></span>](lync-server-2013-using-lync-skype-connectivity-as-an-end-user.md)

  - [<span data-ttu-id="94628-117">질문과 대답: Skype 연결용 Lync Server 2013 프로 비전</span><span class="sxs-lookup"><span data-stu-id="94628-117">Frequently Asked Questions: Provisioning Lync Server 2013 for Skype connectivity</span></span>](lync-server-2013-frequently-asked-questions-provisioning-lync-server-for-skype-connectivity.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

