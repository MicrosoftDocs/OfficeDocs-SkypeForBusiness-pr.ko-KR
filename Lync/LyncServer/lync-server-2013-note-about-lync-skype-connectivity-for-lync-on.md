---
title: 'Lync Server 2013: lync 온 lync-Skype 연결에 대 한 참고 사항'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Note about Lync-Skype connectivity for Lync On
ms:assetid: 1d0f5c1a-74c6-468f-9877-ad2b1ddf355f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn440169(v=OCS.15)
ms:contentKeyID: 57793359
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: de54cbdde864da5600c06b608344e8593529d604
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "43780707"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="note-about-lync-skype-connectivity-in-lync-server-2013-for-lync-online-customers"></a><span data-ttu-id="b77c1-102">Lync Online 고객에 대 한 lync Server 2013의 Lync Skype 연결에 대 한 참고 사항</span><span class="sxs-lookup"><span data-stu-id="b77c1-102">Note about Lync-Skype connectivity in Lync Server 2013 for Lync Online customers</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b77c1-103">_**마지막으로 수정 된 항목:** 2013-09-23_</span><span class="sxs-lookup"><span data-stu-id="b77c1-103">_**Topic Last Modified:** 2013-09-23_</span></span>

<span data-ttu-id="b77c1-104">이 문서는 Lync Server 온-프레미스 관리자가 Lync Skype 연결을 설정 하도록 지원 하기 위해 작성 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="b77c1-104">This document was written to help Lync Server on-premise administrators set up Lync-Skype connectivity.</span></span><span data-ttu-id="b77c1-105">Lync Online의 기능으로는 Office 365의 일부인 lync 온라인 기능도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b77c1-105">  Lync-Skype connectivity is also a feature of Lync Online, which is part of Office 365.</span></span> <span data-ttu-id="b77c1-106">Microsoft 365 관리 센터 내의 Lync 관리 센터에서 Lync-Skype 연결 기능을 사용 하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b77c1-106">You can enable the Lync-Skype connectivity feature from the Lync Administration Center within the Microsoft 365 admin center.</span></span>

<span data-ttu-id="b77c1-107">Office 365 중간 규모 비즈니스, Office 365 Enterprise, Office 365 교육 및 정부용 Office 365: Microsoft 365 관리 센터에 로그인 하 여 **Lync 관리 센터로**이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="b77c1-107">For Office 365 Midsize Business, Office 365 Enterprise, Office 365 Education, and Office 365 for Government: Sign in to the Microsoft 365 admin center and navigate to the **Lync Administration Center**.</span></span> <span data-ttu-id="b77c1-108">**외부 통신**으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="b77c1-108">Go to **External Communications**.</span></span> <span data-ttu-id="b77c1-109">**공용 IM 서비스 공급자**아래에서 **사용**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="b77c1-109">Under **Public IM Service Providers**, click **Enable**.</span></span> <span data-ttu-id="b77c1-110">Lync-Skype 연결에 대 한 개별 사용자 액세스를 제어 하려는 경우 개별 사용자의 외부 통신 설정을 편집 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b77c1-110">If you want to control individual user access to Lync-Skype Connectivity, you can do so by editing individual users’ External Communications settings.</span></span>

<span data-ttu-id="b77c1-111">Office 365 Small Business Premium의 경우 로그인 하 고 \*\* \> 관리 서비스 설정 \> 인스턴트 메시징, 모임 및 회의\*\*로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="b77c1-111">For Office 365 Small Business Premium: Sign in, and go to **Admin \> Service Settings \> Instant messaging, meetings and conferencing**.</span></span> <span data-ttu-id="b77c1-112">외부 통신을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b77c1-112">Turn on External communications.</span></span> <span data-ttu-id="b77c1-113">외부 통신 스위치는 lync를 사용 하는 다른 조직과의 통신을 모두 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b77c1-113">The External communications switch turns on both Lync-Skype connectivity and communications with other organizations that use Lync.</span></span> <span data-ttu-id="b77c1-114">Lync Online 사용을 시작한 시점에 따라 "설정" 상태의 외부 통신 스위치는 초기에 다른 Lync 조직과의 통신을 활성화 했다는 것을 나타낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b77c1-114">Depending on when you started using Lync Online, the External communications switch in an "on" state may initially indicate only that communications with other Lync organizations is activated.</span></span> <span data-ttu-id="b77c1-115">Lync-Skype 연결을 켜려면 스위치를 껐다가 다시 설정 하기만 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b77c1-115">To turn on Lync-Skype Connectivity, simply toggle the switch off and then back on again.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

