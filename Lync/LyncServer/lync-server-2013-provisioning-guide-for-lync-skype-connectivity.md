---
title: 'Lync Server 2013: Lync-Skype 연결에 대한 프로비전 가이드'
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
ms.openlocfilehash: f94da566e4322f9b8d1d039441c561f5ed60f6c2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41747218"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="provisioning-guide-for-lync-skype-connectivity-in-lync-server-2013"></a><span data-ttu-id="a1440-102">Lync Server 2013의 Lync-Skype 연결에 대한 프로비전 가이드</span><span class="sxs-lookup"><span data-stu-id="a1440-102">Provisioning guide for Lync-Skype connectivity in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a1440-103">_**마지막으로 수정한 주제:** 2014-11-26_</span><span class="sxs-lookup"><span data-stu-id="a1440-103">_**Topic Last Modified:** 2014-11-26_</span></span>

<span data-ttu-id="a1440-p101">Lync Server 2013에서는 Skype와의 연결이 지원됩니다. 이 연결을 통해 Lync 2013 사용자는 Skype 사용자의 MSA(Microsoft 계정)를 사용하여 Skype 대화 상대를 추가할 수 있습니다. Skype 클라이언트가 Lync 사용자를 대화 상대 목록에 추가할 수도 있습니다. Lync Server에서 관리자 권한으로 설정된 정책을 기반으로 Lync 및 Skype 사용자는 메신저를 사용해 통신하고, 서로의 현재 상태를 확인하고, 오디오 및 비디오 통화를 시작할 수 있습니다. Lync-Skype 연결은 Lync Online의 기능이기도 하며 Office 365 포털 내의 Lync 관리 센터에서 Lync Online 고객도 사용하도록 설정될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1440-p101">Lync Server 2013 supports connectivity with Skype. This connectivity enables your Lync 2013 users to add Skype contacts by using the Skype user’s Microsoft Account (MSA). Skype clients can also add Lync users to their contact list. Based on policies administratively set in Lync Server, Lync and Skype users will be able to communicate using instant messaging, see each other’s presence, and initiate audio and video calls. Lync-Skype connectivity is also a feature of Lync Online, and can be enabled for Lync Online customers from the Lync Administration Center within the Office 365 portal.</span></span>

<div>

> [!IMPORTANT]  
> <span data-ttu-id="a1440-p102">Lync Server가 PIC(공용 메신저 연결)를 사용하여 Windows Messenger와 연결하도록 이미 구성된 경우 해당 배포는 Lync-Skype 연결에 맞게 이미 구성되어 있습니다. 따라서 사용자는 기존 메신저 PIC 항목의 이름을 Skype로 바꿀 것인지만 고려할 수 있습니다. 자세한 내용은 이 가이드 뒷부분에 나오는 "Lync에 대해 Skype PIC 공급자 설정 구성"을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a1440-p102">If Lync Server is already configured to connect with Windows Messenger by using Public Instant Messaging Connectivity (PIC), your deployment is already configured for Lync-Skype connectivity. The only change you may want to consider is to rename your existing Messenger PIC entry as Skype. For details, see Configure the Skype PIC provider setting for Lync later in this guide.</span></span>

</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="a1440-112">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="a1440-112">In This Section</span></span>

  - [<span data-ttu-id="a1440-113">Lync Online 고객을 위한 lync Server 2013의 Lync-Skype 연결에 대 한 참고 사항</span><span class="sxs-lookup"><span data-stu-id="a1440-113">Note about Lync-Skype connectivity in Lync Server 2013 for Lync Online customers</span></span>](lync-server-2013-note-about-lync-skype-connectivity-for-lync-on.md)

  - [<span data-ttu-id="a1440-114">Lync Server 2013에서 Lync Server 공용 메신저 연결 프로비저닝 사이트에 액세스</span><span class="sxs-lookup"><span data-stu-id="a1440-114">Accessing the Lync Server public IM connectivity provisioning site from Lync Server 2013</span></span>](lync-server-2013-accessing-the-lync-server-public-im-connectivity-provisioning-site.md)

  - [<span data-ttu-id="a1440-115">Lync Server 2013에서 Lync-Skype 연결 사용</span><span class="sxs-lookup"><span data-stu-id="a1440-115">Enabling Lync-Skype connectivity in Lync Server 2013</span></span>](lync-server-2013-enabling-lync-skype-connectivity.md)

  - [<span data-ttu-id="a1440-116">최종 사용자로서 Lync Server 2013에서 Lync-Skype 연결 사용</span><span class="sxs-lookup"><span data-stu-id="a1440-116">Using Lync-Skype connectivity in Lync Server 2013 as an end user</span></span>](lync-server-2013-using-lync-skype-connectivity-as-an-end-user.md)

  - [<span data-ttu-id="a1440-117">질문과 대답: Skype 연결을 위한 Lync Server 2013 프로비전</span><span class="sxs-lookup"><span data-stu-id="a1440-117">Frequently Asked Questions: Provisioning Lync Server 2013 for Skype connectivity</span></span>](lync-server-2013-frequently-asked-questions-provisioning-lync-server-for-skype-connectivity.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

